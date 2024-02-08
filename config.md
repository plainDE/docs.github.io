---
layout: default
title: config.json
nav_order: 4
---


# config.json

## Introduction to config.json
config.json file is located at ~/.config/plainDE/config.json. This file creates automatically with first start of plainPanel by <a href="https://github.com/plainDE/plainBase/blob/main/usr/share/plainDE/tools/genconfig.py">this script</a>. It contains default configuration. config.json can be either edited manually, or by plainControlCenter. Next we will review all properties of config.json.

## Property description
<table>
  <tr>
    <td><b>Name of property</b></td>
    <td><b>Type of value</b></td>
    <td><b>Acceptable value</b></td>
    <td><b>Description</b></td>
    <td><b>Default value</b></td>
  </tr>
  
  <tr>
    <td>accent</td>
    <td>String</td>
    <td>HEX color starting with #</td>
    <td>Sets accent color. This is the color of QListWidget selected items, QPushButtons, etc</td>
    <td>"#376594"</td>
  </tr>
  
  <tr>
    <td>avatar</td>
    <td>String</td>
    <td>Path to an image</td>
    <td>Sets a picture next to your username. If an option is empty, we use 'computer' icon.</td>
    <td><i>Empty</i></td>
  </tr>
  
  <tr>
    <td>useTriangularTabs</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if App Menu tabs should have triangular form.</td>
    <td>true</td>
  </tr>

  <tr>
    <td>autostart</td>
    <td>Array of string</td>
    <td>Array of desktop files (/usr/share/applications/*.desktop; ~/.local/share/applications/*.desktop)</td>
    <td>Sets list of apps that should start with plainPanel automatically</td>
    <td><i>Empty</i></td>
  </tr>

  <tr>
    <td>configVersion</td>
    <td>String</td>
    <td>Version of plainDE</td>
    <td>Sets version to make possible updating config automatically if needed in newer versions. Should not be changed by user.</td>
    <td><i>Installed version of plainDE</i></td>
  </tr>
  
  <tr>
    <td>countPanels</td>
    <td>Int</td>
    <td>1 ~ 4</td>
    <td>Says panel and control center how many panels should be processed. Should not be changed by user (deleted panels are null'ed, so there's no need to change this property).</td>
    <td>4</td>
  </tr>
  
  <tr>
    <td>dateFormat</td>
    <td>String</td>
    <td>d (1~31) <br> dd (01~31) <br> ddd (Mon~Sun) <br> M (1~12) <br> MM (01~12) <br> MMM (Jan~Dec) <br> yy (00~99) <br> yyyy (1970~9999)</td>
    <td>Sets format of the date in datetime applet (if date is not hidden)</td>
    <td>"MMM d"</td>
  </tr>
  
  <tr>
    <td>enableAnimation</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if panel slide animation is required</td>
    <td>true</td>
  </tr>

  <tr>
    <td>enableOveramplification</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Lets you increase volume over 100% (max is 150%). <b>Note. Works only with PulseAudio adjustVolumeMethod</b>.</td>
    <td>false</td>
  </tr>
  
  <tr>
    <td>defaultVolume</td>
    <td>Int</td>
    <td>0 ~ 150</td>
    <td>Sets initial volume set after plainPanel startup.</td>
    <td>40</td>
  </tr>
  
  <tr>
    <td>favApps</td>
    <td>Array of string</td>
    <td>Array of desktop files (/usr/share/applications/*.desktop; ~/.local/share/applications/*.desktop)</td>
    <td>Sets list of apps showed in 'Favorites' tab of App Menu applet</td>
    <td><i>Empty array</i></td>
  </tr>
  
  <tr>
    <td>firstDayOfWeek</td>
    <td>Int</td>
    <td>1 ~ 7</td>
    <td>Sets first day of week in Calendar applet. <a href="https://code.woboq.org/qt5/qtbase/src/corelib/global/qnamespace.h.html#Qt::DayOfWeek">See Qt::DayOfWeek.</a></td>
    <td>1</td>
  </tr>
  
  <tr>
    <td>fontFamily</td>
    <td>String</td>
    <td>Name of the preferred font</td>
    <td>Sets font family in plainPanel, plainControlCenter, plainAbout</td>
    <td>"Open Sans"</td>
  </tr>
  
  <tr>
    <td>fontSize</td>
    <td>Int</td>
    <td>Point size of font</td>
    <td>Sets font size in plainPanel, plainControlCenter, plainAbout</td>
    <td>10</td>
  </tr>
  
  <tr>
    <td>iconTheme</td>
    <td>String</td>
    <td>Name of preferred icon pack</td>
    <td>Sets icons in plainPanel, plainControlCenter. Currently Mint-Y theme is recommended. We use some icons that present only there. Previously we used Adwaita as default, but with GNOME 42 update Adwaita completely stopped following freedesktop.org specifications.</td>
    <td><i>Empty. This property needs to be set after plainDE installation.</i></td>
  </tr>
  
  <tr>
    <td>ipIfname</td>
    <td>String</td>
    <td>Network interface name</td>
    <td>Sets network interface for using with Local IPv4 applet</td>
    <td><i>Empty</i></td>
  </tr>
  
  <tr>
    <td>ipColor</td>
    <td>String</td>
    <td>HEX color starting with #</td>
    <td>Sets color that should be used for showing Local IPv4 address. It is separate from QSS because we use QGraphicsView for showing IP (lets us rotate applet - we use it in vertical panels). It does not support QSS text customization.</td>
    <td>#ffffff</td>
  </tr>
  
  <tr>
    <td>kbLayoutToggle</td>
    <td>String</td>
    <td>Method that will be used for switching keyboard layouts</td>
    <td>Sets keyboard layout toggle method for setxkbmap. See all methods in <a href="https://github.com/plainDE/plainBase/blob/main/usr/share/plainDE/layoutSwitchMethods.json">/usr/share/plainDE/layoutSwitchMethods.json</a></td>
    <td>grp:win_space_toggle</td>
  </tr>
  
  <tr>
    <td>kbLayouts</td>
    <td>String</td>
    <td>Keyboard layouts ISO codes separated by commas (,)</td>
    <td>Sets keyboard layouts list for setxkbmap. See all keyboard layouts in <a href="https://github.com/plainDE/plainBase/blob/main/usr/share/plainDE/layouts.json">/usr/share/plainDE/layouts.json</a></td>
    <td>"us"</td>
  </tr>
  
  <tr>
    <td>menuIcon</td>
    <td>String</td>
    <td>Path to preferrable PNG menu icon</td>
    <td>Sets custom icon for App Menu applet</td>
    <td>"/usr/share/plainDE/menuIcon.png"</td>
  </tr>

  <tr>
    <td>menuIconSize</td>
    <td>Int</td>
    <td>0 ~ 256</td>
    <td>Size of App Menu icon</td>
    <td>16</td>
  </tr>
  
  <tr>
    <td>menuText</td>
    <td>String</td>
    <td>Any string or empty string</td>
    <td>Sets custom text for App Menu applet.</td>
    <td>"Apps"</td>
  </tr>
  
  <tr>
    <td>showDate</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if date should be shown next to time</td>
    <td>true</td>
  </tr>
  
  <tr>
    <td>winListIconSize</td>
    <td>Int</td>
    <td>0 ~ 256</td>
    <td>Sets size of icons in Window List applet</td>
    <td>22</td>
  </tr>
  
  <tr>
    <td>theme</td>
    <td>String</td>
    <td>Preferred theme name (QSS)</td>
    <td>Sets preferred QSS theme name (see available themes at <a href="https://github.com/plainDE/plainBase/tree/main/usr/share/plainDE/styles">/usr/share/plainDE/styles/</a>)</td>
    <td>"gradient-dark.qss"</td>
  </tr>
  
  <tr>
    <td>timeFormat</td>
    <td>String</td>
    <td>h (0~23, 1~12) <br> hh (00~23, 01~12) <br> m (0~59) <br> mm (00~59) <br> s (0~59) <br> ss (00~59) <br> AP (AM/PM) <br> t (timezone)</td>
    <td>Sets time format in datetime applet</td>
    <td>"h:mm AP"</td>
  </tr>
  
  <tr>
    <td>useCountryFlag</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets is country flag should be shown instead of kayboard layout ISO code</td>
    <td>true</td>
  </tr>

  <tr>
    <td>volumeAdjustMethod</td>
    <td>String</td>
    <td>"ALSA" / "PulseAudio"</td>
    <td>Sets which method panel should use for adjusting volume</td>
    <td>"ALSA"</td>
  </tr>

  <tr>
    <td>winListShowTitles</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if window titles should be shown.</td>
    <td>true</td>
  </tr>

  <tr>
    <td>showWeekNumbers</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if week numbers should be shown in QCalendarWidget</td>
    <td>true</td>
  </tr>

  <tr>
    <td>showDesktopNames</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if workspace names should be shown instead of numbers</td>
    <td>false</td>
  </tr>

  <tr>
    <td>secondsUntilPowerOff</td>
    <td>Int</td>
    <td>-1 ~ INT_MAX</td>
    <td>Sets timeout for shutdown, reboot and log out procedures. Value of -1 disables it (only manual confirmation)</td>
    <td>30</td>
  </tr>
</table>

### Panel property description
These properties should be inside of `panel1`, `panel2`, `panel3` or `panel4` property in config.json.
<table>
  <tr>
    <td>applets</td>
    <td>Array of string</td>
    <td>Array of applets (<a href="https://github.com/plainDE/plainPanel/tree/main/applets/appmenu">appmenu</a>, 
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/datetime">datetime</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/kblayout">kblayout</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/localipv4">localipv4</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/battery">battery</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/snitray">snitray</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/mpris">mpris</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/usermenu">usermenu</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/volume">volume</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/windowlist">windowlist</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/workspaces">workspaces</a>,
                          <a href="https://github.com/plainDE/plainPanel/blob/main/panel.cpp#L708">spacer</a>,
                          <a href="https://github.com/plainDE/plainPanel/blob/main/panel.cpp#L717">splitter</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/launcher">launcher:app.desktop / launcher:/path/to/script:/path/to/icon</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/clioutput">clioutput:appletname</a>)<br>
      // follow these links to view source code of every applet
    </td>
    <td>Sets list of applets and their position</td>
    <td>Panel 1: ["appmenu", "spacer", "sni", "battery", "mpris", "volume", "kblayout", "datetime", "splitter", "usermenu"]<br><br>
        Panel 2: ["windowlist", "spacer", "localipv4", "workspaces"]</td>
  </tr>

  <tr>
    <td>backgroundImage</td>
    <td>String</td>
    <td>Path to background image</td>
    <td>Sets background image of panel</td>
    <td><i>Empty</i></td>
  </tr>
  
  <tr>
    <td>expand</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if panel should be full width (using all width of screen)</td>
    <td>true</td>
  </tr>
  
  <tr>
    <td>thickness</td>
    <td>Int</td>
    <td>>= 0</td>
    <td>Sets thickness of panel (height for horizontal one, width for vertical one) in pixels</td>
    <td>28</td>
  </tr>
  
  <tr>
    <td>launcherIconSize</td>
    <td>Int</td>
    <td>>= 0</td>
    <td>Sets size of launchers icons (height and width) in pixels</td>
    <td>22</td>
  </tr>
    
  <tr>
    <td>location</td>
    <td>String</td>
    <td>"top", "bottom", "left" <i>or</i> "right"</td>
    <td>Sets location of panel to top or bottom</td>
    <td>Panel 1: "top"<br><br>Panel 2: "bottom"</td>
  </tr>
  
  <tr>
    <td>opacity</td>
    <td>Float</td>
    <td>0.0 ~ 1.0</td>
    <td>Sets opacity for panel and applets (you must have compositor for this to work!)</td>
    <td>0.85</td>
  </tr>
  
  <tr>
    <td>shift</td>
    <td>Int</td>
    <td>>= 0</td>
    <td>Sets how many pixels the panel should be shifted. `expand` disables this option.</td>
    <td>0</td>
  </tr>

  <tr>
    <td>margin</td>
    <td>Int</td>
    <td>>= 0</td>
    <td>Sets how many pixels should be left on left and right sides (horizontal panel) or on top and bottom (vertical panel)</td>
    <td>5</td>
  </tr>

  <tr>
    <td>screen</td>
    <td>String</td>
    <td>Name of one of the screens</td>
    <td>Sets which monitor will be used for a panel</td>
    <td><i>Empty</i></td>
  </tr>
</table>

## Conclusion
plainControlCenter lets you edit all of this properties, but now you can edit config.json manually if you want.
