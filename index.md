<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>METUSALEM696 — Project Hub</title>
  <meta name="description" content="PCB • Arduino/ESP32 • Python Automation — projects, docs & services." />
  <style>
    :root{
      --bg:#0b1020;
      --panel:#0f1731;
      --panel2:#121c3a;
      --text:#e7ecff;
      --muted:#a8b3e6;
      --line:rgba(255,255,255,.10);
      --shadow: 0 12px 34px rgba(0,0,0,.35);
      --r:18px;
      --max:1120px;
      --accent:#7aa2ff;
      --accent2:#7dffcc;
      --warn:#ffd27a;
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      font-family: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Arial, "Apple Color Emoji","Segoe UI Emoji";
      color:var(--text);
      background:
        radial-gradient(900px 600px at 15% 10%, rgba(122,162,255,.18), transparent 60%),
        radial-gradient(900px 600px at 85% 15%, rgba(125,255,204,.12), transparent 60%),
        radial-gradient(900px 600px at 50% 90%, rgba(255,210,122,.08), transparent 55%),
        var(--bg);
      line-height:1.55;
    }
    a{color:inherit}
    .wrap{max-width:var(--max); margin:0 auto; padding:28px 16px 64px}
    header{
      display:flex; gap:18px; align-items:center; justify-content:space-between;
      padding:12px 0 8px;
      position:sticky; top:0;
      background: linear-gradient(180deg, rgba(11,16,32,.92), rgba(11,16,32,.72));
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(255,255,255,.06);
      z-index:10;
    }
    .brand{
      display:flex; align-items:center; gap:12px; text-decoration:none;
    }
    .logo{
      width:44px; height:44px; border-radius:14px;
      background: linear-gradient(135deg, rgba(122,162,255,.95), rgba(125,255,204,.85));
      box-shadow: var(--shadow);
      flex:0 0 auto;
    }
    .brand h1{font-size:16px; margin:0}
    .brand p{margin:0; color:var(--muted); font-size:12.5px}
    nav{display:flex; gap:8px; flex-wrap:wrap; justify-content:flex-end}
    .chip{
      text-decoration:none;
      padding:8px 10px;
      border:1px solid var(--line);
      background: rgba(255,255,255,.04);
      border-radius:999px;
      font-size:13px;
      color:var(--muted);
      transition:.15s ease;
      white-space:nowrap;
    }
    .chip:hover{transform:translateY(-1px); color:var(--text); border-color:rgba(122,162,255,.35)}
    .hero{
      margin-top:16px;
      padding:22px;
      border:1px solid var(--line);
      border-radius: var(--r);
      background: linear-gradient(180deg, rgba(255,255,255,.05), rgba(255,255,255,.02));
      box-shadow: var(--shadow);
    }
    .hero h2{margin:0; font-size:28px; letter-spacing:.2px}
    .hero .sub{margin:8px 0 0; color:var(--muted); max-width:80ch}
    .cta{
      display:flex; gap:10px; flex-wrap:wrap; align-items:center; margin-top:14px
    }
    .btn{
      display:inline-flex; gap:8px; align-items:center;
      padding:10px 12px;
      border-radius:12px;
      border:1px solid var(--line);
      text-decoration:none;
      background: rgba(255,255,255,.04);
      transition:.15s ease;
      font-weight:650;
      font-size:13.5px;
    }
    .btn.primary{
      border-color: rgba(122,162,255,.45);
      background: linear-gradient(135deg, rgba(122,162,255,.22), rgba(125,255,204,.10));
    }
    .btn:hover{transform:translateY(-1px); border-color: rgba(122,162,255,.55)}
    .small{font-size:12px; color:var(--muted)}
    .section{
      margin-top:18px;
      padding:18px;
      border:1px solid var(--line);
      border-radius: var(--r);
      background: rgba(255,255,255,.03);
      box-shadow: var(--shadow);
    }
    .section h2{margin:0 0 10px; font-size:20px}
    .grid3{display:grid; grid-template-columns: repeat(3, 1fr); gap:12px}
    @media (max-width: 980px){ .grid3{grid-template-columns: repeat(2, 1fr);} }
    @media (max-width: 640px){
      .grid3{grid-template-columns: 1fr;}
      .hero h2{font-size:24px}
      header{position:static}
    }
    .card{
      border:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.02);
      border-radius: 16px;
      overflow:hidden;
      display:flex;
      flex-direction:column;
      min-height: 280px;
    }
    .thumb{
      height:160px;
      background: rgba(255,255,255,.02);
      border-bottom:1px solid rgba(255,255,255,.08);
      position:relative;
      overflow:hidden;
    }
    .thumb img{
      width:100%;
      height:100%;
      object-fit:cover;
      display:block;
      transform:scale(1.02);
      filter:saturate(1.05) contrast(1.02);
    }
    .badge{
      position:absolute; top:10px; left:10px;
      font-size:12px; padding:6px 8px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.18);
      background: rgba(0,0,0,.35);
      backdrop-filter: blur(6px);
    }
    .content{padding:12px 12px 10px; display:flex; flex-direction:column; gap:8px; flex:1}
    .title{display:flex; align-items:flex-start; justify-content:space-between; gap:10px}
    .title h3{margin:0; font-size:16px; line-height:1.25}
    .meta{color:var(--muted); font-size:13px}
    .tags{display:flex; gap:8px; flex-wrap:wrap; margin-top:2px}
    .tag{
      font-size:12px; color:var(--muted);
      padding:5px 8px;
      border:1px solid rgba(255,255,255,.10);
      border-radius:999px;
      background: rgba(255,255,255,.03);
    }
    .actions{
      padding:10px 12px 12px;
      border-top:1px solid rgba(255,255,255,.08);
      background: rgba(255,255,255,.02);
      display:flex; gap:10px; flex-wrap:wrap;
    }
    .cols{
      display:grid; gap:12px;
      grid-template-columns: 1.1fr .9fr;
    }
    @media (max-width: 980px){ .cols{grid-template-columns: 1fr;} }
    .box{
      border:1px solid rgba(255,255,255,.10);
      border-radius:16px;
      background: rgba(255,255,255,.02);
      padding:14px;
    }
    ul{margin:8px 0 0; padding-left:18px}
    li{margin:6px 0}
    .gallery{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:10px;
      margin-top:10px;
    }
    @media (max-width: 980px){ .gallery{grid-template-columns: repeat(2, 1fr);} }
    @media (max-width: 640px){ .gallery{grid-template-columns: 1fr;} }
    .shot{
      border:1px solid rgba(255,255,255,.10);
      border-radius:16px;
      overflow:hidden;
      background: rgba(255,255,255,.02);
    }
    .shot img{width:100%; height:220px; object-fit:cover; display:block}
    footer{
      margin-top:22px;
      padding-top:18px;
      border-top:1px solid rgba(255,255,255,.10);
      color:var(--muted);
      display:flex; gap:12px; flex-wrap:wrap; align-items:center; justify-content:space-between;
    }
    .foot-links{display:flex; gap:12px; flex-wrap:wrap}
    .foot-links a{color:var(--muted); text-decoration:none}
    .foot-links a:hover{color:var(--text)}
    .hr{height:1px; background:rgba(255,255,255,.08); margin:14px 0}
  </style>
</head>

<body>
  <div class="wrap">

    <header>
      <a class="brand" href="#top">
        <div class="logo" aria-hidden="true"></div>
        <div>
          <h1>METUSALEM696</h1>
          <p>PCB • Arduino/ESP32 • Python Automation</p>
        </div>
      </a>

      <nav>
        <a class="chip" href="#hardware">🧩 PCB</a>
        <a class="chip" href="#power">⚡ Power Board</a>
        <a class="chip" href="#nano">🧠 Nano Shield</a>
        <a class="chip" href="#firmware">🚀 Arduino/ESP32</a>
        <a class="chip" href="#python">🐍 Python</a>
        <a class="chip" href="#contact">📩 Contact</a>
      </nav>
    </header>

    <section class="hero" id="top">
      <h2>Project Hub — one-page portfolio ⚡</h2>
      <p class="sub">
        A single-page showcase of my PCB boards, Arduino/ESP32 IoT & automation work, and Python automation services.
        Built for real-world reliability, clean wiring, and practical docs.
      </p>
      <div class="cta">
        <a class="btn primary" href="#hardware">🚀 Browse Sections</a>
        <a class="btn" href="#contact">📩 Hire / Message</a>
      </div>
      <p class="small" style="margin:10px 0 0;">
        ✅ Low-voltage electronics only • 🔒 Authorized projects only
      </p>
    </section>

    <!-- QUICK OVERVIEW CARDS -->
    <section class="section" id="hardware">
      <h2>🧩 Hardware / PCB</h2>
      <div class="grid3">

        <article class="card">
          <div class="thumb">
            <span class="badge">⚡ PCB</span>
            <img loading="lazy" alt="12V to 5V Power Board + MOSFET"
              src="assets/img/Screenshot%202026-02-07%20160822.png"
              onerror="this.style.display='none'; this.parentElement.style.background='linear-gradient(135deg, rgba(122,162,255,.25), rgba(125,255,204,.10))';">
          </div>
          <div class="content">
            <div class="title"><h3>12V → 5V Power Board + MOSFET</h3></div>
            <div class="meta">Power + protection footprints + MOSFET output area (low-voltage DIY projects).</div>
            <div class="tags">
              <span class="tag">12V</span><span class="tag">Buck</span><span class="tag">Protection</span><span class="tag">MOSFET</span>
            </div>
          </div>
          <div class="actions">
            <a class="btn primary" href="#power">Open section</a>
            <a class="btn" href="assets/img/Screenshot%202026-02-07%20161730.png">View image</a>
          </div>
        </article>

        <article class="card">
          <div class="thumb">
            <span class="badge">🧠 PCB</span>
            <img loading="lazy" alt="Arduino Nano Round Shield / Breakout"
              src="assets/img/IMG_20260205_124823.jpg"
              onerror="this.style.display='none'; this.parentElement.style.background='linear-gradient(135deg, rgba(255,210,122,.20), rgba(122,162,255,.12))';">
          </div>
          <div class="content">
            <div class="title"><h3>Arduino Nano Round Shield / Breakout</h3></div>
            <div class="meta">Clean pin access for fast prototyping, wiring and enclosure builds.</div>
            <div class="tags">
              <span class="tag">Arduino Nano</span><span class="tag">Breakout</span><span class="tag">Round PCB</span>
            </div>
          </div>
          <div class="actions">
            <a class="btn primary" href="#nano">Open section</a>
            <a class="btn" href="assets/img/IMG_20260205_124137.jpg">Second photo</a>
          </div>
        </article>

        <article class="card">
          <div class="thumb">
            <span class="badge">🚀 Services</span>
            <img loading="lazy" alt="Services"
              src="assets/img/Screenshot%202026-02-07%20161754.png"
              onerror="this.style.display='none'; this.parentElement.style.background='linear-gradient(135deg, rgba(125,255,204,.12), rgba(255,255,255,.04))';">
          </div>
          <div class="content">
            <div class="title"><h3>Firmware + Software Services</h3></div>
            <div class="meta">Arduino/ESP32 IoT builds + Python automations with clean deliverables and support.</div>
            <div class="tags">
              <span class="tag">IoT</span><span class="tag">Automation</span><span class="tag">Docs</span>
            </div>
          </div>
          <div class="actions">
            <a class="btn primary" href="#firmware">Arduino/ESP32</a>
            <a class="btn" href="#python">Python</a>
          </div>
        </article>

      </div>
    </section>

    <!-- POWER BOARD -->
    <section class="section" id="power">
      <h2>⚡ 12V → 5V Power Board + MOSFET</h2>

      <div class="cols">
        <div class="box">
          <div class="meta">
            Round PCB for low-voltage DIY projects: power section + protection footprints + MOSFET output area.
          </div>

          <div class="hr"></div>

          <strong>✅ Highlights</strong>
          <ul>
            <li>Low-voltage board for prototypes and small automation builds</li>
            <li>Protection footprint area (as designed)</li>
            <li>MOSFET switching area for loads (as designed)</li>
          </ul>

          <div class="hr"></div>

          <strong>⚠️ Notes</strong>
          <ul>
            <li>Low voltage only. <b>Not for mains/230V.</b></li>
            <li>Double-check polarity before powering.</li>
          </ul>

          <div class="cta">
            <!-- If you don't have the PDF yet, delete this button -->
            <a class="btn primary" href="assets/pdf/power-board-quickstart.pdf">📥 Quick Start PDF</a>
            <a class="btn" href="#contact">📩 Ask / Order</a>
          </div>
        </div>

        <div class="box">
          <strong>🖼️ Gallery</strong>
          <div class="gallery">
            <div class="shot"><img loading="lazy" src="assets/img/Screenshot%202026-02-07%20160822.png" alt="Power Board image 1"></div>
            <div class="shot"><img loading="lazy" src="assets/img/Screenshot%202026-02-07%20161730.png" alt="Power Board image 2"></div>
            <div class="shot"><img loading="lazy" src="assets/img/Screenshot%202026-02-07%20161754.png" alt="Power Board image 3"></div>
          </div>
          <p class="small" style="margin:10px 0 0;">Tip: if any image doesn’t show, rename files to remove spaces.</p>
        </div>
      </div>
    </section>

    <!-- NANO SHIELD -->
    <section class="section" id="nano">
      <h2>🧠 Arduino Nano Round Shield / Breakout</h2>

      <div class="cols">
        <div class="box">
          <div class="meta">
            Clean access to Arduino Nano pins for faster wiring, prototyping, and enclosure builds.
          </div>

          <div class="hr"></div>

          <strong>✅ Highlights</strong>
          <ul>
            <li>Faster prototyping: neat wiring, easier pin access</li>
            <li>Great for projects that need stable mounting & clean cabling</li>
          </ul>

          <div class="cta">
            <!-- If you don't have the PDF yet, delete this button -->
            <a class="btn primary" href="assets/pdf/nano-shield-quickstart.pdf">📥 Quick Start PDF</a>
            <a class="btn" href="#contact">📩 Ask / Order</a>
          </div>
        </div>

        <div class="box">
          <strong>🖼️ Gallery</strong>
          <div class="gallery">
            <div class="shot"><img loading="lazy" src="assets/img/IMG_20260205_124823.jpg" alt="Nano Shield photo 1"></div>
            <div class="shot"><img loading="lazy" src="assets/img/IMG_20260205_124137.jpg" alt="Nano Shield photo 2"></div>
          </div>
        </div>
      </div>
    </section>

    <!-- ARDUINO / ESP32 -->
    <section class="section" id="firmware">
      <h2>🚀 Arduino / ESP32 Custom Projects (IoT & Automation)</h2>

      <div class="cols">
        <div class="box">
          <div class="meta">
            Need a reliable Arduino/ESP32 solution that <i>actually works</i>? I build clean, tested firmware + complete wiring guidance for DIY and small-business projects. ✅
          </div>

          <div class="hr"></div>

          <strong>💡 Example Projects</strong>
          <ul>
            <li>🧴 Smart dispenser / pump controller (timers, safety timeout, settings)</li>
            <li>🏠 Room monitor (temp/humidity + motion + display + alerts)</li>
            <li>🌱 Greenhouse logger (sensors + automation + cloud graphs)</li>
            <li>⚙️ Motor/relay automation (state machines, watchdog, fail-safes)</li>
            <li>🖥️ Basic dashboards / control panels (optional)</li>
          </ul>

          <div class="hr"></div>

          <strong>📦 Packages</strong>
          <ul>
            <li>🟢 <b>Basic</b> — small feature / fix (1 revision)</li>
            <li>🟡 <b>Standard</b> — full project firmware + wiring diagram (2 revisions)</li>
            <li>🔴 <b>Premium</b> — complete system (WiFi/MQTT/HTTP + docs) (3 revisions)</li>
          </ul>
        </div>

        <div class="box">
          <strong>🧠 What I can build</strong>
          <ul>
            <li>🏠 Smart Home / IoT: sensors, triggers, automation</li>
            <li>🌐 Connectivity: WiFi, MQTT, HTTP/REST, cloud logging</li>
            <li>⚙️ Control: relays, motors, pumps (safe low-voltage logic)</li>
            <li>⏱️ Non-blocking firmware: state machines, timers, watchdog</li>
            <li>🧩 Protocols: I2C / SPI / UART / OneWire</li>
            <li>🖥️ Displays: LCD / OLED / TFT</li>
          </ul>

          <div class="hr"></div>

          <strong>🛠️ To start (send this)</strong>
          <ul>
            <li>Board model + modules list (links/photos)</li>
            <li>Power voltage + loads (relay/motor/pump etc.)</li>
            <li>Required behavior (steps/events), deadline, budget</li>
          </ul>

          <p class="small" style="margin-top:10px;">
            🔒 Authorized projects only. Low-voltage logic preferred.
          </p>

          <div class="cta">
            <a class="btn primary" href="#contact">📩 Message me</a>
            <a class="btn" href="#python">🐍 Python services</a>
          </div>
        </div>
      </div>
    </section>

    <!-- PYTHON -->
    <section class="section" id="python">
      <h2>🐍 Python Automation & Web Scrapers</h2>

      <div class="cols">
        <div class="box">
          <div class="meta">
            Automation scripts and data extraction with clean outputs (CSV/Excel/JSON), logging, and reliability. Built to run unattended and deliver results.
          </div>

          <div class="hr"></div>

          <strong>💡 Examples</strong>
          <ul>
            <li>📦 Price/stock monitoring + alerts</li>
            <li>🧾 Data extraction into CSV/Excel/JSON</li>
            <li>🗂️ File automation (rename, sort, backup, reports)</li>
            <li>🌐 Scraping with pagination / dynamic pages (where allowed)</li>
          </ul>

          <div class="hr"></div>

          <strong>📦 Packages</strong>
          <ul>
            <li>🟢 <b>Basic</b> — single task script</li>
            <li>🟡 <b>Standard</b> — multi-step automation + outputs</li>
            <li>🔴 <b>Premium</b> — complete solution + docs + robust handling</li>
          </ul>
        </div>

        <div class="box">
          <strong>✅ Deliverables</strong>
          <ul>
            <li>Clean code + instructions</li>
            <li>Output format you need (CSV/Excel/JSON)</li>
            <li>Logging + error handling</li>
            <li>Basic support for setup</li>
          </ul>

          <div class="hr"></div>

          <strong>🛠️ To start</strong>
          <ul>
            <li>Target website/data source</li>
            <li>Fields you want (example output)</li>
            <li>Frequency (one-time / scheduled)</li>
            <li>Deadline + budget</li>
          </ul>

          <div class="cta">
            <a class="btn primary" href="#contact">📩 Message me</a>
          </div>

          <p class="small" style="margin-top:10px;">
            ✅ I follow site terms/robots & legal constraints.
          </p>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section class="section" id="contact">
      <h2>📩 Contact / Hire</h2>
      <div class="box">
        <p class="meta" style="margin:0;">
          Pune aici link-urile tale (Fiverr/Upwork). Dacă mi le dai, îți scriu și textul “pro” de profil + CTA.
        </p>

        <div class="cta">
          <!-- Replace # with your real links -->
          <a class="btn primary" href="#" rel="noopener">💼 Fiverr</a>
          <a class="btn" href="#" rel="noopener">🧾 Upwork</a>
          <a class="btn" href="https://github.com/METUSALEM696" rel="noopener">🐙 GitHub</a>
          <a class="btn" href="#top">⬆️ Top</a>
        </div>

        <p class="small" style="margin:10px 0 0;">
          Tip: renumește fișierele de imagini fără spații (ex: <b>power-board-1.png</b>) ca să eviți probleme.
        </p>
      </div>
    </section>

    <footer>
      <div>© <span id="y"></span> METUSALEM696 — one-page hub</div>
      <div class="foot-links">
        <a href="#hardware">PCB</a>
        <a href="#firmware">Arduino/ESP32</a>
        <a href="#python">Python</a>
        <a href="#contact">Contact</a>
      </div>
    </footer>

  </div>

  <script>
    document.getElementById('y').textContent = new Date().getFullYear();
  </script>
</body>
</html>
