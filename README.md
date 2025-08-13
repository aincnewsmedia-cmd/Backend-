<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>AINC Media</title>
  <style>
    :root{
      --bg: #ffffff;
      --fg: #0f172a;      /* slate-900 */
      --muted:#475569;    /* slate-600 */
      --brand:#0ea5e9;    /* sky-500 */
      --brand-600:#0284c7;/* sky-600 */
      --border:#e2e8f0;   /* slate-200 */
      --chip:#f1f5f9;     /* slate-100 */
    }
    @media (prefers-color-scheme: dark){
      :root{
        --bg:#0b1220;
        --fg:#e5e7eb;
        --muted:#94a3b8;
        --brand:#38bdf8;
        --brand-600:#0ea5e9;
        --border:#1f2937;
        --chip:#111827;
      }
    }

    *{box-sizing:border-box}
    body{margin:0;font-family: system-ui, -apple-system, Segoe UI, Roboto, Ubuntu, Cantarell, "Helvetica Neue", Arial, "Noto Sans", "Apple Color Emoji","Segoe UI Emoji"; background:var(--bg); color:var(--fg)}

    /* Header */
    .site-header{
      position:sticky; top:0; z-index:50; backdrop-filter:saturate(180%) blur(10px);
      background: color-mix(in oklab, var(--bg) 85%, transparent); border-bottom:1px solid var(--border);
    }
    .container{max-width:1200px; margin:0 auto; padding:0 16px}

    .topbar{
      display:flex; align-items:center; justify-content:space-between; gap:12px; padding:12px 0;
    }

    .brand{
      display:flex; align-items:center; gap:12px; text-decoration:none; color:inherit;
    }
    .brand-mark{
      width:40px;height:40px; border-radius:12px; display:grid; place-items:center;
      background: linear-gradient(135deg, var(--brand), var(--brand-600));
      color:#fff; font-weight:800; letter-spacing:0.5px;
      box-shadow:0 6px 16px color-mix(in oklab, var(--brand) 40%, transparent);
    }
    .brand-name{ font-weight:800; font-size:1.25rem; line-height:1 }
    .brand-tag{ display:block; font-size:.72rem; color:var(--muted); margin-top:2px }

    /* Nav */
    .nav{
      display:flex; align-items:center; gap:12px;
    }
    .nav a{
      text-decoration:none; color:var(--muted); padding:8px 10px; border-radius:10px; font-weight:600;
    }
    .nav a.active, .nav a:hover{ color:var(--fg); background:var(--chip) }

    /* Utilities (right side) */
    .utils{ display:flex; align-items:center; gap:10px }
    .search{
      display:flex; align-items:center; gap:8px; background:var(--chip); border:1px solid var(--border);
      border-radius:999px; padding:6px 10px; min-width:220px;
    }
    .search input{
      border:none; outline:none; background:transparent; color:var(--fg); width:100%;
    }
    .search button{
      border:none; background:transparent; cursor:pointer; color:var(--muted)
    }
    .cta{
      background:var(--brand); color:#fff; border:none; padding:10px 14px; border-radius:12px;
      font-weight:700; cursor:pointer;
      box-shadow:0 8px 18px color-mix(in oklab, var(--brand) 35%, transparent);
    }
    .cta:active{ transform:translateY(1px) }
    .menu-btn{
      display:none; border:1px solid var(--border); background:var(--chip); border-radius:12px; padding:8px 10px; cursor:pointer
    }

    /* Secondary nav (sections) */
    .sections{
      border-top:1px solid var(--border);
      display:flex; gap:6px; padding:8px 0; overflow:auto; scrollbar-width:none;
    }
    .sections::-webkit-scrollbar{ display:none }
    .chip{
      white-space:nowrap; padding:8px 12px; border:1px solid var(--border); background:var(--chip);
      border-radius:999px; text-decoration:none; color:var(--muted); font-weight:600;
    }
    .chip:hover, .chip.active{ color:var(--fg) }

    /* Mobile */
    @media (max-width: 900px){
      .nav{ display:none }
      .menu-btn{ display:inline-flex; align-items:center; gap:6px }
      .search{ display:none }
      .brand-name{ font-size:1.05rem }
      .brand-mark{ width:36px;height:36px }
      .drawer{ display:none; border-top:1px solid var(--border); padding:10px 0 }
      .drawer.open{ display:block }
      .drawer .search{ display:flex; margin:10px 0 }
      .drawer .nav{ display:flex; flex-direction:column; align-items:stretch }
      .drawer .nav a{ padding:12px; border-radius:10px }
    }
    /* Reduce motion */
    @media (prefers-reduced-motion: no-preference){
      .drawer{ transition: height .25s ease }
    }
    /* Visually hidden for a11y */
    .sr-only{ position:absolute; width:1px; height:1px; padding:0; margin:-1px; overflow:hidden; clip:rect(0,0,0,0); border:0 }
  </style>
</head>
<body>

  <header class="site-header" role="banner">
    <div class="container">

      <!-- Top bar -->
      <div class="topbar">
        <a href="/" class="brand" aria-label="AINC Media home">
          <div class="brand-mark" aria-hidden="true">A</div>
          <div>
            <span class="brand-name">AINC Media</span>
            <small class="brand-tag">News • Analysis • Narratives</small>
          </div>
        </a>

        <nav class="nav" aria-label="Primary">
          <a href="#" class="active">Home</a>
          <a href="#">India</a>
          <a href="#">World</a>
          <a href="#">Politics</a>
          <a href="#">Business</a>
          <a href="#">Tech</a>
          <a href="#">Sports</a>
          <a href="#">Entertainment</a>
          <a href="#">Opinion</a>
        </nav>

        <div class="utils">
          <form class="search" role="search" aria-label="Site search">
            <input type="search" name="q" placeholder="Search AINC Media…" aria-label="Search" />
            <button type="submit" title="Search" aria-label="Search">
              🔎
            </button>
          </form>
          <button class="cta">Subscribe</button>
          <button class="menu-btn" id="menuBtn" aria-expanded="false" aria-controls="mobileDrawer" aria-label="Open menu">☰</button>
        </div>
      </div>

      <!-- Mobile drawer -->
      <div id="mobileDrawer" class="drawer" hidden>
        <form class="search" role="search" aria-label="Mobile site search">
          <input type="search" name="q" placeholder="Search AINC Media…" aria-label="Search" />
          <button type="submit" title="Search" aria-label="Search">🔎</button>
        </form>
        <nav class="nav" aria-label="Mobile primary">
          <a href="#" class="active">Home</a>
          <a href="#">India</a>
          <a href="#">World</a>
          <a href="#">Politics</a>
          <a href="#">Business</a>
          <a href="#">Tech</a>
          <a href="#">Sports</a>
          <a href="#">Entertainment</a>
          <a href="#">Opinion</a>
        </nav>
      </div>

      <!-- Section chips -->
      <div class="sections" aria-label="Trending sections">
        <a class="chip active" href="#">Top Stories</a>
        <a class="chip" href="#">Elections 2025</a>
        <a class="chip" href="#">Market Live</a>
        <a class="chip" href="#">Explainers</a>
        <a class="chip" href="#">Fact Check</a>
        <a class="chip" href="#">Science</a>
        <a class="chip" href="#">Lifestyle</a>
        <a class="chip" href="#">Podcasts</a>
        <a class="chip" href="#">Videos</a>
      </div>

    </div>
  </header>

  <main class="container" style="padding:24px 16px">
    <h1 class="sr-only">AINC Media</h1>
    <p>Page content goes here…</p>
  </main>

  <script>
    // Mobile menu toggle
    const btn = document.getElementById('menuBtn');
    const drawer = document.getElementById('mobileDrawer');

    function setOpen(open){
      drawer.hidden = !open;
      drawer.classList.toggle('open', open);
      btn.setAttribute('aria-expanded', String(open));
    }

    btn?.addEventListener('click', () => {
      const open = btn.getAttribute('aria-expanded') === 'true';
      setOpen(!open);
    });

    // Basic search handler (prevent empty submits)
    document.querySelectorAll('form[role="search"]').forEach(form=>{
      form.addEventListener('submit', (e)=>{
        const q = form.querySelector('input[name="q"]').value.trim();
        if(!q){ e.preventDefault(); alert('Type something to search.'); return; }
        // Replace with your search route:
        // window.location.href = `/search?q=${encodeURIComponent(q)}`;
        e.preventDefault();
        console.log('Search for:', q);
      });
    });
  </script>
</body>
</html>