# Diagnostic APIs Guide
Guide for OpenFin APIs that are useful in diagnostics, debugging, and reporting.  Built on the OpenFin Runtime and [Reveal-js](http://lab.hakim.se/reveal-js/).

## Documentation



Documentation for the full OpenFin Runtime API can be found [here](https://openfin.co/developers/javascript-api/).

## Setup

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

#### fin.desktop.System.getCommandLineArguments
```javascript
  fin.desktop.System.getCommandLineArguments(args => {
	    document.getElementById("clArgsInfo").innerHTML = JSON.stringify(args);
	    hljs.highlightBlock(document.getElementById("clArgsInfo"));
      });
```
#### fin.desktop.System.getDeviceId
```javascript
fin.desktop.System.getDeviceId(args => {
	document.getElementById("dIdInfo").innerHTML = JSON.stringify(args);
	hljs.highlightBlock(document.getElementById("dIdInfo"));
});
```
#### fin.desktop.System.getHostSpecs
```javascript
fin.desktop.System.getHostSpecs(args => {
	document.getElementById("hSpecsInfo").innerHTML = JSON.stringify(args);
	hljs.highlightBlock(document.getElementById("hSpecsInfo"));
});
```

#### fin.desktop.System.log
```javascript
fin.desktop.System.log("info",
  "An example log message",
  function () {
      console.log("message successfully logged");
  }, function(err) {
      console.log(err);
});
```
#### fin.desktop.System.getLogList
```javascript
fin.desktop.System.getLogList(logList => {
	document.getElementById("logListInfo").innerHTML = JSON.stringify(logList);
	hljs.highlightBlock(document.getElementById("logListInfo"));
});					
```

#### fin.desktop.System.getLog
```javascript
fin.desktop.System.getLog("debugl170315170013.log",log => {
	document.getElementById("getLogInfo").innerHTML = log;
});
```

#### fin.desktop.System.getMousePosition
```javascript

fin.desktop.System.getMousePosition(r => {
	document.getElementById("mousePInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("mousePInfo"));
});					
```

#### fin.desktop.System.getProcessList
```javascript
fin.desktop.System.getProcessList(r => {
	document.getElementById("processListInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("processListInfo"));
});
```
#### fin.desktop.System.getProxySettings
```javascript
fin.desktop.System.getProxySettings(r => {
	document.getElementById("proxySettingsInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("proxySettingsInfo"));
});
```

#### fin.desktop.System.getRvmInfo
```javascript
fin.desktop.System.getRvmInfo(r => {
	document.getElementById("rvmInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("rvmInfo"));
});
```

#### fin.desktop.System.getVersion
```javascript
fin.desktop.System.getVersion(r => {
	document.getElementById("versionInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("versionInfo"));
});
```


#### fin.desktop.System.getMonitorInfo
```javascript
fin.desktop.System.getMonitorInfo(function (monitorInfo) {
	document.getElementById("monitorInfo").innerHTML = JSON.stringify(monitorInfo);
	 hljs.highlightBlock(document.getElementById("monitorInfo"));
});
```


#### fin.desktop.Window.getSnapshot
```javascript
fin.desktop.Window.getCurrent().getSnapshot( bSixFour =>{
	document.getElementById("b64Info").innerHTML = bSixFour;
	});
```


#### fin.desktop.Window.getState
```javascript
fin.desktop.Window.getCurrent().getState(r =>{
	document.getElementById("stateInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("stateInfo"));
	});
```

#### fin.desktop.Window.getZoomLevel
```javascript
fin.desktop.Window.getCurrent().getZoomLevel(r =>{
	document.getElementById("zoomInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("zoomInfo"));
	});
```
#### fin.desktop.Window.isShowing
```javascript
fin.desktop.Window.getCurrent().isShowing(r =>{
	document.getElementById("showingInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("showingInfo"));
});
```

#### fin.desktop.Window.getBounds
```javascript
fin.desktop.Window.getCurrent().getBounds(r =>{
	document.getElementById("boundsInfo").innerHTML = JSON.stringify(r);
	hljs.highlightBlock(document.getElementById("boundsInfo"));
});
```
