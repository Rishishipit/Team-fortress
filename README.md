<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Fortress Protocol — Cybersecurity, Privacy &amp; Digital Resilience Platform v1.2</title>
<style>
  
    /*--live-background-->*/
    body::before{
        content: "";
        position: fixed;
        inset: 0;
        background: rgba(0,0,0,.45);
        z-index: -1;
    }
    #bg-video{
    position:fixed;
    top:0;
    left:0;
    height:100%;
    inset:0;
    width:100%;
    object-fit:cover;
    z-index:-2;
    pointer-events: none;
    background:transparent;
    filter: brightness(2);

    object-position:right center;

    }
   .sidebar,.dashboard,.ai-assistant-widget{
    position:relative;
    z-index:1;
    }
    .card{
        background: rgba(18,24,38,.55);
        backdrop-filter: blur(15px);
        border:1px solid rgba(255,255,255,.08);
        border-radius: 18px;
        box-shadow:0 0 20px rgba(0,180,255,.12);
    }
    .status{
        width:10px;
        height:10px;
        background: #00ff66;
        border-radius:50%;
        box-shadow:0 0 15px #00ff66;
    }
    /*original code*/
  :root {
    --bg-base: #060911;
    --bg-surface: #0f1520;
    --bg-surface-hover: #17202f;
    --bg-card: #111827;
    --brand-primary: #2563eb;
    --brand-primary-hover: #1d4ed8;
    --brand-accent: #38bdf8;
    --status-critical: #ef4444;
    --status-warning: #f59e0b;
    --status-success: #10b981;
    --status-info: #3b82f6;
    --text-main: #f1f5f9;
    --text-muted: #94a3b8;
    --text-dark: #5b6b85;
    --border-color: #1e293b;
    --border-focus: #3b82f6;
    --mono: 'JetBrains Mono', 'Consolas', 'Courier New', monospace;
    --shadow-sm: 0 1px 2px 0 rgba(0,0,0,.25);
    --shadow-md: 0 4px 6px -1px rgba(0,0,0,.35), 0 2px 4px -1px rgba(0,0,0,.2);
    --shadow-lg: 0 10px 30px -5px rgba(0,0,0,.55);
  }

  * { margin:0; padding:0; box-sizing:border-box; font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif; }
  html { scroll-behavior:smooth; }
  body { background-color:var(--bg-base); color:var(--text-main); display:flex; min-height:100vh; overflow-x:hidden; font-size:14px; }
  ::selection { background: rgba(56,189,248,.3); }
  ::-webkit-scrollbar { width:8px; height:8px; }
  ::-webkit-scrollbar-track { background:transparent; }
  ::-webkit-scrollbar-thumb { background:#233047; border-radius:8px; }
  ::-webkit-scrollbar-thumb:hover { background:#2c3c59; }
  a:focus-visible, button:focus-visible, input:focus-visible, textarea:focus-visible, select:focus-visible {
    outline: 2px solid var(--brand-accent); outline-offset: 2px;
  }

  /* ---------- Live network wallpaper (signature element) ---------- */
  .bg-video { position:fixed; inset:0; z-index:-6; width:100%; height:100%; object-fit:cover; filter: saturate(1.15) brightness(.5) contrast(1.05); }
  .bg-layer { position:fixed; inset:0; z-index:-4; background:
      radial-gradient(ellipse 80% 60% at 15% 0%, rgba(37,99,235,.22), transparent 60%),
      radial-gradient(ellipse 60% 55% at 100% 100%, rgba(56,189,248,.16), transparent 60%),
      radial-gradient(ellipse 50% 40% at 80% 0%, rgba(16,185,129,.08), transparent 60%),
      rgba(6,9,17,.68);
  }
  .bg-grid { position:fixed; inset:0; z-index:-3; opacity:.28;
      background-image: linear-gradient(rgba(56,189,248,.05) 1px, transparent 1px), linear-gradient(90deg, rgba(56,189,248,.05) 1px, transparent 1px);
      background-size: 42px 42px;
      mask-image: radial-gradient(ellipse 70% 70% at 50% 20%, black 20%, transparent 75%);
  }
  #bg-canvas { position:fixed; inset:0; z-index:-2; width:100%; height:100%; display:block; pointer-events:none; }
  .bg-sweep { position:fixed; top:-25%; left:-25%; width:150%; height:150%; z-index:-1; pointer-events:none;
      background: conic-gradient(from 0deg, transparent 0deg, rgba(56,189,248,.05) 12deg, transparent 45deg, transparent 360deg);
      animation: sweep 14s linear infinite; opacity:.5; mix-blend-mode:screen;
  }
  .bg-vignette { position:fixed; inset:0; z-index:-1; pointer-events:none; background: radial-gradient(ellipse 90% 80% at 50% 40%, transparent 30%, rgba(6,9,17,.68) 100%); }
  @keyframes sweep { to { transform: rotate(360deg); } }
  @media (prefers-reduced-motion: reduce) { .bg-sweep { animation:none; } #bg-canvas { display:none; } .bg-video { display:none; } }

  .card, .glass { background: rgba(17,24,39,.6); backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px); border:1px solid rgba(255,255,255,.06); }
  .status-dot { width:9px; height:9px; background:var(--status-success); border-radius:50%; box-shadow:0 0 12px var(--status-success); flex-shrink:0; }

  /* ---------- Brand mark (now lives in the top header) ---------- */
  .brand-logo { width:32px; height:32px; background:linear-gradient(135deg,var(--brand-primary),var(--brand-accent)); border-radius:9px; display:flex; align-items:center; justify-content:center; color:#fff; font-weight:900; font-size:.9rem; box-shadow:0 0 18px rgba(56,189,248,.4); position:relative; flex-shrink:0; }
  .brand-logo::after { content:""; position:absolute; inset:-4px; border-radius:13px; border:1px solid rgba(56,189,248,.35); animation:logoPulse 2.6s ease-in-out infinite; }
  @keyframes logoPulse { 0%,100%{ opacity:.6; transform:scale(1); } 50%{ opacity:0; transform:scale(1.18); } }

  .sys-status { margin-top:auto; padding:.85rem .9rem; background:rgba(0,0,0,.25); border-top:1px solid var(--border-color); }
  .metric-row { margin-bottom:.6rem; }
  .metric-row:last-child { margin-bottom:0; }
  .metric-label { display:flex; justify-content:space-between; font-size:.62rem; color:var(--text-muted); margin-bottom:.25rem; }
  .progress-bg { height:4px; background:var(--border-color); border-radius:2px; overflow:hidden; }
  .progress-fill { height:100%; background:var(--brand-primary); transition:width .5s ease; border-radius:2px; }

  /* ---------- Main layout ---------- */
  .dashboard { flex:1; display:flex; flex-direction:column; overflow-y:auto; padding-bottom:60px; min-width:0; }
  .top-header { height:64px; background:rgba(15,21,32,.75); backdrop-filter:blur(10px); border-bottom:1px solid var(--border-color); display:flex; align-items:center; justify-content:space-between; padding:0 2rem; position:sticky; top:0; z-index:10; }
  .header-title h1 { font-size:1.05rem; font-weight:650; color:#fff; display:flex; align-items:center; gap:.6rem; }
  .header-title h2 { font-size:.73rem; color:var(--text-muted); font-weight:400; margin-top:1px; }
  .header-actions { display:flex; align-items:center; gap:.9rem; }
  .status-indicator { display:flex; align-items:center; gap:.5rem; padding:.35rem .75rem; background:rgba(16,185,129,.1); border:1px solid rgba(16,185,129,.22); border-radius:20px; color:var(--status-success); font-size:.7rem; font-weight:700; letter-spacing:.3px; }
  .indicator-dot { width:6px; height:6px; background:var(--status-success); border-radius:50%; box-shadow:0 0 8px var(--status-success); }
  .clock { font-family:var(--mono); font-size:.75rem; color:var(--text-muted); min-width:150px; text-align:right; }
  .main-container { padding:1.75rem 2rem; max-width:1400px; width:100%; margin:0 auto; }

  /* ---------- Profile menu (fancy header menu) ---------- */
  .profile-menu { position:relative; }
  .profile-trigger { display:flex; align-items:center; gap:.55rem; background:rgba(255,255,255,.03); border:1px solid var(--border-color); padding:.3rem .6rem .3rem .3rem; border-radius:24px; cursor:pointer; transition:.15s ease; }
  .profile-trigger:hover { background:var(--bg-surface-hover); border-color:#2a3a56; }
  .profile-avatar { width:30px; height:30px; border-radius:50%; background:linear-gradient(135deg,var(--brand-accent),var(--brand-primary)); display:flex; align-items:center; justify-content:center; font-size:.68rem; font-weight:800; color:#fff; flex-shrink:0; box-shadow:0 0 10px rgba(56,189,248,.35); }
  .profile-avatar.lg { width:38px; height:38px; font-size:.8rem; }
  .profile-info { display:flex; flex-direction:column; align-items:flex-start; line-height:1.25; }
  .profile-name { font-size:.76rem; font-weight:650; color:#fff; }
  .profile-role { font-size:.63rem; color:var(--text-dark); }
  .profile-caret { font-size:.6rem; color:var(--text-dark); transition:transform .2s ease; }
  .profile-menu.open .profile-caret { transform:rotate(180deg); }
  .profile-dropdown { position:absolute; top:calc(100% + 10px); right:0; width:230px; background:var(--bg-card); border:1px solid var(--border-color); border-radius:12px; box-shadow:var(--shadow-lg); padding:.5rem; opacity:0; visibility:hidden; transform:translateY(-6px); transition: opacity .18s ease, transform .18s ease, visibility .18s; z-index:50; }
  .profile-menu.open .profile-dropdown { opacity:1; visibility:visible; transform:translateY(0); }
  .profile-dropdown-head { display:flex; align-items:center; gap:.6rem; padding:.5rem .6rem .75rem; border-bottom:1px solid var(--border-color); margin-bottom:.4rem; }
  .profile-item { display:flex; align-items:center; gap:.55rem; padding:.55rem .6rem; border-radius:7px; font-size:.78rem; color:var(--text-muted); text-decoration:none; cursor:pointer; transition:.15s ease; }
  .profile-item:hover { background:var(--bg-surface-hover); color:#fff; }
  .profile-item.danger:hover { background:rgba(239,68,68,.1); color:var(--status-critical); }
  .profile-divider { height:1px; background:var(--border-color); margin:.4rem 0; }
  .avatar-stack { display:flex; align-items:center; }
  .avatar-stack .stack-av { width:26px; height:26px; font-size:.62rem; border:2px solid var(--bg-surface); margin-left:-8px; box-shadow:0 0 8px rgba(0,0,0,.35); }
  .avatar-stack .stack-av:first-child { margin-left:0; }
  .profile-item.team-member { gap:.65rem; }
  .profile-item.team-member .profile-avatar { width:24px; height:24px; font-size:.62rem; flex-shrink:0; }

  /* ---------- Apple-style mega menu ---------- */
  .mega-nav { position:sticky; top:64px; z-index:15; background:rgba(9,13,22,.72); backdrop-filter:blur(20px) saturate(160%); -webkit-backdrop-filter:blur(20px) saturate(160%); border-bottom:1px solid var(--border-color); }
  .mega-nav-inner { max-width:1400px; margin:0 auto; display:flex; align-items:center; justify-content:space-between; gap:.5rem; padding:0 2rem; }
  .mega-nav-items { display:flex; align-items:center; gap:.25rem; }
  .mega-item { position:relative; }
  .mega-item-trigger { background:none; border:none; color:var(--text-muted); font-size:.78rem; font-weight:600; letter-spacing:.2px; padding:.85rem 1.1rem; cursor:pointer; display:flex; align-items:center; gap:.4rem; transition:color .15s ease; }
  .mega-item-trigger .car { font-size:.55rem; opacity:.6; transition:transform .2s ease; }
  .mega-item-trigger::after { content:""; position:absolute; left:1.1rem; right:1.1rem; bottom:0; height:2px; background:linear-gradient(90deg,var(--brand-accent),var(--brand-primary)); transform:scaleX(0); transform-origin:center; transition:transform .22s ease; border-radius:2px 2px 0 0; }
  .mega-item:hover .mega-item-trigger, .mega-item.open .mega-item-trigger { color:#fff; }
  .mega-item:hover .mega-item-trigger::after, .mega-item.open .mega-item-trigger::after { transform:scaleX(1); }
  .mega-item.open .mega-item-trigger .car { transform:rotate(180deg); }

  .mega-panel { position:fixed; left:0; right:0; top:112px; background:rgba(10,14,23,.88); backdrop-filter:blur(24px) saturate(160%); -webkit-backdrop-filter:blur(24px) saturate(160%); border-bottom:1px solid var(--border-color); box-shadow:0 24px 48px -12px rgba(0,0,0,.6); opacity:0; visibility:hidden; transform:translateY(-8px); transition:opacity .2s ease, transform .2s ease, visibility .2s; z-index:14; }
  .mega-item.open .mega-panel { opacity:1; visibility:visible; transform:translateY(0); }
  @media (hover:hover) { .mega-item:hover .mega-panel { opacity:1; visibility:visible; transform:translateY(0); } .mega-item:hover .mega-item-trigger { color:#fff; } .mega-item:hover .mega-item-trigger::after { transform:scaleX(1); } }
  .mega-panel-inner { max-width:1400px; margin:0 auto; padding:2rem; display:grid; grid-template-columns:repeat(auto-fit,minmax(230px,1fr)); gap:.4rem; }
  .mega-eyebrow { grid-column:1/-1; font-size:.63rem; font-weight:750; text-transform:uppercase; letter-spacing:1.2px; color:var(--text-dark); margin-bottom:.3rem; }
  .mega-link { display:flex; align-items:flex-start; gap:.75rem; padding:.85rem .9rem; border-radius:10px; text-decoration:none; color:var(--text-main); cursor:pointer; transition:background .15s ease, transform .15s ease; }
  .mega-link:hover { background:rgba(255,255,255,.045); transform:translateX(2px); }
  .mega-link .mega-ico { width:38px; height:38px; border-radius:10px; background:rgba(255,255,255,.04); border:1px solid rgba(255,255,255,.07); display:flex; align-items:center; justify-content:center; font-size:1rem; color:var(--brand-accent); flex-shrink:0; transition:.15s ease; }
  .mega-link:hover .mega-ico { background:linear-gradient(135deg,var(--brand-primary),var(--brand-accent)); color:#fff; border-color:transparent; box-shadow:0 0 12px rgba(56,189,248,.4); }
  .mega-link-title { font-size:.82rem; font-weight:650; margin-bottom:.15rem; }
  .mega-link-desc { font-size:.7rem; color:var(--text-muted); line-height:1.4; }
  .mega-panel-aside { border-left:1px solid var(--border-color); padding-left:1.6rem; display:flex; flex-direction:column; gap:.6rem; justify-content:center; }
  .mega-panel-aside .stat-num { font-size:1.6rem; font-weight:800; color:#fff; letter-spacing:-.5px; }
  .mega-panel-aside .stat-lbl { font-size:.68rem; color:var(--text-muted); margin-top:.15rem; }
  .mega-panel-aside.threat-pulse .stat-num { color:var(--status-critical); }
  .mega-live-strip { grid-column:1/-1; display:flex; gap:.5rem; flex-wrap:wrap; margin-top:.25rem; padding-top:1rem; border-top:1px solid var(--border-color); }
  .mega-live-chip { display:flex; align-items:center; gap:.4rem; font-size:.68rem; color:var(--text-muted); background:rgba(255,255,255,.03); border:1px solid var(--border-color); padding:.32rem .65rem; border-radius:20px; font-family:var(--mono); }
  .mega-live-chip .flag { font-size:.8rem; }
  .mega-live-chip .cnt { color:#fff; font-weight:700; }
  @media (max-width: 980px) { .mega-nav { display:none; } }

  /* ---------- Nav search trigger ---------- */
  .mega-search-trigger { display:flex; align-items:center; gap:.55rem; background:rgba(255,255,255,.03); border:1px solid var(--border-color); color:var(--text-muted); font-size:.74rem; padding:.42rem .55rem .42rem .8rem; border-radius:20px; cursor:pointer; transition:.15s ease; flex-shrink:0; }
  .mega-search-trigger:hover { background:var(--bg-surface-hover); border-color:#2a3a56; color:#fff; }
  .mega-search-trigger .mega-search-ico { font-size:.8rem; opacity:.75; }
  .mega-search-trigger kbd { font-family:var(--mono); font-size:.62rem; color:var(--text-dark); background:rgba(0,0,0,.35); border:1px solid var(--border-color); border-radius:5px; padding:.1rem .35rem; }
  @media (max-width: 1180px) { .mega-search-trigger .search-label { display:none; } }
  @media (max-width: 980px) { .mega-search-trigger { display:none; } }

  /* ---------- Command palette ---------- */
  .cmdk-overlay { position:fixed; inset:0; z-index:200; background:rgba(4,6,11,.72); backdrop-filter:blur(4px); display:flex; align-items:flex-start; justify-content:center; padding-top:11vh; opacity:0; visibility:hidden; transition:opacity .16s ease, visibility .16s; }
  .cmdk-overlay.open { opacity:1; visibility:visible; }
  .cmdk-panel { width:100%; max-width:560px; margin:0 1rem; background:var(--bg-card); border:1px solid var(--border-color); border-radius:14px; box-shadow:var(--shadow-lg); overflow:hidden; transform:translateY(-10px) scale(.98); transition:transform .16s ease; }
  .cmdk-overlay.open .cmdk-panel { transform:translateY(0) scale(1); }
  .cmdk-input-row { display:flex; align-items:center; gap:.7rem; padding:.9rem 1.1rem; border-bottom:1px solid var(--border-color); }
  .cmdk-input-row .mega-search-ico { color:var(--brand-accent); font-size:.95rem; }
  .cmdk-input-row input { flex:1; background:none; border:none; outline:none; color:#fff; font-size:.88rem; }
  .cmdk-input-row input::placeholder { color:var(--text-dark); }
  .cmdk-input-row .cmdk-esc { font-family:var(--mono); font-size:.62rem; color:var(--text-dark); background:rgba(0,0,0,.35); border:1px solid var(--border-color); border-radius:5px; padding:.15rem .4rem; }
  .cmdk-results { max-height:340px; overflow-y:auto; padding:.5rem; }
  .cmdk-result { display:flex; align-items:center; gap:.75rem; padding:.6rem .7rem; border-radius:9px; cursor:pointer; color:var(--text-muted); }
  .cmdk-result .mega-ico { width:32px; height:32px; font-size:.85rem; }
  .cmdk-result-title { font-size:.8rem; font-weight:650; color:#fff; }
  .cmdk-result-desc { font-size:.68rem; color:var(--text-muted); margin-top:1px; }
  .cmdk-result-group { font-size:.6rem; font-weight:750; text-transform:uppercase; letter-spacing:1px; color:var(--text-dark); padding:.5rem .7rem .3rem; }
  .cmdk-result.active { background:rgba(56,189,248,.1); color:#fff; }
  .cmdk-result.active .mega-ico { background:linear-gradient(135deg,var(--brand-primary),var(--brand-accent)); color:#fff; border-color:transparent; }
  .cmdk-empty { padding:2rem 1rem; text-align:center; color:var(--text-dark); font-size:.78rem; }

  /* ---------- Live threat ticker ---------- */
  .live-ticker { background:rgba(5,8,14,.85); border-bottom:1px solid var(--border-color); overflow:hidden; white-space:nowrap; position:relative; height:34px; display:flex; align-items:center; }
  .live-ticker-track { display:inline-flex; align-items:center; gap:2.5rem; padding-left:1.5rem; animation:tickerScroll 38s linear infinite; font-family:var(--mono); font-size:.7rem; color:var(--text-muted); }
  .live-ticker:hover .live-ticker-track { animation-play-state:paused; }
  .live-ticker-track span { color:var(--brand-accent); }
  .live-ticker-track b { color:var(--text-main); font-weight:650; }
  @keyframes tickerScroll { from{transform:translateX(0);} to{transform:translateX(-50%);} }
  @media (prefers-reduced-motion: reduce) { .live-ticker-track { animation:none; } }

  /* ---------- Notification center ---------- */
  .notif-menu { position:relative; }
  .notif-badge-count { position:absolute; top:-4px; right:-5px; min-width:16px; height:16px; padding:0 3px; border-radius:8px; background:var(--status-critical); color:#fff; font-size:.58rem; font-weight:800; display:flex; align-items:center; justify-content:center; box-shadow:0 0 8px rgba(239,68,68,.6); line-height:1; }
  .notif-badge-count.hidden { display:none; }
  .notif-dropdown { position:absolute; top:calc(100% + 10px); right:-40px; width:340px; max-width:calc(100vw - 32px); background:var(--bg-card); border:1px solid var(--border-color); border-radius:12px; box-shadow:var(--shadow-lg); opacity:0; visibility:hidden; transform:translateY(-6px); transition:opacity .18s ease, transform .18s ease, visibility .18s; z-index:50; overflow:hidden; }
  .notif-menu.open .notif-dropdown { opacity:1; visibility:visible; transform:translateY(0); }
  .notif-head { display:flex; align-items:center; justify-content:space-between; padding:.85rem 1rem; border-bottom:1px solid var(--border-color); }
  .notif-head-title { font-size:.82rem; font-weight:700; color:#fff; display:flex; align-items:center; gap:.5rem; }
  .notif-mark-all { background:none; border:none; color:var(--brand-accent); font-size:.66rem; font-weight:650; cursor:pointer; padding:.2rem .3rem; }
  .notif-mark-all:hover { text-decoration:underline; }
  .notif-list { max-height:340px; overflow-y:auto; }
  .notif-item { display:flex; gap:.7rem; padding:.75rem 1rem; border-bottom:1px solid var(--border-color); cursor:pointer; transition:background .15s ease; position:relative; }
  .notif-item:last-child { border-bottom:none; }
  .notif-item:hover { background:var(--bg-surface-hover); }
  .notif-item.unread { background:rgba(37,99,235,.06); }
  .notif-item.unread::before { content:""; position:absolute; left:6px; top:1.15rem; width:6px; height:6px; border-radius:50%; background:var(--brand-accent); box-shadow:0 0 6px var(--brand-accent); }
  .notif-icon { width:30px; height:30px; border-radius:8px; display:flex; align-items:center; justify-content:center; font-size:.8rem; flex-shrink:0; margin-left:.4rem; }
  .notif-icon.critical { background:rgba(239,68,68,.14); color:var(--status-critical); }
  .notif-icon.warning { background:rgba(245,158,11,.14); color:var(--status-warning); }
  .notif-icon.success { background:rgba(16,185,129,.14); color:var(--status-success); }
  .notif-icon.info { background:rgba(59,130,246,.14); color:var(--brand-accent); }
  .notif-body { flex:1; min-width:0; }
  .notif-title { font-size:.76rem; font-weight:650; color:#fff; margin-bottom:.15rem; }
  .notif-desc { font-size:.7rem; color:var(--text-muted); line-height:1.4; }
  .notif-time { font-size:.63rem; color:var(--text-dark); margin-top:.3rem; }
  .notif-empty { padding:2.2rem 1rem; text-align:center; color:var(--text-dark); font-size:.76rem; }
  .notif-foot { padding:.65rem 1rem; text-align:center; border-top:1px solid var(--border-color); }
  .notif-foot a { font-size:.72rem; color:var(--brand-accent); text-decoration:none; font-weight:600; cursor:pointer; }
  .notif-foot a:hover { text-decoration:underline; }
  .notif-item.new-flash { animation:notifFlash 1.6s ease; }
  @keyframes notifFlash { 0%{ background:rgba(56,189,248,.22); } 100%{ background:transparent; } }
  @media (max-width: 560px) { .notif-dropdown { right:-90px; width:300px; } }

  /* ---------- Scanline overlay (signature live-tech effect) ---------- */
  .bg-scanline { position:fixed; left:0; right:0; height:140px; z-index:-1; pointer-events:none; background:linear-gradient(180deg, transparent, rgba(56,189,248,.05) 45%, rgba(56,189,248,.09) 50%, rgba(56,189,248,.05) 55%, transparent); animation:scanlineMove 7s ease-in-out infinite; mix-blend-mode:screen; }
  @keyframes scanlineMove { 0%{ top:-140px; } 50%{ top:100vh; } 100%{ top:-140px; } }
  @media (prefers-reduced-motion: reduce) { .bg-scanline { display:none; } }

  .view-section { display:none; }
  .view-section.active { display:block; animation:fadeIn .25s ease-out; }
  @keyframes fadeIn { from{opacity:0; transform:translateY(6px);} to{opacity:1; transform:translateY(0);} }
  .section-header { margin-bottom:1.4rem; display:flex; justify-content:space-between; align-items:flex-end; flex-wrap:wrap; gap:.75rem; }
  .section-title { font-size:1.15rem; font-weight:650; color:#fff; }
  .section-sub { font-size:.76rem; color:var(--text-muted); margin-top:.2rem; }

  /* ---------- Cards / grid ---------- */
  .metrics-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(220px,1fr)); gap:1.1rem; margin-bottom:1.5rem; }
  .metric-card { background:var(--bg-card); border:1px solid var(--border-color); border-radius:10px; padding:1.2rem; box-shadow:var(--shadow-sm); transition:.2s ease; position:relative; overflow:hidden; }
  .metric-card:hover { border-color:#00E5FF; transform:translateY(-8px); box-shadow:0 0 20px rgba(0,229,225,.3); }
  .metric-card-title { font-size:.72rem; color:var(--text-muted); font-weight:600; margin-bottom:.55rem; display:flex; justify-content:space-between; text-transform:uppercase; letter-spacing:.4px; }
  .metric-card-value { font-size:1.6rem; font-weight:750; color:#fff; margin-bottom:.3rem; letter-spacing:-.5px; }
  .metric-card-subtext { font-size:.7rem; color:var(--status-success); display:flex; align-items:center; gap:.25rem; }
  .metric-card-subtext.negative { color:var(--status-critical); }
  .metric-card-subtext.neutral { color:var(--text-muted); }

  .data-table-container { background:var(--bg-card); border:1px solid var(--border-color); border-radius:10px; overflow:hidden; box-shadow:var(--shadow-md); margin-bottom:1.5rem; }
  .table-header { padding:1rem 1.25rem; border-bottom:1px solid var(--border-color); display:flex; justify-content:space-between; align-items:center; flex-wrap:wrap; gap:.5rem; }
  .table-title { font-size:.87rem; font-weight:650; color:#fff; }
  .table-scroll { overflow-x:auto; }
  .data-table { width:100%; border-collapse:collapse; text-align:left; font-size:.79rem; min-width:600px; }
  .data-table th { background:rgba(0,0,0,.22); color:var(--text-muted); font-weight:650; padding:.7rem 1.25rem; border-bottom:1px solid var(--border-color); white-space:nowrap; font-size:.68rem; text-transform:uppercase; letter-spacing:.4px; }
  .data-table td { padding:.8rem 1.25rem; border-bottom:1px solid var(--border-color); color:var(--text-main); }
  .data-table tr:last-child td { border-bottom:none; }
  .data-table tr { transition:background .15s ease; }
  .data-table tr:hover td { background-color:rgba(255,255,255,.025); }
  .mono { font-family:var(--mono); font-size:.76rem; color:var(--brand-accent); }

  .badge { display:inline-flex; align-items:center; gap:4px; padding:.22rem .55rem; border-radius:5px; font-size:.62rem; font-weight:750; text-transform:uppercase; letter-spacing:.4px; }
  .badge-critical { background:rgba(239,68,68,.14); color:var(--status-critical); border:1px solid rgba(239,68,68,.3); }
  .badge-warning { background:rgba(245,158,11,.14); color:var(--status-warning); border:1px solid rgba(245,158,11,.3); }
  .badge-success { background:rgba(16,185,129,.14); color:var(--status-success); border:1px solid rgba(16,185,129,.3); }
  .badge-info { background:rgba(59,130,246,.14); color:var(--brand-accent); border:1px solid rgba(59,130,246,.3); }

  .icon-btn { background:transparent; border:1px solid var(--border-color); color:var(--text-muted); width:28px; height:28px; border-radius:6px; cursor:pointer; display:inline-flex; align-items:center; justify-content:center; font-size:.75rem; transition:.15s ease; }
  .icon-btn:hover { color:#fff; border-color:var(--brand-primary); background:rgba(37,99,235,.1); }

  /* ---------- Forms ---------- */
  .input-control { width:100%; background:var(--bg-surface); border:1px solid var(--border-color); color:#fff; padding:.62rem .85rem; border-radius:7px; font-size:.8rem; outline:none; transition:.15s ease; }
  .input-control::placeholder { color:var(--text-dark); }
  .input-control:focus { border-color:var(--border-focus); box-shadow:0 0 0 3px rgba(59,130,246,.15); }
  textarea.input-control { resize:vertical; min-height:100px; font-family:inherit; line-height:1.5; }
  select.input-control { cursor:pointer; }
  .form-group { display:flex; flex-direction:column; gap:.4rem; margin-bottom:.9rem; }
  .form-row { display:grid; grid-template-columns:1fr 1fr; gap:1rem; }
  .form-label { font-size:.7rem; font-weight:650; color:var(--text-muted); text-transform:uppercase; letter-spacing:.5px; }
  .form-hint { font-size:.68rem; color:var(--text-dark); }

  .btn { background:var(--brand-primary); color:#fff; border:none; padding:.65rem 1.3rem; border-radius:7px; font-size:.8rem; font-weight:650; cursor:pointer; display:inline-flex; align-items:center; justify-content:center; gap:.5rem; transition:.15s ease; box-shadow:0 2px 6px rgba(37,99,235,.3); }
  .btn:hover { background:var(--brand-primary-hover); transform:translateY(-1px); }
  .btn:active { transform:translateY(0); }
  .btn-secondary { background:transparent; border:1px solid var(--border-color); color:var(--text-main); box-shadow:none; }
  .btn-secondary:hover { background:var(--bg-surface-hover); }
  .btn-danger { background:var(--status-critical); box-shadow:0 2px 6px rgba(239,68,68,.3); }
  .btn-danger:hover { background:#dc2626; }
  .btn-success { background:var(--status-success); box-shadow:0 2px 6px rgba(16,185,129,.3); }
  .btn-success:hover { background:#0d9c6f; }
  .btn-block { width:100%; }
  .btn-sm { padding:.4rem .8rem; font-size:.7rem; }
  .btn:disabled { opacity:.5; cursor:not-allowed; transform:none; }

  /* ---------- Analysis / result panels ---------- */
  .analysis-card { background:var(--bg-card); border:1px solid var(--border-color); border-radius:10px; padding:1.3rem; margin-bottom:1.5rem; box-shadow:var(--shadow-md); }
  .analysis-grid { display:grid; grid-template-columns:1fr 1fr; gap:1.5rem; }
  .result-box { background:#050810; border:1px dashed var(--border-color); border-radius:8px; padding:1.1rem; margin-top:1rem; display:none; }
  .result-box.active { display:block; animation:fadeIn .25s ease; }
  .threat-score-gauge { display:flex; align-items:center; gap:1rem; margin-bottom:.85rem; }
  .score-circle { width:56px; height:56px; border-radius:50%; display:flex; align-items:center; justify-content:center; font-weight:800; font-size:1.05rem; background:var(--bg-surface); border:3px solid var(--border-color); flex-shrink:0; }
  .score-circle.high-risk { border-color:var(--status-critical); color:var(--status-critical); box-shadow:0 0 14px rgba(239,68,68,.3); }
  .score-circle.med-risk { border-color:var(--status-warning); color:var(--status-warning); box-shadow:0 0 14px rgba(245,158,11,.3); }
  .score-circle.low-risk { border-color:var(--status-success); color:var(--status-success); box-shadow:0 0 14px rgba(16,185,129,.3); }
  .result-title { font-weight:700; font-size:.85rem; color:#fff; margin-bottom:.2rem; }
  .result-desc { font-size:.76rem; color:var(--text-muted); line-height:1.5; }
  .indicator-list { list-style:none; margin-top:.75rem; display:flex; flex-direction:column; gap:.4rem; }
  .indicator-list li { font-size:.74rem; color:var(--text-muted); display:flex; gap:.5rem; align-items:flex-start; }
  .indicator-list li::before { content:"▸"; color:var(--brand-accent); flex-shrink:0; }

  .panel-card { background:var(--bg-card); border:1px solid var(--border-color); border-radius:10px; padding:1.3rem; display:flex; flex-direction:column; gap:1rem; margin-bottom:1.5rem; }

  /* ---------- Terminal console ---------- */
  .console-card { background:#04060c; border:1px solid var(--border-color); border-radius:10px; padding:1rem; font-family:var(--mono); font-size:.74rem; }
  .console-header { display:flex; justify-content:space-between; color:var(--text-muted); border-bottom:1px solid var(--border-color); padding-bottom:.5rem; margin-bottom:.75rem; letter-spacing:.4px; }
  .console-header span:last-child { color:var(--status-success); }
  .console-logs { height:150px; overflow-y:auto; display:flex; flex-direction:column-reverse; gap:.32rem; color:#8fe07a; }
  .console-logs p { opacity:0; animation:logIn .3s ease forwards; }
  @keyframes logIn { to{opacity:1;} }
  .console-logs .tag-warn { color:#fbbf24; }
  .console-logs .tag-crit { color:#f87171; }
  .console-logs .tag-time { color:#4b5f7f; margin-right:.4rem; }

  /* ---------- Toggle ---------- */
  .toggle-switch { display:flex; align-items:center; justify-content:space-between; padding:.85rem 1rem; background:var(--bg-surface); border:1px solid var(--border-color); border-radius:8px; margin-bottom:.55rem; }
  .toggle-switch span.tlabel { font-size:.8rem; font-weight:550; }
  .toggle-switch span.tdesc { font-size:.68rem; color:var(--text-dark); display:block; margin-top:2px; }
  .switch { position:relative; width:40px; height:22px; flex-shrink:0; }
  .switch input { opacity:0; width:0; height:0; }
  .slider { position:absolute; cursor:pointer; inset:0; background:#2a3752; transition:.2s; border-radius:22px; }
  .slider::before { content:""; position:absolute; height:16px; width:16px; left:3px; bottom:3px; background:#94a3b8; transition:.2s; border-radius:50%; }
  input:checked + .slider { background:var(--brand-primary); }
  input:checked + .slider::before { transform:translateX(18px); background:#fff; }

  /* ---------- Endpoint grid ---------- */
  .endpoint-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(230px,1fr)); gap:1rem; }
  .endpoint-card { background:var(--bg-card); border:1px solid var(--border-color); border-radius:10px; padding:1.1rem; }
  .endpoint-top { display:flex; justify-content:space-between; align-items:flex-start; margin-bottom:.6rem; }
  .endpoint-name { font-weight:650; font-size:.85rem; color:#fff; }
  .endpoint-meta { font-size:.68rem; color:var(--text-dark); margin-top:2px; }
  .endpoint-actions { display:flex; gap:.5rem; margin-top:.9rem; }
  .endpoint-card.isolated { border-color:rgba(239,68,68,.4); background:linear-gradient(180deg, rgba(239,68,68,.06), var(--bg-card) 40%); }

  /* ---------- AI Assistant Widget ---------- */
  .ai-assistant-widget { position:fixed; bottom:22px; right:22px; width:380px; max-width:calc(100vw - 32px); background:var(--bg-card); border:1px solid var(--border-color); border-radius:14px; box-shadow:var(--shadow-lg); display:flex; flex-direction:column; z-index:100; overflow:hidden; transition:all .25s cubic-bezier(.4,0,.2,1); }

  /* ---------- Case brief modal ---------- */
  .case-brief-overlay { position:fixed; inset:0; background:rgba(3,6,12,.72); z-index:200; display:none; align-items:center; justify-content:center; padding:1.5rem; }
  .case-brief-overlay.open { display:flex; }
  .case-brief-box { background:#fff; color:#111; width:100%; max-width:620px; max-height:85vh; overflow-y:auto; border-radius:12px; padding:1.75rem; box-shadow:var(--shadow-lg); }
  .case-brief-box h1 { font-size:1.15rem; border-bottom:2px solid #2563eb; padding-bottom:.5rem; margin-bottom:1rem; }
  .case-brief-box .row { margin-bottom:.85rem; }
  .case-brief-box .lbl { font-weight:700; font-size:.68rem; text-transform:uppercase; letter-spacing:.4px; color:#555; }
  .case-brief-box .val { font-size:.88rem; margin-top:.15rem; }
  .case-brief-box ul { margin:.3rem 0 0 1.1rem; font-size:.85rem; }
  .case-brief-actions { display:flex; gap:.6rem; margin-top:1.25rem; padding-top:1rem; border-top:1px solid #e5e7eb; }
  @media print {
    body > *:not(.case-brief-overlay) { display:none !important; }
    .case-brief-overlay { position:static !important; background:#fff !important; display:block !important; padding:0 !important; }
    .case-brief-box { max-height:none !important; box-shadow:none !important; max-width:none !important; }
    .case-brief-actions { display:none !important; }
  }
  .ai-assistant-widget.collapsed { height:56px; }
  .ai-assistant-widget.collapsed .ai-widget-body, .ai-assistant-widget.collapsed .ai-playbooks, .ai-assistant-widget.collapsed .ai-widget-footer { display:none; }
  .ai-widget-header { background:var(--bg-surface); padding:.7rem 1rem; display:flex; justify-content:space-between; align-items:center; cursor:pointer; border-bottom:1px solid var(--border-color); user-select:none; }
  .ai-widget-title { font-size:.85rem; font-weight:650; color:#fff; display:flex; align-items:center; gap:.6rem; }
  .cute-robot-avatar { width:32px; height:32px; background:linear-gradient(135deg,#38bdf8,#2563eb); border-radius:50%; display:flex; align-items:center; justify-content:center; box-shadow:0 0 10px rgba(56,189,248,.4); flex-shrink:0; font-size:.9rem; }
  .ai-widget-titlewrap { display:flex; flex-direction:column; }
  .ai-widget-status { font-size:.62rem; font-weight:600; color:var(--status-success); display:flex; align-items:center; gap:4px; }
  .ai-widget-status .d { width:5px; height:5px; border-radius:50%; background:var(--status-success); box-shadow:0 0 6px var(--status-success); }
  .ai-widget-status.offline { color:var(--text-dark); }
  .ai-widget-status.offline .d { background:var(--text-dark); box-shadow:none; }
  .ai-widget-collapse-btn { background:none; border:none; color:var(--text-muted); font-size:1rem; cursor:pointer; padding:2px 6px; }

  .ai-widget-body { height:300px; padding:1rem; overflow-y:auto; display:flex; flex-direction:column; gap:.75rem; font-size:.775rem; background:rgba(4,6,12,.5); }
  .assistant-row { display:flex; gap:.5rem; align-items:flex-start; }
  .assistant-row.user { flex-direction:row-reverse; }
  .assistant-msg { padding:.65rem .85rem; border-radius:10px; max-width:86%; line-height:1.45; word-break:break-word; }
  .assistant-msg.agent { background:var(--bg-surface); border:1px solid var(--border-color); color:var(--text-main); border-bottom-left-radius:2px; }
  .assistant-msg.user { background:var(--brand-primary); color:#fff; border-bottom-right-radius:2px; }
  .assistant-avatar-sm { width:22px; height:22px; border-radius:50%; background:linear-gradient(135deg,#38bdf8,#2563eb); flex-shrink:0; display:flex; align-items:center; justify-content:center; font-size:.65rem; }
  .typing-dots { display:inline-flex; gap:3px; padding:.4rem 0; }
  .typing-dots span { width:5px; height:5px; border-radius:50%; background:var(--text-muted); animation:blink 1.2s infinite ease-in-out; }
  .typing-dots span:nth-child(2){animation-delay:.2s;} .typing-dots span:nth-child(3){animation-delay:.4s;}
  @keyframes blink { 0%,80%,100%{opacity:.3;} 40%{opacity:1;} }

  .ai-playbooks { padding:.5rem .75rem; display:flex; gap:.35rem; overflow-x:auto; background:var(--bg-surface); border-top:1px solid var(--border-color); }
  .playbook-btn { background:rgba(255,255,255,.05); border:1px solid var(--border-color); color:var(--text-muted); font-size:.65rem; padding:.32rem .6rem; border-radius:5px; white-space:nowrap; cursor:pointer; transition:.15s ease; }
  .playbook-btn:hover { background:var(--bg-surface-hover); color:#fff; border-color:var(--brand-primary); }
  .ai-widget-footer { padding:.65rem; border-top:1px solid var(--border-color); display:flex; gap:.5rem; background:var(--bg-surface); }
  .ai-widget-footer input { flex:1; }
  .ai-send-btn { width:36px; height:36px; border-radius:8px; background:var(--brand-primary); border:none; color:#fff; cursor:pointer; display:flex; align-items:center; justify-content:center; flex-shrink:0; transition:.15s ease; }
  .ai-send-btn:hover { background:var(--brand-primary-hover); }

  .key-status-chip { font-size:.65rem; padding:.15rem .5rem; border-radius:5px; font-weight:650; }
  .key-status-chip.live { background:rgba(16,185,129,.14); color:var(--status-success); border:1px solid rgba(16,185,129,.3); }
  .key-status-chip.local { background:rgba(148,163,184,.14); color:var(--text-muted); border:1px solid rgba(148,163,184,.25); }

  /* ---------- Discover & Learn ---------- */
  .streak-chip { font-size:.72rem; font-weight:700; color:var(--status-warning); background:rgba(245,158,11,.1); border:1px solid rgba(245,158,11,.25); padding:.4rem .8rem; border-radius:20px; }
  .learn-daily { background:linear-gradient(135deg, rgba(37,99,235,.16), rgba(56,189,248,.08)); border:1px solid rgba(56,189,248,.28); border-radius:12px; padding:1.3rem 1.5rem; margin-bottom:1.4rem; position:relative; overflow:hidden; }
  .learn-daily::after { content:"✨"; position:absolute; right:1.3rem; top:1.1rem; font-size:1.6rem; opacity:.5; }
  .learn-daily-badge { font-size:.62rem; font-weight:800; letter-spacing:1px; color:var(--brand-accent); margin-bottom:.4rem; }
  .learn-daily-title { font-size:1rem; font-weight:700; color:#fff; margin-bottom:.3rem; max-width:560px; }
  .learn-daily-sub { font-size:.76rem; color:var(--text-muted); margin-bottom:.9rem; max-width:560px; line-height:1.5; }

  .learn-filter-row { display:flex; flex-wrap:wrap; gap:.5rem; margin-bottom:1.6rem; position:sticky; top:0; z-index:5; background:rgba(6,9,17,.7); backdrop-filter:blur(8px); padding:.6rem 0; }
  .learn-filter { background:var(--bg-surface); border:1px solid var(--border-color); color:var(--text-muted); font-size:.72rem; font-weight:650; padding:.4rem .85rem; border-radius:20px; cursor:pointer; transition:.15s ease; display:flex; align-items:center; gap:.35rem; }
  .learn-filter:hover { color:#fff; border-color:#2a3a56; }
  .learn-filter.active { background:linear-gradient(135deg,var(--brand-primary),var(--brand-accent)); color:#fff; border-color:transparent; box-shadow:0 0 10px rgba(56,189,248,.35); }

  /* Category section (a "sub-section" of the Learn hub, one per topic area) */
  .learn-category { margin-bottom:2.4rem; scroll-margin-top:90px; }
  .learn-category-banner { position:relative; border-radius:14px; overflow:hidden; border:1px solid var(--border-color); margin-bottom:1.1rem; height:132px; display:flex; align-items:flex-end; }
  .learn-category-banner img { position:absolute; inset:0; width:100%; height:100%; object-fit:cover; filter:brightness(.5) saturate(1.1); }
  .learn-category-banner::after { content:""; position:absolute; inset:0; background:linear-gradient(0deg, rgba(6,9,17,.92) 10%, rgba(6,9,17,.15) 85%); }
  .learn-category-banner-inner { position:relative; z-index:1; padding:1rem 1.3rem; display:flex; align-items:center; gap:.8rem; width:100%; }
  .learn-category-ico { width:42px; height:42px; border-radius:11px; display:flex; align-items:center; justify-content:center; font-size:1.25rem; flex-shrink:0; background:rgba(255,255,255,.08); border:1px solid rgba(255,255,255,.15); }
  .learn-category-title { font-size:1.02rem; font-weight:750; color:#fff; }
  .learn-category-desc { font-size:.74rem; color:var(--text-muted); max-width:640px; margin-top:2px; }
  .learn-category-count { margin-left:auto; font-size:.64rem; font-weight:700; color:var(--text-muted); background:rgba(0,0,0,.35); border:1px solid rgba(255,255,255,.1); padding:.3rem .7rem; border-radius:20px; white-space:nowrap; }

  .learn-grid { display:grid; grid-template-columns:repeat(auto-fit,minmax(255px,1fr)); gap:1.1rem; }
  .learn-card { background:var(--bg-card); border:1px solid var(--border-color); border-radius:12px; overflow:hidden; cursor:pointer; transition:.2s ease; display:flex; flex-direction:column; }
  .learn-card:hover { border-color:#2a3a56; transform:translateY(-3px); box-shadow:var(--shadow-md); }
  .learn-card-img-wrap { position:relative; height:120px; overflow:hidden; flex-shrink:0; }
  .learn-card-img-wrap img { width:100%; height:100%; object-fit:cover; display:block; transition:transform .35s ease; }
  .learn-card:hover .learn-card-img-wrap img { transform:scale(1.06); }
  .learn-card-img-wrap::after { content:""; position:absolute; inset:0; background:linear-gradient(180deg, rgba(6,9,17,0) 55%, rgba(6,9,17,.85) 100%); }
  .learn-card-tag { position:absolute; top:.6rem; left:.6rem; z-index:1; font-size:.58rem; font-weight:750; text-transform:uppercase; letter-spacing:.4px; padding:.22rem .5rem; border-radius:5px; white-space:nowrap; }
  .learn-card-tag.beginner { background:rgba(16,185,129,.85); color:#04140d; }
  .learn-card-tag.intermediate { background:rgba(245,158,11,.85); color:#1d1204; }
  .learn-card-tag.advanced { background:rgba(239,68,68,.85); color:#1d0505; }
  .learn-card-ico { position:absolute; bottom:.55rem; left:.65rem; z-index:1; width:34px; height:34px; border-radius:9px; display:flex; align-items:center; justify-content:center; font-size:1rem; }
  .learn-card-body { padding:.95rem 1.05rem 1.05rem; display:flex; flex-direction:column; gap:.5rem; flex:1; }
  .learn-card-title { font-size:.86rem; font-weight:700; color:#fff; }
  .learn-card-desc { font-size:.74rem; color:var(--text-muted); line-height:1.5; flex:1; }
  .learn-card-meta { display:flex; align-items:center; justify-content:space-between; font-size:.68rem; color:var(--text-dark); border-top:1px solid var(--border-color); padding-top:.6rem; }
  .learn-card-meta .done-check { color:var(--status-success); display:none; align-items:center; gap:.25rem; font-weight:650; }
  .learn-card.completed .learn-card-meta .done-check { display:flex; }
  .learn-card.completed .learn-card-meta .est-time { display:none; }
  .learn-card.completed { border-color:rgba(16,185,129,.35); }
  .learn-fact-box { display:none; background:#050810; border:1px dashed var(--border-color); border-radius:8px; padding:.75rem .85rem; font-size:.73rem; color:var(--text-muted); line-height:1.55; }
  .learn-card.expanded .learn-fact-box { display:block; animation:fadeIn .2s ease; }
  .learn-fact-box b { color:var(--brand-accent); }
  .learn-hub-stats { display:grid; grid-template-columns:repeat(auto-fit,minmax(150px,1fr)); gap:.8rem; margin-bottom:1.6rem; }
  .learn-hub-stat { background:var(--bg-card); border:1px solid var(--border-color); border-radius:10px; padding:.85rem 1rem; }
  .learn-hub-stat .num { font-size:1.3rem; font-weight:800; color:#fff; }
  .learn-hub-stat .lbl { font-size:.68rem; color:var(--text-muted); margin-top:2px; }

  /* ---------- Responsive ---------- */
  @media (max-width: 980px) {
    .analysis-grid { grid-template-columns:1fr; }
    .form-row { grid-template-columns:1fr; }
    .ai-assistant-widget { right:12px; bottom:12px; width:calc(100vw - 24px); }
    .clock { display:none; }
  }
</style>
</head>
<body>
  <video class="bg-video" id="bg-video" autoplay muted loop playsinline preload="auto">
    <source src="bg-video.mp4" type="video/mp4">
  </video>
  <div class="bg-layer"></div>
  <div class="bg-grid"></div>
  <canvas id="bg-canvas"></canvas>
  <div class="bg-sweep"></div>
  <div class="bg-scanline"></div>
  <div class="bg-vignette"></div>

  <!-- Main Content Dashboard -->
  <main class="dashboard">
    <header class="top-header">
      <div style="display:flex; align-items:center; gap:1rem;">
        <div class="brand-logo">F</div>
        <div class="header-title">
          <h1>Fortress Protocol Command Center <span style="font-size:.72rem; color:var(--brand-accent); background:rgba(56,189,248,.1); padding:2px 6px; border-radius:4px; border:1px solid rgba(56,189,248,.3);">v1.2</span></h1>
          <h2>Cybersecurity, Privacy &amp; Digital Resilience</h2>
        </div>
      </div>
      <div class="header-actions">
        <span class="clock" id="clock">—</span>
        <div class="status-indicator" id="defcon-indicator"><div class="indicator-dot"></div> DEFCON 5 — NORMAL</div>
        <div class="notif-menu" id="notif-menu">
          <button class="icon-btn" id="notif-btn" aria-label="Notifications" style="width:34px;height:34px;position:relative;">
            🔔<span id="notif-badge-count" class="notif-badge-count hidden">0</span>
          </button>
          <div class="notif-dropdown" id="notif-dropdown">
            <div class="notif-head">
              <div class="notif-head-title">🔔 Notifications</div>
              <button class="notif-mark-all" id="notif-mark-all">Mark all read</button>
            </div>
            <div class="notif-list" id="notif-list"></div>
            <div class="notif-foot"><a data-target="analytics-view" id="notif-view-all">View all in Audit Logs</a></div>
          </div>
        </div>
        <div class="profile-menu" id="profile-menu">
          <button class="profile-trigger" id="profile-trigger">
            <div class="avatar-stack">
              <div class="profile-avatar stack-av" style="background:linear-gradient(135deg,#38bdf8,#2563eb);">R</div>
              <div class="profile-avatar stack-av" style="background:linear-gradient(135deg,#a78bfa,#7c3aed);">H</div>
              <div class="profile-avatar stack-av" style="background:linear-gradient(135deg,#34d399,#059669);">D</div>
              <div class="profile-avatar stack-av" style="background:linear-gradient(135deg,#f59e0b,#d97706);">K</div>
            </div>
            <div class="profile-info">
              <span class="profile-name">SOC Team</span>
              <span class="profile-role">4 analysts on shift</span>
            </div>
            <span class="profile-caret">▾</span>
          </button>
          <div class="profile-dropdown" id="profile-dropdown">
            <div class="profile-dropdown-head">
              <div>
                <div class="profile-name">On-Shift SOC Team</div>
                <div class="profile-role">fortressprotocol.local</div>
              </div>
            </div>
            <a class="profile-item team-member"><span class="profile-avatar" style="background:linear-gradient(135deg,#38bdf8,#2563eb);">R</span> Rishi</a>
            <a class="profile-item team-member"><span class="profile-avatar" style="background:linear-gradient(135deg,#a78bfa,#7c3aed);">H</span> Harnoor</a>
            <a class="profile-item team-member"><span class="profile-avatar" style="background:linear-gradient(135deg,#34d399,#059669);">D</span> Divyanshu</a>
            <a class="profile-item team-member"><span class="profile-avatar" style="background:linear-gradient(135deg,#f59e0b,#d97706);">K</span> Krishna</a>
            <div class="profile-divider"></div>
            <a class="profile-item" data-target="settings-view">⚙ SOC Configurations</a>
            <a class="profile-item" data-target="analytics-view">▤ Team Audit Trail</a>
            <a class="profile-item">🌓 Toggle Compact Mode</a>
            <div class="profile-divider"></div>
            <a class="profile-item danger">⏻ Sign Out</a>
          </div>
        </div>
      </div>
    </header>

    <!-- Apple-style mega menu -->
    <nav class="mega-nav" id="mega-nav">
      <div class="mega-nav-inner">
      <div class="mega-nav-items">
        <div class="mega-item" data-group="overview">
          <button class="mega-item-trigger">Overview <span class="car">▾</span></button>
          <div class="mega-panel">
            <div class="mega-panel-inner" style="grid-template-columns:1fr 1fr 260px;">
              <div>
                <div class="mega-eyebrow">Command Center</div>
                <a class="mega-link" data-target="dashboard-view"><span class="mega-ico">◈</span><span><div class="mega-link-title">Executive Overview</div><div class="mega-link-desc">Org-wide posture, live metrics &amp; console</div></span></a>
                <a class="mega-link" data-target="analytics-view"><span class="mega-ico">▤</span><span><div class="mega-link-title">Audit Logs</div><div class="mega-link-desc">Full history of analyst &amp; system actions</div></span></a>
              </div>
              <div>
                <div class="mega-eyebrow">Quick Actions</div>
                <a class="mega-link" data-target="report-threat-view"><span class="mega-ico">⚑</span><span><div class="mega-link-title">Log Threat Report</div><div class="mega-link-desc">Submit a new suspicious artifact</div></span></a>
                <a class="mega-link" data-target="ai-view"><span class="mega-ico">◉</span><span><div class="mega-link-title">Neural AI Telemetry</div><div class="mega-link-desc">Model confidence &amp; classifier health</div></span></a>
              </div>
              <div class="mega-panel-aside">
                <div><div class="stat-num" style="color:var(--status-success);">DEFCON 5</div><div class="stat-lbl">Current posture — normal operations</div></div>
                <div><div class="stat-num" id="mega-open-incidents">—</div><div class="stat-lbl">Open incidents right now</div></div>
              </div>
            </div>
          </div>
        </div>

        <div class="mega-item" data-group="ops">
          <button class="mega-item-trigger">Core Operations <span class="car">▾</span></button>
          <div class="mega-panel">
            <div class="mega-panel-inner">
              <a class="mega-link" data-target="threats-view"><span class="mega-ico">▣</span><span><div class="mega-link-title">Incident Management</div><div class="mega-link-desc">Triage, assign &amp; resolve active cases</div></span></a>
              <a class="mega-link" data-target="firewall-view"><span class="mega-ico">▦</span><span><div class="mega-link-title">Perimeter Rules</div><div class="mega-link-desc">Firewall policy &amp; traffic controls</div></span></a>
              <a class="mega-link" data-target="report-threat-view"><span class="mega-ico">⚑</span><span><div class="mega-link-title">Log Threat Report</div><div class="mega-link-desc">Escalate a new finding for review</div></span></a>
              <a class="mega-link" data-target="ai-view"><span class="mega-ico">◉</span><span><div class="mega-link-title">Neural AI Telemetry</div><div class="mega-link-desc">Autonomous detection engine status</div></span></a>
            </div>
          </div>
        </div>

        <div class="mega-item" data-group="protection">
          <button class="mega-item-trigger">Vector Protection <span class="car">▾</span></button>
          <div class="mega-panel">
            <div class="mega-panel-inner">
              <a class="mega-link" data-target="phishing-view"><span class="mega-ico">✉</span><span><div class="mega-link-title">Email Phishing Gateway</div><div class="mega-link-desc">Analyze &amp; score suspicious email</div></span></a>
              <a class="mega-link" data-target="telephony-view"><span class="mega-ico">☎</span><span><div class="mega-link-title">Telephony &amp; SMS Radar</div><div class="mega-link-desc">Voice &amp; SMS phishing detection</div></span></a>
              <a class="mega-link" data-target="link-view"><span class="mega-ico">⛓</span><span><div class="mega-link-title">URL Sandbox Engine</div><div class="mega-link-desc">Detonate &amp; inspect suspicious links</div></span></a>
              <a class="mega-link" data-target="cases-view"><span class="mega-ico">🗂</span><span><div class="mega-link-title">Security Case Review</div><div class="mega-link-desc">Label, filter &amp; export analyzed cases</div></span></a>
              <a class="mega-link" data-target="ransomware-view"><span class="mega-ico">⛔</span><span><div class="mega-link-title">Endpoint Containment</div><div class="mega-link-desc">Isolate &amp; remediate compromised hosts</div></span></a>
            </div>
          </div>
        </div>

        <div class="mega-item" data-group="threat-intel">
          <button class="mega-item-trigger">Threat Intel <span class="car">▾</span></button>
          <div class="mega-panel">
            <div class="mega-panel-inner" style="grid-template-columns:1fr 1fr 260px;">
              <div>
                <div class="mega-eyebrow">Global Feed</div>
                <a class="mega-link" data-target="threats-view"><span class="mega-ico">🌐</span><span><div class="mega-link-title">Live Attack Map</div><div class="mega-link-desc">Real-time origin &amp; target of active incidents</div></span></a>
                <a class="mega-link" data-target="analytics-view"><span class="mega-ico">📡</span><span><div class="mega-link-title">Threat Intel Feed</div><div class="mega-link-desc">Aggregated IOCs from partner networks</div></span></a>
              </div>
              <div>
                <div class="mega-eyebrow">Deep Dive</div>
                <a class="mega-link" data-target="ai-view"><span class="mega-ico">◉</span><span><div class="mega-link-title">Neural AI Telemetry</div><div class="mega-link-desc">See what the detection engine is flagging now</div></span></a>
                <a class="mega-link" data-target="firewall-view"><span class="mega-ico">▦</span><span><div class="mega-link-title">Perimeter Rules</div><div class="mega-link-desc">Rules triggered by recent global activity</div></span></a>
              </div>
              <div class="mega-panel-aside threat-pulse">
                <div><div class="stat-num" id="mega-intel-attacks">—</div><div class="stat-lbl">Attacks blocked, last 24h</div></div>
                <div><div class="stat-num" style="color:var(--status-success);" id="mega-intel-countries">—</div><div class="stat-lbl">Source countries tracked</div></div>
              </div>
              <div class="mega-live-strip" id="mega-live-strip"></div>
            </div>
          </div>
        </div>

        <div class="mega-item" data-group="privacy-resilience">
          <button class="mega-item-trigger">Privacy &amp; Resilience <span class="car">▾</span></button>
          <div class="mega-panel">
            <div class="mega-panel-inner" style="grid-template-columns:1fr 1fr 260px;">
              <div>
                <div class="mega-eyebrow">Privacy</div>
                <a class="mega-link" data-target="privacy-view"><span class="mega-ico">🛡</span><span><div class="mega-link-title">Privacy &amp; Data Protection</div><div class="mega-link-desc">DSARs, data inventory &amp; consent controls</div></span></a>
              </div>
              <div>
                <div class="mega-eyebrow">Resilience</div>
                <a class="mega-link" data-target="resilience-view"><span class="mega-ico">♻</span><span><div class="mega-link-title">Digital Resilience &amp; BCP</div><div class="mega-link-desc">Backups, recovery targets &amp; DR drills</div></span></a>
              </div>
              <div class="mega-panel-aside">
                <div><div class="stat-num" style="color:var(--status-success);">3</div><div class="stat-lbl">Open privacy requests</div></div>
                <div><div class="stat-num">94%</div><div class="stat-lbl">Resilience score</div></div>
              </div>
            </div>
          </div>
        </div>

        <div class="mega-item" data-group="governance">
          <button class="mega-item-trigger">Governance <span class="car">▾</span></button>
          <div class="mega-panel">
            <div class="mega-panel-inner">
              <a class="mega-link" data-target="analytics-view"><span class="mega-ico">▤</span><span><div class="mega-link-title">Audit Logs</div><div class="mega-link-desc">Compliance-ready action history</div></span></a>
              <a class="mega-link" data-target="settings-view"><span class="mega-ico">⚙</span><span><div class="mega-link-title">SOC Configurations</div><div class="mega-link-desc">Alerting, integrations &amp; access</div></span></a>
              <a class="mega-link" data-target="learn-view"><span class="mega-ico">🎓</span><span><div class="mega-link-title">Discover &amp; Learn</div><div class="mega-link-desc">Fun, bite-sized cybersecurity topics</div></span></a>
            </div>
          </div>
        </div>
      </div>

      <button class="mega-search-trigger" id="mega-search-trigger" aria-label="Open quick search">
        <span class="mega-search-ico">🔎</span><span class="search-label">Quick search</span><kbd>⌘K</kbd>
      </button>
      </div>
    </nav>

    <!-- Command palette -->
    <div class="cmdk-overlay" id="cmdk-overlay">
      <div class="cmdk-panel">
        <div class="cmdk-input-row">
          <span class="mega-search-ico">🔎</span>
          <input type="text" id="cmdk-input" placeholder="Jump to a view, action, or tool…" autocomplete="off">
          <span class="cmdk-esc">ESC</span>
        </div>
        <div class="cmdk-results" id="cmdk-results"></div>
      </div>
    </div>

    <!-- Live threat ticker -->
    <div class="live-ticker">
      <div class="live-ticker-track" id="live-ticker-track"></div>
    </div>

    <div class="main-container">

      <!-- 1. Executive Overview -->
      <section id="dashboard-view" class="view-section active">
        <div class="section-header">
          <div>
            <h2 class="section-title">Security Posture Summary</h2>
            <div class="section-sub">Live rollup across all monitored vectors and endpoints</div>
          </div>
          <button class="btn btn-secondary" id="btn-export-report">⬇ Export SOC Briefing</button>
        </div>

        <div class="metrics-grid">
          <div class="metric-card">
            <div class="metric-card-title">ACTIVE INCIDENTS <span>12h</span></div>
            <div class="metric-card-value" id="metric-incidents-count">2</div>
            <div class="metric-card-subtext negative">▲ 1 Critical requiring review</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">AUTONOMOUS NEUTRALIZATIONS</div>
            <div class="metric-card-value" id="metric-neutralized-count">1,482</div>
            <div class="metric-card-subtext">▼ 12% vs last 24h</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">AI ENGINE CONFIDENCE</div>
            <div class="metric-card-value">99.8%</div>
            <div class="metric-card-subtext">Zero false positives recorded</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">GLOBAL THREAT INDEX</div>
            <div class="metric-card-value" id="threat-index-val">Low</div>
            <div class="metric-card-subtext neutral" id="threat-index-sub">Nominal baseline load</div>
          </div>
        </div>

        <div class="data-table-container">
          <div class="table-header">
            <div class="table-title">Real-Time Threat Ingress Queue</div>
            <span class="badge badge-info" id="ingress-live-badge">● LIVE</span>
          </div>
          <div class="table-scroll">
            <table class="data-table" id="ingress-table">
              <thead>
                <tr>
                  <th>Incident ID</th><th>Vector Type</th><th>Source Origin</th><th>Severity</th><th>Action Taken</th>
                </tr>
              </thead>
              <tbody>
                <tr>
                  <td class="mono">INC-8902</td>
                  <td>SQL Injection Attempt</td>
                  <td class="mono">192.168.1.45</td>
                  <td><span class="badge badge-critical">Critical</span></td>
                  <td>Isolated via Perimeter Firewall</td>
                </tr>
                <tr>
                  <td class="mono">INC-8899</td>
                  <td>Credential Harvesting Link</td>
                  <td class="mono">mail.internal-update.org</td>
                  <td><span class="badge badge-warning">High</span></td>
                  <td>Email Quarantined</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>

        <div class="console-card">
          <div class="console-header">
            <span>SOC REAL-TIME SYSTEM LOG AUDIT STREAM</span>
            <span>● SYSTEM AUDIT ON</span>
          </div>
          <div class="console-logs" id="console-logs">
            <p><span class="tag-time">[00:00:00]</span>SYSTEM INITIALIZED — FORTRESS PROTOCOL v1.2 fully connected to threat intelligence mesh.</p>
          </div>
        </div>
      </section>

      <!-- 2. Log Threat Report -->
      <section id="report-threat-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Log Threat Report</h2>
            <div class="section-sub">Submit an observed incident for triage and analyst review</div>
          </div>
        </div>
        <div class="panel-card" style="max-width:640px;">
          <form id="threat-report-form">
            <div class="form-row">
              <div class="form-group">
                <label class="form-label">Vector Type</label>
                <select class="input-control" id="rpt-vector" required>
                  <option value="">Select vector…</option>
                  <option>Phishing Email</option>
                  <option>Malicious URL</option>
                  <option>Suspicious Call / SMS</option>
                  <option>Ransomware / Malware</option>
                  <option>Unauthorized Access</option>
                  <option>Other</option>
                </select>
              </div>
              <div class="form-group">
                <label class="form-label">Severity</label>
                <select class="input-control" id="rpt-severity" required>
                  <option value="Low">Low</option>
                  <option value="Medium" selected>Medium</option>
                  <option value="High">High</option>
                  <option value="Critical">Critical</option>
                </select>
              </div>
            </div>
            <div class="form-group">
              <label class="form-label">Source / Origin</label>
              <input class="input-control" id="rpt-source" placeholder="IP address, domain, sender, or phone number" required>
            </div>
            <div class="form-group">
              <label class="form-label">Description</label>
              <textarea class="input-control" id="rpt-desc" placeholder="Describe what was observed…" required></textarea>
            </div>
            <button type="submit" class="btn btn-block">Submit Threat Report</button>
            <div class="form-hint" style="margin-top:.6rem;">Reports are appended to the Incident Management queue instantly and routed to the on-call analyst.</div>
          </form>
        </div>
      </section>

      <!-- 3. Incident Management -->
      <section id="threats-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Incident Management</h2>
            <div class="section-sub">Track, escalate, and resolve open security incidents</div>
          </div>
        </div>
        <div class="data-table-container">
          <div class="table-scroll">
            <table class="data-table" id="incidents-table">
              <thead>
                <tr><th>Incident ID</th><th>Vector</th><th>Source</th><th>Severity</th><th>Status</th><th>Actions</th></tr>
              </thead>
              <tbody id="incidents-tbody">
                <tr data-id="INC-8902">
                  <td class="mono">INC-8902</td><td>SQL Injection Attempt</td><td class="mono">192.168.1.45</td>
                  <td><span class="badge badge-critical">Critical</span></td>
                  <td><span class="badge badge-warning status-cell">Open</span></td>
                  <td style="display:flex; gap:.4rem;">
                    <button class="btn btn-sm btn-success act-resolve">Resolve</button>
                    <button class="btn btn-sm btn-secondary act-escalate">Escalate</button>
                  </td>
                </tr>
                <tr data-id="INC-8899">
                  <td class="mono">INC-8899</td><td>Credential Harvesting Link</td><td class="mono">mail.internal-update.org</td>
                  <td><span class="badge badge-warning">High</span></td>
                  <td><span class="badge badge-warning status-cell">Open</span></td>
                  <td style="display:flex; gap:.4rem;">
                    <button class="btn btn-sm btn-success act-resolve">Resolve</button>
                    <button class="btn btn-sm btn-secondary act-escalate">Escalate</button>
                  </td>
                </tr>
                <tr data-id="INC-8873">
                  <td class="mono">INC-8873</td><td>Brute Force Login</td><td class="mono">203.0.113.9</td>
                  <td><span class="badge badge-info">Medium</span></td>
                  <td><span class="badge badge-success status-cell">Resolved</span></td>
                  <td style="display:flex; gap:.4rem;">
                    <button class="btn btn-sm btn-secondary" disabled>Closed</button>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </section>

      <!-- 4. Neural AI Telemetry -->
      <section id="ai-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Neural AI Telemetry</h2>
            <div class="section-sub">Detection model performance across the last analysis window</div>
          </div>
        </div>
        <div class="metrics-grid">
          <div class="metric-card"><div class="metric-card-title">MODEL PRECISION</div><div class="metric-card-value">99.4%</div><div class="metric-card-subtext">Gemini-backed classifier</div></div>
          <div class="metric-card"><div class="metric-card-title">MODEL RECALL</div><div class="metric-card-value">97.8%</div><div class="metric-card-subtext">Stable over 7 days</div></div>
          <div class="metric-card"><div class="metric-card-title">AVG INFERENCE TIME</div><div class="metric-card-value">142ms</div><div class="metric-card-subtext neutral">Per artifact scanned</div></div>
          <div class="metric-card"><div class="metric-card-title">SAMPLES PROCESSED</div><div class="metric-card-value">48.2K</div><div class="metric-card-subtext">Last 24 hours</div></div>
        </div>
        <div class="panel-card">
          <div class="table-title">Model Confidence Distribution</div>
          <div style="display:flex; flex-direction:column; gap:.7rem;">
            <div class="metric-row"><div class="metric-label"><span>Phishing Detection</span><span>98.9%</span></div><div class="progress-bg"><div class="progress-fill" style="width:98.9%;"></div></div></div>
            <div class="metric-row"><div class="metric-label"><span>Malicious URL Detection</span><span>97.2%</span></div><div class="progress-bg"><div class="progress-fill" style="width:97.2%; background:var(--brand-accent);"></div></div></div>
            <div class="metric-row"><div class="metric-label"><span>Voice / SMS Scam Detection</span><span>95.6%</span></div><div class="progress-bg"><div class="progress-fill" style="width:95.6%; background:var(--status-success);"></div></div></div>
            <div class="metric-row"><div class="metric-label"><span>Ransomware Behavior Detection</span><span>99.1%</span></div><div class="progress-bg"><div class="progress-fill" style="width:99.1%; background:var(--status-warning);"></div></div></div>
          </div>
        </div>
      </section>

      <!-- 5. Perimeter Rules -->
      <section id="firewall-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Perimeter Firewall Rules</h2>
            <div class="section-sub">Manage inbound and outbound traffic policy</div>
          </div>
        </div>
        <div class="panel-card">
          <div class="form-row" style="align-items:flex-end;">
            <div class="form-group"><label class="form-label">Rule Name</label><input class="input-control" id="fw-name" placeholder="e.g. Block TOR Exit Nodes"></div>
            <div class="form-group"><label class="form-label">Target (IP / CIDR / Domain)</label><input class="input-control" id="fw-target" placeholder="e.g. 185.220.0.0/16"></div>
          </div>
          <div class="form-row" style="align-items:flex-end;">
            <div class="form-group"><label class="form-label">Direction</label>
              <select class="input-control" id="fw-dir"><option>Inbound</option><option>Outbound</option><option>Both</option></select>
            </div>
            <div class="form-group"><label class="form-label">Policy</label>
              <select class="input-control" id="fw-policy"><option>Block</option><option>Allow</option><option>Monitor Only</option></select>
            </div>
          </div>
          <button class="btn" id="fw-add-btn">+ Add Rule</button>
        </div>
        <div class="data-table-container">
          <div class="table-scroll">
            <table class="data-table" id="fw-table">
              <thead><tr><th>Rule</th><th>Target</th><th>Direction</th><th>Policy</th><th></th></tr></thead>
              <tbody id="fw-tbody">
                <tr><td>Block Known Botnet C2</td><td class="mono">45.155.204.0/24</td><td>Inbound</td><td><span class="badge badge-critical">Block</span></td><td><button class="icon-btn act-fw-remove" title="Remove">✕</button></td></tr>
                <tr><td>Allow VPN Gateway</td><td class="mono">10.20.0.0/16</td><td>Both</td><td><span class="badge badge-success">Allow</span></td><td><button class="icon-btn act-fw-remove" title="Remove">✕</button></td></tr>
                <tr><td>Monitor Cloud Storage Egress</td><td class="mono">*.blob.core.net</td><td>Outbound</td><td><span class="badge badge-info">Monitor</span></td><td><button class="icon-btn act-fw-remove" title="Remove">✕</button></td></tr>
              </tbody>
            </table>
          </div>
        </div>
      </section>

      <!-- 6. Email Phishing Gateway -->
      <section id="phishing-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Email Phishing Gateway</h2>
            <div class="section-sub">Paste raw email content or headers for heuristic analysis</div>
          </div>
        </div>
        <div class="analysis-card">
          <div class="analysis-grid">
            <div>
              <div class="form-group">
                <label class="form-label">Sender Address</label>
                <input class="input-control" id="ph-sender" placeholder="e.g. accounts@paypa1-secure.com">
              </div>
              <div class="form-group">
                <label class="form-label">Subject &amp; Body</label>
                <textarea class="input-control" id="ph-body" placeholder="Paste the email subject and body text…" style="min-height:160px;"></textarea>
              </div>
              <button class="btn" id="ph-analyze-btn">Analyze Message</button>
            </div>
            <div>
              <div id="ph-result" class="result-box">
                <div class="threat-score-gauge">
                  <div class="score-circle" id="ph-score-circle">—</div>
                  <div><div class="result-title" id="ph-result-title">—</div><div class="result-desc" id="ph-result-desc">—</div></div>
                </div>
                <ul class="indicator-list" id="ph-indicators"></ul>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- 7. Telephony & SMS Radar -->
      <section id="telephony-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Telephony &amp; SMS Radar</h2>
            <div class="section-sub">Screen inbound calls and text messages for scam indicators</div>
          </div>
        </div>
        <div class="analysis-card">
          <div class="analysis-grid">
            <div>
              <div class="form-group">
                <label class="form-label">Caller / Sender Number</label>
                <input class="input-control" id="tel-number" placeholder="e.g. +1 (800) 555-0199">
              </div>
              <div class="form-group">
                <label class="form-label">Message / Call Transcript</label>
                <textarea class="input-control" id="tel-body" placeholder="Paste the SMS text or call transcript…" style="min-height:160px;"></textarea>
              </div>
              <button class="btn" id="tel-analyze-btn">Analyze Contact</button>
            </div>
            <div>
              <div id="tel-result" class="result-box">
                <div class="threat-score-gauge">
                  <div class="score-circle" id="tel-score-circle">—</div>
                  <div><div class="result-title" id="tel-result-title">—</div><div class="result-desc" id="tel-result-desc">—</div></div>
                </div>
                <ul class="indicator-list" id="tel-indicators"></ul>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- 8. URL Sandbox Engine -->
      <section id="link-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">URL Sandbox Engine</h2>
            <div class="section-sub">Detonate suspicious links in an isolated environment before allow-listing</div>
          </div>
        </div>
        <div class="analysis-card">
          <div class="form-group">
            <label class="form-label">Target URL</label>
            <div style="display:flex; gap:.6rem;">
              <input class="input-control" id="url-input" placeholder="https://example.com/reset-password">
              <button class="btn" id="url-analyze-btn" style="flex-shrink:0;">Detonate</button>
            </div>
          </div>
          <div id="url-result" class="result-box">
            <div class="threat-score-gauge">
              <div class="score-circle" id="url-score-circle">—</div>
              <div><div class="result-title" id="url-result-title">—</div><div class="result-desc" id="url-result-desc">—</div></div>
            </div>
            <ul class="indicator-list" id="url-indicators"></ul>
          </div>
        </div>
      </section>

      <!-- 8b. Security Case Review -->
      <section id="cases-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Security Case Review</h2>
            <div class="section-sub">Investigate, label, and export cases generated by the Email, Telephony, and URL analyzers</div>
          </div>
        </div>

        <div class="panel-card" style="margin-bottom:1.25rem;">
          <div class="form-row" style="align-items:flex-end;">
            <div class="form-group">
              <label class="form-label">Search</label>
              <input class="input-control" id="case-search" placeholder="Search subject or case ID…">
            </div>
            <div class="form-group">
              <label class="form-label">Risk Level</label>
              <select class="input-control" id="case-filter-risk">
                <option value="all">All Risk Levels</option>
                <option value="high">High Risk</option>
                <option value="med">Suspicious</option>
                <option value="low">Likely Safe</option>
              </select>
            </div>
            <div class="form-group">
              <label class="form-label">Media Type</label>
              <select class="input-control" id="case-filter-type">
                <option value="all">All Types</option>
                <option value="Email">Email</option>
                <option value="Call/SMS">Call / SMS</option>
                <option value="URL">URL</option>
              </select>
            </div>
            <div class="form-group">
              <label class="form-label">Disposition</label>
              <select class="input-control" id="case-filter-status">
                <option value="all">All Statuses</option>
                <option value="Needs Review">Needs Review</option>
                <option value="Suspected">Suspected</option>
                <option value="Verified">Verified</option>
              </select>
            </div>
            <button class="btn btn-secondary" id="case-filter-reset">Reset</button>
          </div>
        </div>

        <div class="data-table-container">
          <div class="table-scroll">
            <table class="data-table" id="cases-table">
              <thead>
                <tr><th>Case ID</th><th>Type</th><th>Subject</th><th>Risk Score</th><th>Disposition</th><th>Investigator Note</th><th>Actions</th></tr>
              </thead>
              <tbody id="cases-tbody"></tbody>
            </table>
            <div id="cases-empty" style="display:none; padding:2rem; text-align:center; color:var(--text-muted); font-size:.8rem;">No cases match the current filters.</div>
          </div>
        </div>
      </section>

      <!-- 9. Endpoint Containment -->
      <section id="ransomware-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Endpoint Containment</h2>
            <div class="section-sub">Isolate compromised hosts to halt lateral movement</div>
          </div>
        </div>
        <div class="endpoint-grid" id="endpoint-grid">
          <div class="endpoint-card isolated" data-host="FIN-WKS-014">
            <div class="endpoint-top"><div><div class="endpoint-name">FIN-WKS-014</div><div class="endpoint-meta">Finance · 10.4.12.14</div></div><span class="badge badge-critical">Isolated</span></div>
            <div class="endpoint-meta">Ransomware behavior detected — file encryption pattern matched</div>
            <div class="endpoint-actions"><button class="btn btn-sm btn-success act-restore">Restore Network</button></div>
          </div>
          <div class="endpoint-card" data-host="ENG-LT-221">
            <div class="endpoint-top"><div><div class="endpoint-name">ENG-LT-221</div><div class="endpoint-meta">Engineering · 10.2.4.221</div></div><span class="badge badge-success">Healthy</span></div>
            <div class="endpoint-meta">No anomalies in the last 24h</div>
            <div class="endpoint-actions"><button class="btn btn-sm btn-danger act-isolate">Isolate Host</button></div>
          </div>
          <div class="endpoint-card" data-host="SALES-MBP-08">
            <div class="endpoint-top"><div><div class="endpoint-name">SALES-MBP-08</div><div class="endpoint-meta">Sales · 10.6.1.8</div></div><span class="badge badge-warning">Monitoring</span></div>
            <div class="endpoint-meta">Unusual outbound traffic to unclassified host</div>
            <div class="endpoint-actions"><button class="btn btn-sm btn-danger act-isolate">Isolate Host</button></div>
          </div>
        </div>
      </section>

      <!-- 10. Audit Logs -->
      <!-- Privacy & Data Protection -->
      <section id="privacy-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Privacy &amp; Data Protection</h2>
            <div class="section-sub">Data subject requests, data inventory &amp; consent posture</div>
          </div>
        </div>

        <div class="metrics-grid">
          <div class="metric-card">
            <div class="metric-card-title">OPEN DSARs</div>
            <div class="metric-card-value">3</div>
            <div class="metric-card-subtext neutral">1 access, 1 deletion, 1 export</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">AVG. RESPONSE TIME</div>
            <div class="metric-card-value">6.2 days</div>
            <div class="metric-card-subtext">Target: within 30 days</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">PII DATA STORES MONITORED</div>
            <div class="metric-card-value">27</div>
            <div class="metric-card-subtext">All encrypted at rest</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">CONSENT OPT-OUT RATE</div>
            <div class="metric-card-value">4.1%</div>
            <div class="metric-card-subtext neutral">Stable vs last quarter</div>
          </div>
        </div>

        <div class="data-table-container">
          <div class="table-header">
            <div class="table-title">Data Subject Access Requests (DSARs)</div>
            <span class="badge badge-info">● TRACKED</span>
          </div>
          <div class="table-scroll">
            <table class="data-table">
              <thead><tr><th>Request ID</th><th>Type</th><th>Requester</th><th>Received</th><th>Status</th></tr></thead>
              <tbody>
                <tr><td class="mono">DSAR-241</td><td>Data Access</td><td>customer@domain.com</td><td>2 days ago</td><td><span class="badge badge-warning">In Progress</span></td></tr>
                <tr><td class="mono">DSAR-240</td><td>Deletion Request</td><td>user@webmail.com</td><td>4 days ago</td><td><span class="badge badge-warning">In Progress</span></td></tr>
                <tr><td class="mono">DSAR-239</td><td>Data Export</td><td>partner@vendor.co</td><td>6 days ago</td><td><span class="badge badge-info">Awaiting Verification</span></td></tr>
                <tr><td class="mono">DSAR-238</td><td>Data Access</td><td>employee@corp.local</td><td>11 days ago</td><td><span class="badge badge-success">Fulfilled</span></td></tr>
              </tbody>
            </table>
          </div>
        </div>

        <div class="data-table-container" style="margin-top:1.5rem;">
          <div class="table-header">
            <div class="table-title">Sensitive Data Inventory</div>
          </div>
          <div class="table-scroll">
            <table class="data-table">
              <thead><tr><th>Data Store</th><th>Classification</th><th>Encryption</th><th>Retention</th><th>Owner</th></tr></thead>
              <tbody>
                <tr><td>Customer CRM Database</td><td><span class="badge badge-critical">Restricted — PII</span></td><td><span class="badge badge-success">AES-256</span></td><td>7 years</td><td>Sales Ops</td></tr>
                <tr><td>HR Payroll System</td><td><span class="badge badge-critical">Restricted — PII</span></td><td><span class="badge badge-success">AES-256</span></td><td>10 years</td><td>People Team</td></tr>
                <tr><td>Support Ticket Archive</td><td><span class="badge badge-warning">Confidential</span></td><td><span class="badge badge-success">AES-256</span></td><td>3 years</td><td>Support</td></tr>
                <tr><td>Marketing Analytics Warehouse</td><td><span class="badge badge-info">Internal</span></td><td><span class="badge badge-success">TLS + at-rest</span></td><td>18 months</td><td>Marketing</td></tr>
              </tbody>
            </table>
          </div>
        </div>

        <div class="panel-card" style="margin-top:1.5rem;">
          <div class="form-label" style="margin-bottom:.8rem; font-size:.8rem;">Consent &amp; Data Minimization Controls</div>
          <div class="metric-row" style="display:flex; align-items:center; justify-content:space-between; padding:.5rem 0; border-bottom:1px solid var(--border-color);">
            <span style="font-size:.8rem; color:var(--text-muted);">Require explicit opt-in for analytics cookies</span>
            <span class="badge badge-success">Enabled</span>
          </div>
          <div class="metric-row" style="display:flex; align-items:center; justify-content:space-between; padding:.5rem 0; border-bottom:1px solid var(--border-color);">
            <span style="font-size:.8rem; color:var(--text-muted);">Auto-purge inactive customer data after retention window</span>
            <span class="badge badge-success">Enabled</span>
          </div>
          <div class="metric-row" style="display:flex; align-items:center; justify-content:space-between; padding:.5rem 0;">
            <span style="font-size:.8rem; color:var(--text-muted);">Third-party data sharing agreements under review</span>
            <span class="badge badge-warning">2 pending</span>
          </div>
        </div>
      </section>

      <!-- Digital Resilience & Business Continuity -->
      <section id="resilience-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Digital Resilience &amp; Business Continuity</h2>
            <div class="section-sub">Backup health, recovery objectives &amp; disaster recovery readiness</div>
          </div>
        </div>

        <div class="metrics-grid">
          <div class="metric-card">
            <div class="metric-card-title">RESILIENCE SCORE</div>
            <div class="metric-card-value">94%</div>
            <div class="metric-card-subtext">▲ 2 pts vs last drill</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">BACKUP SUCCESS RATE (30d)</div>
            <div class="metric-card-value">99.6%</div>
            <div class="metric-card-subtext neutral">2 retried jobs, 0 failed</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">RTO / RPO TARGET</div>
            <div class="metric-card-value">4h / 15m</div>
            <div class="metric-card-subtext">Recovery time / recovery point objective</div>
          </div>
          <div class="metric-card">
            <div class="metric-card-title">LAST DR DRILL</div>
            <div class="metric-card-value">19 days ago</div>
            <div class="metric-card-subtext neutral">Next scheduled in 41 days</div>
          </div>
        </div>

        <div class="data-table-container">
          <div class="table-header">
            <div class="table-title">Backup Job Status</div>
            <span class="badge badge-info">● LIVE</span>
          </div>
          <div class="table-scroll">
            <table class="data-table">
              <thead><tr><th>Job</th><th>System</th><th>Last Run</th><th>Size</th><th>Status</th></tr></thead>
              <tbody>
                <tr><td>Nightly Full — Prod DB</td><td>customer-db-01</td><td>3 hr ago</td><td>412 GB</td><td><span class="badge badge-success">Success</span></td></tr>
                <tr><td>Hourly Incremental — App Storage</td><td>app-storage-cluster</td><td>22 min ago</td><td>18 GB</td><td><span class="badge badge-success">Success</span></td></tr>
                <tr><td>Nightly Full — File Server</td><td>fs-corp-02</td><td>3 hr ago</td><td>1.1 TB</td><td><span class="badge badge-warning">Retried Once</span></td></tr>
                <tr><td>Weekly Offline Snapshot</td><td>cold-storage-vault</td><td>2 days ago</td><td>3.4 TB</td><td><span class="badge badge-success">Success</span></td></tr>
              </tbody>
            </table>
          </div>
        </div>

        <div class="data-table-container" style="margin-top:1.5rem;">
          <div class="table-header">
            <div class="table-title">Disaster Recovery &amp; Continuity Runbooks</div>
          </div>
          <div class="table-scroll">
            <table class="data-table">
              <thead><tr><th>Scenario</th><th>Owner</th><th>Last Tested</th><th>Readiness</th></tr></thead>
              <tbody>
                <tr><td>Primary Data Center Outage</td><td>Infrastructure</td><td>19 days ago</td><td><span class="badge badge-success">Ready</span></td></tr>
                <tr><td>Ransomware — Full Environment Restore</td><td>SOC / Infra</td><td>41 days ago</td><td><span class="badge badge-warning">Needs Retest</span></td></tr>
                <tr><td>Key Vendor / SaaS Outage</td><td>IT Ops</td><td>63 days ago</td><td><span class="badge badge-warning">Needs Retest</span></td></tr>
                <tr><td>Regional Cloud Region Failover</td><td>Infrastructure</td><td>12 days ago</td><td><span class="badge badge-success">Ready</span></td></tr>
              </tbody>
            </table>
          </div>
        </div>

        <div class="panel-card" style="margin-top:1.5rem;">
          <div class="form-label" style="margin-bottom:.8rem; font-size:.8rem;">Redundancy Posture</div>
          <div class="metric-row" style="display:flex; align-items:center; justify-content:space-between; padding:.5rem 0; border-bottom:1px solid var(--border-color);">
            <span style="font-size:.8rem; color:var(--text-muted);">Multi-region database replication</span>
            <span class="badge badge-success">Active</span>
          </div>
          <div class="metric-row" style="display:flex; align-items:center; justify-content:space-between; padding:.5rem 0; border-bottom:1px solid var(--border-color);">
            <span style="font-size:.8rem; color:var(--text-muted);">Offline / air-gapped backup copy</span>
            <span class="badge badge-success">Active</span>
          </div>
          <div class="metric-row" style="display:flex; align-items:center; justify-content:space-between; padding:.5rem 0;">
            <span style="font-size:.8rem; color:var(--text-muted);">Secondary internet / ISP failover</span>
            <span class="badge badge-warning">Provisioning</span>
          </div>
        </div>
      </section>

      <section id="analytics-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Audit Logs</h2>
            <div class="section-sub">Full trail of analyst and system actions</div>
          </div>
          <input class="input-control" id="audit-filter" placeholder="Filter logs…" style="max-width:220px;">
        </div>
        <div class="data-table-container">
          <div class="table-scroll">
            <table class="data-table" id="audit-table">
              <thead><tr><th>Timestamp</th><th>Actor</th><th>Action</th><th>Target</th></tr></thead>
              <tbody id="audit-tbody">
                <tr><td class="mono">2026-08-06 09:12:03</td><td>system.ai</td><td>Auto-quarantined message</td><td class="mono">INC-8899</td></tr>
                <tr><td class="mono">2026-08-06 08:47:51</td><td>r.iyer</td><td>Escalated incident</td><td class="mono">INC-8902</td></tr>
                <tr><td class="mono">2026-08-05 22:03:10</td><td>system.ai</td><td>Isolated endpoint</td><td class="mono">FIN-WKS-014</td></tr>
                <tr><td class="mono">2026-08-05 19:30:44</td><td>a.chen</td><td>Added firewall rule</td><td class="mono">Block Known Botnet C2</td></tr>
              </tbody>
            </table>
          </div>
        </div>
      </section>

      <!-- 11. SOC Configurations -->
      <section id="settings-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">SOC Configurations</h2>
            <div class="section-sub">Platform behavior, alerting, and AI assistant setup</div>
          </div>
        </div>

        <div class="panel-card">
          <div class="table-title">Automation</div>
          <div class="toggle-switch">
            <span><span class="tlabel">Auto-quarantine suspicious email</span><span class="tdesc">Immediately quarantines messages scoring above the risk threshold</span></span>
            <label class="switch"><input type="checkbox" checked><span class="slider"></span></label>
          </div>
          <div class="toggle-switch">
            <span><span class="tlabel">Auto-isolate compromised endpoints</span><span class="tdesc">Cuts network access on ransomware behavior detection</span></span>
            <label class="switch"><input type="checkbox" checked><span class="slider"></span></label>
          </div>
          <div class="toggle-switch">
            <span><span class="tlabel">Real-time analyst notifications</span><span class="tdesc">Sends a push alert for High and Critical severity incidents</span></span>
            <label class="switch"><input type="checkbox"><span class="slider"></span></label>
          </div>
        </div>

        <div class="panel-card">
          <div class="table-title">AI Assistant — Neural Engine Connection</div>
          <div class="form-hint" style="margin-bottom:.4rem;">Connect a Gemini API key to power the SOC assistant with live model responses. Without a key, the assistant runs on its built-in offline playbook logic.</div>
          <div class="form-row">
            <div class="form-group">
              <label class="form-label">Gemini API Key</label>
              <input class="input-control" id="gemini-key-input" type="password" placeholder="Paste your Gemini API key…">
            </div>
            <div class="form-group">
              <label class="form-label">Model</label>
              <select class="input-control" id="gemini-model-select">
                <option value="gemini-2.0-flash">gemini-2.0-flash</option>
                <option value="gemini-2.5-flash">gemini-2.5-flash</option>
                <option value="gemini-3.5-flash-lite">gemini-3.5-flash-lite</option>
                <option value="gemini-1.5-pro">gemini-1.5-pro</option>
              </select>
            </div>
          </div>
          <div style="display:flex; align-items:center; gap:.7rem;">
            <button class="btn" id="gemini-save-btn">Save &amp; Connect</button>
            <button class="btn btn-secondary" id="gemini-clear-btn">Disconnect</button>
            <span class="key-status-chip local" id="gemini-status-chip">Offline mode</span>
          </div>
          <div class="form-hint">The key is held in memory for this session only and is never written to disk or sent anywhere besides Google's Gemini API.</div>
        </div>
      </section>

      <!-- 12. Discover & Learn -->
      <section id="learn-view" class="view-section">
        <div class="section-header">
          <div>
            <h2 class="section-title">Discover &amp; Learn</h2>
            <div class="section-sub">Bite-sized cybersecurity topics to level up your SOC instincts</div>
          </div>
          <div class="streak-chip" id="streak-chip">🔥 <span id="streak-count">0</span> topics explored today</div>
        </div>

        <div class="learn-daily">
          <div class="learn-daily-badge">TODAY'S CHALLENGE</div>
          <div class="learn-daily-title">Can you spot the fake login page in under 30 seconds?</div>
          <div class="learn-daily-sub">A quick eye-training exercise on phishing site tells — URL quirks, cert warnings, and layout glitches.</div>
          <button class="btn btn-sm" id="learn-daily-btn">Take the challenge</button>
        </div>

        <div class="learn-hub-stats" id="learn-hub-stats"></div>

        <div class="learn-filter-row" id="learn-filter-row"></div>

        <div id="learn-categories"></div>
      </section>

    </div>
  </main>

  <!-- AI Assistant Widget -->
  <div class="case-brief-overlay" id="case-brief-overlay">
    <div class="case-brief-box" id="case-brief-box"></div>
  </div>

  <div class="ai-assistant-widget" id="ai-widget">
    <div class="ai-widget-header" id="ai-widget-toggle">
      <div class="ai-widget-title">
        <div class="cute-robot-avatar">🤖</div>
        <div class="ai-widget-titlewrap">
          <span>ARIA — SOC Assistant</span>
          <span class="ai-widget-status offline" id="ai-widget-status"><span class="d"></span>Offline mode</span>
        </div>
      </div>
      <button class="ai-widget-collapse-btn" id="ai-widget-collapse-btn">─</button>
    </div>
    <div class="ai-widget-body" id="ai-widget-body">
      <div class="assistant-row">
        <div class="assistant-avatar-sm">🤖</div>
        <div class="assistant-msg agent" id="ai-response">Hi, I'm ARIA. I can help you triage alerts, interpret scores, and suggest containment playbooks. Ask me anything about the current SOC state.</div>
      </div>
    </div>
    <div class="ai-playbooks" id="ai-playbooks">
      <button class="playbook-btn" data-prompt="Summarize current active incidents">Summarize incidents</button>
      <button class="playbook-btn" data-prompt="What should I do about a phishing email?">Phishing playbook</button>
      <button class="playbook-btn" data-prompt="Walk me through isolating a compromised endpoint">Isolate endpoint</button>
      <button class="playbook-btn" data-prompt="Explain the current threat index">Threat index</button>
    </div>
    <div class="ai-widget-footer">
      <input class="input-control" id="ai-input" placeholder="Ask ARIA about your SOC…">
      <button class="ai-send-btn" id="ai-send-btn" aria-label="Send">➤</button>
    </div>
  </div>
  
  <!--live-background-->
  <video autoplay muted loop playinline id="bg-video">
    <source src="background-black-ops.mp4" type="video/mp4">

  </video>

<script>
(function(){
  "use strict";

  /* ---------------- Background video safety net ---------------- */
  const bgVideo = document.getElementById('bg-video');
  if (bgVideo && !window.matchMedia('(prefers-reduced-motion: reduce)').matches) {
    const tryPlay = () => bgVideo.play().catch(() => {});
    tryPlay();
    document.addEventListener('click', tryPlay, { once:true });
  }

  /* ---------------- Nav / view switching ---------------- */
  const sections = document.querySelectorAll('.view-section');

  function activateView(target){
    if (!target) return;
    sections.forEach(s => s.classList.toggle('active', s.id === target));
    window.scrollTo({top:0, behavior:'smooth'});
  }

  // profile-dropdown quick links
  document.querySelectorAll('.profile-item[data-target]').forEach(item => {
    item.addEventListener('click', () => activateView(item.dataset.target));
  });

  /* ---------------- Apple-style mega menu ---------------- */
  const megaItems = document.querySelectorAll('.mega-item');
  megaItems.forEach(item => {
    const trigger = item.querySelector('.mega-item-trigger');
    trigger.addEventListener('click', (e) => {
      e.stopPropagation();
      const wasOpen = item.classList.contains('open');
      megaItems.forEach(i => i.classList.remove('open'));
      if (!wasOpen) item.classList.add('open');
    });
  });
  document.addEventListener('click', (e) => {
    if (!e.target.closest('.mega-nav')) megaItems.forEach(i => i.classList.remove('open'));
  });
  document.querySelectorAll('.mega-link[data-target]').forEach(item => {
    item.addEventListener('click', () => {
      activateView(item.dataset.target);
      megaItems.forEach(i => i.classList.remove('open'));
    });
  });

  /* ---------------- Profile dropdown ---------------- */
  const profileMenu = document.getElementById('profile-menu');
  const profileTrigger = document.getElementById('profile-trigger');
  profileTrigger.addEventListener('click', (e) => { e.stopPropagation(); profileMenu.classList.toggle('open'); });
  document.addEventListener('click', (e) => { if (!profileMenu.contains(e.target)) profileMenu.classList.remove('open'); });
  document.querySelectorAll('.profile-item').forEach(item => item.addEventListener('click', () => profileMenu.classList.remove('open')));

  /* ---------------- Notification center ---------------- */
  const notifMenu = document.getElementById('notif-menu');
  const notifBtn = document.getElementById('notif-btn');
  const notifList = document.getElementById('notif-list');
  const notifBadge = document.getElementById('notif-badge-count');
  const notifMarkAll = document.getElementById('notif-mark-all');
  const notifViewAll = document.getElementById('notif-view-all');

  let notifications = [
    { id:5, type:'critical', title:'SQL Injection Attempt Blocked', desc:'INC-8902 isolated at the perimeter firewall. Requires analyst review.', time:'2 min ago', target:'threats-view', unread:true },
    { id:4, type:'warning', title:'Elevated login attempts', desc:'12 failed attempts from 203.0.113.9 in the last 5 minutes.', time:'14 min ago', target:'analytics-view', unread:true },
    { id:3, type:'warning', title:'Suspicious domain flagged', desc:'DNS query to a newly registered domain queued for review.', time:'27 min ago', target:'link-view', unread:true },
    { id:2, type:'success', title:'Vulnerability scan complete', desc:'Nightly scan finished — 0 critical findings across 214 assets.', time:'1 hr ago', target:'analytics-view', unread:false },
    { id:1, type:'info', title:'AI classifier updated', desc:'Neural detection model refreshed to checkpoint v4.12.3.', time:'3 hr ago', target:'ai-view', unread:false },
  ];
  let notifSeq = 6;
  const notifIcon = { critical:'⛔', warning:'⚠', success:'✔', info:'ℹ' };

  function renderNotifications(flashId){
    const unreadCount = notifications.filter(n => n.unread).length;
    notifBadge.textContent = unreadCount > 9 ? '9+' : String(unreadCount);
    notifBadge.classList.toggle('hidden', unreadCount === 0);

    if (!notifications.length) {
      notifList.innerHTML = '<div class="notif-empty">You\'re all caught up — no notifications.</div>';
      return;
    }
    notifList.innerHTML = notifications.map(n => `
      <div class="notif-item ${n.unread ? 'unread' : ''} ${n.id === flashId ? 'new-flash' : ''}" data-id="${n.id}" data-target="${n.target}">
        <div class="notif-icon ${n.type}">${notifIcon[n.type]}</div>
        <div class="notif-body">
          <div class="notif-title">${n.title}</div>
          <div class="notif-desc">${n.desc}</div>
          <div class="notif-time">${n.time}</div>
        </div>
      </div>
    `).join('');
  }
  renderNotifications();

  notifBtn.addEventListener('click', (e) => { e.stopPropagation(); notifMenu.classList.toggle('open'); });
  document.addEventListener('click', (e) => { if (!notifMenu.contains(e.target)) notifMenu.classList.remove('open'); });

  notifMarkAll.addEventListener('click', (e) => {
    e.stopPropagation();
    notifications.forEach(n => n.unread = false);
    renderNotifications();
  });

  notifList.addEventListener('click', (e) => {
    const row = e.target.closest('.notif-item');
    if (!row) return;
    const id = Number(row.dataset.id);
    const n = notifications.find(x => x.id === id);
    if (n) n.unread = false;
    renderNotifications();
    activateView(row.dataset.target);
    notifMenu.classList.remove('open');
  });

  notifViewAll.addEventListener('click', (e) => {
    e.preventDefault();
    activateView('analytics-view');
    notifMenu.classList.remove('open');
  });

  /* Simulate live incoming SOC notifications */
  const liveNotifPool = [
    { type:'critical', title:'Ransomware signature detected', desc:'Endpoint FIN-WK-114 flagged for suspicious file encryption behavior.', target:'ransomware-view' },
    { type:'warning', title:'Phishing campaign spike', desc:'Inbound volume from a spoofed domain up 340% in the last hour.', target:'phishing-view' },
    { type:'warning', title:'New outbound connection', desc:'Unrecognized destination IP contacted from the finance VLAN.', target:'firewall-view' },
    { type:'info', title:'Threat intel feed synced', desc:'14,203 new indicators of compromise ingested.', target:'analytics-view' },
    { type:'success', title:'Incident auto-resolved', desc:'Low-confidence alert closed automatically after 24h with no recurrence.', target:'threats-view' },
  ];
  function pushLiveNotification(){
    const pick = liveNotifPool[Math.floor(Math.random()*liveNotifPool.length)];
    const n = { id: notifSeq++, type:pick.type, title:pick.title, desc:pick.desc, time:'just now', target:pick.target, unread:true };
    notifications.unshift(n);
    if (notifications.length > 12) notifications.pop();
    renderNotifications(n.id);
    notifBadge.classList.remove('hidden');
  }
  setInterval(pushLiveNotification, 26000);

  /* ---------------- Live network wallpaper (canvas) ---------------- */
  (function(){
    const canvas = document.getElementById('bg-canvas');
    if (!canvas || window.matchMedia('(prefers-reduced-motion: reduce)').matches) return;
    const ctx = canvas.getContext('2d');
    let w, h, nodes;
    const NODE_COUNT_BASE = 70;

    function resize(){
      w = canvas.width = window.innerWidth;
      h = canvas.height = window.innerHeight;
      const count = Math.max(30, Math.min(90, Math.round((w*h)/22000)));
      nodes = Array.from({length: count}, () => ({
        x: Math.random()*w, y: Math.random()*h,
        vx: (Math.random()-0.5)*0.35, vy: (Math.random()-0.5)*0.35,
        r: Math.random()*1.6 + 0.6
      }));
    }
    window.addEventListener('resize', resize);
    resize();

    const mouse = { x: -9999, y: -9999 };
    window.addEventListener('mousemove', e => { mouse.x = e.clientX; mouse.y = e.clientY; });
    window.addEventListener('mouseleave', () => { mouse.x = -9999; mouse.y = -9999; });

    const LINK_DIST = 150;

    function frame(){
      ctx.clearRect(0,0,w,h);
      for (const n of nodes) {
        n.x += n.vx; n.y += n.vy;
        if (n.x < 0 || n.x > w) n.vx *= -1;
        if (n.y < 0 || n.y > h) n.vy *= -1;
      }
      for (let i=0; i<nodes.length; i++){
        for (let j=i+1; j<nodes.length; j++){
          const a = nodes[i], b = nodes[j];
          const dx = a.x-b.x, dy = a.y-b.y;
          const dist = Math.sqrt(dx*dx+dy*dy);
          if (dist < LINK_DIST) {
            ctx.strokeStyle = `rgba(56,189,248,${(1 - dist/LINK_DIST) * 0.16})`;
            ctx.lineWidth = 1;
            ctx.beginPath(); ctx.moveTo(a.x,a.y); ctx.lineTo(b.x,b.y); ctx.stroke();
          }
        }
      }
      // mouse proximity links
      for (const n of nodes) {
        const dx = n.x - mouse.x, dy = n.y - mouse.y;
        const dist = Math.sqrt(dx*dx+dy*dy);
        if (dist < 170) {
          ctx.strokeStyle = `rgba(56,189,248,${(1 - dist/170) * 0.35})`;
          ctx.lineWidth = 1;
          ctx.beginPath(); ctx.moveTo(n.x,n.y); ctx.lineTo(mouse.x,mouse.y); ctx.stroke();
        }
      }
      for (const n of nodes) {
        ctx.beginPath();
        ctx.arc(n.x, n.y, n.r, 0, Math.PI*2);
        ctx.fillStyle = 'rgba(148,197,255,0.55)';
        ctx.fill();
      }
      requestAnimationFrame(frame);
    }
    requestAnimationFrame(frame);
  })();

  /* ---------------- Clock ---------------- */
  const clockEl = document.getElementById('clock');
  function tickClock(){
    const d = new Date();
    clockEl.textContent = d.toLocaleString('en-US', { weekday:'short', hour:'2-digit', minute:'2-digit', second:'2-digit', hour12:false });
  }
  tickClock(); setInterval(tickClock, 1000);

  /* ---------------- Live threat ticker feed ---------------- */
  const tickerTrack = document.getElementById('live-ticker-track');
  const tickerFacts = [
    'Global threat index: <b>LOW</b>',
    '<span>14,203</span> IOCs synced in the last sync cycle',
    '<span>203.0.113.9</span> flagged for elevated login attempts',
    'AI classifier confidence: <b>98.4%</b>',
    'Perimeter firewall blocked <span>1,842</span> connections in the last hour',
    'Endpoint fleet health: <b>214/214</b> reporting',
    'Last vulnerability scan: <b>0</b> critical findings',
    'Phishing gateway processed <span>3,910</span> messages today',
  ];
  function buildTicker(){
    const text = tickerFacts.join('&nbsp;&nbsp;•&nbsp;&nbsp;');
    tickerTrack.innerHTML = text + '&nbsp;&nbsp;•&nbsp;&nbsp;' + text; // duplicate for seamless loop
  }
  buildTicker();

  /* ---------------- Mega-nav live incident stat ---------------- */
  const megaOpenIncidents = document.getElementById('mega-open-incidents');
  function refreshMegaStat(){
    if (!megaOpenIncidents) return;
    const count = document.querySelectorAll('#incidents-tbody .status-cell.badge-warning, #incidents-tbody .status-cell.badge-critical').length;
    megaOpenIncidents.textContent = count;
  }
  refreshMegaStat();
  setInterval(refreshMegaStat, 5000);

  /* ---------------- Threat Intel mega-nav item ---------------- */
  const intelAttacks = document.getElementById('mega-intel-attacks');
  const intelCountries = document.getElementById('mega-intel-countries');
  const liveStrip = document.getElementById('mega-live-strip');
  const intelOrigins = [
    {flag:'🇷🇺', label:'RU'}, {flag:'🇨🇳', label:'CN'}, {flag:'🇧🇷', label:'BR'},
    {flag:'🇻🇳', label:'VN'}, {flag:'🇳🇬', label:'NG'}, {flag:'🇺🇸', label:'US'},
  ];
  function refreshThreatIntel(){
    if (intelAttacks) intelAttacks.textContent = (18400 + Math.round(Math.random()*900)).toLocaleString();
    if (intelCountries) intelCountries.textContent = 41 + Math.round(Math.random()*4);
    if (liveStrip) {
      liveStrip.innerHTML = intelOrigins.map(o =>
        `<span class="mega-live-chip"><span class="flag">${o.flag}</span>${o.label} <span class="cnt">${Math.round(Math.random()*140)+5}</span></span>`
      ).join('');
    }
  }
  refreshThreatIntel();
  setInterval(refreshThreatIntel, 6000);

  /* ---------------- Command palette (⌘K quick search) ---------------- */
  const cmdkOverlay = document.getElementById('cmdk-overlay');
  const cmdkInput = document.getElementById('cmdk-input');
  const cmdkResults = document.getElementById('cmdk-results');
  const cmdkTrigger = document.getElementById('mega-search-trigger');

  const cmdkIndex = [];
  const seenTargets = new Set();
  document.querySelectorAll('.mega-link[data-target]').forEach(link => {
    const target = link.dataset.target;
    const title = link.querySelector('.mega-link-title')?.textContent.trim();
    const desc = link.querySelector('.mega-link-desc')?.textContent.trim() || '';
    const icon = link.querySelector('.mega-ico')?.textContent.trim() || '◈';
    const key = target + '|' + title;
    if (!title || seenTargets.has(key)) return;
    seenTargets.add(key);
    cmdkIndex.push({ target, title, desc, icon, group:'Go to' });
  });
  cmdkIndex.push(
    { target:'report-threat-view', title:'Report a new threat', desc:'Quick action', icon:'⚑', group:'Actions' },
    { target:'settings-view', title:'Open SOC configurations', desc:'Quick action', icon:'⚙', group:'Actions' },
  );

  let cmdkActiveIndex = 0;
  let cmdkCurrentList = [];

  function renderCmdkResults(query){
    const q = query.trim().toLowerCase();
    cmdkCurrentList = !q ? cmdkIndex : cmdkIndex.filter(item =>
      item.title.toLowerCase().includes(q) || item.desc.toLowerCase().includes(q)
    );
    cmdkActiveIndex = 0;
    if (!cmdkCurrentList.length) {
      cmdkResults.innerHTML = '<div class="cmdk-empty">No matches. Try “phishing”, “audit”, or “settings”.</div>';
      return;
    }
    let lastGroup = '';
    cmdkResults.innerHTML = cmdkCurrentList.map((item, i) => {
      const groupHtml = item.group !== lastGroup ? `<div class="cmdk-result-group">${item.group}</div>` : '';
      lastGroup = item.group;
      return `${groupHtml}<div class="cmdk-result${i === cmdkActiveIndex ? ' active' : ''}" data-idx="${i}">
        <span class="mega-ico">${item.icon}</span>
        <span><div class="cmdk-result-title">${item.title}</div><div class="cmdk-result-desc">${item.desc}</div></span>
      </div>`;
    }).join('');
  }

  function updateCmdkActive(){
    cmdkResults.querySelectorAll('.cmdk-result').forEach(el => {
      el.classList.toggle('active', Number(el.dataset.idx) === cmdkActiveIndex);
    });
    cmdkResults.querySelector('.cmdk-result.active')?.scrollIntoView({ block:'nearest' });
  }

  function openCmdk(){
    cmdkOverlay.classList.add('open');
    renderCmdkResults('');
    cmdkInput.value = '';
    setTimeout(() => cmdkInput.focus(), 30);
  }
  function closeCmdk(){
    cmdkOverlay.classList.remove('open');
  }
  function selectCmdkItem(item){
    if (!item) return;
    activateView(item.target);
    closeCmdk();
  }

  cmdkTrigger?.addEventListener('click', openCmdk);
  cmdkOverlay.addEventListener('click', e => { if (e.target === cmdkOverlay) closeCmdk(); });
  cmdkInput.addEventListener('input', () => renderCmdkResults(cmdkInput.value));
  cmdkResults.addEventListener('click', e => {
    const row = e.target.closest('.cmdk-result');
    if (row) selectCmdkItem(cmdkCurrentList[Number(row.dataset.idx)]);
  });
  document.addEventListener('keydown', e => {
    if ((e.metaKey || e.ctrlKey) && e.key.toLowerCase() === 'k') {
      e.preventDefault();
      cmdkOverlay.classList.contains('open') ? closeCmdk() : openCmdk();
      return;
    }
    if (!cmdkOverlay.classList.contains('open')) return;
    if (e.key === 'Escape') { closeCmdk(); return; }
    if (e.key === 'ArrowDown') { e.preventDefault(); cmdkActiveIndex = Math.min(cmdkActiveIndex + 1, cmdkCurrentList.length - 1); updateCmdkActive(); }
    if (e.key === 'ArrowUp') { e.preventDefault(); cmdkActiveIndex = Math.max(cmdkActiveIndex - 1, 0); updateCmdkActive(); }
    if (e.key === 'Enter') { e.preventDefault(); selectCmdkItem(cmdkCurrentList[cmdkActiveIndex]); }
  });

  /* ---------------- System load simulation ---------------- */
  function jitter(el, barEl, base, range){
    const val = Math.max(4, Math.min(96, Math.round(base + (Math.random()-0.5)*range)));
    el.textContent = val + '%';
    barEl.style.width = val + '%';
  }
  setInterval(() => {
    jitter(document.getElementById('cpu-val'), document.getElementById('cpu-bar'), 26, 18);
    jitter(document.getElementById('ram-val'), document.getElementById('ram-bar'), 58, 10);
  }, 3500);

  /* ---------------- Live console log stream ---------------- */
  const consoleLogs = document.getElementById('console-logs');
  const logPool = [
    {t:'info', m:'Heuristic scan complete — 0 anomalies in outbound queue.'},
    {t:'info', m:'Threat intel feed synced (14,203 new IOCs ingested).'},
    {t:'warn', m:'Elevated login attempts detected from 203.0.113.9 — monitoring.'},
    {t:'info', m:'Endpoint ENG-LT-221 heartbeat OK.'},
    {t:'crit', m:'Signature match: known C2 beacon pattern blocked at perimeter.'},
    {t:'info', m:'Nightly vulnerability scan queued for 02:00 UTC.'},
    {t:'warn', m:'DNS query to newly registered domain flagged for review.'},
    {t:'info', m:'AI classifier model checkpoint refreshed (v4.12.3).'},
  ];
  function pushLog(){
    const item = logPool[Math.floor(Math.random()*logPool.length)];
    const cls = item.t === 'crit' ? 'tag-crit' : (item.t === 'warn' ? 'tag-warn' : '');
    const time = new Date().toLocaleTimeString('en-US', {hour12:false});
    const p = document.createElement('p');
    p.innerHTML = `<span class="tag-time">[${time}]</span><span class="${cls}">${item.m}</span>`;
    consoleLogs.prepend(p);
    while (consoleLogs.children.length > 40) consoleLogs.removeChild(consoleLogs.lastChild);
  }
  setInterval(pushLog, 4200);

  /* ---------------- Threat report form -> incident queue ---------------- */
  let incidentCounter = 8910;
  const incidentsTbody = document.getElementById('incidents-tbody');
  const ingressTbody = document.querySelector('#ingress-table tbody');
  const metricIncidents = document.getElementById('metric-incidents-count');

  document.getElementById('threat-report-form').addEventListener('submit', function(e){
    e.preventDefault();
    const vector = document.getElementById('rpt-vector').value || 'Unclassified';
    const severity = document.getElementById('rpt-severity').value;
    const source = document.getElementById('rpt-source').value;
    const id = 'INC-' + (incidentCounter++);
    const badgeClass = severity === 'Critical' ? 'badge-critical' : severity === 'High' ? 'badge-warning' : severity === 'Medium' ? 'badge-info' : 'badge-success';

    const row = document.createElement('tr');
    row.dataset.id = id;
    row.innerHTML = `
      <td class="mono">${id}</td><td>${vector}</td><td class="mono">${source}</td>
      <td><span class="badge ${badgeClass}">${severity}</span></td>
      <td><span class="badge badge-warning status-cell">Open</span></td>
      <td style="display:flex; gap:.4rem;">
        <button class="btn btn-sm btn-success act-resolve">Resolve</button>
        <button class="btn btn-sm btn-secondary act-escalate">Escalate</button>
      </td>`;
    incidentsTbody.prepend(row);

    const ingressRow = document.createElement('tr');
    ingressRow.innerHTML = `<td class="mono">${id}</td><td>${vector}</td><td class="mono">${source}</td><td><span class="badge ${badgeClass}">${severity}</span></td><td>Pending analyst review</td>`;
    ingressTbody.prepend(ingressRow);

    metricIncidents.textContent = parseInt(metricIncidents.textContent) + 1;
    pushLog();
    this.reset();
    document.getElementById('rpt-severity').value = 'Medium';

    // jump to incident view
    document.querySelector('[data-target="threats-view"]').click();
  });

  /* ---------------- Incident actions (delegated) ---------------- */
  incidentsTbody.addEventListener('click', function(e){
    const row = e.target.closest('tr');
    if (!row) return;
    if (e.target.classList.contains('act-resolve')) {
      const cell = row.querySelector('.status-cell');
      cell.textContent = 'Resolved';
      cell.className = 'badge badge-success status-cell';
      row.querySelectorAll('button').forEach(b => { b.disabled = true; });
      row.querySelector('.act-resolve').textContent = 'Closed';
      metricIncidents.textContent = Math.max(0, parseInt(metricIncidents.textContent) - 1);
      pushLog();
    }
    if (e.target.classList.contains('act-escalate')) {
      const cell = row.querySelector('.status-cell');
      cell.textContent = 'Escalated';
      cell.className = 'badge badge-critical status-cell';
      pushLog();
    }
  });

  /* ---------------- Firewall rules ---------------- */
  document.getElementById('fw-add-btn').addEventListener('click', function(){
    const name = document.getElementById('fw-name').value.trim();
    const target = document.getElementById('fw-target').value.trim();
    const dir = document.getElementById('fw-dir').value;
    const policy = document.getElementById('fw-policy').value;
    if (!name || !target) return;
    const badgeClass = policy === 'Block' ? 'badge-critical' : policy === 'Allow' ? 'badge-success' : 'badge-info';
    const row = document.createElement('tr');
    row.innerHTML = `<td>${name}</td><td class="mono">${target}</td><td>${dir}</td><td><span class="badge ${badgeClass}">${policy}</span></td><td><button class="icon-btn act-fw-remove" title="Remove">✕</button></td>`;
    document.getElementById('fw-tbody').prepend(row);
    document.getElementById('fw-name').value = '';
    document.getElementById('fw-target').value = '';
  });
  document.getElementById('fw-tbody').addEventListener('click', function(e){
    if (e.target.classList.contains('act-fw-remove')) e.target.closest('tr').remove();
  });

  /* ---------------- Endpoint containment ---------------- */
  document.getElementById('endpoint-grid').addEventListener('click', function(e){
    const card = e.target.closest('.endpoint-card');
    if (!card) return;
    if (e.target.classList.contains('act-isolate')) {
      card.classList.add('isolated');
      card.querySelector('.badge').className = 'badge badge-critical';
      card.querySelector('.badge').textContent = 'Isolated';
      e.target.outerHTML = '<button class="btn btn-sm btn-success act-restore">Restore Network</button>';
      pushLog();
    } else if (e.target.classList.contains('act-restore')) {
      card.classList.remove('isolated');
      card.querySelector('.badge').className = 'badge badge-success';
      card.querySelector('.badge').textContent = 'Healthy';
      e.target.outerHTML = '<button class="btn btn-sm btn-danger act-isolate">Isolate Host</button>';
      pushLog();
    }
  });

  /* ---------------- Analyzer scoring helper ---------------- */
  function scoreCircleClass(score){
    if (score >= 70) return 'high-risk';
    if (score >= 35) return 'med-risk';
    return 'low-risk';
  }
  function scoreLabel(score){
    if (score >= 70) return 'High Risk';
    if (score >= 35) return 'Suspicious';
    return 'Likely Safe';
  }

  function runAnalysis({ circleEl, titleEl, descEl, listEl, boxEl, score, indicators, subjectLabel }){
    circleEl.className = 'score-circle ' + scoreCircleClass(score);
    circleEl.textContent = score;
    titleEl.textContent = `${scoreLabel(score)} — ${subjectLabel}`;
    descEl.textContent = score >= 70
      ? 'Multiple strong risk indicators detected. Recommend blocking and escalating for analyst review.'
      : score >= 35
      ? 'Some risk indicators present. Recommend caution and further verification before acting.'
      : 'No significant risk indicators found based on available signals.';
    listEl.innerHTML = indicators.map(i => `<li>${i}</li>`).join('');
    boxEl.classList.add('active');
  }

  function heuristicScore(text, extra){
    text = (text || '').toLowerCase();
    let score = 8 + Math.round(Math.random()*10);
    const hits = [];
    const flagWords = [
      ['urgent', 'Urgency language pressuring immediate action'],
      ['verify your account', 'Requests account verification — common credential-harvest pattern'],
      ['click here', 'Generic call-to-action link phrasing'],
      ['password', 'References password / credentials directly'],
      ['bank', 'References banking or financial institution'],
      ['gift card', 'Gift card payment request — classic scam pattern'],
      ['wire transfer', 'Requests wire transfer of funds'],
      ['irs', 'Impersonates a government tax authority'],
      ['suspended', 'Threatens account suspension'],
      ['limited time', 'Artificial time pressure tactic'],
      ['confirm your', 'Requests confirmation of sensitive info'],
      ['won', 'Prize / lottery scam language'],
      ['social security', 'References Social Security number'],
      ['ceo', 'Potential executive impersonation (BEC)'],
    ];
    flagWords.forEach(([word, desc]) => {
      if (text.includes(word)) { score += 14; hits.push(desc); }
    });
    if (extra) { score += extra.bonus || 0; if (extra.reason) hits.push(extra.reason); }
    score = Math.max(2, Math.min(98, score));
    if (hits.length === 0) hits.push('No known malicious keyword or urgency patterns detected in supplied text.');
    return { score, hits };
  }

  document.getElementById('ph-analyze-btn').addEventListener('click', function(){
    const sender = document.getElementById('ph-sender').value;
    const body = document.getElementById('ph-body').value;
    let bonus = 0, reason = null;
    if (/\d/.test(sender) && /paypa1|amaz0n|micros0ft|g00gle/.test(sender.toLowerCase())) { bonus = 20; reason = 'Sender domain uses lookalike / typosquatted branding'; }
    const { score, hits } = heuristicScore(sender + ' ' + body, { bonus, reason });
    runAnalysis({
      circleEl: document.getElementById('ph-score-circle'), titleEl: document.getElementById('ph-result-title'),
      descEl: document.getElementById('ph-result-desc'), listEl: document.getElementById('ph-indicators'),
      boxEl: document.getElementById('ph-result'), score, indicators: hits, subjectLabel: 'Email Message'
    });
    addSecurityCase({ type: 'Email', subject: sender.trim() || 'Unlabeled sender address', score, indicators: hits });
    pushLog();
  });

  document.getElementById('tel-analyze-btn').addEventListener('click', function(){
    const num = document.getElementById('tel-number').value;
    const body = document.getElementById('tel-body').value;
    let bonus = 0, reason = null;
    if (/^\+?1?\s*8(00|33|44|55|66|77|88)/.test(num.replace(/[()\-\s]/g,''))) { bonus = 6; }
    if (/robocall|recorded message|press 1/.test(body.toLowerCase())) { bonus += 12; reason = 'Automated / robocall pattern detected in transcript'; }
    const { score, hits } = heuristicScore(body, { bonus, reason });
    runAnalysis({
      circleEl: document.getElementById('tel-score-circle'), titleEl: document.getElementById('tel-result-title'),
      descEl: document.getElementById('tel-result-desc'), listEl: document.getElementById('tel-indicators'),
      boxEl: document.getElementById('tel-result'), score, indicators: hits, subjectLabel: 'Call / SMS Contact'
    });
    addSecurityCase({ type: 'Call/SMS', subject: num.trim() || 'Unlabeled caller / sender number', score, indicators: hits });
    pushLog();
  });

  document.getElementById('url-analyze-btn').addEventListener('click', function(){
    const url = document.getElementById('url-input').value;
    let bonus = 0, reason = null;
    const lower = url.toLowerCase();
    if (/\d+\.\d+\.\d+\.\d+/.test(lower)) { bonus += 15; reason = 'Raw IP address used instead of a domain name'; }
    if (/-secure|-verify|-login|-update/.test(lower)) { bonus += 15; }
    if (!/^https:\/\//.test(lower) && lower.length > 0) { bonus += 10; }
    if ((lower.match(/\./g) || []).length > 3) { bonus += 8; }
    const { score, hits } = heuristicScore(url, { bonus, reason });
    runAnalysis({
      circleEl: document.getElementById('url-score-circle'), titleEl: document.getElementById('url-result-title'),
      descEl: document.getElementById('url-result-desc'), listEl: document.getElementById('url-indicators'),
      boxEl: document.getElementById('url-result'), score, indicators: hits, subjectLabel: 'URL'
    });
    addSecurityCase({ type: 'URL', subject: url.trim() || 'Unlabeled URL', score, indicators: hits });
    pushLog();
  });

  /* ---------------- Security Case Review (T196 · Fortress Protocol bounty) ---------------- */
  let caseSeq = 1;
  const securityCases = [];

  function riskBand(score){
    if (score >= 70) return 'high';
    if (score >= 35) return 'med';
    return 'low';
  }
  function riskBadgeClass(score){
    const b = riskBand(score);
    return b === 'high' ? 'badge-critical' : b === 'med' ? 'badge-warning' : 'badge-success';
  }

  function addSecurityCase({ type, subject, score, indicators, disposition, note }){
    const id = 'CASE-' + String(1000 + caseSeq++);
    const record = {
      id, type, subject, score,
      indicators: indicators && indicators.length ? indicators : ['No specific risk indicators recorded for this artifact.'],
      disposition: disposition || 'Needs Review',
      note: note || '',
      time: new Date().toLocaleString()
    };
    securityCases.unshift(record);
    renderCases();
    return record;
  }

  function escapeHtml(str){
    return String(str).replace(/[&<>"]/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;'}[c]));
  }

  function caseRowHtml(c){
    return `
      <tr data-case-id="${c.id}">
        <td class="mono">${c.id}</td>
        <td>${c.type}</td>
        <td>${escapeHtml(c.subject)}</td>
        <td><span class="badge ${riskBadgeClass(c.score)}">${c.score} · ${scoreLabel(c.score)}</span></td>
        <td>
          <select class="input-control case-disposition-select" style="padding:.3rem .5rem; font-size:.7rem;">
            <option ${c.disposition==='Needs Review'?'selected':''}>Needs Review</option>
            <option ${c.disposition==='Suspected'?'selected':''}>Suspected</option>
            <option ${c.disposition==='Verified'?'selected':''}>Verified</option>
          </select>
        </td>
        <td><input class="input-control case-note-input" style="padding:.3rem .5rem; font-size:.7rem;" placeholder="Add investigator note…" value="${escapeHtml(c.note)}"></td>
        <td><button class="btn btn-sm btn-secondary act-case-brief">Brief</button></td>
      </tr>
    `;
  }

  function passesCaseFilters(c){
    const q = (document.getElementById('case-search').value || '').toLowerCase();
    const risk = document.getElementById('case-filter-risk').value;
    const type = document.getElementById('case-filter-type').value;
    const status = document.getElementById('case-filter-status').value;
    if (q && !(c.id.toLowerCase().includes(q) || c.subject.toLowerCase().includes(q))) return false;
    if (risk !== 'all' && riskBand(c.score) !== risk) return false;
    if (type !== 'all' && c.type !== type) return false;
    if (status !== 'all' && c.disposition !== status) return false;
    return true;
  }

  function renderCases(){
    const tbody = document.getElementById('cases-tbody');
    const empty = document.getElementById('cases-empty');
    if (!tbody) return;
    const visible = securityCases.filter(passesCaseFilters);
    tbody.innerHTML = visible.map(caseRowHtml).join('');
    empty.style.display = visible.length === 0 ? '' : 'none';
  }

  document.getElementById('cases-tbody').addEventListener('change', function(e){
    const row = e.target.closest('tr');
    if (!row) return;
    const c = securityCases.find(x => x.id === row.dataset.caseId);
    if (!c) return;
    if (e.target.classList.contains('case-disposition-select')) {
      c.disposition = e.target.value;
      pushLog();
    } else if (e.target.classList.contains('case-note-input')) {
      c.note = e.target.value;
    }
  });

  document.getElementById('cases-tbody').addEventListener('click', function(e){
    if (!e.target.classList.contains('act-case-brief')) return;
    const row = e.target.closest('tr');
    const c = securityCases.find(x => x.id === row.dataset.caseId);
    if (c) openCaseBriefModal(c);
  });

  ['case-search','case-filter-risk','case-filter-type','case-filter-status'].forEach(id => {
    const el = document.getElementById(id);
    el.addEventListener('input', renderCases);
    el.addEventListener('change', renderCases);
  });
  document.getElementById('case-filter-reset').addEventListener('click', function(){
    document.getElementById('case-search').value = '';
    document.getElementById('case-filter-risk').value = 'all';
    document.getElementById('case-filter-type').value = 'all';
    document.getElementById('case-filter-status').value = 'all';
    renderCases();
  });

  function briefBodyHtml(c){
    return `
      <h1>Fortress Protocol — Investigator Evidence Brief</h1>
      <div class="row"><div class="lbl">Case ID</div><div class="val">${c.id}</div></div>
      <div class="row"><div class="lbl">Case Type</div><div class="val">${c.type}</div></div>
      <div class="row"><div class="lbl">Subject / Artifact</div><div class="val">${escapeHtml(c.subject)}</div></div>
      <div class="row"><div class="lbl">Detection Score</div><div class="val">${c.score} / 100 — ${scoreLabel(c.score)}</div></div>
      <div class="row"><div class="lbl">Hash / Metadata</div><div class="val">Not applicable — text/URL-based analysis, no binary artifact hashed.</div></div>
      <div class="row"><div class="lbl">Model Explanation / Indicators</div><ul>${c.indicators.map(i => `<li>${escapeHtml(i)}</li>`).join('')}</ul></div>
      <div class="row"><div class="lbl">Investigator Disposition</div><div class="val">${c.disposition}</div></div>
      <div class="row"><div class="lbl">Investigator Note</div><div class="val">${c.note ? escapeHtml(c.note) : '—'}</div></div>
      <div class="row"><div class="lbl">Logged</div><div class="val">${c.time}</div></div>
    `;
  }

  function fullBriefHtmlDoc(c){
    return `<!DOCTYPE html><html><head><meta charset="UTF-8"><title>${c.id} — Evidence Brief</title>
<style>body{font-family:Arial,sans-serif;max-width:680px;margin:2rem auto;color:#111;} h1{font-size:1.2rem;border-bottom:2px solid #2563eb;padding-bottom:.5rem;} .row{margin-bottom:.9rem;} .lbl{font-weight:700;font-size:.72rem;text-transform:uppercase;letter-spacing:.4px;color:#555;} .val{font-size:.92rem;margin-top:.15rem;} ul{margin:.3rem 0 0 1.1rem;}</style>
</head><body>${briefBodyHtml(c)}</body></html>`;
  }

  function openCaseBriefModal(c){
    const box = document.getElementById('case-brief-box');
    box.innerHTML = briefBodyHtml(c) + `
      <div class="case-brief-actions">
        <button class="btn btn-sm" id="brief-download-btn">⬇ Download HTML</button>
        <button class="btn btn-sm btn-secondary" id="brief-print-btn">🖨 Print / Save as PDF</button>
        <button class="btn btn-sm btn-secondary" id="brief-close-btn" style="margin-left:auto;">Close</button>
      </div>
    `;
    document.getElementById('brief-download-btn').addEventListener('click', () => downloadCaseBrief(c));
    document.getElementById('brief-print-btn').addEventListener('click', () => window.print());
    document.getElementById('brief-close-btn').addEventListener('click', closeCaseBriefModal);
    document.getElementById('case-brief-overlay').classList.add('open');
  }

  function closeCaseBriefModal(){
    document.getElementById('case-brief-overlay').classList.remove('open');
  }

  document.getElementById('case-brief-overlay').addEventListener('click', function(e){
    if (e.target === this) closeCaseBriefModal();
  });

  function downloadCaseBrief(c){
    try {
      const blob = new Blob([fullBriefHtmlDoc(c)], { type: 'text/html' });
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url; a.download = `${c.id}-evidence-brief.html`;
      document.body.appendChild(a); a.click(); a.remove();
      setTimeout(() => URL.revokeObjectURL(url), 1000);
    } catch (err) {
      alert('Automatic download was blocked by the browser. Use "Print / Save as PDF" instead, or copy the brief text shown on screen.');
    }
  }

  // Seed one sample already-reviewed case so the queue and disposition workflow are visible on load.
  addSecurityCase({
    type: 'Email',
    subject: 'accounts@paypa1-secure.com — "Your account will be suspended"',
    score: 82,
    indicators: [
      'Sender domain uses lookalike / typosquatted branding',
      'Urgency language pressuring immediate action',
      'Requests account verification — common credential-harvest pattern',
      'Threatens account suspension'
    ],
    disposition: 'Verified',
    note: 'Confirmed against known typosquat list; sender domain registered 4 days ago. Blocked at gateway.'
  });

  /* ---------------- Audit filter ---------------- */
  document.getElementById('audit-filter').addEventListener('input', function(){
    const q = this.value.toLowerCase();
    document.querySelectorAll('#audit-tbody tr').forEach(row => {
      row.style.display = row.textContent.toLowerCase().includes(q) ? '' : 'none';
    });
  });

  /* ---------------- Export briefing (client-side text file) ---------------- */
  document.getElementById('btn-export-report').addEventListener('click', function(){
    const lines = [
      'FORTRESS PROTOCOL — SOC BRIEFING', new Date().toString(), '',
      'ACTIVE INCIDENTS: ' + document.getElementById('metric-incidents-count').textContent,
      'AUTONOMOUS NEUTRALIZATIONS: ' + document.getElementById('metric-neutralized-count').textContent,
      'GLOBAL THREAT INDEX: ' + document.getElementById('threat-index-val').textContent, '',
      'INCIDENT QUEUE:'
    ];
    document.querySelectorAll('#incidents-tbody tr').forEach(r => {
      const cells = [...r.children].slice(0,5).map(c => c.textContent.trim());
      lines.push(' - ' + cells.join(' | '));
    });
    const blob = new Blob([lines.join('\n')], {type:'text/plain'});
    const a = document.createElement('a');
    a.href = URL.createObjectURL(blob);
    a.download = 'soc-briefing-' + Date.now() + '.txt';
    a.click();
  });

  /* ================= AI Assistant Widget ================= */
  const aiWidget = document.getElementById('ai-widget');
  const aiToggleHeader = document.getElementById('ai-widget-toggle');
  const aiCollapseBtn = document.getElementById('ai-widget-collapse-btn');
  const aiBody = document.getElementById('ai-widget-body');
  const aiInput = document.getElementById('ai-input');
  const aiSendBtn = document.getElementById('ai-send-btn');
  const aiStatusEl = document.getElementById('ai-widget-status');
  const geminiKeyInput = document.getElementById('gemini-key-input');
  const geminiModelSelect = document.getElementById('gemini-model-select');
  const geminiStatusChip = document.getElementById('gemini-status-chip');

  let geminiApiKey = '';   // held in memory only, for this session
  let geminiModel = geminiModelSelect.value;

  function setConnectionState(live){
    if (live) {
      aiStatusEl.classList.remove('offline');
      aiStatusEl.innerHTML = '<span class="d"></span>Live — Gemini connected';
      geminiStatusChip.textContent = 'Live — ' + geminiModel;
      geminiStatusChip.className = 'key-status-chip live';
    } else {
      aiStatusEl.classList.add('offline');
      aiStatusEl.innerHTML = '<span class="d"></span>Offline mode';
      geminiStatusChip.textContent = 'Offline mode';
      geminiStatusChip.className = 'key-status-chip local';
    }
  }

  document.getElementById('gemini-save-btn').addEventListener('click', function(){
    const key = geminiKeyInput.value.trim();
    geminiModel = geminiModelSelect.value;
    if (!key) { setConnectionState(false); return; }
    geminiApiKey = key;
    setConnectionState(true);
    addAgentMessage("Connected. I'm now running on the live Gemini model — ask me anything about your SOC.");
  });
  document.getElementById('gemini-clear-btn').addEventListener('click', function(){
    geminiApiKey = '';
    geminiKeyInput.value = '';
    setConnectionState(false);
    addAgentMessage("Disconnected. I'll fall back to my built-in offline playbooks.");
  });

  aiToggleHeader.addEventListener('click', function(e){
    if (e.target === aiCollapseBtn) return;
    aiWidget.classList.toggle('collapsed');
  });
  aiCollapseBtn.addEventListener('click', function(){ aiWidget.classList.toggle('collapsed'); });

  function scrollAiBody(){ aiBody.scrollTop = aiBody.scrollHeight; }

  function addUserMessage(text){
    const row = document.createElement('div');
    row.className = 'assistant-row user';
    row.innerHTML = `<div class="assistant-msg user"></div>`;
    row.querySelector('.assistant-msg').textContent = text;
    aiBody.appendChild(row);
    scrollAiBody();
  }
  function addAgentMessage(text){
    const row = document.createElement('div');
    row.className = 'assistant-row';
    row.innerHTML = `<div class="assistant-avatar-sm">🤖</div><div class="assistant-msg agent"></div>`;
    row.querySelector('.assistant-msg').textContent = text;
    aiBody.appendChild(row);
    scrollAiBody();
  }
  function addTypingIndicator(){
    const row = document.createElement('div');
    row.className = 'assistant-row';
    row.id = 'typing-row';
    row.innerHTML = `<div class="assistant-avatar-sm">🤖</div><div class="assistant-msg agent"><div class="typing-dots"><span></span><span></span><span></span></div></div>`;
    aiBody.appendChild(row);
    scrollAiBody();
  }
  function removeTypingIndicator(){
    const r = document.getElementById('typing-row');
    if (r) r.remove();
  }

  const SOC_SYSTEM_PROMPT = "You are ARIA, the AI assistant embedded in the Fortress Protocol enterprise Security Operations Center dashboard, covering cybersecurity, privacy, and digital resilience. You help security analysts triage alerts, interpret phishing/URL/call risk scores, recommend containment playbooks (isolating endpoints, quarantining email, blocking IPs), explain data-privacy posture, and advise on resilience/recovery readiness. Be concise, professional, and precise — respond in 2-4 sentences unless the analyst asks for more detail. Never fabricate specific incident IDs or data you were not given.";

  async function callGeminiAPI(userMessage){
    if (!geminiApiKey) return null;
    const endpoint = `https://generativelanguage.googleapis.com/v1beta/models/${geminiModel}:generateContent?key=${encodeURIComponent(geminiApiKey)}`;
    try {
      const res = await fetch(endpoint, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          systemInstruction: { parts: [{ text: SOC_SYSTEM_PROMPT }] },
          contents: [{ role: 'user', parts: [{ text: userMessage }] }],
          generationConfig: { temperature: 0.6, maxOutputTokens: 300 }
        })
      });
      if (!res.ok) {
        console.warn('Gemini API error', res.status, await res.text().catch(()=>'')); 
        return null;
      }
      const data = await res.json();
      const text = data && data.candidates && data.candidates[0] && data.candidates[0].content &&
                   data.candidates[0].content.parts && data.candidates[0].content.parts[0] &&
                   data.candidates[0].content.parts[0].text;
      return text ? text.trim() : null;
    } catch (err) {
      console.warn('Gemini fetch failed', err);
      return null;
    }
  }

  /* Offline fallback playbook logic */
  function offlineReply(msg){
    const m = msg.toLowerCase();
    if (/incident|active|open/.test(m)) {
      const openCount = document.querySelectorAll('#incidents-tbody .status-cell.badge-warning, #incidents-tbody .status-cell.badge-critical').length;
      return `There are currently ${openCount} open incident(s) in the queue. The highest severity item is INC-8902 (SQL Injection Attempt), isolated at the perimeter firewall. Head to Incident Management to resolve or escalate.`;
    }
    if (/phish/.test(m)) {
      return "For a suspected phishing email: don't click any links, report it via Log Threat Report, and run the message through the Email Phishing Gateway analyzer for a risk score. If credentials were entered, force a password reset immediately.";
    }
    if (/isolat|endpoint|contain/.test(m)) {
      return "To contain a compromised host: go to Endpoint Containment, find the device, and click Isolate Host. This cuts network access while preserving the machine state for forensics. Restore only after the endpoint is confirmed clean.";
    }
    if (/threat index|posture/.test(m)) {
      return "The Global Threat Index reflects a rolling composite of open incident severity, anomalous traffic volume, and AI classifier confidence. It's currently Low, meaning no coordinated or elevated activity has been detected.";
    }
    if (/firewall|block|rule/.test(m)) {
      return "You can add a perimeter rule under Perimeter Rules — specify the target IP/CIDR or domain, direction, and policy (Block, Allow, or Monitor Only). New rules apply immediately to the simulated traffic queue.";
    }
    if (/hello|hi|hey/.test(m)) {
      return "Hello — I'm ARIA, your SOC assistant. Ask me about open incidents, phishing triage, endpoint isolation, or connect a Gemini API key in Settings for live AI responses.";
    }
    return "I can help with incident triage, phishing/URL/call analysis, endpoint containment, and firewall rules. Connect a Gemini API key under SOC Configurations for more open-ended answers, or try one of the quick playbooks below.";
  }

  async function handleUserQuery(text) {
    text = (text || "").trim();
    if (!text) return;

    addUserMessage(text);
    aiInput.value = "";

    addTypingIndicator();

    const reply = await getGEMINI(text);

    removeTypingIndicator();

    addAgentMessage(reply);
}

  aiSendBtn.addEventListener('click', () => handleUserQuery(aiInput.value));
  aiInput.addEventListener('keydown', e => { if (e.key === 'Enter') handleUserQuery(aiInput.value); });
  document.getElementById('ai-playbooks').addEventListener('click', e => {
    if (e.target.classList.contains('playbook-btn')) handleUserQuery(e.target.dataset.prompt);
  });


  setConnectionState(false);

  /* ---------------- Discover & Learn ---------------- */
  const learnCategories = [
    { id:'phishing',    label:'Phishing & Email Threats',      icon:'✉',  color:'#ef4444', seed:'phish-hero',   desc:'How fake emails, spoofed senders, and urgency tricks slip past busy inboxes.' },
    { id:'identity',    label:'Identity & Access',              icon:'🔑', color:'#38bdf8', seed:'idkeys-hero',  desc:'Passwords, MFA, passkeys, and the human tricks used to bypass all three.' },
    { id:'malware',     label:'Malware & Ransomware',           icon:'🦠', color:'#f59e0b', seed:'malware-hero', desc:'How malicious code spreads, hides, and holds data hostage — and how it\'s stopped.' },
    { id:'network',     label:'Network Security',               icon:'🛰', color:'#10b981', seed:'network-hero', desc:'Firewalls, DNS, segmentation, and the plumbing that keeps traffic honest.' },
    { id:'privacy',     label:'Privacy & OSINT',                icon:'🕶', color:'#a78bfa', seed:'privacy-hero', desc:'What\'s visible about you and your org from the open internet alone.' },
    { id:'cloud',       label:'Cloud Security',                 icon:'☁',  color:'#22d3ee', seed:'cloud-hero',   desc:'Shared responsibility, misconfigurations, and securing infrastructure you don\'t own.' },
    { id:'mobile',      label:'Mobile Security',                icon:'📱', color:'#fb7185', seed:'mobile-hero',  desc:'App permissions, SIM swaps, and the unique risks that live in your pocket.' },
    { id:'iot',         label:'IoT & Smart Devices',            icon:'🏠', color:'#84cc16', seed:'iot-hero',     desc:'Cameras, thermostats, and printers — the quiet, overlooked corners of the attack surface.' },
    { id:'crypto',      label:'Cryptography Basics',            icon:'🔐', color:'#eab308', seed:'crypto-hero',  desc:'Encryption, hashing, and certificates explained without the intimidating math.' },
    { id:'social',      label:'Social Engineering',             icon:'🎭', color:'#f472b6', seed:'social-hero',  desc:'Pretexting, tailgating, and the psychology attackers use instead of code.' },
    { id:'incident',    label:'Incident Response',               icon:'🚨', color:'#f87171', seed:'incident-hero',desc:'What actually happens in the first hour after something goes wrong.' },
    { id:'compliance',  label:'Compliance & Governance',        icon:'📋', color:'#60a5fa', seed:'compliance-hero', desc:'The frameworks and audits that turn good security habits into provable ones.' },
    { id:'ai',          label:'AI & ML Security',               icon:'🤖', color:'#c084fc', seed:'ai-hero',      desc:'Prompt injection, data poisoning, and defending systems that learn.' },
    { id:'physical',    label:'Physical Security',              icon:'🚪', color:'#fbbf24', seed:'physical-hero',desc:'Badges, tailgating, and why a lot of breaches start in a hallway, not a browser.' },
    { id:'career',      label:'Careers in Cybersecurity',       icon:'🎓', color:'#34d399', seed:'career-hero',  desc:'Entry points, certifications, and how SOC careers actually progress.' },
  ];

  const learnTopics = [
    // Phishing
    { id:'t1', cat:'phishing', icon:'✉', tag:'beginner', title:'Spot a Phishing Email in 10 Seconds', time:'3 min', img:'phish1', desc:'The 5 tells that give away a fake email — sender mismatch, urgency, and more.', fact:'<b>Did you know?</b> Over 90% of successful breaches start with a phishing email. The fastest tell: hover the sender name — the real address rarely matches the display name.' },
    { id:'t2', cat:'phishing', icon:'🎣', tag:'intermediate', title:'Spear Phishing vs. Mass Phishing', time:'4 min', img:'phish2', desc:'Why a targeted email to your CFO is far more dangerous than a spray-and-pray scam.', fact:'<b>Fun fact:</b> Spear phishing emails are personalized using public info — job title, recent LinkedIn posts, even conference attendance — making them 3x more likely to be clicked.' },
    { id:'t13', cat:'phishing', icon:'🐋', tag:'advanced', title:'Whaling: When the CEO Is the Target', time:'5 min', img:'phish3', desc:'Why executives get custom-crafted lures — and why one click can cost millions.', fact:'<b>Did you know?</b> "Whaling" attacks often skip malware entirely, using pure social pressure to trigger a wire transfer.' },
    { id:'t14', cat:'phishing', icon:'📎', tag:'intermediate', title:'The Anatomy of a Malicious Attachment', time:'4 min', img:'phish4', desc:'How a harmless-looking invoice PDF or macro-enabled doc becomes a foothold.', fact:'<b>Fun fact:</b> Office macros were disabled by default across Microsoft 365 in 2022 specifically because of how often they were weaponized.' },
    // Identity
    { id:'t3', cat:'identity', icon:'🔑', tag:'beginner', title:'Why MFA Stops 99% of Attacks', time:'3 min', img:'id1', desc:'A one-tap authenticator app can block almost every automated account takeover.', fact:'<b>Did you know?</b> Microsoft found that enabling multi-factor authentication blocks over 99.9% of automated account compromise attempts.' },
    { id:'t4', cat:'identity', icon:'🧬', tag:'intermediate', title:'Passkeys: The End of Passwords?', time:'5 min', img:'id2', desc:'How passkeys use device biometrics instead of a typed secret — and why they resist phishing.', fact:'<b>Fun fact:</b> Passkeys can\'t be phished because the cryptographic key never leaves your device — there\'s no secret to trick you into typing.' },
    { id:'t15', cat:'identity', icon:'🪪', tag:'beginner', title:'Least Privilege, Explained Simply', time:'3 min', img:'id3', desc:'Why every account should have the smallest set of permissions it needs — no more.', fact:'<b>Did you know?</b> Least privilege limits blast radius: if one account is compromised, the damage is capped by what that account could touch.' },
    { id:'t16', cat:'identity', icon:'🧭', tag:'advanced', title:'Zero Trust in Plain English', time:'6 min', img:'id4', desc:'"Never trust, always verify" — what it means in practice, not just as a slogan.', fact:'<b>Fun fact:</b> Zero Trust assumes attackers are already inside the network, so it verifies every request regardless of source.' },
    // Malware
    { id:'t5', cat:'malware', icon:'🦠', tag:'beginner', title:'Ransomware 101', time:'4 min', img:'mal1', desc:'How ransomware spreads, what "double extortion" means, and the first move on infection.', fact:'<b>Did you know?</b> The single best defense against ransomware is offline, tested backups — attackers can encrypt live data, but not a disconnected drive.' },
    { id:'t6', cat:'malware', icon:'🐴', tag:'intermediate', title:'Living-off-the-Land Attacks', time:'6 min', img:'mal2', desc:'Why attackers increasingly use built-in OS tools instead of custom malware to stay hidden.', fact:'<b>Fun fact:</b> "LotL" attacks abuse legitimate tools like PowerShell, so they often don\'t trigger traditional antivirus signatures at all.' },
    { id:'t7', cat:'malware', icon:'🕳', tag:'advanced', title:'Zero-Days, Explained Simply', time:'5 min', img:'mal3', desc:'What makes a vulnerability a "zero-day," and why patch speed is a race against time.', fact:'<b>Did you know?</b> The name comes from the "zero days" defenders have had to patch it before it\'s exploited in the wild.' },
    { id:'t17', cat:'malware', icon:'🪱', tag:'intermediate', title:'Worms vs. Viruses vs. Trojans', time:'4 min', img:'mal4', desc:'The three classic malware families and the one key trait that tells them apart.', fact:'<b>Did you know?</b> Worms are unique because they self-replicate across a network without needing a human to open anything.' },
    // Network
    { id:'t8', cat:'network', icon:'🛰', tag:'beginner', title:'What a Firewall Actually Does', time:'3 min', img:'net1', desc:'A friendly breakdown of allow/block rules, ports, and why "default deny" wins.', fact:'<b>Fun fact:</b> The term "firewall" comes from construction — a literal wall built to stop fire from spreading between building sections.' },
    { id:'t9', cat:'network', icon:'📡', tag:'intermediate', title:'DNS Tunneling Basics', time:'5 min', img:'net2', desc:'How attackers sneak data out of a network hidden inside ordinary-looking DNS queries.', fact:'<b>Did you know?</b> DNS tunneling can leak data one query at a time — slow, but often invisible to firewalls that only inspect web and email traffic.' },
    { id:'t18', cat:'network', icon:'🧱', tag:'advanced', title:'Network Segmentation & the "Flat Network" Problem', time:'6 min', img:'net3', desc:'Why one compromised laptop shouldn\'t be able to reach every server in the building.', fact:'<b>Fun fact:</b> Segmentation is why a factory floor and a finance department are often on completely separate VLANs.' },
    // Privacy
    { id:'t10', cat:'privacy', icon:'🕶', tag:'beginner', title:'Public Wi-Fi: Safe or Risky?', time:'3 min', img:'priv1', desc:'What a coffee-shop network can and can\'t see — and when a VPN actually matters.', fact:'<b>Fun fact:</b> On modern HTTPS sites, public Wi-Fi snooping is much harder than it used to be — but network name spoofing ("evil twin" hotspots) is still a live risk.' },
    { id:'t11', cat:'privacy', icon:'🧩', tag:'intermediate', title:'The OSINT Footprint You Don\'t See', time:'6 min', img:'priv2', desc:'How attackers build a profile of your org from public job posts, GitHub, and metadata.', fact:'<b>Did you know?</b> Job listings that mention specific software versions are a common OSINT source for attackers planning targeted exploits.' },
    { id:'t19', cat:'privacy', icon:'🖼', tag:'beginner', title:'Metadata: The Data Hidden in Your Files', time:'3 min', img:'priv3', desc:'What a photo or PDF quietly reveals about who made it, when, and sometimes where.', fact:'<b>Did you know?</b> Photos can embed GPS coordinates in EXIF data — which is why security teams strip metadata before publishing images.' },
    // Cloud
    { id:'t20', cat:'cloud', icon:'☁', tag:'beginner', title:'The Shared Responsibility Model', time:'4 min', img:'cloud1', desc:'What your cloud provider secures — and what\'s still entirely on you.', fact:'<b>Did you know?</b> Most cloud breaches trace back to misconfiguration on the customer side, not a flaw in the provider\'s infrastructure.' },
    { id:'t21', cat:'cloud', icon:'🪣', tag:'intermediate', title:'The Open Storage Bucket Problem', time:'4 min', img:'cloud2', desc:'How a single misconfigured setting can expose millions of records to the open internet.', fact:'<b>Fun fact:</b> Some of the largest data leaks in history required no hacking at all — just a storage bucket left publicly readable.' },
    { id:'t22', cat:'cloud', icon:'🔗', tag:'advanced', title:'Supply Chain Attacks via Cloud Dependencies', time:'6 min', img:'cloud3', desc:'Why compromising one small software package can ripple into thousands of companies.', fact:'<b>Did you know?</b> A single poisoned open-source library can be pulled into production by any app that lists it as a dependency.' },
    // Mobile
    { id:'t23', cat:'mobile', icon:'📱', tag:'beginner', title:'App Permissions: What\'s Actually Necessary?', time:'3 min', img:'mobile1', desc:'Why a flashlight app asking for your contacts list is a red flag.', fact:'<b>Did you know?</b> Both major app stores now require developers to disclose exactly what data an app collects before you install it.' },
    { id:'t24', cat:'mobile', icon:'📶', tag:'intermediate', title:'SIM Swapping Explained', time:'5 min', img:'mobile2', desc:'How attackers hijack your phone number to intercept SMS-based verification codes.', fact:'<b>Fun fact:</b> SIM swapping is a major reason security experts recommend app-based authenticators over SMS codes.' },
    // IoT
    { id:'t25', cat:'iot', icon:'📷', tag:'beginner', title:'Default Passwords: The IoT Achilles\' Heel', time:'3 min', img:'iot1', desc:'Why smart cameras and routers are scanned constantly for factory-default logins.', fact:'<b>Did you know?</b> Some of the largest botnets ever recorded were built almost entirely from IoT devices still using default credentials.' },
    { id:'t26', cat:'iot', icon:'🖨', tag:'intermediate', title:'The Forgotten Printer on the Network', time:'4 min', img:'iot2', desc:'Why office printers are a surprisingly common entry point in penetration tests.', fact:'<b>Fun fact:</b> Printers often run outdated firmware for years because no one thinks to patch them.' },
    // Cryptography
    { id:'t27', cat:'crypto', icon:'🔐', tag:'beginner', title:'Encryption vs. Hashing: What\'s the Difference?', time:'4 min', img:'crypto1', desc:'One can be reversed with a key, the other never can — and mixing them up matters.', fact:'<b>Did you know?</b> Passwords should always be hashed, never encrypted — hashing is a one-way street by design.' },
    { id:'t28', cat:'crypto', icon:'📜', tag:'intermediate', title:'What That Padlock Icon Really Means', time:'3 min', img:'crypto2', desc:'TLS certificates prove a site is who it claims to be — not that it\'s trustworthy.', fact:'<b>Fun fact:</b> A phishing site can have a valid padlock too — HTTPS confirms encryption in transit, not good intentions.' },
    // Social engineering
    { id:'t12', cat:'social', icon:'🎭', tag:'advanced', title:'Social Engineering Playbook', time:'7 min', img:'social1', desc:'Pretexting, baiting, and tailgating — the human-side tricks that bypass every firewall.', fact:'<b>Fun fact:</b> The costliest breaches often start with a phone call, not code — a confident voice asking an IT helpdesk to "reset my password."' },
    { id:'t29', cat:'social', icon:'☎', tag:'intermediate', title:'Vishing: Phishing Over the Phone', time:'4 min', img:'social2', desc:'Why a calm, confident voice claiming to be "IT support" is one of the oldest tricks that still works.', fact:'<b>Did you know?</b> Vishing calls often spoof caller ID to show an internal extension, making the call look legitimate.' },
    // Incident response
    { id:'t30', cat:'incident', icon:'🚨', tag:'beginner', title:'The First 60 Minutes of a Breach', time:'5 min', img:'ir1', desc:'Contain, document, notify — the order of operations that limits damage.', fact:'<b>Did you know?</b> Isolating an affected device from the network is usually prioritized over immediately wiping it, to preserve evidence.' },
    { id:'t31', cat:'incident', icon:'🧯', tag:'intermediate', title:'Why "Don\'t Panic and Reboot" Is a Real Rule', time:'4 min', img:'ir2', desc:'Rebooting a compromised machine can destroy the evidence investigators need most.', fact:'<b>Fun fact:</b> Volatile memory (RAM) often holds attacker activity that vanishes completely the moment a machine restarts.' },
    // Compliance
    { id:'t32', cat:'compliance', icon:'📋', tag:'beginner', title:'SOC 2 in Plain English', time:'4 min', img:'comp1', desc:'What auditors actually check for, and why customers ask to see the report.', fact:'<b>Did you know?</b> SOC 2 isn\'t a single checklist — it\'s built around five "trust service criteria" a company chooses to be audited on.' },
    { id:'t33', cat:'compliance', icon:'🇪🇺', tag:'intermediate', title:'GDPR Basics for Non-Lawyers', time:'5 min', img:'comp2', desc:'The core idea behind Europe\'s privacy law — and why it affects companies worldwide.', fact:'<b>Fun fact:</b> GDPR applies to any company handling EU residents\' data, regardless of where that company is headquartered.' },
    // AI security
    { id:'t34', cat:'ai', icon:'🤖', tag:'intermediate', title:'Prompt Injection, Explained', time:'5 min', img:'ai1', desc:'How hidden text can hijack an AI assistant into ignoring its own instructions.', fact:'<b>Did you know?</b> Prompt injection can hide inside a webpage or document an AI is asked to summarize, not just in direct chat messages.' },
    { id:'t35', cat:'ai', icon:'🧪', tag:'advanced', title:'Data Poisoning 101', time:'6 min', img:'ai2', desc:'How corrupting training data can quietly bias or backdoor a machine learning model.', fact:'<b>Fun fact:</b> A poisoned model can behave completely normally until it sees one very specific trigger pattern.' },
    // Physical security
    { id:'t36', cat:'physical', icon:'🚪', tag:'beginner', title:'Tailgating: The Oldest Trick in the Book', time:'3 min', img:'phys1', desc:'Why holding the door for a stranger in a lanyard is a classic way inside a building.', fact:'<b>Did you know?</b> Physical penetration testers often get further just by carrying a box and looking busy than with any digital tool.' },
    { id:'t37', cat:'physical', icon:'🗑', tag:'intermediate', title:'Dumpster Diving Still Works', time:'4 min', img:'phys2', desc:'What discarded printouts, sticky notes, and old hard drives can reveal.', fact:'<b>Fun fact:</b> Shredding policies exist largely because unshredded documents remain a legitimate OSINT source for attackers.' },
    // Career
    { id:'t38', cat:'career', icon:'🎓', tag:'beginner', title:'Breaking Into a SOC Analyst Role', time:'5 min', img:'career1', desc:'The entry-level path most Tier-1 analysts actually took to get hired.', fact:'<b>Did you know?</b> Many SOC teams value hands-on lab experience and certifications as much as a traditional degree.' },
    { id:'t39', cat:'career', icon:'🏅', tag:'intermediate', title:'Which Certification Should You Get First?', time:'5 min', img:'career2', desc:'A grounded comparison of entry-level certs and what each one signals to employers.', fact:'<b>Fun fact:</b> Many analysts stack a foundational cert early, then specialize later toward offense, defense, or cloud.' },
  ];

  const learnHubStats = document.getElementById('learn-hub-stats');
  const learnFilterRow = document.getElementById('learn-filter-row');
  const learnCategoriesEl = document.getElementById('learn-categories');
  const streakCountEl = document.getElementById('streak-count');
  const streakChip = document.getElementById('streak-chip');
  let completedTopics = new Set();

  function imgUrl(seed, w, h){ return `https://picsum.photos/seed/${seed}/${w}/${h}`; }

  function cardHtml(t, cat){
    return `
      <div class="learn-card ${completedTopics.has(t.id) ? 'completed' : ''}" data-id="${t.id}">
        <div class="learn-card-img-wrap">
          <img src="${imgUrl(t.img, 400, 240)}" alt="" loading="lazy">
          <div class="learn-card-tag ${t.tag}">${t.tag}</div>
          <div class="learn-card-ico" style="background:${cat.color}; color:#04070d;">${t.icon}</div>
        </div>
        <div class="learn-card-body">
          <div class="learn-card-title">${t.title}</div>
          <div class="learn-card-desc">${t.desc}</div>
          <div class="learn-fact-box">${t.fact}</div>
          <div class="learn-card-meta">
            <span class="est-time">⏱ ${t.time} read</span>
            <span class="done-check">✔ Completed</span>
          </div>
        </div>
      </div>
    `;
  }

  function renderLearnHub(){
    learnHubStats.innerHTML = `
      <div class="learn-hub-stat"><div class="num">${learnTopics.length}</div><div class="lbl">Total topics</div></div>
      <div class="learn-hub-stat"><div class="num">${learnCategories.length}</div><div class="lbl">Topic areas</div></div>
      <div class="learn-hub-stat"><div class="num" id="learn-hub-completed">0</div><div class="lbl">You've completed</div></div>
      <div class="learn-hub-stat"><div class="num">~${Math.round(learnTopics.reduce((a,t)=>a+parseInt(t.time),0)/learnTopics.length)} min</div><div class="lbl">Avg. read time</div></div>
    `;

    learnFilterRow.innerHTML = `<button class="learn-filter active" data-cat="all">🗂 All Areas</button>` +
      learnCategories.map(c => `<button class="learn-filter" data-cat="${c.id}">${c.icon} ${c.label}</button>`).join('');

    learnCategoriesEl.innerHTML = learnCategories.map(cat => {
      const topics = learnTopics.filter(t => t.cat === cat.id);
      return `
        <div class="learn-category" id="learn-cat-${cat.id}" data-cat="${cat.id}">
          <div class="learn-category-banner">
            <img src="${imgUrl(cat.seed, 1200, 300)}" alt="" loading="lazy">
            <div class="learn-category-banner-inner">
              <div class="learn-category-ico" style="background:${cat.color}33; color:${cat.color}; border-color:${cat.color}55;">${cat.icon}</div>
              <div>
                <div class="learn-category-title">${cat.label}</div>
                <div class="learn-category-desc">${cat.desc}</div>
              </div>
              <div class="learn-category-count">${topics.length} topics</div>
            </div>
          </div>
          <div class="learn-grid">${topics.map(t => cardHtml(t, cat)).join('')}</div>
        </div>
      `;
    }).join('');
  }
  renderLearnHub();

  function updateStreak(){
    streakCountEl.textContent = completedTopics.size;
    streakChip.style.opacity = completedTopics.size > 0 ? '1' : '.7';
    const hubCompleted = document.getElementById('learn-hub-completed');
    if (hubCompleted) hubCompleted.textContent = completedTopics.size;
  }
  updateStreak();

  learnCategoriesEl.addEventListener('click', (e) => {
    const card = e.target.closest('.learn-card');
    if (!card) return;
    card.classList.toggle('expanded');
    const id = card.dataset.id;
    if (card.classList.contains('expanded') && !completedTopics.has(id)) {
      completedTopics.add(id);
      card.classList.add('completed');
      updateStreak();
    }
  });

  learnFilterRow.addEventListener('click', (e) => {
    const btn = e.target.closest('.learn-filter');
    if (!btn) return;
    learnFilterRow.querySelectorAll('.learn-filter').forEach(b => b.classList.remove('active'));
    btn.classList.add('active');
    const cat = btn.dataset.cat;
    if (cat === 'all') {
      document.querySelectorAll('.learn-category').forEach(el => el.style.display = '');
    } else {
      document.querySelectorAll('.learn-category').forEach(el => el.style.display = el.dataset.cat === cat ? '' : 'none');
      document.getElementById(`learn-cat-${cat}`).scrollIntoView({behavior:'smooth', block:'start'});
    }
  });

  const learnDailyBtn = document.getElementById('learn-daily-btn');
  learnDailyBtn.addEventListener('click', () => {
    learnFilterRow.querySelectorAll('.learn-filter').forEach(b => b.classList.toggle('active', b.dataset.cat === 'phishing'));
    document.querySelectorAll('.learn-category').forEach(el => el.style.display = el.dataset.cat === 'phishing' ? '' : 'none');
    const catEl = document.getElementById('learn-cat-phishing');
    const first = catEl && catEl.querySelector('.learn-card');
    if (first) {
      first.classList.add('expanded');
      if (!completedTopics.has(first.dataset.id)) { completedTopics.add(first.dataset.id); first.classList.add('completed'); updateStreak(); }
      first.scrollIntoView({behavior:'smooth', block:'center'});
    }
  });
})();
const APIkey = "AQ.Ab8RN6LAAukMCNCnfUe2WapdNekm6VwRtj5n77VC49zG8x_8oQ";


const input = document.getElementById("fetch");
const send = document.getElementById("send-ai2");
const p = document.getElementById("ai-response2");

send.addEventListener("click", getGEMINI);
async function getGEMINI(prompt) {

    prompt += "\nSummarize in 4-5 lines maximum.";

    try {
        const res = await fetch(
            `https://generativelanguage.googleapis.com/v1beta/models/gemini-3.5-flash-lite:generateContent?key=${APIkey}`,
            {
                method: "POST",
                headers: {
                    "Content-Type": "application/json"
                },
                body: JSON.stringify({
                    contents: [{
                        parts: [{
                            text: prompt
                        }]
                    }]
                })
            }
        );

        const data = await res.json();

        if (!res.ok) {
            console.error(data);
            return data.error?.message || "Gemini API error.";
        }

        return data.candidates?.[0]?.content?.parts?.[0]?.text || "No response.";

    } catch (err) {
        console.error(err);
        return "Unable to connect to Gemini.";
    }
}
</script>
</body>
</html>
