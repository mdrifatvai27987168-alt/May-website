<!DOCTYPE html><html lang="bn">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>PlayBetPro.com — Smart Sports Betting</title>
  <meta name="description" content="PlayBetPro.com — A clean, modern sports betting landing page template with logo, sections, and responsive design." />
  <link rel="icon" href="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64'%3E%3Crect width='64' height='64' rx='12' fill='%230b1220'/%3E%3Cpath d='M14 44 L22 20 h8 l-8 24 h-8 Z M40 44 q8 0 8-8 0-8-8-8 h-6 v-8 h-8 v24 h14 Z' fill='%2300e07b'/%3E%3C/svg%3E" />
  <style>
    :root{
      --bg:#0b1220;        /* deep navy */
      --card:#101a2e;      /* darker card */
      --fg:#e6edf6;        /* near white */
      --muted:#8aa2c0;     /* slate */
      --accent:#00e07b;    /* neon green */
      --accent-2:#00a2ff;  /* electric blue */
      --ring: 0 0 0 3px color-mix(in srgb, var(--accent) 40%, transparent);
      --shadow: 0 8px 24px rgba(0,0,0,.35);
      --radius: 16px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0; font-family: ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", "Liberation Sans", sans-serif;
      background: radial-gradient(1000px 600px at 20% -10%, rgba(0,224,123,.15), transparent 60%),
                  radial-gradient(900px 500px at 110% 0%, rgba(0,162,255,.12), transparent 60%),
                  var(--bg);
      color:var(--fg);
    }
    a{color:inherit; text-decoration:none}
    .container{max-width:1120px; margin:auto; padding:24px}/* HEADER */
header{position:sticky; top:0; z-index:50; background:linear-gradient(180deg, rgba(11,18,32,.9), rgba(11,18,32,.7), rgba(11,18,32,0)); backdrop-filter:saturate(140%) blur(8px)}
.nav{display:flex; align-items:center; justify-content:space-between; gap:16px}
.brand{display:flex; align-items:center; gap:12px}
.brand svg{width:36px; height:36px}
.brand .wordmark{font-weight:800; letter-spacing:.3px}
.brand .pro{color:var(--accent)}

.nav-actions{display:flex; align-items:center; gap:10px}
.btn{
  display:inline-flex; align-items:center; gap:8px;
  border:1px solid color-mix(in srgb, var(--fg) 10%, transparent);
  padding:10px 14px; border-radius:999px; font-weight:600; transition:.2s ease; background:transparent; color:var(--fg);
}
.btn:hover{transform:translateY(-1px); box-shadow:var(--shadow)}
.btn.primary{background:linear-gradient(135deg, color-mix(in srgb, var(--accent) 85%, #fff 5%), color-mix(in srgb, var(--accent-2) 65%, #fff 5%)); color:#02140a; border:none}

/* HERO */
.hero{padding:64px 0 40px}
.hero-grid{display:grid; grid-template-columns:1.1fr .9fr; gap:24px; align-items:center}
.chip{display:inline-flex; align-items:center; gap:8px; padding:6px 12px; border-radius:999px; background:linear-gradient(180deg, #0e1b31 0%, #0b1220 100%); border:1px solid #183154; color:var(--muted); font-weight:600}
h1{font-size: clamp(28px, 4vw, 48px); line-height:1.12; margin:16px 0 8px}
.sub{color:var(--muted); font-size: clamp(14px, 2.4vw, 18px)}
.hero-cta{margin-top:18px; display:flex; gap:12px; flex-wrap:wrap}

.glass{background:linear-gradient(180deg, rgba(255,255,255,.04), rgba(255,255,255,.02)); border:1px solid rgba(255,255,255,.08); border-radius:var(--radius); box-shadow:var(--shadow)}
.stats{display:grid; grid-template-columns:repeat(3, 1fr); gap:12px; margin-top:18px}
.stat{padding:16px; text-align:center}
.stat .k{font-weight:800; font-size:22px; color:var(--accent)}
.stat .lbl{color:var(--muted); font-size:12px}

/* CARDS */
.section{padding:28px 0}
.cards{display:grid; grid-template-columns:repeat(3, 1fr); gap:16px}
.card{padding:18px; border-radius:var(--radius); background:var(--card); border:1px solid rgba(255,255,255,.06); box-shadow:var(--shadow)}
.card h3{margin:8px 0 6px}
.muted{color:var(--muted)}

/* LIVE TICKER */
.ticker{display:grid; grid-template-columns:repeat(2, 1fr); gap:16px}
.match{display:flex; justify-content:space-between; border-radius:14px; padding:12px 14px; background:linear-gradient(180deg, #0f1b31, #0d1628); border:1px solid #1a2a47}
.match .teams{display:flex; align-items:center; gap:8px}
.match .odds{display:flex; gap:8px}
.pill{padding:6px 10px; border-radius:12px; background:#12233e; font-weight:700}
.odds .pill{background:#0f2b1f; color:#93ffca}

/* CTA */
.cta{display:grid; grid-template-columns:1fr .7fr; gap:16px; align-items:center; margin-top:12px}
.cta .box{padding:22px}

/* FOOTER */
footer{padding:24px 0 46px; color:var(--muted)}
.footer-grid{display:grid; grid-template-columns:1.2fr .8fr .8fr; gap:16px}
.small{font-size:12px}

/* RESPONSIVE */
@media (max-width: 960px){
  .hero-grid, .cards, .ticker, .cta, .footer-grid{grid-template-columns:1fr}
}

  </style>
</head>
<body>
  <!-- SVG LOGO (inline, reusable) -->
  <svg style="position:absolute; width:0; height:0; overflow:hidden" aria-hidden="true" focusable="false">
    <symbol id="logo-playbetpro" viewBox="0 0 64 64">
      <rect x="2" y="2" width="60" height="60" rx="12" fill="#0b1220" />
      <path d="M14 44 L22 20 h8 l-8 24 h-8 Z M40 44 q8 0 8-8 0-8-8-8 h-6 v-8 h-8 v24 h14 Z" fill="#00e07b" />
    </symbol>
  </svg>  <header>
    <div class="container nav">
      <a class="brand" href="#" aria-label="PlayBetPro Home">
        <svg aria-hidden="true"><use href="#logo-playbetpro" /></svg>
        <div class="wordmark" aria-label="PlayBetPro dot com">
          <span>PlayBet</span><span class="pro">Pro</span><span>.com</span>
        </div>
      </a>
      <nav class="nav-actions" aria-label="Primary">
        <a class="btn" href="#features">Features</a>
        <a class="btn" href="#live">Live</a>
        <a class="btn" href="#security">Security</a>
        <a class="btn primary" href="#signup">Sign Up</a>
      </nav>
    </div>
  </header>  <main>
    <!-- HERO -->
    <section class="hero">
      <div class="container hero-grid">
        <div>
          <span class="chip">⚡ দ্রুত, নিরাপদ, স্মার্ট</span>
          <h1>PlayBetPro.com — স্মার্ট স্পোর্টস বেটিং প্ল্যাটফর্মের জন্য আধুনিক টেমপ্লেট</h1>
          <p class="sub">এই ল্যান্ডিং পেজটিকে আপনার ব্যাকএন্ড/অ্যাডমিনের সাথে কানেক্ট করে সহজেই লাইভ অডস, ম্যাচ ট্র্যাকিং, এবং সিকিউর পেমেন্ট সেটআপ করতে পারেন।</p>
          <div class="hero-cta">
            <a class="btn primary" href="#signup">Create Account</a>
            <a class="btn" href="#learn">Learn More</a>
          </div>
          <div class="stats glass" role="group" aria-label="Platform highlights">
            <div class="stat"><div class="k" id="stat-users">0</div><div class="lbl">রেজিস্টার্ড ইউজার</div></div>
            <div class="stat"><div class="k" id="stat-markets">0</div><div class="lbl">মার্কেট লাইভ</div></div>
            <div class="stat"><div class="k" id="stat-uptime">99.99%</div><div class="lbl">SLA Uptime</div></div>
          </div>
        </div>
        <div class="glass" style="padding:18px">
          <div class="cards" style="grid-template-columns:1fr;">
            <div class="card">
              <h3>🎯 Quick Bet Slip</h3>
              <p class="muted">এক ক্লিকে সিলেক্ট করুন, অটো–অডস আপডেট পান, ইনস্ট্যান্ট টিকিট জেনারেট।</p>
            </div>
            <div class="card">
              <h3>🔒 Bank‑grade Security</h3>
              <p class="muted">HTTPS, 2FA, এবং রোল‑বেসড এক্সেস কন্ট্রোল (RBAC) যুক্ত করুন।</p>
            </div>
            <div class="card">
              <h3>📊 Live Analytics</h3>
              <p class="muted">রিয়েল‑টাইম হিটম্যাপ, ট্র্যাফিক ও কনভার্সন চার্ট প্লাগ‑ইন করুন।</p>
            </div>
          </div>
        </div>
      </div>
    </section><!-- FEATURES -->
<section id="features" class="section">
  <div class="container">
    <h2>মূল ফিচারসমূহ</h2>
    <div class="cards">
      <article class="card">
        <h3>⚽ Multi‑Sport Markets</h3>
        <p class="muted">ফুটবল, ক্রিকেট, টেনিস সহ আরও অনেক স্পোর্টস মার্কেট যোগ করুন।</p>
      </article>
      <article class="card">
        <h3>💳 Payment Ready</h3>
        <p class="muted">SSLCommerz, bKash, Nagad বা স্ট্রাইপ API প্লাগ‑ইন করার জন্য রেডি।</p>
      </article>
      <article class="card">
        <h3>🧩 Modular API</h3>
        <p class="muted">Node/Express, Laravel বা Firebase—যেটাই পছন্দ করেন, এই টেমপ্লেট সহজে কানেক্ট করবে।</p>
      </article>
    </div>
  </div>
</section>

<!-- LIVE TICKER (Demo) -->
<section id="live" class="section">
  <div class="container">
    <h2>লাইভ ম্যাচ (ডেমো)</h2>
    <div class="ticker" id="ticker">
      <!-- JS will inject demo matches here -->
    </div>
  </div>
</section>

<!-- SECURITY & CTA -->
<section id="security" class="section">
  <div class="container cta">
    <div class="box glass">
      <h2>সিকিউরিটি ও কমপ্লায়েন্স</h2>
      <p class="muted">আপনার দেশের আইন/নীতিমালা মেনে প্ল্যাটফর্ম পরিচালনা করুন। KYC, AML এবং Responsible Gaming নীতিমালা যুক্ত করতে ভুলবেন না।</p>
      <ul class="muted">
        <li>2FA (ইমেইল/এসএমএস) • ডিভাইস ফিঙ্গারপ্রিন্টিং</li>
        <li>এনক্রিপ্টেড ট্রান্সফার (TLS 1.3) • সিকিউর হ্যাশিং (Argon2/BCrypt)</li>
        <li>অ্যাডমিন অডিট লগ • রেট‑লিমিটিং • WAF/CDN</li>
      </ul>
    </div>
    <div class="box glass" id="signup">
      <h2>এখনই শুরু করুন</h2>
      <form class="muted" onsubmit="event.preventDefault(); alert('Thanks for your interest! This is a demo form.');">
        <label class="small" for="email">ইমেইল</label>
        <input id="email" type="email" required placeholder="you@example.com" style="width:100%; margin:6px 0 10px; padding:12px 14px; border-radius:12px; border:1px solid #2a3b5f; background:#0e1730; color:var(--fg)"/>
        <label class="small" for="country">দেশ</label>
        <input id="country" type="text" placeholder="Bangladesh" style="width:100%; margin:6px 0 16px; padding:12px 14px; border-radius:12px; border:1px solid #2a3b5f; background:#0e1730; color:var(--fg)"/>
        <button class="btn primary" type="submit">Request Demo</button>
      </form>
    </div>
  </div>
</section>

  </main>  <footer>
    <div class="container footer-grid">
      <div>
        <div class="brand" style="margin-bottom:8px">
          <svg aria-hidden="true" width="28" height="28"><use href="#logo-playbetpro" /></svg>
          <div class="wordmark"><strong>PlayBet</strong><span class="pro">Pro</span><span>.com</span></div>
        </div>
        <p class="small">© <span id="year"></span> PlayBetPro.com — All rights reserved.</p>
      </div>
      <div>
        <p class="small">Responsible Gaming</p>
        <p class="small">18+ only. Bet responsibly. প্রয়োজনে স্থানীয় কর্তৃপক্ষ ও হেল্পলাইনের সাথে যোগাযোগ করুন।</p>
      </div>
      <div>
        <p class="small">Legal</p>
        <p class="small">এই টেমপ্লেট ডেমো/শিক্ষামূলক উদ্দেশ্যে। প্রকৃত বেটিং সার্ভিস চালুর আগে আইনগত পরামর্শ নিন।</p>
      </div>
    </div>
  </footer>  <script>
    // year
    document.getElementById('year').textContent = new Date().getFullYear();

    // demo stats counter
    function animateCounter(el, target){
      let v = 0; const step = Math.max(1, Math.floor(target/60));
      const t = setInterval(()=>{ v += step; if(v >= target){ v = target; clearInterval(t); } el.textContent = v.toLocaleString(); }, 16);
    }
    animateCounter(document.getElementById('stat-users'), 12500);
    animateCounter(document.getElementById('stat-markets'), 340);

    // demo live matches
    const demoMatches = [
      { teams: 'BAN vs IND', mins: 18, odds:[1.72, 2.10, 3.40] },
      { teams: 'LIV vs MCI', mins: 62, odds:[2.30, 3.10, 2.85] },
      { teams: 'PSG vs RMA', mins: 41, odds:[2.05, 3.30, 3.10] },
      { teams: 'AUS vs ENG', mins: 9, odds:[1.88, 2.45, 3.80] }
    ];
    const $ticker = document.getElementById('ticker');
    function renderTicker(){
      $ticker.innerHTML = '';
      demoMatches.forEach(m => {
        const row = document.createElement('div');
        row.className = 'match';
        row.innerHTML = `
          <div class="teams">
            <span class="pill">${m.mins}'</span>
            <strong>${m.teams}</strong>
          </div>
          <div class="odds" aria-label="odds">
            ${m.odds.map(o=>`<span class='pill'>${o.toFixed(2)}</span>`).join('')}
          </div>
        `;
        $ticker.appendChild(row);
      });
    }
    renderTicker();

    // subtle odds wiggle (demo only)
    setInterval(()=>{
      demoMatches.forEach(m => {
        m.odds = m.odds.map(o => Math.max(1.2, o + (Math.random()-.5)*0.06));
        m.mins = (m.mins + (Math.random() < .4 ? 1 : 0)) % 90;
      });
      renderTicker();
    }, 2500);
  </script></body>
</html>
