<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <title>Déposer votre vidéo</title>
  <script>
    UPLOADCARE_PUBLIC_KEY = 'f44deb9e0290fb01757b';
  </script>
  <script src="https://ucarecdn.com/libs/widget/3.x/uploadcare.full.min.js"></script>
</head>
<body>
  <h2>Déposez votre vidéo</h2>
  <input
    type="hidden"
    role="uploadcare-uploader"
    data-tabs="file camera"
    data-clearable
    data-multiple="false"
    data-max-size="157286400"
  />

  <p>Copiez le lien généré ci-dessous et collez-le dans le formulaire Google Forms :</p>
  <input type="text" id="videoLink" style="width: 90%; font-size: 16px;" readonly />

  <script>
    uploadcare.Widget('[role=uploadcare-uploader]').onUploadComplete(function(fileInfo) {
      document.getElementById('videoLink').value = fileInfo.cdnUrl;
    });
  </script>
</body>
</html>
