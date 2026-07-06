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
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            margin: 0;
            padding: 30px 20px;
            box-sizing: border-box;
        }

        /* --- ESTILOS DEL SOBRE INTERACTIVO --- */
        .contenedor-sobre {
            perspective: 1000px;
            margin-bottom: 40px;
            display: flex;
            flex-direction: column;
            align-items: center;
            width: 100%;
            max-width: 450px;
        }

        .frase-sobre-superior {
            color: #ffffff;
            font-size: 18px;
            font-weight: bold;
            letter-spacing: 2px;
            margin-bottom: 20px;
            text-align: center;
            text-shadow: 0 2px 10px rgba(255, 255, 255, 0.3);
            font-family: 'Courier New', Courier, monospace;
        }

        .sobre {
            position: relative;
            width: 100%;
            height: 250px;
            background-color: var(--color-vino);
            border-radius: 0 0 15px 15px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.6);
            cursor: pointer;
            transition: transform 0.5s ease;
        }

        .sobre:hover {
            transform: translateY(-5px);
        }

        .sobre::before {
            content: "";
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 0;
            border-left: 225px solid transparent;
            border-right: 225px solid transparent;
            border-bottom: 150px solid var(--color-vino-claro);
            border-radius: 0 0 15px 15px;
            z-index: 3;
            box-sizing: border-box;
        }

        @media (max-width: 450px) {
            .sobre::before {
                border-left-width: calc(50vw - 20px);
                border-right-width: calc(50vw - 20px);
            }
        }

        .solapa {
            position: absolute;
            top: 0;
            left: 0;
            width: 0;
            height: 0;
            border-left: 225px solid transparent;
            border-right: 225px solid transparent;
            border-top: 130px solid var(--color-vino-oscuro);
            transform-origin: top;
            transition: transform 0.4s ease 0.2s, z-index 0.2s ease 0.2s;
            z-index: 4;
        }

        @media (max-width: 450px) {
            .solapa {
                border-left-width: calc(50vw - 20px);
                border-right-width: calc(50vw - 20px);
            }
        }

        .sobre.abierto .solapa {
            transform: rotateX(180deg);
            z-index: 1;
            transition: transform 0.4s ease, z-index 0.2s ease 0.2s;
        }

        .texto-sobre-interior {
            position: absolute;
            bottom: 30px;
            width: 100%;
            text-align: center;
            color: var(--color-crema-rosa);
            font-size: 16px;
            font-weight: 600;
            letter-spacing: 1.5px;
            z-index: 5;
            text-shadow: 0 2px 4px rgba(0,0,0,0.5);
            padding: 0 15px;
            box-sizing: border-box;
        }

        /* --- CONFIGURACIÓN DE LAS 3 SECCIONES (TABS) --- */
        .contenedor-navegacion {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 30px;
            width: 100%;
            max-width: 600px;
            opacity: 0;
            pointer-events: none;
            transition: opacity 0.6s ease;
        }

        .contenedor-navegacion.visible {
            opacity: 1;
            pointer-events: auto;
        }

        .boton-tab {
            background: linear-gradient(135deg, var(--color-negro) 0%, var(--color-vino-oscuro) 100%);
            color: var(--color-crema-rosa);
            border: 2px solid var(--color-vino-claro);
            padding: 12px 20px;
            font-size: 14px;
            font-weight: bold;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 4px 15px rgba(0,0,0,0.4);
        }

        .boton-tab:hover, .boton-tab.activo {
            background: var(--color-vino-claro);
            border-color: #ffffff;
            transform: scale(1.05);
            box-shadow: 0 6px 20px rgba(114, 47, 55, 0.6);
        }

        /* --- TARJETA PRINCIPAL DE CONTENIDO --- */
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
            display: none;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease, transform 0.5s ease;
        }

        .tarjeta-carta.visible {
            display: block;
            opacity: 1;
            transform: translateY(0);
        }

        .seccion-contenido {
            display: none;
        }

        .seccion-contenido.activa {
            display: block;
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
            margin-bottom: 20px;
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.02);
        }

        /* --- SECCIÓN DE MÚSICA MISTERIOSA (ME SIENTO ASÍ) --- */
        .contenedor-musica {
            background: var(--color-crema-rosa);
            padding: 20px;
            border-radius: 15px;
            border: 2px dashed var(--color-vino-claro);
            margin-top: 10px;
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

        /* --- SECCIÓN: CARRETERA PARA EL AMOR DE MI VIDA --- */
        .contenedor-carretera {
            background: var(--color-crema-rosa);
            padding: 20px;
            border-radius: 15px;
            border: 2px dashed var(--color-vino-claro);
        }

        .titulo-carretera {
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

        .bloque-imagen {
            margin-bottom: 25px;
            text-align: center;
            padding-bottom: 15px;
            border-bottom: 1px dashed #d9c5c7;
        }

        .bloque-imagen:last-of-type {
            border-bottom: none;
            padding-bottom: 0;
            margin-bottom: 15px;
        }

        .imagen-proyecto {
            width: 100%;
            max-width: 100%;
            height: auto;
            border-radius: 12px;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
            margin-bottom: 10px;
            display: block;
        }

        .dedicatoria-imagen {
            color: #444444;
            font-size: 14.5px;
            line-height: 1.5;
            font-style: italic;
            background: #ffffff;
            padding: 12px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.03);
            text-align: left;
        }

        .texto-broma {
            color: var(--color-negro);
            font-size: 15px;
            line-height: 1.6;
            text-align: left;
            background: #ffffff;
            padding: 15px;
            border-radius: 10px;
            border-left: 4px solid var(--color-vino-claro);
            margin-top: 15px;
            font-weight: 500;
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

    <div class="contenedor-sobre" id="contenedor-sobre">
        <div class="frase-sobre-superior">"AHORA IGNORAME A VER....."</div>
        <div class="sobre" id="sobre" onclick="abrirCarta()">
            <div class="solapa"></div>
            <div class="texto-sobre-interior">PARA EL AMOR DE MI VIDA</div>
        </div>
    </div>

    <div class="contenedor-navegacion" id="navegacion">
        <button class="boton-tab activo" onclick="cambiarTab(0)">❤️ Mi amor....</button>
        <button class="boton-tab" onclick="cambiarTab(1)">🎵 Me siento asi...</button>
        <button class="boton-tab" onclick="cambiarTab(2)">🚧 Una carretera para el amor de mi vida...</button>
    </div>

    <div class="tarjeta-carta" id="tarjeta-carta">
        <span class="corazon">❤️</span>
        <h1 id="titulo-dinamico">Para Wendy</h1>
        
        <div id="sec-mi-amor" class="seccion-contenido activa">
            <div class="bloque-texto">Mi amor...

No sé qué está pasando y, siendo sincero, estoy muy preocupado. Este silencio no se siente normal para mí y lo único que quisiera saber es si estás bien. Si hay algo que pasó, si hice algo que te lastimó o simplemente necesitas espacio, solo te pido que me lo digas cuando te sientas lista. Prefiero una verdad que duela antes que imaginar mil cosas.

Quisiera que habláramos en persona. Si hace falta, yo voy hasta donde estés. No quiero discutir ni presionarte; solo quiero escucharte, entender qué está pasando y hablar contigo con calma.

No quiero perder lo que hemos construido. Te amo muchísimo, Wendy, y por eso sigo aquí. Creo en nosotros y quiero luchar por esto, pero también quiero hacerlo de la manera correcta: escuchándote y respetando lo que sientes.

Si en algún momento te hice sentir mal, de verdad lo siento. Sé que me equivoco, como cualquier persona, pero también sé reconocer mis errores y quiero aprender de ellos. Lo único que busco es ser una mejor persona para ti y para el futuro que soñaba construir contigo.

Solo quería que supieras cómo me siento. No escribo esto para hacerte violentar ni para obligarte a responder; lo hago porque te amo y porque me importas de verdad.

Espero de corazón que estés bien. Cuando quieras hablar, aquí voy a estar.

Y, por favor, nunca dudes de esto: te amo muchísimo y siempre voy a desear lo mejor para ti.</div>
        </div>

        <div id="sec-me-siento" class="seccion-contenido">
            <div class="contenedor-musica">
                <div class="titulo-musica">"-7 canciones para dedicar( de hecho son mas pero ahora estoy contabilizando) AJAJAJAJ"</div>
                
                <div class="bloque-cancion">
                    <div class="dedicatoria-cancion">"Yo me siento asi contigo mi amor y tu lo sabes es una de la primeras canciones que te dedique pero enserio gracias mi amor por estar en mi vida, y por hacerme cambiar la perspectiva en muchas cosas.."</div>
                    <audio id="audio6" src="cancion6.mp3"></audio>
                    <button class="boton-reproductor" onclick="controlarAudio('audio6', 30, 180)">
                        <span class="icono-play" id="icono-audio6">▶</span> <span id="texto-audio6">Canción 6</span>
                    </button>
                </div>

                <div class="bloque-cancion">
                    <div class="dedicatoria-cancion">"Y hoy me siento asi escuchala de verdad es mi manera mas honesta de decir todo lo que quiero contigo"</div>
                    <audio id="audio7" src="cancion7.mp3"></audio>
                    <button class="boton-reproductor" onclick="controlarAudio('audio7', 45, 183)">
                        <span class="icono-play" id="icono-audio7">▶</span> <span id="texto-audio7">Canción 7</span>
                    </button>
                </div>

                <div class="bloque-cancion">
                    <div class="dedicatoria-cancion">Y quiero que sepas algo más...
Soy muy miedoso, tú lo sabes. Me pongo muy nervioso con todo esto y, aunque no siempre lo parezca, me cuesta muchísimo decirte cómo me siento. Abrirme de esta manera no es algo que me salga natural.

Todo esto es nuevo para mí. Nunca había querido construir algo tan en serio con alguien y, muchas veces, no sé cuál es la forma correcta de reaccionar. Pero te juro que siempre intento pensar las cosas antes de actuar contigo. No tomo decisiones a la ligera, porque lo nuestro es demasiado importante para mí.

Tal vez suene un poco tonto, pero hasta me pongo a ver videos de psicología en TikTok jajaja. Hay una cuenta que sigo mucho(psialap) porque quiero entenderme mejor, aprender a comunicarme mejor y dejar atrás cosas que sé que debo cambiar. No lo hago porque alguien me obligue; lo hago porque quiero ser una mejor persona y porque sueño con tener un futuro contigo.

No pretendo que pienses que soy perfecto, porque no lo soy. Solo quiero que que veas el esfuerzo que estoy haciendo. Hay días en los que tengo miedo de equivocarme, miedo de decir algo que no debía o de perderte por no saber expresar lo que siento. Aun así, sigo intentándolo porque para mí tú vales ese esfuerzo.

También me identifico con esa idea de intentar ser mejor que ayer. No porque alguien me lo exija, sino porque quiero crecer como persona. Quiero aprender a comunicarme mejor, a manejar mis inseguridades y a no dejar que mis miedos dañen algo tan bonito como lo que siento por ti.

No sabes cuánto me preparo antes de hablar contigo o antes de escribirte algo importante. A veces hasta ensayo en mi cabeza lo que quiero decir para no hacerlo mal jajaja. Puede sonar exagerado, pero es porque eres una de las personas más importantes que han llegado a mi vida y de verdad quiero cuidar lo que estamos construyendo.

Solo quería que supieras eso.</div>
                    <audio id="audio8" src="cancion8.mp3"></audio>
                    <button class="boton-reproductor" onclick="controlarAudio('audio8', 196, 260)">
                        <span class="icono-play" id="icono-audio8">▶</span> <span id="texto-audio8">así me siento de depre....</span>
                    </button>
                </div>
            </div>
        </div>

        <div id="sec-carretera" class="seccion-contenido">
            <div class="contenedor-carretera">
                <div class="titulo-carretera">🚧 UNA CARRETERA PARA EL AMOR DE MI VIDA 🚧</div>
                
                <div class="bloque-imagen">
                    <img src="imagen1.jpg" alt="Carretera 1" class="imagen-proyecto">
                    <div class="dedicatoria-imagen">"Una carretera bien diseñada conecta destinos; tú conectaste mi presente con el futuro que quiero construir."</div>
                </div>

                <div class="bloque-imagen">
                    <img src="imagen2.jpg" alt="Carretera 2" class="imagen-proyecto">
                    <div class="dedicatoria-imagen">"Entre todas las secciones transversales que he dibujado, la única que de verdad quiero estudiar es el camino que me lleva a tu corazón."</div>
                </div>

                <div class="texto-broma">si lo hice jajajaj te paso el documneto ok no JJAJAJAJA y bueno wendy decirte que de verdad te amo mucho mi amor....</div>
            </div>
        </div>

        <div class="firma">Con amor, Leonardo</div>
    </div>

    <script>
        const estadosIniciales = {};

        // Función para manejar la apertura del sobre inicial
        function abrirCarta() {
            const sobre = document.getElementById('sobre');
            sobre.classList.add('abierto');

            setTimeout(() => {
                document.getElementById('contenedor-sobre').style.display = 'none';
                
                const navegacion = document.getElementById('navegacion');
                const tarjeta = document.getElementById('tarjeta-carta');
                
                navegacion.classList.add('visible');
                tarjeta.classList.add('visible');
            }, 800);
        }

        // Función para cambiar de sección controlada por los 3 botones superiores
        function cambiarTab(indice) {
            const tabs = document.querySelectorAll('.boton-tab');
            const secciones = document.querySelectorAll('.seccion-contenido');
            
            // Pausar cualquier audio activo al cambiar de sección
            document.querySelectorAll('audio').forEach(aud => {
                aud.pause();
                const icono = document.getElementById('icono-' + aud.id);
                if (icono) icono.innerText = '▶';
            });

            tabs.forEach(tab => tab.classList.remove('activo'));
            secciones.forEach(sec => sec.classList.remove('activa'));

            tabs[indice].classList.add('activo');
            secciones[indice].classList.add('activa');
        }

        // Reproductor de música personalizado
        function controlarAudio(idAudio, tiempoInicio, tiempoFin) {
            const audio = document.getElementById(idAudio);
            const icono = document.getElementById('icono-' + idAudio);

            document.querySelectorAll('audio').forEach(aud => {
                if (aud.id !== idAudio && !aud.paused) {
                    aud.pause();
                    const iconoAud = document.getElementById('icono-' + aud.id);
                    if (iconoAud) iconoAud.innerText = '▶';
                }
            });

            if (audio.paused) {
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

            audio.ontimeupdate = () => {
                if (audio.currentTime < tiempoInicio) {
                    audio.currentTime = tiempoInicio;
                }
                if (audio.currentTime >= tiempoFin) {
                    audio.pause();
                    audio.currentTime = tiempoInicio;
                    icono.innerText = '▶';
                    estadosIniciales[idAudio] = false;
                }
            };
        }
    </script>
</body>
</html>
