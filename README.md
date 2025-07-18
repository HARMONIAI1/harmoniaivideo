<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Uploader une vidéo</title>
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

  <p>Lien de votre vidéo :</p>
  <input type="text" id="videoLink" style="width: 90%;" readonly />

  <script>
    uploadcare.Widget('[role=uploadcare-uploader]').onUploadComplete(function(info) {
      document.getElementById('videoLink').value = info.cdnUrl;
    });
  </script>
</body>
</html>
