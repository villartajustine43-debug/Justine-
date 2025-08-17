# Justine-
boring
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Flower with HTML & Canvas</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f5f5f5;
    }
    canvas {
      background: white;
      border: 2px solid #ccc;
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <canvas id="flowerCanvas" width="400" height="400"></canvas>

  <script>
    const canvas = document.getElementById("flowerCanvas");
    const ctx = canvas.getContext("2d");

    function drawPetal(x, y, radius, angle, color) {
      ctx.save();
      ctx.translate(x, y);
      ctx.rotate(angle);
      ctx.beginPath();
      ctx.ellipse(0, -radius / 2, radius / 2, radius, 0, 0, 2 * Math.PI);
      ctx.fillStyle = color;
      ctx.fill();
      ctx.restore();
    }

    function drawFlower() {
      const centerX = canvas.width / 2;
      const centerY = canvas.height / 2;
      const petalCount = 8;
      const petalColor = "#FF69B4"; // pink

      for (let i = 0; i < petalCount; i++) {
        const angle = (i * 2 * Math.PI) / petalCount;
        drawPetal(centerX, centerY, 80, angle, petalColor);
      }

      // Draw flower center
      ctx.beginPath();
      ctx.arc(centerX, centerY, 30, 0, 2 * Math.PI);
      ctx.fillStyle = "#FFD700"; // yellow
      ctx.fill();
    }

    drawFlower();
  </script>
</body>
</html>

