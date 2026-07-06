<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Para Ti</title>
    <style>
        :root {
            --color-vino-oscuro: #2c050b;
            --color-vino: #58111a;
            --color-vino-claro: #722f37;
            --color-negro: #0d0204;
            --color-crema-rosa: #fdf5f6;
        }

        body {
            background: linear-gradient(135deg, var(--color-negro) 0%, var(--color-vino-oscuro) 50%, var(--color-negro) 100%);
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 20px;
            box-sizing: border-box;
        }

        .tarjeta-carta {
            background-color: #ffffff;
            padding: 40px 30px;
            border-radius: 25px;
            box-shadow: 0px 20px 50px rgba(0, 0, 0, 0.9);
            max-width: 600px;
            width: 100%;
            border: 4px solid var(--color-vino);
            box-sizing: border-box;
            text-align: center;
        }

        .corazon {
            color: var(--color-vino-claro);
            font-size: 45px;
            animation: latido 1.3s infinite;
            display: block;
            margin-bottom: 10px;
        }

        @keyframes latido {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        h1 {
            color: var(--color-vino);
            font-size: 28px;
            margin-bottom: 25px;
            letter-spacing: 1px;
        }

        .bloque-texto {
            color: var(--color-negro);
            font-size: 16px;
            line-height: 1.7;
            text-align: left;
            white-space: pre-line;
            background-color: var(--color-crema-rosa);
            padding: 25px;
            border-radius: 15px;
            border-left: 5px solid var(--color-vino);
            margin-bottom: 30px;
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.02);
        }

        /* --- SECCIÓN DE MÚSICA MISTERIOSA --- */
        .contenedor-musica {
            background: var(--color-crema-rosa);
            padding: 20px;
            border-radius: 15px;
            border: 2px dashed var(--color-vino-claro);
            margin-top: 20px;
        }

        .titulo-musica {
            color: var(--color-vino);
            font-weight: bold;
            font-size: 16px;
            margin-bottom: 20px;
            letter-spacing: 0.5px;
            border-bottom: 2px solid var(--color-vino);
            padding-bottom: 8px;
            line-height: 1.4;
            text-align: center;
        }

        .bloque-cancion {
            margin-bottom: 25px;
            text-align: left;
            padding-bottom: 15px;
            border-bottom: 1px dashed #d9c5c7;
        }

        .bloque-cancion:last-child {
            border-bottom: none;
            padding-bottom: 0;
            margin-bottom: 0;
        }

        .dedicatoria-cancion {
            color: #444444;
            font-size: 14.5px;
            line-height: 1.5;
            margin-bottom: 15px;
            font-style: italic;
            background: #ffffff;
            padding: 12px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.03);
            white-space: pre-line;
        }

        /* --- ESTILO DE BOTÓN IGUAL A TU CAPTURA --- */
        .boton-reproductor {
            background: linear-gradient(to right, #400a11, #1d0306);
            color: white;
            border: none;
            width: 100%;
            padding: 14px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 12px;
            cursor: pointer;
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 10px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.3);
            transition: background 0.3s ease;
        }

        .boton-reproductor:hover {
            background: linear-gradient(to right, #500f17, #2c050b);
        }

        .icono-play {
            font-size: 14px;
        }

        .firma {
            margin-top: 30px;
            font-size: 15px;
            color: var(--color-vino-claro);
            font-weight: bold;
            font-style: italic;
            text-align: right;
        }
    </style>
</head>
<body>

    <div class="tarjeta-carta">
        <span class="corazon">❤️</span>
        <h1>Para Wendy</h1>
        
        <div class="bloque-texto">Mi amor...

No sé qué está pasando y, siendo sincero, estoy muy preocupado. Este silencio no se siente normal para mí y lo único que quisiera saber es si estás bien. Si hay algo que pasó, si hice algo que te lastimó o simplemente necesitas espacio, solo te pido que me lo digas cuando te sientas lista. Prefiero una verdad que duela antes que imaginar mil cosas.

Quisiera que habláramos en persona. Si hace falta, yo voy hasta donde estés. No quiero discutir ni presionarte; solo quiero escucharte, entender qué está pasando y hablar contigo con calma.

No quiero perder lo que hemos construido. Te amo muchísimo, Wendy, y por eso sigo aquí. Creo en nosotros y quiero luchar por esto, pero también quiero hacerlo de la manera correcta: escuchándote y respetando lo que sientes.

Si en algún momento te hice sentir mal, de verdad lo siento. Sé que me equivoco, como cualquier persona, pero también sé reconocer mis errores y quiero aprender de ellos. Lo único que busco es ser una mejor persona para ti y para el futuro que soñaba construir contigo.

Solo quería que supieras cómo me siento. No escribo esto para hacerte sentir culpable ni para obligarte a responder; lo hago porque te amo y porque me importas de verdad.

Espero de corazón que estés bien. Cuando quieras hablar, aquí voy a estar.

Y, por favor, nunca dudes de esto: te amo muchísimo y siempre voy a desear lo mejor para ti.</div>

        <!-- SECCIÓN DE BOTONES INALTERABLES -->
        <div class="contenedor-musica">
            <div class="titulo-musica">"-7 canciones para dedicar( de hecho son mas pero ahora estoy contabilizando) AJAJAJAJ"</div>
            
            <!-- CANCIÓN 6 -->
            <div class="bloque-cancion">
                <div class="dedicatoria-cancion">"Yo me siento asi contigo mi amor y tu lo sabes es una de la primeras canciones que te dedique pero enserio gracias mi amor por estar en mi vida, y por hacerme cambiar la perspectiva en muchas cosas.."</div>
                <audio id="audio6" src="cancion6.mp3"></audio>
                <button class="boton-reproductor" onclick="controlarAudio('audio6', 30, 180)">
                    <span class="icono-play" id="icono-audio6">▶</span> <span id="texto-audio6">Canción 6</span>
                </button>
            </div>

            <!-- CANCIÓN 7 -->
            <div class="bloque-cancion">
                <div class="dedicatoria-cancion">"Y hoy me siento asi escuchala de verdad es mi manera mas honesta de decir todo lo que quiero contigo"</div>
                <audio id="audio7" src="cancion7.mp3"></audio>
                <button class="boton-reproductor" onclick="controlarAudio('audio7', 45, 183)">
                    <span class="icono-play" id="icono-audio7">▶</span> <span id="texto-audio7">Canción 7</span>
                </button>
            </div>

            <!-- CANCIÓN 8 (APARTADO DEPRE) -->
            <div class="bloque-cancion">
                <div class="dedicatoria-cancion">Y quiero que sepas algo más...
Soy muy miedoso, tú lo sabes. Me pongo muy nervioso con todo esto y, aunque no siempre lo parezca, me cuesta muchísimo decirte cómo me siento. Abrirme de esta manera no es algo que me salga natural.

Todo esto es nuevo para mí. Nunca había querido construir algo tan en serio con alguien y, muchas veces, no sé cuál es la forma correcta de reaccionar. Pero te juro que siempre intento pensar las cosas antes de actuar contigo. No tomo decisiones a la ligera, porque lo nuestro es demasiado importante para mí.

Tal vez suene un poco tonto, pero hasta me pongo a ver videos de psicología en TikTok jajaja. Hay una cuenta que sigo mucho(psialap) porque quiero entenderme mejor, aprender a comunicarme mejor y dejar atrás cosas que sé que debo cambiar. No lo hago porque alguien me obligue; lo hago porque quiero ser una mejor persona y porque sueño con tener un futuro contigo.

No pretendo que pienses que soy perfecto, porque no lo soy. Solo quiero que veas el esfuerzo que estoy haciendo. Hay días en los que tengo miedo de equivocarme, miedo de decir algo que no debía o de perderte por no saber expresar lo que siento. Aun así, sigo intentándolo porque para mí tú vales ese esfuerzo.

También me identifico con esa idea de intentar ser mejor que ayer. No porque alguien me lo exija, sino porque quiero crecer como persona. Quiero aprender a comunicarme mejor, a manejar mis inseguridades y a no dejar que mis miedos dañen algo tan bonito como lo que siento por ti.

No sabes cuánto me preparo antes de hablar contigo o antes de escribirte algo importante. A veces hasta ensayo en mi cabeza lo que quiero decir para no hacerlo mal jajaja. Puede sonar exagerado, pero es porque eres una de las personas más importantes que han llegado a mi vida y de verdad quiero cuidar lo que estamos construyendo.

Solo quería que supieras eso.</div>
                <audio id="audio8" src="cancion8.mp3"></audio>
                <button class="boton-reproductor" onclick="controlarAudio('audio8', 196, 260)">
                    <span class="icono-play" id="icono-audio8">▶</span> <span id="texto-audio8">así me siento de depre....</span>
                </button>
            </div>
        </div>

        <div class="firma">Con amor, Leonardo</div>
    </div>

    <script>
        // Diccionario para registrar si los audios ya se inicializaron en su segundo correspondiente
        const estadosIniciales = {};

        function controlarAudio(idAudio, tiempoInicio, tiempoFin) {
            const audio = document.getElementById(idAudio);
            const icono = document.getElementById('icono-' + idAudio);

            // Pausar cualquier otro audio que esté sonando
            document.querySelectorAll('audio').forEach(aud => {
                if (aud.id !== idAudio && !aud.paused) {
                    aud.pause();
                    document.getElementById('icono-' + aud.id).innerText = '▶';
                }
            });

            if (audio.paused) {
                // Si nunca ha empezado a sonar, lo forzamos a ir al segundo indicado
                if (!estadosIniciales[idAudio]) {
                    audio.currentTime = tiempoInicio;
                    estadosIniciales[idAudio] = true;
                }
                audio.play();
                icono.innerText = '⏸';
            } else {
                audio.pause();
                icono.innerText = '▶';
            }

            // Monitorear el tiempo para que no se pase del límite
            audio.ontimeupdate = () => {
                if (audio.currentTime < tiempoInicio) {
                    audio.currentTime = tiempoInicio;
                }
                if (audio.currentTime >= tiempoFin) {
                    audio.pause();
                    audio.currentTime = tiempoInicio;
                    icono.innerText = '▶';
                    estadosIniciales[idAudio] = false; // Permite reiniciar el ciclo si da play otra vez
                }
            };
        }
    </script>
</body>
</html>
