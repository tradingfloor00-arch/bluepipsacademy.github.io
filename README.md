
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#07111f">
<meta name="description" content="Trading Floor — market tools, trading education, trading opportunities and investor information.">
<title>Trading Floor | Markets & Trading</title>

<style>
:root {
  --bg: #07111f;
  --panel: #0e1b2d;
  --panel2: #12243a;
  --text: #f4f7fb;
  --muted: #9eafc4;
  --green: #25e6a3;
  --gold: #ffc857;
  --blue: #56a9ff;
  --purple: #b18cff;
  --red: #ff647c;
  --border: rgba(255,255,255,.10);
  --radius: 18px;
  --shadow: 0 18px 45px rgba(0,0,0,.22);
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
  scroll-padding-top: 100px;
}

body {
  min-height: 100vh;
  background:
    radial-gradient(ellipse at 15% 0%, rgba(37,230,163,.09), transparent 32%),
    radial-gradient(ellipse at 90% 12%, rgba(86,169,255,.10), transparent 30%),
    var(--bg);
  color: var(--text);
  font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  line-height: 1.6;
  overflow-x: hidden;
}

a {
  color: inherit;
  text-decoration: none;
}

button,
input,
select,
textarea {
  font: inherit;
}

button,
a {
  -webkit-tap-highlight-color: transparent;
}

button {
  cursor: pointer;
}

img,
svg {
  max-width: 100%;
}

button:focus-visible,
a:focus-visible,
input:focus-visible,
select:focus-visible,
textarea:focus-visible {
  outline: 2px solid var(--green);
  outline-offset: 4px;
}

.container {
  width: min(1160px, calc(100% - 40px));
  margin-inline: auto;
}

.section {
  padding: 76px 0;
  scroll-margin-top: 90px;
}

.section-heading {
  max-width: 740px;
  margin-bottom: 30px;
}

.eyebrow {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  color: var(--green);
  font-size: .76rem;
  font-weight: 800;
  letter-spacing: .15em;
  text-transform: uppercase;
  margin-bottom: 12px;
}

.section-heading h2 {
  font-size: clamp(1.8rem, 4vw, 3rem);
  line-height: 1.15;
  letter-spacing: -.04em;
  margin-bottom: 14px;
}

.section-heading p {
  color: var(--muted);
  max-width: 680px;
}

.gradient-text {
  background: linear-gradient(100deg, var(--green), var(--blue), var(--purple));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.btn {
  display: inline-flex;
  justify-content: center;
  align-items: center;
  gap: 9px;
  min-height: 46px;
  padding: 12px 20px;
  border: 1px solid transparent;
  border-radius: 12px;
  font-weight: 800;
  font-size: .92rem;
  transition: transform .2s ease, opacity .2s ease, background .2s ease;
  text-align: center;
}

.btn:hover {
  transform: translateY(-2px);
}

.btn-primary {
  color: #06141a;
  background: linear-gradient(110deg, var(--green), #8cf5cd);
}

.btn-secondary {
  color: var(--text);
  background: rgba(255,255,255,.04);
  border-color: var(--border);
}

.btn-gold {
  color: #241703;
  background: linear-gradient(110deg, var(--gold), #ffe6a0);
}

.btn-blue {
  color: #061625;
  background: linear-gradient(110deg, var(--blue), #a3d5ff);
}

.btn-block {
  width: 100%;
}

.card {
  min-width: 0;
  background: linear-gradient(145deg, rgba(18,36,58,.96), rgba(10,23,39,.96));
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 24px;
  box-shadow: var(--shadow);
}

.card p {
  color: var(--muted);
}

.grid {
  display: grid;
  gap: 20px;
}

.grid-2 {
  grid-template-columns: repeat(2, minmax(0, 1fr));
}

.grid-3 {
  grid-template-columns: repeat(3, minmax(0, 1fr));
}

.grid-4 {
  grid-template-columns: repeat(4, minmax(0, 1fr));
}

/* Top navigation */

.site-header {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: rgba(7,17,31,.90);
  border-bottom: 1px solid var(--border);
  backdrop-filter: blur(18px);
  -webkit-backdrop-filter: blur(18px);
}

.header-inner {
  min-height: 76px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
}

.brand {
  display: inline-flex;
  align-items: center;
  gap: 11px;
  flex-shrink: 0;
}

.brand-mark {
  width: 42px;
  height: 42px;
  display: grid;
  place-items: center;
  border-radius: 13px;
  color: #06141a;
  background: linear-gradient(135deg, var(--green), var(--blue));
  font-size: 1.2rem;
  font-weight: 1000;
  box-shadow: 0 6px 24px rgba(37,230,163,.17);
}

.brand-copy strong {
  display: block;
  font-size: 1rem;
  line-height: 1.2;
  letter-spacing: .02em;
}

.brand-copy span {
  display: block;
  color: var(--muted);
  font-size: .7rem;
  margin-top: 3px;
}

.main-nav {
  display: flex;
  align-items: center;
  gap: 5px;
}

.main-nav a {
  padding: 10px 12px;
  color: #c1cddd;
  font-size: .85rem;
  font-weight: 650;
  border-radius: 9px;
  transition: color .2s ease, background .2s ease;
}

.main-nav a:hover {
  color: var(--green);
  background: rgba(255,255,255,.05);
}

.header-action {
  flex-shrink: 0;
}

.menu-toggle {
  display: none;
  width: 44px;
  height: 44px;
  color: var(--text);
  background: var(--panel);
  border: 1px solid var(--border);
  border-radius: 12px;
  font-size: 1.3rem;
}

/* Market ticker */

.market-ticker {
  border-bottom: 1px solid var(--border);
  background: rgba(10,23,39,.88);
}

.ticker-inner {
  min-height: 42px;
  display: flex;
  align-items: center;
  gap: 24px;
  overflow-x: auto;
  scrollbar-width: thin;
}

.ticker-label {
  flex-shrink: 0;
  color: var(--green);
  font-size: .7rem;
  font-weight: 900;
  letter-spacing: .12em;
}

.ticker-item {
  flex-shrink: 0;
  display: flex;
  align-items: center;
  gap: 8px;
  color: #d9e4f1;
  font-size: .77rem;
}

.ticker-value {
  color: var(--muted);
  font-variant-numeric: tabular-nums;
}

.ticker-dot {
  width: 7px;
  height: 7px;
  border-radius: 50%;
  background: var(--gold);
}

/* Quick-access sidebar */

.quick-sidebar {
  position: fixed;
  z-index: 900;
  top: 50%;
  right: 14px;
  transform: translateY(-50%);
  display: flex;
  flex-direction: column;
  gap: 8px;
  padding: 9px;
  background: rgba(9,23,39,.94);
  border: 1px solid var(--border);
  border-radius: 17px;
  box-shadow: var(--shadow);
  backdrop-filter: blur(16px);
}

.quick-sidebar a {
  width: 48px;
  min-height: 48px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  border-radius: 12px;
  color: #b9c8d9;
  font-size: 1.2rem;
  transition: color .2s ease, background .2s ease, transform .2s ease;
}

.quick-sidebar a:hover,
.quick-sidebar a.active {
  color: var(--green);
  background: rgba(37,230,163,.12);
  transform: translateX(-2px);
}

.quick-sidebar a::after {
  content: attr(data-label);
  position: absolute;
  right: 58px;
  top: 50%;
  transform: translateY(-50%);
  padding: 7px 10px;
  border-radius: 8px;
  background: #15263b;
  border: 1px solid var(--border);
  color: var(--text);
  font-size: .75rem;
  font-weight: 700;
  white-space: nowrap;
  opacity: 0;
  pointer-events: none;
  transition: opacity .15s ease;
}

.quick-sidebar a:hover::after,
.quick-sidebar a:focus-visible::after {
  opacity: 1;
}

/* Shared section components */

.icon-box {
  width: 48px;
  height: 48px;
  display: grid;
  place-items: center;
  border-radius: 14px;
  margin-bottom: 17px;
  font-size: 1.35rem;
  background: rgba(37,230,163,.12);
  border: 1px solid rgba(37,230,163,.18);
}

.icon-box.gold {
  background: rgba(255,200,87,.12);
  border-color: rgba(255,200,87,.2);
}

.icon-box.blue {
  background: rgba(86,169,255,.12);
  border-color: rgba(86,169,255,.2);
}

.icon-box.purple {
  background: rgba(177,140,255,.12);
  border-color: rgba(177,140,255,.2);
}

.card h3 {
  font-size: 1.12rem;
  line-height: 1.35;
  margin-bottom: 10px;
}

.pill {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 6px 10px;
  border-radius: 100px;
  background: rgba(37,230,163,.10);
  color: var(--green);
  border: 1px solid rgba(37,230,163,.18);
  font-size: .72rem;
  font-weight: 800;
}

.muted {
  color: var(--muted);
}

.small {
  font-size: .82rem;
}

.divider {
  height: 1px;
  background: var(--border);
  margin: 20px 0;
}

.form-group {
  display: grid;
  gap: 7px;
  margin-bottom: 16px;
}

.form-group label {
  font-size: .84rem;
  color: #d7e2ef;
  font-weight: 700;
}

.form-control {
  width: 100%;
  min-height: 46px;
  padding: 11px 13px;
  color: var(--text);
  background: #081525;
  border: 1px solid var(--border);
  border-radius: 11px;
}

.form-control::placeholder {
  color: #74859a;
}

.form-control option {
  color: var(--text);
  background: var(--panel);
}

.notice {
  padding: 14px 16px;
  border: 1px solid rgba(255,200,87,.22);
  border-radius: 12px;
  background: rgba(255,200,87,.07);
  color: #e9d9b5;
  font-size: .84rem;
}

.notice strong {
  color: var(--gold);
}

/* Responsive layouts */

@media (max-width: 1050px) {
  .main-nav {
    gap: 0;
  }

  .main-nav a {
    padding-inline: 8px;
    font-size: .8rem;
  }

  .grid-4 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .quick-sidebar {
    right: 8px;
  }

  .quick-sidebar a {
    width: 42px;
    min-height: 42px;
  }
}

@media (max-width: 820px) {
  html {
    scroll-padding-top: 80px;
  }

  .header-inner {
    min-height: 68px;
  }

  .menu-toggle {
    display: inline-grid;
    place-items: center;
  }

  .main-nav {
    display: none;
    position: absolute;
    top: calc(100% + 1px);
    left: 0;
    right: 0;
    padding: 12px 20px 18px;
    background: rgba(7,17,31,.98);
    border-bottom: 1px solid var(--border);
    flex-direction: column;
    align-items: stretch;
  }

  .main-nav.open {
    display: flex;
  }

  .main-nav a {
    padding: 12px;
    font-size: .92rem;
  }

  .header-action {
    display: none;
  }

  .quick-sidebar {
    top: auto;
    right: 0;
    bottom: 0;
    left: 0;
    transform: none;
    border-radius: 15px 15px 0 0;
    border-bottom: 0;
    padding: 8px 5px calc(8px + env(safe-area-inset-bottom));
    flex-direction: row;
    justify-content: space-around;
    gap: 3px;
  }

  .quick-sidebar a {
    flex: 1;
    width: auto;
    min-height: 43px;
    font-size: 1.1rem;
  }

  .quick-sidebar a::after {
    display: none;
  }

  body {
    padding-bottom: calc(67px + env(safe-area-inset-bottom));
  }

  .section {
    padding: 58px 0;
  }

  .grid-3 {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 580px) {
  .container {
    width: min(100% - 28px, 1160px);
  }

  .brand-mark {
    width: 38px;
    height: 38px;
  }

  .brand-copy strong {
    font-size: .92rem;
  }

  .brand-copy span {
    font-size: .64rem;
  }

  .grid-2,
  .grid-3,
  .grid-4 {
    grid-template-columns: 1fr;
  }

  .card {
    padding: 20px;
  }

  .section {
    padding: 48px 0;
  }

  .section-heading {
    margin-bottom: 23px;
  }

  .btn {
    width: 100%;
  }

  .ticker-inner {
    gap: 17px;
  }

  .quick-sidebar a {
    font-size: 1rem;
  }
}

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    animation-duration: .01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: .01ms !important;
  }
}
</style>
</head>

<body>

<header class="site-header">
  <div class="container header-inner">
    <a class="brand" href="#home" aria-label="Trading Floor home">
      <span class="brand-mark" aria-hidden="true">TF</span>
      <span class="brand-copy">
        <strong>TRADING FLOOR</strong>
        <span>Markets · Knowledge · Opportunity</span>
      </span>
    </a>

    <nav class="main-nav" id="mainNav" aria-label="Main navigation">
      <a href="#home">Home</a>
      <a href="#markets">Markets</a>
      <a href="#offers">Opportunities</a>
      <a href="#app">Our App</a>
      <a href="#investors">Investors</a>
      <a href="#faq">FAQ</a>
    </nav>

    <a class="btn btn-primary header-action" href="#markets">Explore Markets ↗</a>

    <button
      class="menu-toggle"
      id="menuToggle"
      type="button"
      aria-label="Open navigation menu"
      aria-expanded="false"
      aria-controls="mainNav"
    >☰</button>
  </div>
</header>

<div class="market-ticker" aria-label="Market information">
  <div class="container ticker-inner">
    <span class="ticker-label">MARKET WATCH</span>
    <div class="ticker-item">
      <span class="ticker-dot"></span>
      <span>BTC / USDT</span>
      <span class="ticker-value">Illustrative data</span>
    </div>
    <div class="ticker-item">
      <span class="ticker-dot" style="background:var(--gold)"></span>
      <span>GOLD</span>
      <span class="ticker-value">Market overview</span>
    </div>
    <div class="ticker-item">
      <span class="ticker-dot" style="background:var(--blue)"></span>
      <span>FOREX</span>
      <span class="ticker-value">Market overview</span>
    </div>
    <div class="ticker-item">
      <span class="ticker-dot" style="background:var(--purple)"></span>
      <span>INDICES</span>
      <span class="ticker-value">Market overview</span>
    </div>
  </div>
</div>

<nav class="quick-sidebar" aria-label="Quick access">
  <a href="#home" data-label="Home" aria-label="Home" class="active">⌂</a>
  <a href="#markets" data-label="Markets" aria-label="Markets">▥</a>
  <a href="#offers" data-label="Opportunities" aria-label="Opportunities">✦</a>
  <a href="#app" data-label="Our App" aria-label="Our App">▣</a>
  <a href="#investors" data-label="Investors" aria-label="Investors">◈</a>
  <a href="#faq" data-label="FAQ" aria-label="Frequently asked questions">?</a>
</nav>

<main id="home">

<section class="section" id="hero">
  <div class="container">
    <div class="grid grid-2" style="align-items:center;gap:36px">
      <div>
        <span class="eyebrow">◆ YOUR TRADING JOURNEY STARTS HERE</span>
        <h1 style="font-size:clamp(2.5rem,6vw,4.8rem);line-height:1.03;letter-spacing:-.055em;margin-bottom:22px">
          Think clearly.<br>
          Trade with <span class="gradient-text">purpose.</span>
        </h1>
        <p class="muted" style="font-size:1.05rem;max-width:560px;margin-bottom:25px">
          Explore market information, trading tools, educational resources and opportunities designed to help you make more informed decisions.
        </p>
        <div class="grid grid-2" style="max-width:460px;gap:12px">
          <a class="btn btn-primary" href="#markets">Explore Markets ↗</a>
          <a class="btn btn-secondary" href="#app">Discover Our App</a>
        </div>
        <div style="display:flex;flex-wrap:wrap;gap:10px;margin-top:24px">
          <span class="pill">◆ Market insights</span>
          <span class="pill" style="color:var(--blue);background:rgba(86,169,255,.1);border-color:rgba(86,169,255,.2)">◇ Trading tools</span>
          <span class="pill" style="color:var(--gold);background:rgba(255,200,87,.1);border-color:rgba(255,200,87,.2)">✦ Learning resources</span>
        </div>
      </div>

      <div class="card" style="padding:20px;overflow:hidden">
        <div style="display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:20px">
          <div>
            <span class="eyebrow" style="margin-bottom:5px">MARKET SNAPSHOT</span>
            <h3 style="margin:0">Trading overview</h3>
          </div>
          <span class="pill">DEMO VIEW</span>
        </div>

        <div style="display:grid;grid-template-columns:1fr 1fr;gap:12px">
          <div style="padding:16px;border-radius:14px;background:rgba(37,230,163,.07);border:1px solid rgba(37,230,163,.15)">
            <span class="muted small">Market focus</span>
            <h3 style="font-size:1.2rem;margin:7px 0;color:var(--green)">BTC / USDT</h3>
            <span class="small muted">Crypto market</span>
          </div>
          <div style="padding:16px;border-radius:14px;background:rgba(86,169,255,.07);border:1px solid rgba(86,169,255,.15)">
            <span class="muted small">Asset focus</span>
            <h3 style="font-size:1.2rem;margin:7px 0;color:var(--blue)">GOLD</h3>
            <span class="small muted">Precious metals</span>
          </div>
        </div>

        <div style="margin-top:18px;padding:15px;border-radius:14px;background:#091625">
          <div style="display:flex;justify-content:space-between;gap:10px;margin-bottom:10px">
            <span class="muted small">Illustrative price movement</span>
            <span class="small" style="color:var(--gold)">Example only</span>
          </div>
          <svg viewBox="0 0 500 150" role="img" aria-label="Illustrative market movement chart" style="width:100%;height:auto;display:block">
            <defs>
              <linearGradient id="chartFill" x1="0" y1="0" x2="0" y2="1">
                <stop offset="0%" stop-color="#25e6a3" stop-opacity=".25"/>
                <stop offset="100%" stop-color="#25e6a3" stop-opacity="0"/>
              </linearGradient>
            </defs>
            <g stroke="rgba(255,255,255,.08)" stroke-width="1">
              <path d="M0 30H500 M0 65H500 M0 100H500 M0 135H500"/>
            </g>
            <path d="M0 120 L30 105 L58 112 L85 80 L112 91 L142 60 L169 76 L198 53 L224 65 L251 40 L278 56 L306 32 L332 45 L360 24 L389 39 L415 17 L444 31 L470 12 L500 20 L500 150 L0 150Z" fill="url(#chartFill)"/>
            <path d="M0 120 L30 105 L58 112 L85 80 L112 91 L142 60 L169 76 L198 53 L224 65 L251 40 L278 56 L306 32 L332 45 L360 24 L389 39 L415 17 L444 31 L470 12 L500 20" fill="none" stroke="#25e6a3" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <p class="muted small" style="margin-top:9px">This illustration is not a live chart, price feed or trading signal.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="section" id="markets">
  <div class="container">
    <div class="section-heading">
      <span class="eyebrow">◆ Explore the markets</span>
      <h2>One place to explore <span class="gradient-text">different assets.</span></h2>
      <p>Learn about major market categories and the risks involved before deciding whether an instrument suits your goals.</p>
    </div>

    <div class="grid grid-3">
      <article class="card">
        <div class="icon-box">₿</div>
        <h3>Cryptocurrency</h3>
        <p>Explore digital assets, blockchain markets, volatility and the factors that can influence crypto prices.</p>
        <a class="btn btn-secondary btn-block" href="#faq" style="margin-top:18px">Learn more ↗</a>
      </article>

      <article class="card">
        <div class="icon-box gold">◆</div>
        <h3>Gold & Commodities</h3>
        <p>Understand precious metals and commodities, including the impact of supply, demand and economic news.</p>
        <a class="btn btn-secondary btn-block" href="#faq" style="margin-top:18px">Learn more ↗</a>
      </article>

      <article class="card">
        <div class="icon-box blue">⇄</div>
        <h3>Forex</h3>
        <p>Explore currency pairs, exchange rates, market sessions and the risks associated with leveraged trading.</p>
        <a class="btn btn-secondary btn-block" href="#faq" style="margin-top:18px">Learn more ↗</a>
      </article>

      <article class="card">
        <div class="icon-box purple">▥</div>
        <h3>Stock Indices</h3>
        <p>Discover how indices track groups of shares and reflect broader movements in equity markets.</p>
        <a class="btn btn-secondary btn-block" href="#faq" style="margin-top:18px">Learn more ↗</a>
      </article>

      <article class="card">
        <div class="icon-box blue">⌁</div>
        <h3>Technical Analysis</h3>
        <p>Learn about price charts, support and resistance, trends, indicators and risk-management concepts.</p>
        <a class="btn btn-secondary btn-block" href="#faq" style="margin-top:18px">Explore tools ↗</a>
      </article>

      <article class="card">
        <div class="icon-box gold">◎</div>
        <h3>Risk Management</h3>
        <p>Study position sizing, stop-loss planning, diversification and why protecting capital matters.</p>
        <a class="btn btn-secondary btn-block" href="#faq" style="margin-top:18px">Learn the basics ↗</a>
      </article>
    </div>
  </div>
</section>

<section class="section" id="offers">
  <div class="container">
    <div class="section-heading">
      <span class="eyebrow">◆ Opportunities</span>
      <h2>Explore trading <span class="gradient-text">resources.</span></h2>
      <p>Find learning materials and third-party services that you may want to investigate independently. Review the terms before registering or paying.</p>
    </div>

    <div class="grid grid-2">
      <article class="card" style="border-color:rgba(37,230,163,.24)">
        <div class="icon-box">✦</div>
        <span class="pill">LEARNING & DEVELOPMENT</span>
        <h3 style="font-size:1.45rem;margin-top:14px">Build your trading knowledge</h3>
        <p>Start with market fundamentals, trading psychology, strategy testing and risk controls before using real money.</p>
        <a class="btn btn-primary btn-block" href="#faq" style="margin-top:20px">Explore learning topics ↗</a>
      </article>

      <article class="card" style="border-color:rgba(255,200,87,.24)">
        <div class="icon-box gold">↗</div>
        <span class="pill" style="color:var(--gold);background:rgba(255,200,87,.1);border-color:rgba(255,200,87,.2)">THIRD-PARTY SERVICE</span>
        <h3 style="font-size:1.45rem;margin-top:14px">FundedNext</h3>
        <p>Visit the provider's website to review its current evaluation rules, fees, eligibility requirements, payout conditions and risks.</p>
        <a class="btn btn-gold btn-block" href="https://app.fundednext.com/registration" target="_blank" rel="noopener noreferrer" style="margin-top:20px">Visit FundedNext ↗</a>
        <p class="small" style="margin-top:12px">Trading Floor does not guarantee approval, funded status or payouts from this provider.</p>
      </article>
    </div>

    <div class="card" style="margin-top:20px;background:linear-gradient(110deg,rgba(86,169,255,.10),rgba(177,140,255,.08))">
      <div class="grid grid-2" style="align-items:center">
        <div>
          <span class="eyebrow">Forex · Gold · Indices</span>
          <h3 style="font-size:1.5rem">Research before you trade.</h3>
          <p>Compare fees, spreads, leverage, withdrawal rules and regulatory information before choosing a broker or trading service.</p>
        </div>
        <div style="display:flex;align-items:center;justify-content:center;gap:10px;flex-wrap:wrap">
          <span class="pill">FOREX</span>
          <span class="pill" style="color:var(--gold);background:rgba(255,200,87,.1);border-color:rgba(255,200,87,.2)">GOLD</span>
          <span class="pill" style="color:var(--blue);background:rgba(86,169,255,.1);border-color:rgba(86,169,255,.2)">INDICES</span>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="section" id="app">
  <div class="container">
    <div class="grid grid-2" style="align-items:center;gap:36px">
      <div>
        <span class="eyebrow">◆ Trading Floor App</span>
        <h2 style="font-size:clamp(2rem,5vw,3.3rem);line-height:1.1;letter-spacing:-.04em;margin-bottom:18px">
          Your trading resources.<br>
          <span class="gradient-text">Within reach.</span>
        </h2>
        <p class="muted" style="margin-bottom:22px">
          Access the Trading Floor Android application using the release link below. Only install applications from sources you trust, and review the requested permissions before proceeding.
        </p>
        <div class="grid grid-2" style="max-width:470px;gap:12px">
          <a class="btn btn-primary" href="https://github.com/kipchogedarius-cmyk/Trading-Floor-/releases/download/%23/_Trading_Floor_20108666.apk" target="_blank" rel="noopener noreferrer">Get Android App ↗</a>
          <a class="btn btn-secondary" href="https://github.com/kipchogedarius-cmyk/Trading-Floor-/releases" target="_blank" rel="noopener noreferrer">View Releases</a>
        </div>
        <p class="muted small" style="margin-top:14px">Android APK download. Your device may ask you to confirm installation from an external source.</p>
      </div>

      <div class="card" style="text-align:center;padding:34px 22px;background:radial-gradient(circle at top,rgba(37,230,163,.12),transparent 55%),var(--panel)">
        <div style="width:100px;height:100px;display:grid;place-items:center;margin:0 auto 20px;border-radius:28px;background:linear-gradient(135deg,var(--green),var(--blue));color:#06141a;font-size:2.4rem;font-weight:1000;box-shadow:0 12px 36px rgba(37,230,163,.16)">TF</div>
        <h3 style="font-size:1.45rem">Trading Floor</h3>
        <p class="muted">Market resources and trading tools</p>
        <div class="divider"></div>
        <div class="grid grid-2" style="text-align:left">
          <div>
            <span class="muted small">Platform</span>
            <p style="color:var(--text);font-weight:800">Android</p>
          </div>
          <div>
            <span class="muted small">Download source</span>
            <p style="color:var(--text);font-weight:800">GitHub Releases</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="section" id="asset-management">
  <div class="container">
    <div class="section-heading">
      <span class="eyebrow">◆ Financial awareness</span>
      <h2>Understand the risks before considering <span class="gradient-text">asset management.</span></h2>
      <p>Financial services require careful checks. Understand who controls the funds, how the service operates, and what legal protections may apply.</p>
    </div>

    <div class="grid grid-3">
      <article class="card">
        <div class="icon-box">⌕</div>
        <h3>Verify credentials</h3>
        <p>Independently check the provider's identity, registration, authorisations and regulatory status with the relevant authority.</p>
      </article>

      <article class="card">
        <div class="icon-box gold">◇</div>
        <h3>Understand the risks</h3>
        <p>Trading and investment activities can result in substantial losses. Past performance does not guarantee future results.</p>
      </article>

      <article class="card">
        <div class="icon-box blue">▤</div>
        <h3>Read the agreement</h3>
        <p>Review fees, custody arrangements, withdrawal conditions, dispute procedures and the terms governing any service.</p>
      </article>
    </div>

    <div class="notice" style="margin-top:22px">
      <strong>Important:</strong> Do not send money or cryptocurrency to an individual or wallet solely because a website displays it. Verify the recipient independently and understand whether any service is authorised to operate in your jurisdiction.
    </div>
  </div>
</section>

<section class="section" id="investors">
  <div class="container">
    <div class="section-heading">
      <span class="eyebrow">◆ Investor information</span>
      <h2>Investor <span class="gradient-text">support centre.</span></h2>
      <p>Use the contact option below to ask a question or request information. This page does not access a live investment account or verify balances, deposits or withdrawals.</p>
    </div>

    <div class="grid grid-2" style="align-items:start;gap:24px">
      <div class="card">
        <div class="icon-box purple">◈</div>
        <h3>Contact support</h3>
        <p>Send a message through WhatsApp to ask about the website, available resources or account-related enquiries.</p>
        <div class="divider"></div>
        <p class="muted small" style="margin-bottom:14px">WhatsApp contact</p>
        <a class="btn btn-primary btn-block" href="https://wa.me/254110501210" target="_blank" rel="noopener noreferrer">Message Trading Floor ↗</a>
        <p class="muted small" style="margin-top:12px">Confirm the identity of the person you contact before sharing personal or financial information.</p>
      </div>

      <div class="card">
        <div class="icon-box gold">⌑</div>
        <h3>Wallet information</h3>
        <p class="muted small" style="margin-bottom:16px">The address below is displayed as supplied for this website. Its ownership, purpose and safety have not been independently verified.</p>

        <div class="form-group">
          <label for="walletAddress">Displayed wallet address</label>
          <input
            class="form-control"
            id="walletAddress"
            type="text"
            value="0x2654fe1f759ea7c4ef010f8ceeb4d846267a2362"
            readonly
            aria-describedby="walletHelp"
          >
        </div>

        <button class="btn btn-secondary btn-block" id="copyWalletBtn" type="button">Copy wallet address</button>
        <p class="muted small" id="walletHelp" style="margin-top:12px">Always verify the network and full address independently before making any transfer. Blockchain transfers may be irreversible.</p>
        <p class="small" id="copyStatus" role="status" aria-live="polite" style="margin-top:8px"></p>
      </div>
    </div>

    <div class="card" style="margin-top:24px">
      <span class="eyebrow">Withdrawal enquiry</span>
      <h3 style="font-size:1.4rem">Send a withdrawal-related enquiry</h3>
      <p style="margin-bottom:22px">This form prepares a WhatsApp message only. It does not submit a withdrawal, confirm a balance or initiate a payment.</p>

      <form id="withdrawalForm">
        <div class="grid grid-2">
          <div class="form-group">
            <label for="customerName">Your name</label>
            <input class="form-control" id="customerName" name="customerName" type="text" maxlength="100" placeholder="Enter your name" required>
          </div>

          <div class="form-group">
            <label for="contactNumber">Contact number</label>
            <input class="form-control" id="contactNumber" name="contactNumber" type="tel" maxlength="30" placeholder="Enter your contact number" required>
          </div>

          <div class="form-group">
            <label for="withdrawalAmount">Enquiry amount</label>
            <input class="form-control" id="withdrawalAmount" name="withdrawalAmount" type="number" min="0.01" step="0.01" placeholder="Enter amount" required>
          </div>

          <div class="form-group">
            <label for="withdrawalCurrency">Currency</label>
            <select class="form-control" id="withdrawalCurrency" name="withdrawalCurrency" required>
              <option value="">Select currency</option>
              <option value="KES">KES</option>
              <option value="USD">USD</option>
              <option value="USDT">USDT</option>
              <option value="Other">Other / discuss with support</option>
            </select>
          </div>
        </div>

        <div class="form-group">
          <label for="withdrawalMessage">Message (optional)</label>
          <textarea class="form-control" id="withdrawalMessage" name="withdrawalMessage" rows="3" maxlength="500" placeholder="Describe your enquiry without sharing passwords, PINs or private keys."></textarea>
        </div>

        <button class="btn btn-primary" type="submit">Prepare WhatsApp Enquiry ↗</button>
        <p class="muted small" style="margin-top:13px">Never include account passwords, one-time codes, private keys or wallet recovery phrases in this form.</p>
      </form>
    </div>
  </div>
</section>

<section class="section" id="faq">
  <div class="container">
    <div class="section-heading">
      <span class="eyebrow">◆ Help centre</span>
      <h2>Frequently asked <span class="gradient-text">questions.</span></h2>
      <p>Open a question to read the answer.</p>
    </div>

    <div class="faq-list" style="max-width:850px">
      <details class="card" style="margin-bottom:12px;padding:0">
        <summary style="cursor:pointer;list-style:none;padding:20px 22px;display:flex;align-items:center;justify-content:space-between;gap:15px;font-weight:800">
          What is Trading Floor?
          <span aria-hidden="true" style="color:var(--green);font-size:1.3rem">+</span>
        </summary>
        <div style="padding:0 22px 20px;color:var(--muted)">
          Trading Floor is a website for exploring trading-related resources, market topics and opportunities. Information displayed on this website should not be treated as personalised financial advice.
        </div>
      </details>

      <details class="card" style="margin-bottom:12px;padding:0">
        <summary style="cursor:pointer;list-style:none;padding:20px 22px;display:flex;align-items:center;justify-content:space-between;gap:15px;font-weight:800">
          Are the market prices and charts live?
          <span aria-hidden="true" style="color:var(--green);font-size:1.3rem">+</span>
        </summary>
        <div style="padding:0 22px 20px;color:var(--muted)">
          The illustrative chart and market labels on this page are examples, not a verified live price feed. Check a reputable market data provider before making any trading decision.
        </div>
      </details>

      <details class="card" style="margin-bottom:12px;padding:0">
        <summary style="cursor:pointer;list-style:none;padding:20px 22px;display:flex;align-items:center;justify-content:space-between;gap:15px;font-weight:800">
          Does this website execute trades?
          <span aria-hidden="true" style="color:var(--green);font-size:1.3rem">+</span>
        </summary>
        <div style="padding:0 22px 20px;color:var(--muted)">
          No. The website code provided here does not connect to a broker, execute trades or place orders. The enquiry form only prepares a WhatsApp message.
        </div>
      </details>

      <details class="card" style="margin-bottom:12px;padding:0">
        <summary style="cursor:pointer;list-style:none;padding:20px 22px;display:flex;align-items:center;justify-content:space-between;gap:15px;font-weight:800">
          Does submitting the withdrawal form send money?
          <span aria-hidden="true" style="color:var(--green);font-size:1.3rem">+</span>
        </summary>
        <div style="padding:0 22px 20px;color:var(--muted)">
          No. It opens WhatsApp with a drafted enquiry. It does not verify your account, approve a withdrawal or transfer funds. You must review the message and choose whether to send it.
        </div>
      </details>

      <details class="card" style="margin-bottom:12px;padding:0">
        <summary style="cursor:pointer;list-style:none;padding:20px 22px;display:flex;align-items:center;justify-content:space-between;gap:15px;font-weight:800">
          Is trading risk-free?
          <span aria-hidden="true" style="color:var(--green);font-size:1.3rem">+</span>
        </summary>
        <div style="padding:0 22px 20px;color:var(--muted)">
          No. Forex, cryptocurrency, commodities, indices and other financial instruments can be volatile. Leverage can increase losses, and you may lose some or all of the money you commit.
        </div>
      </details>

      <details class="card" style="margin-bottom:12px;padding:0">
        <summary style="cursor:pointer;list-style:none;padding:20px 22px;display:flex;align-items:center;justify-content:space-between;gap:15px;font-weight:800">
          How do I check whether a broker or investment service is legitimate?
          <span aria-hidden="true" style="color:var(--green);font-size:1.3rem">+</span>
        </summary>
        <div style="padding:0 22px 20px;color:var(--muted)">
          Independently verify its legal identity, regulatory authorisation, fees, custody arrangements and withdrawal terms. In Kenya, consult the relevant regulator, such as the Capital Markets Authority where applicable. Do not rely solely on claims made by the provider or this website.
        </div>
      </details>

      <details class="card" style="margin-bottom:12px;padding:0">
        <summary style="cursor:pointer;list-style:none;padding:20px 22px;display:flex;align-items:center;justify-content:space-between;gap:15px;font-weight:800">
          How can I contact Trading Floor?
          <span aria-hidden="true" style="color:var(--green);font-size:1.3rem">+</span>
        </summary>
        <div style="padding:0 22px 20px;color:var(--muted)">
          Use the WhatsApp contact link in the Investor Support Centre. Verify that you are communicating with the intended recipient before sharing personal information or sending funds.
        </div>
      </details>
    </div>
  </div>
</section>

<section class="section" id="important-information" style="padding-top:20px">
  <div class="container">
    <div class="card" style="border-color:rgba(255,200,87,.28);background:linear-gradient(145deg,rgba(255,200,87,.07),rgba(18,36,58,.96))">
      <span class="eyebrow" style="color:var(--gold)">◆ Important information</span>
      <h2 style="font-size:1.7rem;margin-bottom:16px">Please read before using this website</h2>

      <div style="display:grid;gap:14px">
        <p class="muted">
          <strong style="color:var(--text)">Educational information:</strong>
          Website content is provided for general information and educational purposes. It is not personalised investment, legal, tax or financial advice.
        </p>

        <p class="muted">
          <strong style="color:var(--text)">Trading risk:</strong>
          Trading and investing involve risk. Prices may move rapidly, leverage can magnify losses, and past performance does not guarantee future results. Never trade money you cannot afford to lose.
        </p>

        <p class="muted">
          <strong style="color:var(--text)">No guaranteed returns:</strong>
          No profit, return, funding approval, investment outcome or withdrawal is guaranteed by the information on this website.
        </p>

        <p class="muted">
          <strong style="color:var(--text)">Third-party services:</strong>
          External services and links are provided for convenience. Trading Floor does not automatically endorse or control those providers. Verify their terms, fees, legitimacy and regulatory status independently.
        </p>

        <p class="muted">
          <strong style="color:var(--text)">Wallet and payments:</strong>
          Any wallet address displayed must be independently verified before use. Confirm the blockchain network and recipient. Cryptocurrency transfers may be irreversible. This website does not itself verify wallet ownership or initiate transfers.
        </p>

        <p class="muted">
          <strong style="color:var(--text)">Website functionality:</strong>
          Illustrative charts and market labels are not live data unless explicitly connected to a verified data provider. Forms on this version do not connect to an investor database, verify balances or execute transactions.
        </p>

        <p class="muted">
          <strong style="color:var(--text)">Regulatory status:</strong>
          Do not assume that Trading Floor or any associated service is licensed, registered or authorised based solely on this website. Independently verify any such claim with the relevant authority.
        </p>
      </div>
    </div>
  </div>
</section>

<footer style="padding:35px 0 25px;border-top:1px solid var(--border);background:rgba(4,12,22,.75)">
  <div class="container">
    <div class="grid grid-2" style="align-items:center;gap:22px">
      <div class="brand">
        <span class="brand-mark" aria-hidden="true">TF</span>
        <span class="brand-copy">
          <strong>TRADING FLOOR</strong>
          <span>Markets · Knowledge · Opportunity</span>
        </span>
      </div>

      <div style="display:flex;justify-content:flex-end;gap:16px;flex-wrap:wrap">
        <a class="muted small" href="#home">Home</a>
        <a class="muted small" href="#markets">Markets</a>
        <a class="muted small" href="#investors">Support</a>
        <a class="muted small" href="#faq">FAQ</a>
        <a class="muted small" href="#important-information">Important information</a>
      </div>
    </div>

    <div class="divider"></div>

    <p class="muted small">
      © <span id="currentYear"></span> Trading Floor. All rights reserved.
    </p>
    <p class="muted small" style="margin-top:7px">
      Trading involves risk. Review the important information above before using third-party services or making financial decisions.
    </p>
  </div>
</footer>

<script>
"use strict";

document.addEventListener("DOMContentLoaded", function () {
  const menuToggle = document.getElementById("menuToggle");
  const mainNav = document.getElementById("mainNav");

  if (menuToggle && mainNav) {
    menuToggle.addEventListener("click", function () {
      const isOpen = mainNav.classList.toggle("open");
      menuToggle.setAttribute("aria-expanded", String(isOpen));
      menuToggle.setAttribute(
        "aria-label",
        isOpen ? "Close navigation menu" : "Open navigation menu"
      );
      menuToggle.textContent = isOpen ? "✕" : "☰";
    });

    mainNav.querySelectorAll("a").forEach(function (link) {
      link.addEventListener("click", function () {
        mainNav.classList.remove("open");
        menuToggle.setAttribute("aria-expanded", "false");
        menuToggle.setAttribute("aria-label", "Open navigation menu");
        menuToggle.textContent = "☰";
      });
    });

    document.addEventListener("click", function (event) {
      if (
        mainNav.classList.contains("open") &&
        !mainNav.contains(event.target) &&
        !menuToggle.contains(event.target)
      ) {
        mainNav.classList.remove("open");
        menuToggle.setAttribute("aria-expanded", "false");
        menuToggle.setAttribute("aria-label", "Open navigation menu");
        menuToggle.textContent = "☰";
      }
    });
  }

  const year = document.getElementById("currentYear");
  if (year) {
    year.textContent = new Date().getFullYear();
  }

  const copyButton = document.getElementById("copyWalletBtn");
  const walletInput = document.getElementById("walletAddress");
  const copyStatus = document.getElementById("copyStatus");

  if (copyButton && walletInput) {
    copyButton.addEventListener("click", async function () {
      const address = walletInput.value.trim();

      try {
        if (navigator.clipboard && window.isSecureContext) {
          await navigator.clipboard.writeText(address);
        } else {
          walletInput.focus();
          walletInput.select();
          walletInput.setSelectionRange(0, address.length);

          const copied = document.execCommand("copy");
          if (!copied) {
            throw new Error("Copy command unavailable");
          }

          window.getSelection()?.removeAllRanges();
        }

        if (copyStatus) {
          copyStatus.textContent = "Address copied. Verify it independently before using it.";
          copyStatus.style.color = "var(--green)";
        }
      } catch (error) {
        walletInput.focus();
        walletInput.select();

        if (copyStatus) {
          copyStatus.textContent = "Automatic copy failed. The address is selected so you can copy it manually.";
          copyStatus.style.color = "var(--gold)";
        }
      }
    });
  }

  const withdrawalForm = document.getElementById("withdrawalForm");

  if (withdrawalForm) {
    withdrawalForm.addEventListener("submit", function (event) {
      event.preventDefault();

      if (!withdrawalForm.reportValidity()) {
        return;
      }

      const customerName = document.getElementById("customerName").value.trim();
      const contactNumber = document.getElementById("contactNumber").value.trim();
      const amount = document.getElementById("withdrawalAmount").value;
      const currency = document.getElementById("withdrawalCurrency").value;
      const message = document.getElementById("withdrawalMessage").value.trim();

      const text = [
        "Trading Floor enquiry",
        "",
        "Name: " + customerName,
        "Contact: " + contactNumber,
        "Enquiry amount: " + amount + " " + currency,
        "Message: " + (message || "No additional message"),
        "",
        "I understand this is an enquiry, not a confirmed withdrawal request."
      ].join("\n");

      const whatsappUrl =
        "https://wa.me/254110501210?text=" + encodeURIComponent(text);

      window.open(whatsappUrl, "_blank", "noopener,noreferrer");
    });
  }

  const quickLinks = document.querySelectorAll(".quick-sidebar a");
  const trackedSections = Array.from(quickLinks)
    .map(function (link) {
      const target = document.querySelector(link.getAttribute("href"));
      return target ? { link: link, target: target } : null;
    })
    .filter(Boolean);

  if ("IntersectionObserver" in window && trackedSections.length) {
    const observer = new IntersectionObserver(
      function (entries) {
        entries.forEach(function (entry) {
          if (!entry.isIntersecting) return;

          trackedSections.forEach(function (item) {
            const isActive = item.target === entry.target;
            item.link.classList.toggle("active", isActive);

            if (isActive) {
              item.link.setAttribute("aria-current", "location");
            } else {
              item.link.removeAttribute("aria-current");
            }
          });
        });
      },
      {
        rootMargin: "-25% 0px -55% 0px",
        threshold: 0
      }
    );

    trackedSections.forEach(function (item) {
      observer.observe(item.target);
    });
  }
});
</script>

</main>
</body>
</html>
