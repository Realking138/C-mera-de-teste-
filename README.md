# C-mera-de-teste-
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Camera Test Page</title>
  <style>
    body { font-family: Arial, sans-serif; display: flex; justify-content: center; align-items: center; height: 100vh; margin: 0; }
    .container { text-align: center; }
    video { width: 100%; max-width: 500px; margin-top: 20px; border: 2px solid #333; }
  </style>
</head>
<body>
  <div class="container">
    <h1>Camera Test Page</h1>
    <button onclick="startCamera()">Activate Camera</button>
    <video id="camera" autoplay playsinline></video>
  </div>

  <script>
    async function startCamera() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: true });
        document.getElementById('camera').srcObject = stream;
      } catch (error) {
        alert('Unable to access camera. Please allow camera access.');
      }
    }
  </script>
</body>
</html>
