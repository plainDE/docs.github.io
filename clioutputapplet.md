---
layout: default
title: CLI Output Applet Configuration
nav_order: 7
---

# CLI Output Applet Configuration
Since plainDE 0.6 release there is CLI Output applet. It lets you show output of 
a command or data depending on output of a command on the panel.

<b>Note.</b> plainControlCenter 0.6.1 and upper fully supports CLI Output Applet.

# How to set it up?
CLI Output applet can be configured both using plainControlCenter and manually.
All configs of CLI Output applets are stored in `~/.config/plainDE/clioutput-applets/`
and have JSON format.

## Property description
<table>
	<tr>
		<td>Name of property</td>
		<td>Type of value</td>
		<td>Acceptable value</td>
		<td>Description</td>
	</tr>
	<tr>
		<td>type</td>
		<td>String</td>
		<td>"stdout" / "condition" / "data"</td>
		<td>Sets type of CLI Output applet. <code>stdout</code> - just show
		    output of command. <code>condition</code> - compare command
		    output or exit code with preset conditions and show required data.
		    <code>data</code> - use stdout as Output Data (IconNameOrPath;Text)</td>
	</tr>
	<tr>
		<td>command</td>
		<td>String</td>
		<td>Shell command. Note. Pipes are not supported. Put them in separate script
		    if needed.</td>
		<td>Sets shell command that will be executed to get data.</td>
	</tr>
	<tr>
		<td>interval</td>
		<td>Int</td>
		<td>milliseconds value</td>
		<td>Delay between each update.</td>
	</tr>
	<tr>
		<td>conditionType</td>
		<td>String</td>
		<td>stdout / exitcode</td>
		<td>Criteria that will be used to find matching output data. 
		    <b>Note</b> Works only if <code>condition</code> mode is used.</td>
	</tr>
	<tr>
		<td>conditions</td>
		<td>JsonObject</td>
		<td>Match pair: Criteria -> Output Data</td>
		<td>Sets matching pairs that will be used to find suitable output data.
		    <b>Note</b> Works only if <code>condition</code> mode is used.</td>
	</tr>
	<tr>
		<td>elseCondition</td>
		<td>String</td>
		<td>Output Data</td>
		<td>Sets output data that will be shown if no suitable option was found in previous option.</td>
	</tr>
	<tr>
		<td>waitData</td>
		<td>String</td>
		<td>IconNameOrPath;Text</td>
		<td>Data that will be set to QLabel while command is running.
		    <b>Note</b> Works only if <code>condition</code> mode is used.</td>
	</tr>
</table>

### Config sample
`~/.config/plainDE/clioutput-applets/checkupdates.json`
```
{
	"type": "condition",
	"command": "checkupdates",
	"interval": 3600000,
	"conditionType": "exitcode",
	"conditions": {
		"0": "help-info;Updates available",
		"2": "mail-mark-notjunk;No updates"
	},
	"elseCondition": "gtk-cancel;Failed",
	"waitData": "mail-send-receive;Fetching info"
}
```
P.S. This a real config that checks updates every 1 hour. It works on Arch Linux with installed `pacman-contrib` package.<br><br>
Add `clioutput:[appletname]` in `applets` property of your panel in order to enable this applet. [appletname] is name of a file from ~/.config/plainDE/clioutput-applets/ without `.json` in the end.

Example:
```
'panel1': {
	'applets': [..., 'clioutput:checkupdates'],
	...
}
```

