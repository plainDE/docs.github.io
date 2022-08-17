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
    <td>applets</td>
    <td>Array of string</td>
    <td>Array of applets (<a href="https://github.com/plainDE/plainPanel/tree/main/applets/appmenu">appmenu</a>, 
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/datetime">datetime</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/kblayout">kblayout</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/localipv4">localipv4</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/usermenu">usermenu</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/volume">volume</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/windowlist">windowlist</a>,
                          <a href="https://github.com/plainDE/plainPanel/tree/main/applets/workspaces">workspaces</a>)</td>
    <td>Sets list of applets and their position</td>
    <td>["appmenu", "windowlist", "spacer", "workspaces", "volume", "kblayout", "datetime", "splitter", "usermenu"]</td>
  </tr>
  
  <tr>
    <td>autostart</td>
    <td>Array of string</td>
    <td>Array of desktop files (/usr/share/applications/*.desktop)</td>
    <td>Sets list of apps that should start with plainPanel automatically</td>
    <td><i>Empty</i></td>
  </tr>
  
  <tr>
    <td>background</td>
    <td>String</td>
    <td>Path to the background image</td>
    <td>Currently unused property</td>
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
    <td>dateFormat</td>
    <td>String</td>
    <td>d - 1-31 <br> dd - 01-31 <br> ddd - Mon-Sun <br> M - 1-12 <br> MM - 01-12 <br> MMM - Jan-Dec <br> yy - 00-99 <br> yyyy - 1970-9999</td>
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
    <td>expandPanel</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if panel should be full width (using all width of screen)</td>
    <td>true</td>
  </tr>
  
  <tr>
    <td>favApps</td>
    <td>Array of string</td>
    <td>Array of desktop files (/usr/share/applications/*.desktop)</td>
    <td>Sets list of apps showed in 'Favorites' tab of App Menu applet</td>
    <td><i>Empty array</i></td>
  </tr>
  
  <tr>
    <td>firstDayOfWeek</td>
    <td>Int</td>
    <td>Number in range from 1 through 7</td>
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
    <td>menuText</td>
    <td>String</td>
    <td>Text shown next to the menu icon</td>
    <td>Sets custom text for App Menu applet. Default value is 'Apps'</td>
    <td>"Apps"</td>
  </tr>
  
  <tr>
    <td>panelHeight</td>
    <td>Int</td>
    <td>Number that represents height of panel in pixels</td>
    <td>Sets height of panel in pixels</td>
    <td>28</td>
  </tr>
  
  <tr>
    <td>panelLocation</td>
    <td>String</td>
    <td>"top" <i>or</i> "bottom"</td>
    <td>Sets location of panel to top or bottom</td>
    <td>"top"</td>
  </tr>
  
  <tr>
    <td>panelOpacity</td>
    <td>Float</td>
    <td>A number in range from 0 through 1</td>
    <td>Sets opacity for panel and applets</td>
    <td>0.85</td>
  </tr>
  
  <tr>
    <td>showDate</td>
    <td>Bool</td>
    <td>true/false</td>
    <td>Sets if date should be shown next to time</td>
    <td>true</td>
  </tr>
  
  <tr>
    <td>theme</td>
    <td>String</td>
    <td>Preferred theme name (QSS)</td>
    <td>Sets preferred QSS theme name (see available themes at <a href="https://github.com/plainDE/plainBase/tree/main/usr/share/plainDE/styles">/usr/share/plainDE/styles/</a>)</td>
    <td>"gradient-light.qss"</td>
  </tr>
  
  <tr>
    <td>timeFormat</td>
    <td>String</td>
    <td>h - 0-23, 1-12 <br> hh - 00-23, 01-12 <br> m - 0-59 <br> mm - 00-59 <br> s - 0-59 <br> ss - 00-59 <br> AP - AM/PM <br> t - timezone</td>
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
    <td>xOffset</td>
    <td>Int</td>
    <td>Number in range from 0 through (screen width - panel width)</td>
    <td>Sets how many pixels the panel should be shifted. Use with `expandPanel` turned off.</td>
    <td>0</td>
  </tr>
  
</table>


## Conclusion
plainControlCenter lets you edit all of this properties, but now you can edit config.json manually if you want.
