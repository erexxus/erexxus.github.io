<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8">
  <title>EXPERIMENT</title>
  <style>
    body {
      text-align: center;
      font-family: Arial, sans-serif;
      padding: 50px;
      background-color: #f5f5f5;
    }
    h1 {
      font-size: 48px;
      margin-bottom: 20px;
    }
    p {
      font-size: 18px;
      margin-bottom: 40px;
    }
    video::-webkit-media-controls-timeline {
      display: none !important; /* Skryje časovou osu */
    }
  </style>
</head>
<body>

  <h1>EXPERIMENT</h1>
  <p>
    Tohle je pouze test. Video se po spuštění přehraje pouze jednou bez možnosti video přetáčet nebo zastavit.
    Po skončení tě přesměruje na dotazník. :3
  </p>

  <video id="myVideo" width="720" autoplay muted>
    <source src="Tiny Dog Barking.mp4" type="video/mp4">
    Váš prohlížeč nepodporuje HTML5 video.
  </video>

  <script>
    const video = document.getElementById("myVideo");
    video.controls = false;

    // Zamez přetáčení
    video.addEventListener('seeking', () => {
      video.currentTime = 0;
    });

    // Zamez pravému kliknutí
    video.addEventListener('contextmenu', e => e.preventDefault());

    // Přesměrování po skončení
    video.addEventListener('ended', () => {
      window.location.href = "https://docs.google.com/forms/d/e/1FAIpQLSdjyKc4PUbYi6lu4owINCLrJ1LgnIgCOXq-0xU2NUEidHdYcg/viewform?usp=header";
    });
  </script>

</body>
</html>
