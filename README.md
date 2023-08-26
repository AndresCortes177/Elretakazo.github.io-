# Elretakazo.github.io-
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Pantalla Publicitaria El Retakazo</title>
<style>
  body {
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #000;
  }
  #content {
    max-width: 400px;
    text-align: center;
  }
  video, img {
    max-height: 100%;
    width: auto;
    display: none;
  }
</style>
<script>
  document.addEventListener("DOMContentLoaded", function() {
    const mediaItems = document.querySelectorAll(".media-item");
    let currentIndex = 0;

    function showMedia(index) {
      mediaItems.forEach(item => item.style.display = "none");
      mediaItems[index].style.display = "block";
    }

    function nextMedia() {
      currentIndex = (currentIndex + 1) % mediaItems.length;
      showMedia(currentIndex);

      if (mediaItems[currentIndex].tagName === "VIDEO") {
        const video = mediaItems[currentIndex];
        video.currentTime = 0; // Reiniciar el video
        video.play(); // Iniciar la reproducción del video automáticamente
        setTimeout(nextMedia, (video.duration * 1000) + 200); // Esperar la duración del video + un pequeño margen antes de cambiar
      } else {
        setTimeout(nextMedia, 5000); // 5 minutos (300,000 ms) para imágenes
      }
    }

    showMedia(currentIndex);
    nextMedia(); // Comenzar la secuencia
  });
</script>
</head>
<body>
<div id="content">
  <img class="media-item" src="PXL_20230616_034103141.PORTRAIT.jpg" alt="Imagen 1">
  <video class="media-item">
    <source src="C:\Users\Ferchito\Desktop\Pagina Retakazo\Imagenes Pagina\SaveInsta.App - 3125334385461283260_7145066119.mp4" type="video/mp4">
    Tu navegador no admite el elemento de video.
  </video>
  <img class="media-item" src="C:\Users\Ferchito\Desktop\Pagina Retakazo\Imagenes Pagina\PXL_20230616_034103141.PORTRAIT.jpg" alt="Imagen 2">
  <video class="media-item">
    <source src="2023-07-17-201825459.mp4" type="video/mp4">
    Tu navegador no admite el elemento de video.
  </video>
</div>
</body>
</html>
