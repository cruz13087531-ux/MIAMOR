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

        /* --- SECCIÓN DE MÚSICA --- */
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
            font-size: 18px;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 1px;
            border-bottom: 2px solid var(--color-vino);
            padding-bottom: 8px;
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

        .info-cancion {
            font-size: 15px;
            font-weight: bold;
            color: var(--color-vino-oscuro);
            margin-bottom: 5px;
        }

        .dedicatoria-cancion {
            color: #444444;
            font-size: 14.5px;
            line-height: 1.5;
            margin-bottom: 12px;
            font-style: italic;
            background: #ffffff;
            padding: 12px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.03);
        }

        audio {
            width: 100%;
            margin-top: 5px;
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

        <!-- REPRODUCTORES DE MÚSICA CON TIEMPOS CONFIGURADOS -->
        <div class="contenedor-musica">
            <div class="titulo-musica">🎵 Canciones para escuchar</div>
            
            <!-- CANCIÓN 6 -->
            <div class="bloque-cancion">
                <div class="info-cancion">1. Talismán - Rata Blanca</div>
                <div class="dedicatoria-cancion">"Yo me siento asi contigo mi amor y tu lo sabes es una de la primeras canciones que te dedique pero enserio gracias mi amor por estar en mi vida, y por hacerme cambiar la perspectiva en muchas cosas.."</div>
                <audio id="audio6" controls src="cancion6"></audio>
            </div>

            <!-- CANCIÓN 7 -->
            <div class="bloque-cancion">
                <div class="info-cancion">2. Necesito tu amor - Charly García</div>
                <div class="dedicatoria-cancion">"Y hoy me siento asi escuchala de verdad es mi manera mas honesta de decir todo lo que quiero contigo"</div>
                <audio id="audio7" controls src="cancion7"></audio>
            </div>
        </div>

        <div class="firma">Con amor, Leonardo</div>
    </div>

    <script>
        // Configuración para Canción 6: Inicia en 0:30 (30s) y termina en 3:00 (180s)
        const audio6 = document.getElementById('audio6');
        let inicializado6 = false;

        audio6.addEventListener('play', () => {
            if (!inicializado6) {
                audio6.currentTime = 30;
                inicializado6 = true;
            }
        });

        audio6.addEventListener('timeupdate', () => {
            if (audio6.currentTime >= 180) {
                audio6.pause();
            }
        });

        // Configuración para Canción 7: Inicia en 0:45 (45s) y termina en 3:03 (183s)
        const audio7 = document.getElementById('audio7');
        let inicializado7 = false;

        audio7.addEventListener('play', () => {
            if (!inicializado7) {
                audio7.currentTime = 45;
                inicializado7 = true;
            }
        });

        audio7.addEventListener('timeupdate', () => {
            if (audio7.currentTime >= 183) {
                audio7.pause();
            }
        });
    </script>
</body>
</html>
