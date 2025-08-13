<!doctype html>

<html lang="en" class="scroll-smooth">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>AINC Media — Latest News, Breaking Stories & Analysis</title>
  <meta name="description" content="AINC Media: a clean, modern, accessible, responsive news website theme with breaking ticker, sections, dark mode, search, and article templates — in one HTML file." />
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&family=Merriweather:wght@300;400;700;900&display=swap" rel="stylesheet">
  <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 64 64'><rect width='64' height='64' rx='12' fill='%23111'/><text x='50%' y='54%' font-size='34' text-anchor='middle' fill='%23fff' font-family='Arial' font-weight='700'>A</text></svg>">
  <meta name="theme-color" content="#ffffff" id="themeMeta"/>
  <style>
    :root{
      --bg:#0b0c10; --surface:#111217; --muted:#1b1d24; --card:#151823; --text:#111317; --sub:#4b5563; --brand:#f43f5e; --brand-2:#0ea5e9; --ok:#10b981; --warn:#f59e0b; --danger:#ef4444; --ring:rgba(14,165,233,.35);
      --light-bg:#ffffff; --light-surface:#f8fafc; --light-muted:#eef2f7; --light-card:#ffffff; --light-text:#0f172a; --light-sub:#475569;
      --radius:16px; --radius-sm:12px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{margin:0; font-family:Inter, system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, Noto Sans, sans-serif; color:var(--light-text); background:var(--light-bg);}
    body.dark{color:#e5e7eb; background:var(--bg)}
    a{color:inherit; text-decoration:none}
    img{max-width:100%; display:block}
    .container{width:min(1220px, 92%); margin-inline:auto}
    .visually-hidden{position:absolute!important; width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}/* Topbar */
.topbar{display:flex; align-items:center; gap:12px; padding:8px 0; color:#475569}
.badge{padding:3px 8px; font-size:12px; border-radius:999px; background:#e5e7eb}
body.dark .badge{background:#1f2937;color:#cbd5e1}

/* Header */
header.site{position:sticky; top:0; z-index:50; backdrop-filter:saturate(180%) blur(10px); background:color-mix(in srgb, var(--light-bg) 78%, transparent)}
body.dark header.site{background:color-mix(in srgb, var(--bg) 70%, transparent)}
.masthead{display:flex; align-items:center; justify-content:space-between; padding:14px 0}
.brand{display:flex; align-items:center; gap:12px}
.logo{width:44px;height:44px;border-radius:10px;background:linear-gradient(135deg,var(--brand),var(--brand-2)); display:grid; place-items:center; color:white; font-weight:800}
.brand h1{font-family:Merriweather, serif; font-size:1.6rem; letter-spacing:.2px; margin:0}
.actions{display:flex; align-items:center; gap:10px}
.btn{display:inline-flex; align-items:center; gap:8px; padding:10px 14px; border-radius:12px; border:1px solid #e5e7eb; background:#fff; cursor:pointer}
.iconbtn{width:40px;height:40px; display:inline-grid; place-items:center; border:1px solid #e5e7eb; border-radius:12px; background:#fff}
.btn.primary{background:var(--brand); color:white; border-color:transparent}
.btn.ghost{background:transparent}
body.dark .btn, body.dark .iconbtn{background:#0f1117; border-color:#1f2937}

/* Nav */
nav.primary{border-top:1px solid #e5e7eb; border-bottom:1px solid #e5e7eb; overflow:auto; white-space:nowrap}
body.dark nav.primary{border-color:#1f2937}
nav.primary a{display:inline-flex; align-items:center; gap:8px; font-weight:600; padding:12px 14px; color:#334155}
nav.primary a.active{color:var(--brand)}
body.dark nav.primary a{color:#cbd5e1}
nav.primary .pill{background:#f1f5f9; padding:2px 8px; border-radius:40px; font-size:12px}
body.dark nav.primary .pill{background:#111827}

/* Breaking ticker */
.ticker{display:flex; gap:16px; align-items:center; padding:10px 0}
.marquee{overflow:hidden; position:relative; flex:1}
.marquee-inner{display:flex; gap:40px; position:absolute; width:max-content; animation:scroll 28s linear infinite}
@keyframes scroll{from{transform:translateX(0)} to{transform:translateX(-50%)} }
.tag{font-size:12px; padding:4px 8px; border-radius:999px; color:white; background:var(--danger)}

/* Layout */
.grid{display:grid; gap:22px}
.grid-cols-12{grid-template-columns:repeat(12,1fr)}
.col-span-8{grid-column:span 8}
.col-span-4{grid-column:span 4}
@media(max-width:1000px){.grid-cols-12{grid-template-columns:1fr}.col-span-8,.col-span-4{grid-column:1}}

/* Cards */
.card{background:var(--light-card); border:1px solid #e5e7eb; border-radius:var(--radius); overflow:hidden}
body.dark .card{background:var(--card); border-color:#1f2937}
.card .thumb{aspect-ratio:16/9; background:#e5e7eb; object-fit:cover}
body.dark .card .thumb{background:#0b0f17}
.card .p{padding:16px}
.eyebrow{font-size:12px; color:var(--brand); font-weight:700; text-transform:uppercase; letter-spacing:.8px}
.meta{display:flex; gap:12px; align-items:center; color:#64748b; font-size:12px}

/* Hero */
.hero{display:grid; grid-template-columns:2fr 1fr; gap:22px}
@media(max-width:1000px){.hero{grid-template-columns:1fr}}
.hero .lead{position:relative}
.hero .lead .overlay{position:absolute; inset:auto 0 0 0; padding:18px; background:linear-gradient(180deg, transparent, rgba(0,0,0,.72)); color:#fff}
.hero .lead h2{margin:6px 0 10px; font-family:Merriweather,serif; font-size:1.9rem; line-height:1.2}

/* Section header */
.section-head{display:flex; align-items:center; justify-content:space-between; margin:4px 6px 10px}
.section-head h3{margin:0; font-size:1.1rem}
.section-head .tabs{display:flex; gap:10px}
.chip{border:1px solid #e5e7eb; padding:6px 10px; border-radius:999px; font-size:12px; cursor:pointer}
.chip.active{background:var(--brand); border-color:var(--brand); color:white}
body.dark .chip{border-color:#1f2937}

/* Sidebar widgets */
.widget{padding:14px}
.widget h4{margin:0 0 10px}
.list{display:grid; gap:12px}
.list a{display:grid; grid-template-columns:64px 1fr; gap:12px; align-items:center}
.list img{width:64px;height:64px; object-fit:cover; border-radius:10px}

/* Footer */
footer{margin-top:28px; padding:28px 0; color:#64748b; border-top:1px solid #e5e7eb}
body.dark footer{border-color:#1f2937}
.footer-grid{display:grid; grid-template-columns:2fr repeat(4,1fr); gap:24px}
@media(max-width:900px){.footer-grid{grid-template-columns:1fr 1fr}}
@media(max-width:600px){.footer-grid{grid-template-columns:1fr}}
.footer-logo{display:flex; align-items:center; gap:12px}

/* Utilities */
.muted{color:#64748b}
.row{display:flex; gap:14px; align-items:center}
.nowrap{white-space:nowrap}
.divider{height:1px;background:#e5e7eb}
body.dark .divider{background:#1f2937}
.hide-mobile{display:block}
@media(max-width:680px){.hide-mobile{display:none}}

/* Modal */
dialog{border:none; border-radius:18px; padding:0; max-width:min(900px, 92%); background:var(--light-card)}
body.dark dialog{background:var(--card)}
dialog::backdrop{background:rgba(0,0,0,.55)}
.modal-head{display:flex; align-items:center; justify-content:space-between; padding:14px 16px; border-bottom:1px solid #e5e7eb}
body.dark .modal-head{border-color:#1f2937}
.modal-body{padding:16px}

/* Article page */
.article{display:none}
.article.active{display:block}
.article h1{font-family:Merriweather,serif; font-size:2rem; line-height:1.2}
.article .byline{color:#64748b; margin:10px 0 16px}
.article .body{font-size:1.05rem; line-height:1.7}
.article figure{margin:16px 0}
.article figcaption{font-size:12px; color:#64748b}

/* Pagination */
.pagination{display:flex; gap:8px; flex-wrap:wrap}
.page{border:1px solid #e5e7eb; border-radius:10px; padding:8px 12px}
.page.active{background:var(--brand); border-color:var(--brand); color:#fff}
body.dark .page{border-color:#1f2937}

  </style>
</head>
<body>
  <!-- Top utility bar -->
  <div class="container topbar" aria-label="Utility bar">
    <span class="badge">LIVE</span>
    <div class="row" style="gap:8px">
      <span class="nowrap"><span id="weekdayOut">—</span>, <span id="dateOut">—</span></span>
      <span class="divider" style="width:1px"></span>
      <span class="hide-mobile">Markets: <strong id="mktSensex">—</strong> • <strong id="mktNifty">—</strong></span>
    </div>
    <div style="margin-left:auto" class="row">
      <a href="#about" class="muted">About</a>
      <span class="divider" style="width:1px"></span>
      <a href="#advertise" class="muted">Advertise</a>
      <span class="divider" style="width:1px"></span>
      <a href="#contact" class="muted">Contact</a>
    </div>
  </div>  <!-- Header / Masthead -->  <header class="site">
    <div class="container masthead">
      <a class="brand" href="#" aria-label="AINC Media Home" id="homeLink">
        <div class="logo" aria-hidden="true">A</div>
        <h1>AINC Media</h1>
      </a>
      <div class="actions">
        <button class="btn ghost" id="openSearch" aria-label="Open search">🔎 Search</button>
        <button class="iconbtn" id="toggleTheme" aria-label="Toggle dark mode" title="Toggle dark mode">🌗</button>
        <button class="btn primary" id="subscribeBtn" aria-haspopup="dialog">Subscribe</button>
        <button class="iconbtn" id="menuBtn" aria-label="Open menu" title="Open menu">☰</button>
      </div>
    </div><!-- Primary Nav -->
<nav class="primary" aria-label="Primary">
  <div class="container" id="navLinks">
    <a class="active" href="#" data-section="top">Top</a>
    <a href="#" data-section="india">India</a>
    <a href="#" data-section="world">World</a>
    <a href="#" data-section="politics">Politics</a>
    <a href="#" data-section="business">Business <span class="pill">Markets</span></a>
    <a href="#" data-section="tech">Tech</a>
    <a href="#" data-section="sports">Sports</a>
    <a href="#" data-section="entertainment">Entertainment</a>
    <a href="#" data-section="health">Health</a>
    <a href="#" data-section="lifestyle">Lifestyle</a>
    <a href="#" data-section="opinion">Opinion</a>
    <a href="#" data-section="science">Science</a>
    <a href="#" data-section="education">Education</a>
    <a href="#" data-section="weather">Weather</a>
    <a href="#" data-section="photos">Photos</a>
    <a href="#" data-section="videos">Videos</a>
    <a href="#" data-section="live">Live</a>
    <a href="#" data-section="trending">Trending</a>
  </div>
</nav>

  </header>  <!-- Breaking Ticker -->  <div class="container ticker" aria-label="Breaking news ticker">
    <span class="tag" aria-hidden="true">Breaking</span>
    <div class="marquee" role="region" aria-live="polite">
      <div class="marquee-inner" id="ticker"></div>
    </div>
  </div>  <!-- Main -->  <main class="container grid grid-cols-12" style="margin-top:18px">
    <!-- Left: Content -->
    <section class="col-span-8" id="homeContent">
      <!-- Hero -->
      <div class="hero">
        <article class="lead card" id="heroLead">
          <img class="thumb" alt="Lead story image" src="https://images.unsplash.com/photo-1520607162513-77705c0f0d4a?q=80&w=1600&auto=format&fit=crop" loading="lazy" />
          <div class="overlay">
            <span class="eyebrow" id="heroCategory">Top Story</span>
            <h2 id="heroTitle">AINC Media — clean, modern, fast news theme</h2>
            <div class="meta"><span id="heroTime">Just now</span> • <span id="heroAuthor">AINC Desk</span></div>
          </div>
        </article>
        <div class="grid" style="gap:16px">
          <article class="card">
            <img class="thumb" alt="Secondary" src="https://images.unsplash.com/photo-1495020689067-958852a7765e?q=80&w=1200&auto=format&fit=crop" loading="lazy" />
            <div class="p">
              <span class="eyebrow">Business</span>
              <h3 style="margin:6px 0">Markets open mixed as investors digest earnings</h3>
              <div class="meta"><span>2h ago</span> • <span>AINC Business Desk</span></div>
            </div>
          </article>
          <article class="card">
            <img class="thumb" alt="Secondary" src="https://images.unsplash.com/photo-1516542076529-1ea3854896e1?q=80&w=1200&auto=format&fit=crop" loading="lazy" />
            <div class="p">
              <span class="eyebrow">Tech</span>
              <h3 style="margin:6px 0">AI chips race: what it means for consumers</h3>
              <div class="meta"><span>3h ago</span> • <span>Tech Desk</span></div>
            </div>
          </article>
        </div>
      </div><!-- Top Stories grid -->
  <div style="margin-top:20px">
    <div class="section-head">
      <h3>Top Stories</h3>
      <div class="tabs" role="tablist" aria-label="Top stories tabs">
        <button class="chip active" data-tab="latest" role="tab" aria-selected="true">Latest</button>
        <button class="chip" data-tab="trending" role="tab">Trending</button>
        <button class="chip" data-tab="editors" role="tab">Editor’s Picks</button>
      </div>
    </div>
    <div class="grid" style="grid-template-columns:repeat(3,1fr); gap:16px" id="topGrid">
      <!-- Cards injected by JS -->
    </div>
  </div>

  <!-- Video Strip -->
  <section style="margin-top:24px">
    <div class="section-head">
      <h3>Latest Videos</h3>
      <a class="muted" href="#" data-section="videos">See all →</a>
    </div>
    <div class="grid" style="grid-template-columns:repeat(4,1fr); gap:14px" id="videoStrip">
      <!-- Video thumbs by JS -->
    </div>
  </section>

  <!-- Newsletter CTA -->
  <section class="card" style="margin-top:24px; padding:18px">
    <div class="row" style="justify-content:space-between; align-items:center; flex-wrap:wrap; gap:12px">
      <div>
        <div class="eyebrow">Newsletter</div>
        <div style="font-weight:700; font-size:1.05rem">Get the AINC Morning Brief in your inbox</div>
        <div class="muted" style="font-size:.95rem">Daily at 7am IST • Curated headlines, no spam</div>
      </div>
      <form class="row" id="nlForm" style="gap:8px" onsubmit="event.preventDefault(); subscribe('newsletter')">
        <label class="visually-hidden" for="nlEmail">Email</label>
        <input id="nlEmail" type="email" required placeholder="you@example.com" style="padding:10px 12px; border:1px solid #e5e7eb; border-radius:12px; background:transparent; color:inherit" />
        <button class="btn primary" type="submit">Subscribe</button>
      </form>
    </div>
  </section>
</section>

<!-- Right: Sidebar -->
<aside class="col-span-4" id="sidebar">
  <section class="card widget">
    <h4>Most Read</h4>
    <div class="list" id="mostRead"></div>
  </section>
  <section class="card widget">
    <h4>Weather (Demo)</h4>
    <div class="row" style="justify-content:space-between">
      <div>
        <div class="muted">Location</div>
        <div style="font-weight:700">New Delhi</div>
      </div>
      <div style="text-align:right">
        <div style="font-size:1.6rem; font-weight:800">32°</div>
        <div class="muted">Partly Cloudy</div>
      </div>
    </div>
  </section>
  <section class="card widget">
    <h4>Markets (Demo)</h4>
    <div class="row" style="justify-content:space-between">
      <div>NIFTY 50</div>
      <div><strong>+0.32%</strong></div>
    </div>
    <div class="row" style="justify-content:space-between">
      <div>SENSEX</div>
      <div><strong>-0.11%</strong></div>
    </div>
  </section>
  <section class="card widget">
    <h4>Follow AINC</h4>
    <div class="row" style="flex-wrap:wrap">
      <a class="btn" href="#">Twitter/X</a>
      <a class="btn" href="#">Instagram</a>
      <a class="btn" href="#">YouTube</a>
      <a class="btn" href="#">Telegram</a>
    </div>
  </section>
</aside>

  </main>  <!-- Article Template (Single page view) -->  <section class="container article" id="articleView" aria-live="polite">
    <nav class="row" style="gap:8px; margin:20px 0 8px">
      <a href="#" id="backHome" class="btn">← Back</a>
      <span class="muted">You are reading</span>
    </nav>
    <article class="card" style="overflow:visible">
      <img id="articleCover" class="thumb" alt="Article cover" src=""/>
      <div class="p">
        <span class="eyebrow" id="articleCategory">Category</span>
        <h1 id="articleTitle">Title</h1>
        <div class="byline" id="articleByline">By AINC Desk • <span id="articleTime">Just now</span></div>
        <div class="body" id="articleBody"></div>
        <figure>
          <img id="articleInline" alt="Inline media" src="https://images.unsplash.com/photo-1495567720989-cebdbdd97913?q=80&w=1400&auto=format&fit=crop"/>
          <figcaption>Representative image.</figcaption>
        </figure>
        <div class="row" style="flex-wrap:wrap; gap:8px; margin-top:14px">
          <span class="badge">Share</span>
          <a class="btn" href="#">Twitter/X</a>
          <a class="btn" href="#">Facebook</a>
          <a class="btn" href="#">WhatsApp</a>
          <button class="btn" onclick="window.print()">Print</button>
        </div>
      </div>
    </article><section style="margin:24px 0">
  <div class="section-head"><h3>More from AINC</h3></div>
  <div class="grid" style="grid-template-columns:repeat(3,1fr); gap:16px" id="moreGrid"></div>
  <div class="pagination" style="margin-top:16px">
    <a class="page" href="#">« Prev</a>
    <a class="page active" href="#">1</a>
    <a class="page" href="#">2</a>
    <a class="page" href="#">3</a>
    <a class="page" href="#">Next »</a>
  </div>
</section>

  </section>  <!-- Footer -->  <footer>
    <div class="container footer-grid">
      <div>
        <div class="footer-logo">
          <div class="logo" aria-hidden="true">A</div>
          <strong>AINC Media</strong>
        </div>
        <p class="muted">Independent journalism. Clear design. Built with performance and accessibility in mind.</p>
        <p class="muted">© <span id="year"></span> AINC Media. All rights reserved.</p>
      </div>
      <div>
        <strong>Sections</strong>
        <ul style="list-style:none; padding:0; margin:10px 0">
          <li><a href="#" data-section="india">India</a></li>
          <li><a href="#" data-section="world">World</a></li>
          <li><a href="#" data-section="business">Business</a></li>
          <li><a href="#" data-section="tech">Tech</a></li>
          <li><a href="#" data-section="sports">Sports</a></li>
        </ul>
      </div>
      <div>
        <strong>Company</strong>
        <ul style="list-style:none; padding:0; margin:10px 0">
          <li><a href="#about">About</a></li>
          <li><a href="#contact">Contact</a></li>
          <li><a href="#careers">Careers</a></li>
          <li><a href="#privacy">Privacy</a></li>
          <li><a href="#terms">Terms</a></li>
        </ul>
      </div>
      <div>
        <strong>Newsletters</strong>
        <p class="muted">Daily Brief, Markets PM, Weekend Read.</p>
        <button class="btn primary" id="footerSubscribe">Subscribe</button>
      </div>
      <div>
        <strong>Apps</strong>
        <p class="muted">Get our app for iOS & Android (demo links).</p>
        <div class="row">
          <a class="btn" href="#">App Store</a>
          <a class="btn" href="#">Google Play</a>
        </div>
      </div>
    </div>
  </footer>  <!-- Search Modal -->  <dialog id="searchModal" aria-label="Search AINC">
    <div class="modal-head">
      <strong>Search AINC</strong>
      <button class="iconbtn" onclick="closeModal('searchModal')">✕</button>
    </div>
    <div class="modal-body">
      <form onsubmit="event.preventDefault()" class="row" style="gap:8px">
        <input id="searchInput" placeholder="Search articles, topics, authors…" autofocus style="flex:1; padding:12px 14px; border:1px solid #e5e7eb; border-radius:12px; background:transparent; color:inherit"/>
        <button class="btn">Clear</button>
      </form>
      <div style="margin-top:12px" id="searchResults"></div>
    </div>
  </dialog>  <!-- Subscribe Modal -->  <dialog id="subscribeModal" aria-label="Subscribe to AINC">
    <div class="modal-head">
      <strong>Subscribe</strong>
      <button class="iconbtn" onclick="closeModal('subscribeModal')">✕</button>
    </div>
    <div class="modal-body">
      <p class="muted">Support independent journalism. Choose a plan:</p>
      <div class="grid" style="grid-template-columns:repeat(3,1fr); gap:12px">
        <div class="card" style="padding:14px">
          <div class="eyebrow">Monthly</div>
          <div style="font-size:1.6rem; font-weight:800">₹99</div>
          <ul>
            <li>Ad-lite experience</li>
            <li>Newsletter access</li>
            <li>Commenting</li>
          </ul>
          <button class="btn primary" onclick="subscribe('monthly')">Continue</button>
        </div>
        <div class="card" style="padding:14px; outline:2px solid var(--brand);">
          <div class="eyebrow">Yearly (Best)</div>
          <div style="font-size:1.6rem; font-weight:800">₹899</div>
          <ul>
            <li>No ads</li>
            <li>All newsletters</li>
            <li>Download PDFs</li>
          </ul>
          <button class="btn primary" onclick="subscribe('yearly')">Continue</button>
        </div>
        <div class="card" style="padding:14px">
          <div class="eyebrow">Student</div>
          <div style="font-size:1.6rem; font-weight:800">₹49</div>
          <ul>
            <li>Ad-lite</li>
            <li>Newsletter</li>
            <li>Campus perks</li>
          </ul>
          <button class="btn primary" onclick="subscribe('student')">Continue</button>
        </div>
      </div>
    </div>
  </dialog>  <!-- Mobile Menu Modal -->  <dialog id="menuModal" aria-label="AINC Menu">
    <div class="modal-head">
      <strong>Menu</strong>
      <button class="iconbtn" onclick="closeModal('menuModal')">✕</button>
    </div>
    <div class="modal-body" id="menuBody">
      <!-- Filled by JS from nav -->
    </div>
  </dialog>  <script>
    // ---------- Sample Content Data (replace with CMS/API) ----------
    const sampleArticles = [
      {
        id: 'a1',
        title: 'Monsoon patterns shift across India: what the data says',
        category: 'India',
        author: 'AINC Weather Desk',
        time: '1h ago',
        cover: 'https://images.unsplash.com/photo-1501691223387-dd0500403074?q=80&w=1600&auto=format&fit=crop',
        body: `<p>India\'s monsoon has exhibited increased intra-seasonal variability over the last decade. We break down regional patterns, IMD data, and what it means for agriculture and cities.</p>
               <p>Experts suggest investing in drainage, water storage, and high-resolution forecasts to reduce urban flooding risks.</p>`
      },
      {
        id: 'a2',
        title: 'Rupee steadies as crude cools; IT stocks lift indices',
        category: 'Business',
        author: 'AINC Business Desk',
        time: '2h ago',
        cover: 'https://images.unsplash.com/photo-1559526324-593bc073d938?q=80&w=1600&auto=format&fit=crop',
        body: `<p>Domestic markets opened mixed but stabilized by noon as energy prices softened. IT and pharma outperformed while banks were range-bound.</p>`
      },
      {
        id: 'a3',
        title: 'Explained: The new privacy rules and what changes for users',
        category: 'Tech',
        author: 'Tech Desk',
        time: '3h ago',
        cover: 'https://images.unsplash.com/photo-1519389950473-47ba0277781c?q=80&w=1600&auto=format&fit=crop',
        body: `<p>The latest privacy framework introduces stronger data portability and clearer consent. Here\'s what companies must do to comply.</p>`
      },
      {
        id: 'a4',
        title: 'India vs SA: Bowlers shine in low-scoring thriller',
        category: 'Sports',
        author: 'Sports Desk',
        time: '30m ago',
        cover: 'https://images.unsplash.com/photo-1471295253337-3ceaaedca402?q=80&w=1600&auto=format&fit=crop',
        body: `<p>A disciplined bowling display defended a modest total as fielding made the difference in the final overs.</p>`
      },
      {
        id: 'a5',
        title: 'City\'s new Metro line opens: routes, fares and timings',
        category: 'India',
        author: 'City Desk',
        time: 'Just in',
        cover: 'https://images.unsplash.com/photo-1463595373836-6e0b0a8ee322?q=80&w=1600&auto=format&fit=crop',
        body: `<p>The much-awaited line adds 18km and 16 stations, connecting dense residential clusters with the central business district.</p>`
      },
      {
        id: 'a6',
        title: 'Opinion: Why we need more local climate action now',
        category: 'Opinion',
        author: 'Guest Column',
        time: '4h ago',
        cover: 'https://images.unsplash.com/photo-1502303756789-9accc9c86ee0?q=80&w=1600&auto=format&fit=crop',
        body: `<p>National pledges are important, but city-level execution often lags. The next five years should focus on local financing and capacity building.</p>`
      },
      {
        id: 'a7',
        title: 'World markets eye central bank signals this week',
        category: 'World',
        author: 'World Desk',
        time: '1d ago',
        cover: 'https://images.unsplash.com/photo-1552581234-26160f608093?q=80&w=1600&auto=format&fit=crop',
        body: `<p>Investors await commentary from major central banks on inflation and growth. Meanwhile, commodities remain volatile.</p>`
      },
      {
        id: 'a8',
        title: 'New study links sleep to long-term heart health',
        category: 'Health',
        author: 'Health Desk',
        time: '5h ago',
        cover: 'https://images.unsplash.com/photo-1516822003754-cca485356ecb?q=80&w=1600&auto=format&fit=crop',
        body: `<p>Seven to eight hours of quality sleep is associated with significantly lower cardiovascular risk, the study finds.</p>`
      },
      {
        id: 'a9',
        title: 'How to shoot better photos on your phone',
        category: 'Lifestyle',
        author: 'Features',
        time: '6h ago',
        cover: 'https://images.unsplash.com/photo-1494790108377-be9c29b29330?q=80&w=1600&auto=format&fit=crop',
        body: `<p>Pro tips on composition, exposure, and editing to get the most from your smartphone camera.</p>`
      },
      {
        id: 'a10',
        title: 'Gallery: Monsoon across the subcontinent',
        category: 'Photos',
        author: 'Photo Desk',
        time: '2d ago',
        cover: 'https://images.unsplash.com/photo-1500530855697-b586d89ba3ee?q=80&w=1600&auto=format&fit=crop',
        body: `<p>A visual tour through the rains: cities, villages, and landscapes transformed.</p>`
      },
    ];

    const sampleVideos = [
      {id:'v1', title:'Morning Brief: 5 stories in 5 minutes', duration:'4:32', cover:'https://images.unsplash.com/photo-1515378791036-0648a3ef77b2?q=80&w=1200&auto=format&fit=crop'},
      {id:'v2', title:'Budget 101 with the Finance Minister', duration:'9:10', cover:'https://images.unsplash.com/photo-1495567720989-cebdbdd97913?q=80&w=1200&auto=format&fit=crop'},
      {id:'v3', title:'Match highlights: India vs SA', duration:'6:51', cover:'https://images.unsplash.com/photo-1517999349371-c43520457b23?q=80&w=1200&auto=format&fit=crop'},
      {id:'v4', title:'What’s changing in global trade', duration:'7:22', cover:'https://images.unsplash.com/photo-1495020689067-958852a7765e?q=80&w=1200&auto=format&fit=crop'}
    ];

    const breaking = [
      'City\'s new Metro line opens today; expect crowds on Purple corridor',
      'Sensex trims early losses; IT, pharma advance',
      'New privacy rules notified; firms get 6 months to comply',
      'Weather alert: Heavy rain likely in coastal districts',
    ];

    // ---------- Helpers ----------
    function qs(sel, el=document){return el.querySelector(sel)}
    function qsa(sel, el=document){return [...el.querySelectorAll(sel)]}

    function setDate(){
      const now = new Date();
      const weekday = now.toLocaleDateString(undefined,{weekday:'long'});
      const date = now.toLocaleDateString(undefined,{day:'2-digit', month:'long', year:'numeric'});
      qs('#weekdayOut').textContent = weekday;
      qs('#dateOut').textContent = date;
      qs('#year').textContent = now.getFullYear();
    }

    function fillTicker(){
      const t = qs('#ticker');
      const items = breaking.concat(breaking); // duplicate for seamless loop
      t.innerHTML = items.map(s=>`<span>🗞️ ${s}</span>`).join('');
    }

    function buildTopGrid(tab='latest'){
      const grid = qs('#topGrid');
      let list = sampleArticles.slice(0,9);
      if(tab==='trending') list = sampleArticles.slice().reverse();
      if(tab==='editors') list = sampleArticles.filter(a=>['Opinion','India','Tech'].includes(a.category));
      grid.innerHTML = list.map(a=>cardHTML(a)).join('');
      attachCardClicks(grid);
    }

    function cardHTML(a){
      return `
      <article class="card" data-id="${a.id}" role="button" tabindex="0">
        <img class="thumb" alt="${a.title}" src="${a.cover}" loading="lazy"/>
        <div class="p">
          <span class="eyebrow">${a.category}</span>
          <h3 style="margin:6px 0">${a.title}</h3>
          <div class="meta"><span>${a.time}</span> • <span>${a.author}</span></div>
        </div>
      </article>`
    }

    function attachCardClicks(root=document){
      qsa('[data-id]', root).forEach(el=>{
        el.addEventListener('click',()=>openArticle(el.getAttribute('data-id')));
        el.addEventListener('keypress',(e)=>{ if(e.key==='Enter') openArticle(el.getAttribute('data-id'))});
      })
    }

    function populateSidebar(){
      const list = qs('#mostRead');
      const items = sampleArticles.slice(0,5);
      list.innerHTML = items.map(a=>`
        <a href="#" data-id="${a.id}">
          <img src="${a.cover}" alt="${a.title}" loading="lazy"/>
          <div>
            <div style="font-weight:600; line-height:1.25">${a.title}</div>
            <div class="muted" style="font-size:12px">${a.category} • ${a.time}</div>
          </div>
        </a>`).join('');
      attachCardClicks(list);
    }

    function fillVideos(){
      const strip = qs('#videoStrip');
      strip.innerHTML = sampleVideos.map(v=>`
        <a class="card" href="#">
          <img class="thumb" src="${v.cover}" alt="${v.title}" loading="lazy" />
          <div class="p row" style="justify-content:space-between">
            <div>
              <span class="eyebrow">Video</span>
              <div>${v.title}</div>
            </div>
            <span class="badge">▶ ${v.duration}</span>
          </div>
        </a>`).join('');
    }

    function openArticle(id){
      const a = sampleArticles.find(x=>x.id===id) || sampleArticles[0];
      qs('#homeContent').style.display='none';
      qs('#sidebar').style.display='none';
      const art = qs('#articleView');
      art.classList.add('active');
      qs('#articleCover').src = a.cover;
      qs('#articleTitle').textContent = a.title;
      qs('#articleCategory').textContent = a.category;
      qs('#articleByline').innerHTML = `By ${a.author} • <span id="articleTime">${a.time}</span>`;
      qs('#articleBody').innerHTML = a.body + '<p>— End —</p>';
      // more grid
      const more = sampleArticles.filter(x=>x.id!==a.id).slice(0,6);
      qs('#moreGrid').innerHTML = more.map(cardHTML).join('');
      attachCardClicks(qs('#moreGrid'));
      window.scrollTo({top:0, behavior:'smooth'});
    }

    function backHome(){
      qs('#articleView').classList.remove('active');
      qs('#homeContent').style.display='block';
      qs('#sidebar').style.display='block';
    }

    // ---------- Search ----------
    function openModal(id){ qs('#'+id).showModal(); }
    function closeModal(id){ qs('#'+id).close(); }

    function search(q){
      const res = sampleArticles.filter(a=>
        a.title.toLowerCase().includes(q) || a.category.toLowerCase().includes(q) || a.author.toLowerCase().includes(q)
      );
      return res;
    }

    function renderSearchResults(list){
      const node = qs('#searchResults');
      if(!list.length){ node.innerHTML = '<p class="muted">No results.</p>'; return; }
      node.innerHTML = '<div class="grid" style="grid-template-columns:repeat(2,1fr); gap:12px">'+ list.map(cardHTML).join('') +'</div>';
      attachCardClicks(node);
    }

    // ---------- Theme ----------
    function setTheme(mode){
      const isDark = mode==='dark';
      document.body.classList.toggle('dark', isDark);
      localStorage.setItem('ainc-theme', mode);
      qs('#themeMeta').setAttribute('content', isDark ? '#0b0c10' : '#ffffff');
    }

    // ---------- Subscribe ----------
    function subscribe(plan){
      alert(`Thanks for choosing the ${plan} plan! (Demo)`);
      closeModal('subscribeModal');
    }

    // ---------- Mobile Menu ----------
    function fillMenu(){
      const nav = qs('#navLinks');
      qs('#menuBody').innerHTML = '<div class="grid" style="grid-template-columns:1fr 1fr; gap:12px">' +
        qsa('a', nav).map(a=>`<a class="btn" href="#" data-section="${a.dataset.section||'top'}">${a.textContent}</a>`).join('') + '</div>';
    }

    // ---------- Init ----------
    function init(){
      setDate();
      fillTicker();
      buildTopGrid('latest');
      populateSidebar();
      fillVideos();
      attachCardClicks();

      // Tabs
      qsa('.chip').forEach(ch=>ch.addEventListener('click', (e)=>{
        qsa('.chip').forEach(c=>c.classList.remove('active'));
        ch.classList.add('active');
        buildTopGrid(ch.dataset.tab);
      }));

      // Search
      qs('#openSearch').addEventListener('click', ()=>{openModal('searchModal'); setTimeout(()=>qs('#searchInput').focus(),50)});
      qs('#searchModal').addEventListener('close', ()=>{qs('#searchResults').innerHTML=''; qs('#searchInput').value='';});
      qs('#searchInput').addEventListener('input', (e)=>{
        const q = e.target.value.trim().toLowerCase();
        renderSearchResults(q ? search(q) : []);
      });

      // Theme
      const saved = localStorage.getItem('ainc-theme');
      if(saved) setTheme(saved); else if(window.matchMedia('(prefers-color-scheme: dark)').matches) setTheme('dark');
      qs('#toggleTheme').addEventListener('click', ()=>{
        const isDark = document.body.classList.contains('dark');
        setTheme(isDark? 'light':'dark');
      });

      // Subscribe
      qs('#subscribeBtn').addEventListener('click', ()=>openModal('subscribeModal'));
      qs('#footerSubscribe').addEventListener('click', ()=>openModal('subscribeModal'));

      // Back
      qs('#backHome').addEventListener('click', (e)=>{e.preventDefault(); backHome();});

      // Menu
      qs('#menuBtn').addEventListener('click', ()=>{ fillMenu(); openModal('menuModal'); });

      // Nav section filters (demo: just scroll to top grid)
      qsa('[data-section]').forEach(a=>a.addEventListener('click', (e)=>{
        e.preventDefault();
        qsa('nav.primary a').forEach(x=>x.classList.remove('active'));
        const node = e.currentTarget.closest('nav')? e.currentTarget : qs(`nav.primary a[data-section="${e.currentTarget.dataset.section}"]`);
        if(node) node.classList.add('active');
        window.scrollTo({top: qs('#topGrid').getBoundingClientRect().top + window.scrollY - 100, behavior:'smooth'});
      }));
    }

    document.addEventListener('DOMContentLoaded', init);
  </script></body>
</html>
