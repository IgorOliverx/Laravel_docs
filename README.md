# GuardandoRepositorios


malware python: https://github.com/vitormluz/Python-Malware
back end rapido https://www.youtube.com/live/Kp4m-JmvLck?si=rmN8bjL7PZgDHKDc
crud completin explicado: https://alexandrebbarbosa.wordpress.com/2016/09/04/php-pdo-crud-completo/comment-page-1/





<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Teclado virtual</title>
    <link rel="stylesheet" href="css/stylePiano.css">
    <link rel="shortcut icon" href="img/download-removebg-preview.png" type="image/x-icon">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css"
        integrity="sha512-z3gLpd7yknf1YoNbCzqRKc4qyor8gaKU1qmn+CShxbuBusANI9QpRohGBreCFkKxLhei6S9CQXFEbbKuqLg0DA=="
        crossorigin="anonymous" referrerpolicy="no-referrer" />
    <link rel="stylesheet"
        href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200" />
</head>

<body>

    <div class="cabecalho">
        <header>
            <a href="index.html" class="seta">
                <span class="material-symbols-outlined">
                    arrow_back
                </span>
            </a>
            <div class="nav">
                <a href="index.html">
                    <a class="nav-item">PIANO</a>
                </a>
            </div>
        </header>
    </div>







    <div class="container-main">
        <header class="header">
            <p class="tittle"><i class="fa-brands fa-js fa-2xl"></i></p>
            <div class="icon">
                <i class="fa-solid fa-music fa-beat"></i>
                <i class="fa-solid fa-square fa-beat-fade"></i>
                <i class="fa-solid fa-square fa-beat-fade"></i>
            </div>
        </header>
        <div class="container1">
            <button id="btn0" class="piano-key"></button>
            <button id="btn1" class="piano-key"></button>
            <button id="btn2" class="piano-key"></button>
            <button id="btn3" class="piano-key"></button>
            <button id="btn4" class="piano-key"></button>
            <button id="btn5" class="piano-key"></button>
            <button id="btn6" class="piano-key"></button>
            <button id="btn7" class="piano-key"></button>
            <button id="btn8" class="piano-key"></button>
            <button id="btn9" class="piano-key"></button>
            <button id="btn10" class="piano-key"></button>
            <button id="btn11" class="piano-key"></button>
            <button id="btn12" class="piano-key"></button>
            <button id="btn13" class="piano-key"></button>
            <button id="btn14" class="piano-key"></button>
        </div>


        <div class="container">
            <br><br>
            <button id="btn15" class="piano-key"></button>
            <button id="btn16" class="piano-key"></button>
            <button id="btn17" class="piano-key"></button>
            <button id="btn18" class="piano-key"></button>
            <button id="btn19" class="piano-key"></button>
            <button id="btn20" class="piano-key"></button>
            <button id="btn21" class="piano-key"></button>
            <button id="btn22" class="piano-key"></button>
            <button id="btn23" class="piano-key"></button>
            <button id="btn24" class="piano-key"></button>
            <button id="btn25" class="piano-key"></button>
            <button id="btn26" class="piano-key"></button>
            <button id="btn27" class="piano-key"></button>
            <button id="btn28" class="piano-key"></button>
            <button id="btn29" class="piano-key"></button>
            <button id="btn30" class="piano-key"></button>

        </div>
    </div>


    <audio id="audio0" src="sons/do8.wav"></audio>
    <audio id="audio1" src="sons/re.wav"></audio>
    <audio id="audio2" src="sons/mi.wav"></audio>
    <audio id="audio3" src="sons/fa.wav"></audio>
    <audio id="audio4" src="sons/sol.wav"></audio>
    <audio id="audio5" src="sons/la.wav"></audio>
    <audio id="audio6" src="sons/si.wav"></audio>
    <audio id="audio7" src="sons/do8.wav"></audio>
    <audio id="audio8" src="sons/do8.wav"></audio>
    <audio id="audio9" src="sons/re.wav"></audio>
    <audio id="audio10" src="sons/mi.wav"></audio>
    <audio id="audio11" src="sons/fa.wav"></audio>
    <audio id="audio12" src="sons/sol.wav"></audio>
    <audio id="audio13" src="sons/la.wav"></audio>
    <audio id="audio14" src="sons/si.wav"></audio>
    <audio id="audio15" src="sons/do8.wav"></audio>
    <audio id="audio16" src="sons/do8.wav"></audio>
    <audio id="audio17" src="sons/re.wav"></audio>
    <audio id="audio18" src="sons/mi.wav"></audio>
    <audio id="audio19" src="sons/fa.wav"></audio>
    <audio id="audio20" src="sons/sol.wav"></audio>
    <audio id="audio21" src="sons/la.wav"></audio>
    <audio id="audio22" src="sons/si.wav"></audio>
    <audio id="audio23" src="sons/do8.wav"></audio>
    <audio id="audio24" src="sons/do8.wav"></audio>
    <audio id="audio25" src="sons/re.wav"></audio>
    <audio id="audio26" src="sons/mi.wav"></audio>
    <audio id="audio27" src="sons/fa.wav"></audio>
    <audio id="audio28" src="sons/sol.wav"></audio>
    <audio id="audio29" src="sons/la.wav"></audio>
    <audio id="audio30" src="sons/si.wav"></audio>

    <div class="controls">
        <button id="startRecording">Iniciar Gravação</button>
        <button id="stopRecording">Parar Gravação</button>
        <button id="playRecording">Reproduzir Gravação</button>
      </div>
      


    <script src="script/scriptPiano.js"></script>
    <script src="script/app.js"></script>
</body>

</html>


class App {
    constructor() {
      this.recordedNotes = [];
      this.isRecording = false;
      this.isPlaying = false;
      this.startTime = 0;
  
      this.initializeButtons();
      this.initializeEventListeners();
    }
  
    initializeButtons() {
      this.buttons = Array.from(document.querySelectorAll('.piano-key'));
    }
  
    initializeEventListeners() {
      this.buttons.forEach((button, index) => {
        button.addEventListener('click', () => this.playNoteAtIndex(index));
      });
  
      document.getElementById('startRecording').addEventListener('click', () =>
        this.startRecording()
      );
  
      document.getElementById('stopRecording').addEventListener('click', () =>
        this.stopRecording()
      );
  
      document.getElementById('playRecording').addEventListener('click', () =>
        this.playRecording()
      );
    }
  
    playNoteAtIndex(index) {
      const audio = document.getElementById(`audio${index}`);
      audio.currentTime = 0;
      audio.play();
  
      if (this.isRecording) {
        const time = Date.now() - this.startTime;
        this.recordedNotes.push({ index, time });
      }
    }
  
    startRecording() {
      this.isRecording = true;
      this.recordedNotes = [];
      this.startTime = Date.now();
    }
  
    stopRecording() {
      this.isRecording = false;
    }
  
    playRecording() {
      if (this.recordedNotes.length === 0 || this.isPlaying) return;
  
      this.isPlaying = true;
      this.playRecordedNotes(0);
    }
  
    playRecordedNotes(index) {
      if (index < this.recordedNotes.length) {
        const { index: noteIndex, time } = this.recordedNotes[index];
        setTimeout(() => {
          this.buttons[noteIndex].click();
          this.playRecordedNotes(index + 1);
        }, time);
      } else {
        this.isPlaying = false;
      }
    }
  }
  
  const app = new App();
  
