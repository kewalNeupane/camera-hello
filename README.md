<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Camera Access Example</title>
</head>
<body>
  <h2>Click the button to allow camera access</h2>
  <button onclick="startCamera()">Allow Camera</button>
  <video id="cameraFeed" width="400" autoplay></video>

  <script>
    async function startCamera() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: true });
        const video = document.getElementById('cameraFeed');
        video.srcObject = stream;
      } catch (err) {
        alert('Camera access denied or not available.');
        console.error(err);
      }
    }
  </script>
</body>
</html>
