
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Vibdark - Archivo Prohibido</title>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <style>
    body {
      background-color: #0a0a0a;
      color: #00ffcc;
      font-family: 'Courier New', Courier, monospace;
      overflow: hidden;
    }
    .glitch {
      animation: glitch 1s infinite;
    }
    @keyframes glitch {
      0% { opacity: 1; }
      50% { opacity: 0.7; transform: translateX(1px); }
      100% { opacity: 1; transform: translateX(0); }
    }
    .hidden-screen { display: none; }
    .terminal { white-space: pre-line; }
    .file:hover { color: #ff0040; cursor: pointer; }
    img { margin-top: 20px; max-width: 100%; border: 2px solid #00ffcc; }
  </style>
</head>
<body class="p-6">

  <!-- Sonido de fondo -->
  <audio autoplay loop>
    <source src="misterio.mp3" type="audio/mpeg">
    Tu navegador no soporta audio.
  </audio>

  <!-- Pantalla de acceso -->
  <div id="loginScreen" class="flex items-center justify-center h-screen">
    <div class="text-center">
      <h1 class="text-3xl glitch">[ACCESO RESTRINGIDO]</h1>
      <p class="mt-4">Ingrese al archivo prohibido de Vibdark</p>
      <button onclick="acceder()" class="mt-6 bg-green-600 px-4 py-2 rounded hover:bg-green-800">ACCESAR</button>
    </div>
  </div>

  <!-- Pantalla principal -->
  <div id="mainScreen" class="hidden-screen">
    <div class="terminal">
      <h2 class="text-2xl mb-4">> directorio: /vibdark/archivos_clasificados</h2>
      <ul class="space-y-2">
        <li class="file" onclick="mostrarArchivo('1')">[001] INCIDENTE EN LA ESTACIÓN ECHO</li>
        <li class="file" onclick="mostrarArchivo('2')">[002] LA ENTIDAD QUE HABLA DESDE LAS PAREDES</li>
        <li class="file" onclick="mostrarArchivo('3')">[003] TRANSMISIÓN DESDE UN FUTURO COLAPSADO</li>
      </ul>

      <div id="archivo" class="mt-8 hidden">
        <h3 id="archivoTitulo" class="text-xl mb-2"></h3>
        <p id="archivoTexto" class="text-sm"></p>
        <img id="archivoImagen" src="imagen_misteriosa.jpg" alt="Imagen misteriosa" class="hidden">
        <button onclick="cerrarArchivo()" class="mt-4 bg-red-600 px-3 py-1 rounded hover:bg-red-800">Cerrar</button>
      </div>
    </div>
  </div>

  <script>
    function acceder() {
      document.getElementById('loginScreen').style.display = 'none';
      document.getElementById('mainScreen').style.display = 'block';
    }

    const archivos = {
      '1': {
        titulo: '[001] INCIDENTE EN LA ESTACIÓN ECHO',
        texto: 'Archivo desclasificado sobre la anomalía detectada en la estación orbital ECHO. Tres investigadores desaparecieron tras escuchar un zumbido en frecuencias inaudibles. El experimento fue abortado, pero se cree que algo logró salir.',
      },
      '2': {
        titulo: '[002] LA ENTIDAD QUE HABLA DESDE LAS PAREDES',
        texto: 'Durante la remodelación de un edificio abandonado, los obreros reportaron voces pidiendo ayuda desde dentro de las paredes. Uno de ellos fue encontrado catatónico, murmurando códigos binarios sin sentido.',
      },
      '3': {
        titulo: '[003] TRANSMISIÓN DESDE UN FUTURO COLAPSADO',
        texto: 'Un archivo de audio apareció en un servidor antiguo. Analizado con IA, contiene un mensaje de socorro en un dialecto modificado del español. Se sospecha que fue enviado desde una línea de tiempo futura donde la humanidad cayó.',
      }
    };

    function mostrarArchivo(id) {
      document.getElementById('archivo').style.display = 'block';
      document.getElementById('archivoTitulo').textContent = archivos[id].titulo;
      document.getElementById('archivoTexto').textContent = archivos[id].texto;
      document.getElementById('archivoImagen').classList.remove('hidden');
    }

    function cerrarArchivo() {
      document.getElementById('archivo').style.display = 'none';
      document.getElementById('archivoImagen').classList.add('hidden');
    }
  </script>
</body>
</html>
# MR-Eyes
La pagina oculta y secreta de MR Eyes. ¿Te atreves a verla?
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>EXPEDIENTE #89-B: MR. EYES</title>
    <style>
        /* --- ESTILOS GENERALES Y ATMÓSFERA --- */
        body {
            background-color: #050505;
            color: #dcdcdc;
            font-family: 'Courier New', Courier, monospace;
            margin: 0;
            padding: 20px;
            overflow-x: hidden;
            line-height: 1.6;
            user-select: none; /* Evita seleccionar texto durante el juego */
        }

        /* Efecto de líneas de escaneo (CRT) */
        .scanlines {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(
                to bottom,
                rgba(255,255,255,0),
                rgba(255,255,255,0) 50%,
                rgba(0,0,0,0.2) 50%,
                rgba(0,0,0,0.2)
            );
            background-size: 100% 4px;
            pointer-events: none;
            z-index: 10;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            border: 1px solid #333;
            background-color: #0a0a0a;
            padding: 30px;
            box-shadow: 0 0 20px rgba(0,0,0,0.9);
            position: relative;
            z-index: 1;
        }

        /* --- TIPOGRAFÍA Y ENCABEZADOS --- */
        h1 {
            color: #b30000;
            font-size: 2.5em;
            text-shadow: 2px 2px 0px #000;
            letter-spacing: 5px;
            text-align: center;
            border-bottom: 2px solid #333;
            padding-bottom: 10px;
        }

        h2, h3 {
            text-transform: uppercase;
            border-bottom: 1px solid #333;
            color: #ccc;
        }

        .warning-box {
            background-color: #380000;
            color: #ffcccc;
            border: 1px solid #ff0000;
            padding: 15px;
            margin-bottom: 25px;
            text-align: center;
            font-weight: bold;
            animation: pulse 2s infinite;
        }

        /* --- IMAGEN MALDITA --- */
        .entity-image-container {
            text-align: center;
            margin: 20px 0;
            position: relative;
        }

        .entity-img {
            max-width: 100%;
            width: 400px;
            height: auto;
            border: 5px solid #111;
            filter: contrast(1.2) grayscale(80%);
            transition: all 0.3s ease;
        }

        .entity-img:hover {
            filter: contrast(1.5) grayscale(0%);
            border-color: #500;
            transform: scale(1.02);
        }

        /* --- DATA BLOCKS --- */
        .data-block {
            margin-bottom: 20px;
            padding: 15px;
            background: #111;
            border-left: 3px solid #555;
        }

        .label { color: #888; font-weight: bold; }
        ul { list-style-type: square; }
        li { margin-bottom: 8px; }
        blockquote {
            font-style: italic;
            border-left: 2px solid #b30000;
            margin: 20px;
            padding-left: 15px;
            color: #aaa;
            background: #0f0f0f;
            padding: 10px;
        }

        /* --- ANIMACIONES --- */
        @keyframes pulse {
            0% { box-shadow: 0 0 5px #500; }
            50% { box-shadow: 0 0 20px #f00; }
            100% { box-shadow: 0 0 5px #500; }
        }

        .glitch { position: relative; }
        .glitch::before, .glitch::after {
            content: "MR. EYES";
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: #0a0a0a;
        }
        .glitch::before {
            left: 2px; text-shadow: -1px 0 red; clip: rect(24px, 550px, 90px, 0);
            animation: glitch-anim-1 2.5s infinite linear alternate-reverse;
        }
        .glitch::after {
            left: -2px; text-shadow: -1px 0 blue; clip: rect(85px, 550px, 140px, 0);
            animation: glitch-anim-2 3s infinite linear alternate-reverse;
        }
        @keyframes glitch-anim-1 { 0% { clip: rect(20px, 9999px, 10px, 0); } 100% { clip: rect(80px, 9999px, 90px, 0); } }
        @keyframes glitch-anim-2 { 0% { clip: rect(10px, 9999px, 80px, 0); } 100% { clip: rect(90px, 9999px, 10px, 0); } }

        /* --- MINI JUEGO ESTILOS --- */
        .game-btn {
            display: block;
            width: 100%;
            padding: 20px;
            background: #111;
            color: red;
            border: 1px solid red;
            font-family: 'Courier New', Courier, monospace;
            font-size: 1.2em;
            cursor: pointer;
            text-transform: uppercase;
            margin-top: 30px;
            transition: 0.3s;
        }
        .game-btn:hover { background: red; color: black; font-weight: bold; }

        #game-overlay {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: black;
            z-index: 100;
            cursor: crosshair;
        }

        #game-ui {
            position: absolute;
            top: 20px;
            width: 100%;
            text-align: center;
            color: white;
            z-index: 101;
            pointer-events: none;
        }

        .creepy-eye {
            position: absolute;
            width: 60px;
            height: 30px;
            font-size: 25px;
            color: white;
            text-shadow: 0 0 10px red;
            cursor: pointer;
            user-select: none;
            display: flex;
            justify-content: center;
            align-items: center;
            font-weight: bold;
        }

        .creepy-eye:hover {
            color: #333;
            text-shadow: none;
        }

        #jumpscare {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background-color: black;
            background-image: url('1000000608.png'); /* La misma imagen */
            background-size: cover;
            background-position: center;
            z-index: 200;
            filter: contrast(2) sepia(1) hue-rotate(-50deg) saturate(5);
        }
        
        #jumpscare h1 {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 5em;
            color: red;
            background: black;
            padding: 20px;
        }

    </style>
</head>
<body>

    <div class="scanlines"></div>

    <div id="game-overlay">
        <div id="game-ui">
            <h2>SOBREVIVE: <span id="timer">30</span>s</h2>
            <p>OJOS OBSERVANDO: <span id="eye-count" style="color:red">0</span> / 5</p>
            <p style="font-size: 0.8em; color: #666;">Haz clic en los ojos para cerrarlos...</p>
        </div>
    </div>

    <div id="jumpscare">
        <h1>TE VEO</h1>
    </div>

    <div class="container">
        <h1 class="glitch">MR. EYES</h1>

        <div class="warning-box">
            ⚠ ALERTA DE NIVEL 5: NO MIRAR LA IMAGEN POR MÁS DE 10 SEGUNDOS.
        </div>

        <div class="entity-image-container">
            <img src="1000000608.png" alt="Fotografía recuperada de Mr. Eyes" class="entity-img">
            <p style="font-size: 10px; color: #555;">Fig 1.1: Fotografía recuperada.</p>
        </div>

        <div class="data-block">
            <h3>👤 PERFIL DE LA ENTIDAD</h3>
            <p><span class="label">CLASIFICACIÓN:</span> Hostil / Parasitario</p>
            <p><span class="label">UBICACIÓN:</span> Rincones oscuros.</p>
        </div>

        <div class="content-text">
            <h2>LA LEYENDA</h2>
            <p>Mr. Eyes no tiene ojos, pero los quiere. Posee una visión omnisciente. Su sonrisa es una herida anatómica imposible.</p>
            
            <h2>💀 MODUS OPERANDI</h2>
            <ul>
                <li><strong>Fase 1:</strong> Sensación de ser observado.</li>
                <li><strong>Fase 2:</strong> Sombras en la visión periférica.</li>
                <li><strong>Fase 3:</strong> Parálisis del sueño a las 3:33 AM.</li>
            </ul>

            <div class="warning-box" style="background: #000; border: 1px dashed #555; color: #fff;">
                <strong>REGLA DE ORO:</strong> Si sientes que te mira, NO LE DEVUELVAS LA MIRADA.
            </div>

            <h2>🎙 TESTIMONIO</h2>
            <blockquote>
                "No tiene ojos, pero lloraba líquido negro. Me dijo que mis ojos eran 'hermosos' y que quedarían perfectos en su colección..."
            </blockquote>
        </div>

        <button class="game-btn" onclick="startGame()">⚔ INICIAR RITUAL DE CONTENCIÓN</button>

        <div class="footer" style="margin-top: 20px; text-align: center; color: #444; font-size: 0.8em;">
            EXPEDIENTE #89-B | CONFIDENCIAL
        </div>
    </div>

    <script>
        // --- LÓGICA DEL JUEGO ---
        let gameActive = false;
        let score = 0;
        let timeLeft = 30;
        let eyeCount = 0;
        let spawnRate = 1000;
        let gameLoop;
        let spawnLoop;

        const overlay = document.getElementById('game-overlay');
        const timerDisplay = document.getElementById('timer');
        const eyeCountDisplay = document.getElementById('eye-count');
        const jumpscareScreen = document.getElementById('jumpscare');

        function startGame() {
            gameActive = true;
            timeLeft = 30;
            eyeCount = 0;
            spawnRate = 800;
            
            overlay.style.display = 'block';
            updateDisplay();
            
            // Ciclo de tiempo
            gameLoop = setInterval(() => {
                timeLeft--;
                updateDisplay();
                
                // Aumentar dificultad
                if (timeLeft < 20) spawnRate = 600;
                if (timeLeft < 10) spawnRate = 400;

                if (timeLeft <= 0) {
                    winGame();
                }
            }, 1000);

            // Ciclo de aparición de ojos
            spawnEyesLoop();
        }

        function spawnEyesLoop() {
            if (!gameActive) return;
            
            spawnEye();
            
            // Llama recursivamente con la nueva velocidad
            setTimeout(spawnEyesLoop, spawnRate);
        }

        function spawnEye() {
            if(eyeCount >= 5) {
                loseGame();
                return;
            }

            const eye = document.createElement('div');
            eye.classList.add('creepy-eye');
            eye.innerHTML = '◉ ◉'; // Símbolo de ojos
            
            // Posición aleatoria
            const x = Math.random() * (window.innerWidth - 100);
            const y = Math.random() * (window.innerHeight - 100);
            
            eye.style.left = x + 'px';
            eye.style.top = y + 'px';

            // Evento al hacer clic (matar al ojo)
            eye.onclick = function() {
                this.remove();
                eyeCount--;
                updateDisplay();
                // Sonido visual (flash)
                overlay.style.backgroundColor = '#111';
                setTimeout(() => overlay.style.backgroundColor = 'black', 50);
            };

            overlay.appendChild(eye);
            eyeCount++;
            updateDisplay();
        }

        function updateDisplay() {
            timerDisplay.innerText = timeLeft;
            eyeCountDisplay.innerText = eyeCount;
            
            // Efecto visual si hay muchos ojos
            if(eyeCount >= 3) {
                eyeCountDisplay.style.fontSize = "1.5em";
                overlay.style.boxShadow = "inset 0 0 50px red";
            } else {
                eyeCountDisplay.style.fontSize = "1em";
                overlay.style.boxShadow = "none";
            }
        }

        function loseGame() {
            gameActive = false;
            clearInterval(gameLoop);
            
            // Jumpscare
            jumpscareScreen.style.display = 'block';
            
            // Vibrar si es móvil
            if (navigator.vibrate) navigator.vibrate(500);

            setTimeout(() => {
                location.reload(); // Reiniciar página
            }, 3000);
        }

        function winGame() {
            gameActive = false;
            clearInterval(gameLoop);
            alert("HAS SOBREVIVIDO... POR AHORA. Mr. Eyes se retira a las sombras.");
            location.reload();
        }

        // --- EFECTO AMBIENTAL IMAGEN ---
        const img = document.querySelector('.entity-img');
        setInterval(() => {
            if(Math.random() > 0.92) {
                img.style.opacity = 0.5;
                setTimeout(() => img.style.opacity = 1, 50);
            }
        }, 1000);
    </script>
</body>
</html>
