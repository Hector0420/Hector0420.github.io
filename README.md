# Hector0420.github.io
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Preparatoria Oficial No. 56 - YouTube</title>
    <style>
        /* Estilos generales */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }

        body {
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }

        header {
            background-color: #e62117; /* Rojo YouTube */
            color: white;
            padding: 1rem;
            text-align: center;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 1rem;
        }

        /* Sección del video destacado */
        .featured-video {
            margin: 2rem 0;
            text-align: center;
        }

        .video-container {
            position: relative;
            padding-bottom: 56.25%; /* Relación 16:9 */
            height: 0;
            overflow: hidden;
            margin-bottom: 1rem;
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
            border-radius: 8px;
        }

        /* Sección de videos adicionales */
        .video-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 1.5rem;
            margin: 2rem 0;
        }

        .video-card {
            background: white;
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }

        .video-card:hover {
            transform: translateY(-5px);
        }

        .thumbnail {
            width: 100%;
            height: 140px;
            background-color: #ddd;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #777;
            font-size: 0.9rem;
        }

        .video-info {
            padding: 1rem;
        }

        .video-info h3 {
            font-size: 1rem;
            margin-bottom: 0.5rem;
        }

        /* Call-To-Action (Suscribirse) */
        .cta {
            background-color: #e62117;
            color: white;
            text-align: center;
            padding: 2rem;
            border-radius: 8px;
            margin: 2rem 0;
        }

        .cta h2 {
            margin-bottom: 1rem;
        }

        .subscribe-btn {
            background-color: white;
            color: #e62117;
            border: none;
            padding: 0.8rem 1.5rem;
            font-size: 1rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .subscribe-btn:hover {
            background-color: #f0f0f0;
        }

        footer {
            text-align: center;
            padding: 1.5rem;
            background-color: #333;
            color: white;
            margin-top: 2rem;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .video-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header con logo -->
    <header>
        <div class="logo">Preparatoria Oficial No. 56</div>
    </header>

    <div class="container">
        <!-- Video destacado -->
        <section class="featured-video">
            <h2>Video Destacado</h2>
            <div class="video-container">
                <!-- Reemplaza el ID del video de YouTube -->
                <iframe 
                    src="https://www.youtube.com/embed/?autoplay=1&mute=1" 
                    frameborder="0" 
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
                    allowfullscreen>
                </iframe>
            </div>
            <p>Mira nuestro contenido más reciente.</p>
        </section>

        <!-- Call-To-Action (Suscribirse) -->
        <section class="cta">
            <h2>¡Suscríbete a nuestro canal!</h2>
            <button class="subscribe-btn" id="subscribeBtn">Suscribirse</button>
        </section>

        <!-- Videos adicionales (placeholders) -->
        <section>
            <h2>Más videos</h2>
            <div class="video-grid">
                <!-- Video 1 -->
                <div class="video-card">
                    <div class="thumbnail">Miniatura del Video 1</div>
                    <div class="video-info">
                        <h3>Título del Video 1</h3>
                        <p>Descripción breve...</p>
                    </div>
                </div>

                <!-- Video 2 -->
                <div class="video-card">
                    <div class="thumbnail">Miniatura del Video 2</div>
                    <div class="video-info">
                        <h3>Título del Video 2</h3>
                        <p>Descripción breve...</p>
                    </div>
                </div>

                <!-- Video 3 -->
                <div class="video-card">
                    <div class="thumbnail">Miniatura del Video 3</div>
                    <div class="video-info">
                        <h3>Título del Video 3</h3>
                        <p>Descripción breve...</p>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2024 Preparatoria Oficial No. 56. Todos los derechos reservados.</p>
    </footer>

    <!-- JavaScript para el botón de suscripción -->
    <script>
        document.getElementById('subscribeBtn').addEventListener('click', function() {
            // Reemplaza con el enlace real de tu canal
            window.open('https://www.youtube.com/@tucanal?sub_confirmation=1', '_blank');
        });
    </script>
</body>
</html>
