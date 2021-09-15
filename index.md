<html>
  <head>
    <link rel="shortcut icon" type="image/x-icon" href="favicon.ico">
    <title>Sonntagsfilm</title>
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <style>
      body {
        margin: 25px;
      }
      img {
        width: 330px;
        border-radius: 10px;
        float: left;
        margin: 15px;
      }
      * {
        box-sizing: border-box;
      }
      div {
        padding: 10px;
        background-color: #f6f6f6;
        overflow: hidden;
      }
      input[type="text"],
      textarea,
      select {
        font: 17px Calibri;
        width: 100%;
        padding: 12px;
        border: 1px solid #ccc;
        border-radius: 4px;
      }
      input[type="button"] {
        font: 17px Calibri;
        width: auto;
        float: right;
        cursor: pointer;
        padding: 7px;
      }
    </style>
  </head>
  <body
    style="background-color: #f6f6f6"
    style="font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif"
  >
    <h1>Sonntagsfilm 1</h1>
    <p>
      Liebe:r [Name einfügen],<br />
      <br />
      ganz herzlich lade ich dich zu einer Ausgabe "Sonntagsfilm" zu mir ein.
      Wir werden in Kino-Atmospähre einen Film schauen, den wir im Vorfeld
      ausgesucht haben. Dabei starten wir ganz flexibel. Mittags, Nachmittags,
      Abends, ... je nachdem wie es am Samstag so lief. Den Termin können wir
      aber schon lange vorher festlegen. Es gibt Soft-Drinks und Knabberzeug.
      Alles wird schon bereit sein, wenn du kommst. Im Anschluss werden wir über
      den Film diskutieren. Oder auch nicht. Ist voll egal! Du kannst alleine
      kommen oder eine weitere Person mitbringen. In Ausnahmefällen (mit
      Begründung) können wir uns auch zu Viert treffen. Mehr passt nicht auf
      meine Couch.<br />
      <br />
      Herzliche Grüße, Tobaies
    </p>
    <br />
    <h2>Ich benötige folgende Infos:</h2>
    <div>
      <div>
        <input type="text" id="txtName" placeholder="Name oder Alias" />
      </div>
      <div>
        <input
          type="text"
          id="txtFilm1"
          placeholder="Wunschfilm (was immer du auch möchtest)"
        />
      </div>
      <div>
        <input
          type="text"
          id="txtFilm2"
          placeholder="Alternativer Wunschfilm"
        />
      </div>
      <div>
        <select id="Sonntag">
          <option selected value="">-- Welcher Sonntag? --</option>
          <option value="12.09.21">12. September 2021</option>
          <option value="19.09.21">19. September 2021</option>
          <option value="26.09.21">26. September 2021</option>
        </select>
      </div>
      <div>
        <select id="Getränke">
          <option selected value="">-- Bevorzugtes Getränk --</option>
          <option value="Limo">Limo</option>
          <option value="Cola">Cola</option>
          <option value="Bier">Bier</option>
          <option value="nix">nichts davon</option>
        </select>
      </div>
      <div>
        <select id="Speisen">
          <option selected value="">-- Bevorzugte Speise --</option>
          <option value="Pop süß">Popcorn süß</option>
          <option value="Pop salzig">Popcorn salzig</option>
          <option value="Chips">Chips</option>
          <option value="nix">nichts davon</option>
        </select>
      </div>
      <div>
        <input type="text" id="txtComment" placeholder="Optionaler Kommentar" />
      </div>
      <div>
        <input type="button" id="bt" value="Absenden" onclick="saveFile()" />
      </div>
    </div>
    <br />
    <br />
    <img
      src="images/MV5BMTkwNTczNTMyOF5BMl5BanBnXkFtZTcwNzUxOTUyMw@@._V1_.jpg"
      alt=""
    /><img
      src="images/MV5BNDQ1NDE5NzQ1NF5BMl5BanBnXkFtZTgwNzA5OTM2NTE@._V1_.jpg"
      alt=""
    />
    <!--<img src="images/elic-cuckoo-poster.jpg" alt="" />-->
    <img src="images/p7968444_p_v13_ad.jpg" alt="" />
    <img src="images/garden_state_ver4.jpg" alt="" />
    <br />
  </body>
  <script>
    let saveFile = () => {
      // Get the data from each element on the form.
      const name = document.getElementById("txtName");
      const film1 = document.getElementById("txtFilm1");
      const film2 = document.getElementById("txtFilm2");
      const datum = document.getElementById("Sonntag");
      const trinken = document.getElementById("Getränke");
      const essen = document.getElementById("Speisen");
      const comment = document.getElementById("txtComment");

      // This variable stores all the data.
      let data =
        "\r Name: " +
        name.value +
        " \r\n " +
        "Film 1: " +
        film1.value +
        " \r\n " +
        "Film 2: " +
        film2.value +
        " \r\n " +
        "Datum: " +
        datum.value +
        " \r\n " +
        "Trinken: " +
        trinken.value;
      " \r\n " +
        "Essen: " +
        essen.value +
        " \r\n " +
        "Kommentar: " +
        comment.value;

      // Convert the text to BLOB.
      const textToBLOB = new Blob([data], { type: "text/plain" });
      const sFileName = "formData.txt"; // The file to save the data.

      let newLink = document.createElement("a");
      newLink.download = sFileName;

      if (window.webkitURL != null) {
        newLink.href = window.webkitURL.createObjectURL(textToBLOB);
      } else {
        newLink.href = window.URL.createObjectURL(textToBLOB);
        newLink.style.display = "none";
        document.body.appendChild(newLink);
      }

      newLink.click();
    };

  </script>
</html>
