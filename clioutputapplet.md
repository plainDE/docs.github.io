# CLI Output Applet Configuration
Since plainDE 0.6 release there is CLI Output applet. It lets you show output of 
a command or data depending on output of a command on the panel.

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
		<td>"stdout" / "condition"</td>
		<td>Sets type of CLI Output applet. <code>stdout</code> - just show
		    output of command. <code>condition</code> - compare command
		    output or exit code with preset conditions and show required data.</td>
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
		<td>waitData</td>
		<td>String</td>
		<td>[IconName];[Text]</td>
		<td>Data that will be set to QLabel while command is running.
		    <b>Note</b> Works only if <code>condition</code> mode is used.</td>
	</tr>
</table>