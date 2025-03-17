<!DOCTYPE html>
<html lang="pt-br">
<!-- Declaração inicial do documento HTML com a linguagem definida como português brasileiro (pt-br). -->

<head>
    <!-- Seção de metadados: Define configurações e informações sobre o documento. -->
    <meta charset="UTF-8">
    <!-- Define a codificação de caracteres como UTF-8 para suportar caracteres especiais. -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- Configura a responsividade para dispositivos móveis, ajustando a largura e escala inicial. -->
    <title>Elementos HTML</title>
    <!-- Define o título exibido na aba do navegador. -->
    <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
</head>

<style>
    /* Estilos globais */
    :root {
        --primary-color: #8B4513; /* Sienna */
        --secondary-color: #A0522D; /* Sienna */
        --accent-color: #D2691E; /* Chocolate */
        --text-color: #4B3621; /* Dark Brown */
        --light-bg: #F5F5DC; /* Beige */
        --dark-bg: #3E2723; /* Dark Brown */
        --shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
        --transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
        --glass-bg: rgba(255, 255, 255, 0.15);
        --glass-border: 1px solid rgba(255, 255, 255, 0.2);
        --glass-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.37);
    }

    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'Poppins', 'Roboto', sans-serif;
        line-height: 1.6;
        color: var(--text-color);
        background-color: var(--light-bg);
        padding: 0;
        margin: 0;
        overflow-x: hidden;
        background-image: 
            radial-gradient(circle at 10% 20%, rgba(139, 69, 19, 0.1) 0%, transparent 50%),
            radial-gradient(circle at 90% 80%, rgba(160, 82, 45, 0.1) 0%, transparent 50%),
            radial-gradient(circle at 50% 50%, rgba(210, 105, 30, 0.05) 0%, transparent 70%);
        background-attachment: fixed;
    }

    /* Cabeçalho e navegação */
    header {
        background-color: rgba(26, 26, 46, 0.9);
        backdrop-filter: blur(10px);
        -webkit-backdrop-filter: blur(10px);
        color: white;
        padding: 1rem;
        position: sticky;
        top: 0;
        z-index: 100;
        box-shadow: var(--shadow);
        border-bottom: var(--glass-border);
    }

    nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        max-width: 1200px;
        margin: 0 auto;
    }

    .logo {
        font-size: 1.5rem;
        font-weight: 700;
        color: white;
        text-decoration: none;
        display: flex;
        align-items: center;
        position: relative;
        overflow: hidden;
    }

    .logo i {
        margin-right: 0.5rem;
        color: var(--primary-color);
        animation: pulse 2s infinite;
    }

    @keyframes pulse {
        0% { transform: scale(1); }
        50% { transform: scale(1.1); }
        100% { transform: scale(1); }
    }

    .nav-links {
        display: flex;
        list-style: none;
    }

    .nav-links li {
        margin-left: 1.5rem;
        position: relative;
    }

    .nav-links a {
        color: white;
        text-decoration: none;
        transition: var(--transition);
        padding: 0.5rem 0;
        position: relative;
    }

    .nav-links a::after {
        content: '';
        position: absolute;
        width: 0;
        height: 2px;
        bottom: 0;
        left: 0;
        background-color: var(--primary-color);
        transition: var(--transition);
    }

    .nav-links a:hover {
        color: var(--primary-color);
    }

    .nav-links a:hover::after {
        width: 100%;
    }

    /* Container principal */
    .container {
        max-width: 1200px;
        margin: 2rem auto;
        padding: 0 1rem;
    }

    /* Seções */
    .section {
        background-color: rgba(255, 255, 255, 0.9);
        backdrop-filter: blur(10px);
        -webkit-backdrop-filter: blur(10px);
        border-radius: 16px;
        box-shadow: var(--shadow);
        padding: 2rem;
        margin-bottom: 3rem;
        transition: var(--transition);
        border: 1px solid rgba(255, 255, 255, 0.5);
        position: relative;
        overflow: hidden;
    }

    .section::before {
        content: '';
        position: absolute;
        top: -50%;
        left: -50%;
        width: 200%;
        height: 200%;
        background: radial-gradient(circle, rgba(255,255,255,0.2) 0%, transparent 70%);
        opacity: 0;
        transition: var(--transition);
        z-index: 0;
        pointer-events: none;
    }

    .section:hover::before {
        opacity: 1;
        transform: translate(25%, 25%);
    }

    .section:hover {
        transform: translateY(-10px);
        box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
    }

    .section-title {
        color: var(--primary-color);
        margin-bottom: 1.5rem;
        padding-bottom: 0.5rem;
        border-bottom: 2px solid var(--primary-color);
        display: inline-block;
        position: relative;
        z-index: 1;
    }

    .section-title::after {
        content: '';
        position: absolute;
        width: 30px;
        height: 30px;
        background-color: rgba(67, 97, 238, 0.1);
        border-radius: 50%;
        right: -15px;
        top: -15px;
        z-index: -1;
    }

    /* Cards */
    .cards-container {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
        gap: 1.5rem;
        position: relative;
        z-index: 1;
    }

    .card {
        background-color: white;
        border-radius: 16px;
        overflow: hidden;
        box-shadow: var(--shadow);
        transition: var(--transition);
        position: relative;
        border: 1px solid rgba(0, 0, 0, 0.05);
    }

    .card:hover {
        transform: translateY(-10px) scale(1.02);
        box-shadow: 0 15px 30px rgba(0, 0, 0, 0.15);
    }

    .card-header {
        background: linear-gradient(135deg, var(--primary-color), #7209b7);
        color: white;
        padding: 1.2rem;
        position: relative;
        overflow: hidden;
    }

    .card-header::after {
        content: '';
        position: absolute;
        width: 150px;
        height: 150px;
        background: rgba(255, 255, 255, 0.1);
        border-radius: 50%;
        top: -75px;
        right: -75px;
    }

    .card-body {
        padding: 1.5rem;
        position: relative;
        z-index: 1;
    }

    /* Botões */
    .btn {
        display: inline-block;
        padding: 0.7rem 1.5rem;
        background: linear-gradient(135deg, var(--primary-color), #3a0ca3);
        color: white;
        border: none;
        border-radius: 30px;
        cursor: pointer;
        text-decoration: none;
        transition: var(--transition);
        font-weight: 500;
        box-shadow: 0 4px 15px rgba(67, 97, 238, 0.3);
        position: relative;
        overflow: hidden;
    }

    .btn::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 100%;
        height: 100%;
        background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
        transition: var(--transition);
    }

    .btn:hover {
        transform: translateY(-3px);
        box-shadow: 0 8px 25px rgba(67, 97, 238, 0.4);
    }

    .btn:hover::before {
        left: 100%;
    }

    .btn-secondary {
        background: linear-gradient(135deg, var(--secondary-color), #2a9d8f);
        box-shadow: 0 4px 15px rgba(59, 196, 125, 0.3);
    }

    .btn-secondary:hover {
        box-shadow: 0 8px 25px rgba(59, 196, 125, 0.4);
    }

    .btn-accent {
        background: linear-gradient(135deg, var(--accent-color), #b5179e);
        box-shadow: 0 4px 15px rgba(247, 37, 133, 0.3);
    }

    .btn-accent:hover {
        box-shadow: 0 8px 25px rgba(247, 37, 133, 0.4);
    }

    .btn-group {
        display: flex;
        gap: 1rem;
        flex-wrap: wrap;
    }

    /* Listas */
    ul, ol {
        padding-left: 1.5rem;
        margin-bottom: 1rem;
    }

    li {
        margin-bottom: 0.5rem;
        position: relative;
    }

    ul li::marker {
        color: var(--primary-color);
    }

    ol li::marker {
        color: var(--primary-color);
        font-weight: 600;
    }

    /* Imagens */
    img {
        max-width: 100%;
        height: auto;
        border-radius: 12px;
        transition: var(--transition);
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
    }

    img:hover {
        transform: scale(1.03);
        box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        filter: brightness(1.05);
    }

    /* Barra de progresso */
    .progress-container {
        margin: 2rem 0;
        text-align: center;
    }

    progress {
        width: 100%;
        height: 20px;
        border-radius: 30px;
        overflow: hidden;
        margin-bottom: 0.5rem;
        background-color: #f0f0f0;
        border: none;
    }

    progress::-webkit-progress-bar {
        background-color: #f0f0f0;
        border-radius: 30px;
    }

    progress::-webkit-progress-value {
        background: linear-gradient(to right, var(--primary-color), #7209b7);
        border-radius: 30px;
        transition: width 0.5s ease;
        position: relative;
    }

    #progressText {
        font-weight: bold;
        color: var(--primary-color);
        transition: var(--transition);
    }

    /* Animações */
    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(30px); }
        to { opacity: 1; transform: translateY(0); }
    }

    @keyframes slideInRight {
        from { opacity: 0; transform: translateX(50px); }
        to { opacity: 1; transform: translateX(0); }
    }

    @keyframes slideInLeft {
        from { opacity: 0; transform: translateX(-50px); }
        to { opacity: 1; transform: translateX(0); }
    }

    @keyframes zoomIn {
        from { opacity: 0; transform: scale(0.8); }
        to { opacity: 1; transform: scale(1); }
    }

    .fade-in {
        opacity: 0;
        animation: fadeIn 0.8s ease forwards;
    }

    .slide-in-right {
        opacity: 0;
        animation: slideInRight 0.8s ease forwards;
    }

    .slide-in-left {
        opacity: 0;
        animation: slideInLeft 0.8s ease forwards;
    }

    .zoom-in {
        opacity: 0;
        animation: zoomIn 0.8s ease forwards;
    }

    /* Responsividade */
    @media (max-width: 768px) {
        .cards-container {
            grid-template-columns: 1fr;
        }

        .nav-links {
            display: none;
        }

        .mobile-menu-btn {
            display: block;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .mobile-menu {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--dark-bg);
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            transform: translateX(-100%);
            transition: var(--transition);
        }

        .mobile-menu.active {
            transform: translateX(0);
        }

        .mobile-menu .nav-links {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .mobile-menu .nav-links li {
            margin: 1rem 0;
        }

        .mobile-menu-close {
            position: absolute;
            top: 20px;
            right: 20px;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
    }

    /* Tema escuro */
    .dark-mode {
        background-color: var(--dark-bg);
        color: white;
        background-image: 
            radial-gradient(circle at 10% 20%, rgba(67, 97, 238, 0.15) 0%, transparent 50%),
            radial-gradient(circle at 90% 80%, rgba(59, 196, 125, 0.15) 0%, transparent 50%),
            radial-gradient(circle at 50% 50%, rgba(247, 37, 133, 0.1) 0%, transparent 70%);
    }

    .dark-mode .section {
        background-color: rgba(26, 26, 46, 0.8);
        backdrop-filter: blur(10px);
        -webkit-backdrop-filter: blur(10px);
        border: 1px solid rgba(255, 255, 255, 0.1);
        color: white;
    }

    .dark-mode .card {
        background-color: rgba(40, 40, 70, 0.9);
        border: 1px solid rgba(255, 255, 255, 0.1);
        color: white;
    }

    .dark-mode progress::-webkit-progress-bar {
        background-color: #2c2c44;
    }

    /* Botão de tema */
    .theme-toggle {
        position: fixed;
        bottom: 20px;
        right: 20px;
        background: linear-gradient(135deg, var(--dark-bg), #16213e);
        color: white;
        width: 60px;
        height: 60px;
        border-radius: 50%;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        box-shadow: var(--shadow);
        z-index: 100;
        transition: var(--transition);
        border: var(--glass-border);
    }

    .theme-toggle:hover {
        transform: rotate(45deg) scale(1.1);
    }

    /* Barra de rolagem personalizada */
    ::-webkit-scrollbar {
        width: 12px;
    }

    ::-webkit-scrollbar-track {
        background: #f1f1f1;
        border-radius: 10px;
    }

    ::-webkit-scrollbar-thumb {
        background: linear-gradient(var(--primary-color), #3a0ca3);
        border-radius: 10px;
        border: 3px solid #f1f1f1;
    }

    ::-webkit-scrollbar-thumb:hover {
        background: linear-gradient(#3a0ca3, var(--primary-color));
    }

    .dark-mode ::-webkit-scrollbar-track {
        background: #2c2c44;
    }

    .dark-mode ::-webkit-scrollbar-thumb {
        border: 3px solid #2c2c44;
    }

    /* Efeitos de vidro (glassmorphism) */
    .glass-card {
        background: var(--glass-bg);
        backdrop-filter: blur(10px);
        -webkit-backdrop-filter: blur(10px);
        border-radius: 16px;
        border: var(--glass-border);
        box-shadow: var(--glass-shadow);
    }

    /* Tooltip personalizado */
    .tooltip {
        position: relative;
        display: inline-block;
    }

    .tooltip .tooltip-text {
        visibility: hidden;
        width: 200px;
        background-color: rgba(0, 0, 0, 0.8);
        color: #fff;
        text-align: center;
        border-radius: 6px;
        padding: 10px;
        position: absolute;
        z-index: 1;
        bottom: 125%;
        left: 50%;
        margin-left: -100px;
        opacity: 0;
        transition: opacity 0.3s;
    }

    .tooltip .tooltip-text::after {
        content: "";
        position: absolute;
        top: 100%;
        left: 50%;
        margin-left: -5px;
        border-width: 5px;
        border-style: solid;
        border-color: rgba(0, 0, 0, 0.8) transparent transparent transparent;
    }

    .tooltip:hover .tooltip-text {
        visibility: visible;
        opacity: 1;
    }

    /* Cursor personalizado */
    .custom-cursor {
        position: fixed;
        width: 20px;
        height: 20px;
        border-radius: 50%;
        background-color: rgba(67, 97, 238, 0.5);
        pointer-events: none;
        z-index: 9999;
        transform: translate(-50%, -50%);
        transition: transform 0.1s ease;
        mix-blend-mode: difference;
    }

    /* Partículas de fundo */
    #particles-js {
        position: fixed;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        z-index: -1;
    }

    /* Efeito de destaque para elementos */
    .highlight-effect {
        position: relative;
        overflow: hidden;
    }

    .highlight-effect::before {
        content: '';
        position: absolute;
        top: -50%;
        left: -50%;
        width: 200%;
        height: 200%;
        background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%);
        transform: rotate(30deg);
        opacity: 0;
        transition: var(--transition);
        z-index: 0;
        pointer-events: none;
    }

    .highlight-effect:hover::before {
        opacity: 1;
        animation: shine 1.5s infinite;
    }

    @keyframes shine {
        0% { transform: rotate(30deg) translateY(0); opacity: 0; }
        50% { opacity: 1; }
        100% { transform: rotate(30deg) translateY(100px); opacity: 0; }
    }

    /* Notificações */
    .notification {
        position: fixed;
        top: 20px;
        right: 20px;
        background-color: white;
        color: var(--text-color);
        padding: 15px 20px;
        border-radius: 8px;
        box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        transform: translateX(150%);
        transition: transform 0.5s ease;
        z-index: 1000;
        display: flex;
        align-items: center;
    }

    .notification.show {
        transform: translateX(0);
    }

    .notification i {
        margin-right: 10px;
        font-size: 1.2rem;
    }

    .notification.success {
        border-left: 4px solid var(--secondary-color);
    }

    .notification.error {
        border-left: 4px solid var(--accent-color);
    }

    .notification.info {
        border-left: 4px solid var(--primary-color);
    }

    /* Efeito de onda para botões */
    .ripple {
        position: relative;
        overflow: hidden;
    }

    .ripple::after {
        content: "";
        display: block;
        position: absolute;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        pointer-events: none;
        background-image: radial-gradient(circle, rgba(255, 255, 255, 0.3) 10%, transparent 10.01%);
        background-repeat: no-repeat;
        background-position: 50%;
        transform: scale(10, 10);
        opacity: 0;
        transition: transform 0.5s, opacity 0.8s;
    }

    .ripple:active::after {
        transform: scale(0, 0);
        opacity: 0.3;
        transition: 0s;
    }

    /* Efeito de paralaxe */
    .parallax-container {
        position: relative;
        height: 300px;
        overflow: hidden;
        border-radius: 16px;
        margin: 2rem 0;
    }

    .parallax-bg {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 150%;
        background-image: url('/Imagem/foto generica 2.jpg');
        background-size: cover;
        background-position: center;
        transform: translateY(0);
        transition: transform 0.5s ease-out;
    }

    .parallax-content {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        color: white;
        text-align: center;
        padding: 2rem;
        background-color: rgba(0, 0, 0, 0.4);
        backdrop-filter: blur(2px);
        -webkit-backdrop-filter: blur(2px);
    }

    /* Efeito de digitação */
    .typing-effect {
        overflow: hidden;
        border-right: 2px solid var(--primary-color);
        white-space: nowrap;
        margin: 0 auto;
        animation: typing 3.5s steps(40, end), blink-caret 0.75s step-end infinite;
    }

    @keyframes typing {
        from { width: 0 }
        to { width: 100% }
    }

    @keyframes blink-caret {
        from, to { border-color: transparent }
        50% { border-color: var(--primary-color) }
    }

    /* Efeito de flutuação */
    .floating {
        animation: floating 3s ease-in-out infinite;
    }

    @keyframes floating {
        0% { transform: translateY(0px); }
        50% { transform: translateY(-10px); }
        100% { transform: translateY(0px); }
    }

    /* Efeito de confete */
    #confetti-canvas {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        z-index: 1000;
        pointer-events: none;
    }
</style>

<body>
    <!-- Cursor personalizado -->
    <div class="custom-cursor"></div>

    <!-- Partículas de fundo -->
    <div id="particles-js"></div>

    <!-- Canvas para confete -->
    <canvas id="confetti-canvas"></canvas>

    <!-- Notificação -->
    <div class="notification info" id="welcomeNotification">
        <i class="fas fa-info-circle"></i>
        <div>
            <strong>Bem-vindo!</strong> Explore os elementos HTML neste guia interativo.
        </div>
    </div>

    <!-- Cabeçalho com navegação -->
    <header>
        <nav>
            <a href="#" class="logo"><i class="fas fa-code"></i> Elementos HTML</a>
            <ul class="nav-links">
                <li><a href="#titulos">Títulos</a></li>
                <li><a href="#textos">Textos</a></li>
                <li><a href="#listas">Listas</a></li>
                <li><a href="#imagens">Imagens</a></li>
                <li><a href="#interativo">Interativo</a></li>
                <li><a href="#novidades">Novidades</a></li>
            </ul>
            <button class="mobile-menu-btn" id="mobileMenuBtn">
                <i class="fas fa-bars"></i>
            </button>
        </nav>
    </header>

    <!-- Menu móvel -->
    <div class="mobile-menu" id="mobileMenu">
        <button class="mobile-menu-close" id="mobileMenuClose">
            <i class="fas fa-times"></i>
        </button>
        <ul class="nav-links">
            <li><a href="#titulos">Títulos</a></li>
            <li><a href="#textos">Textos</a></li>
            <li><a href="#listas">Listas</a></li>
            <li><a href="#imagens">Imagens</a></li>
            <li><a href="#interativo">Interativo</a></li>
            <li><a href="#novidades">Novidades</a></li>
        </ul>
    </div>

    <div class="container">
        <!-- Introdução -->
        <section class="section" id="intro">
            <h1 class="section-title typing-effect">Guia de Elementos HTML</h1>
            <p>Este guia demonstra os diferentes elementos HTML e suas funcionalidades. Explore as seções abaixo para aprender mais sobre cada tipo de elemento.</p>
            <div class="btn-group" style="margin-top: 1.5rem;">
                <button class="btn ripple" onclick="showNotification('success', 'Vamos começar! Explore as seções abaixo.')">Começar</button>
                <button class="btn btn-secondary ripple" onclick="window.open('https://developer.mozilla.org/pt-BR/docs/Web/HTML', '_blank')">Documentação</button>
                <button class="btn btn-accent ripple" onclick="toggleConfetti()">Surpresa!</button>
            </div>
        </section>

        <!-- Efeito de paralaxe -->
        <div class="parallax-container" id="parallaxContainer">
            <div class="parallax-bg" id="parallaxBg"></div>
            <div class="parallax-content">
                <h2 class="floating">Descubra o Poder do HTML</h2>
                <p>Explore elementos, atributos e técnicas modernas para criar páginas web incríveis</p>
                <button class="btn ripple" style="margin-top: 1rem;" onclick="showNotification('info', 'Continue rolando para explorar mais conteúdo!')">Saiba mais</button>
            </div>
        </div>

        <!-- Seção de Títulos -->
        <section class="section" id="titulos">
            <h2 class="section-title">Níveis de Títulos</h2>
            <p>HTML oferece seis níveis de títulos, de h1 a h6, para estruturar o conteúdo da página.</p>
            
            <div class="cards-container">
                <div class="card highlight-effect zoom-in" style="animation-delay: 0.1s;">
                    <div class="card-header">
                        <h3>Título Principal (h1)</h3>
                    </div>
                    <div class="card-body">
                        <h1 style="font-size: 1.8rem;">Título Principal</h1>
                        <p>O mais importante, geralmente usado para o título principal da página.</p>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Subtítulos (h2-h3)</h3>
                    </div>
                    <div class="card-body">
                        <h2 style="font-size: 1.5rem;">Título (h2)</h2>
                        <p>Usado para subtítulos ou seções principais.</p>
                        <h3 style="font-size: 1.3rem;">SubTítulo (h3)</h3>
                        <p>Usado para subseções dentro de seções maiores.</p>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Títulos Menores (h4-h6)</h3>
                    </div>
                    <div class="card-body">
                        <h4 style="font-size: 1.1rem;">SubSubTítulo (h4)</h4>
                        <h5 style="font-size: 0.9rem;">SubSubSubTítulo (h5)</h5>
                        <h6 style="font-size: 0.8rem;">SubSubSubSubTítulo (h6)</h6>
                        <p>Usados para níveis mais específicos na hierarquia de conteúdo.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção de Textos -->
        <section class="section fade-in" id="textos">
            <h2 class="section-title">Formatação de Texto</h2>
            <p>HTML oferece várias maneiras de formatar texto para diferentes propósitos.</p>
            
            <div class="cards-container">
                <div class="card">
                    <div class="card-header">
                        <h3>Parágrafos e Quebras</h3>
                    </div>
                    <div class="card-body">
                        <p>Este é um parágrafo simples.</p>
                        <p>Este <br> é um parágrafo <br> com quebras de linha.</p>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Estilos de Texto</h3>
                    </div>
                    <div class="card-body">
                        <p><i>Texto em itálico</i> para ênfase.</p>
                        <p><small>Texto pequeno</small> para notas ou disclaimers.</p>
                        <p><mark>Texto marcado</mark> para destaque.</p>
                        <p><del>Texto excluído</del> e <ins>texto inserido</ins>.</p>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Texto Especial</h3>
                    </div>
                    <div class="card-body">
                        <p>Fórmula química: H<sub>2</sub>O</p>
                        <p>Expressão matemática: E = mc<sup>2</sup></p>
                        <p><code>console.log("Código de exemplo");</code></p>
                        <p><bdo dir="rtl">Texto invertido (direita para esquerda)</bdo></p>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Texto Pré-formatado</h3>
                    </div>
                    <div class="card-body">
                        <pre>
O seguinte
texto    está
pré  formatado
Preserva   os  espaços
        for i = 1 to 10
            print i
        next i</pre>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção de Listas -->
        <section class="section fade-in" id="listas">
            <h2 class="section-title">Tipos de Listas</h2>
            <p>As listas HTML ajudam a organizar informações de forma estruturada.</p>
            
            <div class="cards-container">
                <div class="card">
                    <div class="card-header">
                        <h3>Lista Não Ordenada</h3>
                    </div>
                    <div class="card-body">
                        <ul>
                            <li>Feijão</li>
                            <li>Arroz</li>
                            <li>Carne</li>
                        </ul>
                        
                        <ul style="list-style-type: square;">
                            <li>Item com marcador quadrado</li>
                            <li>Outro item</li>
                        </ul>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Lista Ordenada</h3>
                    </div>
                    <div class="card-body">
                        <ol>
                            <li>Água</li>
                            <li>Café</li>
                            <li>Vodka</li>
                        </ol>
                        
                        <p>Outros estilos:</p>
                        <ol type="a">
                            <li>Letras minúsculas</li>
                            <li>Segundo item</li>
                        </ol>
                        
                        <ol type="I">
                            <li>Numerais romanos</li>
                            <li>Segundo item</li>
                        </ol>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Listas Aninhadas</h3>
                    </div>
                    <div class="card-body">
                        <ol>
                            <li>Primeiro nível</li>
                            <li>Primeiro nível
                                <ol type="a">
                                    <li>Segundo nível</li>
                                    <li>Segundo nível
                                        <ul>
                                            <li>Terceiro nível</li>
                                            <li>Terceiro nível</li>
                                        </ul>
                                    </li>
                                </ol>
                            </li>
                            <li>Primeiro nível</li>
                        </ol>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção de Imagens -->
        <section class="section fade-in" id="imagens">
            <h2 class="section-title">Imagens e Mídia</h2>
            <p>As imagens enriquecem o conteúdo visual da página.</p>
            
            <div class="cards-container">
                <div class="card">
                    <div class="card-header">
                        <h3>Imagem Básica</h3>
                    </div>
                    <div class="card-body">
                        <img src="/Imagem/foto generica 2.jpg" alt="Imagem Genérica" style="width: 100%; border-radius: 8px;">
                        <p style="margin-top: 1rem;">Imagem com bordas arredondadas e largura responsiva.</p>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Imagem com Áreas Clicáveis</h3>
                    </div>
                    <div class="card-body">
                        <img src="/Imagem/foto generica 1.jpeg" alt="Imagem Genérica 2" usemap="#image-map" style="width: 100%; border-radius: 8px;">
                        <p style="margin-top: 1rem;">Esta imagem contém áreas clicáveis. Tente clicar em diferentes partes.</p>
                        
                        <map name="image-map">
                            <area target="_blank" alt="Qual o maior rio do mundo?" title="Qual o maior rio do mundo?"
                                href="https://pt.wikipedia.org/wiki/Amazonas,_o_maior_rio_do_mundo"
                                coords="302,745,322,691,360,657,443,629,526,629,662,654,730,671,832,691,949,686,1044,683,1109,650,1085,606,992,582,915,548,730,504,652,487,473,491,264,495,236,481,311,451,588,439,620,417,515,399,430,408,520,412,580,420,556,427,464,432,363,433,305,439,247,451,214,466,198,485,235,502,351,513,464,510,549,511,652,514,766,543,809,557,936,593,974,628,879,633,719,609,598,595,522,589,430,589,314,600,229,633,198,653,168,677,155,718,145,745,229,746,276,745"
                                shape="poly">
                            <area target="_blank" alt="Nuvem" title="Nuvem" href="https://pt.wikipedia.org/wiki/Nuvem"
                                coords="448,54,419,66,419,87,412,100,421,110,456,115,497,119,532,121,570,124,605,124,644,124,688,118,699,107,730,110,752,105,734,94,685,92,672,81,655,72,642,66,638,46,628,36,613,43,605,37,586,51,560,47,548,54,548,64,521,67,503,51,478,56"
                                shape="poly">
                        </map>
                    </div>
                </div>
            </div>
        </section>

        <!-- Seção Interativa -->
        <section class="section fade-in" id="interativo">
            <h2 class="section-title">Elementos Interativos</h2>
            <p>HTML permite criar elementos interativos para melhorar a experiência do usuário.</p>
            
            <div class="cards-container">
                <div class="card">
                    <div class="card-header">
                        <h3>Barra de Progresso</h3>
                    </div>
                    <div class="card-body">
                        <div class="progress-container">
                            <progress id="progressBar" max="100" value="0"></progress>
                            <span id="progressText">0%</span>
                            <button class="btn" onclick="startProgress()">Iniciar Progresso</button>
                        </div>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Links e Abreviações</h3>
                    </div>
                    <div class="card-body">
                        <p>
                            <a href="https://google.com" class="btn" target="_blank">
                                <i class="fas fa-external-link-alt"></i> Visitar Google
                            </a>
                        </p>
                        <p style="margin-top: 1rem;">
                            O <abbr title="BetoCarreiro World" style="border-bottom: 1px dotted; cursor: help;">BCW</abbr> 
                            foi fundado em 1991. (Passe o mouse sobre "BCW")
                        </p>
                    </div>
                </div>
                
                <div class="card">
                    <div class="card-header">
                        <h3>Informações de Contato</h3>
                    </div>
                    <div class="card-body">
                        <address>
                            Escrito por <a href="mailto:vinicius.sebold@gmail.com">Vinicius Sebold</a> <br>
                            Visite-nos em: <br>
                            Rua 564, Blumenau <br>
                            SC, Brasil
                        </address>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Botão de alternar tema -->
    <div class="theme-toggle" id="themeToggle">
        <i class="fas fa-moon"></i>
    </div>

    <!-- Rodapé -->
    <footer style="background-color: var(--dark-bg); color: white; padding: 2rem 0; text-align: center; margin-top: 2rem;">
        <div class="container">
            <p>&copy; 2023 Guia de Elementos HTML. Todos os direitos reservados.</p>
            <div style="margin-top: 1rem;">
                <a href="#" style="color: white; margin: 0 10px;"><i class="fab fa-facebook"></i></a>
                <a href="#" style="color: white; margin: 0 10px;"><i class="fab fa-twitter"></i></a>
                <a href="#" style="color: white; margin: 0 10px;"><i class="fab fa-instagram"></i></a>
                <a href="#" style="color: white; margin: 0 10px;"><i class="fab fa-github"></i></a>
            </div>
        </div>
    </footer>

    <script>
        // Função para a barra de progresso
        function startProgress() {
            var progressBar = document.getElementById('progressBar');
            var progressText = document.getElementById('progressText');
            var value = 0;

            // Desabilita o botão durante a animação
            document.querySelector('.progress-container .btn').disabled = true;

            var interval = setInterval(function () {
                value += 2;
                progressBar.value = value;
                progressText.innerHTML = Math.round(value) + "%";

                if (value >= progressBar.max) {
                    clearInterval(interval);
                    progressText.innerHTML = "Completo!";
                    
                    // Reativa o botão após completar
                    setTimeout(function() {
                        document.querySelector('.progress-container .btn').disabled = false;
                    }, 1000);
                }
            }, 100);
        }

        // Animação de entrada para seções
        document.addEventListener('DOMContentLoaded', function() {
            const sections = document.querySelectorAll('.section');
            
            const observer = new IntersectionObserver((entries) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('fade-in');
                    }
                });
            }, { threshold: 0.1 });
            
            sections.forEach(section => {
                observer.observe(section);
            });
        });

        // Alternância de tema claro/escuro
        const themeToggle = document.getElementById('themeToggle');
        const body = document.body;
        const icon = themeToggle.querySelector('i');
        
        themeToggle.addEventListener('click', () => {
            body.classList.toggle('dark-mode');
            
            if (body.classList.contains('dark-mode')) {
                icon.classList.remove('fa-moon');
                icon.classList.add('fa-sun');
            } else {
                icon.classList.remove('fa-sun');
                icon.classList.add('fa-moon');
            }
        });

        // Rolagem suave para links de navegação
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Função para exibir data e hora atual
        function showDateTime() {
            const dateTimeElement = document.getElementById('dateTime');
            const now = new Date();
            const formattedDateTime = now.toLocaleString('pt-BR', {
                dateStyle: 'full',
                timeStyle: 'long'
            });
            dateTimeElement.innerHTML = formattedDateTime;
        }

        // Atualiza a data e hora a cada segundo
        setInterval(showDateTime, 1000);
    </script>

    <!-- Exibição de data e hora -->
    <div id="dateTime" style="position: fixed; bottom: 20px; left: 20px; background-color: var(--dark-bg); color: white; padding: 10px; border-radius: 8px; box-shadow: var(--shadow);"></div>
</body>
</html><!-- Fechamento do documento HTML. -->
