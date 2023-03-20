# D-Bus Integration

## Introduction
D-Bus is an IPC that lets you interact with programs and transfer data between them with a convenient way. This page shows you D-Bus capabilities of plainDE.

## Description
plainPanel runs 2 D-Bus services: ```org.plainDE.plainPanel``` and ```org.kde.StatusNotifierWatcher```. First one is for interacting with panel directly, second one is for SNI tray applet.

## org.plainDE.plainPanel
This service has 1 interface (```org.plainDE.actions```) on path ```/Actions``` that currently (plainDE 0.5) has 1 method: ```reconfigurePanel```. It helps panel understand that it is required to read config (~/.config/plainDE/config.json) again. We use this method in plainControlCenter to apply settings immediately. However, it can be used by user if they need to reload config now.

In future it is planned to extend capabilities of this service. It will have methods to interact with applets (i.e., toggleAppMenu, toggleCalendar, toggleMPRIS etc). This will provide users with even wider ways to customize desktop and make it more convenient.

## org.kde.StatusNotifierWatcher
### Service description
This service has 1 interface (```org.kde.StatusNotifier```) on path ```/StatusNotifierWatcher``` that has methods and properties connected with tray icons.
Currently it includes:

<table>
  <tr>
    <td>Type of entry</td>
    <td>Entry name</td>
    <td>Description</td>
  </tr>
  
  <tr>
    <td>Property</td>
    <td>IsStatusNotifierHostRegistered</td>
    <td>Returns bool value (true/false) that indicates if StatusNotifierHost is registered in StatusNotifierWatcher.</td>
  </tr>
  
  <tr>
    <td>Property</td>
    <td>RegisteredStatusNotifierItems</td>
    <td>Returns array of strings (QStringList) that contains all registered StatusNotifierItems. Each item is represented via D-Bus service name of the owner.</td>
  </tr>
  
  <tr>
    <td>Signal</td>
    <td>StatusNotifierItemRegistered</td>
    <td>Indicates when a new StatusNotifierItem is registered. We use it for informing panel that a new item is registered and require processing.</td>
  </tr>
  
  <tr>
    <td>Signal</td>
    <td>StatusNotifierItemUnregistered</td>
    <td>Indicates when a new StatusNotifierItem is unregistered. We use it for informing panel that an item is destructed and corresponding icon should be removed.</td>
  </tr>
  
  <tr>
    <td>Signal</td>
    <td>StatusNotifierHostRegistered</td>
    <td>Indicates when StatusNotifierHost is registered in StatusNotifierWatcher.</td>
  </tr>
  
  <tr>
    <td>Method</td>
    <td>RegisterStatusNotifierItem</td>
    <td>Registers a new StatusNotifierItem. The only argument is D-Bus service name of the owner.</td>
  </tr>
  
  <tr>
    <td>Method</td>
    <td>RegisterStatusNotifierHost</td>
    <td>Registers StatusNotifierHost in StatusNotifierWatcher. We use this only because property <code>IsStatusNotifierHostRegistered</code> should be <code>true</code> so apps can add their icon to tray.</td>
  </tr>
  
  <tr>
    <td>Method</td>
    <td>UnregisterStatusNotifierItem</td>
    <td>It <i>should</i> unregister a StatusNotifierItem. Actually, it does nothing because usually, this method is not used. We track a D-Bus service of every program that wants to place an icon to a tray. When the service dissapears, we just remove icon and forget it.</td>
  </tr>
</table>

This interface is compliant with specifications on StatusNotifierWatcher<br>
Check out<br>
<a href="https://github.com/KDE/plasma-workspace/blob/master/xembed-sni-proxy/org.kde.StatusNotifierWatcher.xml">https://github.com/KDE/plasma-workspace/blob/master/xembed-sni-proxy/org.kde.StatusNotifierWatcher.xml</a><br>
<a href="https://www.freedesktop.org/wiki/Specifications/StatusNotifierItem/StatusNotifierWatcher/">https://www.freedesktop.org/wiki/Specifications/StatusNotifierItem/StatusNotifierWatcher/</a>

### How do we get icon for StatusNotifierItem?
We try to get icon with 3 ways. We use them one by one hoping that something will work.
1) Ideal situation is when D-Bus service provide IconName property in <a href="https://www.freedesktop.org/wiki/Specifications/StatusNotifierItem/StatusNotifierItem/">org.kde.StatusNotifierItem</a> interface. We just grab icon from theme.
2) More often app icon is not included in icon packs, so developers have to provide us IconPixmap property which is a byte array. Then we convert it to QImage and finally to QIcon.
3) There are even worse cases, though. Sometimes developers don't provide us neither with IconName, nor with IconPixmap (i.e., JetBrains Toolbox). Then we have last chance to get the icon. We can get Window ID of the app that wants to place an icon. After that we can get icon by Window ID. Please note that this way will work only if application opens window after starting.


# Conclusion
We reviewed all uses of D-Bus in plainDE.
