<!DOCTYPE html><html lang="bn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Crash Game – Demo (Education Only)</title>
  <style>
    :root { --bg:#0b1320; --card:#111a2e; --accent:#3ea6ff; --text:#e6eefb; --muted:#9fb3d1; --danger:#ff5d6c; --success:#54d38a; }
    *{box-sizing:border-box}
    body{margin:0;font-family:system-ui,-apple-system,Segoe UI,Roboto,Ubuntu,"Helvetica Neue",Arial; background:var(--bg); color:var(--text)}
    .wrap{max-width:1000px;margin:24px auto;padding:16px}
    .header{display:flex;align-items:center;justify-content:space-between;margin-bottom:16px}
    .title{font-size:24px;font-weight:700;letter-spacing:.3px}
    .badge{font-size:12px;color:var(--bg);background:var(--accent);padding:4px 10px;border-radius:999px}
    .grid{display:grid;grid-template-columns:1.2fr .8fr;gap:16px}
    .card{background:var(--card);border:1px solid rgba(255,255,255,.06);border-radius:16px;padding:16px;box-shadow:0 8px 24px rgba(0,0,0,.25)}
    .row{display:flex;gap:12px;flex-wrap:wrap}
    label{font-size:13px;color:var(--muted)}
    .field{display:flex;flex-direction:column;gap:6px;min-width:120px}
    input[type="number"], input[type="text"]{appearance:textfield}
    input{width:100%;padding:10px 12px;border-radius:12px;border:1px solid rgba(255,255,255,.08);background:#0a1022;color:var(--text);outline:none}
    input:focus{border-color:var(--accent);box-shadow:0 0 0 3px rgba(62,166,255,.15)}
    button{cursor:pointer;border:0;border-radius:12px;padding:12px 14px;font-weight:600}
    .btn-primary{background:var(--accent);color:#061224}
    .btn-secondary{background:#1b2847;color:var(--text)}
    .btn-danger{background:var(--danger);color:#1a0f10}
    .btn-disabled{opacity:.5;cursor:not-allowed}
    .stats{display:flex;gap:16px;flex-wrap:wrap;margin-top:8px}
    .stat{background:#0a1022;border:1px solid rgba(255,255,255,.06);padding:10px 12px;border-radius:12px;font-size:14px}
    canvas{width:100%;height:360px;background:linear-gradient(180deg, rgba(255,255,255,.04),rgba(255,255,255,0));border-radius:12px}
    .status{margin-top:10px;font-size:14px;color:var(--muted)}
    .multiplier{font-size:40px;font-weight:800;letter-spacing:.5px}
    .multiplier .x{font-size:18px;color:var(--muted)}
    .history{max-height:360px;overflow:auto;border-radius:12px}
    table{width:100%;border-collapse:collapse}
    th,td{padding:10px 12px;border-bottom:1px solid rgba(255,255,255,.06);font-size:14px}
    th{position:sticky;top:0;background:#0e1730;text-align:left;color:var(--muted)}
    .tag{padding:2px 8px;border-radius:999px;font-size:12px}
    .tag.win{background:rgba(84,211,138,.15);color:var(--success)}
    .tag.lose{background:rgba(255,93,108,.15);color:var(--danger)}
    .mt{margin-top:12px}
    .small{font-size:12px;color:var(--muted)}
  </style>
</head>
<body>
  <div class="wrap">
    <div class="header">
      <div class="title">Crash Game – Demo <span class="badge">শুধু শেখার জন্য</span></div>
      <div class="stat">ব্যালেন্স: <b id="balance">1000</b> কয়েন</div>
    </div><div class="grid">
  <!-- Left: Chart -->
  <div class="card">
    <canvas id="chart" width="800" height="360"></canvas>
    <div class="status">
      <div class="multiplier"><span id="multiplier">1.00</span><span class="x">×</span></div>
      <div id="status">রাউন্ড শুরু করতে BET দিয়ে Start চাপুন।</div>
    </div>
  </div>

  <!-- Right: Controls + History -->
  <div class="card">
    <div class="row">
      <div class="field" style="flex:1">
        <label>Bet (কয়েন)</label>
        <input id="bet" type="number" min="1" value="50" />
      </div>
      <div class="field" style="flex:1">
        <label>Auto Cashout (ঐচ্ছিক, যেমন 2.5)</label>
        <input id="autoCash" type="number" min="1.01" step="0.01" placeholder="" />
      </div>
    </div>
    <div class="row mt">
      <button id="startBtn" class="btn-primary">Start</button>
      <button id="cashoutBtn" class="btn-secondary btn-disabled" disabled>Cash Out</button>
      <button id="resetBtn" class="btn-danger">Reset Demo</button>
    </div>
    <div class="small mt">⚠️ এই ডেমোতে বাস্তব টাকার কোনো লেনদেন নেই। শুধুই শিক্ষামূলক ও পরীক্ষামূলক ব্যবহার। আপনার দেশের আইন মেনে চলুন।</div>
  </div>
</div>

<div class="card mt history">
  <table>
    <thead>
      <tr>
        <th>রাউন্ড</th>
        <th>Bet</th>
        <th>ক্যাশআউট</th>
        <th>বস্ট</th>
        <th>প্রফিট</th>
        <th>স্ট্যাটাস</th>
      </tr>
    </thead>
    <tbody id="history"></tbody>
  </table>
</div>

  </div>  <script>
    // ====== Utility RNG with crypto ======
    function rand() {
      const buf = new Uint32Array(1);
      crypto.getRandomValues(buf);
      return buf[0] / 2**32; // [0,1)
    }

    // Sample a bust multiplier with a light tail, capped to 20x
    function sampleBust() {
      const u = rand();
      // Exponential-like distribution shifted by 1: mean around ~2.6x, min ~1.03x
      let m = 1.03 + (-Math.log(1 - u)) * 1.6; 
      if (m > 20) m = 20;
      return m;
    }

    // Format helpers
    const fmt = (v, d=2) => Number(v).toFixed(d);

    // DOM
    const canvas = document.getElementById('chart');
    const ctx = canvas.getContext('2d');
    const balEl = document.getElementById('balance');
    const multEl = document.getElementById('multiplier');
    const statusEl = document.getElementById('status');
    const betEl = document.getElementById('bet');
    const autoEl = document.getElementById('autoCash');
    const startBtn = document.getElementById('startBtn');
    const cashBtn = document.getElementById('cashoutBtn');
    const resetBtn = document.getElementById('resetBtn');
    const historyTbody = document.getElementById('history');

    // State
    let balance = 1000;
    let running = false;
    let cashed = false;
    let round = 0;
    let bet = 0;
    let bustAt = 0;
    let startTime = 0;
    let points = []; // {t, m}
    let raf = null;

    // Curve parameters
    const growth = 0.55; // multiplier = e^{growth * t}

    function currentMultiplier() {
      const elapsed = (performance.now() - startTime) / 1000;
      return Math.exp(growth * elapsed);
    }

    function draw() {
      // Determine max for scaling
      const nowM = running ? currentMultiplier() : (points.length ? points[points.length-1].m : 1);
      const maxM = Math.max(2, Math.min(20, Math.ceil(Math.max(nowM, bustAt) * 1.1)));

      // Clear
      ctx.clearRect(0,0,canvas.width, canvas.height);

      // Grid
      ctx.globalAlpha = 0.15;
      ctx.strokeStyle = '#ffffff';
      ctx.lineWidth = 1;
      for (let i=1;i<maxM;i+=1){
        const y = mapY(i, maxM);
        ctx.beginPath(); ctx.moveTo(0,y); ctx.lineTo(canvas.width, y); ctx.stroke();
      }
      ctx.globalAlpha = 1;

      // Axis labels
      ctx.fillStyle = '#9fb3d1';
      ctx.font = '12px system-ui';
      for (let i=1;i<=maxM;i+=1){
        const y = mapY(i, maxM);
        ctx.fillText(i+'×', 6, y-4);
      }

      // Path
      ctx.strokeStyle = '#3ea6ff';
      ctx.lineWidth = 3;
      ctx.beginPath();
      points.forEach((p, idx)=>{
        const x = mapX(p.t);
        const y = mapY(p.m, maxM);
        if(idx===0) ctx.moveTo(x,y); else ctx.lineTo(x,y);
      });
      ctx.stroke();

      // Bust marker
      if (bustAt>0){
        const y = mapY(bustAt, maxM);
        ctx.strokeStyle = '#ff5d6c';
        ctx.setLineDash([6,6]);
        ctx.beginPath(); ctx.moveTo(0,y); ctx.lineTo(canvas.width, y); ctx.stroke();
        ctx.setLineDash([]);
      }
    }

    function mapX(t){
      // show last 10 seconds window
      const maxT = 10;
      const x = (t / maxT) * canvas.width;
      return Math.max(0, Math.min(canvas.width, x));
    }
    function mapY(m, maxM){
      const pad = 20;
      const h = canvas.height - pad*2;
      const y = canvas.height - pad - (Math.min(m, maxM)-1)/(maxM-1) * h;
      return y;
    }

    function tick(){
      if (!running) return;
      const t = (performance.now() - startTime)/1000;
      const m = currentMultiplier();

      // Push point for drawing
      points.push({t, m});

      // Update UI multiplier
      multEl.textContent = fmt(m, 2);

      // Auto-cashout
      const auto = parseFloat(autoEl.value);
      if (!isNaN(auto) && !cashed && m >= auto){ doCashout(m); }

      // Bust check
      if (m >= bustAt){
        endRound(false, m);
        return;
      }

      draw();
      raf = requestAnimationFrame(tick);
    }

    function startRound(){
      if (running) return;
      bet = Math.max(1, Math.floor(parseFloat(betEl.value)||0));
      if (bet > balance){ statusEl.textContent = 'পর্যাপ্ত ব্যালেন্স নেই।'; return; }

      balance -= bet; updateBalance();
      cashed = false; running = true; round += 1; points = []; startTime = performance.now();
      bustAt = sampleBust();

      statusEl.textContent = 'রাউন্ড চলছে… Cash Out করলে লাভ হবে।';
      startBtn.classList.add('btn-disabled'); startBtn.disabled = true;
      cashBtn.classList.remove('btn-disabled'); cashBtn.disabled = false;

      multEl.textContent = '1.00';
      draw();
      raf = requestAnimationFrame(tick);
    }

    function doCashout(m){
      if (!running || cashed) return;
      cashed = true;
      const win = Math.floor(bet * m);
      balance += win; updateBalance();
      statusEl.textContent = `ক্যাশআউট হয়েছে ${fmt(m)}× এ।`; 
      // End round immediately upon cashout
      endRound(true, m);
    }

    function endRound(won, m){
      running = false;
      cancelAnimationFrame(raf);
      draw();

      const bustShown = Math.max(m, bustAt);
      const profit = won ? Math.floor(bet * m) - bet : -bet;
      addHistory({round, bet, cashout: won ? m : null, bust: bustAt, profit, won});

      startBtn.classList.remove('btn-disabled'); startBtn.disabled = false;
      cashBtn.classList.add('btn-disabled'); cashBtn.disabled = true;

      if (!won){
        statusEl.textContent = `বস্ট হয়ে গেছে ${fmt(bustAt)}× এ।`; 
      }
    }

    function addHistory({round, bet, cashout, bust, profit, won}){
      const tr = document.createElement('tr');
      tr.innerHTML = `
        <td>#${round}</td>
        <td>${bet}</td>
        <td>${cashout? fmt(cashout)+'×' : '-'}</td>
        <td>${fmt(bust)}×</td>
        <td>${profit}</td>
        <td><span class="tag ${won?'win':'lose'}">${won?'WIN':'LOSE'}</span></td>`;
      historyTbody.prepend(tr);
    }

    function updateBalance(){ balEl.textContent = balance; }

    function resetDemo(){
      balance = 1000; updateBalance();
      running = false; cashed = false; bet = 0; bustAt = 0; points = []; draw();
      startBtn.classList.remove('btn-disabled'); startBtn.disabled = false;
      cashBtn.classList.add('btn-disabled'); cashBtn.disabled = true;
      statusEl.textContent = 'রাউন্ড শুরু করতে BET দিয়ে Start চাপুন।';
      multEl.textContent = '1.00';
      historyTbody.innerHTML = '';
    }

    // Events
    startBtn.addEventListener('click', startRound);
    cashBtn.addEventListener('click', ()=> doCashout(currentMultiplier()));
    resetBtn.addEventListener('click', resetDemo);

    // Initial draw
    draw();
  </script></body>
</html>
