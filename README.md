# Remote Ninja
Remote control for OBS using a dash of the VDO.Ninja special sauce

Keep this either docked in OBS or loaded on the same computer in a browser window.

https://steveseguin.github.io/remote_ninja/index.html

and 

This link can be accessed by a user to remote control OBS anywhere on the Internet, thanks for VDO.Ninja and OBS websocket plugin/js.

https://steveseguin.github.io/remote_ninja/interface.html


Requires OBS to have the OBS Websockets plugin installed (simple/quick to do).

https://github.com/Palakis/obs-websocket


The provided link is the remote control interface: it works across firewalls, by using VDO.Ninja's IFRAME API to transmit the commands.  It does use websockets also, but only for the last-mile of transport.

Currently, the interface is setup to list available scenes, the active scene, and lets you remotely change between scenes.  It can be easily modified to do anything the websocket API of OBS allows.

If interested in sending other types of data messages across VDO.Ninja, the VDO.Ninja IFRAME API is pretty simple yet powerful:

To send a message,
```
iframe.contentWindow.postMessage({"sendData":msg}, '*');
```
and to receive:
```
window.addEventListener("onmessage"=>
    if ("dataReceived" in e.data){ ... } 
)
```
