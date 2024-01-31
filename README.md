<!doctype html>
<html lang="en-us">
  <head>
  <link rel="icon" type="image/x-icon" href="logo.png"/>
    <meta charset="utf-8">
    <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
    <title>School Heaven</title>
    <style>
      body, html{
        margin: 0;
        padding: 0;
        width: 100vw;
        min-height: 100vh;
        background-color: #111;
        font-family: Arial, Helvetica, sans-serif;
        color: white;
        image-rendering: pixelated;
        scrollbar-width: none;
      }
      ::-webkit-scrollbar {
        display: none;
      }
      #container {
        width: 100vw;
        height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
      }
      canvas {
        width: 100vw;
        height: 100vh;
      }
      #controls {
        margin-left: 1em;
        display: flex;
        align-items: center;
      }
      #controller, #dmca {
        padding-left: 4em;
      }
    </style>
  </head>
  <body>
    <div id="controls">
      <div id="keyboard">
        <h2>Keyboard Controls</h2>
        <ul>
          <li>Movement: Arrow Keys</li>
          <li>A: X</li>
          <li>B: C</li>
          <li>L: Q</li>
          <li>Z: Space</li>
          <li>Start: Enter</li>
          <li>C-stick: WASD</li>
        </ul>
      </div>
      <div id="controller">
        <h2>You can use a controller!</h2>
        <h2>You can save!</h2>
        <h2>Press page down to hide these instructions.</h2>
        <h2>Press page up to see them again.</h2>
      </div>
    </div>
    <div id="container">
      <canvas class="emscripten" id="canvas"></canvas>
    </div>
    <script type='text/javascript'>
      var Module = {
        preRun: [],
        postRun: [],
        print: (function() {
          return function(text) {
            if (arguments.length > 1) text = Array.prototype.slice.call(arguments).join(' ');
            console.log(text);
          };
        })(),
        printErr: function(text) {
          if (arguments.length > 1)
            text = Array.prototype.slice.call(arguments).join(' ');
          console.error(text);
        },
        canvas: (function() {
          var canvas = document.getElementById('canvas');
          canvas.width = window.innerWidth; // Todo: how to do this from c++
          canvas.height = window.innerHeight;
          canvas.addEventListener("webglcontextlost", function(e) {
            alert('WebGL context lost. You will need to reload the page.');
            e.preventDefault();
          }, false);
          return canvas;
        })(),
        setStatus: function(text) {
        }
      };
    </script>
    <script async type="text/javascript" src="sm64.us.f3dex2e.js"></script>
    <script>
    </script>
  </body>
</html>
