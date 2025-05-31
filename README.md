<!DOCTYPE html>
<html lang="cs">
<head>
  <meta charset="UTF-8">
  <title>Video Experiment</title>
</head>
<body style="text-align:center; font-family:sans-serif; padding:50px;">
  <h1>Experiment: Video</h1>
  <p>Podívejte se prosím na celé video. Po skončení budete automaticky přesměrováni.</p>

  <!-- YouTube embed -->
  <div id="player"></div>

  <script>
    // 1. Načti YouTube IFrame API
    var tag = document.createElement('script');
    tag.src = "https://www.youtube.com/iframe_api";
    var firstScriptTag = document.getElementsByTagName('script')[0];
    firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

    var player;

    // 2. Inicializuj přehrávač
    function onYouTubeIframeAPIReady() {
      player = new YT.Player('player', {
        height: '390',
        width: '640',
        videoId: 'y0sF5xhGreA',
        playerVars: {
          'playsinline': 1,
          'modestbranding': 1,
          'controls': 1,
          'rel': 0
        },
        events: {
          'onStateChange': onPlayerStateChange
        }
      });
    }

    // 3. Reaguj na dokončení videa
    function onPlayerStateChange(event) {
      if (event.data == YT.PlayerState.ENDED) {
        // Zabraň opětovnému přehrání
        player.destroy();
        // Přesměruj na dotazník nebo jinou stránku
        window.location.href = "https://www.google.com";
      }
    }
  </script>
</body>
</html>
