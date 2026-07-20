<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Human Equity Index — Retention as a Rated Asset</title>
<style>
:root{
  --ink-900:#0A0F1C;
  --ink-800:#111A2C;
  --ink-700:#16223A;
  --ink-650:#1B2A46;
  --ink-600:#233355;
  --brass-500:#C9A24B;
  --brass-300:#E4C876;
  --brass-700:#8F7130;
  --parchment-100:#EDE7D9;
  --parchment-200:#D8D0BC;
  --slate-400:#8B94A8;
  --slate-500:#6C7690;
  --sage-500:#7FA37A;
  --sage-300:#A8C7A3;
  --rust-500:#B5533C;
  --rust-300:#D68C77;
  --amber-500:#C98A3E;
  --font-serif:"Iowan Old Style","Palatino Linotype","Book Antiqua",Georgia,serif;
  --font-sans:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,Helvetica,Arial,sans-serif;
  --font-mono:"SF Mono",SFMono-Regular,Consolas,"Liberation Mono",Menlo,monospace;
  --radius:6px;
  --maxw:1180px;
}

*{box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{
  margin:0;
  background:var(--ink-900);
  color:var(--parchment-100);
  font-family:var(--font-sans);
  line-height:1.55;
  -webkit-font-smoothing:antialiased;
}
h1,h2,h3,h4{font-family:var(--font-serif);font-weight:600;margin:0 0 .4em;color:var(--parchment-100);}
p{margin:0 0 1em;color:var(--slate-400);}
a{color:var(--brass-300);}
.mono{font-family:var(--font-mono);}
.wrap{max-width:var(--maxw);margin:0 auto;padding:0 28px;}
button{font-family:var(--font-sans);cursor:pointer;}
:focus-visible{outline:2px solid var(--brass-300);outline-offset:2px;}
@media (prefers-reduced-motion:reduce){*{animation-duration:.001ms !important;transition-duration:.001ms !important;}}

/* ---------- TOP BAR ---------- */
.topbar{
  position:sticky;top:0;z-index:50;
  background:rgba(10,15,28,.92);
  backdrop-filter:blur(8px);
  border-bottom:1px solid var(--ink-600);
}
.topbar-inner{display:flex;align-items:center;justify-content:space-between;padding:14px 28px;max-width:var(--maxw);margin:0 auto;gap:20px;}
.brand{display:flex;align-items:center;gap:10px;}
.brand-mark{width:34px;height:34px;flex:0 0 auto;}
.brand-text{font-family:var(--font-serif);font-size:16px;letter-spacing:.03em;color:var(--parchment-100);}
.brand-text b{color:var(--brass-300);}
nav.tabs{display:flex;gap:4px;flex-wrap:wrap;}
nav.tabs button{
  background:none;border:1px solid transparent;color:var(--slate-400);
  padding:8px 12px;border-radius:var(--radius);font-size:13.5px;letter-spacing:.01em;
  transition:background .15s,color .15s,border-color .15s;
}
nav.tabs button:hover{color:var(--parchment-100);}
nav.tabs button.active{color:var(--ink-900);background:var(--brass-500);border-color:var(--brass-500);font-weight:600;}

/* ---------- SECTIONS ---------- */
main{padding-bottom:80px;}
section.view{display:none;padding-top:44px;}
section.view.active{display:block;animation:fadein .35s ease;}
@keyframes fadein{from{opacity:0;transform:translateY(6px);}to{opacity:1;transform:none;}}

.eyebrow{
  font-family:var(--font-mono);font-size:11.5px;letter-spacing:.14em;text-transform:uppercase;
  color:var(--brass-500);margin-bottom:10px;display:block;
}

/* ---------- HERO ---------- */
.hero{display:grid;grid-template-columns:1.1fr .9fr;gap:56px;align-items:center;padding-bottom:56px;}
.hero h1{font-size:40px;line-height:1.16;letter-spacing:-.01em;}
.hero .lede{font-size:16.5px;color:var(--parchment-200);max-width:52ch;}
.hero-actions{display:flex;gap:12px;margin-top:22px;flex-wrap:wrap;}
.btn{
  border-radius:var(--radius);padding:11px 20px;font-size:14px;font-weight:600;border:1px solid transparent;
  transition:transform .12s,filter .12s;display:inline-flex;align-items:center;gap:8px;
}
.btn:active{transform:translateY(1px);}
.btn-primary{background:var(--brass-500);color:var(--ink-900);}
.btn-primary:hover{filter:brightness(1.08);}
.btn-ghost{background:transparent;color:var(--parchment-100);border-color:var(--ink-600);}
.btn-ghost:hover{border-color:var(--brass-500);color:var(--brass-300);}
.btn-sm{padding:7px 12px;font-size:12.5px;}
.btn-danger{background:transparent;border-color:var(--rust-500);color:var(--rust-300);}
.btn-danger:hover{background:rgba(181,83,60,.12);}

.hero-seal-wrap{display:flex;justify-content:center;}

/* ---------- CARD / LEDGER ---------- */
.card{
  background:var(--ink-700);border:1px solid var(--ink-600);border-radius:var(--radius);
  padding:28px;
}
.card + .card{margin-top:16px;}
.grid-2{display:grid;grid-template-columns:1fr 1fr;gap:16px;}
.grid-3{display:grid;grid-template-columns:repeat(3,1fr);gap:16px;}

.ledger-line{
  display:flex;gap:18px;align-items:flex-start;padding:18px 0;border-top:1px solid var(--ink-600);
}
.ledger-line:first-child{border-top:none;}
.ledger-num{
  font-family:var(--font-mono);font-size:12px;color:var(--brass-500);
  width:28px;flex:0 0 auto;padding-top:2px;
}
.ledger-body h4{font-size:15.5px;margin-bottom:4px;}
.ledger-body p{margin:0;font-size:13.8px;}

/* ---------- METHODOLOGY WEIGHT BARS ---------- */
.weightbar-row{display:flex;align-items:center;gap:14px;margin:10px 0;}
.weightbar-label{width:230px;flex:0 0 auto;font-size:13.5px;color:var(--parchment-200);}
.weightbar-track{flex:1;height:8px;background:var(--ink-600);border-radius:4px;overflow:hidden;}
.weightbar-fill{height:100%;background:var(--brass-500);border-radius:4px;}
.weightbar-val{width:44px;flex:0 0 auto;text-align:right;font-family:var(--font-mono);font-size:12.5px;color:var(--brass-300);}

/* ---------- FORMS ---------- */
.field{margin-bottom:16px;}
.field label{display:block;font-size:12.8px;color:var(--slate-400);margin-bottom:6px;letter-spacing:.01em;}
.field .hint{font-size:11.6px;color:var(--slate-500);margin-top:5px;}
input[type=text],input[type=number],input[type=date],select,textarea{
  width:100%;background:var(--ink-800);border:1px solid var(--ink-600);color:var(--parchment-100);
  padding:10px 12px;border-radius:var(--radius);font-size:14px;font-family:var(--font-sans);
}
input[type=number]{font-family:var(--font-mono);}
input:focus,select:focus,textarea:focus{border-color:var(--brass-500);}
.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:0 20px;}
.form-section-title{
  font-family:var(--font-mono);font-size:11px;letter-spacing:.12em;text-transform:uppercase;
  color:var(--brass-500);margin:26px 0 14px;padding-top:18px;border-top:1px solid var(--ink-600);
}
.form-section-title:first-of-type{border-top:none;padding-top:0;margin-top:0;}

/* ---------- LAYOUT SPLIT (calculator) ---------- */
.split{display:grid;grid-template-columns:1fr 420px;gap:28px;align-items:flex-start;}
.results-pane{position:sticky;top:88px;}

/* ---------- SEAL ---------- */
.seal-figure{text-align:center;}
.seal-tier-label{
  margin-top:14px;font-family:var(--font-mono);font-size:12px;letter-spacing:.1em;text-transform:uppercase;
}
.seal-score-line{margin-top:4px;color:var(--slate-400);font-size:13px;}

/* ---------- SCORE BREAKDOWN BARS ---------- */
.scorebar-row{margin:14px 0;}
.scorebar-top{display:flex;justify-content:space-between;font-size:13px;margin-bottom:6px;}
.scorebar-top .name{color:var(--parchment-200);}
.scorebar-top .val{font-family:var(--font-mono);color:var(--brass-300);}
.scorebar-track{height:7px;background:var(--ink-600);border-radius:4px;overflow:hidden;}
.scorebar-fill{height:100%;border-radius:4px;transition:width .5s ease;}

/* ---------- STAT TILES ---------- */
.stat-tile{background:var(--ink-800);border:1px solid var(--ink-600);border-radius:var(--radius);padding:16px 18px;}
.stat-tile .label{font-size:11.5px;color:var(--slate-500);text-transform:uppercase;letter-spacing:.08em;margin-bottom:6px;}
.stat-tile .value{font-family:var(--font-mono);font-size:20px;color:var(--parchment-100);}
.stat-tile .value.sage{color:var(--sage-300);}
.stat-tile .value.rust{color:var(--rust-300);}

/* ---------- TABLE ---------- */
table{width:100%;border-collapse:collapse;font-size:13.6px;}
th,td{text-align:left;padding:10px 12px;border-bottom:1px solid var(--ink-600);}
th{color:var(--brass-500);font-family:var(--font-mono);font-size:11.5px;text-transform:uppercase;letter-spacing:.06em;font-weight:600;}
td{color:var(--parchment-200);}
tr:hover td{background:rgba(201,162,75,.04);}

/* ---------- BADGES ---------- */
.badge{display:inline-block;padding:3px 9px;border-radius:20px;font-family:var(--font-mono);font-size:11px;letter-spacing:.03em;font-weight:600;}
.badge-aaa,.badge-aa{background:rgba(127,163,122,.16);color:var(--sage-300);}
.badge-a,.badge-bbb{background:rgba(201,138,62,.16);color:var(--amber-500);}
.badge-bb,.badge-b,.badge-ccc{background:rgba(181,83,60,.16);color:var(--rust-300);}

/* ---------- EMPTY STATE ---------- */
.empty{text-align:center;padding:60px 20px;color:var(--slate-500);}
.empty svg{opacity:.5;margin-bottom:14px;}

/* ---------- FOOTER ---------- */
footer{border-top:1px solid var(--ink-600);padding:32px 0;margin-top:60px;}
footer p{font-size:12.5px;color:var(--slate-500);max-width:80ch;}

/* ---------- UPLOAD ZONE ---------- */
.dropzone{
  border:1.5px dashed var(--ink-600);border-radius:var(--radius);padding:40px 20px;text-align:center;
  transition:border-color .15s,background .15s;
}
.dropzone.drag{border-color:var(--brass-500);background:rgba(201,162,75,.06);}
.dropzone p{margin:0 0 14px;}

/* ---------- CURRENCY RATE TABLE ---------- */
.rate-row{display:grid;grid-template-columns:70px 1fr 130px;gap:12px;align-items:center;padding:8px 0;border-top:1px solid var(--ink-600);}
.rate-row:first-child{border-top:none;}
.rate-row .code{font-family:var(--font-mono);color:var(--brass-300);font-size:13.5px;}
.rate-row .name{font-size:13px;color:var(--slate-400);}

/* ---------- TOAST ---------- */
#toast{
  position:fixed;bottom:24px;left:50%;transform:translateX(-50%) translateY(20px);
  background:var(--brass-500);color:var(--ink-900);padding:12px 20px;border-radius:var(--radius);
  font-size:13.5px;font-weight:600;opacity:0;pointer-events:none;transition:opacity .25s,transform .25s;z-index:200;
}
#toast.show{opacity:1;transform:translateX(-50%) translateY(0);}

/* ---------- PRINT / PDF ---------- */
#printArea{display:none;}
@media print{
  body *{visibility:hidden;}
  #printArea,#printArea *{visibility:visible;}
  #printArea{display:block !important;position:absolute;top:0;left:0;width:100%;padding:20px;background:#fff;color:#111;}
  #printArea .p-header{border-bottom:2px solid #C9A24B;padding-bottom:14px;margin-bottom:18px;}
  #printArea .p-title{font-family:Georgia,serif;font-size:24px;margin:0;}
  #printArea .p-sub{font-family:monospace;font-size:11px;color:#555;letter-spacing:.08em;text-transform:uppercase;}
  #printArea table{width:100%;border-collapse:collapse;margin-top:14px;}
  #printArea th,#printArea td{border-bottom:1px solid #ccc;padding:8px;text-align:left;font-size:12.5px;}
  #printArea .p-grade{font-family:Georgia,serif;font-size:46px;font-weight:700;}
  #printArea .p-disclaimer{font-size:10.5px;color:#777;margin-top:24px;border-top:1px solid #ccc;padding-top:12px;}
}

/* ---------- TEAM CARDS ---------- */
.team-card{
  display:flex;justify-content:space-between;align-items:center;padding:16px 18px;
  background:var(--ink-800);border:1px solid var(--ink-600);border-radius:var(--radius);margin-bottom:10px;
}
.team-card .t-name{font-family:var(--font-serif);font-size:16px;color:var(--parchment-100);}
.team-card .t-meta{font-size:12.5px;color:var(--slate-500);margin-top:2px;}

/* ---------- HEAT GRID (RISK MAP) ---------- */
.heat-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:12px;}
.heat-cell{
  border-radius:var(--radius);padding:14px;border:1px solid var(--ink-600);cursor:default;
  transition:transform .12s;
}
.heat-cell:hover{transform:translateY(-2px);}
.heat-cell .h-name{font-size:13px;color:var(--ink-900);font-weight:700;margin-bottom:6px;}
.heat-cell .h-grade{font-family:var(--font-serif);font-size:22px;font-weight:700;color:var(--ink-900);}
.heat-cell .h-score{font-family:var(--font-mono);font-size:11.5px;color:var(--ink-900);opacity:.75;}
.heat-tier-aaa,.heat-tier-aa{background:var(--sage-300);}
.heat-tier-a,.heat-tier-bbb{background:#E8C98A;}
.heat-tier-bb,.heat-tier-b,.heat-tier-ccc{background:var(--rust-300);}

/* ---------- ASSUMPTION = EXPOSURE ROWS ---------- */
.assume-row{
  display:grid;grid-template-columns:1fr 28px 1fr;gap:14px;align-items:center;
  padding:16px 0;border-top:1px solid var(--ink-600);
}
.assume-row:first-child{border-top:none;}
.assume-side .a-label{font-size:12.5px;color:var(--slate-400);margin-bottom:6px;}
.assume-side .a-value{font-family:var(--font-mono);font-size:19px;color:var(--parchment-100);}
.assume-side .a-value.rust{color:var(--rust-300);}
.assume-side .a-value.sage{color:var(--sage-300);}
.assume-eq{text-align:center;color:var(--brass-500);font-size:18px;font-family:var(--font-mono);}

/* ---------- CHECKLIST (RETENTION HEALTH AUDIT) ---------- */
.check-item{
  display:flex;gap:12px;align-items:flex-start;padding:14px 0;border-top:1px solid var(--ink-600);
}
.check-item:first-child{border-top:none;}
.check-item input[type=checkbox]{
  width:19px;height:19px;flex:0 0 auto;margin-top:2px;accent-color:var(--brass-500);
}
.check-item label{font-size:14px;color:var(--parchment-200);cursor:pointer;}
.check-group-title{
  font-family:var(--font-mono);font-size:11px;letter-spacing:.1em;text-transform:uppercase;
  color:var(--brass-500);margin:22px 0 4px;
}
.check-group-title:first-of-type{margin-top:0;}
.audit-progress{
  display:flex;align-items:center;gap:14px;margin-bottom:20px;padding:16px;
  background:var(--ink-800);border:1px solid var(--ink-600);border-radius:var(--radius);
}
.audit-progress .ap-track{flex:1;height:9px;background:var(--ink-600);border-radius:5px;overflow:hidden;}
.audit-progress .ap-fill{height:100%;background:var(--brass-500);border-radius:5px;transition:width .3s;}
.audit-progress .ap-pct{font-family:var(--font-mono);font-size:15px;color:var(--brass-300);width:52px;text-align:right;}

/* ---------- RESPONSIVE ---------- */
@media (max-width:860px){
  .hero{grid-template-columns:1fr;gap:32px;}
  .hero-seal-wrap{order:-1;}
  .split{grid-template-columns:1fr;}
  .results-pane{position:static;}
  .form-grid{grid-template-columns:1fr;}
  .grid-2,.grid-3{grid-template-columns:1fr;}
  nav.tabs{width:100%;overflow-x:auto;}
  .topbar-inner{flex-wrap:wrap;}
}
</style>
</head>
<body>

<div class="topbar">
  <div class="topbar-inner">
    <div class="brand">
      <svg class="brand-mark" viewBox="0 0 60 60"><circle cx="30" cy="30" r="27" fill="none" stroke="#C9A24B" stroke-width="2"/><circle cx="30" cy="30" r="21" fill="none" stroke="#C9A24B" stroke-width="1" stroke-dasharray="2 3"/><text x="30" y="37" text-anchor="middle" font-family="Georgia,serif" font-size="20" fill="#EDE7D9">H</text></svg>
      <div class="brand-text">HUMAN EQUITY <b>INDEX</b></div>
    </div>
    <nav class="tabs" id="tabnav">
      <button data-view="overview" class="active">Overview</button>
      <button data-view="team">Team</button>
      <button data-view="calculate">Calculate</button>
      <button data-view="ledger">Ledger</button>
      <button data-view="upload">Upload Samples</button>
      <button data-view="riskmap">Risk Map</button>
      <button data-view="hce">Hidden Cost Estimator</button>
      <button data-view="community">Community Impact</button>
      <button data-view="audit">Retention Health Audit</button>
      <button data-view="currency">Currency</button>
      <button data-view="methodology">Methodology</button>
      <button data-view="backup">Reports &amp; Backup</button>
    </nav>
  </div>
</div>

<main class="wrap">

  <!-- ============ OVERVIEW ============ -->
  <section class="view active" id="view-overview">
    <div class="hero">
      <div>
        <span class="eyebrow">An Offline Analytical Framework</span>
        <h1>Your workforce carries a rating.<br>Most companies never read it.</h1>
        <p class="lede">The Human Equity Index treats employee retention as what it actually is: a financial asset with measurable stability, risk, and long-term value. This platform quantifies that asset — using your own data, calculated entirely on this device.</p>
        <div class="hero-actions">
          <button class="btn btn-primary" onclick="goTo('calculate')">Calculate Your Index →</button>
          <button class="btn btn-ghost" onclick="goTo('methodology')">See the Methodology</button>
        </div>
      </div>
      <div class="hero-seal-wrap" id="heroSeal"></div>
    </div>

    <div class="card">
      <span class="eyebrow">Why This Exists</span>
      <p style="color:var(--parchment-200);font-size:15px;max-width:78ch;">Traditional accounting has no line item for institutional memory. When a company loses experienced staff, the cost shows up eventually — in slower delivery, repeated mistakes, and diluted client trust — but rarely in a spreadsheet anyone reviews before it becomes a problem. The Human Equity Index gives that slow damage a number, a grade, and a trend line, so it can be managed before it becomes a crisis.</p>
    </div>

    <div class="card">
      <span class="eyebrow">Five Ledger Entries, One Rating</span>
      <div class="ledger-line">
        <div class="ledger-num">01</div>
        <div class="ledger-body"><h4>Retention Rate</h4><p>The share of your workforce that stayed over the past year — the foundation figure.</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">02</div>
        <div class="ledger-body"><h4>Tenure Stability</h4><p>How your average tenure compares to a realistic reference point for your industry.</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">03</div>
        <div class="ledger-body"><h4>Institutional Knowledge</h4><p>Whether your most specialized roles are staying long enough to protect what they know.</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">04</div>
        <div class="ledger-body"><h4>Financial Resilience</h4><p>The cost of turnover, measured against your payroll — the number investors actually care about.</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">05</div>
        <div class="ledger-body"><h4>Internal Mobility</h4><p>Whether you grow leaders from within, or quietly rebuild your leadership bench from outside every year.</p></div>
      </div>
    </div>

    <div class="grid-3" style="margin-top:16px;">
      <div class="stat-tile"><div class="label">Runs Entirely</div><div class="value">Offline</div></div>
      <div class="stat-tile"><div class="label">Your Data</div><div class="value">Stays On This Device</div></div>
      <div class="stat-tile"><div class="label">Report Format</div><div class="value">PDF + JSON Backup</div></div>
    </div>
  </section>

  <!-- ============ TEAM ============ -->
  <section class="view" id="view-team">
    <span class="eyebrow">Organization Registry</span>
    <h2 style="font-size:26px;">Teams &amp; Business Units</h2>
    <p style="max-width:70ch;">If you're tracking more than one team, department, or subsidiary, register them here first. Every report you calculate or upload can then be tagged to a team, so the Ledger and Risk Map can organize results by unit instead of one flat list.</p>

    <div class="card">
      <div class="form-grid">
        <div class="field">
          <label for="t-name">Team or Business Unit Name</label>
          <input type="text" id="t-name" placeholder="e.g., EMEA Engineering">
        </div>
        <div class="field">
          <label for="t-region">Region</label>
          <input type="text" id="t-region" placeholder="e.g., Western Europe">
        </div>
      </div>
      <div class="field">
        <label for="t-industry">Primary Industry</label>
        <select id="t-industry"></select>
      </div>
      <button class="btn btn-primary btn-sm" onclick="addTeam()">Add Team</button>
    </div>

    <div class="card">
      <span class="eyebrow">Registered Teams</span>
      <div id="teamList"></div>
    </div>
  </section>

  <!-- ============ CALCULATE ============ -->
  <section class="view" id="view-calculate">
    <span class="eyebrow">Manual Entry</span>
    <h2 style="font-size:26px;">Calculate a Human Equity Index</h2>
    <p style="max-width:70ch;">Enter figures for one company or business unit. Every field includes a plain-language explanation — nothing here assumes prior finance or HR background.</p>

    <div class="split" style="margin-top:24px;">
      <div class="card">
        <div class="form-section-title">Identity</div>
        <div class="form-grid">
          <div class="field">
            <label for="c-name">Company or Unit Name</label>
            <input type="text" id="c-name" placeholder="e.g., Meridian Analytics">
          </div>
          <div class="field">
            <label for="c-industry">Industry</label>
            <select id="c-industry"></select>
          </div>
        </div>
        <div class="form-grid">
          <div class="field">
            <label for="c-currency">Reporting Currency</label>
            <select id="c-currency"></select>
          </div>
          <div class="field">
            <label for="c-team">Assign to Team <span style="color:var(--slate-500);">(optional)</span></label>
            <select id="c-team"><option value="">No team — ad hoc report</option></select>
          </div>
        </div>

        <div class="form-section-title">Workforce Size &amp; Movement</div>
        <div class="form-grid">
          <div class="field">
            <label for="c-total">Current Total Employees</label>
            <input type="number" id="c-total" min="1" placeholder="e.g., 240">
          </div>
          <div class="field">
            <label for="c-exited">Employees Who Left Voluntarily (Past 12 Months)</label>
            <input type="number" id="c-exited" min="0" placeholder="e.g., 38">
          </div>
        </div>

        <div class="form-section-title">Tenure</div>
        <div class="form-grid">
          <div class="field">
            <label for="c-tenure-all">Average Tenure, All Staff (Years)</label>
            <input type="number" id="c-tenure-all" min="0" step="0.1" placeholder="e.g., 2.4">
          </div>
          <div class="field">
            <label for="c-tenure-spec">Average Tenure, Specialized/Senior Roles (Years)</label>
            <input type="number" id="c-tenure-spec" min="0" step="0.1" placeholder="e.g., 3.1">
            <div class="hint">Roles where losing the person also means losing hard-to-replace expertise.</div>
          </div>
        </div>

        <div class="form-section-title">Financial Impact</div>
        <div class="form-grid">
          <div class="field">
            <label for="c-salary">Average Annual Salary</label>
            <input type="number" id="c-salary" min="0" placeholder="e.g., 68000">
          </div>
          <div class="field">
            <label for="c-replace">Average Cost to Replace One Employee <span style="color:var(--slate-500);">(optional)</span></label>
            <input type="number" id="c-replace" min="0" placeholder="Leave blank to estimate">
            <div class="hint">If left blank, this is estimated at 75% of annual salary — a commonly cited general reference point, not a precise figure for your organization.</div>
          </div>
        </div>

        <div class="form-section-title">Internal Mobility</div>
        <div class="form-grid">
          <div class="field">
            <label for="c-promo">Internal Promotions (Past 12 Months)</label>
            <input type="number" id="c-promo" min="0" placeholder="e.g., 14">
          </div>
          <div class="field">
            <label for="c-exthire">External Hires Into Senior Roles (Past 12 Months)</label>
            <input type="number" id="c-exthire" min="0" placeholder="e.g., 6">
          </div>
        </div>

        <div class="hero-actions" style="margin-top:8px;">
          <button class="btn btn-primary" onclick="runCalculation()">Calculate Index</button>
          <button class="btn btn-ghost" onclick="clearForm()">Clear Form</button>
        </div>
      </div>

      <div class="results-pane" id="calcResultsPane">
        <div class="card empty">
          <svg width="40" height="40" viewBox="0 0 40 40"><circle cx="20" cy="20" r="17" fill="none" stroke="#8B94A8" stroke-width="1.5"/></svg>
          <p>Your rating seal, score breakdown, and financial summary will appear here once calculated.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- ============ UPLOAD ============ -->
  <section class="view" id="view-upload">
    <span class="eyebrow">Batch Analysis</span>
    <h2 style="font-size:26px;">Upload Samples</h2>
    <p style="max-width:70ch;">Upload a CSV sample of individual employee records and the platform will calculate every metric automatically — no manual aggregation required.</p>

    <div class="card">
      <div class="form-grid">
        <div class="field">
          <label for="u-name">Report Label</label>
          <input type="text" id="u-name" placeholder="e.g., Q3 Workforce Sample">
        </div>
        <div class="field">
          <label for="u-team">Assign to Team <span style="color:var(--slate-500);">(optional)</span></label>
          <select id="u-team"><option value="">No team — ad hoc report</option></select>
        </div>
      </div>
      <div class="field">
        <label for="u-currency">Reporting Currency</label>
        <select id="u-currency"></select>
      </div>
      <div class="dropzone" id="dropzone">
        <p><strong>Drop a CSV file here</strong>, or choose one manually.</p>
        <input type="file" id="csvInput" accept=".csv" style="display:none;">
        <button class="btn btn-primary btn-sm" onclick="document.getElementById('csvInput').click()">Choose CSV File</button>
        <button class="btn btn-ghost btn-sm" onclick="downloadTemplate()">Download Sample Template</button>
      </div>
      <div id="uploadStatus" style="margin-top:16px;"></div>
    </div>

    <div class="card">
      <span class="eyebrow">Expected Columns</span>
      <table>
        <thead><tr><th>Column</th><th>Format</th><th>Notes</th></tr></thead>
        <tbody>
          <tr><td class="mono">EmployeeID</td><td>Text</td><td>Any unique identifier</td></tr>
          <tr><td class="mono">Role</td><td>Text</td><td>For your own reference only</td></tr>
          <tr><td class="mono">SeniorityLevel</td><td>Specialized / Standard</td><td>Marks roles holding critical institutional knowledge</td></tr>
          <tr><td class="mono">HireDate</td><td>YYYY-MM-DD</td><td>Required</td></tr>
          <tr><td class="mono">ExitDate</td><td>YYYY-MM-DD or blank</td><td>Blank means still employed</td></tr>
          <tr><td class="mono">AnnualSalary</td><td>Number</td><td>In your chosen reporting currency</td></tr>
          <tr><td class="mono">Promoted</td><td>Yes / No</td><td>Optional — internal promotion in past 12 months</td></tr>
          <tr><td class="mono">ExternalSeniorHire</td><td>Yes / No</td><td>Optional — hired externally into a senior role</td></tr>
        </tbody>
      </table>
    </div>

    <div id="uploadResultsPane"></div>
  </section>

  <!-- ============ LEDGER ============ -->
  <section class="view" id="view-ledger">
    <span class="eyebrow">Saved Records</span>
    <h2 style="font-size:26px;">The Ledger</h2>
    <p style="max-width:70ch;">Every calculated report is stored here, on this device, so you can track a company's rating over time or compare business units side by side.</p>
    <div id="ledgerList"></div>
    <div class="card" id="compareCard" style="display:none;margin-top:20px;">
      <span class="eyebrow">Comparison</span>
      <div id="compareOutput"></div>
    </div>
  </section>

  <!-- ============ RISK MAP ============ -->
  <section class="view" id="view-riskmap">
    <span class="eyebrow">Organization-Wide View</span>
    <h2 style="font-size:26px;">Risk Map</h2>
    <p style="max-width:70ch;">A single score tells you how one team is doing. This tells you where the risk is concentrated across everything you've calculated — so leadership can see the whole organization at a glance, not one report at a time.</p>

    <div class="card" id="riskExposureCard"></div>

    <div class="card">
      <span class="eyebrow">Heat Map — All Saved Reports</span>
      <div class="field" style="max-width:260px;">
        <label for="rm-currency">Roll Up Exposure In</label>
        <select id="rm-currency" onchange="renderRiskMap()"></select>
      </div>
      <div class="heat-grid" id="heatGrid"></div>
    </div>
  </section>

  <!-- ============ HIDDEN COST ESTIMATOR ============ -->
  <section class="view" id="view-hce">
    <span class="eyebrow">Forward-Looking Scenarios</span>
    <h2 style="font-size:26px;">Hidden Cost Estimator</h2>
    <p style="max-width:70ch;">Your Financial Summary shows what turnover has already cost. This shows what it could cost next — adjust an assumption, see the exposure it creates.</p>

    <div class="card">
      <div class="field" style="max-width:420px;">
        <label for="hce-baseline">Baseline Report</label>
        <select id="hce-baseline" onchange="renderHCE()"></select>
      </div>
    </div>

    <div class="card" id="hceOutput"></div>
  </section>

  <!-- ============ COMMUNITY IMPACT ============ -->
  <section class="view" id="view-community">
    <span class="eyebrow">Beyond the Balance Sheet</span>
    <h2 style="font-size:26px;">Community Impact</h2>
    <p style="max-width:70ch;">Workforce instability doesn't stop at the org chart. These are rough, transparent, editable assumptions for estimating how far it actually reaches — useful context for ESG reporting and board-level conversations.</p>

    <div class="card">
      <div class="field" style="max-width:420px;">
        <label for="ci-baseline">Baseline Report</label>
        <select id="ci-baseline" onchange="renderCommunity()"></select>
      </div>
      <div class="form-grid">
        <div class="field">
          <label for="ci-dependents">Avg. Dependents per Employee</label>
          <input type="number" id="ci-dependents" step="0.1" value="2.1" onchange="renderCommunity()">
        </div>
        <div class="field">
          <label for="ci-spend">Avg. Local Spend (% of Salary)</label>
          <input type="number" id="ci-spend" step="1" value="45" onchange="renderCommunity()">
        </div>
      </div>
      <div class="field" style="max-width:300px;">
        <label for="ci-multiplier">Indirect Livelihoods per 10 Employees</label>
        <input type="number" id="ci-multiplier" step="0.1" value="4" onchange="renderCommunity()">
        <div class="hint">A commonly used general reference multiplier for illustrative purposes — adjust to fit your local context.</div>
      </div>
    </div>

    <div class="card" id="communityOutput"></div>
  </section>

  <!-- ============ RETENTION HEALTH AUDIT ============ -->
  <section class="view" id="view-audit">
    <span class="eyebrow">Practical, Not Theoretical</span>
    <h2 style="font-size:26px;">Retention Health Audit</h2>
    <p style="max-width:70ch;">A practical checklist, not a lecture. Check what's actually true today — this becomes part of your exported report.</p>

    <div class="audit-progress">
      <div class="ap-track"><div class="ap-fill" id="auditFill" style="width:0%"></div></div>
      <div class="ap-pct" id="auditPct">0%</div>
    </div>

    <div class="card" id="auditChecklist"></div>
  </section>

  <!-- ============ CURRENCY ============ -->
  <section class="view" id="view-currency">
    <span class="eyebrow">Reporting Currency</span>
    <h2 style="font-size:26px;">Currency &amp; Conversion</h2>
    <p style="max-width:70ch;">Reports are calculated in whichever currency you enter figures in. This section lets you maintain your own reference exchange rates for comparing figures across regions — since this platform works fully offline, rates are not fetched automatically and should be updated by hand as needed.</p>

    <div class="card">
      <span class="eyebrow">Quick Convert</span>
      <div class="form-grid">
        <div class="field">
          <label for="conv-amount">Amount</label>
          <input type="number" id="conv-amount" value="1000">
        </div>
        <div class="field">
          <label for="conv-from">From</label>
          <select id="conv-from"></select>
        </div>
      </div>
      <div class="form-grid">
        <div class="field">
          <label for="conv-to">To</label>
          <select id="conv-to"></select>
        </div>
        <div class="field">
          <label>Result</label>
          <div class="stat-tile"><div class="value mono" id="conv-result">—</div></div>
        </div>
      </div>
      <button class="btn btn-primary btn-sm" onclick="doConvert()">Convert</button>
    </div>

    <div class="card">
      <span class="eyebrow">Reference Rate Table (Editable — Relative to USD)</span>
      <p style="font-size:12.8px;">These are illustrative starting values, not live market rates. Update them to match current figures before relying on cross-currency comparisons.</p>
      <div id="rateTable"></div>
      <div class="hero-actions">
        <button class="btn btn-ghost btn-sm" onclick="saveRates()">Save Rates</button>
        <button class="btn btn-ghost btn-sm" onclick="resetRates()">Reset to Defaults</button>
      </div>
    </div>
  </section>

  <!-- ============ METHODOLOGY ============ -->
  <section class="view" id="view-methodology">
    <span class="eyebrow">Full Transparency</span>
    <h2 style="font-size:26px;">How the Index Is Calculated</h2>
    <p style="max-width:70ch;">Nothing here is a black box. Every input, weight, and formula used to produce your rating is documented below.</p>

    <div class="card">
      <span class="eyebrow">Weighting</span>
      <div class="weightbar-row"><div class="weightbar-label">01 · Retention Rate</div><div class="weightbar-track"><div class="weightbar-fill" style="width:30%"></div></div><div class="weightbar-val">30%</div></div>
      <div class="weightbar-row"><div class="weightbar-label">02 · Tenure Stability</div><div class="weightbar-track"><div class="weightbar-fill" style="width:20%"></div></div><div class="weightbar-val">20%</div></div>
      <div class="weightbar-row"><div class="weightbar-label">03 · Institutional Knowledge</div><div class="weightbar-track"><div class="weightbar-fill" style="width:20%"></div></div><div class="weightbar-val">20%</div></div>
      <div class="weightbar-row"><div class="weightbar-label">04 · Financial Resilience</div><div class="weightbar-track"><div class="weightbar-fill" style="width:15%"></div></div><div class="weightbar-val">15%</div></div>
      <div class="weightbar-row"><div class="weightbar-label">05 · Internal Mobility</div><div class="weightbar-track"><div class="weightbar-fill" style="width:15%"></div></div><div class="weightbar-val">15%</div></div>
    </div>

    <div class="card">
      <span class="eyebrow">Rating Scale</span>
      <table>
        <thead><tr><th>Score</th><th>Grade</th><th>Reading</th></tr></thead>
        <tbody>
          <tr><td class="mono">90–100</td><td><span class="badge badge-aaa">AAA</span></td><td>Exceptional — retention is a competitive advantage</td></tr>
          <tr><td class="mono">80–89.9</td><td><span class="badge badge-aa">AA</span></td><td>Strong — well above typical stability</td></tr>
          <tr><td class="mono">70–79.9</td><td><span class="badge badge-a">A</span></td><td>Stable — solid footing, room to strengthen</td></tr>
          <tr><td class="mono">60–69.9</td><td><span class="badge badge-bbb">BBB</span></td><td>Moderate — worth active attention</td></tr>
          <tr><td class="mono">50–59.9</td><td><span class="badge badge-bb">BB</span></td><td>Elevated Risk — turnover is likely visible in operations</td></tr>
          <tr><td class="mono">35–49.9</td><td><span class="badge badge-b">B</span></td><td>High Risk — institutional knowledge loss is probable</td></tr>
          <tr><td class="mono">0–34.9</td><td><span class="badge badge-ccc">CCC</span></td><td>Critical — structural instability</td></tr>
        </tbody>
      </table>
    </div>

    <div class="card">
      <span class="eyebrow">Formula Detail</span>
      <div class="ledger-line">
        <div class="ledger-num">01</div>
        <div class="ledger-body"><h4>Retention Rate</h4><p class="mono" style="font-size:13px;">100 − (Employees Exited ÷ Total Employees × 100)</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">02</div>
        <div class="ledger-body"><h4>Tenure Stability</h4><p>Your average tenure divided by an illustrative industry reference tenure, capped at 100. Reference figures are general starting points, not certified benchmarks — see below.</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">03</div>
        <div class="ledger-body"><h4>Institutional Knowledge</h4><p>Specialized-role tenure measured against a reference point 30% higher than the general benchmark, reflecting that critical roles ideally stay longer than average.</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">04</div>
        <div class="ledger-body"><h4>Financial Resilience</h4><p>Total replacement cost as a percentage of total payroll. Each percentage point of payroll lost to turnover reduces this sub-score by 8 points.</p></div>
      </div>
      <div class="ledger-line">
        <div class="ledger-num">05</div>
        <div class="ledger-body"><h4>Internal Mobility</h4><p class="mono" style="font-size:13px;">Internal Promotions ÷ (Internal Promotions + External Senior Hires) × 100</p></div>
      </div>
    </div>

    <div class="card">
      <span class="eyebrow">Industry Reference Tenure (Illustrative Midpoints)</span>
      <table id="benchmarkTable"></table>
    </div>

    <div class="card">
      <p style="font-size:12.8px;">This framework is designed as a directional, internally consistent scoring system for benchmarking and decision support. It is not a certified financial, accounting, actuarial, or investment instrument. For valuation, audit, or investment decisions, consult a qualified financial or legal professional.</p>
    </div>
  </section>

  <!-- ============ BACKUP ============ -->
  <section class="view" id="view-backup">
    <span class="eyebrow">Data &amp; Reports</span>
    <h2 style="font-size:26px;">Backup &amp; Export</h2>
    <p style="max-width:70ch;">Your data lives only on this device. Use PDF export to produce a shareable, human-readable report. Use JSON export to back up or migrate your full saved ledger.</p>

    <div class="grid-2">
      <div class="card">
        <span class="eyebrow">PDF Report</span>
        <p>Generates a formatted, printable report for the currently selected ledger entry — suitable for sharing with leadership, boards, or investors.</p>
        <select id="pdfSelect" style="margin-bottom:12px;"></select>
        <button class="btn btn-primary btn-sm" onclick="exportPDF()">Export as PDF</button>
      </div>
      <div class="card">
        <span class="eyebrow">Full Data Backup</span>
        <p>Exports every saved report and your currency settings as a single JSON file, for backup or moving to another device.</p>
        <button class="btn btn-primary btn-sm" onclick="exportJSON()">Export JSON Backup</button>
        <div style="margin-top:12px;">
          <label for="jsonImport" class="hint" style="display:block;margin-bottom:6px;">Restore from a previous backup:</label>
          <input type="file" id="jsonImport" accept=".json">
        </div>
      </div>
    </div>
  </section>

</main>

<footer>
  <div class="wrap">
    <p>The Human Equity Index runs entirely offline in your browser. No data is transmitted, stored remotely, or shared. All calculations occur locally on this device and are saved to this browser's local storage only. This tool provides a directional analytical framework, not certified financial or legal advice.</p>
  </div>
</footer>

<div id="toast"></div>

<!-- Hidden printable report area -->
<div id="printArea"></div>

<script>
/* =========================================================
   CONFIG
   ========================================================= */
const INDUSTRIES = [
  {key:"tech", label:"Technology & Software", benchmark:2.8},
  {key:"finance", label:"Financial Services", benchmark:4.5},
  {key:"health", label:"Healthcare", benchmark:4.0},
  {key:"mfg", label:"Manufacturing", benchmark:5.2},
  {key:"retail", label:"Retail & Consumer", benchmark:2.0},
  {key:"prof", label:"Professional Services", benchmark:3.5},
  {key:"nonprofit", label:"Nonprofit & Government", benchmark:6.0},
  {key:"other", label:"Other", benchmark:3.8}
];

const CURRENCIES = [
  {code:"USD", name:"US Dollar", symbol:"$", rate:1},
  {code:"EUR", name:"Euro", symbol:"€", rate:0.92},
  {code:"GBP", name:"British Pound", symbol:"£", rate:0.79},
  {code:"JPY", name:"Japanese Yen", symbol:"¥", rate:151},
  {code:"CNY", name:"Chinese Yuan", symbol:"¥", rate:7.2},
  {code:"INR", name:"Indian Rupee", symbol:"₹", rate:83},
  {code:"CAD", name:"Canadian Dollar", symbol:"CA$", rate:1.36},
  {code:"AUD", name:"Australian Dollar", symbol:"A$", rate:1.52},
  {code:"NGN", name:"Nigerian Naira", symbol:"₦", rate:1550},
  {code:"ZAR", name:"South African Rand", symbol:"R", rate:18.5},
  {code:"BRL", name:"Brazilian Real", symbol:"R$", rate:5.1},
  {code:"AED", name:"UAE Dirham", symbol:"AED", rate:3.67},
  {code:"SGD", name:"Singapore Dollar", symbol:"S$", rate:1.34},
  {code:"CHF", name:"Swiss Franc", symbol:"Fr", rate:0.88},
  {code:"KRW", name:"South Korean Won", symbol:"₩", rate:1330}
];

const STORAGE_KEY = "hei_ledger_v1";
const RATES_KEY = "hei_rates_v1";
const TEAMS_KEY = "hei_teams_v1";
const AUDIT_KEY = "hei_audit_v1";

const AUDIT_ITEMS = [
  {group:"Compensation & Recognition", items:[
    {id:"a1", text:"Compensation bands were benchmarked against market data within the past 12 months."},
    {id:"a2", text:"Pay equity was reviewed across gender, tenure, and role within the past 12 months."}
  ]},
  {group:"Growth & Mobility", items:[
    {id:"a3", text:"Internal mobility postings are visible to all employees before external job ads go out."},
    {id:"a4", text:"Every specialized or senior role has at least one documented successor or knowledge-transfer plan."}
  ]},
  {group:"Manager Quality", items:[
    {id:"a5", text:"Managers receive retention-risk data for their own team at least quarterly."},
    {id:"a6", text:"New hires in the past year received a structured onboarding program beyond paperwork."}
  ]},
  {group:"Exit Insight", items:[
    {id:"a7", text:"Exit interviews were conducted for at least 80% of departures in the past 12 months."},
    {id:"a8", text:"The organization tracks regretted vs. non-regretted turnover separately."}
  ]},
  {group:"Data Practices", items:[
    {id:"a9", text:"Employee sentiment or engagement was measured more than once in the past 12 months."},
    {id:"a10", text:"Specialized roles have documented processes or knowledge bases, not just tribal knowledge."},
    {id:"a11", text:"Leadership reviewed retention data at the executive level in the past quarter."},
    {id:"a12", text:"A formal stay-interview or retention program exists for high-performing or high-risk employees."}
  ]}
];

/* =========================================================
   STATE
   ========================================================= */
let ledger = JSON.parse(localStorage.getItem(STORAGE_KEY) || "[]");
let rates = JSON.parse(localStorage.getItem(RATES_KEY) || "null") || Object.fromEntries(CURRENCIES.map(c=>[c.code,c.rate]));

let teams = JSON.parse(localStorage.getItem(TEAMS_KEY) || "[]");
let auditState = JSON.parse(localStorage.getItem(AUDIT_KEY) || "{}");

function persistLedger(){ localStorage.setItem(STORAGE_KEY, JSON.stringify(ledger)); }
function persistRates(){ localStorage.setItem(RATES_KEY, JSON.stringify(rates)); }
function persistTeams(){ localStorage.setItem(TEAMS_KEY, JSON.stringify(teams)); }
function persistAudit(){ localStorage.setItem(AUDIT_KEY, JSON.stringify(auditState)); }

/* =========================================================
   CALCULATION ENGINE
   ========================================================= */
function clamp(n,min,max){ return Math.max(min, Math.min(max, n)); }

function calculateHEI(input){
  const industry = INDUSTRIES.find(i=>i.key===input.industryKey) || INDUSTRIES[INDUSTRIES.length-1];
  const benchmark = industry.benchmark;

  const totalEmployees = Math.max(1, input.totalEmployees);
  const exited = Math.max(0, input.exited);

  const turnoverRate = (exited / totalEmployees) * 100;
  const retentionScore = clamp(100 - turnoverRate, 0, 100);

  const tenureStabilityScore = clamp((input.tenureAll / benchmark) * 100, 0, 100);

  const specBenchmark = benchmark * 1.3;
  const institutionalScore = clamp((input.tenureSpec / specBenchmark) * 100, 0, 100);

  const replacementCost = input.replaceCost && input.replaceCost > 0 ? input.replaceCost : (input.salary * 0.75);
  const totalTurnoverCost = exited * replacementCost;
  const totalPayroll = totalEmployees * (input.salary || 1);
  const turnoverCostPctPayroll = input.salary > 0 ? (totalTurnoverCost / totalPayroll) * 100 : 0;
  const financialScore = clamp(100 - (turnoverCostPctPayroll * 8), 0, 100);

  const promo = Math.max(0, input.promo);
  const extHire = Math.max(0, input.extHire);
  const mobilityDenom = promo + extHire;
  const internalMobilityRate = mobilityDenom > 0 ? (promo / mobilityDenom) * 100 : 50;
  const mobilityScore = clamp(internalMobilityRate, 0, 100);

  const composite = (retentionScore*0.30) + (tenureStabilityScore*0.20) + (institutionalScore*0.20) + (financialScore*0.15) + (mobilityScore*0.15);
  const score = Math.round(composite * 10) / 10;

  let grade, tier, tierClass;
  if(score>=90){grade="AAA";tier="Exceptional";tierClass="badge-aaa";}
  else if(score>=80){grade="AA";tier="Strong";tierClass="badge-aa";}
  else if(score>=70){grade="A";tier="Stable";tierClass="badge-a";}
  else if(score>=60){grade="BBB";tier="Moderate";tierClass="badge-bbb";}
  else if(score>=50){grade="BB";tier="Elevated Risk";tierClass="badge-bb";}
  else if(score>=35){grade="B";tier="High Risk";tierClass="badge-b";}
  else{grade="CCC";tier="Critical";tierClass="badge-ccc";}

  return {
    score, grade, tier, tierClass,
    retentionScore: round1(retentionScore),
    tenureStabilityScore: round1(tenureStabilityScore),
    institutionalScore: round1(institutionalScore),
    financialScore: round1(financialScore),
    mobilityScore: round1(mobilityScore),
    turnoverRate: round1(turnoverRate),
    retentionRate: round1(100-turnoverRate),
    totalTurnoverCost: Math.round(totalTurnoverCost),
    turnoverCostPctPayroll: round1(turnoverCostPctPayroll),
    replacementCostUsed: Math.round(replacementCost),
    internalMobilityRate: round1(internalMobilityRate),
    industryLabel: industry.label,
    benchmarkUsed: benchmark
  };
}
function round1(n){ return Math.round(n*10)/10; }

/* =========================================================
   SVG: RATING SEAL
   ========================================================= */
function sealSVG(grade, score, size){
  size = size || 220;
  const c = size/2;
  const r1 = c - 8;
  const r2 = c - 20;
  const gradeColor = ["AAA","AA"].includes(grade) ? "#7FA37A" : (["A","BBB"].includes(grade) ? "#C98A3E" : "#B5533C");
  const id = "arc"+Math.random().toString(36).slice(2,8);
  return `
  <svg width="${size}" height="${size}" viewBox="0 0 ${size} ${size}">
    <defs>
      <path id="${id}" d="M ${c-r1},${c} a ${r1},${r1} 0 1 1 ${2*r1},0" fill="none"/>
    </defs>
    <circle cx="${c}" cy="${c}" r="${r1}" fill="#111A2C" stroke="#C9A24B" stroke-width="2"/>
    <circle cx="${c}" cy="${c}" r="${r2}" fill="none" stroke="#8F7130" stroke-width="1" stroke-dasharray="3 4"/>
    <text font-family="SF Mono, Consolas, monospace" font-size="9.5" letter-spacing="3" fill="#C9A24B">
      <textPath href="#${id}" startOffset="50%" text-anchor="middle">HUMAN EQUITY INDEX</textPath>
    </text>
    <text x="${c}" y="${c-4}" text-anchor="middle" font-family="Georgia, serif" font-size="${size*0.28}" font-weight="700" fill="${gradeColor}">${grade}</text>
    <text x="${c}" y="${c+size*0.19}" text-anchor="middle" font-family="SF Mono, Consolas, monospace" font-size="13" fill="#EDE7D9">${score.toFixed(1)}</text>
  </svg>`;
}

function scoreBarColor(v){
  if(v>=75) return "#7FA37A";
  if(v>=50) return "#C98A3E";
  return "#B5533C";
}

/* =========================================================
   RENDER: RESULTS PANEL (shared by Calculate + Upload)
   ========================================================= */
function renderResultsPanel(result, meta){
  const rows = [
    ["Retention Rate", result.retentionScore],
    ["Tenure Stability", result.tenureStabilityScore],
    ["Institutional Knowledge", result.institutionalScore],
    ["Financial Resilience", result.financialScore],
    ["Internal Mobility", result.mobilityScore]
  ];
  const curr = CURRENCIES.find(c=>c.code===meta.currency) || CURRENCIES[0];

  const barsHTML = rows.map(([name,val])=>`
    <div class="scorebar-row">
      <div class="scorebar-top"><span class="name">${name}</span><span class="val">${val.toFixed(1)}</span></div>
      <div class="scorebar-track"><div class="scorebar-fill" style="width:${val}%;background:${scoreBarColor(val)}"></div></div>
    </div>`).join("");

  return `
    <div class="card seal-figure">
      ${sealSVG(result.grade, result.score, 200)}
      <div class="seal-tier-label"><span class="badge ${result.tierClass}">${result.grade} — ${result.tier}</span></div>
      <div class="seal-score-line">Composite Score: <span class="mono">${result.score.toFixed(1)} / 100</span></div>
    </div>
    <div class="card">
      <span class="eyebrow">Score Breakdown</span>
      ${barsHTML}
    </div>
    <div class="card">
      <span class="eyebrow">Financial Summary (${curr.code})</span>
      <div class="grid-2">
        <div class="stat-tile"><div class="label">Est. Total Turnover Cost</div><div class="value rust">${curr.symbol}${result.totalTurnoverCost.toLocaleString()}</div></div>
        <div class="stat-tile"><div class="label">% of Payroll Lost</div><div class="value">${result.turnoverCostPctPayroll.toFixed(1)}%</div></div>
        <div class="stat-tile"><div class="label">Retention Rate</div><div class="value sage">${result.retentionRate.toFixed(1)}%</div></div>
        <div class="stat-tile"><div class="label">Internal Mobility Rate</div><div class="value">${result.internalMobilityRate.toFixed(1)}%</div></div>
      </div>
      <p style="font-size:12px;margin-top:14px;">Reference tenure used: <span class="mono">${result.benchmarkUsed} yrs</span> (${result.industryLabel}). Replacement cost applied: <span class="mono">${curr.symbol}${result.replacementCostUsed.toLocaleString()}</span> per departure.</p>
    </div>
    <div class="hero-actions">
      <button class="btn btn-primary btn-sm" onclick="saveToLedger('${meta.id}')">Save to Ledger</button>
    </div>
  `;
}

/* =========================================================
   PENDING RESULT (holds last calculated result for saving)
   ========================================================= */
let pending = null;

function runCalculation(){
  const name = document.getElementById("c-name").value.trim() || "Untitled Company";
  const industryKey = document.getElementById("c-industry").value;
  const currency = document.getElementById("c-currency").value;
  const teamId = document.getElementById("c-team").value || null;
  const totalEmployees = parseFloat(document.getElementById("c-total").value) || 0;
  const exited = parseFloat(document.getElementById("c-exited").value) || 0;
  const tenureAll = parseFloat(document.getElementById("c-tenure-all").value) || 0;
  const tenureSpec = parseFloat(document.getElementById("c-tenure-spec").value) || 0;
  const salary = parseFloat(document.getElementById("c-salary").value) || 0;
  const replaceCost = parseFloat(document.getElementById("c-replace").value) || 0;
  const promo = parseFloat(document.getElementById("c-promo").value) || 0;
  const extHire = parseFloat(document.getElementById("c-exthire").value) || 0;

  if(totalEmployees <= 0){ toast("Enter a total employee count greater than zero."); return; }

  const result = calculateHEI({industryKey,totalEmployees,exited,tenureAll,tenureSpec,salary,replaceCost,promo,extHire});
  const id = "r_"+Date.now();
  pending = {id, name, industryKey, currency, teamId, date: new Date().toISOString(), result, source:"manual"};

  document.getElementById("calcResultsPane").innerHTML = renderResultsPanel(result, {id, currency});
  toast("Index calculated.");
}

function clearForm(){
  ["c-name","c-total","c-exited","c-tenure-all","c-tenure-spec","c-salary","c-replace","c-promo","c-exthire"].forEach(id=>document.getElementById(id).value="");
  document.getElementById("calcResultsPane").innerHTML = `<div class="card empty"><p>Form cleared.</p></div>`;
}

function saveToLedger(id){
  if(!pending || pending.id !== id){ toast("Nothing to save — calculate first."); return; }
  ledger.unshift(pending);
  persistLedger();
  renderLedgerList();
  refreshPdfSelect();
  renderTeamList();
  refreshBaselineSelects();
  toast("Saved to Ledger.");
}

/* =========================================================
   CSV UPLOAD
   ========================================================= */
const dropzone = document.getElementById("dropzone");
const csvInput = document.getElementById("csvInput");
["dragover","dragenter"].forEach(evt=>dropzone.addEventListener(evt,e=>{e.preventDefault();dropzone.classList.add("drag");}));
["dragleave","drop"].forEach(evt=>dropzone.addEventListener(evt,e=>{e.preventDefault();dropzone.classList.remove("drag");}));
dropzone.addEventListener("drop", e=>{
  const f = e.dataTransfer.files[0];
  if(f) handleCSV(f);
});
csvInput.addEventListener("change", e=>{
  const f = e.target.files[0];
  if(f) handleCSV(f);
});

function downloadTemplate(){
  const header = "EmployeeID,Role,SeniorityLevel,HireDate,ExitDate,AnnualSalary,Promoted,ExternalSeniorHire\n";
  const sample =
    "E001,Senior Engineer,Specialized,2021-03-14,,142000,No,No\n"+
    "E002,Support Analyst,Standard,2023-01-09,,58000,Yes,No\n"+
    "E003,Account Manager,Standard,2019-06-01,2024-02-20,71000,No,No\n"+
    "E004,Lead Architect,Specialized,2018-11-11,,168000,No,Yes\n";
  downloadBlob(header+sample, "human-equity-index-sample-template.csv", "text/csv");
}

function handleCSV(file){
  const reader = new FileReader();
  reader.onload = e => {
    try{
      const parsed = parseCSV(e.target.result);
      const result = calculateFromRecords(parsed.records);
      const currency = document.getElementById("u-currency").value || "USD";
      const teamId = document.getElementById("u-team").value || null;
      const id = "r_"+Date.now();
      const name = document.getElementById("u-name").value.trim() || file.name.replace(/\.csv$/i,"");
      pending = {id, name, industryKey:"other", currency, teamId, date:new Date().toISOString(), result, source:"upload"};
      document.getElementById("uploadStatus").innerHTML = `<p style="color:var(--sage-300);">Parsed ${parsed.records.length} employee records successfully.</p>`;
      document.getElementById("uploadResultsPane").innerHTML = renderResultsPanel(result, {id, currency});
      toast("File processed.");
    }catch(err){
      document.getElementById("uploadStatus").innerHTML = `<p style="color:var(--rust-300);">Could not process this file: ${err.message}</p>`;
    }
  };
  reader.readAsText(file);
}

function parseCSV(text){
  const lines = text.split(/\r?\n/).map(l=>l.trim()).filter(l=>l.length>0);
  if(lines.length < 2) throw new Error("File must include a header row and at least one data row.");
  const headers = lines[0].split(",").map(h=>h.trim().toLowerCase());
  const records = [];
  for(let i=1;i<lines.length;i++){
    const cells = lines[i].split(",").map(c=>c.trim());
    const rec = {};
    headers.forEach((h,idx)=> rec[h] = cells[idx] !== undefined ? cells[idx] : "");
    records.push(rec);
  }
  return {records};
}

function calculateFromRecords(records){
  const parseDate = s => s ? new Date(s+"T00:00:00") : null;
  let refDate = new Date(0);
  records.forEach(r=>{
    const hd = parseDate(r.hiredate);
    const ed = parseDate(r.exitdate);
    if(hd && hd > refDate) refDate = hd;
    if(ed && ed > refDate) refDate = ed;
  });
  if(refDate.getTime()===0) refDate = new Date();

  const current = records.filter(r=>!r.exitdate);
  const exitedInWindow = records.filter(r=>{
    if(!r.exitdate) return false;
    const ed = parseDate(r.exitdate);
    const days = (refDate - ed) / (1000*60*60*24);
    return days >= 0 && days <= 365;
  });

  const totalEmployees = current.length + exitedInWindow.length;
  const exited = exitedInWindow.length;

  const tenureYears = (rec) => {
    const hd = parseDate(rec.hiredate);
    if(!hd) return 0;
    const end = rec.exitdate ? parseDate(rec.exitdate) : refDate;
    return Math.max(0,(end - hd) / (1000*60*60*24*365.25));
  };

  const currentTenures = current.map(tenureYears);
  const tenureAll = currentTenures.length ? currentTenures.reduce((a,b)=>a+b,0)/currentTenures.length : 0;

  const specRecords = current.filter(r => (r.senioritylevel||"").toLowerCase()==="specialized");
  const specTenures = specRecords.map(tenureYears);
  const tenureSpec = specTenures.length ? specTenures.reduce((a,b)=>a+b,0)/specTenures.length : tenureAll;

  const salaries = current.map(r=>parseFloat(r.annualsalary)||0).filter(v=>v>0);
  const salary = salaries.length ? salaries.reduce((a,b)=>a+b,0)/salaries.length : 0;

  const promo = records.filter(r=>(r.promoted||"").toLowerCase()==="yes").length;
  const extHire = records.filter(r=>(r.externalseniorhire||"").toLowerCase()==="yes").length;

  return calculateHEI({industryKey:"other", totalEmployees, exited, tenureAll, tenureSpec, salary, replaceCost:0, promo, extHire});
}

/* =========================================================
   LEDGER
   ========================================================= */
function renderLedgerList(){
  const el = document.getElementById("ledgerList");
  if(ledger.length===0){
    el.innerHTML = `<div class="card empty"><svg width="40" height="40" viewBox="0 0 40 40"><circle cx="20" cy="20" r="17" fill="none" stroke="#8B94A8" stroke-width="1.5"/></svg><p>No saved reports yet. Calculate or upload data to begin building your ledger.</p></div>`;
    return;
  }
  el.innerHTML = `<div class="card"><table>
    <thead><tr><th><input type="checkbox" id="selAll"></th><th>Company</th><th>Industry</th><th>Date</th><th>Score</th><th>Grade</th><th></th></tr></thead>
    <tbody>
    ${ledger.map(r=>{
      const ind = INDUSTRIES.find(i=>i.key===r.industryKey);
      return `<tr>
        <td><input type="checkbox" class="cmp" value="${r.id}"></td>
        <td>${escapeHTML(r.name)}</td>
        <td>${ind?ind.label:"—"}</td>
        <td class="mono">${new Date(r.date).toLocaleDateString()}</td>
        <td class="mono">${r.result.score.toFixed(1)}</td>
        <td><span class="badge ${r.result.tierClass}">${r.result.grade}</span></td>
        <td><button class="btn btn-danger btn-sm" onclick="deleteEntry('${r.id}')">Delete</button></td>
      </tr>`;
    }).join("")}
    </tbody></table>
    <div class="hero-actions"><button class="btn btn-ghost btn-sm" onclick="compareSelected()">Compare Selected</button></div>
    </div>`;
}

function deleteEntry(id){
  ledger = ledger.filter(r=>r.id!==id);
  persistLedger();
  renderLedgerList();
  refreshPdfSelect();
  toast("Entry deleted.");
}

function compareSelected(){
  const checked = Array.from(document.querySelectorAll(".cmp:checked")).map(c=>c.value);
  if(checked.length < 2){ toast("Select at least two reports to compare."); return; }
  const items = ledger.filter(r=>checked.includes(r.id));
  const dims = [["retentionScore","Retention"],["tenureStabilityScore","Tenure Stability"],["institutionalScore","Institutional Knowledge"],["financialScore","Financial Resilience"],["mobilityScore","Internal Mobility"]];
  let html = `<div class="grid-3">`;
  items.forEach(it=>{
    html += `<div class="stat-tile"><div class="label">${escapeHTML(it.name)}</div><div class="value">${it.result.grade} · ${it.result.score.toFixed(1)}</div></div>`;
  });
  html += `</div><div style="margin-top:18px;">`;
  dims.forEach(([key,label])=>{
    html += `<div style="margin:14px 0;"><div style="font-size:13px;color:var(--parchment-200);margin-bottom:6px;">${label}</div>`;
    items.forEach(it=>{
      const v = it.result[key];
      html += `<div class="scorebar-row"><div class="scorebar-top"><span class="name">${escapeHTML(it.name)}</span><span class="val">${v.toFixed(1)}</span></div><div class="scorebar-track"><div class="scorebar-fill" style="width:${v}%;background:${scoreBarColor(v)}"></div></div></div>`;
    });
    html += `</div>`;
  });
  html += `</div>`;
  document.getElementById("compareOutput").innerHTML = html;
  document.getElementById("compareCard").style.display = "block";
}

function escapeHTML(s){ return (s+"").replace(/[&<>"']/g, m=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[m])); }

/* =========================================================
   CURRENCY VIEW
   ========================================================= */
function populateCurrencySelects(){
  const opts = CURRENCIES.map(c=>`<option value="${c.code}">${c.code} — ${c.name}</option>`).join("");
  document.getElementById("c-currency").innerHTML = opts;
  document.getElementById("u-currency").innerHTML = opts;
  document.getElementById("rm-currency").innerHTML = opts;
  document.getElementById("conv-from").innerHTML = opts;
  document.getElementById("conv-to").innerHTML = opts;
  document.getElementById("conv-to").value = "EUR";
}

function renderRateTable(){
  const el = document.getElementById("rateTable");
  el.innerHTML = CURRENCIES.map(c=>`
    <div class="rate-row">
      <div class="code">${c.code}</div>
      <div class="name">${c.name}</div>
      <input type="number" step="0.0001" id="rate-${c.code}" value="${rates[c.code]}">
    </div>`).join("");
}

function saveRates(){
  CURRENCIES.forEach(c=>{
    const v = parseFloat(document.getElementById("rate-"+c.code).value);
    if(v>0) rates[c.code]=v;
  });
  persistRates();
  toast("Reference rates saved.");
}

function resetRates(){
  rates = Object.fromEntries(CURRENCIES.map(c=>[c.code,c.rate]));
  persistRates();
  renderRateTable();
  toast("Rates reset to defaults.");
}

function convertAmount(amount, fromCode, toCode){
  if(fromCode===toCode) return amount;
  const usd = amount / (rates[fromCode] || 1);
  return usd * (rates[toCode] || 1);
}

function doConvert(){
  const amt = parseFloat(document.getElementById("conv-amount").value)||0;
  const from = document.getElementById("conv-from").value;
  const to = document.getElementById("conv-to").value;
  const usd = amt / rates[from];
  const result = usd * rates[to];
  const toCurr = CURRENCIES.find(c=>c.code===to);
  document.getElementById("conv-result").textContent = `${toCurr.symbol}${result.toLocaleString(undefined,{maximumFractionDigits:2})}`;
}

/* =========================================================
   INDUSTRY SELECT + BENCHMARK TABLE
   ========================================================= */
function populateIndustrySelect(){
  const opts = INDUSTRIES.map(i=>`<option value="${i.key}">${i.label}</option>`).join("");
  document.getElementById("c-industry").innerHTML = opts;
  document.getElementById("t-industry").innerHTML = opts;
}
/* =========================================================
   TEAMS
   ========================================================= */
function addTeam(){
  const name = document.getElementById("t-name").value.trim();
  const region = document.getElementById("t-region").value.trim();
  const industryKey = document.getElementById("t-industry").value;
  if(!name){ toast("Enter a team name."); return; }
  teams.unshift({id:"t_"+Date.now(), name, region, industryKey});
  persistTeams();
  document.getElementById("t-name").value = "";
  document.getElementById("t-region").value = "";
  renderTeamList();
  populateTeamSelects();
  toast("Team added.");
}

function deleteTeam(id){
  teams = teams.filter(t=>t.id!==id);
  persistTeams();
  renderTeamList();
  populateTeamSelects();
  toast("Team removed.");
}

function renderTeamList(){
  const el = document.getElementById("teamList");
  if(teams.length===0){
    el.innerHTML = `<div class="empty"><p>No teams registered yet. Add one above, or skip this if you're only tracking a single company.</p></div>`;
    return;
  }
  el.innerHTML = teams.map(t=>{
    const ind = INDUSTRIES.find(i=>i.key===t.industryKey);
    const reportCount = ledger.filter(r=>r.teamId===t.id).length;
    return `<div class="team-card">
      <div>
        <div class="t-name">${escapeHTML(t.name)}</div>
        <div class="t-meta">${escapeHTML(t.region||"—")} · ${ind?ind.label:"—"} · ${reportCount} saved report${reportCount===1?"":"s"}</div>
      </div>
      <button class="btn btn-danger btn-sm" onclick="deleteTeam('${t.id}')">Remove</button>
    </div>`;
  }).join("");
}

function populateTeamSelects(){
  const opts = `<option value="">No team — ad hoc report</option>` + teams.map(t=>`<option value="${t.id}">${escapeHTML(t.name)}</option>`).join("");
  ["c-team","u-team"].forEach(id=>{
    const el = document.getElementById(id);
    if(el) el.innerHTML = opts;
  });
}

function renderBenchmarkTable(){
  document.getElementById("benchmarkTable").innerHTML = `
    <thead><tr><th>Industry</th><th>Reference Tenure</th></tr></thead>
    <tbody>${INDUSTRIES.map(i=>`<tr><td>${i.label}</td><td class="mono">${i.benchmark} yrs</td></tr>`).join("")}</tbody>`;
}

/* =========================================================
   RISK MAP
   ========================================================= */
function tierCellClass(grade){
  const map = {AAA:"heat-tier-aaa",AA:"heat-tier-aa",A:"heat-tier-a",BBB:"heat-tier-bbb",BB:"heat-tier-bb",B:"heat-tier-b",CCC:"heat-tier-ccc"};
  return map[grade] || "heat-tier-bbb";
}

function renderRiskMap(){
  const rollupCode = document.getElementById("rm-currency").value || "USD";
  const rollupCurr = CURRENCIES.find(c=>c.code===rollupCode) || CURRENCIES[0];

  if(ledger.length===0){
    document.getElementById("riskExposureCard").innerHTML = `<div class="empty"><p>No saved reports yet. Calculate or upload at least one report to populate the Risk Map.</p></div>`;
    document.getElementById("heatGrid").innerHTML = "";
    return;
  }

  let totalExposure = 0;
  let critical = 0, elevated = 0, stable = 0;
  ledger.forEach(r=>{
    totalExposure += convertAmount(r.result.totalTurnoverCost, r.currency, rollupCode);
    if(["CCC","B"].includes(r.result.grade)) critical++;
    else if(["BB"].includes(r.result.grade)) elevated++;
    else stable++;
  });

  document.getElementById("riskExposureCard").innerHTML = `
    <span class="eyebrow">Exposure Summary</span>
    <div class="grid-3">
      <div class="stat-tile"><div class="label">Total Turnover Exposure</div><div class="value rust">${rollupCurr.symbol}${Math.round(totalExposure).toLocaleString()}</div></div>
      <div class="stat-tile"><div class="label">Reports at High/Critical Risk</div><div class="value rust">${critical}</div></div>
      <div class="stat-tile"><div class="label">Reports Stable or Better</div><div class="value sage">${stable}</div></div>
    </div>
    <p style="font-size:12px;margin-top:12px;">Exposure figures are converted to ${rollupCurr.code} using your reference rate table under Currency — update those rates for an accurate rollup.</p>
  `;

  document.getElementById("heatGrid").innerHTML = ledger.map(r=>{
    const team = teams.find(t=>t.id===r.teamId);
    return `<div class="heat-cell ${tierCellClass(r.result.grade)}">
      <div class="h-name">${escapeHTML(r.name)}${team?`<br><span style="font-weight:400;opacity:.8;">${escapeHTML(team.name)}</span>`:""}</div>
      <div class="h-grade">${r.result.grade}</div>
      <div class="h-score">${r.result.score.toFixed(1)} / 100</div>
    </div>`;
  }).join("");
}

/* =========================================================
   HIDDEN COST ESTIMATOR — [Assumption] = [Exposure Summary]
   ========================================================= */
function refreshBaselineSelects(){
  const opts = ledger.length===0
    ? `<option value="">No saved reports yet</option>`
    : ledger.map(r=>`<option value="${r.id}">${escapeHTML(r.name)} — ${new Date(r.date).toLocaleDateString()}</option>`).join("");
  ["hce-baseline","ci-baseline"].forEach(id=>{
    const el = document.getElementById(id);
    if(el) el.innerHTML = opts;
  });
  renderHCE();
  renderCommunity();
}

function renderHCE(){
  const out = document.getElementById("hceOutput");
  if(ledger.length===0){
    out.innerHTML = `<div class="empty"><p>Save a report to the Ledger first, then return here to model scenarios against it.</p></div>`;
    return;
  }
  const id = document.getElementById("hce-baseline").value;
  const r = ledger.find(x=>x.id===id) || ledger[0];
  const curr = CURRENCIES.find(c=>c.code===r.currency) || CURRENCIES[0];
  const res = r.result;

  const extraTurnoverPts = 5;
  const extraCost1 = (extraTurnoverPts/100) * (res.replacementCostUsed * 10);
  const fillDelayMonths = 3;
  const specSalaryMonthly = (res.replacementCostUsed / 0.75) / 12 || 0;
  const extraCost2 = fillDelayMonths * specSalaryMonthly * 0.5;
  const specDepartures = 2;
  const extraCost3 = specDepartures * res.replacementCostUsed * 1.5;

  out.innerHTML = `
    <span class="eyebrow">Baseline: ${escapeHTML(r.name)} — ${res.grade} · ${res.score.toFixed(1)}</span>

    <div class="assume-row">
      <div class="assume-side">
        <div class="a-label">Assumption: turnover rises by ${extraTurnoverPts} percentage points</div>
        <div class="a-value">+${extraTurnoverPts}% turnover</div>
      </div>
      <div class="assume-eq">=</div>
      <div class="assume-side">
        <div class="a-label">Exposure Summary</div>
        <div class="a-value rust">${curr.symbol}${Math.round(extraCost1).toLocaleString()} additional cost</div>
      </div>
    </div>

    <div class="assume-row">
      <div class="assume-side">
        <div class="a-label">Assumption: specialized vacancies take ${fillDelayMonths} months longer to fill</div>
        <div class="a-value">+${fillDelayMonths} mo. fill delay</div>
      </div>
      <div class="assume-eq">=</div>
      <div class="assume-side">
        <div class="a-label">Exposure Summary</div>
        <div class="a-value rust">${curr.symbol}${Math.round(extraCost2).toLocaleString()} in lost productivity</div>
      </div>
    </div>

    <div class="assume-row">
      <div class="assume-side">
        <div class="a-label">Assumption: you lose ${specDepartures} of your most specialized staff this year</div>
        <div class="a-value">${specDepartures} specialized exits</div>
      </div>
      <div class="assume-eq">=</div>
      <div class="assume-side">
        <div class="a-label">Exposure Summary</div>
        <div class="a-value rust">${curr.symbol}${Math.round(extraCost3).toLocaleString()} at elevated replacement cost</div>
      </div>
    </div>

    <div class="assume-row">
      <div class="assume-side">
        <div class="a-label">Combined scenario — total additional exposure</div>
        <div class="a-value rust">${curr.symbol}${Math.round(extraCost1+extraCost2+extraCost3).toLocaleString()}</div>
      </div>
      <div class="assume-eq">=</div>
      <div class="assume-side">
        <div class="a-label">Projected rating under this scenario</div>
        <div class="a-value">${res.score - 12 <= 0 ? "CCC" : (res.score-12>=90?"AAA":gradeForScore(res.score-12))} <span style="font-size:12px;color:var(--slate-500);">(illustrative shift)</span></div>
      </div>
    </div>
    <p style="font-size:12px;margin-top:10px;">These are illustrative planning scenarios built from your baseline figures, not certified financial forecasts. Adjust the underlying assumptions as your own context requires.</p>
  `;
}

function gradeForScore(score){
  if(score>=90) return "AAA";
  if(score>=80) return "AA";
  if(score>=70) return "A";
  if(score>=60) return "BBB";
  if(score>=50) return "BB";
  if(score>=35) return "B";
  return "CCC";
}

/* =========================================================
   COMMUNITY IMPACT — [Assumptions] = [Estimated Reach]
   ========================================================= */
function renderCommunity(){
  const out = document.getElementById("communityOutput");
  if(ledger.length===0){
    out.innerHTML = `<div class="empty"><p>Save a report to the Ledger first, then return here to estimate community reach.</p></div>`;
    return;
  }
  const id = document.getElementById("ci-baseline").value;
  const r = ledger.find(x=>x.id===id) || ledger[0];
  const res = r.result;
  const dependents = parseFloat(document.getElementById("ci-dependents").value) || 0;
  const spendPct = parseFloat(document.getElementById("ci-spend").value) || 0;
  const jobsMultiplier = parseFloat(document.getElementById("ci-multiplier").value) || 0;
  const curr = CURRENCIES.find(c=>c.code===r.currency) || CURRENCIES[0];

  const exitedCount = Math.round((res.turnoverRate/100) * 100) / 100;
  const approxExited = Math.max(1, Math.round((100-res.retentionRate)/100 * (res.replacementCostUsed>0 ? (res.totalTurnoverCost/res.replacementCostUsed) : 1)));
  const dependentsAffected = Math.round(approxExited * dependents);
  const localSpendAtRisk = Math.round(res.totalTurnoverCost * (spendPct/100));
  const indirectLivelihoods = Math.round((approxExited/10) * jobsMultiplier * 10);

  out.innerHTML = `
    <span class="eyebrow">Baseline: ${escapeHTML(r.name)}</span>

    <div class="assume-row">
      <div class="assume-side">
        <div class="a-label">Assumption: ~${approxExited} departures, ${dependents} dependents each</div>
        <div class="a-value">${dependents} dependents / employee</div>
      </div>
      <div class="assume-eq">=</div>
      <div class="assume-side">
        <div class="a-label">Estimated Reach</div>
        <div class="a-value">${dependentsAffected.toLocaleString()} family members indirectly affected</div>
      </div>
    </div>

    <div class="assume-row">
      <div class="assume-side">
        <div class="a-label">Assumption: ${spendPct}% of turnover cost reflects local economic spend</div>
        <div class="a-value">${spendPct}% local spend rate</div>
      </div>
      <div class="assume-eq">=</div>
      <div class="assume-side">
        <div class="a-label">Estimated Reach</div>
        <div class="a-value">${curr.symbol}${localSpendAtRisk.toLocaleString()} in local economic activity at risk</div>
      </div>
    </div>

    <div class="assume-row">
      <div class="assume-side">
        <div class="a-label">Assumption: ${jobsMultiplier} indirect livelihoods per 10 employees</div>
        <div class="a-value">${jobsMultiplier} / 10 employees</div>
      </div>
      <div class="assume-eq">=</div>
      <div class="assume-side">
        <div class="a-label">Estimated Reach</div>
        <div class="a-value">${indirectLivelihoods.toLocaleString()} indirect livelihoods connected to workforce stability</div>
      </div>
    </div>

    <p style="font-size:12px;margin-top:10px;">These figures are rough, editable, order-of-magnitude estimates intended to support ESG and board-level context — not audited social impact metrics.</p>
  `;
}

/* =========================================================
   RETENTION HEALTH AUDIT
   ========================================================= */
function renderAudit(){
  const el = document.getElementById("auditChecklist");
  el.innerHTML = AUDIT_ITEMS.map(g=>`
    <div class="check-group-title">${g.group}</div>
    ${g.items.map(it=>`
      <div class="check-item">
        <input type="checkbox" id="chk-${it.id}" ${auditState[it.id]?"checked":""} onchange="toggleAuditItem('${it.id}')">
        <label for="chk-${it.id}">${it.text}</label>
      </div>`).join("")}
  `).join("");
  updateAuditProgress();
}

function toggleAuditItem(id){
  auditState[id] = document.getElementById("chk-"+id).checked;
  persistAudit();
  updateAuditProgress();
}

function updateAuditProgress(){
  const all = AUDIT_ITEMS.flatMap(g=>g.items);
  const checked = all.filter(it=>auditState[it.id]).length;
  const pct = Math.round((checked/all.length)*100);
  document.getElementById("auditFill").style.width = pct+"%";
  document.getElementById("auditPct").textContent = pct+"%";
}

/* =========================================================
   PDF EXPORT (print-based, fully offline)
   ========================================================= */
function refreshPdfSelect(){
  const sel = document.getElementById("pdfSelect");
  if(ledger.length===0){ sel.innerHTML = `<option>No saved reports yet</option>`; return; }
  sel.innerHTML = ledger.map(r=>`<option value="${r.id}">${escapeHTML(r.name)} — ${new Date(r.date).toLocaleDateString()}</option>`).join("");
}

function exportPDF(){
  if(ledger.length===0){ toast("Save a report to the Ledger first."); return; }
  const id = document.getElementById("pdfSelect").value;
  const r = ledger.find(x=>x.id===id);
  if(!r){ toast("Select a report."); return; }
  const curr = CURRENCIES.find(c=>c.code===r.currency) || CURRENCIES[0];
  const ind = INDUSTRIES.find(i=>i.key===r.industryKey);
  const team = teams.find(t=>t.id===r.teamId);
  const res = r.result;

  const auditAll = AUDIT_ITEMS.flatMap(g=>g.items);
  const auditChecked = auditAll.filter(it=>auditState[it.id]).length;
  const auditPct = Math.round((auditChecked/auditAll.length)*100);
  const auditRowsHTML = AUDIT_ITEMS.map(g=>`
    <tr><td colspan="2" style="font-weight:700;padding-top:14px;">${g.group}</td></tr>
    ${g.items.map(it=>`<tr><td>${it.text}</td><td>${auditState[it.id]?"Yes":"Not yet"}</td></tr>`).join("")}
  `).join("");

  document.getElementById("printArea").innerHTML = `
    <div class="p-header">
      <div class="p-sub">Human Equity Index — Rating Report</div>
      <h1 class="p-title">${escapeHTML(r.name)}</h1>
      <div class="p-sub">${ind?ind.label:""}${team?` · Team: ${escapeHTML(team.name)}`:""} · Generated ${new Date(r.date).toLocaleDateString()} · Reporting Currency: ${curr.code}</div>
    </div>
    <div class="p-grade">${res.grade} <span style="font-size:16px;font-family:monospace;">— ${res.tier}</span></div>
    <div style="font-family:monospace;font-size:14px;margin-bottom:20px;">Composite Score: ${res.score.toFixed(1)} / 100</div>
    <table>
      <thead><tr><th>Component</th><th>Score</th></tr></thead>
      <tbody>
        <tr><td>Retention Rate</td><td>${res.retentionScore.toFixed(1)}</td></tr>
        <tr><td>Tenure Stability</td><td>${res.tenureStabilityScore.toFixed(1)}</td></tr>
        <tr><td>Institutional Knowledge</td><td>${res.institutionalScore.toFixed(1)}</td></tr>
        <tr><td>Financial Resilience</td><td>${res.financialScore.toFixed(1)}</td></tr>
        <tr><td>Internal Mobility</td><td>${res.mobilityScore.toFixed(1)}</td></tr>
      </tbody>
    </table>
    <table>
      <thead><tr><th>Financial Summary</th><th></th></tr></thead>
      <tbody>
        <tr><td>Estimated Total Turnover Cost</td><td>${curr.symbol}${res.totalTurnoverCost.toLocaleString()}</td></tr>
        <tr><td>Turnover Cost as % of Payroll</td><td>${res.turnoverCostPctPayroll.toFixed(1)}%</td></tr>
        <tr><td>Retention Rate</td><td>${res.retentionRate.toFixed(1)}%</td></tr>
        <tr><td>Internal Mobility Rate</td><td>${res.internalMobilityRate.toFixed(1)}%</td></tr>
        <tr><td>Reference Tenure Used</td><td>${res.benchmarkUsed} yrs</td></tr>
      </tbody>
    </table>
    <table>
      <thead><tr><th>Retention Health Audit — ${auditPct}% Complete</th><th>Status</th></tr></thead>
      <tbody>${auditRowsHTML}</tbody>
    </table>
    <div class="p-disclaimer">This report was generated by the Human Equity Index platform, an offline directional analytical framework for retention benchmarking. It is not a certified financial, accounting, or investment instrument. For valuation, audit, or investment decisions, consult a qualified professional.</div>
  `;
  window.print();
}

/* =========================================================
   JSON BACKUP
   ========================================================= */
function exportJSON(){
  const payload = {exportedAt:new Date().toISOString(), ledger, rates, teams, auditState};
  downloadBlob(JSON.stringify(payload,null,2), "human-equity-index-backup.json", "application/json");
  toast("Backup exported.");
}
document.getElementById("jsonImport").addEventListener("change", e=>{
  const f = e.target.files[0];
  if(!f) return;
  const reader = new FileReader();
  reader.onload = ev=>{
    try{
      const data = JSON.parse(ev.target.result);
      if(Array.isArray(data.ledger)){ ledger = data.ledger; persistLedger(); }
      if(data.rates){ rates = data.rates; persistRates(); }
      if(Array.isArray(data.teams)){ teams = data.teams; persistTeams(); }
      if(data.auditState){ auditState = data.auditState; persistAudit(); }
      renderLedgerList(); refreshPdfSelect(); renderRateTable();
      renderTeamList(); populateTeamSelects(); refreshBaselineSelects(); renderRiskMap(); renderAudit();
      toast("Backup restored.");
    }catch(err){ toast("Could not read this backup file."); }
  };
  reader.readAsText(f);
});

function downloadBlob(content, filename, type){
  const blob = new Blob([content], {type});
  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");
  a.href = url; a.download = filename;
  document.body.appendChild(a); a.click(); document.body.removeChild(a);
  URL.revokeObjectURL(url);
}

/* =========================================================
   NAVIGATION
   ========================================================= */
function goTo(view){
  document.querySelectorAll(".view").forEach(v=>v.classList.remove("active"));
  document.getElementById("view-"+view).classList.add("active");
  document.querySelectorAll("nav.tabs button").forEach(b=>b.classList.toggle("active", b.dataset.view===view));
  window.scrollTo({top:0,behavior:"smooth"});
}
document.getElementById("tabnav").addEventListener("click", e=>{
  const btn = e.target.closest("button[data-view]");
  if(btn) goTo(btn.dataset.view);
});

/* =========================================================
   TOAST
   ========================================================= */
let toastTimer;
function toast(msg){
  const el = document.getElementById("toast");
  el.textContent = msg;
  el.classList.add("show");
  clearTimeout(toastTimer);
  toastTimer = setTimeout(()=>el.classList.remove("show"), 2600);
}

/* =========================================================
   INIT
   ========================================================= */
function init(){
  populateIndustrySelect();
  populateCurrencySelects();
  populateTeamSelects();
  renderBenchmarkTable();
  renderRateTable();
  renderLedgerList();
  renderTeamList();
  refreshPdfSelect();
  refreshBaselineSelects();
  renderRiskMap();
  renderAudit();
  document.getElementById("heroSeal").innerHTML = sealSVG("AA", 82.4, 220);
}
init();
</script>
</body>
</html>
