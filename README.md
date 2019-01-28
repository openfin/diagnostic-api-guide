# Diagnostic APIs Guide

## Overview
Guide for OpenFin APIs that are useful in diagnostics, debugging, and reporting on your application.  Built on the OpenFin Runtime and [Reveal-js](http://lab.hakim.se/reveal-js/).

### Features
The following information is obtainable through the OpenFin API. These API calls can be beneficial in supporting your applications post deployment.
* **Command Line Arguments** - Retrieves the command line argument string that started OpenFin Runtime
* **Device ID** - Retrieves the UUID of the computer on which the runtime is installed
* **Device User ID** - Returns a hex encoded hash of the mac address and the currently logged in user name
* **Host Specs** - Retrieves system information
* **Log** - Writes the passed message into both the log file and the console
* **Log List** - Retrieves an array containing information for each log file
* **Get Log** - Retrieves the contents of the log with the specified filename
* **Mouse Position** - Returns the mouse in virtual screen coordinates (left, top)
* **Process List** - Retrieves an array of all of the runtime processes that are currently running. Each element in the array is an object containing the uuid and the name of the application to which the process belongs
* **Proxy Settings** - Retrieves the Proxy settings
* **RVM Info** - Returns information about the running RVM in an object
* **Version** - Returns the version of the runtime. The version contains the major, minor, build and revision numbers
* **Monitor Info** - Retrieves an object that contains data about the monitor setup of the computer that the runtime is running on
* **Window Snapshot** - Gets a base64 encoded PNG snapshot of the window
* **Window State** - Gets the current state ("minimized", "maximized", or "restored") of the window
* **Window Is Showing** - Determines if the window is currently showing
* **Window Bounds** - Gets the current bounds (top, left, width, height) of the window
* **Window Zoom Level** - Returns the zoom level of the window

## Documentation
Documentation for the full OpenFin Runtime API can be found [here](http://cdn.openfin.co/jsdocs/stable/).

## Launch
### Run Locally

```sh
$ npm install
```
```sh
$ bower install
```
```sh
$ npm start
```
```sh
$ openfin -l app.json
```

## APIs
This guide provides an interactive view of the following OpenFin runtime APIs:

#### [fin.desktop.System.getCommandLineArguments](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getCommandLineArguments)
```javascript
  fin.desktop.System.getCommandLineArguments(args => {
	    document.getElementById("clArgsInfo").innerHTML = JSON.stringify(args);
	    hljs.highlightBlock(document.getElementById("clArgsInfo"));
      });
```

#### [fin.desktop.System.getDeviceId](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getDeviceId)
```javascript
fin.desktop.System.getDeviceId(args => {
	document.getElementById("dIdInfo").innerHTML = JSON.stringify(args);
	hljs.highlightBlock(document.getElementById("dIdInfo"));
});
```

#### [fin.desktop.System.getDeviceUserId](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getDeviceUserId)
```javascript
fin.desktop.System.getDeviceUserId(args => {
	document.getElementById("dUserIdInfo").innerHTML = JSON.stringify(args);
	hljs.highlightBlock(document.getElementById("dUserIdInfo"));
});
```

#### [fin.desktop.System.getHostSpecs](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getHostSpecs)
```javascript
fin.desktop.System.getHostSpecs(args => {
	document.getElementById("hSpecsInfo").innerHTML = JSON.stringify(args);
	hljs.highlightBlock(document.getElementById("hSpecsInfo"));
});
```

#### [fin.desktop.System.log](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.log)
```javascript
fin.desktop.System.log("info",
  "An example log message",
  function () {
      console.log("message successfully logged");
  }, function(err) {
      console.log(err);
});
```

#### [fin.desktop.System.getLogList](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getLogList)
```javascript
fin.desktop.System.getLogList(logList => {
	document.getElementById("logListInfo").innerHTML = JSON.stringify(logList);
	hljs.highlightBlock(document.getElementById("logListInfo"));
});					
```

#### [fin.desktop.System.getLog](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getLog)
```javascript
fin.desktop.System.getLog("debugl170315170013.log",log => {
	document.getElementById("getLogInfo").innerHTML = log;
});
```

#### [fin.desktop.System.getMousePosition](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getMousePosition)
```javascript

fin.desktop.System.getMousePosition(r => {
	document.getElementById("mousePInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("mousePInfo"));
});					
```

#### [fin.desktop.System.getProcessList](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getProcessList)
```javascript
fin.desktop.System.getProcessList(r => {
	document.getElementById("processListInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("processListInfo"));
});
```
#### [fin.desktop.System.getProxySettings](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getProxySettings)
```javascript
fin.desktop.System.getProxySettings(r => {
	document.getElementById("proxySettingsInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("proxySettingsInfo"));
});
```

#### [fin.desktop.System.getRvmInfo](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getRvmInfo)
```javascript
fin.desktop.System.getRvmInfo(r => {
	document.getElementById("rvmInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("rvmInfo"));
});
```

#### [fin.desktop.System.getVersion](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getVersion)
```javascript
fin.desktop.System.getVersion(r => {
	document.getElementById("versionInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("versionInfo"));
});
```

#### [fin.desktop.System.getMonitorInfo](http://cdn.openfin.co/jsdocs/stable/fin.desktop.System.html#.getMonitorInfo)
```javascript
fin.desktop.System.getMonitorInfo(function (monitorInfo) {
	document.getElementById("monitorInfo").innerHTML = JSON.stringify(monitorInfo);
	 hljs.highlightBlock(document.getElementById("monitorInfo"));
});
```

#### [fin.desktop.Window.getSnapshot](http://cdn.openfin.co/jsdocs/stable/fin.desktop.Window.html#getSnapshot)
```javascript
fin.desktop.Window.getCurrent().getSnapshot( bSixFour =>{
	document.getElementById("b64Info").innerHTML = bSixFour;
	});
```

#### [fin.desktop.Window.getState](http://cdn.openfin.co/jsdocs/stable/fin.desktop.Window.html#getState)
```javascript
fin.desktop.Window.getCurrent().getState(r =>{
	document.getElementById("stateInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("stateInfo"));
	});
```

#### [fin.desktop.Window.getZoomLevel](http://cdn.openfin.co/jsdocs/stable/fin.desktop.Window.html#getZoomLevel)
```javascript
fin.desktop.Window.getCurrent().getZoomLevel(r =>{
	document.getElementById("zoomInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("zoomInfo"));
	});
```
#### [fin.desktop.Window.isShowing](http://cdn.openfin.co/jsdocs/stable/fin.desktop.Window.html#isShowing)
```javascript
fin.desktop.Window.getCurrent().isShowing(r =>{
	document.getElementById("showingInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("showingInfo"));
});
```

#### [fin.desktop.Window.getBounds](http://cdn.openfin.co/jsdocs/stable/fin.desktop.Window.html#getBounds)
```javascript
fin.desktop.Window.getCurrent().getBounds(r =>{
	document.getElementById("boundsInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("boundsInfo"));
});
```

## Disclaimers
* This is a starter example and intended to demonstrate to app providers a sample of how to approach an implementation. There are potentially other ways to approach it and alternatives could be considered. 
* This is an open source project and all are encouraged to contribute.
* Its possible that the repo is not actively maintained.

## License
MIT

The code in this repository is covered by the included license.  If you run this code, it may call on the OpenFin RVM or OpenFin Runtime, which are subject to OpenFin’s [Developer License](https://openfin.co/developer-agreement/). If you have questions, please contact support@openfin.co”

## Support
Please enter an issue in the repo for any questions or problems. 
<br> Alternatively, please contact us at support@openfin.co
