<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GameVerse - Seu Portal de Jogos</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #ff6b35;
            --secondary-color: #2c3e50;
            --accent-color: #00c8ff;
            --background-dark: #1a1a2e;
            --background-light: #2d3047;
            --text-light: #ffffff;
            --text-gray: #b8b8b8;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, var(--background-dark) 0%, var(--background-light) 100%);
            color: var(--text-light);
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(26, 26, 46, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
            border-bottom: 2px solid var(--primary-color);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            color: var(--primary-color);
            text-decoration: none;
        }

        .logo span {
            color: var(--accent-color);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: var(--text-light);
            text-decoration: none;
            font-weight: 500;
            transition: color 0.3s ease;
            padding: 0.5rem 1rem;
            border-radius: 5px;
        }

        nav a:hover {
            color: var(--primary-color);
            background: rgba(255, 107, 53, 0.1);
        }

        /* Hero Section */
        .hero {
            padding: 120px 0 80px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 50% 50%, rgba(255, 107, 53, 0.1) 0%, transparent 50%);
            z-index: -1;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, var(--primary-color), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .hero p {
            font-size: 1.2rem;
            color: var(--text-gray);
            max-width: 600px;
            margin: 0 auto 2rem;
        }

        .cta-button {
            display: inline-block;
            padding: 15px 30px;
            background: linear-gradient(45deg, var(--primary-color), var(--secondary-color));
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: bold;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: none;
            cursor: pointer;
        }

        .cta-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 30px rgba(255, 107, 53, 0.3);
        }

        /* Games Section */
        .games-section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: var(--text-light);
        }

        .games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .game-card {
            background: rgba(45, 48, 71, 0.8);
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .game-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .game-image {
            width: 100%;
            height: 200px;
            overflow: hidden;
        }

        .game-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .game-card:hover .game-image img {
            transform: scale(1.1);
        }

        .game-info {
            padding: 1.5rem;
        }

        .game-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: var(--text-light);
        }

        .game-description {
            color: var(--text-gray);
            margin-bottom: 1rem;
            font-size: 0.9rem;
        }

        .game-meta {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .game-price {
            font-weight: bold;
            color: var(--primary-color);
        }

        .game-rating {
            background: var(--secondary-color);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
        }

        /* Categories Section */
        .categories-section {
            padding: 80px 0;
            background: rgba(26, 26, 46, 0.5);
        }

        .categories-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 1.5rem;
        }

        .category-card {
            background: linear-gradient(135deg, var(--background-light), var(--background-dark));
            padding: 2rem;
            border-radius: 15px;
            text-align: center;
            transition: transform 0.3s ease;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .category-card:hover {
            transform: translateY(-5px);
        }

        .category-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--primary-color);
        }

        .category-title {
            font-size: 1.2rem;
            margin-bottom: 1rem;
            color: var(--text-light);
        }

        /* Footer */
        footer {
            background: var(--background-dark);
            padding: 3rem 0 1rem;
            margin-top: 4rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-section h3 {
            color: var(--primary-color);
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .footer-links {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 0.5rem;
        }

        .footer-links a {
            color: var(--text-gray);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--primary-color);
        }

        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-link {
            width: 40px;
            height: 40px;
            background: var(--background-light);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.3s ease, transform 0.3s ease;
        }

        .social-link:hover {
            background: var(--primary-color);
            transform: translateY(-2px);
        }

        .copyright {
            text-align: center;
            color: var(--text-gray);
            padding-top: 2rem;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            nav ul {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .games-grid {
                grid-template-columns: 1fr;
            }

            .section-title {
                font-size: 2rem;
            }
        }

        @media (max-width: 480px) {
            nav ul {
                flex-direction: column;
                align-items: center;
                gap: 0.5rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .cta-button {
                padding: 12px 25px;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container header-content">
            <a href="#" class="logo">Game<span>Verse</span></a>
            <nav>
                <ul>
                    <li><a href="#">Início</a></li>
                    <li><a href="#">Jogos</a></li>
                    <li><a href="#">Categorias</a></li>
                    <li><a href="#">Sobre</a></li>
                    <li><a href="#">Contato</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <h1>Descubra o Mundo dos Jogos</h1>
            <p>Explore uma vasta coleção de jogos incríveis, desde clássicos atemporais até as mais recentes inovações em entretenimento digital.</p>
            <a href="#" class="cta-button">Explorar Jogos</a>
        </div>
    </section>

    <!-- Games Section -->
    <section class="games-section">
        <div class="container">
            <h2 class="section-title">Jogos em Destaque</h2>
            <div class="games-grid">
                <div class="game-card">
                    <div class="game-image">
                        <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/e43f2d55-cacb-4cb1-85e4-6012ca8c0f0f.png" alt="Cenário futurista de um jogo de tiro em primeira pessoa com armas high-tech e elementos cyberpunk" onerror="this.src='data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDAwIiBoZWlnaHQ9IjMwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjMzMzIi8+PHRleHQgeD0iNTAlIiB5PSI1MCUiIGZvbnQtc2l6ZT0iMTgiIGZpbGw9IiM4ODgiIHRleHQtYW5jaG9yPSJtaWRkbGUiIGR5PSIuM2VtIj5JbWFnZSBub3QgYXZhaWxhYmxlPC90ZXh0Pjwvc3ZnPg=='"/>
                    </div>
                    <div class="game-info">
                        <h3 class="game-title">Cyber Odyssey</h3>
                        <p class="game-description">Aventura futurista em um mundo cyberpunk repleto de desafios e mistérios.</p>
                        <div class="game-meta">
                            <span class="game-price">R$ 149,90</span>
                            <span class="game-rating">⭐ 4.8/5</span>
                        </div>
                    </div>
                </div>

                <div class="game-card">
                    <div class="game-image">
                        <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/bec0c762-356d-4c3b-990e-5d34108f9ca3.png" alt="Paisagem mágica de um RPG medieval com castelos, dragões e florestas encantadas" onerror="this.src='data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDAwIiBoZWlnaHQ9IjMwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjMzMzIi8+PHRleHQgeD0iNTAlIiB5PSI1MCUiIGZvbnQtc2l6ZT0iMTgiIGZpbGw9IiM4ODgiIHRleHQtYW5jaG9yPSJtaWRkbGUiIGR5PSIuM2VtIj5JbWFnZSBub3QgYXZhaWxhYmxlPC90ZXh0Pjwvc3ZnPg=='"/>
                    </div>
                    <div class="game-info">
                        <h3 class="game-title">Dragon's Legacy</h3>
                        <p class="game-description">RPG épico em um mundo medieval cheio de magia, dragões e heróis lendários.</p>
                        <div class="game-meta">
                            <span class="game-price">R$ 199,90</span>
                            <span class="game-rating">⭐ 4.9/5</span>
                        </div>
                    </div>
                </div>

                <div class="game-card">
                    <div class="game-image">
                        <img src="https://storage.googleapis.com/workspace-0f70711f-8b4e-4d94-86f1-2a93ccde5887/image/77a48662-474e-49a9-b21e-f11b110ea9c5.png" alt="Cena de corrida em alta velocidade com carros esportivos em pista urbana noturna" onerror="this.src='data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iNDAwIiBoZWlnaHQ9IjMwMCIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj48cmVjdCB3aWR0aD0iMTAwJSIgaGVpZ2h0PSIxMDAlIiBmaWxsPSIjMzMzIi8+PHRleHQgeD0iNTAlIiB5PSI1MCUiIGZvbnQtc2l6ZT0iMTgiIGZpbGw9IiM4ODgiIHRleHQtYW5jaG9yPSJtaWRkbGUiIGR5PSIuM2VtIj5JbWFnZSBub3QgYXZhaWxhYmxlPC90ZXh0Pjwvc3ZnPg=='"/>
                    </div>
                    <div class="game-info">
                        <h3 class="game-title">Velocity Extreme</h3>
                        <p class="game-description">Corrida em alta velocidade com gráficos realistas e física avançada.</p>
                        <div class="game-meta">
                            <span class="game-price">R$ 129,90</span>
                            <span class="game-rating">⭐ 4.7/5</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Categories Section -->
    <section class="categories-section">
        <div class="container">
            <h2 class="section-title">Categorias</h2>
            <div class="categories-grid">
                <div class="category-card">
                    <div class="category-icon">🎮</div>
                    <h3 class="category-title">Ação</h3>
                    <p>Jogos intensos e emocionantes com muita adrenalina.</p>
                </div>
                <div class="category-card">
                    <div class="category-icon">🛡️</div>
                    <h3 class="category-title">RPG</h3>
                    <p>Mundos imersivos com histórias épicas e personagens complexos.</p>
                </div>
                <div class="category-card">
                    <div class="category-icon">🏎️</div>
                    <h3 class="category-title">Corrida</h3>
                    <p>Velocidade e emoção em pistas desafiadoras.</p>
                </div>
                <div class="category-card">
                    <div class="category-icon">🎯</div>
                    <h3 class="category-title">Estratégia</h3>
                    <p>Desafios mentais que testam sua capacidade de planejamento.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>GameVerse</h3>
                    <p>Seu destino definitivo para os melhores jogos do mercado.</p>
                    <div class="social-links">
                        <a href="#" class="social-link">📱</a>
                        <a href="#" class="social-link">📷</a>
                        <a href="#" class="social-link">🐦</a>
                        <a href="#" class="social-link">📺</a>
                    </div>
                </div>
                <div class="footer-section">
                    <h3>Links Rápidos</h3>
                    <ul class="footer-links">
                        <li><a href="#">Início</a></li>
                        <li><a href="#">Jogos</a></li>
                        <li><a href="#">Categorias</a></li>
                        <li><a href="#">Promoções</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Suporte</h3>
                    <ul class="footer-links">
                        <li><a href="#">FAQ</a></li>
                        <li><a href="#">Contato</a></li>
                        <li><a href="#">Política de Privacidade</a></li>
                        <li><a href="#">Termos de Uso</a></li>
                    </ul>
                </div>
            </div>
            <div class="copyright">
                <p>© 2024 GameVerse. Todos os direitos reservados.</p>
            </div>
        </div>
    </footer>

    <script>
        // Efeito de digitação no título
        document.addEventListener('DOMContentLoaded', function() {
            const heroTitle = document.querySelector('.hero h1');
            const originalText = heroTitle.textContent;
            heroTitle.textContent = '';
            
            let i = 0;
            function typeWriter() {
                if (i < originalText.length) {
                    heroTitle.textContent += originalText.charAt(i);
                    i++;
                    setTimeout(typeWriter, 50);
                }
            }
            setTimeout(typeWriter, 1000);
        });
    </script>
</body>
</html>
