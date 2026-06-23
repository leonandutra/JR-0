<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>JR Importados | Eletrônicos & Acessórios Premium</title>
  
  <!-- Bootstrap 5 CSS -->
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css" rel="stylesheet">
  <!-- Google Fonts: Inter para texto e Montserrat para títulos chamativos -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Montserrat:wght@400;600;700;800&display=swap" rel="stylesheet">
  <!-- Font Awesome Icons -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  
  <style>
    /* Estilos Gerais & Paleta de Cores Premium (Escura) */
    :root {
      --bg-color: #0b0b0c;
      --bg-card: #141416;
      --primary-gold: #d4af37;
      --gold-hover: #f3cf55;
      --text-white: #ffffff;
      --text-gray: #a1a1a6;
      --accent-neon: #ff3366; /* Tom rosa/laranja do gradiente do Instagram */
      --insta-gradient: linear-gradient(45deg, #f09433 0%, #e6683c 25%, #dc2743 50%, #cc2366 75%, #bc1888 100%);
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-white);
      font-family: 'Inter', sans-serif;
      overflow-x: hidden;
    }

    h1, h2, h3, h4, .brand-font {
      font-family: 'Montserrat', sans-serif;
      font-weight: 700;
    }

    /* Scrollbar Personalizada */
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: var(--bg-color);
    }
    ::-webkit-scrollbar-thumb {
      background: #333;
      border-radius: 4px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: var(--primary-gold);
    }

    /* Efeito de Vidro Glow (Glassmorphism) */
    .glass-card {
      background: rgba(20, 20, 22, 0.8);
      backdrop-filter: blur(12px);
      border: 1px solid rgba(255, 255, 255, 0.05);
      border-radius: 16px;
      transition: all 0.3s ease;
    }

    /* Header & Logo */
    .navbar {
      background-color: rgba(11, 11, 12, 0.95) !important;
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      padding: 15px 0;
    }

    .navbar-brand {
      font-size: 1.5rem;
      letter-spacing: 2px;
    }

    .logo-container {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .logo-badge {
      font-weight: 800;
      background: linear-gradient(135deg, #ffffff 0%, var(--primary-gold) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      border: 2px solid var(--primary-gold);
      padding: 2px 8px;
      border-radius: 6px;
      font-size: 1.3rem;
    }

    .nav-link {
      color: var(--text-gray) !important;
      font-weight: 500;
      transition: color 0.3s ease;
    }

    .nav-link:hover, .nav-link.active {
      color: var(--primary-gold) !important;
    }

    /* Hero Section */
    .hero-section {
      position: relative;
      padding: 140px 0 80px;
      background: radial-gradient(circle at top right, rgba(212, 175, 55, 0.07), transparent 45%),
                  radial-gradient(circle at bottom left, rgba(220, 39, 67, 0.05), transparent 40%);
    }

    .hero-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      background: rgba(212, 175, 55, 0.1);
      border: 1px solid rgba(212, 175, 55, 0.2);
      color: var(--primary-gold);
      padding: 6px 16px;
      border-radius: 50px;
      font-size: 0.85rem;
      font-weight: 600;
      margin-bottom: 24px;
      letter-spacing: 1px;
      text-transform: uppercase;
    }

    .hero-title {
      font-size: clamp(2.5rem, 5vw, 4.2rem);
      line-height: 1.15;
      margin-bottom: 20px;
    }

    .hero-title span {
      background: linear-gradient(135deg, #ffffff 40%, var(--primary-gold) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero-desc {
      color: var(--text-gray);
      font-size: 1.15rem;
      max-width: 550px;
      margin-bottom: 35px;
    }

    .hero-showcase {
      position: relative;
      overflow: hidden;
      border-radius: 24px;
      min-height: 460px;
      background: #111113;
      border: 1px solid rgba(212, 175, 55, 0.22);
      box-shadow: 0 24px 60px rgba(0,0,0,0.55);
    }

    .hero-showcase img {
      width: 100%;
      height: 100%;
      min-height: 460px;
      object-fit: cover;
      filter: saturate(1.05) contrast(1.04);
    }

    .hero-showcase::after {
      content: '';
      position: absolute;
      inset: 0;
      background: linear-gradient(180deg, rgba(0,0,0,0.03) 0%, rgba(0,0,0,0.72) 100%);
    }

    .hero-showcase-label {
      position: absolute;
      left: 24px;
      right: 24px;
      bottom: 24px;
      z-index: 2;
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 16px;
    }

    .hero-showcase-label strong {
      display: block;
      font-size: 1.2rem;
    }

    .hero-showcase-label span {
      color: rgba(255,255,255,0.72);
      font-size: 0.9rem;
    }

    /* Botões personalizados */
    .btn-custom-gold {
      background: linear-gradient(135deg, var(--primary-gold) 0%, #b28d28 100%);
      color: #000 !important;
      font-weight: 700;
      padding: 12px 30px;
      border-radius: 10px;
      border: none;
      box-shadow: 0 4px 15px rgba(212, 175, 55, 0.3);
      transition: all 0.3s ease;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }

    .btn-custom-gold:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(212, 175, 55, 0.45);
    }

    .btn-custom-outline {
      background: transparent;
      color: var(--text-white) !important;
      border: 1.5px solid rgba(255, 255, 255, 0.15);
      padding: 12px 30px;
      border-radius: 10px;
      font-weight: 600;
      transition: all 0.3s ease;
      display: inline-flex;
      align-items: center;
      gap: 8px;
    }

    .btn-custom-outline:hover {
      background: rgba(255, 255, 255, 0.05);
      border-color: var(--text-white);
      transform: translateY(-2px);
    }

    /* Seção de Números / Stats */
    .stats-section {
      padding: 40px 0;
      border-top: 1px solid rgba(255, 255, 255, 0.05);
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      background: rgba(255, 255, 255, 0.01);
    }

    .stat-card {
      text-align: center;
      padding: 15px;
    }

    .stat-number {
      font-size: 3rem;
      font-weight: 800;
      background: linear-gradient(135deg, var(--primary-gold), #fff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 5px;
    }

    .stat-label {
      color: var(--text-gray);
      font-size: 0.95rem;
      text-transform: uppercase;
      letter-spacing: 1px;
      font-weight: 500;
    }

    /* Cards de Categorias de Produtos */
    .category-section {
      padding: 100px 0;
    }

    .section-header {
      margin-bottom: 60px;
    }

    .section-subtitle {
      color: var(--primary-gold);
      text-transform: uppercase;
      letter-spacing: 2px;
      font-size: 0.85rem;
      font-weight: 600;
      margin-bottom: 10px;
    }

    .section-title {
      font-size: 2.2rem;
    }

    .category-card {
      border: 1px solid rgba(255, 255, 255, 0.05);
      border-radius: 20px;
      background: var(--bg-card);
      overflow: hidden;
      transition: all 0.4s cubic-bezier(0.165, 0.84, 0.44, 1);
      position: relative;
    }

    .category-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(to bottom, transparent 40%, rgba(0, 0, 0, 0.9));
      z-index: 1;
    }

    .category-card:hover {
      transform: translateY(-8px);
      border-color: rgba(212, 175, 55, 0.3);
      box-shadow: 0 12px 30px rgba(0, 0, 0, 0.5);
    }

    .category-img-wrapper {
      height: 280px;
      overflow: hidden;
      position: relative;
    }

    .category-img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.6s ease;
    }

    .category-card:hover .category-img {
      transform: scale(1.08);
    }

    .category-content {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      padding: 30px;
      z-index: 2;
    }

    .category-icon {
      font-size: 1.8rem;
      color: var(--primary-gold);
      margin-bottom: 15px;
    }

    .category-card-title {
      font-size: 1.4rem;
      font-weight: 700;
      margin-bottom: 8px;
    }

    .category-card-desc {
      color: var(--text-gray);
      font-size: 0.9rem;
      margin-bottom: 0;
    }

    /* Carrossel Deslizante de Imagens de Produtos (Infinito Lateral) */
    .slider-section {
      padding: 80px 0;
      background: rgba(255, 255, 255, 0.02);
      overflow: hidden;
    }

    .slider-container {
      position: relative;
      width: 100%;
      overflow: hidden;
      padding: 20px 0;
    }

    /* Trilha que se move infinitamente via CSS */
    .slider-track {
      display: flex;
      width: calc(290px * 12); /* 260px do card + 30px de margem */
      animation: scrollInfinite 25s linear infinite;
    }

    .slider-track:hover {
      animation-play-state: paused;
    }

    .slider-item {
      width: 260px;
      margin: 0 15px;
      flex-shrink: 0;
      background: var(--bg-card);
      border-radius: 16px;
      border: 1px solid rgba(255, 255, 255, 0.04);
      padding: 15px;
      transition: all 0.3s ease;
      cursor: pointer;
    }

    .slider-item:hover {
      border-color: var(--primary-gold);
      transform: scale(1.03);
    }

    .slider-img-container {
      height: 200px;
      border-radius: 12px;
      overflow: hidden;
      background-color: #1a1a1a;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 12px;
      position: relative;
    }

    .slider-img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      transition: transform 0.5s ease;
    }

    .slider-item:hover .slider-img {
      transform: scale(1.08);
    }

    .product-badge {
      position: absolute;
      top: 8px;
      left: 8px;
      background: rgba(0, 0, 0, 0.75);
      border: 1px solid var(--primary-gold);
      color: var(--primary-gold);
      font-size: 0.7rem;
      font-weight: 700;
      padding: 3px 8px;
      border-radius: 40px;
      text-transform: uppercase;
    }

    .product-name {
      font-size: 1rem;
      font-weight: 600;
      margin-bottom: 5px;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }

    .product-sub {
      color: var(--text-gray);
      font-size: 0.8rem;
      margin-bottom: 10px;
    }

    .product-price-row {
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .product-status {
      font-size: 0.75rem;
      color: #2ec4b6; /* Verde moderno */
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 4px;
    }

    .product-btn-shop {
      background: transparent;
      border: none;
      color: var(--primary-gold);
      font-size: 0.9rem;
      font-weight: 600;
      padding: 0;
      transition: color 0.2s ease;
    }

    .product-btn-shop:hover {
      color: var(--gold-hover);
    }

    .product-btn-shop i {
      font-size: 0.8rem;
    }

    @keyframes scrollInfinite {
      0% {
        transform: translateX(0);
      }
      100% {
        transform: translateX(calc(-290px * 6)); /* Move metade do total */
      }
    }

    /* Seção Depoimentos */
    .testimonials-section {
      padding: 100px 0;
    }

    .testimonial-card {
      padding: 35px;
      height: 100%;
    }

    .testimonial-stars {
      color: var(--primary-gold);
      margin-bottom: 15px;
      font-size: 0.9rem;
    }

    .testimonial-text {
      font-style: italic;
      color: var(--text-gray);
      line-height: 1.6;
      margin-bottom: 20px;
    }

    .client-info {
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .client-avatar {
      width: 48px;
      height: 48px;
      border-radius: 50%;
      background: #252528;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      color: var(--primary-gold);
      border: 1.5px solid rgba(212, 175, 55, 0.3);
    }

    .client-name {
      font-weight: 600;
      font-size: 0.95rem;
      margin-bottom: 2px;
    }

    .client-meta {
      font-size: 0.75rem;
      color: #666;
    }

    /* Seção Chamada p/ Ação (CTA) e Instagram */
    .instagram-cta-section {
      padding: 80px 0;
      background: linear-gradient(135deg, rgba(20, 20, 22, 0.9) 0%, rgba(11, 11, 12, 0.95) 100%), 
                  radial-gradient(circle at center, rgba(188, 24, 136, 0.1) 0%, transparent 60%);
      border: 1px solid rgba(255, 255, 255, 0.05);
      border-radius: 30px;
      margin: 0 15px;
    }

    .instagram-badge {
      background: var(--insta-gradient);
      color: white;
      padding: 8px 20px;
      border-radius: 50px;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 0.9rem;
      font-weight: 600;
      margin-bottom: 25px;
      box-shadow: 0 4px 15px rgba(220, 39, 67, 0.3);
    }

    .btn-instagram {
      background: var(--insta-gradient);
      color: white !important;
      font-weight: 700;
      padding: 14px 35px;
      border-radius: 12px;
      border: none;
      box-shadow: 0 4px 15px rgba(220, 39, 67, 0.3);
      transition: all 0.3s ease;
      display: inline-flex;
      align-items: center;
      gap: 10px;
    }

    .btn-instagram:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 22px rgba(220, 39, 67, 0.5);
    }

    /* Botão Flutuante do WhatsApp */
    .whatsapp-float {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background-color: #25d366;
      color: white;
      width: 60px;
      height: 60px;
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 30px;
      box-shadow: 0 4px 20px rgba(37, 211, 102, 0.4);
      z-index: 9999;
      transition: all 0.3s ease;
      text-decoration: none !important;
    }

    .whatsapp-float:hover {
      transform: scale(1.1) rotate(10deg);
      color: white;
      box-shadow: 0 6px 25px rgba(37, 211, 102, 0.6);
    }

    .whatsapp-pulse {
      position: absolute;
      width: 100%;
      height: 100%;
      background-color: #25d366;
      border-radius: 50%;
      z-index: -1;
      opacity: 0.7;
      animation: pulseWhatsapp 2s infinite;
    }

    @keyframes pulseWhatsapp {
      0% {
        transform: scale(1);
        opacity: 0.7;
      }
      100% {
        transform: scale(1.4);
        opacity: 0;
      }
    }

    /* Rodapé */
    footer {
      background-color: #060607;
      border-top: 1px solid rgba(255, 255, 255, 0.05);
      padding: 60px 0 30px;
    }

    .footer-brand-title {
      font-size: 1.5rem;
      letter-spacing: 1px;
      margin-bottom: 15px;
    }

    .footer-desc {
      color: var(--text-gray);
      font-size: 0.9rem;
      line-height: 1.6;
    }

    .footer-link-title {
      font-weight: 600;
      font-size: 1rem;
      margin-bottom: 20px;
      color: var(--text-white);
    }

    .footer-links {
      list-style: none;
      padding: 0;
      margin: 0;
    }

    .footer-links li {
      margin-bottom: 10px;
    }

    .footer-links a {
      color: var(--text-gray);
      text-decoration: none;
      font-size: 0.9rem;
      transition: color 0.2s ease;
    }

    .footer-links a:hover {
      color: var(--primary-gold);
    }

    .footer-info-item {
      display: flex;
      align-items: center;
      gap: 10px;
      color: var(--text-gray);
      font-size: 0.9rem;
      margin-bottom: 12px;
    }

    .footer-info-item i {
      color: var(--primary-gold);
    }

    .footer-bottom {
      border-top: 1px solid rgba(255, 255, 255, 0.05);
      margin-top: 40px;
      padding-top: 25px;
      font-size: 0.8rem;
      color: #666;
    }

    /* Responsividade */
    @media (max-width: 991.98px) {
      .hero-section {
        padding: 120px 0 60px;
        text-align: center;
      }
      .hero-desc {
        margin: 0 auto 35px;
      }
      .hero-buttons {
        display: flex;
        flex-direction: column;
        gap: 15px;
        align-items: center;
      }
      .hero-buttons .btn {
        width: 100%;
        max-width: 320px;
        justify-content: center;
      }
      .instagram-cta-section {
        text-align: center;
      }
    }
  </style>
</head>
<body>

  <!-- Menu de Navegação -->
  <nav class="navbar navbar-expand-lg navbar-dark fixed-top">
    <div class="container">
      <a class="navbar-brand logo-container" href="#">
        <span class="logo-badge">JR</span>
        <span class="brand-font" style="font-size: 1.15rem; letter-spacing: 1px; color:#fff;">IMPORTADOS</span>
      </a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#mainNavbar" aria-controls="mainNavbar" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="mainNavbar">
        <ul class="navbar-nav ms-auto mb-2 mb-lg-0 gap-3">
          <li class="nav-item">
            <a class="nav-link active" href="#">Início</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#categorias">Categorias</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#vitrine">Vitrine</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#depoimentos">Depoimentos</a>
          </li>
        </ul>
        <div class="ms-lg-4 mt-3 mt-lg-0">
          <a href="#" target="_blank" rel="noopener" class="btn-custom-gold py-2 px-4 js-whatsapp" data-message="Olá, vi o seu portfólio e gostaria de saber mais sobre os produtos!" style="font-size: 0.9rem;">
            <i class="fa-brands fa-whatsapp"></i> Chamar no WhatsApp
          </a>
        </div>
      </div>
    </div>
  </nav>

  <!-- Hero Section (Destaque Inicial) -->
  <section class="hero-section d-flex align-items-center">
    <div class="container">
      <div class="row align-items-center">
        <div class="col-lg-6">
          <div class="hero-badge">
            <i class="fa-solid fa-gem"></i> Qualidade Premium com Preço Justo
          </div>
          <h1 class="hero-title">
            Os Melhores <br><span>Importados</span><br> Estão Aqui.
          </h1>
          <p class="hero-desc">
            Eletrônicos originais, acessórios selecionados e o melhor da tecnologia mundial direto para as suas mãos com a garantia que você merece.
          </p>
          <div class="hero-buttons d-flex gap-3">
            <a href="#" target="_blank" rel="noopener" class="btn-custom-gold js-whatsapp" data-message="Olá! Gostaria de ver o catálogo disponível.">
              <i class="fa-brands fa-whatsapp"></i> Fazer Pedido
            </a>
            <a href="https://www.instagram.com/jr.importados_dte/" target="_blank" rel="noopener" class="btn-custom-outline">
              <i class="fa-brands fa-instagram"></i> Ver Instagram
            </a>
          </div>
        </div>
        
        <!-- Foto de destaque da marca -->
        <div class="col-lg-6 d-none d-lg-block">
          <div class="hero-showcase mx-auto">
            <img src="https://images.unsplash.com/photo-1516321318423-f06f85e504b3?auto=format&fit=crop&w=1000&q=80" alt="Produtos eletronicos premium em uma mesa">
            <div class="hero-showcase-label">
              <div>
                <strong>JR Importados</strong>
                <span>Produtos selecionados, atendimento direto e envio para a regiao.</span>
              </div>
              <span class="logo-badge">JR</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção de Números e Conquistas (Satisfeitos) -->
  <section class="stats-section">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-12 text-center mb-4">
          <p class="text-uppercase tracking-wider text-white-50 small mb-0" style="letter-spacing: 2px;">Nossa Credibilidade</p>
        </div>
      </div>
      <div class="row justify-content-center text-center">
        <div class="col-6 col-md-3">
          <div class="stat-card">
            <div class="stat-number">+100</div>
            <div class="stat-label">Clientes Satisfeitos</div>
          </div>
        </div>
        <div class="col-6 col-md-3">
          <div class="stat-card">
            <div class="stat-number">100%</div>
            <div class="stat-label">Originais e Garantidos</div>
          </div>
        </div>
        <div class="col-6 col-md-3 mt-4 mt-md-0">
          <div class="stat-card">
            <div class="stat-number">+40</div>
            <div class="stat-label">Posts no Instagram</div>
          </div>
        </div>
        <div class="col-6 col-md-3 mt-4 mt-md-0">
          <div class="stat-card">
            <div class="stat-number">2 mil</div>
            <div class="stat-label">Seguidores Conectados</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção de Categorias de Produtos -->
  <section id="categorias" class="category-section">
    <div class="container">
      <div class="section-header text-center">
        <span class="section-subtitle">O que oferecemos</span>
        <h2 class="section-title">Nossos Departamentos</h2>
      </div>
      
      <div class="row g-4">
        <!-- Categoria 1: Eletrônicos -->
        <div class="col-md-4">
          <div class="category-card h-100">
            <div class="category-img-wrapper">
              <img class="category-img" src="https://images.unsplash.com/photo-1511707171634-5f897ff02aa9?auto=format&fit=crop&w=900&q=80" alt="Smartphone moderno">
            </div>
            <div class="category-content">
              <div class="category-icon">
                <i class="fa-solid fa-mobile-screen-button"></i>
              </div>
              <h3 class="category-card-title">Eletrônicos</h3>
              <p class="category-card-desc">Os últimos lançamentos de Smartphones, Tablets e Gadgets com tecnologia avançada de ponta.</p>
            </div>
          </div>
        </div>

        <!-- Categoria 2: Acessórios Premium -->
        <div class="col-md-4">
          <div class="category-card h-100">
            <div class="category-img-wrapper">
              <img class="category-img" src="https://images.unsplash.com/photo-1505740420928-5e560c06d30e?auto=format&fit=crop&w=900&q=80" alt="Fone de ouvido premium">
            </div>
            <div class="category-content">
              <div class="category-icon">
                <i class="fa-solid fa-headphones-simple"></i>
              </div>
              <h3 class="category-card-title">Acessórios</h3>
              <p class="category-card-desc">Fones de ouvido bluetooth, carregadores ultra-rápidos e capas protetoras de máxima resistência.</p>
            </div>
          </div>
        </div>

        <!-- Categoria 3: Importados em Geral -->
        <div class="col-md-4">
          <div class="category-card h-100">
            <div class="category-img-wrapper">
              <img class="category-img" src="https://images.unsplash.com/photo-1546868871-7041f2a55e12?auto=format&fit=crop&w=900&q=80" alt="Relogio inteligente">
            </div>
            <div class="category-content">
              <div class="category-icon">
                <i class="fa-solid fa-clock"></i>
              </div>
              <h3 class="category-card-title">Importados</h3>
              <p class="category-card-desc">Smartwatches premium, perfumes importados e caixas de som das melhores marcas internacionais.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção Carrossel de Imagens passando para os lados (Vitrine Dinâmica) -->
  <section id="vitrine" class="slider-section">
    <div class="container">
      <div class="section-header text-center mb-5">
        <span class="section-subtitle">Desejados da Semana</span>
        <h2 class="section-title">Vitrine Digital JR</h2>
        <p class="text-white-50 mt-2">Passe o mouse ou toque nos produtos para pausar</p>
      </div>
    </div>

    <!-- Container de Slides com rolagem contínua infinita -->
    <div class="slider-container">
      <div class="slider-track" id="sliderTrack">
        <!-- Os itens serão duplicados para garantir o loop contínuo infinito -->
        
        <!-- Item 1 -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Mais vendido</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1592750475338-74b7b21085ab?auto=format&fit=crop&w=700&q=80" alt="iPhone 15 Pro Max">
          </div>
          <h4 class="product-name">iPhone 15 Pro Max</h4>
          <p class="product-sub">Titânio Natural</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('iPhone 15 Pro Max')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 2 -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge" style="border-color:#ff3366; color:#ff3366;">Premium</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1434493907317-a46b5bbe7834?auto=format&fit=crop&w=700&q=80" alt="Apple Watch Series 9">
          </div>
          <h4 class="product-name">Apple Watch Series 9</h4>
          <p class="product-sub">45mm Aluminium</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('Apple Watch Series 9')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 3 -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Novo</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1606220945770-b5b6c2c55bf1?auto=format&fit=crop&w=700&q=80" alt="AirPods Pro 2">
          </div>
          <h4 class="product-name">AirPods Pro 2ª Geração</h4>
          <p class="product-sub">Som Espacial Ativo</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('AirPods Pro 2')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 4 -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Top Desejo</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1606813907291-d86efa9b94db?auto=format&fit=crop&w=700&q=80" alt="PlayStation 5 Slim">
          </div>
          <h4 class="product-name">PlayStation 5 Slim</h4>
          <p class="product-sub">Console Sony 1TB</p>
          <div class="product-price-row">
            <span class="product-status" style="color: #ff9f1c;"><span style="width:6px;height:6px;background:#ff9f1c;border-radius:50%;display:inline-block;"></span> Sob Consulta</span>
            <button class="product-btn-shop" onclick="orderProduct('PlayStation 5 Slim')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 5 -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Som</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1545454675-3531b543be5d?auto=format&fit=crop&w=700&q=80" alt="JBL Boombox 3">
          </div>
          <h4 class="product-name">JBL Boombox 3</h4>
          <p class="product-sub">Potência Premium</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('JBL Boombox 3')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 6 -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Oferta</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1517336714731-489689fd1ca8?auto=format&fit=crop&w=700&q=80" alt="MacBook Air M2">
          </div>
          <h4 class="product-name">MacBook Air M2</h4>
          <p class="product-sub">Super Fino e Veloz</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('MacBook Air M2')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- REPETIÇÃO DOS ITENS PARA FAZER LOOP INFINITO SEM GARGALOS -->
        
        <!-- Item 1 Repetido -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Mais vendido</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1592750475338-74b7b21085ab?auto=format&fit=crop&w=700&q=80" alt="iPhone 15 Pro Max">
          </div>
          <h4 class="product-name">iPhone 15 Pro Max</h4>
          <p class="product-sub">Titânio Natural</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('iPhone 15 Pro Max')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 2 Repetido -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge" style="border-color:#ff3366; color:#ff3366;">Premium</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1434493907317-a46b5bbe7834?auto=format&fit=crop&w=700&q=80" alt="Apple Watch Series 9">
          </div>
          <h4 class="product-name">Apple Watch Series 9</h4>
          <p class="product-sub">45mm Aluminium</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('Apple Watch Series 9')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 3 Repetido -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Novo</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1606220945770-b5b6c2c55bf1?auto=format&fit=crop&w=700&q=80" alt="AirPods Pro 2">
          </div>
          <h4 class="product-name">AirPods Pro 2ª Geração</h4>
          <p class="product-sub">Som Espacial Ativo</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('AirPods Pro 2')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 4 Repetido -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Top Desejo</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1606813907291-d86efa9b94db?auto=format&fit=crop&w=700&q=80" alt="PlayStation 5 Slim">
          </div>
          <h4 class="product-name">PlayStation 5 Slim</h4>
          <p class="product-sub">Console Sony 1TB</p>
          <div class="product-price-row">
            <span class="product-status" style="color: #ff9f1c;"><span style="width:6px;height:6px;background:#ff9f1c;border-radius:50%;display:inline-block;"></span> Sob Consulta</span>
            <button class="product-btn-shop" onclick="orderProduct('PlayStation 5 Slim')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 5 Repetido -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Som</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1545454675-3531b543be5d?auto=format&fit=crop&w=700&q=80" alt="JBL Boombox 3">
          </div>
          <h4 class="product-name">JBL Boombox 3</h4>
          <p class="product-sub">Potência Premium</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('JBL Boombox 3')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

        <!-- Item 6 Repetido -->
        <div class="slider-item">
          <div class="slider-img-container">
            <span class="product-badge">Oferta</span>
            <img class="slider-img" src="https://images.unsplash.com/photo-1517336714731-489689fd1ca8?auto=format&fit=crop&w=700&q=80" alt="MacBook Air M2">
          </div>
          <h4 class="product-name">MacBook Air M2</h4>
          <p class="product-sub">Super Fino e Veloz</p>
          <div class="product-price-row">
            <span class="product-status"><span style="width:6px;height:6px;background:#2ec4b6;border-radius:50%;display:inline-block;"></span> Em Estoque</span>
            <button class="product-btn-shop" onclick="orderProduct('MacBook Air M2')">Quero <i class="fa-solid fa-arrow-right"></i></button>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- Seção Depoimentos Reais de Clientes -->
  <section id="depoimentos" class="testimonials-section">
    <div class="container">
      <div class="section-header text-center">
        <span class="section-subtitle">Quem comprou aprova</span>
        <h2 class="section-title">Depoimentos dos Clientes</h2>
      </div>

      <div class="row g-4">
        <!-- Depoimento 1 -->
        <div class="col-md-4">
          <div class="glass-card testimonial-card">
            <div class="testimonial-stars">
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
            </div>
            <p class="testimonial-text">
              "Atendimento excelente! O produto chegou muito rápido e com lacre original. O pessoal da JR tirou todas as minhas dúvidas sobre a garantia."
            </p>
            <div class="client-info">
              <div class="client-avatar">MS</div>
              <div>
                <h5 class="client-name">Mateus Silva</h5>
                <span class="client-meta">Cliente de Diamante do Norte</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Depoimento 2 -->
        <div class="col-md-4">
          <div class="glass-card testimonial-card">
            <div class="testimonial-stars">
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
            </div>
            <p class="testimonial-text">
              "Comprei meu novo Smartwatch com eles e o preço foi realmente o melhor da região. O produto é espetacular, de qualidade indiscutível."
            </p>
            <div class="client-info">
              <div class="client-avatar">AO</div>
              <div>
                <h5 class="client-name">Amanda Oliveira</h5>
                <span class="client-meta">Cliente de Nova Londrina</span>
              </div>
            </div>
          </div>
        </div>

        <!-- Depoimento 3 -->
        <div class="col-md-4">
          <div class="glass-card testimonial-card">
            <div class="testimonial-stars">
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
              <i class="fa-solid fa-star"></i>
            </div>
            <p class="testimonial-text">
              "Comprei um iPhone 15 e a experiência foi nota 10. Honestidade e preço justo, recomendo muito a JR Importados para todos do Paraná!"
            </p>
            <div class="client-info">
              <div class="client-avatar">RC</div>
              <div>
                <h5 class="client-name">Rodrigo Costa</h5>
                <span class="client-meta">Cliente de Loanda</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- Seção Redes Sociais & CTA Premium (Instagram) -->
  <section class="container mb-5">
    <div class="instagram-cta-section p-4 p-md-5">
      <div class="row align-items-center justify-content-between">
        <div class="col-lg-7 text-center text-lg-start mb-4 mb-lg-0">
          <div class="instagram-badge">
            <i class="fa-brands fa-instagram"></i> @jr.importados_dte
          </div>
          <h2 class="brand-font mb-3" style="font-size: 2rem;">Siga-nos no Instagram</h2>
          <p class="text-white-50 mb-0">
            Fique por dentro das novidades, promoções diárias, unboxings e muito conteúdo tecnológico. Siga nosso perfil oficial e faça parte da nossa comunidade.
          </p>
        </div>
        <div class="col-lg-4 text-center">
          <a href="https://www.instagram.com/jr.importados_dte/" target="_blank" rel="noopener" class="btn-instagram">
            <i class="fa-brands fa-instagram" style="font-size: 1.3rem;"></i> Seguir @jr.importados_dte
          </a>
        </div>
      </div>
    </div>
  </section>

  <!-- Botão Flutuante do WhatsApp -->
  <a href="#" target="_blank" rel="noopener" class="whatsapp-float js-whatsapp" data-message="Olá! Gostaria de consultar a disponibilidade de um importado.">
    <div class="whatsapp-pulse"></div>
    <i class="fa-brands fa-whatsapp"></i>
  </a>

  <!-- Rodapé -->
  <footer>
    <div class="container">
      <div class="row g-4">
        <div class="col-lg-5">
          <div class="logo-container mb-3">
            <span class="logo-badge">JR</span>
            <span class="brand-font" style="font-size: 1.15rem; letter-spacing: 1.5px; color:#fff;">IMPORTADOS</span>
          </div>
          <p class="footer-desc">
            Sua loja referência em importados, eletrônicos e acessórios premium de alta qualidade com o melhor preço de Diamante do Norte - PR e região.
          </p>
        </div>
        
        <div class="col-lg-3 col-md-6">
          <h4 class="footer-link-title">Navegação</h4>
          <ul class="footer-links">
            <li><a href="#">Início</a></li>
            <li><a href="#categorias">Categorias</a></li>
            <li><a href="#vitrine">Vitrine Digital</a></li>
            <li><a href="#depoimentos">Depoimentos</a></li>
          </ul>
        </div>

        <div class="col-lg-4 col-md-6">
          <h4 class="footer-link-title">Contato & Localização</h4>
          <div class="footer-info-item">
            <i class="fa-solid fa-location-dot"></i>
            <span>Diamante do Norte - PR</span>
          </div>
          <div class="footer-info-item">
            <i class="fa-solid fa-envelope"></i>
            <a href="mailto:contato.jrimportados@gmail.com" style="color: var(--text-gray); text-decoration: none;">contato.jrimportados@gmail.com</a>
          </div>
          <div class="footer-info-item">
            <i class="fa-brands fa-instagram"></i>
            <a href="https://www.instagram.com/jr.importados_dte/" target="_blank" rel="noopener" style="color: var(--text-gray); text-decoration: none;">@jr.importados_dte</a>
          </div>
        </div>
      </div>

      <div class="footer-bottom d-flex flex-column flex-md-row justify-content-between align-items-center">
        <p class="mb-2 mb-md-0">&copy; 2026 JR Importados. Todos os direitos reservados.</p>
        <p class="mb-0">Feito com foco em Qualidade Premium e Tecnologia.</p>
      </div>
    </div>
  </footer>

  <!-- Bootstrap 5 JS Bundle com Popper -->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
  
  <script>
    const WHATSAPP_NUMBER = "5544999999999";
    const INSTAGRAM_URL = "https://www.instagram.com/jr.importados_dte/";

    function whatsappUrl(message) {
      return `https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent(message)}`;
    }

    document.querySelectorAll('.js-whatsapp').forEach((link) => {
      link.href = whatsappUrl(link.dataset.message || 'Olá! Vim pelo site da JR Importados.');
    });

    document.querySelectorAll('a[href^="https://www.instagram.com"]').forEach((link) => {
      link.href = INSTAGRAM_URL;
      link.rel = 'noopener';
    });

    const sliderTrack = document.getElementById('sliderTrack');
    if (sliderTrack) {
      sliderTrack.addEventListener('touchstart', () => {
        sliderTrack.style.animationPlayState = 'paused';
      }, { passive: true });

      sliderTrack.addEventListener('touchend', () => {
        sliderTrack.style.animationPlayState = 'running';
      }, { passive: true });
    }

    // Função para direcionar a intenção de compra ao WhatsApp do vendedor de maneira personalizada
    function orderProduct(productName) {
      const message = `Olá, vi seu site portfólio e fiquei interessado no ${productName}. Gostaria de saber mais informações sobre preço e envio!`;
      window.open(whatsappUrl(message), '_blank', 'noopener');
    }

    // Comportamento sutil do scroll para o menu se tornar mais opaco ao rolar
    window.addEventListener('scroll', function() {
      const navbar = document.querySelector('.navbar');
      if (window.scrollY > 50) {
        navbar.style.boxShadow = '0 10px 30px rgba(0,0,0,0.8)';
        navbar.style.borderBottom = '1px solid rgba(212, 175, 55, 0.15)';
      } else {
        navbar.style.boxShadow = 'none';
        navbar.style.borderBottom = '1px solid rgba(255, 255, 255, 0.05)';
      }
    });
  </script>
</body>
</html>

