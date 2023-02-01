<!DOCTYPE html>
<html>
  <head>
    <style>
      canvas {
        border: 1px solid black;
      }
    </style>
  </head>
  <body onload="startAnimation()">
    <canvas id="myCanvas" width="500" height="100"></canvas>
    <script>
      function startAnimation() {
        var canvas = document.getElementById("myCanvas");
        var ctx = canvas.getContext("2d");
        var x = canvas.width;
        var y = canvas.height / 2;
        var fontSize = 30;
        var color = "red";
        
        function animate() {
          ctx.clearRect(0, 0, canvas.width, canvas.height);
          ctx.font = fontSize + "px Arial";
          ctx.fillStyle = color;
          ctx.fillText("Hojjat", x, y);
          x--;
          fontSize += 0.5;
          if (fontSize > 50) {
            fontSize = 30;
            color = (color === "red") ? "blue" : "red";
          }
          if (x < -100) {
            x = canvas.width;
          }
          requestAnimationFrame(animate);
        }
        animate();
      }
    </script>
  </body>
</html>
