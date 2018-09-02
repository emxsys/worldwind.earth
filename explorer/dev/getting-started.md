---
date: 2016-04-20T10:13:26+02:00
title: Getting Started
menu:
  main:
    parent: dev-guide
    identifier: explorer/dev/getting-started
    weight: 10
---

## Simple Example

This is how to use a `WorldWind.WorldWindow` object

```javascript
// Register an event listener to be called when the page is loaded.
window.addEventListener("load", eventWindowLoaded, false);

// Define the event listener to initialize Web WorldWind.
function eventWindowLoaded() {
    // Create a WorldWindow for the canvas.
    var wwd = new WorldWind.WorldWindow("canvasOne");

    // Add some image layers to the WorldWindow's globe.
    wwd.addLayer(new WorldWind.BMNGOneImageLayer());
    wwd.addLayer(new WorldWind.BMNGLandsatLayer());

    // Add a compass, a coordinates display and some view controls to the WorldWindow.
    wwd.addLayer(new WorldWind.CompassLayer());
    wwd.addLayer(new WorldWind.CoordinatesDisplayLayer(wwd));
    wwd.addLayer(new WorldWind.ViewControlsLayer(wwd));
}
```

```html
<!DOCTYPE html>
<!-- This is a very simple example of using Web WorldWind. -->
<html>
<head lang="en">
<meta charset="UTF-8">
<title>WorldWind Example</title>
<!-- Include the Web WorldWind library. -->
<script src="https://files.worldwind.arc.nasa.gov/artifactory/web/0.9.0/worldwind.min.js" type="text/javascript"></script>
</head>
<body>
<div style="position: absolute; top: 50px; left: 50px;">
    <!-- Create a canvas for Web WorldWind. -->
    <canvas id="canvasOne" width="1024" height="768">
        Your browser does not support HTML5 Canvas.
    </canvas>
</div>
<script>
    // Register an event listener to be called when the page is loaded.
    window.addEventListener("load", eventWindowLoaded, false);

    // Define the event listener to initialize Web WorldWind.
    function eventWindowLoaded() {
        // Create a WorldWindow for the canvas.
        var wwd = new WorldWind.WorldWindow("canvasOne");

        // Add some image layers to the WorldWindow's globe.
        wwd.addLayer(new WorldWind.BMNGOneImageLayer());
        wwd.addLayer(new WorldWind.BMNGLandsatLayer());

        // Add a compass, a coordinates display and some view controls to the WorldWindow.
        wwd.addLayer(new WorldWind.CompassLayer());
        wwd.addLayer(new WorldWind.CoordinatesDisplayLayer(wwd));
        wwd.addLayer(new WorldWind.ViewControlsLayer(wwd));
    }
</script>
</body>
</html>
```
