<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>WorldNexus.cc — International News, Religion & Culture</title>
  <meta name="description" content="WorldNexus.cc — Your window into international news, religion, and culture from around the world." />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,700&family=Source+Serif+4:opsz,wght@8..60,300;8..60,400;8..60,600&family=Inter:wght@400;500;600&display=swap" rel="stylesheet" />

  <style>
    /* ========================================================
       CSS VARIABLES — Edit palette/fonts here globally
    ======================================================== */
    :root {
      --clr-bg:         #F7F4EE;        /* warm parchment base */
      --clr-surface:    #FFFFFF;
      --clr-surface-alt:#EDE9DF;        /* subtle panel tint */
      --clr-ink:        #1C1A17;        /* near-black text */
      --clr-ink-mid:    #4A463D;        /* secondary text */
      --clr-ink-light:  #8A857A;        /* captions, meta */
      --clr-accent:     #C0392B;        /* deep red — signature accent */
      --clr-accent-warm:#E8A87C;        /* warm terracotta tag color */
      --clr-accent-blue:#2A7FAF;        /* culture/cold accent */
      --clr-border:     #D9D4C7;
      --clr-news-tag:   #C0392B;
      --clr-relig-tag:  #7D6B4A;
      --clr-cult-tag:   #2A7FAF;

      --font-display:   'Playfair Display', Georgia, serif;
      --font-body:      'Source Serif 4', Georgia, serif;
      --font-ui:        'Inter', system-ui, sans-serif;

      --radius:         4px;
      --radius-lg:      10px;
      --shadow-card:    0 2px 12px rgba(28,26,23,.07);
      --shadow-hover:   0 6px 28px rgba(28,26,23,.13);
      --transition:     0.22s ease;
      --max-w:          1160px;
    }

    /* ========================================================
       RESET & BASE
    ======================================================== */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; font-size: 16px; }
    body {
      background: var(--clr-bg);
      color: var(--clr-ink);
      font-family: var(--font-body);
      line-height: 1.7;
      -webkit-font-smoothing: antialiased;
    }
    img { display: block; max-width: 100%; }
    a { color: inherit; text-decoration: none; }
    ul { list-style: none; }

    /* ========================================================
       LAYOUT UTILITIES
    ======================================================== */
    .container { width: 100%; max-width: var(--max-w); margin-inline: auto; padding-inline: 24px; }
    .sr-only { position: absolute; width: 1px; height: 1px; overflow: hidden; clip: rect(0,0,0,0); white-space: nowrap; }

    /* ========================================================
       HEADER & NAV
    ======================================================== */
    header {
      background: var(--clr-surface);
      border-bottom: 2px solid var(--clr-accent);
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: 0 2px 10px rgba(28,26,23,.06);
    }
    .header-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding-block: 14px;
      gap: 16px;
    }
    .logo {
      font-family: var(--font-display);
      font-size: 1.55rem;
      font-weight: 900;
      letter-spacing: -0.02em;
      color: var(--clr-ink);
      white-space: nowrap;
    }
    .logo span { color: var(--clr-accent); }

    /* ── Top nav pills (News / Religion / Culture) ── */
    .nav-pills {
      display: flex;
      gap: 6px;
      flex-wrap: wrap;
    }
    .nav-pill {
      font-family: var(--font-ui);
      font-size: .8rem;
      font-weight: 600;
      letter-spacing: .06em;
      text-transform: uppercase;
      padding: 7px 18px;
      border-radius: 99px;
      border: 1.5px solid var(--clr-border);
      background: transparent;
      color: var(--clr-ink-mid);
      cursor: pointer;
      transition: background var(--transition), color var(--transition), border-color var(--transition), box-shadow var(--transition);
    }
    .nav-pill:hover { border-color: var(--clr-accent); color: var(--clr-accent); }
    .nav-pill.active { background: var(--clr-accent); color: #fff; border-color: var(--clr-accent); box-shadow: 0 2px 10px rgba(192,57,43,.3); }

    /* Search bar */
    .search-wrap {
      position: relative;
      flex-shrink: 0;
    }
    .search-wrap input {
      font-family: var(--font-ui);
      font-size: .85rem;
      padding: 8px 16px 8px 38px;
      border: 1.5px solid var(--clr-border);
      border-radius: 99px;
      background: var(--clr-bg);
      color: var(--clr-ink);
      width: 210px;
      outline: none;
      transition: border-color var(--transition), box-shadow var(--transition);
    }
    .search-wrap input:focus { border-color: var(--clr-accent); box-shadow: 0 0 0 3px rgba(192,57,43,.12); }
    .search-icon {
      position: absolute;
      left: 12px;
      top: 50%;
      transform: translateY(-50%);
      color: var(--clr-ink-light);
      pointer-events: none;
    }

    /* ========================================================
       HERO
    ======================================================== */
    .hero {
      background: linear-gradient(135deg, #1C1A17 0%, #2E2923 60%, #3D2B1F 100%);
      padding: 72px 0 68px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }
    .hero::before {
      content: '';
      position: absolute;
      inset: 0;
      background: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.025'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E") repeat;
      opacity: 1;
    }
    .hero-eyebrow {
      font-family: var(--font-ui);
      font-size: .75rem;
      font-weight: 600;
      letter-spacing: .18em;
      text-transform: uppercase;
      color: var(--clr-accent-warm);
      margin-bottom: 18px;
    }
    .hero h1 {
      font-family: var(--font-display);
      font-size: clamp(2.4rem, 6vw, 4.2rem);
      font-weight: 900;
      color: #F7F4EE;
      line-height: 1.1;
      max-width: 680px;
      margin-inline: auto;
      margin-bottom: 20px;
    }
    .hero h1 em { font-style: italic; color: var(--clr-accent-warm); }
    .hero p {
      font-family: var(--font-body);
      font-size: 1.1rem;
      color: #B0AA9E;
      max-width: 520px;
      margin-inline: auto;
      margin-bottom: 36px;
    }
    .hero-stats {
      display: flex;
      justify-content: center;
      gap: 40px;
      flex-wrap: wrap;
    }
    .hero-stat { text-align: center; }
    .hero-stat strong {
      display: block;
      font-family: var(--font-display);
      font-size: 1.9rem;
      font-weight: 700;
      color: #F7F4EE;
      line-height: 1;
    }
    .hero-stat span {
      font-family: var(--font-ui);
      font-size: .72rem;
      letter-spacing: .1em;
      text-transform: uppercase;
      color: var(--clr-accent-warm);
    }

    /* ========================================================
       FILTER BAR (Articles section)
    ======================================================== */
    .section-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 14px;
      margin-bottom: 32px;
      padding-bottom: 16px;
      border-bottom: 1.5px solid var(--clr-border);
    }
    .section-title {
      font-family: var(--font-display);
      font-size: 1.6rem;
      font-weight: 700;
    }
    .filter-bar {
      display: flex;
      gap: 6px;
      flex-wrap: wrap;
    }
    .filter-btn {
      font-family: var(--font-ui);
      font-size: .78rem;
      font-weight: 600;
      letter-spacing: .05em;
      text-transform: uppercase;
      padding: 6px 16px;
      border-radius: var(--radius);
      border: 1.5px solid var(--clr-border);
      background: transparent;
      color: var(--clr-ink-mid);
      cursor: pointer;
      transition: all var(--transition);
    }
    .filter-btn:hover { border-color: var(--clr-ink-mid); color: var(--clr-ink); }
    .filter-btn.active { background: var(--clr-ink); color: var(--clr-bg); border-color: var(--clr-ink); }
    .filter-btn[data-cat="news"].active    { background: var(--clr-news-tag);  border-color: var(--clr-news-tag);  }
    .filter-btn[data-cat="religion"].active{ background: var(--clr-relig-tag); border-color: var(--clr-relig-tag); }
    .filter-btn[data-cat="culture"].active { background: var(--clr-cult-tag);  border-color: var(--clr-cult-tag);  }

    /* ========================================================
       ARTICLES SECTION
    ======================================================== */
    .articles-section { padding-block: 60px; }

    /* Grid: 3 cols on desktop, 2 on tablet, 1 on mobile */
    .articles-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 28px;
    }

    /* ── Single Article Card ── */
    .article-card {
      background: var(--clr-surface);
      border-radius: var(--radius-lg);
      overflow: hidden;
      border: 1px solid var(--clr-border);
      box-shadow: var(--shadow-card);
      display: flex;
      flex-direction: column;
      transition: transform var(--transition), box-shadow var(--transition);
      cursor: pointer;
    }
    .article-card:hover {
      transform: translateY(-5px);
      box-shadow: var(--shadow-hover);
    }

    /* Card image placeholder (use real <img> if you have one) */
    .card-img {
      width: 100%;
      aspect-ratio: 16/9;
      object-fit: cover;
      background: var(--clr-surface-alt);
    }
    .card-img-placeholder {
      width: 100%;
      aspect-ratio: 16/9;
      background: linear-gradient(135deg, var(--clr-surface-alt) 60%, var(--clr-border) 100%);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 2.5rem;
    }

    .card-body { padding: 20px 22px 24px; display: flex; flex-direction: column; flex: 1; }

    /* Category tag */
    .card-tag {
      display: inline-block;
      font-family: var(--font-ui);
      font-size: .68rem;
      font-weight: 700;
      letter-spacing: .1em;
      text-transform: uppercase;
      padding: 3px 10px;
      border-radius: 99px;
      margin-bottom: 12px;
      width: fit-content;
    }
    .tag-news     { background: rgba(192,57,43,.1);  color: var(--clr-news-tag);  }
    .tag-religion { background: rgba(125,107,74,.1); color: var(--clr-relig-tag); }
    .tag-culture  { background: rgba(42,127,175,.1); color: var(--clr-cult-tag);  }

    .card-title {
      font-family: var(--font-display);
      font-size: 1.15rem;
      font-weight: 700;
      line-height: 1.35;
      margin-bottom: 10px;
      transition: color var(--transition);
    }
    .article-card:hover .card-title { color: var(--clr-accent); }

    .card-excerpt {
      font-size: .9rem;
      color: var(--clr-ink-mid);
      line-height: 1.65;
      margin-bottom: 18px;
      flex: 1;
    }

    .card-meta {
      display: flex;
      align-items: center;
      gap: 10px;
      font-family: var(--font-ui);
      font-size: .75rem;
      color: var(--clr-ink-light);
    }
    .card-meta-dot { width: 3px; height: 3px; background: var(--clr-ink-light); border-radius: 50%; }
    .card-read-more {
      margin-top: 14px;
      font-family: var(--font-ui);
      font-size: .8rem;
      font-weight: 600;
      color: var(--clr-accent);
      display: flex;
      align-items: center;
      gap: 5px;
      transition: gap var(--transition);
    }
    .article-card:hover .card-read-more { gap: 10px; }

    /* No results message */
    .no-results {
      grid-column: 1 / -1;
      text-align: center;
      padding: 60px 20px;
      color: var(--clr-ink-light);
      font-family: var(--font-ui);
      display: none;
    }
    .no-results.visible { display: block; }

    /* ========================================================
       FEATURED ARTICLE (first card spans 2 cols)
    ======================================================== */
    .article-card.featured {
      grid-column: span 2;
      flex-direction: row;
    }
    .article-card.featured .card-img-placeholder,
    .article-card.featured .card-img {
      width: 45%;
      aspect-ratio: unset;
      min-height: 240px;
      flex-shrink: 0;
    }
    .article-card.featured .card-body { padding: 28px 28px; }
    .article-card.featured .card-title { font-size: 1.4rem; }

    /* ========================================================
       ABOUT STRIP
    ======================================================== */
    .about-strip {
      background: var(--clr-surface-alt);
      border-top: 1px solid var(--clr-border);
      border-bottom: 1px solid var(--clr-border);
      padding-block: 48px;
    }
    .about-inner {
      display: flex;
      align-items: center;
      gap: 48px;
      flex-wrap: wrap;
    }
    .about-text { flex: 1; min-width: 260px; }
    .about-text h2 { font-family: var(--font-display); font-size: 1.5rem; margin-bottom: 10px; }
    .about-text p  { font-size: .95rem; color: var(--clr-ink-mid); max-width: 520px; }
    .about-badge {
      display: flex;
      gap: 14px;
      flex-wrap: wrap;
      flex-shrink: 0;
    }
    .badge-item {
      text-align: center;
      padding: 18px 28px;
      background: var(--clr-surface);
      border: 1px solid var(--clr-border);
      border-radius: var(--radius-lg);
    }
    .badge-item strong { display: block; font-family: var(--font-display); font-size: 1.5rem; color: var(--clr-accent); }
    .badge-item span   { font-family: var(--font-ui); font-size: .7rem; text-transform: uppercase; letter-spacing: .08em; color: var(--clr-ink-light); }

    /* ========================================================
       FOOTER
    ======================================================== */
    footer {
      background: #1C1A17;
      color: #B0AA9E;
      padding-block: 40px 28px;
      font-family: var(--font-ui);
      font-size: .85rem;
    }
    .footer-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 16px;
    }
    .footer-logo { font-family: var(--font-display); font-size: 1.2rem; font-weight: 900; color: #F7F4EE; }
    .footer-logo span { color: var(--clr-accent); }
    .footer-links { display: flex; gap: 22px; }
    .footer-links a { color: #B0AA9E; transition: color var(--transition); }
    .footer-links a:hover { color: var(--clr-accent-warm); }
    .footer-copy { width: 100%; text-align: center; color: #5A564F; margin-top: 24px; font-size: .78rem; }

    /* ========================================================
       SCROLL-TO-TOP BUTTON
    ======================================================== */
    .scroll-top {
      position: fixed;
      bottom: 30px;
      right: 28px;
      width: 44px;
      height: 44px;
      background: var(--clr-accent);
      color: #fff;
      border: none;
      border-radius: 50%;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 4px 16px rgba(192,57,43,.35);
      opacity: 0;
      transform: translateY(12px);
      transition: opacity var(--transition), transform var(--transition);
      pointer-events: none;
      z-index: 200;
    }
    .scroll-top.visible { opacity: 1; transform: translateY(0); pointer-events: all; }
    .scroll-top:hover { background: #a02f24; }

    /* ========================================================
       RESPONSIVE
    ======================================================== */
    @media (max-width: 900px) {
      .articles-grid { grid-template-columns: 1fr 1fr; }
      .article-card.featured { grid-column: span 2; flex-direction: column; }
      .article-card.featured .card-img-placeholder,
      .article-card.featured .card-img { width: 100%; aspect-ratio: 16/9; min-height: unset; }
    }
    @media (max-width: 640px) {
      .articles-grid { grid-template-columns: 1fr; }
      .article-card.featured { grid-column: span 1; }
      .header-inner { flex-wrap: wrap; }
      .search-wrap input { width: 160px; }
      .hero h1 { font-size: 2rem; }
      .hero-stats { gap: 22px; }
      .about-inner { flex-direction: column; }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { transition: none !important; animation: none !important; }
    }
  </style>
</head>
<body>

  <!-- ============================================================
       HEADER — 3-option nav bar (News / Religion / Culture)
  ============================================================ -->
  <header>
    <div class="container header-inner">
      <a href="#" class="logo">World<span>Nexus</span>.cc</a>

      <!-- 3-pill navigation — clicking filters articles to that category -->
      <nav class="nav-pills" aria-label="Topic navigation">
        <button class="nav-pill" data-filter="news"     onclick="setCategory('news')">News</button>
        <button class="nav-pill" data-filter="religion" onclick="setCategory('religion')">Religion</button>
        <button class="nav-pill" data-filter="culture"  onclick="setCategory('culture')">Culture</button>
      </nav>

      <!-- Live search field -->
      <div class="search-wrap">
        <span class="search-icon" aria-hidden="true">
          <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
        </span>
        <input type="search" id="searchInput" placeholder="Search articles…" aria-label="Search articles" oninput="filterArticles()" />
      </div>
    </div>
  </header>

  <!-- ============================================================
       HERO
  ============================================================ -->
  <section class="hero" aria-label="Hero banner">
    <div class="container">
      <p class="hero-eyebrow">Your global window</p>
      <h1>The world's stories,<br /><em>all in one place</em></h1>
      <p>Unbiased coverage of international news, faith traditions, and the cultures that shape our world.</p>
      <div class="hero-stats">
        <div class="hero-stat"><strong>3</strong><span>Topics</span></div>
        <div class="hero-stat"><strong>6+</strong><span>Regions</span></div>
        <div class="hero-stat"><strong>∞</strong><span>Perspectives</span></div>
      </div>
    </div>
  </section>

  <!-- ============================================================
       ARTICLES SECTION
       ──────────────────────────────────────────────────────────
       HOW TO ADD A NEW ARTICLE:
       1. Copy one of the <article> blocks below.
       2. Change data-category to "news", "religion", or "culture".
       3. Update the emoji in .card-img-placeholder, the .card-tag
          class (tag-news / tag-religion / tag-culture), and text.
       4. Fill in title, excerpt, author, date, and read time.
       5. Paste the new block INSIDE the <div id="articlesGrid">.
       6. The first article can use class="article-card featured"
          to make it span 2 columns (remove "featured" for normal cards).
  ============================================================ -->
  <section class="articles-section" id="articles" aria-label="Articles">
    <div class="container">

      <div class="section-header">
        <h2 class="section-title">Latest Articles</h2>
        <!-- Article filter buttons (duplicate of nav pills, inline style) -->
        <div class="filter-bar" role="group" aria-label="Filter by category">
          <button class="filter-btn active" data-cat="all"      onclick="setCategory('all')">All</button>
          <button class="filter-btn"        data-cat="news"     onclick="setCategory('news')">News</button>
          <button class="filter-btn"        data-cat="religion" onclick="setCategory('religion')">Religion</button>
          <button class="filter-btn"        data-cat="culture"  onclick="setCategory('culture')">Culture</button>
        </div>
      </div>

      <!-- ╔══════════════════════════════════════════════════════╗
           ║  ARTICLE LIST — paste new <article> blocks here      ║
           ╚══════════════════════════════════════════════════════╝ -->
      <div class="articles-grid" id="articlesGrid">

        <!-- ARTICLE 1 — FEATURED (spans 2 cols) -->
        <article class="article-card featured" data-category="news" data-title="G20 Summit Reaches Historic Climate Agreement" data-excerpt="World leaders gathered in New Delhi to sign a sweeping accord pledging carbon neutrality by 2045, the most ambitious multilateral pact in a decade of climate negotiations.">
          <div class="card-img-placeholder" aria-hidden="true">🌍</div>
          <div class="card-body">
            <span class="card-tag tag-news">News</span>
            <h3 class="card-title">G20 Summit Reaches Historic Climate Agreement</h3>
            <p class="card-excerpt">World leaders gathered in New Delhi to sign a sweeping accord pledging carbon neutrality by 2045, the most ambitious multilateral pact in a decade of climate negotiations.</p>
            <div class="card-meta">
              <span>Maria Santos</span>
              <span class="card-meta-dot"></span>
              <span>June 14, 2026</span>
              <span class="card-meta-dot"></span>
              <span>5 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 2 -->
        <article class="article-card" data-category="religion" data-title="Vatican Synod Opens Dialogue on AI Ethics and Human Dignity" data-excerpt="Pope Francis convened a special synod addressing the moral responsibilities of artificial intelligence, drawing theologians and tech ethicists from over 80 nations.">
          <div class="card-img-placeholder" aria-hidden="true">⛪</div>
          <div class="card-body">
            <span class="card-tag tag-religion">Religion</span>
            <h3 class="card-title">Vatican Synod Opens Dialogue on AI Ethics and Human Dignity</h3>
            <p class="card-excerpt">Pope Francis convened a special synod addressing the moral responsibilities of artificial intelligence, drawing theologians and tech ethicists from over 80 nations.</p>
            <div class="card-meta">
              <span>James O'Brien</span>
              <span class="card-meta-dot"></span>
              <span>June 12, 2026</span>
              <span class="card-meta-dot"></span>
              <span>6 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 3 -->
        <article class="article-card" data-category="culture" data-title="Seoul's Hanbok Revival: Tradition Meets Streetwear" data-excerpt="South Korean designers are weaving centuries-old textile craft into modern streetwear collections, sparking a global fashion movement that bridges past and present.">
          <div class="card-img-placeholder" aria-hidden="true">🎎</div>
          <div class="card-body">
            <span class="card-tag tag-culture">Culture</span>
            <h3 class="card-title">Seoul's Hanbok Revival: Tradition Meets Streetwear</h3>
            <p class="card-excerpt">South Korean designers are weaving centuries-old textile craft into modern streetwear collections, sparking a global fashion movement that bridges past and present.</p>
            <div class="card-meta">
              <span>Yuna Kim</span>
              <span class="card-meta-dot"></span>
              <span>June 10, 2026</span>
              <span class="card-meta-dot"></span>
              <span>4 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 4 -->
        <article class="article-card" data-category="news" data-title="UN Security Council Adopts New Peacekeeping Framework for Sahel" data-excerpt="A landmark resolution expands mandates for peacekeeping missions in West Africa, prioritizing civilian protection amid growing instability across the Sahel region.">
          <div class="card-img-placeholder" aria-hidden="true">🕊️</div>
          <div class="card-body">
            <span class="card-tag tag-news">News</span>
            <h3 class="card-title">UN Security Council Adopts New Peacekeeping Framework for Sahel</h3>
            <p class="card-excerpt">A landmark resolution expands mandates for peacekeeping missions in West Africa, prioritizing civilian protection amid growing instability across the Sahel region.</p>
            <div class="card-meta">
              <span>Amara Diallo</span>
              <span class="card-meta-dot"></span>
              <span>June 8, 2026</span>
              <span class="card-meta-dot"></span>
              <span>5 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 5 -->
        <article class="article-card" data-category="religion" data-title="Ramadan in the Digital Age: Muslim Communities Build Virtual Ummah" data-excerpt="From livestreamed Taraweeh prayers to AI-powered Quran tutors, Islamic communities worldwide are reshaping how the holy month is observed across distances.">
          <div class="card-img-placeholder" aria-hidden="true">🌙</div>
          <div class="card-body">
            <span class="card-tag tag-religion">Religion</span>
            <h3 class="card-title">Ramadan in the Digital Age: Muslim Communities Build Virtual Ummah</h3>
            <p class="card-excerpt">From livestreamed Taraweeh prayers to AI-powered Quran tutors, Islamic communities worldwide are reshaping how the holy month is observed across distances.</p>
            <div class="card-meta">
              <span>Fatima Al-Rashid</span>
              <span class="card-meta-dot"></span>
              <span>June 5, 2026</span>
              <span class="card-meta-dot"></span>
              <span>7 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 6 -->
        <article class="article-card" data-category="culture" data-title="The Return of Analog: Why Gen Z is Embracing Vinyl and Film" data-excerpt="Across Europe and North America, a generation raised on streaming is investing in record players and disposable cameras — redefining nostalgia as a lifestyle philosophy.">
          <div class="card-img-placeholder" aria-hidden="true">🎵</div>
          <div class="card-body">
            <span class="card-tag tag-culture">Culture</span>
            <h3 class="card-title">The Return of Analog: Why Gen Z is Embracing Vinyl and Film</h3>
            <p class="card-excerpt">Across Europe and North America, a generation raised on streaming is investing in record players and disposable cameras — redefining nostalgia as a lifestyle philosophy.</p>
            <div class="card-meta">
              <span>Lena Fischer</span>
              <span class="card-meta-dot"></span>
              <span>June 2, 2026</span>
              <span class="card-meta-dot"></span>
              <span>5 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 7 -->
        <article class="article-card" data-category="news" data-title="Pacific Island Nations Form Joint Climate Resilience Fund" data-excerpt="Twelve island states in the Pacific have pooled resources into a $2.4 billion resilience fund to fortify coastlines, relocate vulnerable communities, and seed renewable infrastructure.">
          <div class="card-img-placeholder" aria-hidden="true">🏝️</div>
          <div class="card-body">
            <span class="card-tag tag-news">News</span>
            <h3 class="card-title">Pacific Island Nations Form Joint Climate Resilience Fund</h3>
            <p class="card-excerpt">Twelve island states in the Pacific have pooled resources into a $2.4 billion resilience fund to fortify coastlines, relocate vulnerable communities, and seed renewable infrastructure.</p>
            <div class="card-meta">
              <span>Keanu Makoa</span>
              <span class="card-meta-dot"></span>
              <span>May 29, 2026</span>
              <span class="card-meta-dot"></span>
              <span>4 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 8 -->
        <article class="article-card" data-category="religion" data-title="Buddhist Monasteries Across Asia Adopt Eco-Dharma Practices" data-excerpt="A growing movement within Theravāda and Mahāyāna communities sees monks and nuns integrating environmental stewardship directly into daily practice and monastic vows.">
          <div class="card-img-placeholder" aria-hidden="true">🪷</div>
          <div class="card-body">
            <span class="card-tag tag-religion">Religion</span>
            <h3 class="card-title">Buddhist Monasteries Across Asia Adopt Eco-Dharma Practices</h3>
            <p class="card-excerpt">A growing movement within Theravāda and Mahāyāna communities sees monks and nuns integrating environmental stewardship directly into daily practice and monastic vows.</p>
            <div class="card-meta">
              <span>Chandra Patel</span>
              <span class="card-meta-dot"></span>
              <span>May 25, 2026</span>
              <span class="card-meta-dot"></span>
              <span>6 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ARTICLE 9 -->
        <article class="article-card" data-category="culture" data-title="Latin America's Literary Boom 2.0: New Voices Redefining Magic Realism" data-excerpt="A new generation of writers from Colombia, Mexico, and Argentina are reinventing the magical realist tradition, weaving in digital surrealism and post-colonial critiques.">
          <div class="card-img-placeholder" aria-hidden="true">📚</div>
          <div class="card-body">
            <span class="card-tag tag-culture">Culture</span>
            <h3 class="card-title">Latin America's Literary Boom 2.0: New Voices Redefining Magic Realism</h3>
            <p class="card-excerpt">A new generation of writers from Colombia, Mexico, and Argentina are reinventing the magical realist tradition, weaving in digital surrealism and post-colonial critiques.</p>
            <div class="card-meta">
              <span>Valentina Cruz</span>
              <span class="card-meta-dot"></span>
              <span>May 20, 2026</span>
              <span class="card-meta-dot"></span>
              <span>8 min read</span>
            </div>
            <span class="card-read-more" aria-label="Read more about this article">Read more →</span>
          </div>
        </article>

        <!-- ▲▲▲ PASTE NEW ARTICLE BLOCKS ABOVE THIS LINE ▲▲▲ -->

        <!-- No-results message (shown by JS) -->
        <div class="no-results" id="noResults" aria-live="polite">
          <p style="font-size:2rem;margin-bottom:10px">🔍</p>
          <p>No articles found. Try a different search or category.</p>
        </div>

      </div><!-- end #articlesGrid -->
    </div>
  </section>

  <!-- ============================================================
       ABOUT STRIP
  ============================================================ -->
  <section class="about-strip" aria-label="About WorldNexus">
    <div class="container about-inner">
      <div class="about-text">
        <h2>Why WorldNexus?</h2>
        <p>We believe that understanding the world begins with three lenses: the <strong>events</strong> that shape it, the <strong>beliefs</strong> that sustain it, and the <strong>cultures</strong> that color it. WorldNexus.cc brings these threads together in one clean, independent space — no algorithms, no paywalls.</p>
      </div>
      <div class="about-badge">
        <div class="badge-item"><strong>3</strong><span>Categories</span></div>
        <div class="badge-item"><strong>Free</strong><span>Always</span></div>
        <div class="badge-item"><strong>Global</strong><span>Coverage</span></div>
      </div>
    </div>
  </section>

  <!-- ============================================================
       FOOTER
  ============================================================ -->
  <footer aria-label="Footer">
    <div class="container footer-inner">
      <span class="footer-logo">World<span>Nexus</span>.cc</span>
      <nav class="footer-links" aria-label="Footer navigation">
        <a href="#">About</a>
        <a href="#">Contact</a>
        <a href="#">Privacy</a>
        <a href="#articles">Articles</a>
      </nav>
    </div>
    <div class="container">
      <p class="footer-copy">© 2026 WorldNexus.cc — International News, Religion &amp; Culture. All rights reserved.</p>
    </div>
  </footer>

  <!-- Scroll-to-top button -->
  <button class="scroll-top" id="scrollTop" aria-label="Scroll to top" onclick="window.scrollTo({top:0,behavior:'smooth'})">
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><polyline points="18 15 12 9 6 15"/></svg>
  </button>

  <!-- ============================================================
       JAVASCRIPT — Filtering, Search, Scroll-to-top
  ============================================================ -->
  <script>
    /* ── State ── */
    let currentCategory = 'all';

    /* ── Grab all articles once ── */
    const grid        = document.getElementById('articlesGrid');
    const noResults   = document.getElementById('noResults');
    const searchInput = document.getElementById('searchInput');
    const scrollTopBtn= document.getElementById('scrollTop');

    /* Returns NodeList of all article cards (not the no-results div) */
    function getCards() {
      return grid.querySelectorAll('article.article-card');
    }

    /* ── Main filter function — called on category change OR search input ── */
    function filterArticles() {
      const query = searchInput.value.trim().toLowerCase();
      let visible = 0;

      getCards().forEach(card => {
        const cat     = card.dataset.category || '';
        const title   = (card.dataset.title   || '').toLowerCase();
        const excerpt = (card.dataset.excerpt || '').toLowerCase();

        const catMatch  = (currentCategory === 'all') || (cat === currentCategory);
        const textMatch = !query || title.includes(query) || excerpt.includes(query);

        if (catMatch && textMatch) {
          card.style.display = '';
          visible++;
        } else {
          card.style.display = 'none';
        }
      });

      /* Handle featured card layout: hide wide class if not visible */
      noResults.classList.toggle('visible', visible === 0);
    }

    /* ── Category setter — called by both nav pills and filter buttons ── */
    function setCategory(cat) {
      currentCategory = cat;

      /* Sync nav pills */
      document.querySelectorAll('.nav-pill').forEach(p => {
        p.classList.toggle('active', p.dataset.filter === cat);
      });

      /* Sync filter bar buttons */
      document.querySelectorAll('.filter-btn').forEach(b => {
        b.classList.toggle('active', b.dataset.cat === cat);
      });

      filterArticles();

      /* Smooth scroll to articles section */
      document.getElementById('articles').scrollIntoView({ behavior: 'smooth', block: 'start' });
    }

    /* ── Scroll-to-top visibility ── */
    window.addEventListener('scroll', () => {
      scrollTopBtn.classList.toggle('visible', window.scrollY > 400);
    }, { passive: true });

    /* ── Card click — extend this with real article routing or modal ── */
    getCards().forEach(card => {
      card.addEventListener('click', () => {
        /* Replace this alert with your navigation logic or modal open */
        alert('Article: ' + card.dataset.title + '\n\nReplace this handler with your article page/modal logic.');
      });
    });
  </script>

</body>
</html>
