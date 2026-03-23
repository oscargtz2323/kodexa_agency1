<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kodex Agency</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;700&family=Syne:wght@700;800&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'Space Grotesk',sans-serif;background:#08090a;color:#f0f0f0;overflow-x:hidden;}

nav{display:flex;justify-content:space-between;align-items:center;padding:1.2rem 3rem;border-bottom:1px solid #1e1e1e;position:sticky;top:0;z-index:100;background:#08090aee;backdrop-filter:blur(10px);}
.logo{font-family:'Syne',sans-serif;font-size:1.4rem;font-weight:800;letter-spacing:2px;color:#fff;}
.logo span{color:#6c63ff;}
.nav-links{display:flex;gap:2rem;list-style:none;}
.nav-links a{text-decoration:none;color:#888;font-size:0.85rem;letter-spacing:1px;text-transform:uppercase;transition:color 0.3s;}
.nav-links a:hover{color:#6c63ff;}
.nav-cta{background:#6c63ff;color:#fff;padding:0.6rem 1.5rem;font-size:0.8rem;letter-spacing:1px;text-transform:uppercase;border:none;cursor:pointer;font-family:'Space Grotesk',sans-serif;transition:background 0.3s;}
.nav-cta:hover{background:#5a52e0;}

.hero{min-height:95vh;display:flex;flex-direction:column;justify-content:center;align-items:center;text-align:center;padding:4rem 2rem;position:relative;}
.hero::before{content:'';position:absolute;width:600px;height:600px;background:radial-gradient(circle,#6c63ff22 0%,transparent 70%);top:50%;left:50%;transform:translate(-50%,-50%);pointer-events:none;}
.hero-tag{font-size:0.75rem;letter-spacing:4px;text-transform:uppercase;color:#6c63ff;margin-bottom:1.5rem;border:1px solid #6c63ff44;padding:0.4rem 1.2rem;}
.hero h1{font-family:'Syne',sans-serif;font-size:clamp(2.8rem,7vw,5.5rem);font-weight:800;line-height:1.05;margin-bottom:1.5rem;max-width:800px;}
.hero h1 span{color:#6c63ff;}
.hero p{font-size:1.05rem;color:#888;max-width:500px;line-height:1.8;margin-bottom:2.5rem;font-weight:300;}
.btn-group{display:flex;gap:1rem;flex-wrap:wrap;justify-content:center;}
.btn{padding:0.9rem 2.5rem;font-size:0.85rem;letter-spacing:1.5px;text-transform:uppercase;font-family:'Space Grotesk',sans-serif;cursor:pointer;transition:all 0.3s;text-decoration:none;display:inline-block;}
.btn-primary{background:#6c63ff;color:#fff;border:1px solid #6c63ff;}
.btn-primary:hover{background:#5a52e0;}
.btn-secondary{background:transparent;color:#f0f0f0;border:1px solid #333;}
.btn-secondary:hover{border-color:#6c63ff;color:#6c63ff;}

.stats{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:#1e1e1e;border-top:1px solid #1e1e1e;border-bottom:1px solid #1e1e1e;}
.stat{background:#08090a;padding:2.5rem;text-align:center;}
.stat-num{font-family:'Syne',sans-serif;font-size:2.5rem;font-weight:800;color:#6c63ff;}
.stat-label{font-size:0.8rem;color:#888;letter-spacing:2px;text-transform:uppercase;margin-top:0.3rem;}

.section{padding:6rem 3rem;max-width:1100px;margin:0 auto;}
.section-tag{font-size:0.75rem;letter-spacing:4px;text-transform:uppercase;color:#6c63ff;margin-bottom:1rem;}
.section-title{font-family:'Syne',sans-serif;font-size:2.5rem;font-weight:800;margin-bottom:1rem;}
.section-sub{color:#888;max-width:500px;line-height:1.8;margin-bottom:3rem;font-weight:300;}

.services-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:1px;background:#1e1e1e;}
.service-card{background:#08090a;padding:2.5rem;transition:background 0.3s;position:relative;overflow:hidden;}
.service-card:hover{background:#0f0f10;}
.service-card::before{content:'';position:absolute;top:0;left:0;width:3px;height:0;background:#6c63ff;transition:height 0.4s;}
.service-card:hover::before{height:100%;}
.service-num{font-family:'Syne',sans-serif;font-size:0.8rem;color:#6c63ff;letter-spacing:3px;margin-bottom:1.5rem;}
.service-icon{font-size:2rem;margin-bottom:1rem;}
.service-card h3{font-family:'Syne',sans-serif;font-size:1.3rem;font-weight:700;margin-bottom:0.8rem;}
.service-card p{color:#888;font-size:0.9rem;line-height:1.7;font-weight:300;margin-bottom:1.5rem;}
.service-price{font-size:1.1rem;color:#6c63ff;font-weight:500;}

.pricing-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1.5rem;margin-top:3rem;}
.pricing-card{border:1px solid #1e1e1e;padding:2.5rem;transition:border-color 0.3s;}
.pricing-card:hover{border-color:#6c63ff;}
.pricing-card.featured{border-color:#6c63ff;position:relative;}
.featured-badge{position:absolute;top:-1px;left:50%;transform:translateX(-50%);background:#6c63ff;color:#fff;font-size:0.7rem;letter-spacing:2px;text-transform:uppercase;padding:0.3rem 1rem;}
.pricing-name{font-family:'Syne',sans-serif;font-size:1rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;color:#888;margin-bottom:1rem;}
.pricing-price{font-family:'Syne',sans-serif;font-size:2.8rem;font-weight:800;color:#fff;margin-bottom:0.3rem;}
.pricing-price span{font-size:1rem;color:#888;font-weight:300;}
.pricing-desc{font-size:0.85rem;color:#888;margin-bottom:2rem;line-height:1.6;}
.pricing-features{list-style:none;margin-bottom:2rem;}
.pricing-features li{font-size:0.85rem;color:#aaa;padding:0.5rem 0;border-bottom:1px solid #1e1e1e;display:flex;align-items:center;gap:0.5rem;}
.pricing-features li::before{content:'→';color:#6c63ff;font-size:0.8rem;}

.contact-section{background:#0d0d0e;border-top:1px solid #1e1e1e;border-bottom:1px solid #1e1e1e;padding:6rem 3rem;}
.contact-inner{max-width:1100px;margin:0 auto;display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:center;}
.contact-info h2{font-family:'Syne',sans-serif;font-size:2.5rem;font-weight:800;margin-bottom:1rem;}
.contact-info p{color:#888;line-height:1.8;font-weight:300;margin-bottom:2rem;}
.contact-detail{display:flex;align-items:center;gap:1rem;margin-bottom:1rem;font-size:0.9rem;color:#aaa;}
.contact-detail span:first-child{color:#6c63ff;font-size:1rem;}
.contact-form{display:flex;flex-direction:column;gap:1rem;}
.contact-form input,.contact-form textarea{background:#08090a;border:1px solid #1e1e1e;color:#f0f0f0;padding:1rem;font-family:'Space Grotesk',sans-serif;font-size:0.9rem;transition:border-color 0.3s;resize:none;}
.contact-form input:focus,.contact-form textarea:focus{outline:none;border-color:#6c63ff;}
.contact-form textarea{height:120px;}

footer{text-align:center;padding:2rem;color:#444;font-size:0.75rem;letter-spacing:2px;text-transform:uppercase;border-top:1px solid #1e1e1e;}
</style>
</head>
<body>

<nav>
  <div class="logo">KOD<span>X</span></div>
  <ul class="nav-links">
    <li><a href="#servicios">Servicios</a></li>
    <li><a href="#precios">Precios</a></li>
    <li><a href="#contacto">Contacto</a></li>
  </ul>
  <button class="nav-cta">Cotizar gratis</button>
</nav>

<section class="hero">
  <div class="hero-tag">Agencia Digital · Querétaro, México</div>
  <h1>Tu negocio merece<br><span>presencia digital</span><br>de verdad</h1>
  <p>Diseñamos páginas web, manejamos tus redes y activamos publicidad que convierte visitas en clientes.</p>
  <div class="btn-group">
    <a href="#contacto" class="btn btn-primary">Quiero una cotización</a>
    <a href="#servicios" class="btn btn-secondary">Ver servicios</a>
  </div>
</section>

<div class="stats">
  <div class="stat"><div class="stat-num">100%</div><div class="stat-label">Compromiso</div></div>
  <div class="stat"><div class="stat-num">3</div><div class="stat-label">Servicios clave</div></div>
  <div class="stat"><div class="stat-num">QRO</div><div class="stat-label">Base de operaciones</div></div>
</div>

<section class="section" id="servicios">
  <div class="section-tag">Lo que hacemos</div>
  <h2 class="section-title">Servicios</h2>
  <p class="section-sub">Todo lo que tu negocio necesita para crecer en internet, en un solo lugar.</p>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-num">01</div>
      <div class="service-icon">🌐</div>
      <h3>Páginas web</h3>
      <p>Diseño y desarrollo de sitios web profesionales, rápidos y optimizados para que tus clientes te encuentren fácil.</p>
      <div class="service-price">Desde $3,000 MXN</div>
    </div>
    <div class="service-card">
      <div class="service-num">02</div>
      <div class="service-icon">📱</div>
      <h3>Redes sociales</h3>
      <p>Manejo profesional de Instagram y TikTok. Contenido, publicaciones y estrategia para hacer crecer tu comunidad.</p>
      <div class="service-price">Desde $1,500 MXN/mes</div>
    </div>
    <div class="service-card">
      <div class="service-num">03</div>
      <div class="service-icon">🎯</div>
      <h3>Publicidad digital</h3>
      <p>Campañas en Meta Ads y TikTok Ads dirigidas a tus clientes ideales en Querétaro y donde los necesites.</p>
      <div class="service-price">Desde $1,000 MXN/mes</div>
    </div>
  </div>
</section>

<section class="section" id="precios">
  <div class="section-tag">Planes</div>
  <h2 class="section-title">Precios claros,<br>sin sorpresas</h2>
  <div class="pricing-grid">
    <div class="pricing-card">
      <div class="pricing-name">Básico</div>
      <div class="pricing-price">$1,500 <span>/mes</span></div>
      <div class="pricing-desc">Para negocios que quieren empezar a crecer en redes.</div>
      <ul class="pricing-features">
        <li>Manejo de Instagram</li>
        <li>8 publicaciones al mes</li>
        <li>Diseño de contenido</li>
        <li>Reporte mensual</li>
      </ul>
      <a href="#contacto" class="btn btn-secondary" style="width:100%;text-align:center;">Empezar</a>
    </div>
    <div class="pricing-card featured">
      <div class="featured-badge">Más popular</div>
      <div class="pricing-name">Pro</div>
      <div class="pricing-price">$3,500 <span>/mes</span></div>
      <div class="pricing-desc">Redes + publicidad para resultados reales.</div>
      <ul class="pricing-features">
        <li>Instagram + TikTok</li>
        <li>16 publicaciones al mes</li>
        <li>Publicidad en Meta Ads</li>
        <li>Estrategia mensual</li>
        <li>Reporte detallado</li>
      </ul>
      <a href="#contacto" class="btn btn-primary" style="width:100%;text-align:center;">Empezar</a>
    </div>
    <div class="pricing-card">
      <div class="pricing-name">Full</div>
      <div class="pricing-price">$6,000 <span>/mes</span></div>
      <div class="pricing-desc">Presencia digital completa para tu negocio.</div>
      <ul class="pricing-features">
        <li>Página web incluida</li>
        <li>Instagram + TikTok</li>
        <li>Meta Ads + TikTok Ads</li>
        <li>20+ publicaciones</li>
        <li>Soporte prioritario</li>
      </ul>
      <a href="#contacto" class="btn btn-secondary" style="width:100%;text-align:center;">Empezar</a>
    </div>
  </div>
</section>

<div class="contact-section" id="contacto">
  <div class="contact-inner">
    <div class="contact-info">
      <div class="section-tag">Hablemos</div>
      <h2>¿Listo para crecer?</h2>
      <p>Cuéntanos sobre tu negocio y te mandamos una propuesta sin costo ni compromiso.</p>
      <div class="contact-detail"><span>📍</span><span>Querétaro, México</span></div>
      <div class="contact-detail"><span>📱</span><span>WhatsApp: 442 XXX XXXX</span></div>
      <div class="contact-detail"><span>📸</span><span>@kodexagency</span></div>
    </div>
    <div class="contact-form">
      <input type="text" placeholder="Nombre de tu negocio" />
      <input type="text" placeholder="Tu WhatsApp" />
      <input type="text" placeholder="¿Qué servicio te interesa?" />
      <textarea placeholder="Cuéntanos sobre tu negocio..."></textarea>
      <button class="btn btn-primary">Quiero una cotización →</button>
    </div>
  </div>
</div>

<footer>
  © 2024 Kodex Agency · Querétaro, México · Diseño web · Redes sociales · Publicidad digital
</footer>

</body>
</html>
