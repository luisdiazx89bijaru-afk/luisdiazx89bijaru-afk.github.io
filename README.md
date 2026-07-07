<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>WorldNexus.cc — World News, Religion &amp; Culture</title>
<meta name="description" content="WorldNexus.cc — a home for international news, religion, and culture reporting.">

<!-- Display serif (headlines) + body sans, loaded from Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,400;0,9..144,600;0,9..144,700;1,9..144,500&family=Source+Sans+3:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>
  /* ============================================================
     DESIGN TOKENS
     ============================================================ */
  :root{
    /* -- Palette: warm parchment "rustic ledger" with wire-service accents -- */
    --bg:            #F7F2E7;   /* parchment page background */
    --bg-panel:      #FFFDF8;   /* card / panel surface, lighter than bg */
    --bg-alt:        #EEE6D3;   /* deeper parchment for stripes / footer */
    --ink:           #2A241C;   /* warm near-black for text */
    --ink-soft:      #6B6355;   /* muted brown-grey for meta text */
    --line:          #D8CBAE;   /* hairline rule color */

    --brand:         #8A2E22;   /* oxblood red — primary brand / CTA accent */
    --brand-dark:    #6E2419;

    --cat-news:      #29455C;   /* navy — News */
    --cat-religion:  #A8792F;   /* ochre — Religion */
    --cat-culture:   #3C5B45;   /* forest green — Culture */

    --radius:        3px;
    --shadow-soft:   0 1px 2px rgba(42,36,28,0.06);
    --shadow-lift:   0 14px 28px -12px rgba(42,36,28,0.25);

    --font-display:  "Fraunces", Georgia, serif;
    --font-body:     "Source Sans 3", -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;

    --maxw: 1180px;
  }

  /* ============================================================
     RESET / BASE
     ============================================================ */
  *,*::before,*::after{ box-sizing:border-box; }
  html{ scroll-behavior:smooth; }
  body{
    margin:0;
    background:var(--bg);
    color:var(--ink);
    font-family:var(--font-body);
    font-size:16px;
    line-height:1.55;
    -webkit-font-smoothing:antialiased;
  }
  img{ max-width:100%; display:block; }
  a{ color:inherit; text-decoration:none; }
  button{ font-family:inherit; cursor:pointer; }
  .wrap{ max-width:var(--maxw); margin:0 auto; padding:0 24px; }

  @media (prefers-reduced-motion: reduce){
    html{ scroll-behavior:auto; }
    *,*::before,*::after{ animation-duration:0.001ms !important; animation-iteration-count:1 !important; transition-duration:0.001ms !important; }
  }

  /* ============================================================
     UTILITY BAR — thin strip above the masthead
     ============================================================ */
  .utility-bar{
    background:var(--ink);
    color:var(--bg);
    font-size:12px;
    letter-spacing:.04em;
  }
  .utility-bar .wrap{
    display:flex;
    justify-content:space-between;
    align-items:center;
    padding-top:8px;
    padding-bottom:8px;
    flex-wrap:wrap;
    gap:6px;
  }
  .utility-bar .tag{ opacity:.75; text-transform:uppercase; }
  #utility-date{ opacity:.9; }

  /* ============================================================
     MASTHEAD
     ============================================================ */
  .masthead{
    border-bottom:1px solid var(--line);
    background:var(--bg-panel);
  }
  .masthead .wrap{
    display:flex;
    align-items:center;
    justify-content:space-between;
    padding-top:22px;
    padding-bottom:22px;
  }
  .logo{
    font-family:var(--font-display);
    font-weight:700;
    font-size:clamp(26px, 4vw, 34px);
    letter-spacing:-0.01em;
  }
  .logo .dot{ color:var(--brand); }

  .nav{
    display:flex;
    gap:28px;
    font-size:14px;
    font-weight:600;
    text-transform:uppercase;
    letter-spacing:.06em;
  }
  .nav a{
    position:relative;
    padding:4px 0;
  }
  .nav a::after{
    content:"";
    position:absolute; left:0; right:100%; bottom:0;
    height:2px; background:var(--brand);
    transition:right .28s ease;
  }
  .nav a:hover::after{ right:0; }

  .nav-toggle{
    display:none;
    background:none; border:0;
    flex-direction:column; gap:5px;
    padding:6px;
  }
  .nav-toggle span{ width:24px; height:2px; background:var(--ink); display:block; }

  /* ============================================================
     DATELINE TICKER — signature element
     A slow rotating wire-service style dateline strip.
     ============================================================ */
  .ticker{
    background:var(--bg-alt);
    border-bottom:1px solid var(--line);
    overflow:hidden;
    height:38px;
    display:flex;
    align-items:center;
  }
  .ticker .wrap{ display:flex; align-items:center; gap:10px; }
  .ticker-label{
    font-size:11px; font-weight:700; letter-spacing:.08em; text-transform:uppercase;
    color:var(--brand); white-space:nowrap;
  }
  .ticker-item{
    font-size:13px; color:var(--ink-soft);
    font-variant-caps:small-caps;
    letter-spacing:.02em;
    opacity:0;
    transform:translateY(4px);
    transition:opacity .5s ease, transform .5s ease;
  }
  .ticker-item.show{ opacity:1; transform:translateY(0); }
  .ticker-item b{ color:var(--ink); font-weight:700; font-variant-caps:normal; }

  /* ============================================================
     HERO
     ============================================================ */
  .hero{
    padding:64px 0 48px;
    border-bottom:1px solid var(--line);
  }
  .hero-inner{
    display:grid;
    grid-template-columns:1.3fr 1fr;
    gap:48px;
    align-items:end;
  }
  .hero h1{
    font-family:var(--font-display);
    font-weight:600;
    font-size:clamp(38px, 5.6vw, 68px);
    line-height:1.02;
    letter-spacing:-0.015em;
    margin:0 0 18px;
  }
  .hero h1 em{ font-style:italic; color:var(--brand); font-weight:500; }
  .hero p.lede{
    font-size:19px;
    color:var(--ink-soft);
    max-width:52ch;
    margin:0;
  }
  .hero-side{
    border-left:1px solid var(--line);
    padding-left:32px;
  }
  .hero-side p{
    font-family:var(--font-display);
    font-style:italic;
    font-size:20px;
    color:var(--ink);
    margin:0 0 10px;
  }
  .hero-side span{ font-size:13px; color:var(--ink-soft); }

  /* ============================================================
     THREE PILLARS (News / Religion / Culture)
     ============================================================ */
  .pillars{
    padding:56px 0;
    border-bottom:1px solid var(--line);
  }
  .section-eyebrow{
    font-size:12px; font-weight:700; letter-spacing:.14em; text-transform:uppercase;
    color:var(--ink-soft);
    margin:0 0 28px;
    display:flex; align-items:center; gap:14px;
  }
  .section-eyebrow::after{
    content:""; flex:1; height:1px; background:var(--line);
  }
  .pillar-grid{
    display:grid;
    grid-template-columns:repeat(3, 1fr);
    gap:0;
    border:1px solid var(--line);
  }
  .pillar{
    padding:32px 28px;
    border-right:1px solid var(--line);
    background:var(--bg-panel);
    transition:background .25s ease, transform .25s ease;
    position:relative;
  }
  .pillar:last-child{ border-right:none; }
  .pillar:hover{
    background:var(--bg);
    transform:translateY(-4px);
  }
  .pillar .mark{
    width:34px; height:3px;
    margin-bottom:18px;
    transition:width .25s ease;
  }
  .pillar:hover .mark{ width:56px; }
  .pillar[data-pillar="news"] .mark{ background:var(--cat-news); }
  .pillar[data-pillar="religion"] .mark{ background:var(--cat-religion); }
  .pillar[data-pillar="culture"] .mark{ background:var(--cat-culture); }
  .pillar h3{
    font-family:var(--font-display);
    font-size:23px; font-weight:600;
    margin:0 0 10px;
  }
  .pillar p{
    color:var(--ink-soft);
    font-size:15px;
    margin:0;
  }

  /* ============================================================
     FILTER BAR — 3-option search/filter control
     ============================================================ */
  .filter-section{ padding:60px 0 20px; }
  .filter-bar{
    display:flex;
    align-items:center;
    gap:6px;
    flex-wrap:wrap;
    border-bottom:2px solid var(--line);
    padding-bottom:0;
    position:relative;
  }
  .filter-btn{
    background:none;
    border:none;
    padding:12px 18px;
    font-size:14px;
    font-weight:600;
    text-transform:uppercase;
    letter-spacing:.05em;
    color:var(--ink-soft);
    position:relative;
    transition:color .2s ease;
  }
  .filter-btn:hover{ color:var(--ink); }
  .filter-btn.active{ color:var(--ink); }
  .filter-underline{
    position:absolute;
    bottom:-2px; left:0;
    height:2px;
    background:var(--brand);
    transition:left .3s ease, width .3s ease;
  }
  .filter-count{
    margin-left:auto;
    font-size:13px;
    color:var(--ink-soft);
    padding-bottom:12px;
  }

  /* ============================================================
     ARTICLES GRID
     ============================================================ */
  .articles-section{ padding:36px 0 80px; }
  .article-grid{
    display:grid;
    grid-template-columns:repeat(auto-fill, minmax(300px, 1fr));
    gap:28px;
    margin-top:32px;
  }

  /*
    ------------------------------------------------------------
    HOW TO ADD A NEW ARTICLE:
    Copy the commented block below, remove the comment markers,
    paste it inside <div id="article-grid">...</div>, and edit
    the text/image/link/category. Paste new entries directly
    under the marker line so newest articles stay on top.
    data-category must be one of: news | religion | culture
    ------------------------------------------------------------

    <article class="article-card" data-category="news">
      <div class="card-media" style="background-image:url('your-image.jpg');"></div>
      <div class="card-body">
        <span class="card-cat cat-news">News</span>
        <h3><a href="your-article.html">Your Article Headline Goes Here</a></h3>
        <p>A one or two sentence summary of the article.</p>
        <div class="card-meta">
          <span>Author Name</span><span>Month Day, Year</span>
        </div>
      </div>
    </article>

  */
  .article-card{
    background:var(--bg-panel);
    border:1px solid var(--line);
    border-radius:var(--radius);
    overflow:hidden;
    transition:transform .28s ease, box-shadow .28s ease, border-color .28s ease;
    display:flex;
    flex-direction:column;
  }
  .article-card:hover{
    transform:translateY(-6px);
    box-shadow:var(--shadow-lift);
    border-color:transparent;
  }
  .card-media{
    height:170px;
    background:var(--bg-alt) center/cover no-repeat;
    border-bottom:1px solid var(--line);
  }
  .card-body{ padding:20px 22px 22px; }
  .card-cat{
    display:inline-block;
    font-size:11px;
    font-weight:700;
    letter-spacing:.06em;
    text-transform:uppercase;
    padding:3px 9px;
    border-radius:2px;
    color:#fff;
    margin-bottom:12px;
  }
  .cat-news{ background:var(--cat-news); }
  .cat-religion{ background:var(--cat-religion); }
  .cat-culture{ background:var(--cat-culture); }
  .card-body h3{
    font-family:var(--font-display);
    font-size:20px;
    font-weight:600;
    line-height:1.25;
    margin:0 0 8px;
  }
  .card-body h3 a{ transition:color .2s ease; }
  .card-body h3 a:hover{ color:var(--brand); }
  .card-body p{
    font-size:14.5px;
    color:var(--ink-soft);
    margin:0 0 14px;
  }
  .card-meta{
    display:flex; justify-content:space-between;
    font-size:12.5px; color:var(--ink-soft);
    border-top:1px solid var(--line);
    padding-top:12px;
  }

  /* Empty state — shown while there are zero articles, or zero matches */
  .empty-state{
    text-align:center;
    padding:64px 24px;
    border:1px dashed var(--line);
    border-radius:var(--radius);
    color:var(--ink-soft);
  }
  .empty-state h3{
    font-family:var(--font-display);
    font-size:24px;
    color:var(--ink);
    margin:0 0 10px;
  }
  .empty-state p{ margin:0; font-size:15px; }

  /* ============================================================
     ABOUT
     ============================================================ */
  .about{
    background:var(--bg-alt);
    border-top:1px solid var(--line);
    border-bottom:1px solid var(--line);
    padding:64px 0;
  }
  .about-inner{
    display:grid;
    grid-template-columns:1fr 1.4fr;
    gap:48px;
  }
  .about h2{
    font-family:var(--font-display);
    font-size:clamp(28px,3.4vw,38px);
    font-weight:600;
    margin:0;
  }
  .about-text p{
    color:var(--ink-soft);
    font-size:16px;
    max-width:60ch;
    margin:0 0 14px;
  }
  .about-text p:last-child{ margin-bottom:0; }

  /* ============================================================
     FOOTER
     ============================================================ */
  footer{ padding:40px 0; }
  .footer-inner{
    display:flex;
    justify-content:space-between;
    align-items:center;
    flex-wrap:wrap;
    gap:12px;
  }
  .footer-logo{
    font-family:var(--font-display);
    font-weight:700;
    font-size:18px;
  }
  .footer-logo .dot{ color:var(--brand); }
  footer .foot-meta{ font-size:13px; color:var(--ink-soft); }

  /* ============================================================
     RESPONSIVE
     ============================================================ */
  @media (max-width: 860px){
    .hero-inner{ grid-template-columns:1fr; }
    .hero-side{ border-left:none; border-top:1px solid var(--line); padding-left:0; padding-top:24px; }
    .pillar-grid{ grid-template-columns:1fr; }
    .pillar{ border-right:none; border-bottom:1px solid var(--line); }
    .pillar:last-child{ border-bottom:none; }
    .about-inner{ grid-template-columns:1fr; }
  }

  @media (max-width: 680px){
    .nav{
      display:none;
      position:absolute; top:100%; left:0; right:0;
      background:var(--bg-panel);
      border-bottom:1px solid var(--line);
      flex-direction:column; gap:0;
      padding:8px 24px 16px;
    }
    .nav.open{ display:flex; }
    .nav a{ padding:10px 0; border-bottom:1px solid var(--line); }
    .masthead .wrap{ position:relative; flex-wrap:wrap; }
    .nav-toggle{ display:flex; }
    .filter-count{ width:100%; margin-left:0; order:99; padding-top:4px; }
  }
</style>
</head>
<body>

  <!-- UTILITY BAR -->
  <div class="utility-bar">
    <div class="wrap">
      <span class="tag">Reporting the world, faithfully</span>
      <span id="utility-date"></span>
    </div>
  </div>

  <!-- MASTHEAD -->
  <header class="masthead">
    <div class="wrap">
      <a href="#top" class="logo">WorldNexus<span class="dot">.</span>cc</a>
      <button class="nav-toggle" id="navToggle" aria-label="Toggle menu">
        <span></span><span></span><span></span>
      </button>
      <nav class="nav" id="mainNav">
        <a href="#pillars">Sections</a>
        <a href="#articles">Articles</a>
        <a href="#about">About</a>
      </nav>
    </div>
  </header>

  <!-- DATELINE TICKER (signature element, rotates via JS) -->
  <div class="ticker">
    <div class="wrap">
      <span class="ticker-label">Dateline</span>
      <span class="ticker-item show" id="tickerItem"><b>JERUSALEM</b> — Reporting from the crossroads of faith and history.</span>
    </div>
  </div>

  <a id="top"></a>

  <!-- HERO -->
  <section class="hero">
    <div class="wrap hero-inner">
      <div>
        <h1>Where the world's <em>stories</em> meet.</h1>
        <p class="lede">WorldNexus.cc covers the news that moves nations, the faiths that shape them, and the culture that binds them together — reported with context, not noise.</p>
      </div>
      <div class="hero-side">
        <p>"Every border tells a story. Every story crosses a border."</p>
        <span>— The editorial line at WorldNexus</span>
      </div>
    </div>
  </section>

  <!-- THREE PILLARS -->
  <section class="pillars" id="pillars">
    <div class="wrap">
      <p class="section-eyebrow">What we cover</p>
      <div class="pillar-grid">
        <div class="pillar" data-pillar="news">
          <div class="mark"></div>
          <h3>News</h3>
          <p>Global affairs, politics, and the events reshaping the world map — explained clearly, without spin.</p>
        </div>
        <div class="pillar" data-pillar="religion">
          <div class="mark"></div>
          <h3>Religion</h3>
          <p>Faith traditions, theology, and the beliefs that guide billions — covered with nuance and respect.</p>
        </div>
        <div class="pillar" data-pillar="culture">
          <div class="mark"></div>
          <h3>Culture</h3>
          <p>Art, language, food, and tradition — the everyday texture of how people actually live.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- FILTER BAR + ARTICLES -->
  <section class="filter-section">
    <div class="wrap">
      <p class="section-eyebrow" id="articles">Latest articles</p>
      <div class="filter-bar" id="filterBar">
        <button class="filter-btn active" data-filter="all">All</button>
        <button class="filter-btn" data-filter="news">News</button>
        <button class="filter-btn" data-filter="religion">Religion</button>
        <button class="filter-btn" data-filter="culture">Culture</button>
        <span class="filter-underline" id="filterUnderline"></span>
        <span class="filter-count" id="filterCount"></span>
      </div>
    </div>
  </section>

  <section class="articles-section">
    <div class="wrap">

      <!-- ============================================================
           ARTICLE GRID
           Paste new <article class="article-card"> blocks inside this
           div (see the commented template above the grid in the CSS,
           or just copy an existing article card once you've added one).
           Newest articles should go right after the marker comment.
      ============================================================ -->
      <div class="article-grid" id="article-grid">
        <!-- ▽▽ PASTE NEW ARTICLE CARDS HERE ▽▽ -->

        <!-- △△ PASTE NEW ARTICLE CARDS ABOVE THIS LINE △△ -->
      </div>

      <!-- Shown automatically by JS whenever the grid has no matching articles -->
      <div class="empty-state" id="emptyState">
        <h3>No articles yet</h3>
        <p>This section is ready for your first story. Paste an article card into the grid to see it appear here.</p>
      </div>

    </div>
  </section>

  <!-- ABOUT -->
  <section class="about" id="about">
    <div class="wrap about-inner">
      <h2>About WorldNexus</h2>
      <div class="about-text">
        <p>WorldNexus.cc is an independent publication dedicated to three subjects that shape how people understand each other: international news, religion, and culture.</p>
        <p>We believe good reporting travels well — across borders, faiths, and traditions — and that understanding the world starts with taking it seriously.</p>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer>
    <div class="wrap footer-inner">
      <span class="footer-logo">WorldNexus<span class="dot">.</span>cc</span>
      <span class="foot-meta">&copy; <span id="year"></span> WorldNexus.cc — News, Religion &amp; Culture</span>
    </div>
  </footer>

<script>
(function(){
  "use strict";

  /* ---------- Utility bar: live date ---------- */
  var dateEl = document.getElementById('utility-date');
  var today = new Date();
  dateEl.textContent = today.toLocaleDateString('en-US', { weekday:'long', year:'numeric', month:'long', day:'numeric' });
  document.getElementById('year').textContent = today.getFullYear();

  /* ---------- Dateline ticker rotation ---------- */
  var datelines = [
    { city:"JERUSALEM", text:"Reporting from the crossroads of faith and history." },
    { city:"ROME", text:"Where ancient tradition still shapes modern belief." },
    { city:"NEW DELHI", text:"A subcontinent of languages, gods, and stories." },
    { city:"NAIROBI", text:"Watching a continent write its next chapter." },
    { city:"TOKYO", text:"Old rituals, new world, one careful lens." }
  ];
  var tickerEl = document.getElementById('tickerItem');
  var tIndex = 0;
  setInterval(function(){
    tickerEl.classList.remove('show');
    setTimeout(function(){
      tIndex = (tIndex + 1) % datelines.length;
      var d = datelines[tIndex];
      tickerEl.innerHTML = '<b>' + d.city + '</b> — ' + d.text;
      tickerEl.classList.add('show');
    }, 400);
  }, 4200);

  /* ---------- Mobile nav toggle ---------- */
  var navToggle = document.getElementById('navToggle');
  var mainNav = document.getElementById('mainNav');
  navToggle.addEventListener('click', function(){
    mainNav.classList.toggle('open');
  });
  mainNav.querySelectorAll('a').forEach(function(a){
    a.addEventListener('click', function(){ mainNav.classList.remove('open'); });
  });

  /* ---------- Article filter bar (News / Religion / Culture / All) ---------- */
  var filterBar = document.getElementById('filterBar');
  var filterBtns = filterBar.querySelectorAll('.filter-btn');
  var underline = document.getElementById('filterUnderline');
  var countEl = document.getElementById('filterCount');
  var emptyState = document.getElementById('emptyState');
  var grid = document.getElementById('article-grid');

  function moveUnderline(btn){
    underline.style.width = btn.offsetWidth + 'px';
    underline.style.left = btn.offsetLeft + 'px';
  }

  function applyFilter(filter){
    var cards = grid.querySelectorAll('.article-card');
    var visible = 0;
    cards.forEach(function(card){
      var match = (filter === 'all' || card.dataset.category === filter);
      card.style.display = match ? '' : 'none';
      if (match) visible++;
    });
    emptyState.style.display = visible === 0 ? 'block' : 'none';
    countEl.textContent = visible + (visible === 1 ? ' article' : ' articles');
  }

  filterBtns.forEach(function(btn){
    btn.addEventListener('click', function(){
      filterBtns.forEach(function(b){ b.classList.remove('active'); });
      btn.classList.add('active');
      moveUnderline(btn);
      applyFilter(btn.dataset.filter);
    });
  });

  // Initialize underline position and run the default "all" filter
  window.addEventListener('load', function(){
    moveUnderline(filterBar.querySelector('.filter-btn.active'));
    applyFilter('all');
  });
  window.addEventListener('resize', function(){
    moveUnderline(filterBar.querySelector('.filter-btn.active'));
  });

  /* ---------- Gentle scroll-reveal for hero & pillars ---------- */
  var revealTargets = document.querySelectorAll('.pillar, .hero-inner');
  if ('IntersectionObserver' in window){
    var io = new IntersectionObserver(function(entries){
      entries.forEach(function(entry){
        if (entry.isIntersecting){
          entry.target.style.opacity = 1;
          entry.target.style.transform = 'translateY(0)';
          io.unobserve(entry.target);
        }
      });
    }, { threshold:0.15 });
    revealTargets.forEach(function(el){
      el.style.opacity = 0;
      el.style.transform = 'translateY(16px)';
      el.style.transition = 'opacity .6s ease, transform .6s ease';
      io.observe(el);
    });
  }
})();
</script>
</body>
</html>
