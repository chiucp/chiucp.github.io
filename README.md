
<html lang="zh-TW">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Chiucp Tools</title>
  <!--
    Version : V1.0
    Date    : 2026-07-02
    Author  : chiucp w/ manus
  -->
  <style>
    /* ── Reset & Base ── */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --bg:          #f5f5f5;
      --surface:     #ffffff;
      --border:      #e0e0e0;
      --accent:      #2563eb;
      --accent-h:    #1d4ed8;
      --text-main:   #1a1a1a;
      --text-sub:    #6b7280;
      --hidden-bg:   #fef9c3;
      --hidden-border:#fde68a;
      --hidden-text: #92400e;
      --radius:      10px;
      --shadow:      0 1px 4px rgba(0,0,0,.08);
    }

    body {
      font-family: 'Segoe UI', 'PingFang TC', 'Microsoft JhengHei', sans-serif;
      background: var(--bg);
      color: var(--text-main);
      min-height: 100vh;
      padding: 2rem 1rem 4rem;
    }

    /* ── Header ── */
    header {
      text-align: center;
      margin-bottom: 2.5rem;
    }
    header h1 {
      font-size: 2rem;
      font-weight: 700;
      letter-spacing: .04em;
      color: var(--accent);
    }
    header p.subtitle {
      margin-top: .4rem;
      font-size: .9rem;
      color: var(--text-sub);
    }

    /* ── Main layout ── */
    main {
      max-width: 860px;
      margin: 0 auto;
      display: flex;
      flex-direction: column;
      gap: 2rem;
    }

    /* ── Section card ── */
    .section-card {
      background: var(--surface);
      border: 1px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow: hidden;
    }

    .section-header {
      display: flex;
      align-items: center;
      gap: .6rem;
      padding: .85rem 1.2rem;
      background: var(--bg);
      border-bottom: 1px solid var(--border);
    }
    .section-header .icon {
      font-size: 1.1rem;
    }
    .section-header h2 {
      font-size: 1rem;
      font-weight: 600;
      color: var(--text-main);
    }
    .section-header .count {
      margin-left: auto;
      font-size: .75rem;
      color: var(--text-sub);
      background: var(--border);
      border-radius: 999px;
      padding: .1rem .55rem;
    }

    /* ── Tool list ── */
    .tool-list {
      list-style: none;
    }
    .tool-list li {
      border-bottom: 1px solid var(--border);
    }
    .tool-list li:last-child {
      border-bottom: none;
    }

    .tool-link {
      display: flex;
      align-items: center;
      padding: .85rem 1.2rem;
      text-decoration: none;
      color: var(--text-main);
      transition: background .15s, color .15s;
      gap: .75rem;
    }
    .tool-link:hover {
      background: #eff6ff;
      color: var(--accent);
    }
    .tool-link .tool-name {
      font-size: .95rem;
      font-weight: 500;
    }
    .tool-link .tool-desc {
      font-size: .8rem;
      color: var(--text-sub);
      margin-left: auto;
    }
    .tool-link .arrow {
      font-size: .85rem;
      color: var(--text-sub);
      margin-left: .25rem;
      transition: transform .15s;
    }
    .tool-link:hover .arrow {
      transform: translateX(3px);
      color: var(--accent);
    }

    /* ── Hidden tools ── */
    .hidden-section .section-header {
      background: var(--hidden-bg);
      border-color: var(--hidden-border);
    }
    .hidden-section .section-header h2 {
      color: var(--hidden-text);
    }
    .hidden-section .section-header .count {
      background: var(--hidden-border);
      color: var(--hidden-text);
    }
    .hidden-section .tool-list li {
      border-color: #fde68a44;
    }
    .hidden-section .tool-link {
      background: #fffde7;
    }
    .hidden-section .tool-link:hover {
      background: #fef3c7;
      color: #b45309;
    }
    .hidden-section .tool-link:hover .arrow {
      color: #b45309;
    }

    /* ── Toggle button for hidden section ── */
    .toggle-btn {
      display: inline-flex;
      align-items: center;
      gap: .35rem;
      margin-left: auto;
      background: none;
      border: 1px solid var(--hidden-border);
      border-radius: 6px;
      padding: .2rem .65rem;
      font-size: .75rem;
      color: var(--hidden-text);
      cursor: pointer;
      transition: background .15s;
    }
    .toggle-btn:hover {
      background: var(--hidden-border);
    }

    .hidden-content {
      display: none;
    }
    .hidden-content.open {
      display: block;
    }

    /* ── Footer ── */
    footer {
      text-align: center;
      margin-top: 3rem;
      font-size: .78rem;
      color: var(--text-sub);
    }
    footer a {
      color: var(--accent);
      text-decoration: none;
    }
    footer a:hover { text-decoration: underline; }

    /* ── Responsive ── */
    @media (max-width: 540px) {
      header h1 { font-size: 1.5rem; }
      .tool-link .tool-desc { display: none; }
    }
  </style>
</head>
<body>

<!--header>
  <h1>⚙️ Chiucp Tools</h1>
  <p class="subtitle">個人工具集索引 &nbsp;|&nbsp; chiucp</p>
</header-->

<main>

  <!-- ── PCB / 電路設計 ── -->
  <div class="section-card">
    <div class="section-header">
      <span class="icon">🔌</span>
      <h2>PCB / 電路設計</h2>
      <span class="count">4</span>
    </div>
    <ul class="tool-list">
      <li>
        <a class="tool-link" href="netlist_viewer.html" target="_blank">
          <span class="tool-name">Allegro Netlist Analyze</span>
          <span class="tool-desc">網表分析工具</span>
          <span class="arrow">›</span>
        </a>
      </li>
      <li>
        <a class="tool-link" href="pcb_calculator_manus.html" target="_blank">
          <span class="tool-name">PCB 電流計算</span>
          <span class="tool-desc">走線電流承載計算</span>
          <span class="arrow">›</span>
        </a>
      </li>
      <li>
        <a class="tool-link" href="pcb_ipc2221_calculator.html" target="_blank">
          <span class="tool-name">PCB 電流計算 Pro</span>
          <span class="tool-desc">進階版電流計算</span>
          <span class="arrow">›</span>
        </a>
      </li>
      <li>
        <a class="tool-link" href="PCB_Layer_Estimator.html" target="_blank">
          <span class="tool-name">PCB 層數預估</span>
          <span class="tool-desc">板層數量評估工具</span>
          <span class="arrow">›</span>
        </a>
      </li>
    </ul>
  </div>

  <!-- ── 專案管理 ── -->
  <div class="section-card">
    <div class="section-header">
      <span class="icon">📅</span>
      <h2>專案管理</h2>
      <span class="count">1</span>
    </div>
    <ul class="tool-list">
      <li>
        <a class="tool-link" href="GCTool.html" target="_blank">
          <span class="tool-name">Gantt Chart 甘特圖工具</span>
          <span class="tool-desc">專案時程視覺化</span>
          <span class="arrow">›</span>
        </a>
      </li>
    </ul>
  </div>

  <!-- ── 座標 / 圖形 ── -->
  <div class="section-card">
    <div class="section-header">
      <span class="icon">📐</span>
      <h2>座標 / 圖形</h2>
      <span class="count">1</span>
    </div>
    <ul class="tool-list">
      <li>
        <a class="tool-link" href="pin_scatter_plot.html" target="_blank">
          <span class="tool-name">Coordinate to Pattern</span>
          <span class="tool-desc">座標轉圖形工具</span>
          <span class="arrow">›</span>
        </a>
      </li>
    </ul>
  </div>

  <!-- ── 遊戲 ── -->
  <div class="section-card">
    <div class="section-header">
      <span class="icon">🎮</span>
      <h2>遊戲</h2>
      <span class="count">1</span>
    </div>
    <ul class="tool-list">
      <li>
        <a class="tool-link" href="KingShot_Giftcode.html" target="_blank">
          <span class="tool-name">Kingshot Gift Code</span>
          <span class="tool-desc">禮包碼查詢 / 兌換</span>
          <span class="arrow">›</span>
        </a>
      </li>
    </ul>
  </div>

  <!-- ── 隱藏工具 (CHPT / 內部) ── -->
  <div class="section-card hidden-section">
    <div class="section-header">
      <span class="icon">🔒</span>
      <h2>隱藏工具（內部使用）</h2>
      <button class="toggle-btn" onclick="toggleHidden(this)" aria-expanded="false">
        <span class="btn-label">顯示</span> ▾
      </button>
    </div>
    <div class="hidden-content" id="hidden-tools">
      <ul class="tool-list">
        <li>
          <a class="tool-link" href="YTGOGO.html" target="_blank">
            <span class="tool-name">YT 播放器 for CHPT</span>
            <span class="tool-desc">YouTube 內嵌播放器</span>
            <span class="arrow">›</span>
          </a>
        </li>
        <li>
          <a class="tool-link" href="CP_LINK_v10.html" target="_blank">
            <span class="tool-name">CP 超連結 for CHPT</span>
            <span class="tool-desc">快速連結管理</span>
            <span class="arrow">›</span>
          </a>
        </li>
        <li>
          <a class="tool-link" href="z-chun_reflash.html" target="_blank">
            <span class="tool-name">自動刷新網頁 for 立群看診號</span>
            <span class="tool-desc">定時自動重新整理</span>
            <span class="arrow">›</span>
          </a>
        </li>
      </ul>
    </div>
  </div>

</main>

<footer>
  <p>V1.0 &nbsp;|&nbsp; 2026-07-02 &nbsp;|&nbsp; chiucp w/ manus</p>
</footer>

<script>
  // Version : V1.0
  // Date    : 2026-07-02
  // Author  : chiucp w/ manus

  function toggleHidden(btn) {
    const content = document.getElementById('hidden-tools');
    const label   = btn.querySelector('.btn-label');
    const isOpen  = content.classList.toggle('open');
    btn.setAttribute('aria-expanded', isOpen);
    label.textContent = isOpen ? '隱藏' : '顯示';
  }
</script>

</body>

