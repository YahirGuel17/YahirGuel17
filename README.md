<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Para algodoncito de azucar</title>
  <link href="https://fonts.googleapis.com/css2?family=Abril+Fatface&family=Libre+Baskerville&display=swap" rel="stylesheet" />
  <style>
    body {
      margin: 0;
      background: radial-gradient(ellipse at bottom, #1b2735 0%, #090a0f 100%);
      color: #fff;
      font-family: 'Libre Baskerville', serif;
      text-align: center;
      padding: 50px;
      overflow-x: hidden;
      position: relative;
      height: 100vh;
      overflow-y: auto;
    }

    body::before {
      content: "";
      position: fixed;
      top: 0; left: 0; right: 0; bottom: 0;
      background: transparent;
      box-shadow:
        20px 30px 2px 0px white,
        50px 80px 2px 0px #f0f8ff,
        120px 50px 2px 0px #fafafa,
        200px 150px 2px 0px white,
        250px 120px 2px 0px #f0f8ff,
        320px 90px 2px 0px white,
        380px 170px 2px 0px #fafafa,
        430px 30px 2px 0px white,
        480px 130px 2px 0px #f0f8ff,
        530px 80px 2px 0px white,
        580px 140px 2px 0px #fafafa,
        630px 60px 2px 0px white,
        680px 110px 2px 0px #f0f8ff;
      pointer-events: none;
      z-index: -2;
    }

    .luciernagas {
      position: fixed;
      top: 0; left: 0;
      width: 100%; height: 100%;
      pointer-events: none;
      z-index: -1;
      overflow: visible;
    }

    .luciernaga {
      position: absolute;
      background: radial-gradient(circle, #fffacd 0%, rgba(255,255,204,0) 70%);
      border-radius: 50%;
      opacity: 0.8;
      filter: drop-shadow(0 0 6px #fffacd);
      animation-name: brillar;
      animation-timing-function: ease-in-out;
      animation-iteration-count: infinite;
      animation-direction: alternate;
    }

    .luciernaga.pequena {
      width: 6px;
      height: 6px;
      animation-duration: 3s;
    }
    .luciernaga.mediana {
      width: 10px;
      height: 10px;
      animation-duration: 4.5s;
    }
    .luciernaga.grande {
      width: 14px;
      height: 14px;
      animation-duration: 6s;
    }

    @keyframes brillar {
      0% { opacity: 0.2; }
      50% { opacity: 1; }
      100% { opacity: 0.2; }
    }

    .carta {
      background-color: rgba(255 255 255 / 0.95);
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 0 15px rgba(0, 0, 0, 0.2);
      max-width: 600px;
      margin: auto;
      position: relative;
      z-index: 1;
      color: #000;
    }

    h1 {
      font-family: 'Abril Fatface', cursive;
      font-size: 42px;
      margin-bottom: 20px;
      color: #4b2e83;
    }

    .galeria {
      display: flex;
      overflow-x: auto;
      gap: 15px;
      margin-top: 40px;
      padding: 10px;
      scroll-snap-type: x mandatory;
      position: relative;
      z-index: 1;
    }

    .galeria img {
      height: 200px;
      border-radius: 15px;
      flex-shrink: 0;
      scroll-snap-align: center;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
      opacity: 1;
      transform-origin: center center;
      transition: transform 0.3s ease, box-shadow 0.3s ease;
      cursor: pointer;
    }

    .galeria img:hover {
      transform: scale(1.1) rotate(2deg);
      box-shadow: 0 10px 20px rgba(75, 46, 131, 0.6);
      z-index: 10;
    }

    .audio-con-margen {
      margin-top: 30px;
      position: relative;
      z-index: 1;
    }

    .contenedor-carta {
      text-align: center;
      margin-top: 50px;
      position: relative;
      z-index: 1;
    }

    .contenedor-carta button {
      background-color: #fff;
      color: #000;
      padding: 12px 25px;
      border: none;
      border-radius: 15px;
      font-size: 18px;
      font-family: 'Libre Baskerville', serif;
      cursor: pointer;
      transition: background-color 0.3s ease;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
    }

    .contenedor-carta button:hover {
      background-color: #f0e4ff;
    }

    .carta-oculta {
      margin-top: 30px;
      padding: 25px;
      background-color: #ffffffdd;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      border-radius: 15px;
      font-family: 'Libre Baskerville', serif;
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
      white-space: pre-line;
      position: relative;
      z-index: 1;
      color: #000;
      display: block;
    }

    .mensaje-para-ella {
      margin-top: 50px;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      position: relative;
      z-index: 1;
      color: #fff;
      text-align: left;
    }

    .mensaje-para-ella label {
      display: block;
      font-size: 20px;
      margin-bottom: 10px;
      font-weight: bold;
      color: #b0a8ff;
    }

    .mensaje-para-ella textarea {
      width: 100%;
      height: 120px;
      padding: 12px;
      border-radius: 10px;
      border: 1px solid #ccc;
      font-family: 'Libre Baskerville', serif;
      resize: none;
      font-size: 16px;
    }

    .mensaje-para-ella button {
      margin-top: 15px;
      padding: 12px 25px;
      border: none;
      background-color: #b87efb;
      color: white;
      border-radius: 10px;
      cursor: pointer;
      font-size: 18px;
      font-family: 'Libre Baskerville', serif;
      transition: background-color 0.3s ease;
    }

    .mensaje-para-ella button:hover {
      background-color: #a05ce3;
    }

    .abrazo-virtual {
      margin-top: 60px;
      padding: 30px 20px;
      background-color: rgba(255,255,255,0.1);
      border-radius: 20px;
      max-width: 650px;
      margin-left: auto;
      margin-right: auto;
      font-family: 'Libre Baskerville', serif;
      font-size: 20px;
      color: #d0c6ff;
      line-height: 1.6;
    }

    .abrazo-virtual img {
      margin-top: 25px;
      max-width: 100%;
      border-radius: 15px;
      box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
    }
  </style>
</head>
<body>
  <div class="luciernagas" id="luciernagas"></div>

  <div class="carta">
    <h1>Para mi algodoncito de azucar:</h1>
    <p>
      Cariño, esta es una página hecha con todo mi amor para ti.<br />
      Lo hice solo para recordarte cuánto te amo, cuanto me importas,<br />
      lo especial que eres para mi y lo feliz que soy de tenerte en mi vida.<br />
      Enserio no sabes cuanto te amo mi niña chiflada 🤍
    </p>
  </div>

  <audio class="audio-con-margen" controls>
    <source src="roi.mp3" type="audio/mpeg" />
    Tu navegador no soporta audio HTML5.
  </audio>

  <div class="galeria">
    <img src="imagenes/foto1.jpeg" alt="foto 1" />
    <img src="imagenes/foto2.jpeg" alt="foto 2" />
    <img src="imagenes/foto3.jpeg" alt="foto 3" />
    <img src="imagenes/foto4.jpeg" alt="foto 4" />
    <img src="imagenes/foto5.jpeg" alt="foto 5" />
  </div>

  <div class="contenedor-carta">
    <button onclick="toggleCarta()">Mostrar mensajito sorpresa 💌</button>
    <div id="cartaOculta" class="carta-oculta" style="display:none;">
      Querida Sami:<br><br>
      No sé cómo explicarlo…<br>
A veces me quedo sin palabras porque lo que siento por ti<br>
es tan grande que ni siquiera sé cómo explicarlo.<br><br>

Gracias por no rendirte conmigo,<br>
por seguir aquí incluso cuando todo va muy mal,<br>
por levantarme cuando caigo.<br><br>

Tú no solo eres mi novia, eres mi lugar seguro, mi momento de paz…<br>
Cada vez que me miras siento estrellitas en mi pancita,<br>
como si fuese la primera vez que me vieras jiji ✨<br><br>

No sabes cuánto de verdad amo y valoro<br>
que sigas prefiriendo caminar conmigo,<br>
aun con mis errores…<br>
y que aun así sigas aquí conmigo amándome cada día más.<br><br>

Gracias por ser mi razón para seguir creyendo en el amor.<br><br>

Te amo con todo mi corazoncito 💗<br>
y siempre voy a agradecer que estés a mi lado,<br>
porque sin ti… nada tendría sentido.<br><br>

Gracias por ser la luz de mis días,<br>
por tu sonrisa que ilumina mi mundo<br>
y por tu corazón tan hermoso.<br><br>

Espero que esta carta te recuerde lo mucho que te amo<br>
y lo feliz que me haces.<br><br>
💗✨<br><br>
    </div>
  </div>

  <div class="mensaje-para-ella">
    <label for="mensaje">Escríbeme algo lindo amorcito 💖</label>
    <textarea id="mensaje" placeholder="Aquí puedes escribirme lo que quieras. (hasta tus deseos mas sucios)..."></textarea>
    <button onclick="enviarMensaje()">Enviar</button>
    <p id="respuesta" style="margin-top: 12px;"></p>
  </div>

  <div class="abrazo-virtual">
    <p>Y antes de que te vayas... aquí va un abracitooooo para mi corazoncitooooo 💗</p>
    <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZWZ0djMydjZnc3RuNmQ2cG85aWJ0a3d6bDFxcDVjNjdjb2Q3M2pjaiZlcD12MV9naWZzX3NlYXJjaCZjdD1n/od5H3PmEG5EVq/giphy.gif" alt="Abrazo GIF tierno" />
  </div>

  <script>
    function toggleCarta() {
      const carta = document.getElementById('cartaOculta');
      const btn = document.querySelector('.contenedor-carta button');
      if (carta.style.display === 'none') {
        carta.style.display = 'block';
        btn.textContent = 'Ocultar carta sorpresa';
      } else {
        carta.style.display = 'none';
        btn.textContent = 'Mostrar carta sorpresa';
      }
    }

    function crearLuciernagas() {
      const contenedor = document.getElementById('luciernagas');
      const cantidad = 25;
      for(let i=0; i<cantidad; i++) {
        const luciernaga = document.createElement('div');
        const tamaño = ['pequena', 'mediana', 'grande'][Math.floor(Math.random() * 3)];
        luciernaga.classList.add('luciernaga', tamaño);
        luciernaga.style.top = Math.random() * 100 + 'vh';
        luciernaga.style.left = Math.random() * 100 + 'vw';
        luciernaga.style.animationDelay = (Math.random() * 6) + 's';
        contenedor.appendChild(luciernaga);
      }
    }

    crearLuciernagas();

    function enviarMensaje() {
      const textarea = document.getElementById('mensaje');
      const respuesta = document.getElementById('respuesta');
      if (textarea.value.trim() === '') {
        respuesta.style.color = 'red';
        respuesta.textContent = 'porque le picas a enviar si no has escrito nada malditaaa >:c.';
      } else {
        respuesta.style.color = '#b0a8ff';
        respuesta.textContent = 'Jiji gracias por tu mensaje amorcito, lo guardare con mucho cariño 🥰';
        textarea.value = '';
      }
    }
  </script>
</body>
</html>
