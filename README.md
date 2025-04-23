<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hogar Total - Todo para tu hogar</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        :root {
            --primary-color: #2c3e50;
            --secondary-color: #3498db;
            --accent-color: #e74c3c;
            --light-color: #ecf0f1;
            --dark-color: #2c3e50;
            --success-color: #27ae60;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f9f9f9;
            color: #333;
            line-height: 1.6;
        }
        
        /* Header */
        header {
            background-color: var(--primary-color);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }
        
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            display: flex;
            align-items: center;
        }
        
        .logo i {
            color: var(--secondary-color);
            margin-right: 10px;
        }
        
        /* Navigation */
        nav {
            background-color: var(--dark-color);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 20px;
        }
        
        .main-menu {
            display: flex;
            list-style: none;
        }
        
        .main-menu li {
            position: relative;
        }
        
        .main-menu li a {
            color: white;
            text-decoration: none;
            padding: 15px 20px;
            display: block;
            transition: background-color 0.3s;
        }
        
        .main-menu li a:hover {
            background-color: var(--secondary-color);
        }
        
        .dropdown-menu {
            position: absolute;
            background-color: white;
            width: 200px;
            box-shadow: 0 5px 10px rgba(0, 0, 0, 0.1);
            opacity: 0;
            visibility: hidden;
            transition: all 0.3s;
        }
        
        .main-menu li:hover .dropdown-menu {
            opacity: 1;
            visibility: visible;
        }
        
        .dropdown-menu li a {
            color: var(--dark-color);
            border-bottom: 1px solid #eee;
        }
        
        .dropdown-menu li a:hover {
            background-color: var(--light-color);
            color: var(--secondary-color);
        }
        
        .cart-search {
            display: flex;
            align-items: center;
        }
        
        .cart-search a {
            color: white;
            margin-left: 15px;
            font-size: 1.2rem;
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://images.unsplash.com/photo-1556911220-bff31c812dba?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            height: 500px;
            display: flex;
            align-items: center;
            text-align: center;
            color: white;
        }
        
        .hero-content {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .hero h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        
        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        
        .btn {
            display: inline-block;
            background-color: var(--secondary-color);
            color: white;
            padding: 12px 30px;
            border-radius: 5px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #2980b9;
        }
        
        /* Categories */
        .categories {
            padding: 60px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 40px;
            color: var(--dark-color);
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--secondary-color);
            margin: 15px auto 0;
        }
        
        .category-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .category-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s, box-shadow 0.3s;
        }
        
        .category-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        .category-img {
            height: 200px;
            overflow: hidden;
        }
        
        .category-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }
        
        .category-card:hover .category-img img {
            transform: scale(1.1);
        }
        
        .category-info {
            padding: 20px;
            text-align: center;
        }
        
        .category-info h3 {
            margin-bottom: 10px;
            color: var(--dark-color);
        }
        
        /* Featured Products */
        .featured-products {
            padding: 60px 0;
            background-color: var(--light-color);
        }
        
        .product-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .product-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            transition: transform 0.3s;
        }
        
        .product-card:hover {
            transform: translateY(-5px);
        }
        
        .product-img {
            height: 200px;
            position: relative;
            overflow: hidden;
        }
        
        .product-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .product-badge {
            position: absolute;
            top: 10px;
            right: 10px;
            background-color: var(--accent-color);
            color: white;
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 0.8rem;
            font-weight: bold;
        }
        
        .product-info {
            padding: 20px;
        }
        
        .product-info h3 {
            margin-bottom: 10px;
            color: var(--dark-color);
        }
        
        .product-price {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-top: 15px;
        }
        
        .price {
            font-weight: bold;
            color: var(--accent-color);
            font-size: 1.2rem;
        }
        
        .old-price {
            text-decoration: line-through;
            color: #999;
            font-size: 0.9rem;
            margin-right: 5px;
        }
        
        .add-to-cart {
            background-color: var(--secondary-color);
            color: white;
            border: none;
            padding: 8px 15px;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .add-to-cart:hover {
            background-color: #2980b9;
        }
        
        /* About Section */
        .about {
            padding: 60px 0;
            background-color: white;
        }
        
        .about-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
            padding: 0 20px;
        }
        
        .about-img img {
            width: 100%;
            border-radius: 10px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
        }
        
        .about-content h2 {
            color: var(--dark-color);
            margin-bottom: 20px;
        }
        
        .about-content p {
            margin-bottom: 15px;
        }
        
        /* Services */
        .services {
            padding: 60px 0;
            background-color: var(--light-color);
        }
        
        .service-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .service-card {
            background-color: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
            text-align: center;
            transition: transform 0.3s;
        }
        
        .service-card:hover {
            transform: translateY(-10px);
        }
        
        .service-icon {
            font-size: 3rem;
            color: var(--secondary-color);
            margin-bottom: 20px;
        }
        
        .service-card h3 {
            margin-bottom: 15px;
            color: var(--dark-color);
        }
        
        /* Testimonials */
        .testimonials {
            padding: 60px 0;
            background-color: white;
        }
        
        .testimonial-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        .testimonial-card {
            background-color: var(--light-color);
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
        }
        
        .testimonial-text {
            font-style: italic;
            margin-bottom: 20px;
        }
        
        .testimonial-author {
            display: flex;
            align-items: center;
        }
        
        .author-img {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            overflow: hidden;
            margin-right: 15px;
        }
        
        .author-img img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }
        
        .author-info h4 {
            color: var(--dark-color);
            margin-bottom: 5px;
        }
        
        .author-info p {
            color: #777;
            font-size: 0.9rem;
        }
        
        /* Newsletter */
        .newsletter {
            padding: 60px 0;
            background-color: var(--secondary-color);
            color: white;
            text-align: center;
        }
        
        .newsletter h2 {
            margin-bottom: 20px;
        }
        
        .newsletter p {
            max-width: 600px;
            margin: 0 auto 30px;
        }
        
        .newsletter-form {
            display: flex;
            max-width: 500px;
            margin: 0 auto;
        }
        
        .newsletter-form input {
            flex: 1;
            padding: 15px;
            border: none;
            border-radius: 5px 0 0 5px;
            font-size: 1rem;
        }
        
        .newsletter-form button {
            background-color: var(--dark-color);
            color: white;
            border: none;
            padding: 0 25px;
            border-radius: 0 5px 5px 0;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .newsletter-form button:hover {
            background-color: var(--primary-color);
        }
        
        /* Footer */
        footer {
            background-color: var(--dark-color);
            color: white;
            padding: 60px 0 0;
        }
        
        .footer-container {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 40px;
            padding: 0 20px;
        }
        
        .footer-col h3 {
            margin-bottom: 20px;
            font-size: 1.2rem;
            position: relative;
            padding-bottom: 10px;
        }
        
        .footer-col h3::after {
            content: '';
            position: absolute;
            left: 0;
            bottom: 0;
            width: 50px;
            height: 2px;
            background-color: var(--secondary-color);
        }
        
        .footer-col ul {
            list-style: none;
        }
        
        .footer-col ul li {
            margin-bottom: 10px;
        }
        
        .footer-col ul li a {
            color: #ddd;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .footer-col ul li a:hover {
            color: var(--secondary-color);
        }
        
        .social-links {
            display: flex;
            margin-top: 20px;
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            margin-right: 10px;
            color: white;
            transition: background-color 0.3s;
        }
        
        .social-links a:hover {
            background-color: var(--secondary-color);
        }
        
        .footer-bottom {
            background-color: var(--primary-color);
            padding: 20px 0;
            text-align: center;
            margin-top: 40px;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .about-container {
                grid-template-columns: 1fr;
            }
            
            .about-img {
                order: -1;
            }
        }
        
        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
            }
            
            .main-menu {
                position: fixed;
                top: 0;
                left: -100%;
                width: 80%;
                height: 100vh;
                background-color: var(--dark-color);
                flex-direction: column;
                align-items: center;
                padding-top: 80px;
                transition: left 0.3s;
                z-index: 999;
            }
            
            .main-menu.active {
                left: 0;
            }
            
            .main-menu li {
                width: 100%;
                text-align: center;
            }
            
            .main-menu li a {
                padding: 15px;
            }
            
            .dropdown-menu {
                position: static;
                width: 100%;
                opacity: 1;
                visibility: visible;
                display: none;
                box-shadow: none;
            }
            
            .main-menu li:hover .dropdown-menu {
                display: block;
            }
            
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .newsletter-form {
                flex-direction: column;
            }
            
            .newsletter-form input {
                border-radius: 5px;
                margin-bottom: 10px;
            }
            
            .newsletter-form button {
                border-radius: 5px;
                padding: 15px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="header-container">
            <div class="logo">
                <i class="fas fa-home"></i>
                <span>Higiene y Limpieza&nbsp;</span>
            </div>
            <div class="contact-info">
                <i class="fas fa-phone"></i> (712) 186-1266
            </div>
        </div>
    </header>
    
    <!-- Navigation -->
    <nav>
        <div class="nav-container">
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
            <ul class="main-menu">
                <li><a href="index.html">Inicio</a></li>
                <li>
                    <a href="#">Productos <i class="fas fa-chevron-down"></i></a>
                    <ul class="dropdown-menu">
                        <li><a href="practimuebles.html.html">Practimuebles&nbsp;&nbsp;</a></li>
                        <li><a href="hogar.html.html">Hogar&nbsp;</a></li>
                        <li><a href="cocina.html.html">Cocina&nbsp;</a></li>
                        <li><a href="#">Gurmy&nbsp;</a></li>
                        <li><a href="recamara.html.html">Recámara&nbsp;</a></li>
                        <li><a href="#">Bienestar&nbsp;</a></li>
						<li><a href="baño.html.html">Baño&nbsp;</a></li>
						<li><a href="higiene_y_limpieza.html.html">Higiene y Limpieza&nbsp;</a></li>
						<li><a href="contigo.html.html">Contigo&nbsp;</a></li>
                    </ul>
                </li>
                <li><a href="#">Servicios</a></li>
                <li><a href="#">Ofertas</a></li>
                <li><a href="#">Blog</a></li>
                <li><a href="#">Contacto</a></li>
            </ul>
            <div class="cart-search">
                <a href="#"><i class="fas fa-search"></i></a>
                <a href="#"><i class="fas fa-shopping-cart"></i></a>
            </div>
        </div>
    </nav>
    
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Productos de better para hacer de tu casa un lugar especial.</h1>
            <p>Encuentra los mejores productos para cada espacio de tu casa con la mejor calidad y precios, mejoramos cada día en nuestro servicio.&nbsp;&nbsp;</p>
            <a href="#" class="btn">Ver productos</a>
        </div>
    </section>
    
    <!-- Categories -->
    <section class="categories">
        <h2 class="section-title">Nuestras Categorías</h2>
        <div class="category-grid">
            <div class="category-card">
                <div class="category-img">
                    <img src="Imagenes/Slim Clean Pro.jpg" alt="Slim Clean Pro">
                </div>
                <div class="category-info">
                    <h3>Slim Clean Pro</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
            
            <div class="category-card">
                <div class="category-img">
                    <img src="Imagenes/Cepillo Flex.jpg" alt="Cepillo Flex">
                </div>
                <div class="category-info">
                    <h3>Cepillo Flex</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
            
            <div class="category-card">
                <div class="category-img">
                    <img src="Imagenes/Limpia WC.jpg" alt="Limpia WC">
                </div>
                <div class="category-info">
                    <h3>Limpia WC&nbsp;</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
            
            <div class="category-card">
                <div class="category-img">
                    <img src="Imagenes/Set Practi Agujetas.jpg" alt="Set Practi Agujetas">
                </div>
                <div class="category-info">
                    <h3>Set Practi Agujetas</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
            
            <div class="category-card">
                <div class="category-img">
                    <img src="Imagenes/Guante Termo Resist.jpg" alt="Guante Termo Resist">
                </div>
                <div class="category-info">
                    <h3>Guante Termo Resist</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
             <div class="category-card">
                <div class="category-img">
                  <img src="Imagenes/Cepi Estufa 4en1.jpg" alt="Cepi Estufa 4 en 1">
                </div>
                <div class="category-info">
                    <h3>Cepi Estufa 4 en 1</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
			 <div class="category-card">
                <div class="category-img">
                  <img src="Imagenes/Dosi Perfect.jpg" alt="Dosi Perfect">
                </div>
                <div class="category-info">
                    <h3>Dosi Perfect</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
			 <div class="category-card">
                <div class="category-img">
                  <img src="Imagenes/Lava Tenis Pro.jpg" alt="Lava Tenis Pro">
                </div>
                <div class="category-info">
                    <h3>Lava Tenis Pro</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
			 <div class="category-card">
                <div class="category-img">
                  <img src="Imagenes/Better Steam Dúo.jpg" alt="Better Steam Dúo">
                </div>
                <div class="category-info">
                    <h3>Better Steam Dúo&nbsp;</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
			<div class="category-card">
                <div class="category-img">
                  <img src="Imagenes/Talla Residuos.jpg" alt="Talla Residuos">
                </div>
                <div class="category-info">
                    <h3>Talla Residuos</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
			<div class="category-card">
                <div class="category-img">
                  <img src="Imagenes/Estación Practiklin .jpg" alt="Estación Practiklin ">
                </div>
                <div class="category-info">
                    <h3>Estación Practiklin&nbsp;</h3>
                    <a href="#" class="btn">Ver productos</a>
                </div>
            </div>
           </div>
    </section>
    
    <!-- Featured Products -->
    <section class="featured-products">
        <h2 class="section-title">Productos Destacados</h2>
        <div class="product-grid">
            <div class="product-card">
                <div class="product-img">
                    <img src="https://images.unsplash.com/photo-1556228453-efd6c1ff04f6?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Juego de sábanas">
                    <span class="product-badge">Nuevo</span>
                </div>
                <div class="product-info">
                    <h3>Juego de sábanas algodón 300 hilos</h3>
                    <p>Suave y transpirable, disponible en varios colores.</p>
                    <div class="product-price">
                        <div>
                            <span class="old-price">$1,299</span>
                            <span class="price">$999</span>
                        </div>
                        <button class="add-to-cart">Añadir</button>
                    </div>
                </div>
            </div>
            
            <div class="product-card">
                <div class="product-img">
                    <img src="https://images.unsplash.com/photo-1592078615290-033ee584e267?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Juego de ollas">
                    <span class="product-badge">Oferta</span>
                </div>
                <div class="product-info">
                    <h3>Juego de ollas antiadherentes 10 piezas</h3>
                    <p>Duradero y fácil de limpiar, incluye utensilios.</p>
                    <div class="product-price">
                        <div>
                            <span class="old-price">$2,499</span>
                            <span class="price">$1,799</span>
                        </div>
                        <button class="add-to-cart">Añadir</button>
                    </div>
                </div>
            </div>
            
            <div class="product-card">
                <div class="product-img">
                    <img src="https://images.unsplash.com/photo-1600077106724-946750eeaf3c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Toallero">
                </div>
                <div class="product-info">
                    <h3>Toallero de acero inoxidable</h3>
                    <p>Resistente a la humedad, fácil instalación.</p>
                    <div class="product-price">
                        <div>
                            <span class="price">$499</span>
                        </div>
                        <button class="add-to-cart">Añadir</button>
                    </div>
                </div>
            </div>
            
            <div class="product-card">
                <div class="product-img">
                    <img src="https://images.unsplash.com/photo-1567538096630-e0c55bd6374c?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Juego de platos">
                    <span class="product-badge">Más vendido</span>
                </div>
                <div class="product-info">
                    <h3>Juego de platos de porcelana 16 piezas</h3>
                    <p>Elegante y resistente, diseño moderno.</p>
                    <div class="product-price">
                        <div>
                            <span class="price">$1,299</span>
                        </div>
                        <button class="add-to-cart">Añadir</button>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- About Section -->
    <section class="about">
        <div class="about-container">
            <div class="about-content">
                <h2>Sobre Nosotros</h2>
                <p>En Hogar Total nos dedicamos a proporcionar los mejores productos para cada espacio de tu hogar. Con más de 15 años de experiencia en el mercado, nos hemos convertido en líderes en el sector de artículos para el hogar.</p>
                <p>Nuestra misión es ofrecer productos de alta calidad a precios accesibles, con un servicio al cliente excepcional que garantice la satisfacción total de nuestros clientes.</p>
                <p>Todos nuestros productos pasan por rigurosos controles de calidad para asegurar que cumplan con los más altos estándares del mercado.</p>
                <a href="#" class="btn">Conoce más</a>
            </div>
            <div class="about-img">
                <img src="https://images.unsplash.com/photo-1556740738-b6a63e27c4df?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Nuestra tienda">
            </div>
        </div>
    </section>
    
    <!-- Services -->
    <section class="services">
        <h2 class="section-title">Nuestros Servicios</h2>
        <div class="service-grid">
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-truck"></i>
                </div>
                <h3>Envío Gratis</h3>
                <p>En compras mayores a $1,500 en toda la ciudad. Consulta cobertura en otras zonas.</p>
            </div>
            
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-undo"></i>
                </div>
                <h3>Devoluciones Fáciles</h3>
                <p>30 días para devolver tus productos si no quedas satisfecho. Términos y condiciones aplican.</p>
            </div>
            
            <div class="service-card">
                <div class="service-icon">
                    <i class="fas fa-headset"></i>
                </div>
                <h3>Soporte 24/7</h3>
                <p>Nuestro equipo de atención al cliente está disponible para resolver tus dudas en cualquier momento.</p>
            </div>
        </div>
    </section>
    
    <!-- Testimonials -->
    <section class="testimonials">
        <h2 class="section-title">Lo que dicen nuestros clientes</h2>
        <div class="testimonial-grid">
            <div class="testimonial-card">
                <div class="testimonial-text">
                    <p>"Excelente calidad en los productos para la recámara. Las sábanas son suaves y duraderas, superaron mis expectativas. Definitivamente volveré a comprar."</p>
                </div>
                <div class="testimonial-author">
                    <div class="author-img">
                        <img src="https://randomuser.me/api/portraits/women/43.jpg" alt="María González">
                    </div>
                    <div class="author-info">
                        <h4>María González</h4>
                        <p>Cliente frecuente</p>
                    </div>
                </div>
            </div>
            
            <div class="testimonial-card">
                <div class="testimonial-text">
                    <p>"El juego de ollas que compré es increíble. Cocinar se ha vuelto mucho más fácil y se ven como nuevas después de meses de uso. Muy recomendable."</p>
                </div>
                <div class="testimonial-author">
                    <div class="author-img">
                        <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="Carlos Mendoza">
                    </div>
                    <div class="author-info">
                        <h4>Carlos Mendoza</h4>
                        <p>Chef profesional</p>
                    </div>
                </div>
            </div>
            
            <div class="testimonial-card">
                <div class="testimonial-text">
                    <p>"Me encanta la variedad de productos que tienen para el baño. Encontré todo lo que necesitaba para remodelar en un solo lugar y a buen precio."</p>
                </div>
                <div class="testimonial-author">
                    <div class="author-img">
                        <img src="https://randomuser.me/api/portraits/women/65.jpg" alt="Laura Jiménez">
                    </div>
                    <div class="author-info">
                        <h4>Laura Jiménez</h4>
                        <p>Diseñadora de interiores</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <!-- Newsletter -->
    <section class="newsletter">
        <h2>Suscríbete a nuestro boletín</h2>
        <p>Recibe ofertas exclusivas, novedades y consejos para tu hogar directamente en tu correo.</p>
        <form class="newsletter-form">
            <input type="email" placeholder="Tu correo electrónico" required>
            <button type="submit">Suscribirse</button>
        </form>
    </section>
    
    <!-- Footer -->
    <footer>
        <div class="footer-container">
            <div class="footer-col">
                <h3>Hogar Total</h3>
                <p>Todo lo que necesitas para cada espacio de tu hogar en un solo lugar. Calidad, variedad y precios incomparables.</p>
                <div class="social-links">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-pinterest"></i></a>
                </div>
            </div>
            
            <div class="footer-col">
                <h3>Categorías</h3>
                <ul>
                    <li><a href="#">Recámara</a></li>
                    <li><a href="#">Cocina</a></li>
                    <li><a href="#">Baño</a></li>
                    <li><a href="#">Comedor</a></li>
                    <li><a href="#">Cuarto de servicio</a></li>
                    <li><a href="#">Sala</a></li>
                </ul>
            </div>
            
            <div class="footer-col">
                <h3>Enlaces útiles</h3>
                <ul>
                    <li><a href="#">Inicio</a></li>
                    <li><a href="#">Sobre nosotros</a></li>
                    <li><a href="#">Servicios</a></li>
                    <li><a href="#">Blog</a></li>
                    <li><a href="#">Contacto</a></li>
                    <li><a href="#">Preguntas frecuentes</a></li>
                </ul>
            </div>
            
            <div class="footer-col">
                <h3>Contacto</h3>
                <ul>
                    <li><i class="fas fa-map-marker-alt"></i> Av. Principal 123, CDMX</li>
                    <li><i class="fas fa-phone"></i> (55) 1234-5678</li>
                    <li><i class="fas fa-envelope"></i> info@hogartotal.com</li>
                    <li><i class="fas fa-clock"></i> Lunes a Sábado: 9am - 8pm</li>
                </ul>
            </div>
        </div>
        
        <div class="footer-bottom">
            <p>&copy; 2023 Hogar Total. Todos los derechos reservados. | <a href="#">Política de privacidad</a> | <a href="#">Términos y condiciones</a></p>
        </div>
    </footer>
    
    <script>
        // Mobile Menu Toggle
        const mobileMenuBtn = document.querySelector('.mobile-menu-btn');
        const mainMenu = document.querySelector('.main-menu');
        
        mobileMenuBtn.addEventListener('click', () => {
            mainMenu.classList.toggle('active');
        });
        
        // Smooth scrolling for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                if(targetId === '#') return;
                
                const targetElement = document.querySelector(targetId);
                if(targetElement) {
                    targetElement.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });
        
        // Add to cart functionality
        const addToCart
