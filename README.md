<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Upload vidéo HARMONIAI</title>
  <script>
    UPLOADCARE_PUBLIC_KEY = 'f44deb9e0290fb01757b';
  </script>
  <script src="https://ucarecdn.com/libs/widget/3.x/uploadcare.full.min.js"></script>
</head>
<body>
  <h2>Déposez votre vidéo pour HARMONIAI</h2>
  <input type="hidden" role="uploadcare-uploader" 
         data-crop="free" 
         data-images-only="false" 
         data-multiple="false"
         data-clearable 
         data-tabs="file camera url" />

  <p id="status">En attente de l'upload...</p>
  <p><strong>URL de la vidéo :</strong> <span id="videoUrl"></span></p>

  <script>
    uploadcare.Widget('[role=uploadcare-uploader]').onUploadComplete(function(info) {
      document.getElementById('status').textContent = "✅ Upload terminé !";
      document.getElementById('videoUrl').textContent = info.cdnUrl;
    });
  </script>
</body>
</html>
