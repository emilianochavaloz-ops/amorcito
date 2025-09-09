<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>QR en forma de corazón</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      flex-direction: column;
      gap: 20px;
    }
    .container {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
    }
    .heart {
      position: relative;
      width: 200px;
      height: 200px;
      background: white;
      transform: rotate(-45deg);
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    }
    .heart::before,
    .heart::after {
      content: "";
      position: absolute;
      width: 200px;
      height: 200px;
      border-radius: 50%;
      background: white;
      box-shadow: 0 8px 20px rgba(0,0,0,0.2);
    }
    .heart::before {
      top: -100px;
      left: 0;
    }
    .heart::after {
      left: 100px;
      top: 0;
    }
    #qrcode {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(45deg);
      width: 140px;
      height: 140px;
    }
    .photos {
      position: absolute;
      width: 100%;
      height: 100%;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .photos img {
      width: 140px;
      height: auto;
      border-radius: 20px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.3);
    }
    .bottom-photo {
      position: absolute;
      bottom: -180px;
      left: 50%;
      transform: translateX(-50%);
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="photos">
      <img src="IMG_1589.jpg" alt="Foto izquierda">
      <img src="IMG_2541.jpg" alt="Foto derecha">
    </div>
    <div class="heart">
      <div id="qrcode"></div>
    </div>
    <div class="bottom-photo">
      <img src="IMG_1924.jpg" alt="Foto abajo">
    </div>
  </div>

  <script src="https://cdn.jsdelivr.net/npm/qrcodejs/qrcode.min.js"></script>
  <script>
    new QRCode(document.getElementById("qrcode"), {
      text: "https://tu-link-aqui.com", // 👉 Aquí pon la URL a donde quieres que lleve
      width: 140,
      height: 140,
      colorDark : "#000000",
      colorLight : "#ffffff",
      correctLevel : QRCode.CorrectLevel.H
    });
  </script>
</body>
</html>
