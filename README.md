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
            margin-bottom: 20px;
            box-shadow: inset 0 2px 4px rgba(0,0,0,0.02);
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

        <div class="firma">Con amor, Leonardo</div>
    </div>

</body>
</html>
