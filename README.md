<!DOCTYPE html>
<html lang="nl">
<head>
  <meta charset="UTF-8">
  <title>STL Uploader</title>
  <script src="https://js.bytescale.com/upload-widget/v3"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 90vh;
      background: #fafafa;
    }
  </style>
</head>
<body>
  <div id="uploader"></div>

  <script>
    const uploader = Upload.create({
      apiKey: "public_xxx_jouw_key", // vervang met jouw Bytescale public key
      multi: false,
      mimeTypes: ["model/stl"], // alleen STL bestanden
      maxFileCount: 1,
      layout: "inline",
      container: "#uploader",
      onUpdate: files => {
        if (files.length > 0) {
          const file = files[0];
          alert("✅ STL geüpload!\n\nDownloadlink:\n" + file.fileUrl);
          console.log("STL geüpload:", file.fileUrl);
        }
      }
    });

    uploader.mount("#uploader");
  </script>
</body>
</html>
