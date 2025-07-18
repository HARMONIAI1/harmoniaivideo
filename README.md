<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Upload vidéo HARMONIAI</title>
  <script>
    UPLOADCARE_PUBLIC_KEY = 'f44deb9e0290fb01757b';
  </script>
  <script src="https://ucarecdn.com/libs/widget/3.x/uploadcare.full.min.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
    }
    h2 {
      color: #008080;
    }
    #videoUrl {
      font-weight: bold;
      color: #2b2b2b;
      word-break: break-all;
    }
    .url-box {
      background: #f1f1f1;
      padding: 10px;
      margin-top: 10px;
      border-radius: 5px;
    }
  </style>
</head>
<body>

  <h2>📤 Déposez votre vidéo pour HARMONIAI</h2>

  <input type="hidden" role="uploadcare-uploader"
         data-crop="free"
         data-images-only="false"
         data-multiple="false"
         data-clearable
         data-tabs="file url camera" />

  <p id="status">⏳ En attente de l'upload...</p>

  <div class="url-box">
    <strong>URL de la vidéo :</strong><br>
    <span id="videoUrl">(sera affiché ici une fois le fichier uploadé)</span>
  </div>

  <script>
    uploadcare.Widget('[role=uploadcare-uploader]').onUploadComplete(function(info) {
      document.getElementById('status').textContent = "✅ Upload terminé ! Copiez l'URL ci-dessous.";
      document.getElementById('videoUrl').textContent = info.cdnUrl;
    });
  </script>

</body>
</html>
