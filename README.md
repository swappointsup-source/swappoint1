# swappoint1
Website for currency exchange
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>SwapPoint — Best Currency Exchange</title>
  <meta name="description" content="SwapPoint — Best rates, best exchange terms, 24/7 support. Secure currency exchange." />
  <style>
    /* ===== SwapPoint — styles (black / green / white) ===== */
    :root{
      --bg: #0b0b0b;
      --panel: #0d0d0d;
      --accent: #2ecc71; /* bright green */
      --white: #ffffff;
      --muted: #9b9b9b;
      --glass: rgba(255,255,255,0.03);
      --radius: 12px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background: linear-gradient(180deg,var(--bg), #070707);
      color:var(--white);
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.5;
      padding-bottom:40px;
    }

    /* header */
    header{
      width:100%;
      position:sticky;
      top:0;
      z-index:100;
      backdrop-filter: blur(6px);
      border-bottom: 1px solid rgba(255,255,255,0.03);
      background: linear-gradient(180deg, rgba(10,10,10,0.95), rgba(10,10,10,0.85));
      display:flex;
      align-items:center;
      justify-content:space-between;
      padding:12px 20px;
      gap:16px;
    }
    .brand { display:flex; align-items:center; gap:12px; }
    .logo-ctn { width:56px; height:56px; display:flex; align-items:center; justify-content:center; background:var(--panel); border-radius:10px; padding:6px; }
    .logo-ctn svg { width:44px; height:44px; display:block; }
    .brand h1 { margin:0; font-size:18px; letter-spacing:1px; font-weight:700; }
    .brand p { margin:0; font-size:12px; color:var(--muted); }

    nav { display:flex; align-items:center; gap:10px; }
    .nav-link { color:var(--white); text-decoration:none; padding:8px 12px; border-radius:8px; font-weight:600; font-size:14px; opacity:0.95;}
    .nav-link:hover { color:var(--accent); background:transparent; transform:translateY(-1px); }
    .support-btn { background:var(--accent); color:#05100a; padding:9px 14px; border-radius:10px; text-decoration:none; font-weight:800; box-shadow: 0 6px 18px rgba(46,204,113,0.12); }

    /* hero */
    .container { max-width:1100px; margin:28px auto; padding:0 20px; }
    .hero {
      display:grid;
      grid-template-columns: 1fr 420px;
      gap:28px;
      align-items:center;
      margin-top:18px;
    }
    .hero-card {
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border-radius: var(--radius);
      padding:28px;
      box-shadow: 0 8px 30px rgba(2,8,10,0.6);
      border: 1px solid rgba(255,255,255,0.03);
    }
    .hero-card h2 { margin:0 0 12px 0; font-size:32px; }
    .hero-card p { margin:0 0 18px 0; color:var(--muted); font-size:16px; max-width:64ch; }
    .buttons { display:flex; gap:12px; flex-wrap:wrap; }
    .btn {
      display:inline-block;
      padding:12px 18px;
      border-radius:10px;
      text-decoration:none;
      font-weight:700;
      letter-spacing:0.4px;
      transition:transform .16s ease, box-shadow .16s ease;
    }
    .btn.primary {
      background:var(--accent);
      color:#05100a;
      box-shadow: 0 10px 30px rgba(46,204,113,0.12);
    }
    .btn.ghost {
      background:transparent;
      color:var(--white);
      border:1px solid rgba(255,255,255,0.06);
    }
    .btn:hover { transform:translateY(-4px); }

    /* visual */
    .visual {
      display:flex;
      align-items:center;
      justify-content:center;
      padding:18px;
      border-radius:var(--radius);
      background:linear-gradient(180deg, rgba(0,0,0,0.4), rgba(255,255,255,0.02));
      min-height:240px;
      box-shadow: inset 0 -24px 80px rgba(0,0,0,0.6);
    }
    .logo-large { width:220px; height:220px; opacity:0.98; }

    /* features */
    .features { display:flex; gap:14px; margin-top:20px; }
    .feature {
      flex:1;
      background:var(--panel);
      padding:16px;
      border-radius:12px;
      border:1px solid rgba(255,255,255,0.02);
    }
    .feature h3 { margin:0 0 8px 0; font-size:16px; }
    .feature p { margin:0; color:var(--muted); font-size:14px; }

    /* footer */
    footer { margin-top:32px; color:var(--muted); text-align:center; padding:24px 20px; font-size:14px; }

    /* responsive */
    @media (max-width:980px){
      .hero { grid-template-columns: 1fr; }
      .visual { min-height:200px; }
    }
    @media (max-width:520px){
      header { padding:10px; }
      .brand-text h1 { display:none; }
      .logo-ctn { width:48px; height:48px; }
      .hero-card h2 { font-size:22px; }
      .logo-large { width:160px; height:160px; }
    }

    /* small nice micro-animation for logo */
    .logo-anim { transform-origin:center; transition: transform .6s cubic-bezier(.2,.9,.28,1); }
    .logo-ctn:hover .logo-anim { transform: rotate(8deg) scale(1.03); }
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="logo-ctn" aria-hidden="true">
        <!-- SVG logo: circular double arrows (green) -->
        <svg class="logo-anim" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="SwapPoint logo">
          <defs>
            <linearGradient id="g" x1="0" x2="1">
              <stop offset="0" stop-color="#2ecc71"/>
              <stop offset="1" stop-color="#21b66a"/>
            </linearGradient>
          </defs>
          <circle cx="50" cy="50" r="46" fill="none" stroke="rgba(255,255,255,0.02)" stroke-width="2"/>
          <path d="M70 38c0 0 6 1 10 2 2 .6 2.5 2 1 3.5-4 3-18 6-18 6" fill="none" stroke="url(#g)" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M30 62c0 0-6-1-10-2-2-.6-2.5-2-1-3.5 4-3 18-6 18-6" fill="none" stroke="url(#g)" stroke-width="6" stroke-linecap="round" stroke-linejoin="round"/>
          <!-- arrowheads -->
          <path d="M73 41 L79 37 L78 44 Z" fill="url(#g)"/>
          <path d="M27 59 L21 63 L22 56 Z" fill="url(#g)"/>
        </svg>
      </div>
      <div class="brand-text" aria-hidden="false">
        <h1>SwapPoint</h1>
        <p>Best rates · Best exchange terms · 24/7 support</p>
      </div>
    </div>

    <nav>
      <a class="nav-link" href="#home">Home</a>
      <a class="nav-link" href="#rates">Exchange Rates</a>
      <a class="support-btn" href="https://t.me/SwapPoint_15" target="_blank" rel="noopener noreferrer">Support</a>
    </nav>
  </header>

  <main class="container" id="home">
    <section class="hero">
      <div class="hero-card">
        <h2>Best rates. Best terms. 24/7 support.</h2>
        <p>SwapPoint provides secure and fast currency exchange with the most competitive offers on the market. Transparent fees, instant execution, and round-the-clock assistance via Telegram.</p>

        <div class="buttons" role="group" aria-label="Primary actions">
          <a class="btn primary" href="#rates">Check Rates</a>
          <a class="btn ghost" href="https://t.me/SwapPoint_15" target="_blank" rel="noopener">Contact Support</a>
        </div>

        <div style="height:12px"></div>

        <div class="features" aria-hidden="false">
          <div class="feature">
            <h3>Best rate</h3>
            <p>We monitor the market to give you the most favorable exchange rates.</p>
          </div>
          <div class="feature">
            <h3>Best terms</h3>
            <p>Transparent commissions and clear conditions — no hidden fees.</p>
          </div>
          <div class="feature">
            <h3>24/7 Support</h3>
            <p>Round-the-clock support via Telegram to resolve transactions and questions fast.</p>
          </div>
        </div>
      </div>

      <div class="visual" aria-hidden="true">
        <!-- large decorative logo, white-on-black -->
        <svg class="logo-large" viewBox="0 0 220 220" xmlns="http://www.w3.org/2000/svg">
          <defs>
            <linearGradient id="g2" x1="0" x2="1">
              <stop offset="0" stop-color="#2ecc71"/>
              <stop offset="1" stop-color="#21b66a"/>
            </linearGradient>
          </defs>
          <rect width="100%" height="100%" rx="18" fill="rgba(255,255,255,0.02)"/>
          <g transform="translate(110,110)">
            <circle r="90" fill="none" stroke="rgba(255,255,255,0.02)" stroke-width="2"/>
            <path d="M60 -10 C40 -40 10 -60 -30 -40" stroke="url(#g2)" stroke-width="12" stroke-linecap="round" fill="none"/>
            <path d="M-60 10 C-40 40 -10 60 30 40" stroke="url(#g2)" stroke-width="12" stroke-linecap="round" fill="none"/>
            <polygon points="70,-14 80,-20 78,-10" fill="url(#g2)"/>
            <polygon points="-70,14 -80,20 -78,10" fill="url(#g2)"/>
          </g>
        </svg>
      </div>
    </section>

    <!-- Rates section: simple list and external link (Investing.com cannot be embedded) -->
    <section id="rates" style="margin-top:28px;">
      <div class="hero-card">
        <h2>Exchange Rates</h2>
        <p style="color:var(--muted)">For full cross rates and historic charts open the trusted provider.</p>

        <div style="display:flex;gap:12px;flex-wrap:wrap;margin-top:12px;">
          <a class="btn primary" href="https://ru.investing.com/currencies/single-currency-crosses" target="_blank" rel="noopener">Open Investing.com</a>
          <a class="btn ghost" href="#contact">Request Quote</a>
        </div>

        <div style="margin-top:18px;color:var(--muted);font-size:14px">
          <strong>Note:</strong> Live API integration (automatic rates & calculator) can be added on request.
        </div>
      </div>
    </section>

    <!-- small contact / callout -->
    <section id="contact" style="margin-top:18px;">
      <div class="hero-card" style="display:flex;gap:16px;align-items:center;justify-content:space-between;flex-wrap:wrap">
        <div>
          <h3 style="margin:0 0 6px 0">Need help now?</h3>
          <p style="margin:0;color:var(--muted)">Contact our 24/7 support on Telegram for instant assistance and best offers.</p>
        </div>
        <div>
          <a class="support-btn" href="https://t.me/SwapPoint_15" target="_blank" rel="noopener" style="display:inline-block">Support</a>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <div style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:12px">
        <div>© <span id="yr"></span> SwapPoint</div>
        <div style="color:var(--muted)"><small>Secure currency exchange • Transparent fees • Instant support</small></div>
      </div>
    </div>
  </footer>

  <script>
    // small scripts: current year & smooth scroll
    document.getElementById('yr').textContent = new Date().getFullYear();
    // smooth scroll for internal links
    document.querySelectorAll('a[href^="#"]').forEach(a=>{
      a.addEventListener('click', function(e){
        e.preventDefault();
        const target = document.querySelector(this.getAttribute('href'));
        if(target) target.scrollIntoView({behavior:'smooth', block:'start'});
      });
    });
  </script>
</body>
</html>
