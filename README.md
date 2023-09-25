# GuardandoRepositorios


malware python: https://github.com/vitormluz/Python-Malware
back end rapido https://www.youtube.com/live/Kp4m-JmvLck?si=rmN8bjL7PZgDHKDc
crud completin explicado: https://alexandrebbarbosa.wordpress.com/2016/09/04/php-pdo-crud-completo/comment-page-1/

HTML:
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

    <!-- Header bootstrap -->
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



    <!-- Container do piano -->
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

    <div class="barraControles">
        <div class="capad" style="display: flex;">
            <img src="img/cd-cover-2978944_1280.jpg" alt="" class="capad">
            <p class="tituloMusica">Liebestraum - </p>
            <div class="heart"><i class="fa-regular fa-heart" style="color: #808080;"></i></div>

        </div>
        <div class="controlesMain">
            <button style="background-color: transparent; color: white; border: none; cursor: pointer;"><i
                    class="fa-solid fa-repeat" style="color: #ffffff;"></i></button>
            <button id="iniciarGravacao"
                style="border:none; border-radius: 15px; width: 30px; height: 30px; background-color: white; margin-top: 10px; cursor: pointer;"><i
                    class="fa-solid fa-circle"></i></button>
            <button id="reproduzirGravacao"
                style="border:none; border-radius: 25px; width: 50px; height: 50px; background-color: white; cursor: pointer;"><i
                    class="fa-solid fa-play fa-2xl"></i></button>
            <button id="pararGravacao"
                style="border:none; border-radius: 15px; width: 30px; height: 30px; background-color: white;  margin-top: 10px; cursor: pointer;"><i
                    class="fa-solid fa-square"></i></button>
            <button style="background-color: transparent; color: white; border: none; cursor: pointer;"><i
                    class="fa-solid fa-shuffle" style="color: #ffffff;"></i></button>
        </div>

        <div class="barraProgresso"></div>


        <div class="controlesEnd">
            <i class="fa-solid fa-sliders" style="color: #ffffff;"></i>
            <div class="volume" style="display: flex;">
                <i class="fa-solid fa-volume-high" style="color: #ffffff; margin-right:8px ;"></i>
                    <p style="background-color: white; width: 100px; height: 7px; border-radius: 10px; margin-top: 8px;"></p>
                    <p style="background-color: grey; width: 12px; height: 12px; border: grey; border-radius: 11px; position: absolute; margin-left: 90px; margin-top: 5px"></p>
                </div>
            <i class="fa-solid fa-up-right-and-down-left-from-center" style="color: #ffffff;"></i>

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




    <script src="script/scriptPiano.js"></script>
    <script src="script/appPiano.js"></script>
</body>

</html>

css:
@import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300&display=swap');
 
 body {
    margin: 0;
     background-color: lightblue;
     display: flex;
     justify-content: center;
     align-items: center;
 }

 a {
    text-decoration: none;
}

 .material-symbols-outlined {
    font-variation-settings:
    'FILL' 0,
    'wght' 500,
    'GRAD' 0,
    'opsz' 24;
  }
  
  .cabecalho {
      background-color: rgb(54, 51, 51);
      width: 100%;
      border: 0;
 
  }
  
  .cabecalho .nav-item, .seta {
      text-decoration: none;
      font-size: 1.7em;
      font-weight: bold;
      color: white;
      font-family: 'Quicksand', sans-serif;
  }
  
  .cabecalho .nav-item:hover, .seta{
      color: rgb(173, 173, 173);
      transition: 0.1s;
      cursor: pointer;
  }
  
  .cabecalho .nav {
      width: 100%;
      display: flex;
      justify-content: center;
  }
  
  .cabecalho .seta {
      width: 1%;
      margin-left: 1em;

  }
  














body {
    background-color: lightblue;
    display: flex;
    justify-content: center;
    align-items: center;
}

.header {
   margin-top: 15px;
   display: flex;
   color: white;
}
.header .tittle {
   margin-top: 10px;
   margin-left: 55px;
}
.header .icon {
   margin-right: 100px;
   margin-top: 10px;
   display: flex;
   justify-content: space-between;
   width: 150px;
}

.container-main {
    background-color: black;
    margin-top: 520px;
    width: 1200px;
    justify-content: center;
    align-items: center;
    height: 400px;
    border-radius: 20px;
    position: absolute;
}


.container1 {
    position: absolute;
    margin-left: 123px;
    margin-top: 66px;
}

.header {
    display: flex;
    justify-content: space-between;
    width: 100%;
    position: absolute;
}

.tittle {
    margin-top: 1px;
}


.container #btn15 {
    margin-left: 80px;
}



/* 
ESTILIZAÇÃO PRIMEIRA PARTE DOS BOTÕES */
#btn0 {
    width: 32px;
    height: 180px;
    background-color: black;
    border-radius: 6px;
box-shadow: 0 6px 0 grey;
cursor: pointer;
}

#btn1 {
    width: 32px;
    height: 180px;
    margin-left: 32px;
    background-color: black;
    border-radius: 6px;
box-shadow: 0 6px 0 grey;
cursor: pointer;
}

#btn2,
#btn5,
#btn11 {
    width: 32px;
    height: 180px;
    margin-left: 27px;
    background-color: black;
    border-radius: 6px;
box-shadow: 0 6px 0 grey;
cursor: pointer;
}

#btn3,
#btn4,
#btn6,
#btn7,
#btn8,
#btn9,
#btn12,
#btn13,
#btn14 {
    width: 32px;
    height: 180px;
    margin-left: 28px;
    background-color: black;
    border-radius: 6px;
box-shadow: 0 6px 0 grey;
cursor: pointer;
}

#btn10 {
    width: 32px;
    height: 180px;
    margin-left: 29px;
    background-color: black;
    border-radius: 6px;
box-shadow: 0 6px 0 grey;
cursor: pointer;
}


#btn15 {
    height: 275px;
    width: 60px;
    background-color: white;
    margin-top: 30px;
    cursor: pointer;
}

#btn16,
#btn17,
#btn18,
#btn19,
#btn20,
#btn21,
#btn22,
#btn23,
#btn24,
#btn25,
#btn26,
#btn27,
#btn28,
#btn29,
#btn30 {
    height: 275px;
    width: 60px;
    background-color: white;
    cursor: pointer;
}

#btn0:hover,#btn1:hover,#btn2:hover,#btn3:hover,#btn4:hover,#btn5:hover,#btn6:hover,#btn7:hover,#btn8:hover,#btn9:hover,#btn10:hover,
#bt11:hover,#btn12:hover,#btn13:hover,#btn14:hover{background-color: white;
border: 0;
border-radius: 6px;
box-shadow: 0 6px 0 grey;


}
#btn15:hover,#btn16:hover,#btn17:hover,#btn18:hover,#btn19:hover,#btn20:hover,#btn21:hover,
#btn22:hover,#btn23:hover,#btn24:hover,#btn25:hover,#btn26:hover,#btn27:hover,#btn28:hover,#btn29:hover,#btn30:hover{
background-color: snow;


}

.barraControles{
    display: flex;
    justify-content: space-between;
    background: rgb(32,52,52);
    background: linear-gradient(99deg, rgba(32,52,52,1) 0%, rgba(8,20,20,1) 38%, rgba(2,11,11,1) 46%, rgba(6,16,16,1) 56%, rgba(32,52,52,1) 100%);  
    width: 100%;
    position: absolute;
    height: 6em;
    margin-top:65em; 
}

.barraControles .capad {
    width: 60px;
    height: 60px;
    margin-left: 7px;
    margin-top: 5px;
    border-radius: 3px;
    
}
.barraControles .capad .tituloMusica{
    color: white;
    font-family: 'Quicksand', sans-serif;
    margin-left: 10px;
}
.barraControles .capad .heart{
    margin-left: 12px;
    margin-top: 35px;
}


.controlesMain {
    width: 15em;
    margin-top: 8px;
    margin-left: 40px;
    display: flex;
    justify-content: space-between;
}

.barraProgresso{
    width: 0;
    height: 10px;
    max-width: 250px;
    background-color: aliceblue;
    transition: width 0.1s;
    margin-top: 5px;
}

#iniciarGravacao:active, #reproduzirGravacao:active, #pararGravacao:active{
    transform: translateY(2px); 
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.controlesEnd{
    display: flex;
    justify-content: space-between;
    width: 250px;
    margin-right: 25px;
    margin-top: 35px;
}
























































    /* Responsividade */
@media screen and (max-width:1150px) {
  
    body {
        display: flex;
        justify-content: center;
        align-items: center;
    }
    
.header {
   display: none;
}
.header .tittle {
   display: none;
}
.header .icon {
  display: none;
}

    .container-main {
        width: 800px;
        height: 232px;
        display: flex;
        padding-right: 60px;
        padding-bottom: 22px;
        transition: 0.4s;
    }

    .container1 {
        display: flex;
        justify-content: center;
        width: 600px;
        margin-right: 175px;
        margin-bottom: 100px;
        transition: 0.4s;
    }

    .container {
        margin-top: 1px;
        margin-right: 20px;
        transition: 0.4s;
    }

    #btn0 {
        width: 20px;
        height: 100px;
        margin-left: 110px;
        transition: 0.4s;

    }

    #btn1 {
        width: 20px;
        height: 100px;
        transition: 0.4s;



    }

    #btn2,
    #btn5,
    #btn11 {
        width: 20px;
        height: 100px;
        transition: 0.4s;

    }

    #btn3,
    #btn4,
    #btn6,
    #btn7,
    #btn8,
    #btn9,
    #btn12,
    #btn13 {
        width: 20px;
        height: 100px;
        transition: 0.4s;

    }

    #btn14 {

        width: 20px;
        height: 100px;
        transition: 0.4s;

    }

    #btn10 {
        width: 20px;
        height: 100px;
        transition: 0.4s;
    }




    #btn15 {
        height: 175px;
        width: 40px;
        background-color: white;
        margin-top: 5px;
        transition: 0.4s;

    }

    #btn16,
    #btn17,
    #btn18,
    #btn19,
    #btn20,
    #btn21,
    #btn22,
    #btn23,
    #btn24,
    #btn25,
    #btn26,
    #btn27,
    #btn28,
    #btn29,
    #btn30 {
        height: 175px;
        width: 40px;
        background-color: white;
        transition: 0.4s;

    }

}




@media screen and (max-width:768px) {
    body {
        display: flex;
        justify-content: center;
        align-items: center;
        transition: 0.4s;
    }

    .container-main {
        width: 584px;
        height: 169px;
        margin-top: 408px;
        display: flex;
        padding-right: 44px;
        padding-bottom: 16px;
        transition: 0.4s;
    }
    .container1 {
       display: flex;
       justify-content: center;
       width: 600px;
       margin-right: 180px;
       margin-bottom: 100px;
       margin-left: 233px;
       transition: 0.4s;
   }
    .container {
        margin-bottom: 20px;
        margin-right: 14px;
        transition: 0.4s;
    }

   

#btn1,
#btn0,
#btn2, #btn3,

#btn4, #btn5,
#btn6,
#btn7,
#btn8,
#btn10,#btn11,
#btn9,
#btn12{
    width: 17px;
    height: 73px;
    margin-left: 16px;
    transition: 0.4s;

}

#btn13,
#btn14 {
   display: none;
}

#btn15 {
    height: 128px;
    width: 29px;
    background-color: white;
    margin-top: 4px;
    transition: 0.4s;

}

#btn16, #btn17{
   display: none;
}
#btn18,
#btn19,
#btn20,
#btn21,
#btn22,
#btn23,
#btn24,
#btn25,
#btn26,
#btn27,
#btn28,
#btn29,
#btn30 {
    height: 128px;
    width: 29px;
    background-color: white;
    transition: 0.4s;
   }

}

scriptíano:
for (let i = 0; i <= 30; i++) {
    const btn = document.getElementById(`btn${i}`);
    const audio = document.getElementById(`audio${i}`);
    btn.addEventListener('click', function () {
        audio.play();
    });
}
apppiano:
class App {
  constructor() {
      this.notasGravadas = [];
      this.estaGravando = false;
      this.estaReproduzindo = false;
      this.horaInicio = 0;
      this.duracaoGravacao = 0;

      this.inicializarBotoes();
      this.inicializarEventos();
  }

  inicializarBotoes() {
      this.botoes = Array.from(document.querySelectorAll('.piano-key'));
  }

  inicializarEventos() {
      this.botoes.forEach((botao, indice) => {
          botao.addEventListener('click', () => this.reproduzirNotaNoIndice(indice));
      });

      document.getElementById('iniciarGravacao').addEventListener('click', () =>
          this.iniciarGravacao()
      );

      document.getElementById('pararGravacao').addEventListener('click', () =>
          this.pararGravacao()
      );

      document.getElementById('reproduzirGravacao').addEventListener('click', () =>
          this.reproduzirGravacao()
      );
  }

  reproduzirNotaNoIndice(indice) {
      const audio = document.getElementById(`audio${indice}`);
      audio.currentTime = 0;
      audio.play();

      if (this.estaGravando) {
          const tempo = Date.now() - this.horaInicio;
          this.notasGravadas.push({ indice, tempo });
      }
  }

  iniciarGravacao() {
      this.estaGravando = true;
      this.notasGravadas = [];
      this.horaInicio = Date.now();
      this.barraProgresso = document.querySelector('.barraProgresso');
      this.barraProgresso.style.width = '0';
      this.iniciarBarra();
      
  }

  pararGravacao() {
      this.estaGravando = false;
     
  }

  iniciarBarra() {
      if (this.estaGravando) {
          const tempoAtual = Date.now();
          const elapsedTime = tempoAtual - this.horaInicio;
          const progresso = (elapsedTime / 20000 ) * 100; // Calcula o progresso em relação ao tempo máximo de gravação
          this.barraProgresso.style.width = progresso + '%';

          if (progresso < 100) {
              requestAnimationFrame(() => this.iniciarBarra()); // Continua atualizando até que o progresso alcance 100%
          } else {
              this.pararGravacao();
          }
      }
  }

  reproduzirGravacao() {
      if (this.notasGravadas.length === 0 || this.estaReproduzindo) return;

      this.estaReproduzindo = true;
      this.reproduzirNotasGravadas(0);
  }

  reproduzirNotasGravadas(indice) {
      if (indice < this.notasGravadas.length) {
          const { indice: indiceNota, tempo } = this.notasGravadas[indice];
          // Use a duração da gravação para agendar a reprodução no tempo correto
          setTimeout(() => {
              this.botoes[indiceNota].click();
              this.reproduzirNotasGravadas(indice + 1);
          }, tempo);
      } else {
          this.estaReproduzindo = false;
      }
  }

 
}

const app = new App();



