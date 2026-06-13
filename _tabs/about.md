---
layout: page
title: About
icon: fas fa-info-circle
order: 1
---

<style>
/* ── Hero ── */
.rg-banner{width:100%;border-radius:12px;margin-bottom:2rem;display:block;object-fit:cover;max-height:320px;}
.rg-hero{text-align:center;padding:1rem 0 2rem;}
.rg-name{font-size:2.4rem;font-weight:700;background:linear-gradient(135deg,#667eea,#764ba2);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;margin:0.5rem 0;}
.rg-typed-wrap{font-size:1.15rem;color:var(--text-muted-color,#888);margin:0.5rem 0 1.2rem;min-height:1.8rem;}
.rg-cursor{display:inline-block;width:2px;height:1.1em;background:currentColor;margin-left:2px;vertical-align:text-bottom;animation:rg-blink .65s steps(1) infinite;}
@keyframes rg-blink{0%,100%{opacity:1}50%{opacity:0}}
.rg-badges{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin-bottom:1.2rem;}
.rg-badge{padding:4px 14px;border-radius:20px;font-size:.82rem;font-weight:500;border:1px solid;background:rgba(102,126,234,.1);border-color:rgba(102,126,234,.3);color:#667eea;}
.rg-badge.green{background:rgba(16,185,129,.1);border-color:rgba(16,185,129,.35);color:#10b981;}
.rg-socials{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;}
.rg-social-btn{display:inline-flex;align-items:center;gap:6px;padding:8px 18px;border-radius:8px;font-size:.88rem;font-weight:500;text-decoration:none;border:1px solid rgba(102,126,234,.35);color:var(--link-color,#667eea);background:rgba(102,126,234,.06);transition:all .2s;}
.rg-social-btn:hover{background:rgba(102,126,234,.15);transform:translateY(-2px);text-decoration:none;}

/* ── Stats ── */
.rg-stats{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:14px;margin:2rem 0;}
.rg-stat{text-align:center;padding:1.2rem 1rem;border-radius:12px;border:1px solid var(--border-color,rgba(0,0,0,.1));background:var(--card-bg,rgba(255,255,255,.05));transition:transform .2s;}
.rg-stat:hover{transform:translateY(-3px);}
.rg-stat-num{display:block;font-size:2rem;font-weight:700;background:linear-gradient(135deg,#667eea,#764ba2);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;line-height:1.2;}
.rg-stat-label{display:block;font-size:.78rem;color:var(--text-muted-color,#888);margin-top:4px;}

/* ── Sections ── */
.rg-section{margin:2.5rem 0;}
.rg-section-title{font-size:1.35rem;font-weight:700;margin-bottom:1.2rem;display:flex;align-items:center;gap:8px;}
.rg-section-title::after{content:'';flex:1;height:1px;background:linear-gradient(to right,rgba(102,126,234,.4),transparent);margin-left:12px;}
.rg-reveal{opacity:0;transform:translateY(24px);transition:opacity .55s ease,transform .55s ease;}
.rg-reveal.visible{opacity:1;transform:translateY(0);}

/* ── What I Do cards ── */
.rg-do-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:14px;}
.rg-do-card{padding:1.1rem;border-radius:12px;border:1px solid var(--border-color,rgba(0,0,0,.1));background:var(--card-bg,rgba(255,255,255,.03));transition:transform .2s,border-color .2s;}
.rg-do-card:hover{transform:translateY(-3px);border-color:rgba(102,126,234,.5);}
.rg-do-icon{font-size:1.6rem;margin-bottom:8px;}
.rg-do-title{font-weight:600;font-size:.95rem;margin-bottom:4px;}
.rg-do-desc{font-size:.82rem;color:var(--text-muted-color,#888);line-height:1.5;}

/* ── Experience Timeline ── */
.rg-timeline{position:relative;padding-left:20px;}
.rg-timeline::before{content:'';position:absolute;left:6px;top:8px;bottom:8px;width:2px;background:linear-gradient(to bottom,#667eea,#764ba2);}
.rg-job{position:relative;margin-bottom:2rem;cursor:pointer;}
.rg-job::before{content:'';position:absolute;left:-18px;top:8px;width:12px;height:12px;border-radius:50%;background:linear-gradient(135deg,#667eea,#764ba2);border:2px solid var(--main-bg,#fff);transition:transform .2s;}
.rg-job:hover::before{transform:scale(1.3);}
.rg-job-header{display:flex;flex-wrap:wrap;align-items:flex-start;justify-content:space-between;gap:6px;}
.rg-job-title{font-weight:700;font-size:1rem;}
.rg-job-company{font-size:.88rem;color:#667eea;font-weight:500;}
.rg-job-period{font-size:.78rem;color:var(--text-muted-color,#888);padding:2px 10px;border-radius:12px;border:1px solid var(--border-color,rgba(0,0,0,.1));white-space:nowrap;}
.rg-job-body{overflow:hidden;max-height:0;transition:max-height .4s ease,opacity .3s;}
.rg-job-body.open{max-height:400px;opacity:1;}
.rg-job-body{opacity:0;}
.rg-job-body ul{margin-top:10px;padding-left:18px;font-size:.88rem;color:var(--text-muted-color,#888);}
.rg-job-body li{margin-bottom:4px;line-height:1.55;}
.rg-job-tools{display:flex;flex-wrap:wrap;gap:5px;margin-top:10px;}
.rg-tool-tag{font-size:.75rem;padding:3px 10px;border-radius:6px;background:rgba(102,126,234,.12);color:#667eea;border:1px solid rgba(102,126,234,.25);}
.rg-expand-hint{font-size:.75rem;color:var(--text-muted-color,#999);margin-top:4px;}

/* ── Skills ── */
.rg-skill-tabs{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:1.2rem;}
.rg-tab-btn{padding:6px 16px;border-radius:20px;border:1px solid var(--border-color,rgba(0,0,0,.1));background:transparent;cursor:pointer;font-size:.83rem;font-weight:500;color:var(--text-muted-color,#888);transition:all .2s;}
.rg-tab-btn.active{background:linear-gradient(135deg,#667eea,#764ba2);color:#fff;border-color:transparent;}
.rg-skill-panel{display:none;}
.rg-skill-panel.active{display:block;}
.rg-skill-bar-wrap{margin-bottom:12px;}
.rg-skill-label{display:flex;justify-content:space-between;font-size:.85rem;margin-bottom:4px;}
.rg-skill-pct{font-size:.8rem;color:#667eea;font-weight:600;}
.rg-skill-track{height:7px;background:rgba(102,126,234,.12);border-radius:4px;overflow:hidden;}
.rg-skill-fill{height:100%;width:0;border-radius:4px;background:linear-gradient(90deg,#667eea,#764ba2);transition:width 1.1s cubic-bezier(.4,0,.2,1);}
.rg-skill-tags{display:flex;flex-wrap:wrap;gap:8px;margin-top:1rem;}
.rg-tag{padding:5px 14px;border-radius:20px;font-size:.8rem;font-weight:500;border:1px solid;transition:transform .15s;}
.rg-tag:hover{transform:scale(1.05);}
.rg-tag.data{background:rgba(99,179,237,.12);border-color:rgba(99,179,237,.3);color:#4299e1;}
.rg-tag.seo{background:rgba(72,187,120,.12);border-color:rgba(72,187,120,.3);color:#38a169;}
.rg-tag.paid{background:rgba(237,137,54,.12);border-color:rgba(237,137,54,.3);color:#dd6b20;}
.rg-tag.dev{background:rgba(159,122,234,.12);border-color:rgba(159,122,234,.3);color:#805ad5;}

/* ── Projects ── */
.rg-projects{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px;}
.rg-project-card{border-radius:14px;border:1px solid var(--border-color,rgba(0,0,0,.1));overflow:hidden;transition:transform .25s,box-shadow .25s;}
.rg-project-card:hover{transform:translateY(-5px);box-shadow:0 12px 32px rgba(102,126,234,.15);}
.rg-project-top{padding:1.2rem;background:linear-gradient(135deg,rgba(102,126,234,.12),rgba(118,75,162,.08));}
.rg-project-status{font-size:.72rem;font-weight:600;padding:3px 10px;border-radius:12px;background:rgba(16,185,129,.15);color:#10b981;border:1px solid rgba(16,185,129,.25);display:inline-block;margin-bottom:8px;}
.rg-project-name{font-weight:700;font-size:1.05rem;margin-bottom:4px;}
.rg-project-desc{font-size:.83rem;color:var(--text-muted-color,#888);line-height:1.5;}
.rg-project-bottom{padding:1rem 1.2rem;display:flex;align-items:center;justify-content:space-between;flex-wrap:wrap;gap:8px;border-top:1px solid var(--border-color,rgba(0,0,0,.1));}
.rg-project-tags{display:flex;flex-wrap:wrap;gap:5px;}
.rg-ptag{font-size:.72rem;padding:2px 9px;border-radius:5px;background:rgba(102,126,234,.1);color:#667eea;}
.rg-project-link{font-size:.82rem;color:#667eea;text-decoration:none;font-weight:500;}
.rg-project-link:hover{text-decoration:underline;}

/* ── Education ── */
.rg-edu-card{display:flex;gap:14px;padding:1.1rem;border-radius:12px;border:1px solid var(--border-color,rgba(0,0,0,.1));margin-bottom:12px;transition:border-color .2s;}
.rg-edu-card:hover{border-color:rgba(102,126,234,.4);}
.rg-edu-icon{font-size:1.8rem;flex-shrink:0;}
.rg-edu-deg{font-weight:700;font-size:.95rem;}
.rg-edu-uni{font-size:.85rem;color:#667eea;}
.rg-edu-year{font-size:.78rem;color:var(--text-muted-color,#888);margin-top:2px;}

/* ── Certifications ── */
.rg-certs{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:10px;}
.rg-cert{display:flex;align-items:center;gap:10px;padding:10px 14px;border-radius:10px;border:1px solid var(--border-color,rgba(0,0,0,.1));transition:border-color .2s,transform .2s;}
.rg-cert:hover{border-color:rgba(102,126,234,.4);transform:translateX(3px);}
.rg-cert-icon{font-size:1.2rem;}
.rg-cert-name{font-size:.83rem;font-weight:600;}
.rg-cert-org{font-size:.75rem;color:var(--text-muted-color,#888);}

/* ── Current Focus ── */
.rg-focus-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:14px;}
.rg-focus-card{padding:1.2rem;border-radius:14px;border:1px solid var(--border-color,rgba(0,0,0,.1));text-align:center;transition:transform .2s,border-color .2s;}
.rg-focus-card:hover{transform:translateY(-4px);border-color:rgba(102,126,234,.4);}
.rg-focus-icon{font-size:2rem;margin-bottom:10px;display:block;}
.rg-focus-title{font-weight:700;font-size:.95rem;margin-bottom:6px;}
.rg-focus-desc{font-size:.82rem;color:var(--text-muted-color,#888);line-height:1.55;}

/* ── Connect ── */
.rg-connect{text-align:center;padding:2.5rem 1rem;border-radius:16px;background:linear-gradient(135deg,rgba(102,126,234,.08),rgba(118,75,162,.06));border:1px solid rgba(102,126,234,.2);margin-top:2.5rem;}
.rg-connect h2{font-size:1.5rem;font-weight:700;margin-bottom:.6rem;}
.rg-connect p{color:var(--text-muted-color,#888);margin-bottom:1.4rem;font-size:.93rem;}
.rg-connect-btns{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;}
.rg-connect-btn{padding:10px 22px;border-radius:8px;font-size:.9rem;font-weight:600;text-decoration:none;transition:all .2s;}
.rg-connect-btn.primary{background:linear-gradient(135deg,#667eea,#764ba2);color:#fff;}
.rg-connect-btn.primary:hover{opacity:.9;transform:translateY(-2px);text-decoration:none;color:#fff;}
.rg-connect-btn.secondary{border:1px solid rgba(102,126,234,.4);color:#667eea;}
.rg-connect-btn.secondary:hover{background:rgba(102,126,234,.1);text-decoration:none;}
</style>

<!-- ═══════════════ HERO ═══════════════ -->
<img src="/assets/img/about-banner.jpg" alt="Rishav G C — Data, SEO & Digital Marketing" class="rg-banner" />

<div class="rg-hero">
  <h1 class="rg-name">Rishav G C</h1>
  <div class="rg-typed-wrap">
    <span id="rg-typed"></span><span class="rg-cursor"></span>
  </div>
  <div class="rg-badges">
    <span class="rg-badge">📍 Nepal</span>
    <span class="rg-badge green">🟢 Open to Opportunities</span>
  </div>
  <div class="rg-socials">
    <a href="https://www.linkedin.com/in/rishavgc/" class="rg-social-btn" target="_blank">🔗 LinkedIn</a>
    <a href="https://github.com/mrparanoid23" class="rg-social-btn" target="_blank">⚡ GitHub</a>
    <a href="mailto:rishavgc07@gmail.com" class="rg-social-btn">✉️ Email</a>
  </div>
</div>

<!-- ═══════════════ STATS ═══════════════ -->
<div class="rg-stats rg-reveal">
  <div class="rg-stat" data-target="4" data-suffix="+">
    <span class="rg-stat-num" data-val="4" data-suffix="+">0+</span>
    <span class="rg-stat-label">Years Experience</span>
  </div>
  <div class="rg-stat">
    <span class="rg-stat-num" data-val="5" data-suffix="+">0+</span>
    <span class="rg-stat-label">Projects Delivered</span>
  </div>
  <div class="rg-stat">
    <span class="rg-stat-num" data-val="10" data-suffix="K+">0K+</span>
    <span class="rg-stat-label">Organic Sessions</span>
  </div>
  <div class="rg-stat">
    <span class="rg-stat-num" data-val="3" data-suffix="x">0x</span>
    <span class="rg-stat-label">Avg SEO Growth</span>
  </div>
</div>

<!-- ═══════════════ WHAT I DO ═══════════════ -->
<div class="rg-section rg-reveal">
  <div class="rg-section-title">🎯 What I Do</div>
  <div class="rg-do-grid">
    <div class="rg-do-card">
      <div class="rg-do-icon">📊</div>
      <div class="rg-do-title">Data Analytics</div>
      <div class="rg-do-desc">Turn raw data into dashboards, reports, and decisions using Python, SQL, Power BI, Google Search Console(GSC), Google Business Profile(GBP)and GA4.</div>
    </div>
    <div class="rg-do-card">
      <div class="rg-do-icon">🔍</div>
      <div class="rg-do-title">SEO Strategy</div>
      <div class="rg-do-desc">Drive organic traffic with technical SEO audits, keyword research, Core Web Vitals, and content strategy at scale.</div>
    </div>
    <div class="rg-do-card">
      <div class="rg-do-icon">📣</div>
      <div class="rg-do-title">Digital Marketing</div>
      <div class="rg-do-desc">Run paid and organic campaigns across Google, Meta, and LinkedIn — connected to real business outcomes.</div>
    </div>
    <div class="rg-do-card">
      <div class="rg-do-icon">🚀</div>
      <div class="rg-do-title">Startup Growth</div>
      <div class="rg-do-desc">Founder of Compile & Commit — building data-driven growth systems for businesses that want to scale.</div>
    </div>
  </div>
</div>

<!-- ═══════════════ EXPERIENCE ═══════════════ -->
<div class="rg-section rg-reveal">
  <div class="rg-section-title">💼 Experience</div>
  <div class="rg-timeline">

    <div class="rg-job" onclick="rgToggle(this)">
      <div class="rg-job-header">
        <div>
          <div class="rg-job-title">Founder & CEO</div>
          <div class="rg-job-company">Compile & Commit Pvt Ltd</div>
        </div>
        <span class="rg-job-period">2025 · Present</span>
      </div>
      <div class="rg-expand-hint">▾ tap to expand</div>
      <div class="rg-job-body">
        <ul>
          <li>Building data and digital marketing solutions for startups and businesses</li>
          <li>Leading a team delivering SEO, analytics, and marketing strategy</li>
          <li>Developing automation tools and frameworks for marketing and data workflows</li>
          <li>Managed end-to-end campaigns delivering 3x average organic traffic growth</li>
        </ul>
        <div class="rg-job-tools">
          <span class="rg-tool-tag">Python</span><span class="rg-tool-tag">SQL</span>
          <span class="rg-tool-tag">GA4</span><span class="rg-tool-tag">Power BI</span>
          <span class="rg-tool-tag">Ahrefs</span><span class="rg-tool-tag">Semrush</span>
          <span class="rg-tool-tag">Google Ads</span><span class="rg-tool-tag">Meta Ads</span>
        </div>
      </div>
    </div>

    <div class="rg-job" onclick="rgToggle(this)">
      <div class="rg-job-header">
        <div>
          <div class="rg-job-title">Data Analyst</div>
          <div class="rg-job-company">Multiple Clients</div>
        </div>
        <span class="rg-job-period">2020 · 2022</span>
      </div>
      <div class="rg-expand-hint">▾ tap to expand</div>
      <div class="rg-job-body">
        <ul>
          <li>Designed and built data pipelines and BI dashboards for business intelligence</li>
          <li>Conducted market research and competitive analysis using data tools</li>
          <li>Built automated reporting systems reducing manual reporting time by 60%</li>
          <li>Delivered actionable insights from complex datasets for decision-making</li>
        </ul>
        <div class="rg-job-tools">
          <span class="rg-tool-tag">Python</span><span class="rg-tool-tag">SQL</span>
          <span class="rg-tool-tag">Excel</span><span class="rg-tool-tag">Google Analytics</span>
          <span class="rg-tool-tag">Power BI</span><span class="rg-tool-tag">Looker Studio</span>
        </div>
      </div>
    </div>

    <div class="rg-job" onclick="rgToggle(this)">
      <div class="rg-job-header">
        <div>
          <div class="rg-job-title">SEO & Digital Marketing Specialist</div>
          <div class="rg-job-company">Freelance</div>
        </div>
        <span class="rg-job-period">2019 · 2021</span>
      </div>
      <div class="rg-expand-hint">▾ tap to expand</div>
      <div class="rg-job-body">
        <ul>
          <li>Executed SEO strategies driving consistent organic traffic growth for clients</li>
          <li>Managed paid and organic campaigns across Google, Meta, and LinkedIn</li>
          <li>Conducted technical SEO audits, keyword research, and content strategy planning</li>
          <li>Achieved top 3 rankings for competitive industry keywords</li>
        </ul>
        <div class="rg-job-tools">
          <span class="rg-tool-tag">Ahrefs</span><span class="rg-tool-tag">Semrush</span>
          <span class="rg-tool-tag">GSC</span><span class="rg-tool-tag">GA4</span>
          <span class="rg-tool-tag">Google Ads</span><span class="rg-tool-tag">Meta Ads</span>
        </div>
      </div>
    </div>

  </div>
</div>

<!-- ═══════════════ SKILLS ═══════════════ -->
<div class="rg-section rg-reveal">
  <div class="rg-section-title">🧠 Skills</div>

  <div class="rg-skill-tabs">
    <button class="rg-tab-btn active" onclick="rgTab(this,'data')">Data & Analytics</button>
    <button class="rg-tab-btn" onclick="rgTab(this,'seo')">SEO & Marketing</button>
    <button class="rg-tab-btn" onclick="rgTab(this,'paid')">Paid Media</button>
    <button class="rg-tab-btn" onclick="rgTab(this,'dev')">Dev & Tools</button>
  </div>

  <div class="rg-skill-panel active" id="rg-panel-data">
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Excel / Google Sheets</span><span class="rg-skill-pct">95%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="95"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Google Analytics 4</span><span class="rg-skill-pct">90%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="90"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Power BI / Looker Studio</span><span class="rg-skill-pct">82%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="82"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Python (Pandas, NumPy)</span><span class="rg-skill-pct">80%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="80"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>SQL</span><span class="rg-skill-pct">75%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="75"></div></div></div>
    <div class="rg-skill-tags">
      <span class="rg-tag data">Python</span><span class="rg-tag data">SQL</span><span class="rg-tag data">Excel</span>
      <span class="rg-tag data">GA4</span><span class="rg-tag data">Power BI</span><span class="rg-tag data">Looker Studio</span>
      <span class="rg-tag data">Pandas</span><span class="rg-tag data">NumPy</span>
    </div>
  </div>

  <div class="rg-skill-panel" id="rg-panel-seo">
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Google Search Console</span><span class="rg-skill-pct">93%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="93"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Technical SEO Audits</span><span class="rg-skill-pct">90%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="90"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Keyword Research</span><span class="rg-skill-pct">88%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="88"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Content Strategy</span><span class="rg-skill-pct">85%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="85"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Link Building</span><span class="rg-skill-pct">75%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="75"></div></div></div>
    <div class="rg-skill-tags">
      <span class="rg-tag seo">Technical SEO</span><span class="rg-tag seo">Keyword Research</span>
      <span class="rg-tag seo">Content Strategy</span><span class="rg-tag seo">Link Building</span>
      <span class="rg-tag seo">Ahrefs</span><span class="rg-tag seo">Semrush</span><span class="rg-tag seo">GSC</span>
    </div>
  </div>

  <div class="rg-skill-panel" id="rg-panel-paid">
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Google Ads</span><span class="rg-skill-pct">80%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="80"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Meta Ads (Facebook/Instagram)</span><span class="rg-skill-pct">78%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="78"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Email Marketing</span><span class="rg-skill-pct">82%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="82"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>LinkedIn Ads</span><span class="rg-skill-pct">70%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="70"></div></div></div>
    <div class="rg-skill-tags">
      <span class="rg-tag paid">Google Ads</span><span class="rg-tag paid">Meta Ads</span>
      <span class="rg-tag paid">LinkedIn Ads</span><span class="rg-tag paid">Email Marketing</span>
      <span class="rg-tag paid">Marketing Automation</span>
    </div>
  </div>

  <div class="rg-skill-panel" id="rg-panel-dev">
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Git / GitHub</span><span class="rg-skill-pct">82%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="82"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>HTML / CSS</span><span class="rg-skill-pct">78%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="78"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>REST APIs</span><span class="rg-skill-pct">72%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="72"></div></div></div>
    <div class="rg-skill-bar-wrap"><div class="rg-skill-label"><span>Jekyll / Static Sites</span><span class="rg-skill-pct">70%</span></div><div class="rg-skill-track"><div class="rg-skill-fill" data-pct="70"></div></div></div>
    <div class="rg-skill-tags">
      <span class="rg-tag dev">Git</span><span class="rg-tag dev">GitHub</span>
      <span class="rg-tag dev">HTML/CSS</span><span class="rg-tag dev">Jekyll</span>
      <span class="rg-tag dev">REST APIs</span><span class="rg-tag dev">Docker</span>
    </div>
  </div>
</div>

<!-- ═══════════════ PROJECTS ═══════════════ -->
<div class="rg-section rg-reveal">
  <div class="rg-section-title">🚀 Projects</div>
  <div class="rg-projects">
    <div class="rg-project-card">
      <div class="rg-project-top">
        <span class="rg-project-status">🟢 Live</span>
        <div class="rg-project-name">Compile & Commit</div>
        <div class="rg-project-desc">Full-service Data Analytics, AI Automation,  and digital marketing agency helping startups and businesses scale through data, SEO, and marketing strategy.</div>
      </div>
      <div class="rg-project-bottom">
        <div class="rg-project-tags">
          <span class="rg-ptag">SEO</span><span class="rg-ptag">Analytics</span>
          <span class="rg-ptag">Marketing</span>
        </div>
        <a href="https://compileandcommit.com" target="_blank" class="rg-project-link">Visit ↗</a>
      </div>
    </div>
    <div class="rg-project-card">
      <div class="rg-project-top">
        <span class="rg-project-status">🟢 Live</span>
        <div class="rg-project-name">This Blog</div>
        <div class="rg-project-desc">Personal blog covering data analytics, SEO strategies, digital marketing tactics, and founder insights — built with Jekyll on GitHub Pages.</div>
      </div>
      <div class="rg-project-bottom">
        <div class="rg-project-tags">
          <span class="rg-ptag">Jekyll</span><span class="rg-ptag">SEO</span>
          <span class="rg-ptag">GitHub Pages</span>
        </div>
        <a href="https://mrparanoid23.github.io" target="_blank" class="rg-project-link">Visit ↗</a>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════ EDUCATION ═══════════════ -->
<div class="rg-section rg-reveal">
  <div class="rg-section-title">🎓 Education</div>
  <div class="rg-edu-card">
    <div class="rg-edu-icon">🎓</div>
    <div>
      <div class="rg-edu-deg">Bachelor oF Business Administration</div>
      <div class="rg-edu-uni">Pokhara University</div>
      <div class="rg-edu-year">2018-2023</div>
    </div>
  </div>
</div>

<!-- ═══════════════ CERTIFICATIONS ═══════════════ -->
<div class="rg-section rg-reveal">
  <div class="rg-section-title">🏆 Certifications</div>
  <div class="rg-certs">
    <div class="rg-cert"><div class="rg-cert-icon">📊</div><div><div class="rg-cert-name">Google Analytics Certification</div><div class="rg-cert-org">Google</div></div></div>
    <div class="rg-cert"><div class="rg-cert-icon">🔍</div><div><div class="rg-cert-name">SEO Fundamentals</div><div class="rg-cert-org">Semrush Academy</div></div></div>
    <div class="rg-cert"><div class="rg-cert-icon">📈</div><div><div class="rg-cert-name">Google Ads Search</div><div class="rg-cert-org">Google</div></div></div>
    <div class="rg-cert"><div class="rg-cert-icon">🐍</div><div><div class="rg-cert-name">Python for Data Science</div><div class="rg-cert-org">Coursera</div></div></div>
  </div>
</div>

<!-- ═══════════════ CURRENT FOCUS ═══════════════ -->
<div class="rg-section rg-reveal">
  <div class="rg-section-title">🎯 Current Focus</div>
  <div class="rg-focus-grid">
    <div class="rg-focus-card">
      <span class="rg-focus-icon">📊</span>
      <div class="rg-focus-title">Data-Driven Marketing</div>
      <div class="rg-focus-desc">Connecting marketing performance to revenue attribution — from traffic analysis to business impact.</div>
    </div>
    <div class="rg-focus-card">
      <span class="rg-focus-icon">🔍</span>
      <div class="rg-focus-title">SEO at Scale</div>
      <div class="rg-focus-desc">Building SEO frameworks and automation tools that make organic growth predictable and measurable.</div>
    </div>
    <div class="rg-focus-card">
      <span class="rg-focus-icon">🚀</span>
      <div class="rg-focus-title">GEO (Generative Engine Optimization)</div>
      <div class="rg-focus-desc">Ranking on the GEO for better outcome and user interaction.</div>
      </div>
    <div class="rg-focus-card">
      <span class="rg-focus-icon">🚀</span>
      <div class="rg-focus-title">Growing Compile & Commit</div>
      <div class="rg-focus-desc">Scaling the agency and building products that help businesses make smarter decisions with data.</div>
    </div>
  </div>
</div>

<!-- ═══════════════ CONNECT ═══════════════ -->
<div class="rg-connect rg-reveal">
  <h2>Let's Connect</h2>
  <p>I write about data analytics, SEO, and digital marketing — practical stuff, no fluff.<br>If you're building something or want to collaborate, let's talk.</p>
  <div class="rg-connect-btns">
    <a href="https://www.linkedin.com/in/rishavgc/" target="_blank" class="rg-connect-btn primary">Connect on LinkedIn ↗</a>
    <a href="mailto:rishavgc07@gmail.com" class="rg-connect-btn secondary">Email Me ↗</a>
  </div>
</div>

<script>
(function(){
  /* ── Typewriter ── */
  var roles=["Data Analyst","SEO Specialist","Digital Marketer","Founder @ Compile & Commit"];
  var el=document.getElementById('rg-typed');
  var ri=0,ci=0,deleting=false;
  function type(){
    var word=roles[ri];
    if(!deleting){
      el.textContent=word.slice(0,++ci);
      if(ci===word.length){deleting=true;setTimeout(type,1800);return;}
    } else {
      el.textContent=word.slice(0,--ci);
      if(ci===0){deleting=false;ri=(ri+1)%roles.length;}
    }
    setTimeout(type,deleting?60:90);
  }
  setTimeout(type,600);

  /* ── Reveal on scroll ── */
  var reveals=document.querySelectorAll('.rg-reveal');
  var io=new IntersectionObserver(function(entries){
    entries.forEach(function(e){if(e.isIntersecting){e.target.classList.add('visible');}});
  },{threshold:0.12});
  reveals.forEach(function(r){io.observe(r);});

  /* ── Animated counters ── */
  var counters=document.querySelectorAll('.rg-stat-num');
  var cio=new IntersectionObserver(function(entries){
    entries.forEach(function(e){
      if(e.isIntersecting){
        var el2=e.target;
        var target=parseInt(el2.dataset.val);
        var suffix=el2.dataset.suffix||'';
        var start=0,dur=1200,step=16;
        var t=setInterval(function(){
          start+=Math.ceil(target/(dur/step));
          if(start>=target){start=target;clearInterval(t);}
          el2.textContent=start+suffix;
        },step);
        cio.unobserve(el2);
      }
    });
  },{threshold:0.5});
  counters.forEach(function(c){cio.observe(c);});

  /* ── Skill bars ── */
  var fills=document.querySelectorAll('.rg-skill-fill');
  function animateBars(panel){
    panel.querySelectorAll('.rg-skill-fill').forEach(function(f){
      setTimeout(function(){f.style.width=f.dataset.pct+'%';},80);
    });
  }
  var sio=new IntersectionObserver(function(entries){
    entries.forEach(function(e){
      if(e.isIntersecting){
        var active=document.querySelector('.rg-skill-panel.active');
        if(active)animateBars(active);
        sio.disconnect();
      }
    });
  },{threshold:0.3});
  var skillSection=document.querySelector('.rg-skill-tabs');
  if(skillSection)sio.observe(skillSection);
})();

/* ── Tab switcher ── */
function rgTab(btn,panel){
  document.querySelectorAll('.rg-tab-btn').forEach(function(b){b.classList.remove('active');});
  document.querySelectorAll('.rg-skill-panel').forEach(function(p){p.classList.remove('active');});
  btn.classList.add('active');
  var p=document.getElementById('rg-panel-'+panel);
  if(p){
    p.classList.add('active');
    p.querySelectorAll('.rg-skill-fill').forEach(function(f){
      f.style.width='0';
      setTimeout(function(){f.style.width=f.dataset.pct+'%';},50);
    });
  }
}

/* ── Timeline toggle ── */
function rgToggle(job){
  var body=job.querySelector('.rg-job-body');
  var hint=job.querySelector('.rg-expand-hint');
  var isOpen=body.classList.contains('open');
  document.querySelectorAll('.rg-job-body.open').forEach(function(b){
    b.classList.remove('open');
    var h=b.parentElement.querySelector('.rg-expand-hint');
    if(h)h.textContent='▾ tap to expand';
  });
  if(!isOpen){
    body.classList.add('open');
    if(hint)hint.textContent='▴ tap to collapse';
  }
}
</script>
