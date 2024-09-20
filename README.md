<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invitación de Boda 3D</title>
    <link href="https://fonts.googleapis.com/css2?family=Garamond&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            background-image: url('img/july.jpg');
            background-size: cover;
            background-position: center;
            font-family: 'Garamond', serif;
            overflow: hidden;
            position: relative;
            flex-direction: column; /* Cambiar a columna para móviles */
        }

        .scene {
            width: 400px;
            height: 600px;
            perspective: 1500px;
            margin-bottom: 20px; /* Espacio para botones en móvil */
        }

        .card {
            width: 100%;
            height: 100%;
            position: relative;
            transform-style: preserve-3d;
            transition: transform 2s ease-in-out, box-shadow 1s ease-in-out;
        }

        .card.is-flipped {
            transform: rotateY(180deg) scale(1.2);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.4);
        }

        .card-face {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 15px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
        }

        .card-front {
            background: linear-gradient(135deg, #ffecd2 0%, #fcb69f 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }

        .card-front h2 {
            font-size: 2.8rem;
            color: #333;
            text-align: center;
        }

        .card-front p {
            font-size: 1.4rem;
            color: #555;
            margin-top: 10px;
            text-align: center;
        }

        .card-front img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
            margin-top: 10px;
        }

        .card-back {
            background-color: #fff;
            padding: 20px;
            transform: rotateY(180deg);
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
        }

        .card-back h3 {
            font-size: 2rem;
            color: #333;
        }

        .card-back p {
            font-size: 1.2rem;
            color: #666;
            margin: 20px 0;
        }

        .card-back img {
            max-width: 100%;
            height: auto;
            border-radius: 10px;
            margin-top: 10px;
        }

        .cta, .open-btn, .link-box {
            font-size: 1.4rem;
            color: #fff;
            background-color: #8A0F0F;
            padding: 10px 25px;
            border-radius: 8px;
            text-decoration: none;
            margin-top: 20px;
            transition: background-color 0.3s ease;
            display: block; /* Asegura que ocupen el ancho completo */
            text-align: center;
        }

        .cta:hover, .open-btn:hover, .link-box:hover {
            background-color: #b3701d;
        }

        .phone-numbers {
            display: flex; /* Asegura que las imágenes se alineen en línea */
            flex-direction: column; /* Alinea en columna para móviles */
            align-items: center; /* Centra las imágenes */
            position: relative; /* Cambia a relativo para alineación adecuada */
            margin-top: 20px; /* Añadir espacio encima */
        }

        /* Media Query para dispositivos móviles */
        @media (max-width: 768px) {
            body {
                justify-content: flex-start; /* Alinear al inicio en móvil */
                padding-top: 20px; /* Espacio en la parte superior */
            }

            .scene {
                width: 300px;
                height: 450px;
            }

            .card-front h2 {
                font-size: 2rem;
            }

            .card-front p {
                font-size: 1rem;
            }

            .card-back h3 {
                font-size: 1.6rem;
            }

            .card-back p {
                font-size: 1rem;
            }

            .open-btn, .link-box {
                font-size: 1.2rem;
                padding: 10px 20px;
            }

            .phone-numbers {
                font-size: 1rem;
            }

            .cta {
                font-size: 1.2rem;
                padding: 8px 20px;
            }
        }
    </style>
</head>
<body>

<div class="scene">
    <div class="card" id="invitationCard">
        <div class="card-face card-front">
            <h2>¡Te Invitamos!</h2>
            <p>A nuestra boda</p>
            <img src="img/july3.jpg" alt="Imagen ilustrativa de la boda de los novios">
        </div>

        <div class="card-face card-back">
            <h3>24 de Diciembre, 2024</h3>
            <p>Jardines del Sol, Colombia</p>
            <img src="img/july5.jpg" alt="Lugar del evento de la boda: Jardines del Sol, Colombia">
            <a href="#" class="cta">Confirmar Asistencia</a>
        </div>
    </div>
</div>

<div style="display: flex; flex-direction: column; align-items: center;">
    <button class="open-btn" onclick="toggleCard()">Abrir Invitación</button>
    <a href="https://www.google.com/maps/place/Av.+80+%2345f-77,+La+Floresta,+Medell%C3%ADn,+La+Am%C3%A9rica,+Medell%C3%ADn,+Antioquia/@6.2552993,-75.5998501,17z/data=!4m6!3m5!1s0x8e4429749f157ef7:0xfb20bd99c3474c7c!8m2!3d6.2552886!4d-75.598745!16s%2Fg%2F11d_tkq116?entry=tts&g_ep=EgoyMDI0MDkxNi4wKgBIAVAD" class="link-box" target="_blank">Visitar Enlace</a>
</div>

<div class="phone-numbers">
    <img src="img/colores reservados.png" class="extra-image" alt="Colores Reservados">
    <img src="img/numeros.png" alt="Números de contacto">
</div>

<audio id="backgroundMusic" loop>
    <source src="https://www.youtube.com/watch?v=weKJWqw8-3g" type="audio/mpeg">
    Tu navegador no soporta el elemento de audio.
</audio>

<script>
    function toggleCard() {
        const card = document.getElementById('invitationCard');
        card.classList.toggle('is-flipped');
    }
</script>

</body>
</html>
