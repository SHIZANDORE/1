
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Campo de Girasoles</title>
  <style>
    body, html {
      margin: 0;
      height: 100%;
      overflow: hidden;
    }
    body {
      background: linear-gradient(to top, 
        #1e7a1e 25%,   
        #2e8b57 35%,   
        #5fb3ff 60%,   
        #4a90e2 100%   
      );
      cursor: pointer;
    }
    canvas {
      position: absolute;
      top: 0;
      left: 0;
    }
    .mensaje {
      position: absolute;
      top: 20px;
      left: 10%;         /* lo mueve hacia la izquierda */
      width: 80%;
      text-align: left;  /* alineado hacia la izquierda */
      font-size: 32px;
      font-weight: bold;
      color: white;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.4);
      font-family: "Comic Sans MS", cursive, sans-serif;
    }
    .submensaje {
      position: absolute;
      top: 100px;
      width: 80%;
      max-width: 1000px;
      margin: 0 auto;
      left: 0;
      right: 0;
      text-align: center;   /* este sí centrado */
      font-size: 22px;
      font-style: italic;
      color: #fff9d9;
      text-shadow: 1px 1px 3px rgba(0,0,0,0.6);
      font-family: "Georgia", serif;
      line-height: 1.5;
    }
  </style>
</head>
<body>
  <div class="mensaje">🌻 Bienvenido al campo de girasoles 🌻</div>
  <div class="submensaje">
    No soy de dar, pero para que no te sientas espectadora 🌼 (Haz Click)
  </div>
  <canvas id="canvas"></canvas>

  <script>
    const canvas = document.getElementById("canvas");
    const ctx = canvas.getContext("2d");
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    window.onresize = () => {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    };

    function drawSunflower(x, y, size = 50, petals = 20) {
      ctx.beginPath();
      ctx.moveTo(x, y);
      ctx.lineTo(x, y + size * 2);
      ctx.lineWidth = Math.max(3, size / 12);
      ctx.strokeStyle = "#2b7a2b";
      ctx.stroke();

      ctx.save();
      ctx.translate(x, y);

      for (let i = 0; i < petals; i++) {
        ctx.rotate((2 * Math.PI) / petals);
        ctx.beginPath();
        ctx.ellipse(0, -size / 2, size / 3, size / 1.5, 0, 0, 2 * Math.PI);
        ctx.fillStyle = "yellow";
        ctx.fill();
        ctx.strokeStyle = "orange";
        ctx.stroke();
      }

      ctx.beginPath();
      ctx.arc(0, 0, size / 3, 0, 2 * Math.PI);
      ctx.fillStyle = "brown";
      ctx.fill();

      ctx.restore();
    }

    canvas.addEventListener("click", (e) => {
      drawSunflower(e.clientX, e.clientY, 50);
    });
  </script>
</body>
</html>
