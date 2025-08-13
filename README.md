# lamumu-gamee
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Lamumu: İneğin İçindeki Oyun</title>
  <style>
    body {
      background-color: #222;
      color: #0f0;
      font-family: 'Courier New', monospace;
      padding: 20px;
    }
    #terminal {
      border: 2px solid #0f0;
      padding: 20px;
      height: 300px;
      overflow-y: auto;
      background-color: #000;
    }
    input {
      background-color: #000;
      color: #0f0;
      border: none;
      font-family: inherit;
      font-size: 16px;
      width: 100%;
      outline: none;
    }
  </style>
</head>
<body>
  <h1>Lamumu OS - İnek Geliştirici Terminali 🐮</h1>
  <div id="terminal">
    <div>> lamumu@cowOS:~$ Merhaba! Komut gir:</div>
  </div>
  <input type="text" id="commandInput" autofocus />

  <script>
    const terminal = document.getElementById('terminal');
    const input = document.getElementById('commandInput');

    const responses = {
      "run_game": "Lamumu oyunu başlatılıyor... MooMoo Engine çalışıyor... Hata: Hay çok fazla!",
      "help": "Komutlar: run_game, moo, github, exit",
      "moo": "Moooooo! (Bu bir debug sesidir.)",
      "github": "Lamumu oyunu GitHub'a yüklendi. README eksik ama olsun!",
      "exit": "İnek bilgisayarı kapattı. Geliştirme sona erdi. 🐄💻"
    };

    input.addEventListener('keydown', function(e) {
      if (e.key === 'Enter') {
        const cmd = input.value.trim();
        terminal.innerHTML += `<div>> lamumu@cowOS:~$ ${cmd}</div>`;
        const response = responses[cmd] || "Komut tanınmadı. Belki 'help' yazmalısın.";
        terminal.innerHTML += `<div>${response}</div>`;
        terminal.scrollTop = terminal.scrollHeight;
        input.value = '';
      }
    });
  </script>
</body>
</html>
