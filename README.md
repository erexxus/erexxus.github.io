<html lang="cs">
<head>
  <meta charset="UTF-8">
  <title>Experiment – úvod a video</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f5f5f5;
      color: #333;
      line-height: 1.6;
      padding: 40px;
      max-width: 800px;
      margin: auto;
      text-align: center;
    }
    h1 {
      margin-bottom: 30px;
    }
    p {
      text-align: justify;
      margin-bottom: 15px;
    }
    .team {
      margin-top: 30px;
      font-style: italic;
      text-align: right;
    }
    button {
      background-color: #007BFF;
      color: white;
      border: none;
      padding: 12px 24px;
      font-size: 16px;
      border-radius: 8px;
      cursor: pointer;
      margin-top: 20px;
    }
    button:hover {
      background-color: #0056b3;
    }
    video {
      display: none;
      margin-top: 20px;
      max-width: 100%;
      border-radius: 8px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.2);
    }
    video::-webkit-media-controls-timeline {
      display: none !important;
    }
  </style>
</head>
<body>

  <h1>Hokej a pozornost</h1>

  <p><strong>Vážený participante, vážená participantko,</strong></p>

  <p>
    Děkujeme za zájem o účast v tomto experimentu, který vznikl v rámci zápočtu do 
    předmětu <em>Experimentální psychologie 2</em>. Jeho účelem je mapování znalostí 
    týkající se hokeje a jeho vztahu s pozorností diváka během hokejového utkání 
    u studentů ve věku od 18 do 26 let.
  </p>

  <p>
    Účast v experimentu je naprosto dobrovolná a anonymní, s možností z něj kdykoliv 
    bez udání důvodů vystoupit. Rozhodnete-li se pokračovat, dáváte souhlas k zpracování 
    Vašich odpovědí, které budou sloužit výhradně pro účely tohoto výzkumu.
  </p>

  <p>
    Po kliknutí na tlačítko <em>„Spustit video“</em> se Vám pouze jednou přehraje jedno ze třech krátkých videí, které nelze zastavit
    Po skončení videa budete automaticky přesměrováni na dotazník, jehož vyplnění nebude trvat déle než 5 minut.
  </p>

  <div class="team">
    <p>Za Vaši účast děkuje výzkumný tým:</p>
    <p>Matyáš Žák, Markéta Srbová, Alex Král</p>
  </div>

  <button onclick="playVideo()">Spustit video</button>

  <div>
    <video id="myVideo" width="720">
      <source src="video.mp4" type="video/mp4">
      Váš prohlížeč nepodporuje HTML5 video.
    </video>
  </div>

  <script>
    const video = document.getElementById("myVideo");

    // Zakázat pravé tlačítko a přetáčení
    video.addEventListener('contextmenu', e => e.preventDefault());
    video.addEventListener('seeking', () => video.currentTime = 0);

    // Po skončení videa -> přesměrování na náhodný dotazník
    video.addEventListener('ended', () => {
      const urls = [
        "https://forms.gle/hcZoZWJdRYLQvQhJ8",
        "https://forms.gle/juvHuyvj8GENeD2s6",
        "https://forms.gle/Rbjhn2kmVUxp1YwN6"
      ];
      const randomUrl = urls[Math.floor(Math.random() * urls.length)];
      window.location.href = randomUrl;
    });

    function playVideo() {
      document.querySelector("button").style.display = "none"; // schovat tlačítko
      video.style.display = "block"; // zobrazit video
      video.controls = false;
      video.play();
    }
  </script>

</body>
</html>
