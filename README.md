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
    a {
      font-size: 20px;
      text-decoration: none;
      color: #3366cc;
      font-weight: bold;
    }
    a:hover {
      text-decoration: underline;
    }
  </style>
  <script>
    function redirectToRandomVideo() {
      const pages = ["video1.html", "video2.html", "video3.html"];
      const randomIndex = Math.floor(Math.random() * pages.length);
      window.location.href = pages[randomIndex];
    }
  </script>
</head>
<body>

  <h1>EXPERIMENT</h1>
  <p>
    Vážený participante, vážená participantko,

děkujeme za zájem o účast v tomto experimentu, který vznikl v rámci zápočtu do předmětu Experimentální psychologie 2. Jeho účelem je mapování znalostí týkajících se hokeje a jeho vztahu s pozorností diváka během hokejového utkání u studentů ve věku od 18 do 26 let. 
Účast v experimentu je naprosto dobrovolná a anonymní, s možností z něj kdykoliv bez udání důvodů vystoupit. Rozhodnete-li se pokračovat, dáváte souhlas k zpracování Vašich odpovědí, které budou sloužit výhradně pro účely tohoto výzkumu. Po kliknutí na tlačítko níže se Vám jednou přehraje krátké video po jehož skončení budete  automaticky přesměrování na dotazník. Vyplnění dotazníku nebude trvat déle než 5 minut.

Za vaši účast děkuje výzkumný tým
Matyáš Žák, Markéta Srbová, Alex Král

  </p>

  <a href="#" onclick="redirectToRandomVideo()">Klikni pro přehrání videa</a>

</body>
</html>
