<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width,initial-scale=1.0"/>
<title>CFO Pack – Finance Intelligence Platform</title>
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#070D18;--surf:#0C1420;--card:#101B2B;--bdr:#1C2E45;--bdrL:#172540;
  --txt:#E6EDF6;--mut:#607898;--dim:#2E4260;
  --acc:#00C8F0;--accD:rgba(0,200,240,.09);--accG:rgba(0,200,240,.18);
  --grn:#00DFA0;--red:#FF4060;--amb:#FFB020;--pur:#9B7FFF;--pink:#FF6EB0;
  --grid:rgba(28,46,69,.5);
}
html{scroll-behavior:smooth}
body{background:var(--bg);color:var(--txt);font-family:system-ui,-apple-system,'Segoe UI',sans-serif;min-height:100vh;overflow-x:hidden}
::-webkit-scrollbar{width:4px}::-webkit-scrollbar-track{background:var(--surf)}::-webkit-scrollbar-thumb{background:var(--bdr);border-radius:2px}
@keyframes fadeUp{from{opacity:0;transform:translateY(14px)}to{opacity:1;transform:translateY(0)}}
@keyframes spin{to{transform:rotate(360deg)}}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.2}}
.fu{animation:fadeUp .45s ease both}.fu1{animation:fadeUp .45s .08s ease both}
.fu2{animation:fadeUp .45s .16s ease both}.fu3{animation:fadeUp .45s .24s ease both}

/* Layout */
.page{display:none;padding-top:62px;min-height:100vh}
.page.active{display:block}
.wrap{max-width:1100px;margin:0 auto;padding:0 22px}
.grid-bg{background-image:linear-gradient(var(--grid) 1px,transparent 1px),linear-gradient(90deg,var(--grid) 1px,transparent 1px);background-size:44px 44px}
.card{background:var(--card);border:1px solid var(--bdr);border-radius:12px}
.g2{display:grid;grid-template-columns:1fr 1fr;gap:18px}
.g3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:16px}
.g4{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
.g5{display:grid;grid-template-columns:repeat(5,1fr);gap:13px}
@media(max-width:800px){.g2,.g3,.g4,.g5{grid-template-columns:1fr!important}.hm{display:none!important}}

/* Nav */
nav{position:fixed;top:0;left:0;right:0;z-index:300;height:62px;background:rgba(7,13,24,.96);backdrop-filter:blur(20px);border-bottom:1px solid var(--bdr)}
.ni{max-width:1100px;margin:0 auto;padding:0 22px;height:100%;display:flex;align-items:center;justify-content:space-between}
.logo{display:flex;align-items:center;gap:9px;cursor:pointer;user-select:none}
.li{width:28px;height:28px;background:var(--acc);border-radius:7px;display:flex;align-items:center;justify-content:center;flex-shrink:0}
.lt{font-weight:700;font-size:15px;letter-spacing:-.02em}
.lt em{color:var(--acc);font-style:normal}
.nr{display:flex;align-items:center;gap:18px}
.nl{background:none;border:none;color:var(--mut);font-size:13px;font-weight:500;cursor:pointer;padding:0;transition:color .2s;font-family:inherit}
.nl:hover{color:var(--txt)}

/* Buttons */
.btn{display:inline-flex;align-items:center;justify-content:center;gap:7px;border:none;cursor:pointer;font-family:inherit;font-weight:600;transition:all .2s;letter-spacing:.01em;white-space:nowrap}
.bp{background:linear-gradient(135deg,var(--acc),#0088aa);color:#000}
.bp:hover{transform:translateY(-1px);box-shadow:0 8px 24px rgba(0,200,240,.35)}
.bg{background:transparent;color:var(--mut);border:1px solid var(--bdr)}
.bg:hover{border-color:var(--acc);color:var(--acc)}
.bpur{background:linear-gradient(135deg,var(--pur),#6040CC);color:#fff}
.bpur:hover{transform:translateY(-1px);box-shadow:0 8px 24px rgba(155,127,255,.35)}
.bs{padding:7px 15px;border-radius:8px;font-size:13px}
.bm{padding:10px 22px;border-radius:9px;font-size:14px}
.bl{padding:13px 28px;border-radius:10px;font-size:15px}
.bw{width:100%}

/* Tags */
.tag{display:inline-flex;align-items:center;gap:5px;padding:3px 9px;border-radius:20px;font-size:10px;font-weight:700;letter-spacing:.06em;text-transform:uppercase}
.ta{background:var(--accD);color:var(--acc);border:1px solid rgba(0,200,240,.22)}
.tg{background:rgba(0,223,160,.1);color:var(--grn);border:1px solid rgba(0,223,160,.3)}
.tr{background:rgba(255,64,96,.1);color:var(--red);border:1px solid rgba(255,64,96,.3)}
.tam{background:rgba(255,176,32,.1);color:var(--amb);border:1px solid rgba(255,176,32,.3)}
.tpur{background:rgba(155,127,255,.1);color:var(--pur);border:1px solid rgba(155,127,255,.3)}

/* Form */
.inp{width:100%;background:var(--surf);border:1px solid var(--bdr);border-radius:8px;padding:10px 13px;color:var(--txt);font-size:14px;outline:none;font-family:inherit;transition:border-color .2s}
.inp:focus{border-color:var(--acc)}.inp::placeholder{color:var(--dim)}

/* Upload */
.uz{border:2px dashed var(--bdr);border-radius:11px;padding:28px 18px;text-align:center;cursor:pointer;transition:all .25s}
.uz:hover,.uz.drag{border-color:var(--acc);background:var(--accD)}
input[type=file]{display:none}

/* KPI */
.kc{padding:19px 17px}
.kl{font-size:10px;color:var(--mut);text-transform:uppercase;letter-spacing:.08em;margin-bottom:7px}
.kv{font-size:21px;font-weight:700;font-variant-numeric:tabular-nums;margin-bottom:3px}
.ks{font-size:12px;color:var(--mut)}

/* Table */
table{width:100%;border-collapse:collapse}
th{color:var(--mut);font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.07em;padding:9px 13px;text-align:left;border-bottom:1px solid var(--bdr);white-space:nowrap}
td{padding:9px 13px;font-size:13px;border-bottom:1px solid var(--bdrL)}
tr:last-child td{border-bottom:none}
tr:hover td{background:rgba(255,255,255,.012)}
.rr{text-align:right}

/* Progress bar */
.pbar{height:5px;border-radius:3px;background:var(--bdr);overflow:hidden;margin-top:5px}
.pfill{height:100%;border-radius:3px;transition:width .6s ease}

/* Tab bar */
.tab-bar{display:flex;border-bottom:1px solid var(--bdr);margin-bottom:20px;overflow-x:auto}
.tab{padding:9px 18px;font-size:13px;font-weight:600;cursor:pointer;border:none;background:transparent;color:var(--mut);font-family:inherit;border-bottom:2px solid transparent;transition:all .2s;white-space:nowrap}
.tab.on-b{color:var(--acc);border-bottom-color:var(--acc)}
.tab.on-v{color:var(--pur);border-bottom-color:var(--pur)}

/* Insight cards */
.ins{padding:11px 13px;border-radius:9px;margin-bottom:9px}

/* Section label */
.slbl{font-size:10px;font-weight:700;text-transform:uppercase;letter-spacing:.09em;color:var(--mut);margin-bottom:11px}

/* Chat panel */
#chatPan{position:fixed;bottom:20px;right:20px;width:360px;max-height:66vh;z-index:400;background:var(--card);border:1px solid var(--acc);border-radius:13px;box-shadow:0 20px 60px rgba(0,0,0,.65);display:none;flex-direction:column;overflow:hidden}
#chatMsgs{overflow-y:auto;padding:13px;display:flex;flex-direction:column;gap:9px;max-height:300px;min-height:120px}
.bu{max-width:85%;padding:10px 13px;font-size:13px;line-height:1.55}
.bu-u{background:var(--acc);color:#000;border-radius:12px 12px 2px 12px;align-self:flex-end}
.bu-a{background:var(--surf);color:var(--txt);border:1px solid var(--bdr);border-radius:12px 12px 12px 2px;align-self:flex-start}

/* Toast */
#toasts{position:fixed;bottom:20px;left:20px;z-index:9999;display:flex;flex-direction:column;gap:7px;pointer-events:none}

/* Misc */
.oh{overflow:hidden}.ox{overflow-x:auto}
.flex{display:flex}.aic{align-items:center}.jcb{justify-content:space-between}.jcc{justify-content:center}.fw{flex-wrap:wrap}.fdc{flex-direction:column}
.gap6{gap:6px}.gap8{gap:8px}.gap10{gap:10px}.gap12{gap:12px}.gap14{gap:14px}
.s0{flex-shrink:0}
.mono{font-variant-numeric:tabular-nums}
.lh{line-height:1.65}
.fs11{font-size:11px}.fs12{font-size:12px}.fs13{font-size:13px}.fs14{font-size:14px}
.fw5{font-weight:500}.fw6{font-weight:600}.fw7{font-weight:700}
.tc{text-align:center}
.mb8{margin-bottom:8px}.mb12{margin-bottom:12px}.mb16{margin-bottom:16px}.mb20{margin-bottom:20px}.mb24{margin-bottom:24px}
.mt8{margin-top:8px}.mt12{margin-top:12px}
.p16{padding:16px}.p20{padding:20px}.p22{padding:22px}.p24{padding:24px}
.r8{border-radius:8px}.r10{border-radius:10px}.r12{border-radius:12px}
.text-grn{color:var(--grn)}.text-red{color:var(--red)}.text-amb{color:var(--amb)}.text-acc{color:var(--acc)}.text-mut{color:var(--mut)}.text-pur{color:var(--pur)}
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="ni">
    <div class="logo" onclick="go('home')">
      <div class="li">
        <svg width="15" height="15" viewBox="0 0 16 16" fill="none">
          <path d="M2 12L5.5 6L9 10L11.5 7" stroke="#000" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"/>
          <circle cx="11.5" cy="7" r="1.2" fill="#000"/>
        </svg>
      </div>
      <span class="lt">CFO<em>Pack</em></span>
    </div>
    <div class="nr">
      <button class="nl hm" onclick="go('home')">Home</button>
      <button class="nl hm" id="nFPA" style="display:none" onclick="go('fpa-upload')">FP&amp;A</button>
      <button class="nl hm" id="nFIN" style="display:none" onclick="go('fin-upload')">Analysis</button>
      <button class="btn bg bs" id="nBack" style="display:none" onclick="goBack()">← Back</button>
      <button class="btn bp bs" id="nFPAbtn" onclick="go('fpa-upload')">+ FP&amp;A Report</button>
      <button class="btn bpur bs" id="nFINbtn" onclick="go('fin-upload')">+ Analysis</button>
    </div>
  </div>
</nav>

<div id="toasts"></div>

<!-- ═══════════════════════════════════════════════════════ -->
<!-- HOME                                                    -->
<!-- ═══════════════════════════════════════════════════════ -->
<div id="pg-home" class="page active">
  <div class="grid-bg" style="position:relative;min-height:86vh;display:flex;align-items:center;justify-content:center;text-align:center;overflow:hidden">
    <div style="position:absolute;inset:0;background:radial-gradient(ellipse 80% 55% at 50% 0%,rgba(0,200,240,.08),transparent 70%)"></div>
    <div class="fu" style="position:relative;max-width:780px;padding:0 22px">
      <span class="tag ta mb16" style="display:inline-flex;margin-bottom:24px">✦ Finance Intelligence Platform</span>
      <h1 style="font-size:clamp(34px,6.5vw,72px);line-height:1.06;letter-spacing:-.03em;margin-bottom:18px;font-weight:700">
        Your Complete<br><span style="color:var(--acc)">Finance Intelligence</span><br>Platform
      </h1>
      <p style="font-size:clamp(14px,2vw,18px);color:var(--mut);line-height:1.65;max-width:540px;margin:0 auto 36px">
        Two powerful modules. Upload your data and get boardroom-ready insights, smart commentary, charts and actionable recommendations — in minutes.
      </p>
      <!-- Module Cards -->
      <div class="g2" style="max-width:660px;margin:0 auto 32px;text-align:left">
        <div class="card p24 fu" style="cursor:pointer;transition:all .3s;border-color:var(--bdr)" onclick="go('fpa-upload')"
          onmouseenter="this.style.borderColor='var(--acc)';this.style.transform='translateY(-3px)'"
          onmouseleave="this.style.borderColor='var(--bdr)';this.style.transform=''">
          <div style="width:44px;height:44px;border-radius:11px;background:var(--accD);border:1px solid rgba(0,200,240,.2);display:flex;align-items:center;justify-content:center;margin-bottom:14px">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="var(--acc)" stroke-width="2"><rect x="2" y="3" width="20" height="14" rx="2"/><line x1="8" y1="21" x2="16" y2="21"/><line x1="12" y1="17" x2="12" y2="21"/></svg>
          </div>
          <div class="fw7 fs14 mb8">FP&amp;A Suite</div>
          <p class="text-mut fs13 lh mb12">Budget vs Actuals analysis, variance engine, CFO commentary, board packs.</p>
          <div class="flex fw gap6">
            <span class="tag ta" style="font-size:9px">Variance</span>
            <span class="tag ta" style="font-size:9px">Commentary</span>
            <span class="tag ta" style="font-size:9px">Board Pack</span>
          </div>
        </div>
        <div class="card p24 fu1" style="cursor:pointer;transition:all .3s;border-color:var(--bdr)" onclick="go('fin-upload')"
          onmouseenter="this.style.borderColor='var(--pur)';this.style.transform='translateY(-3px)'"
          onmouseleave="this.style.borderColor='var(--bdr)';this.style.transform=''">
          <div style="width:44px;height:44px;border-radius:11px;background:rgba(155,127,255,.1);border:1px solid rgba(155,127,255,.2);display:flex;align-items:center;justify-content:center;margin-bottom:14px">
            <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="var(--pur)" stroke-width="2"><polyline points="22 7 13.5 15.5 8.5 10.5 2 17"/><polyline points="16 7 22 7 22 13"/></svg>
          </div>
          <div class="fw7 fs14 mb8">Financial Analysis</div>
          <p class="text-mut fs13 lh mb12">Trend analysis, margin diagnostics, cost structure, anomaly detection — no budget needed.</p>
          <div class="flex fw gap6">
            <span class="tag tpur" style="font-size:9px">Trends</span>
            <span class="tag tpur" style="font-size:9px">Margins</span>
            <span class="tag tpur" style="font-size:9px">Anomalies</span>
          </div>
        </div>
      </div>
      <div class="flex jcc gap12 fw">
        <button class="btn bp bl" onclick="go('fpa-upload')">Try FP&amp;A Demo</button>
        <button class="btn bpur bl" onclick="go('fin-upload')">Try Analysis Demo</button>
      </div>
    </div>
  </div>

  <!-- Features -->
  <div class="wrap" style="padding-top:64px;padding-bottom:80px">
    <div class="tc mb24" style="margin-bottom:44px">
      <h2 style="font-size:clamp(22px,3.5vw,38px);font-weight:700;margin-bottom:12px">Two modules, one platform</h2>
      <p class="text-mut fs14">Whether you have a budget or just actuals — we have you covered.</p>
    </div>
    <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:16px">
      <div class="card p22 fu" style="transition:all .3s" onmouseenter="this.style.borderColor='var(--acc)'" onmouseleave="this.style.borderColor='var(--bdr)'">
        <div style="font-size:22px;margin-bottom:12px">📊</div>
        <div class="fw6 fs14 mb8">Variance Analysis</div>
        <p class="text-mut fs13 lh">Budget vs Actuals with absolute &amp; % variances, favorable/unfavorable flags and period summaries.</p>
      </div>
      <div class="card p22 fu1" style="transition:all .3s" onmouseenter="this.style.borderColor='var(--pur)'" onmouseleave="this.style.borderColor='var(--bdr)'">
        <div style="font-size:22px;margin-bottom:12px">📈</div>
        <div class="fw6 fs14 mb8">Trend Analysis</div>
        <p class="text-mut fs13 lh">Multi-period revenue, cost and profit trends with period-over-period growth rate calculations.</p>
      </div>
      <div class="card p22 fu2" style="transition:all .3s" onmouseenter="this.style.borderColor='var(--pur)'" onmouseleave="this.style.borderColor='var(--bdr)'">
        <div style="font-size:22px;margin-bottom:12px">🔍</div>
        <div class="fw6 fs14 mb8">Margin Diagnostics</div>
        <p class="text-mut fs13 lh">Identifies exactly what's compressing your gross, operating and net margins with specific numbers.</p>
      </div>
      <div class="card p22 fu" style="transition:all .3s" onmouseenter="this.style.borderColor='var(--pur)'" onmouseleave="this.style.borderColor='var(--bdr)'">
        <div style="font-size:22px;margin-bottom:12px">💸</div>
        <div class="fw6 fs14 mb8">Cost Structure</div>
        <p class="text-mut fs13 lh">See exactly what percentage of revenue each cost line is consuming, ranked by impact.</p>
      </div>
      <div class="card p22 fu1" style="transition:all .3s" onmouseenter="this.style.borderColor='var(--red)'" onmouseleave="this.style.borderColor='var(--bdr)'">
        <div style="font-size:22px;margin-bottom:12px">⚡</div>
        <div class="fw6 fs14 mb8">Anomaly Detection</div>
        <p class="text-mut fs13 lh">Automatically flags unusual spikes, drops and outliers across all line items and periods.</p>
      </div>
      <div class="card p22 fu2" style="transition:all .3s" onmouseenter="this.style.borderColor='var(--acc)'" onmouseleave="this.style.borderColor='var(--bdr)'">
        <div style="font-size:22px;margin-bottom:12px">💬</div>
        <div class="fw6 fs14 mb8">Smart Analyst Chat</div>
        <p class="text-mut fs13 lh">Ask plain-language questions about your data and get CFO-quality answers instantly.</p>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════ -->
<!-- FP&A UPLOAD                                            -->
<!-- ═══════════════════════════════════════════════════════ -->
<div id="pg-fpa-upload" class="page">
  <div class="wrap" style="max-width:660px;padding-top:34px;padding-bottom:60px">
    <div class="tc mb24 fu">
      <span class="tag ta" style="display:inline-flex;margin-bottom:12px">FP&amp;A Suite</span>
      <h1 style="font-size:30px;font-weight:700;margin-bottom:8px;margin-top:10px">Upload Financials</h1>
      <p class="text-mut fs14">Budget &amp; Actuals files — we handle the rest.</p>
    </div>
    <div id="fpaForm">
      <div class="g2 mb14">
        <div class="uz" id="zB" onclick="document.getElementById('fB').click()" ondragover="dd(event,'B')" ondragleave="dl('B')" ondrop="dp(event,'B')">
          <input type="file" id="fB" accept=".csv,.txt" onchange="sf(event,'B')">
          <div id="zBc">
            <div style="width:38px;height:38px;border-radius:9px;background:var(--accD);border:1px solid rgba(0,200,240,.2);display:flex;align-items:center;justify-content:center;margin:0 auto 10px">
              <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="var(--acc)" stroke-width="2"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
            </div>
            <div class="fw6 fs13 mb4">Budget File</div>
            <div class="text-mut fs12">Drag &amp; drop or click</div>
            <div class="fs11 text-mut mt8">.csv or .txt</div>
          </div>
        </div>
        <div class="uz" id="zA" onclick="document.getElementById('fA').click()" ondragover="dd(event,'A')" ondragleave="dl('A')" ondrop="dp(event,'A')">
          <input type="file" id="fA" accept=".csv,.txt" onchange="sf(event,'A')">
          <div id="zAc">
            <div style="width:38px;height:38px;border-radius:9px;background:var(--accD);border:1px solid rgba(0,200,240,.2);display:flex;align-items:center;justify-content:center;margin:0 auto 10px">
              <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="var(--acc)" stroke-width="2"><line x1="18" y1="20" x2="18" y2="10"/><line x1="12" y1="20" x2="12" y2="4"/><line x1="6" y1="20" x2="6" y2="14"/></svg>
            </div>
            <div class="fw6 fs13 mb4">Actuals File</div>
            <div class="text-mut fs12">Drag &amp; drop or click</div>
            <div class="fs11 text-mut mt8">.csv or .txt</div>
          </div>
        </div>
      </div>
      <div class="card flex aic gap12 p16 mb12" style="cursor:pointer" onclick="toggleDemoChk('fpa')">
        <div id="fpaChk" style="width:17px;height:17px;border-radius:4px;border:2px solid var(--bdr);flex-shrink:0;display:flex;align-items:center;justify-content:center;transition:all .2s"></div>
        <div><div class="fw6 fs13">Use sample demo data</div><div class="text-mut fs12">Pre-loaded 3-month P&amp;L — no upload needed</div></div>
      </div>
      <div class="card flex gap12 p14 mb20" style="align-items:flex-start">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="var(--amb)" stroke-width="2" style="flex-shrink:0;margin-top:2px"><path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"/><line x1="12" y1="9" x2="12" y2="13"/><line x1="12" y1="17" x2="12.01" y2="17"/></svg>
        <div><div class="fw6 text-amb fs12 mb4">Expected columns</div><div class="mono text-mut fs11">Department | Account | Budget | Actual | Month</div></div>
      </div>
      <button class="btn bp bl bw" onclick="startFPA()">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="#000"><path d="M12 2L9.19 9.19L2 12l7.19 2.81L12 22l2.81-7.19L22 12l-7.19-2.81Z"/></svg>
        Generate FP&amp;A Report
      </button>
    </div>
    <div id="fpaProc" style="display:none">
      <div class="card p22 tc" style="padding:50px 30px">
        <div style="width:54px;height:54px;border:2px solid var(--bdr);border-top-color:var(--acc);border-radius:50%;animation:spin .8s linear infinite;margin:0 auto 20px"></div>
        <div class="fw6 fs14 mb8" id="fpaSt">Processing…</div>
        <div class="text-mut fs13" id="fpaDsc">Please wait</div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════ -->
<!-- FINANCIAL ANALYSIS UPLOAD                              -->
<!-- ═══════════════════════════════════════════════════════ -->
<div id="pg-fin-upload" class="page">
  <div class="wrap" style="max-width:660px;padding-top:34px;padding-bottom:60px">
    <div class="tc mb24 fu">
      <span class="tag tpur" style="display:inline-flex;margin-bottom:12px">Financial Analysis</span>
      <h1 style="font-size:30px;font-weight:700;margin-bottom:8px;margin-top:10px">Upload Your Financials</h1>
      <p class="text-mut fs14">Just your actuals — no budget needed. Trends, margins, costs &amp; anomalies.</p>
    </div>
    <div id="finForm">
      <!-- Analysis type -->
      <div class="card p20 mb14">
        <div class="slbl mb12">What do you want to analyse?</div>
        <div class="flex fw gap8">
          <button class="btn bp bs" id="at-all" onclick="setAt('all')" style="font-size:12px">All Insights</button>
          <button class="btn bg bs" id="at-trend" onclick="setAt('trend')" style="font-size:12px">📈 Trends</button>
          <button class="btn bg bs" id="at-margin" onclick="setAt('margin')" style="font-size:12px">🔍 Margins</button>
          <button class="btn bg bs" id="at-cost" onclick="setAt('cost')" style="font-size:12px">💸 Costs</button>
        </div>
      </div>
      <!-- Single upload zone -->
      <div class="uz mb14" id="zF" onclick="document.getElementById('fF').click()" ondragover="dd(event,'F')" ondragleave="dl('F')" ondrop="dp(event,'F')">
        <input type="file" id="fF" accept=".csv,.txt" onchange="sf(event,'F')">
        <div id="zFc">
          <div style="width:44px;height:44px;border-radius:11px;background:rgba(155,127,255,.1);border:1px solid rgba(155,127,255,.2);display:flex;align-items:center;justify-content:center;margin:0 auto 12px">
            <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="var(--pur)" stroke-width="2"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="17 8 12 3 7 8"/><line x1="12" y1="3" x2="12" y2="15"/></svg>
          </div>
          <div class="fw6 fs14 mb6">Upload Financial Data</div>
          <div class="text-mut fs13">Drag &amp; drop or click to browse</div>
          <div class="fs11 text-mut mt8">P&amp;L, income statement, trial balance, ledger, bank statement, any CSV</div>
        </div>
      </div>
      <div class="card flex aic gap12 p16 mb12" style="cursor:pointer" onclick="toggleDemoChk('fin')">
        <div id="finChk" style="width:17px;height:17px;border-radius:4px;border:2px solid var(--bdr);flex-shrink:0;display:flex;align-items:center;justify-content:center;transition:all .2s"></div>
        <div><div class="fw6 fs13">Use sample demo data</div><div class="text-mut fs12">6-month P&amp;L with multiple cost lines — no upload needed</div></div>
      </div>
      <div class="card p14 mb20" style="background:rgba(155,127,255,.05);border-color:rgba(155,127,255,.2)">
        <div class="fw6 text-pur fs12 mb6">Flexible column format — use any of these:</div>
        <div class="mono text-mut fs11 lh" style="line-height:1.8">
          Option A: <strong style="color:var(--txt)">Account | Jan | Feb | Mar…</strong> (wide format)<br>
          Option B: <strong style="color:var(--txt)">Account | Month | Amount | Category</strong> (long format)<br>
          Option C: <strong style="color:var(--txt)">Account Name | Debit | Credit</strong> (trial balance / ledger)
        </div>
      </div>
      <button class="btn bpur bl bw" onclick="startFIN()">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="#fff" stroke="none"><path d="M12 2L9.19 9.19L2 12l7.19 2.81L12 22l2.81-7.19L22 12l-7.19-2.81Z"/></svg>
        Run Financial Analysis
      </button>
    </div>
    <div id="finProc" style="display:none">
      <div class="card p22 tc" style="padding:50px 30px">
        <div style="width:54px;height:54px;border:2px solid var(--bdr);border-top-color:var(--pur);border-radius:50%;animation:spin .8s linear infinite;margin:0 auto 20px"></div>
        <div class="fw6 fs14 mb8" id="finSt">Analysing…</div>
        <div class="text-mut fs13" id="finDsc">Please wait</div>
      </div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════ -->
<!-- FP&A REPORT                                            -->
<!-- ═══════════════════════════════════════════════════════ -->
<div id="pg-fpa-report" class="page">
  <div class="wrap" style="padding-top:34px;padding-bottom:120px">
    <div class="flex aic jcb fw gap14 mb24 fu">
      <div>
        <div id="fRtag" class="mb12"></div>
        <h1 id="fRH" style="font-size:clamp(20px,3vw,34px);font-weight:700;line-height:1.1;margin-bottom:7px"></h1>
        <p id="fRM" class="text-mut fs13"></p>
      </div>
      <div class="flex gap10 fw">
        <button class="btn bg bs" onclick="toast('PDF export available in production build','info')">⬇ PDF</button>
        <button class="btn bg bs" onclick="toast('PPT export available in production build','info')">📊 PPT</button>
        <button class="btn bp bs" onclick="openChat('fpa')">💬 Smart Analyst</button>
      </div>
    </div>
    <div class="g4 mb20 fu1" id="fRKPIs"></div>
    <div class="card mb20 fu1" style="padding:22px;border-left:3px solid var(--acc)">
      <div class="flex aic gap8 mb10">
        <span class="text-acc fw6 fs11" style="text-transform:uppercase;letter-spacing:.09em">📋 Executive Summary</span>
      </div>
      <p id="fRExec" style="line-height:1.75;font-size:15px"></p>
    </div>
    <div class="g2 mb20 fu2">
      <div class="card p20"><div class="slbl">Revenue — Actual vs Budget</div><div id="fChRev"></div></div>
      <div class="card p20"><div class="slbl">EBITDA — Actual vs Budget</div><div id="fChEB"></div></div>
    </div>
    <div class="card p20 mb20 fu2">
      <div class="slbl">Expense Breakdown (Actual)</div>
      <div class="g2">
        <div id="fChExp"></div>
        <div id="fExpLeg" class="flex fdc jcc gap10 fs12 text-mut"></div>
      </div>
    </div>
    <div class="g2 mb20 fu3">
      <div class="card p22"><div class="slbl">Key Business Drivers</div><div id="fRDrv" class="flex fdc gap10"></div></div>
      <div class="card p22"><div class="slbl">Cost Analysis</div><p id="fRCost" class="fs13 lh mb16"></p><div class="slbl mt12">Cash Flow</div><p id="fRCash" class="fs13 lh"></p></div>
    </div>
    <div class="g2 mb20 fu3">
      <div class="card p22"><div class="slbl text-red">⚠ Risks</div><div id="fRRisks" class="flex fdc gap8"></div></div>
      <div class="card p22"><div class="slbl text-grn">◆ Opportunities</div><div id="fROpps" class="flex fdc gap8"></div></div>
    </div>
    <div class="card p22 mb20 fu3"><div class="slbl">Recommendations</div><div id="fRRecs" style="display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:10px"></div></div>
    <div class="card oh fu3">
      <div class="p16" style="border-bottom:1px solid var(--bdr)"><span class="fw6 fs14">Variance Table</span></div>
      <div class="ox"><table><thead><tr><th>Dept</th><th>Account</th><th>Month</th><th class="rr">Budget</th><th class="rr">Actual</th><th class="rr">Variance</th><th class="rr">Var%</th><th>Status</th></tr></thead><tbody id="fRTb"></tbody></table></div>
    </div>
  </div>
</div>

<!-- ═══════════════════════════════════════════════════════ -->
<!-- FINANCIAL ANALYSIS REPORT                              -->
<!-- ═══════════════════════════════════════════════════════ -->
<div id="pg-fin-report" class="page">
  <div class="wrap" style="padding-top:34px;padding-bottom:120px">
    <div class="flex aic jcb fw gap14 mb24 fu">
      <div>
        <span class="tag tpur mb12" style="display:inline-block">Financial Analysis</span>
        <h1 id="finRH" style="font-size:clamp(20px,3vw,34px);font-weight:700;line-height:1.1;margin-bottom:7px;margin-top:8px"></h1>
        <p id="finRM" class="text-mut fs13"></p>
      </div>
      <div class="flex gap10 fw">
        <button class="btn bg bs" onclick="toast('PDF export available in production build','info')">⬇ PDF</button>
        <button class="btn bpur bs" onclick="openChat('fin')">💬 Smart Analyst</button>
      </div>
    </div>

    <!-- KPIs -->
    <div class="g4 mb20 fu1" id="finKPIs"></div>

    <!-- Diagnostic Banner -->
    <div class="card mb20 fu1" style="padding:22px;border-left:3px solid var(--pur);background:rgba(155,127,255,.05)">
      <div class="flex aic gap8 mb10">
        <span class="text-pur fw6 fs11" style="text-transform:uppercase;letter-spacing:.09em">🔍 Financial Diagnostic</span>
      </div>
      <p id="finDiag" style="line-height:1.75;font-size:15px"></p>
    </div>

    <!-- Tab bar -->
    <div class="tab-bar" id="finTabBar"></div>
    <div id="finTabContent"></div>
  </div>
</div>

<!-- CHAT PANEL -->
<div id="chatPan">
  <div class="flex aic jcb" style="padding:12px 16px;background:var(--surf);border-bottom:1px solid var(--bdr)">
    <div class="flex aic gap8">
      <span class="fw6 fs13">💬 Smart Analyst</span>
      <div style="width:6px;height:6px;border-radius:50%;background:var(--grn);animation:pulse 2s infinite"></div>
    </div>
    <button onclick="closeChat()" style="background:none;border:none;cursor:pointer;color:var(--mut);font-size:17px;line-height:1">×</button>
  </div>
  <div id="chatMsgs">
    <div class="bu bu-a">Hello! I'm your financial analyst. Ask me anything about this report — variances, drivers, recommendations or what the numbers mean.</div>
  </div>
  <div class="flex gap8" style="padding:9px;border-top:1px solid var(--bdr)">
    <input class="inp" id="chatIn" placeholder="Ask about your financials…" style="font-size:13px;padding:8px 11px" onkeydown="if(event.key==='Enter')sendChat()">
    <button class="btn bp bs s0" onclick="sendChat()" style="padding:8px 12px">
      <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="#000" stroke-width="2"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2" fill="#000"/></svg>
    </button>
  </div>
</div>

<button id="chatFab" onclick="openChatFab()" style="display:none;position:fixed;bottom:20px;right:20px;padding:11px 18px;border-radius:28px;font-size:13px;font-weight:600;border:none;cursor:pointer;box-shadow:0 8px 28px rgba(0,200,240,.32);z-index:200;font-family:inherit;gap:7px;align-items:center">💬 Smart Analyst</button>

<script>
// ════════════════════════════════════════
// STATE & HELPERS
// ════════════════════════════════════════
const S={fpaReport:null,finReport:null,bFile:null,aFile:null,finFile:null,fpaDemoOn:false,finDemoOn:false,analysisType:'all',chatHist:[],chatMode:'fpa',currentPage:'home'};
const PAL=['#00C8F0','#9B7FFF','#FFB020','#00DFA0','#FF4060','#FF6EB0','#60D0FF','#C0A0FF'];
const fK=n=>{const s=n<0?'-':'',a=Math.abs(n);if(a>=1e6)return s+'$'+(a/1e6).toFixed(1)+'M';if(a>=1e3)return s+'$'+Math.round(a/1e3)+'K';return s+'$'+Math.round(a)};
const fP=n=>(n>=0?'+':'')+n.toFixed(1)+'%';
const fX=n=>n.toFixed(1)+'%';
const clr=(v,inv=false)=>v>=0?(inv?'var(--red)':'var(--grn)'):(inv?'var(--grn)':'var(--red)');
const g=id=>document.getElementById(id);
const esc=s=>String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');

// ════════════════════════════════════════
// NAVIGATION
// ════════════════════════════════════════
function go(pg){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  g('pg-'+pg).classList.add('active');
  S.currentPage=pg;
  window.scrollTo(0,0);
  updNav();
  const showChat=pg==='fpa-report'||pg==='fin-report';
  g('chatFab').style.display=showChat?'flex':'none';
  if(!showChat){g('chatPan').style.display='none';}
  if(pg==='fin-report')renderFinTabs();
}
function updNav(){
  const pg=S.currentPage;
  const isReport=pg==='fpa-report'||pg==='fin-report';
  const isUpload=pg==='fpa-upload'||pg==='fin-upload';
  g('nBack').style.display=(isReport||isUpload)?'':'none';
  g('nFPA').style.display='';g('nFIN').style.display='';
}
function goBack(){
  const pg=S.currentPage;
  if(pg==='fpa-report')go('fpa-upload');
  else if(pg==='fin-report')go('fin-upload');
  else go('home');
}

// ════════════════════════════════════════
// DEMO DATA
// ════════════════════════════════════════
const FPA_DEMO=[
  {Department:'Revenue',Account:'Product Sales',Budget:420000,Actual:387000,Month:'Jan'},
  {Department:'Revenue',Account:'Services',Budget:180000,Actual:203000,Month:'Jan'},
  {Department:'Revenue',Account:'Licensing',Budget:90000,Actual:78000,Month:'Jan'},
  {Department:'COGS',Account:'Direct Labor',Budget:95000,Actual:102000,Month:'Jan'},
  {Department:'COGS',Account:'Materials',Budget:62000,Actual:58000,Month:'Jan'},
  {Department:'OpEx',Account:'R&D',Budget:85000,Actual:91000,Month:'Jan'},
  {Department:'OpEx',Account:'Sales & Mktg',Budget:74000,Actual:69000,Month:'Jan'},
  {Department:'OpEx',Account:'G&A',Budget:48000,Actual:52000,Month:'Jan'},
  {Department:'Revenue',Account:'Product Sales',Budget:445000,Actual:421000,Month:'Feb'},
  {Department:'Revenue',Account:'Services',Budget:195000,Actual:218000,Month:'Feb'},
  {Department:'Revenue',Account:'Licensing',Budget:95000,Actual:88000,Month:'Feb'},
  {Department:'COGS',Account:'Direct Labor',Budget:98000,Actual:105000,Month:'Feb'},
  {Department:'COGS',Account:'Materials',Budget:65000,Actual:61000,Month:'Feb'},
  {Department:'OpEx',Account:'R&D',Budget:88000,Actual:94000,Month:'Feb'},
  {Department:'OpEx',Account:'Sales & Mktg',Budget:78000,Actual:72000,Month:'Feb'},
  {Department:'OpEx',Account:'G&A',Budget:50000,Actual:55000,Month:'Feb'},
  {Department:'Revenue',Account:'Product Sales',Budget:470000,Actual:498000,Month:'Mar'},
  {Department:'Revenue',Account:'Services',Budget:210000,Actual:235000,Month:'Mar'},
  {Department:'Revenue',Account:'Licensing',Budget:100000,Actual:94000,Month:'Mar'},
  {Department:'COGS',Account:'Direct Labor',Budget:102000,Actual:108000,Month:'Mar'},
  {Department:'COGS',Account:'Materials',Budget:68000,Actual:63000,Month:'Mar'},
  {Department:'OpEx',Account:'R&D',Budget:92000,Actual:97000,Month:'Mar'},
  {Department:'OpEx',Account:'Sales & Mktg',Budget:82000,Actual:75000,Month:'Mar'},
  {Department:'OpEx',Account:'G&A',Budget:52000,Actual:58000,Month:'Mar'},
];

const FIN_DEMO=[
  {Account:'Product Revenue',Category:'Revenue',Jan:387000,Feb:421000,Mar:498000,Apr:510000,May:476000,Jun:532000},
  {Account:'Services Revenue',Category:'Revenue',Jan:203000,Feb:218000,Mar:235000,Apr:248000,May:261000,Jun:290000},
  {Account:'Licensing',Category:'Revenue',Jan:78000,Feb:88000,Mar:94000,Apr:96000,May:90000,Jun:102000},
  {Account:'Direct Labor',Category:'COGS',Jan:102000,Feb:105000,Mar:108000,Apr:114000,May:118000,Jun:122000},
  {Account:'Materials',Category:'COGS',Jan:58000,Feb:61000,Mar:63000,Apr:68000,May:72000,Jun:75000},
  {Account:'Hosting & Infra',Category:'COGS',Jan:24000,Feb:26000,Mar:28000,Apr:31000,May:34000,Jun:38000},
  {Account:'R&D',Category:'OpEx',Jan:91000,Feb:94000,Mar:97000,Apr:108000,May:115000,Jun:124000},
  {Account:'Sales & Marketing',Category:'OpEx',Jan:69000,Feb:72000,Mar:75000,Apr:79000,May:84000,Jun:91000},
  {Account:'G&A',Category:'OpEx',Jan:52000,Feb:55000,Mar:58000,Apr:60000,May:63000,Jun:66000},
  {Account:'Depreciation',Category:'OpEx',Jan:14000,Feb:14000,Mar:14000,Apr:14000,May:14000,Jun:14000},
];

// ════════════════════════════════════════
// FILE HANDLING
// ════════════════════════════════════════
function dd(e,t){e.preventDefault();g('z'+t).classList.add('drag');}
function dl(t){g('z'+t).classList.remove('drag');}
function dp(e,t){e.preventDefault();dl(t);const f=e.dataTransfer.files[0];if(f)sf2(t,f);}
function sf(e,t){if(e.target.files[0])sf2(t,e.target.files[0]);}
function sf2(t,f){
  if(t==='B')S.bFile=f;else if(t==='A')S.aFile=f;else S.finFile=f;
  const c=g('z'+t+'c');
  c.innerHTML=`<div style="width:38px;height:38px;border-radius:9px;background:rgba(0,223,160,.12);border:1px solid var(--grn);display:flex;align-items:center;justify-content:center;margin:0 auto 10px"><svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="var(--grn)" stroke-width="2.5"><polyline points="20 6 9 17 4 12"/></svg></div><div class="fw6 fs13 text-grn mb4">${esc(f.name)}</div><div class="text-mut fs11">${(f.size/1024).toFixed(1)} KB</div>`;
}

function updChk(t,on){
  const d=g(t+'Chk');
  if(on){d.style.background='var(--acc)';d.style.borderColor='var(--acc)';d.innerHTML='<svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="#000" stroke-width="3"><polyline points="20 6 9 17 4 12"/></svg>';}
  else{d.style.background='';d.style.borderColor='var(--bdr)';d.innerHTML='';}
}
function toggleDemoChk(t){
  if(t==='fpa'){S.fpaDemoOn=!S.fpaDemoOn;updChk('fpa',S.fpaDemoOn);}
  else{S.finDemoOn=!S.finDemoOn;updChk('fin',S.finDemoOn);}
}

let curAt='all';
function setAt(t){
  curAt=t;S.analysisType=t;
  ['all','trend','margin','cost'].forEach(k=>{const b=g('at-'+k);if(b){b.className='btn bs '+(k===t?'bp':'bg');}});
}

function parseCSV(txt){
  const lines=txt.trim().split('\n').filter(l=>l.trim());
  if(lines.length<2)return[];
  const headers=lines[0].split(/[,\t]/).map(h=>h.trim().replace(/^"|"$/g,'').replace(/\r/,''));
  return lines.slice(1).map(l=>{
    const vals=l.split(/[,\t]/).map(v=>v.trim().replace(/^"|"$/g,'').replace(/\r/,'').replace(/[$,]/g,''));
    const o={};headers.forEach((h,i)=>{const v=vals[i]||'';o[h]=v===''?null:isNaN(v)?v:+v;});
    return o;
  }).filter(r=>Object.values(r).some(v=>v!=null&&v!==''));
}
function readFile(f){
  return new Promise((res,rej)=>{const rd=new FileReader();rd.onload=e=>res(parseCSV(e.target.result));rd.onerror=rej;rd.readAsText(f);});
}

// ════════════════════════════════════════
// FP&A ENGINE
// ════════════════════════════════════════
function calcFPA(data){
  const rows=data.map(r=>{
    const v=r.Actual-r.Budget,vp=r.Budget?(v/Math.abs(r.Budget))*100:0;
    return{...r,v,vp,fav:r.Department==='Revenue'?r.Actual>=r.Budget:r.Actual<=r.Budget};
  });
  const months=[...new Set(data.map(r=>r.Month))];
  const monthly=months.map(m=>{
    const mr=rows.filter(r=>r.Month===m);
    const s=(d,k)=>mr.filter(r=>r.Department===d).reduce((a,r)=>a+r[k],0);
    const bR=s('Revenue','Budget'),aR=s('Revenue','Actual');
    const bC=s('COGS','Budget')+s('OpEx','Budget'),aC=s('COGS','Actual')+s('OpEx','Actual');
    return{Month:m,bRev:bR,aRev:aR,bEB:bR-bC,aEB:aR-aC};
  });
  const rev=rows.filter(r=>r.Department==='Revenue');
  const nr=rows.filter(r=>r.Department!=='Revenue');
  const bR=rev.reduce((s,r)=>s+r.Budget,0),aR=rev.reduce((s,r)=>s+r.Actual,0);
  const bC=nr.reduce((s,r)=>s+r.Budget,0),aC=nr.reduce((s,r)=>s+r.Actual,0);
  const expByDept={};nr.forEach(r=>{expByDept[r.Department]=(expByDept[r.Department]||0)+r.Actual;});
  return{rows,monthly,months,expByDept,kpis:{
    bRev:bR,aRev:aR,bCost:bC,aCost:aC,bEB:bR-bC,aEB:aR-aC,
    revVar:aR-bR,revVarP:((aR-bR)/bR)*100,
    expVar:aC-bC,expVarP:((aC-bC)/bC)*100,
    ebVar:(aR-aC)-(bR-bC),ebVarP:(((aR-aC)-(bR-bC))/Math.abs(bR-bC))*100,
    burn:aC/months.length
  }};
}

// ════════════════════════════════════════
// FINANCIAL ANALYSIS ENGINE
// ════════════════════════════════════════
const KW={Revenue:['revenue','sales','income','turnover','licensing','receipts'],COGS:['cost of goods','cogs','direct labor','raw material','materials','manufacturing','hosting'],OpEx:['salary','wages','rent','electricity','utilities','telephone','internet','insurance','depreciation','marketing','advertising','r&d','research','g&a','general','admin','professional','audit','legal','travel','software']};
function classifyAcct(name,cat){
  const n=(name+' '+(cat||'')).toLowerCase();
  for(const[k,ws]of Object.entries(KW)){if(ws.some(w=>n.includes(w)))return k;}
  if(['cash','bank','receivable','inventory','asset','property','equipment'].some(w=>n.includes(w)))return'Assets';
  if(['payable','loan','liability','creditor','borrowing'].some(w=>n.includes(w)))return'Liabilities';
  if(['equity','capital','retained','reserve'].some(w=>n.includes(w)))return'Equity';
  return'Other';
}

function calcFIN(raw){
  const keys=Object.keys(raw[0]);
  const MONTHS=['jan','feb','mar','apr','may','jun','jul','aug','sep','oct','nov','dec','q1','q2','q3','q4'];
  const mCols=keys.filter(k=>MONTHS.some(m=>k.toLowerCase().startsWith(m)));
  const isWide=mCols.length>=2;
  let records=[];
  if(isWide){
    raw.forEach(r=>{
      mCols.forEach(m=>{
        if(r[m]!=null)records.push({account:r.Account||r.Description||'Unknown',category:r.Category||r.Department||classifyAcct(r.Account||'',''),period:m,amount:+r[m]||0});
      });
    });
  }else{
    const hh=keys.map(k=>k.toLowerCase());
    const acol=keys[hh.findIndex(h=>h.includes('account')||h.includes('description')||h.includes('name'))||0];
    const catcol=keys[hh.findIndex(h=>h.includes('category')||h.includes('type'))];
    const amtcol=keys[hh.findIndex(h=>h.includes('amount')||h.includes('value')||h.includes('actual')||h.includes('credit'))];
    const pcol=keys[hh.findIndex(h=>h.includes('month')||h.includes('period'))];
    raw.forEach(r=>{
      const a=String(r[acol]||'Unknown');
      const cat=catcol?String(r[catcol]||classifyAcct(a,'')):classifyAcct(a,'');
      records.push({account:a,category:cat,period:pcol?String(r[pcol]||'Current'):'Current',amount:amtcol?+(r[amtcol]||0):0});
    });
    records=records.filter(r=>r.amount);
  }

  const periods=[...new Set(records.map(r=>r.period))];
  const isRev=r=>r.category==='Revenue';
  const periodData=periods.map(p=>{
    const pr=records.filter(r=>r.period===p);
    const rev=pr.filter(isRev).reduce((s,r)=>s+r.amount,0);
    const cogs=pr.filter(r=>r.category==='COGS').reduce((s,r)=>s+Math.abs(r.amount),0);
    const costs=pr.filter(r=>!isRev(r)).reduce((s,r)=>s+Math.abs(r.amount),0);
    const gross=rev-cogs,op=rev-costs;
    return{period:p,revenue:rev,costs,cogs,grossProfit:gross,operatingProfit:op,grossMargin:rev?gross/rev*100:0,opMargin:rev?op/rev*100:0};
  });

  const acctMap={};
  records.forEach(r=>{if(!acctMap[r.account])acctMap[r.account]={account:r.account,category:r.category,total:0,byPeriod:{}};acctMap[r.account].total+=r.amount;acctMap[r.account].byPeriod[r.period]=(acctMap[r.account].byPeriod[r.period]||0)+r.amount;});
  const accounts=Object.values(acctMap).sort((a,b)=>Math.abs(b.total)-Math.abs(a.total));
  const totalRev=periodData.reduce((s,p)=>s+p.revenue,0);
  const costAccounts=accounts.filter(a=>!isRev({category:a.category}));

  const anomalies=[];
  accounts.forEach(a=>{
    const vals=periods.map(p=>a.byPeriod[p]||0);
    if(vals.length<2)return;
    const prev=vals[vals.length-2],latest=vals[vals.length-1];
    const chg=prev?((latest-prev)/Math.abs(prev))*100:0;
    if(Math.abs(chg)>20)anomalies.push({account:a.account,category:a.category,change:chg,latest,prev});
  });

  const growthRows=[];
  if(periodData.length>=2){
    const last=periodData[periodData.length-1],prev=periodData[periodData.length-2];
    [['Revenue',last.revenue,prev.revenue],['Gross Profit',last.grossProfit,prev.grossProfit],['Operating Profit',last.operatingProfit,prev.operatingProfit],['Total Costs',last.costs,prev.costs]].forEach(([n,l,p])=>{growthRows.push({name:n,latest:l,prior:p,growth:p?((l-p)/Math.abs(p))*100:0});});
  }

  return{records,periods,periodData,accounts,costAccounts,anomalies,growthRows,totalRev};
}

// ════════════════════════════════════════
// COMMENTARY (Claude API)
// ════════════════════════════════════════
const FPA_FB={executiveSummary:'The company delivered mixed results against budget for the period. Revenue came in above plan driven by strong services performance, while cost overruns in R&D and G&A partially offset the gains. EBITDA finished slightly below target, warranting close monitoring.',keyDrivers:['Services revenue outperformed by 12% driven by new enterprise contract wins','R&D spend exceeded budget by 7% reflecting accelerated headcount growth','Product sales declined 3% below plan due to extended enterprise sales cycles'],costAnalysis:'Total operating costs ran 4.1% above budget, driven by headcount additions in R&D and incremental G&A infrastructure. COGS came in favorable at 4% below plan due to improved procurement.',risksAndOpportunities:{risks:['Continued R&D overspend without corresponding revenue acceleration may compress margins','Product sales pipeline elongation could impact Q2 targets'],opportunities:['Services division momentum positions the company for strong upsell cycles','Material cost savings can be further optimised via supplier renegotiation']},cashFlowObservations:'Monthly burn rate remains within acceptable parameters. Working capital is healthy; however, continued cost pressure warrants a mid-quarter budget reforecast.',recommendations:['Initiate a detailed R&D budget review with department heads','Accelerate product pipeline to recover the shortfall','Commission services capacity planning to capitalise on the growth trajectory'],overallRating:'Mixed',headline:'Services shine as R&D costs weigh on EBITDA'};

const FIN_FB={diagnostic:'Revenue is growing steadily across the period, driven primarily by Services expansion. However, margin compression is evident as hosting infrastructure and direct labor costs are growing faster than revenue. R&D investment is the primary driver of operating margin pressure, growing 36% vs 25% revenue growth.',marginInsights:[{severity:'high',text:'R&D spend has grown 36% over the period vs 25% revenue growth — this is the primary margin drag. Review headcount efficiency vs output metrics.',type:'red'},{severity:'high',text:'Hosting & infrastructure costs are scaling super-linearly with revenue, suggesting inefficient cloud spend. A cost optimisation review could recover 1-2% margin.',type:'red'},{severity:'medium',text:'G&A costs are growing at 27% — above revenue growth rate — indicating potential overhead creep. Industry benchmark: G&A should be 8-12% of revenue.',type:'amb'},{severity:'positive',text:'Services gross margin is strong and improving. This segment is the margin engine — continued investment here carries high ROI.',type:'grn'}],recommendations:['Conduct a cloud infrastructure audit — unoptimised spend likely represents 15-20% savings','Implement headcount-to-revenue ratio targets for R&D to protect operating margins','Review G&A vendor contracts and automate repetitive processes','Accelerate Services revenue mix shift — it carries the highest margin profile']};

async function callAPI(system,prompt){
  try{
    const controller=new AbortController();
    const timer=setTimeout(()=>controller.abort(),6000);
    const res=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:1100,system,messages:[{role:'user',content:prompt}]}),signal:controller.signal});
    clearTimeout(timer);
    const d=await res.json();
    return(d.content||[]).filter(b=>b.type==='text').map(b=>b.text).join('');
  }catch(e){return null;}
}

// Build smart fallback commentary from real parsed numbers
function buildFPAFallback(analysis){
  const k=analysis.kpis;
  const topFav=[...analysis.rows].filter(r=>r.fav).sort((a,b)=>Math.abs(b.v)-Math.abs(a.v)).slice(0,2);
  const topUnfav=[...analysis.rows].filter(r=>!r.fav).sort((a,b)=>Math.abs(b.v)-Math.abs(a.v)).slice(0,2);
  const rating=k.ebVar>=0?'Favorable':k.ebVar>=-k.bEB*0.05?'Mixed':'Unfavorable';
  return{
    executiveSummary:`The company delivered ${rating.toLowerCase()} results against budget for the period. Revenue came in ${k.revVar>=0?'above':'below'} plan at ${fK(k.aRev)} vs budget of ${fK(k.bRev)} (${fP(k.revVarP)}). Total costs ran at ${fK(k.aCost)} vs budget ${fK(k.bCost)} (${fP(k.expVarP)}). EBITDA finished at ${fK(k.aEB)}, a variance of ${fK(k.ebVar)} (${fP(k.ebVarP)}) against budget.`,
    keyDrivers:[
      topFav[0]?`${topFav[0].Account} was the strongest performer, coming in ${fP(topFav[0].vp)} ${topFav[0].fav?'favorable':'unfavorable'} vs budget at ${fK(topFav[0].Actual)}`:'Revenue mix performed in line with plan',
      topFav[1]?`${topFav[1].Account} delivered a ${fP(Math.abs(topFav[1].vp))} favorable variance, contributing ${fK(Math.abs(topFav[1].v))} to the overall result`:'Cost lines broadly tracked budget expectations',
      topUnfav[0]?`${topUnfav[0].Account} was the key area of overspend at ${fK(topUnfav[0].Actual)} vs budget ${fK(topUnfav[0].Budget)} (${fP(topUnfav[0].vp)})`:'No material unfavorable variances identified',
    ],
    costAnalysis:`Total operating costs of ${fK(k.aCost)} were ${k.expVar>=0?'above':'below'} budget by ${fK(Math.abs(k.expVar))} (${fP(Math.abs(k.expVarP))}). ${topUnfav[0]?topUnfav[0].Account+' was the primary driver of cost variance.':'Cost performance was broadly in line with plan.'}`,
    risksAndOpportunities:{
      risks:[
        topUnfav[0]?`Continued overspend in ${topUnfav[0].Account} (${fP(topUnfav[0].vp)}) without corresponding revenue offset will pressure margins in future periods`:'Monitor cost lines for any acceleration of spend above budget',
        `Monthly burn rate of ${fK(k.burn)} should be tracked closely; any further cost increases may require a mid-period reforecast`,
      ],
      opportunities:[
        topFav[0]?`${topFav[0].Account} momentum (${fP(topFav[0].vp)} vs budget) represents an opportunity to accelerate growth investment in this area`:'Favorable variances create headroom for targeted reinvestment',
        `Procurement and vendor contract reviews could yield additional savings to offset cost pressures elsewhere`,
      ],
    },
    cashFlowObservations:`Monthly average burn rate stands at ${fK(k.burn)}. Working capital position should be reviewed given the cost variance trajectory of ${fP(k.expVarP)} against budget.`,
    recommendations:[
      topUnfav[0]?`Conduct a detailed review of ${topUnfav[0].Account} spend with department heads to identify savings or reforecast requirements`:'Review all cost lines above 5% unfavorable variance with budget owners',
      topFav[0]?`Build on the ${topFav[0].Account} outperformance — assess capacity to accelerate further in the next period`:'Maintain momentum in outperforming revenue lines',
      `Prepare a revised full-year forecast incorporating Q1 actuals and updated assumptions for the remaining periods`,
    ],
    overallRating:rating,
    headline:`${rating} quarter as ${k.revVar>=0?'revenue beats':'costs exceed'} budget by ${fP(Math.abs(k.revVar>=0?k.revVarP:k.expVarP))}`,
  };
}

function buildFINFallback(fin){
  const pd=fin.periodData;
  if(!pd.length)return FIN_FB;
  const last=pd[pd.length-1],first=pd[0];
  const revGrowth=first.revenue?((last.revenue-first.revenue)/first.revenue)*100:0;
  const gmChg=last.grossMargin-first.grossMargin;
  const topCost=fin.costAccounts[0];
  const topCost2=fin.costAccounts[1];
  const marginTrend=gmChg<-1?'declining':'stable or improving';
  return{
    diagnostic:`Revenue has ${revGrowth>=0?'grown':'declined'} by ${fP(Math.abs(revGrowth))} over the period, from ${fK(first.revenue)} to ${fK(last.revenue)}. Gross margin is ${marginTrend} at ${fX(last.grossMargin)} (${fP(gmChg)}pp change). Operating margin stands at ${fX(last.opMargin)}. ${topCost?topCost.account+' is the largest cost driver at '+fX(fin.totalRev?topCost.total/fin.totalRev*100:0)+'% of total revenue.':'Cost structure appears broadly in line with revenue growth.'}`,
    marginInsights:[
      topCost&&fin.totalRev?{severity:topCost.total/fin.totalRev>0.25?'high':'medium',text:`${topCost.account} consumes ${fX(topCost.total/fin.totalRev*100)} of revenue and is the single largest cost line — review for optimisation opportunities.`,type:topCost.total/fin.totalRev>0.25?'red':'amb'}:{severity:'medium',text:'Review the largest cost lines as a proportion of revenue to identify optimisation opportunities.',type:'amb'},
      gmChg<-2?{severity:'high',text:`Gross margin has compressed ${fP(Math.abs(gmChg))}pp from ${fX(first.grossMargin)} to ${fX(last.grossMargin)} — investigate whether cost of goods is growing faster than pricing can absorb.`,type:'red'}:{severity:'positive',text:`Gross margin is holding at ${fX(last.grossMargin)}, indicating stable pricing power relative to direct costs.`,type:'grn'},
      topCost2&&fin.totalRev?{severity:'medium',text:`${topCost2.account} represents ${fX(topCost2.total/fin.totalRev*100)} of revenue. Monitor whether this scales proportionally as revenue grows.`,type:'amb'}:{severity:'positive',text:'Secondary cost lines appear well-managed relative to revenue scale.',type:'grn'},
      fin.anomalies.length>0?{severity:'medium',text:`${fin.anomalies[0].account} showed a ${fP(Math.abs(fin.anomalies[0].change))} ${fin.anomalies[0].change>0?'increase':'decrease'} period-over-period — this warrants investigation.`,type:Math.abs(fin.anomalies[0].change)>40?'red':'amb'}:{severity:'positive',text:'No significant anomalies detected. All line items are tracking within normal variance ranges.',type:'grn'},
    ],
    recommendations:[
      topCost?`Conduct a detailed review of ${topCost.account} — at ${fX(fin.totalRev?topCost.total/fin.totalRev*100:0)} of revenue it represents the highest leverage opportunity for margin improvement`:'Review the top 3 cost lines for efficiency and vendor renegotiation opportunities',
      gmChg<-1?`Address gross margin compression of ${fP(Math.abs(gmChg))}pp — consider price adjustments, supplier renegotiation or product mix optimisation`:'Maintain current gross margin discipline and monitor for any cost inflation signals',
      `Build a 12-month rolling forecast incorporating the current trend trajectory of ${fP(revGrowth)} revenue growth and ${fX(last.opMargin)} operating margin`,
      fin.anomalies.length>0?`Investigate the ${fP(Math.abs(fin.anomalies[0].change))} movement in ${fin.anomalies[0].account} and determine whether it is a one-off or structural shift`:'Implement monthly variance reporting to detect anomalies earlier in the cycle',
    ],
  };
}

async function genFPACommentary(analysis){
  const k=analysis.kpis;
  const ctx=`Revenue: Budget ${fK(k.bRev)} Actual ${fK(k.aRev)} (${fP(k.revVarP)}), EBITDA: Budget ${fK(k.bEB)} Actual ${fK(k.aEB)} (${fP(k.ebVarP)}), Burn: ${fK(k.burn)}/mo.`;
  const top=[...analysis.rows].sort((a,b)=>Math.abs(b.v)-Math.abs(a.v)).slice(0,4).map(r=>r.Account+':'+fP(r.vp)).join(', ');
  const txt=await callAPI('You are an experienced CFO. Return ONLY valid JSON, no markdown, no fences.',`Analyse these financials and return a board-ready commentary JSON.\n${ctx}\nTop variances: ${top}\n\nReturn exactly:\n{"executiveSummary":"...","keyDrivers":["...","...","..."],"costAnalysis":"...","risksAndOpportunities":{"risks":["...","..."],"opportunities":["...","..."]},"cashFlowObservations":"...","recommendations":["...","...","..."],"overallRating":"Favorable|Unfavorable|Mixed","headline":"8-word punchy headline"}`);
  try{if(txt)return JSON.parse(txt);}catch(e){}
  return buildFPAFallback(analysis);
}

async function genFINCommentary(fin){
  const pd=fin.periodData,last=pd[pd.length-1]||{};
  const ctx=`Periods: ${fin.periods.join(', ')}. Latest Revenue: ${fK(last.revenue)}, Gross Margin: ${fX(last.grossMargin)}, Operating Margin: ${fX(last.opMargin)}. Top costs: ${fin.costAccounts.slice(0,5).map(c=>c.account+':'+fX(fin.totalRev?c.total/fin.totalRev*100:0)+'% of rev').join(', ')}. Anomalies: ${fin.anomalies.slice(0,3).map(a=>a.account+':'+fP(a.change)).join(', ')||'None detected'}.`;
  const txt=await callAPI('You are a senior financial analyst. Return ONLY valid JSON, no markdown, no fences.',`Analyse these financials and return detailed insights JSON.\n${ctx}\n\nReturn exactly:\n{"diagnostic":"3-4 sentence overall diagnostic mentioning specific numbers","marginInsights":[{"severity":"high|medium|positive","text":"specific insight with numbers","type":"red|amb|grn"},{"severity":"...","text":"...","type":"..."},{"severity":"...","text":"...","type":"..."},{"severity":"...","text":"...","type":"..."}],"recommendations":["specific rec 1","specific rec 2","specific rec 3","specific rec 4"]}`);
  try{if(txt)return JSON.parse(txt);}catch(e){}
  return buildFINFallback(fin);
}

// ════════════════════════════════════════
// FP&A FLOW
// ════════════════════════════════════════
async function startFPA(){
  if(!S.fpaDemoOn&&(!S.bFile||!S.aFile)){toast('Upload both files or enable demo data','error');return;}
  g('fpaForm').style.display='none';g('fpaProc').style.display='block';
  const steps=[['Uploading…','Preparing your files'],['Parsing…','Reading rows and columns'],['Calculating variances…','Running the variance engine'],['Generating commentary…','Building insights from your data']];
  async function step(i){g('fpaSt').textContent=steps[i][0];g('fpaDsc').textContent=steps[i][1];await new Promise(r=>setTimeout(r,i===3?600:420));}
  for(let i=0;i<4;i++)await step(i);
  let data=S.fpaDemoOn?FPA_DEMO:null;
  if(!data){
    try{
      const[bR,aR]=await Promise.all([readFile(S.bFile),readFile(S.aFile)]);
      data=aR.map(a=>{const b=bR.find(r=>r.Department===a.Department&&r.Account===a.Account&&r.Month===a.Month)||{};return{Department:a.Department,Account:a.Account,Month:a.Month,Budget:+b.Budget||0,Actual:+a.Actual||0};});
    }catch(e){toast('Error reading files — using demo data','error');data=FPA_DEMO;}
  }
  const analysis=calcFPA(data);
  const commentary=await genFPACommentary(analysis);
  S.fpaReport={analysis,commentary,at:new Date()};
  g('fpaForm').style.display='block';g('fpaProc').style.display='none';
  toast('FP&A Report ready!','success');
  go('fpa-report');
  renderFPAReport();
}

// ════════════════════════════════════════
// FINANCIAL ANALYSIS FLOW
// ════════════════════════════════════════
async function startFIN(){
  if(!S.finDemoOn&&!S.finFile){toast('Upload a file or enable demo data','error');return;}
  g('finForm').style.display='none';g('finProc').style.display='block';
  const steps=[['Uploading…','Preparing your data'],['Detecting format…','Parsing columns and periods'],['Running analysis…','Trend, margin & cost calculations'],['Detecting anomalies…','Scanning for unusual patterns'],['Generating insights…','Building insights from your data']];
  async function step(i){g('finSt').textContent=steps[i][0];g('finDsc').textContent=steps[i][1];await new Promise(r=>setTimeout(r,i===4?700:380));}
  for(let i=0;i<5;i++)await step(i);
  let raw=S.finDemoOn?FIN_DEMO:null;
  if(!raw){try{raw=await readFile(S.finFile);}catch(e){toast('Error reading file — using demo data','error');raw=FIN_DEMO;}}
  const fin=calcFIN(raw);
  const insights=await genFINCommentary(fin);
  S.finReport={fin,insights,at:new Date()};
  g('finForm').style.display='block';g('finProc').style.display='none';
  toast('Financial Analysis ready!','success');
  go('fin-report');
}

// ════════════════════════════════════════
// SVG CHARTS
// ════════════════════════════════════════
function mkLine(labels,datasets,h=200){
  if(!labels||!labels.length)return'<p class="text-mut fs13 tc" style="padding:40px 0">Need 2+ periods for chart</p>';
  const all=datasets.flatMap(d=>d.data).filter(Number.isFinite);
  if(!all.length)return'';
  const mn=Math.min(...all)*0.93,mx=Math.max(...all)*1.07,range=mx-mn||1;
  const W=400,H=h-26,pad=50;
  const xs=i=>pad+i/(Math.max(labels.length-1,1))*(W-pad);
  const ys=v=>H-((v-mn)/range)*H*0.85-8;
  let svg=`<svg viewBox="0 0 ${W} ${h}" style="width:100%;height:${h}px">`;
  for(let i=0;i<=3;i++){const y=8+i/3*(H*0.85);svg+=`<line x1="${pad}" y1="${y}" x2="${W}" y2="${y}" stroke="var(--bdr)" stroke-width="1"/><text x="${pad-4}" y="${y+3}" text-anchor="end" font-size="9" fill="var(--mut)">${fK(mx-(mx-mn)*i/3)}</text>`;}
  labels.forEach((l,i)=>{svg+=`<text x="${xs(i)}" y="${h-5}" text-anchor="middle" font-size="9" fill="var(--mut)">${esc(l)}</text>`;});
  datasets.forEach((ds,di)=>{
    const pts=ds.data.map((v,i)=>`${xs(i)},${ys(v)}`).join(' ');
    if(!ds.dash&&di===0){const area=`${xs(0)},${H} ${pts} ${xs(ds.data.length-1)},${H}`;svg+=`<polygon points="${area}" fill="${ds.color}" opacity="0.13"/>`;}
    svg+=`<polyline points="${pts}" fill="none" stroke="${ds.color}" stroke-width="2" stroke-linejoin="round"${ds.dash?' stroke-dasharray="5 4"':''}/>`;
    ds.data.forEach((v,i)=>{svg+=`<circle cx="${xs(i)}" cy="${ys(v)}" r="3.5" fill="${ds.color}"/>`;});
  });
  return svg+'</svg>';
}

function mkBar(labels,datasets,h=200){
  if(!labels||!labels.length)return'';
  const all=datasets.flatMap(d=>d.data).filter(Number.isFinite);
  if(!all.length)return'';
  const mn=Math.min(0,...all),mx=Math.max(...all)*1.1,range=mx-mn||1;
  const W=400,H=h-26,pad=50;
  const gw=(W-pad)/labels.length,bw=Math.min(30,gw*.36);
  const ys=v=>H-((v-mn)/range)*H*0.85-8;
  const bh=v=>Math.abs(((v-mn)/range)*H*0.85);
  let svg=`<svg viewBox="0 0 ${W} ${h}" style="width:100%;height:${h}px">`;
  for(let i=0;i<=3;i++){const y=8+i/3*(H*0.85);svg+=`<line x1="${pad}" y1="${y}" x2="${W}" y2="${y}" stroke="var(--bdr)" stroke-width="1"/><text x="${pad-4}" y="${y+3}" text-anchor="end" font-size="9" fill="var(--mut)">${fK(mx-(mx-mn)*i/3)}</text>`;}
  labels.forEach((l,i)=>{svg+=`<text x="${pad+(i+0.5)*gw}" y="${h-5}" text-anchor="middle" font-size="9" fill="var(--mut)">${esc(l)}</text>`;});
  datasets.forEach((ds,di)=>{ds.data.forEach((v,i)=>{const x=pad+i*gw+(di===0?gw*.04:bw+gw*.10);svg+=`<rect x="${x}" y="${ys(v)}" width="${bw}" height="${Math.max(bh(v),1)}" fill="${ds.color}" rx="2"/>`;});});
  return svg+'</svg>';
}

function mkDonut(entries,size=140){
  if(!entries.length)return'';
  const total=entries.reduce((s,e)=>s+Math.abs(e.v),0);if(!total)return'';
  const cx=size/2,cy=size/2,r=size*0.38,ir=size*0.22;
  let ang=-Math.PI/2,paths='';
  entries.forEach((e,i)=>{
    const sl=Math.abs(e.v)/total*Math.PI*2;
    const x1=cx+r*Math.cos(ang),y1=cy+r*Math.sin(ang),x2=cx+r*Math.cos(ang+sl),y2=cy+r*Math.sin(ang+sl);
    const ix1=cx+ir*Math.cos(ang),iy1=cy+ir*Math.sin(ang),ix2=cx+ir*Math.cos(ang+sl),iy2=cy+ir*Math.sin(ang+sl);
    const lg=sl>Math.PI?1:0;
    paths+=`<path d="M${ix1},${iy1} L${x1},${y1} A${r},${r} 0 ${lg} 1 ${x2},${y2} L${ix2},${iy2} A${ir},${ir} 0 ${lg} 0 ${ix1},${iy1}" fill="${PAL[i%PAL.length]}" stroke="var(--card)" stroke-width="2"/>`;
    ang+=sl;
  });
  return`<svg viewBox="0 0 ${size} ${size}" style="width:${size}px;height:${size}px">${paths}</svg>`;
}

function mkMarginLine(labels,datasets,h=170){
  if(!labels||!labels.length)return'';
  const all=datasets.flatMap(d=>d.data).filter(Number.isFinite);
  if(!all.length)return'';
  const mn=Math.min(...all,0)-2,mx=Math.max(...all)+5,range=mx-mn||1;
  const W=400,H=h-26,pad=44;
  const xs=i=>pad+i/(Math.max(labels.length-1,1))*(W-pad);
  const ys=v=>H-((v-mn)/range)*H*0.85-8;
  let svg=`<svg viewBox="0 0 ${W} ${h}" style="width:100%;height:${h}px">`;
  for(let i=0;i<=3;i++){const y=8+i/3*(H*0.85);svg+=`<line x1="${pad}" y1="${y}" x2="${W}" y2="${y}" stroke="var(--bdr)" stroke-width="1"/><text x="${pad-4}" y="${y+3}" text-anchor="end" font-size="9" fill="var(--mut)">${fX(mx-(mx-mn)*i/3)}</text>`;}
  labels.forEach((l,i)=>{svg+=`<text x="${xs(i)}" y="${h-5}" text-anchor="middle" font-size="9" fill="var(--mut)">${esc(l)}</text>`;});
  datasets.forEach(ds=>{
    const pts=ds.data.map((v,i)=>`${xs(i)},${ys(v)}`).join(' ');
    svg+=`<polyline points="${pts}" fill="none" stroke="${ds.color}" stroke-width="2" stroke-linejoin="round"/>`;
    ds.data.forEach((v,i)=>{svg+=`<circle cx="${xs(i)}" cy="${ys(v)}" r="3.5" fill="${ds.color}"/>`;});
  });
  return svg+'</svg>';
}

// ════════════════════════════════════════
// FP&A REPORT RENDER
// ════════════════════════════════════════
function renderFPAReport(){
  if(!S.fpaReport)return;
  const{analysis:an,commentary:co,at}=S.fpaReport;
  const k=an.kpis;
  const rc=co.overallRating==='Favorable'?'tg':co.overallRating==='Unfavorable'?'tr':'tam';
  g('fRtag').innerHTML=`<span class="tag ${rc}">${co.overallRating} Performance</span>`;
  g('fRH').textContent=co.headline||'FP&A Report';
  g('fRM').textContent=`Generated ${at?.toLocaleString()} · ${an.months.join(', ')}`;
  g('fRExec').textContent=co.executiveSummary;

  g('fRKPIs').innerHTML=[
    {l:'Total Revenue',v:fK(k.aRev),s:'Budget: '+fK(k.bRev),c:'var(--txt)'},
    {l:'Revenue Var',v:fK(k.revVar),s:fP(k.revVarP),c:clr(k.revVar)},
    {l:'EBITDA',v:fK(k.aEB),s:'Budget: '+fK(k.bEB),c:'var(--txt)'},
    {l:'EBITDA Var',v:fK(k.ebVar),s:fP(k.ebVarP),c:clr(k.ebVar)},
  ].map(x=>`<div class="card kc"><div class="kl">${x.l}</div><div class="kv" style="color:${x.c}">${x.v}</div><div class="ks" style="color:${x.c==='var(--txt)'?'var(--mut)':x.c}">${x.s}</div></div>`).join('');

  const md=an.monthly;
  g('fChRev').innerHTML=mkLine(md.map(m=>m.Month),[{data:md.map(m=>m.aRev),color:'var(--acc)'},{data:md.map(m=>m.bRev),color:'var(--dim)',dash:true}]);
  g('fChEB').innerHTML=mkBar(md.map(m=>m.Month),[{data:md.map(m=>m.bEB),color:'rgba(46,66,96,.85)'},{data:md.map(m=>m.aEB),color:'var(--acc)'}]);
  const expE=Object.entries(an.expByDept);
  g('fChExp').innerHTML=mkDonut(expE.map(([n,v])=>({n,v})));
  g('fExpLeg').innerHTML=expE.map(([n,v],i)=>`<div class="flex aic gap8"><div style="width:10px;height:10px;border-radius:2px;background:${PAL[i%PAL.length]}"></div><span>${esc(n)}: ${fK(v)}</span></div>`).join('');

  g('fRDrv').innerHTML=(co.keyDrivers||[]).map(d=>`<div class="flex gap8" style="align-items:flex-start"><div style="width:6px;height:6px;border-radius:50%;background:var(--acc);flex-shrink:0;margin-top:6px"></div><span class="fs13 lh">${esc(d)}</span></div>`).join('');
  g('fRCost').textContent=co.costAnalysis;
  g('fRCash').textContent=co.cashFlowObservations;
  g('fRRisks').innerHTML=(co.risksAndOpportunities?.risks||[]).map(r=>`<div class="fs13 lh p8 r8" style="background:rgba(255,64,96,.07);border-left:2px solid var(--red)">${esc(r)}</div>`).join('');
  g('fROpps').innerHTML=(co.risksAndOpportunities?.opportunities||[]).map(o=>`<div class="fs13 lh p8 r8" style="background:rgba(0,223,160,.07);border-left:2px solid var(--grn)">${esc(o)}</div>`).join('');
  g('fRRecs').innerHTML=(co.recommendations||[]).map((r,i)=>`<div class="flex gap10" style="align-items:flex-start;padding:10px 12px;background:var(--surf);border-radius:8px;border:1px solid var(--bdr)"><div style="width:20px;height:20px;border-radius:50%;background:var(--accD);border:1px solid rgba(0,200,240,.3);display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;color:var(--acc);flex-shrink:0">${i+1}</div><span class="fs13 lh">${esc(r)}</span></div>`).join('');
  g('fRTb').innerHTML=an.rows.map(r=>`<tr><td class="text-mut fs12">${esc(r.Department)}</td><td class="fw6">${esc(r.Account)}</td><td class="mono text-mut fs12">${esc(r.Month)}</td><td class="rr mono text-mut">${fK(r.Budget)}</td><td class="rr mono">${fK(r.Actual)}</td><td class="rr mono fw6" style="color:${r.fav?'var(--grn)':'var(--red)'}">${r.v>=0?'+':''}${fK(r.v)}</td><td class="rr mono" style="color:${r.fav?'var(--grn)':'var(--red)'}">${fP(r.vp)}</td><td><span class="tag ${r.fav?'tg':'tr'}" style="font-size:9px">${r.fav?'✓ Fav':'✗ Unfav'}</span></td></tr>`).join('');

  // Chat context
  S.chatHist=[];
  S.chatMode='fpa';
  g('chatFab').style.background='linear-gradient(135deg,var(--acc),#0088aa)';
  g('chatFab').style.color='#000';
}

// ════════════════════════════════════════
// FINANCIAL ANALYSIS REPORT RENDER
// ════════════════════════════════════════
let finTab='trends';
function renderFinTabs(){
  if(!S.finReport)return;
  const{fin,insights,at}=S.finReport;
  const pd=fin.periodData,last=pd[pd.length-1]||{revenue:0,grossMargin:0,opMargin:0,costs:0};
  const prev=pd[pd.length-2]||last;
  const revGrowth=prev.revenue?((last.revenue-prev.revenue)/Math.abs(prev.revenue))*100:0;

  g('finRH').textContent=insights.headline||'Financial Analysis Report';
  g('finRM').textContent=`Generated ${at?.toLocaleString()} · ${fin.periods.join(' · ')}`;
  g('finDiag').textContent=insights.diagnostic;

  g('finKPIs').innerHTML=[
    {l:'Latest Revenue',v:fK(last.revenue),s:fP(revGrowth)+' period growth',c:clr(revGrowth)},
    {l:'Gross Margin',v:fX(last.grossMargin),s:fP(last.grossMargin-prev.grossMargin)+'pp vs prior',c:clr(last.grossMargin-prev.grossMargin)},
    {l:'Operating Margin',v:fX(last.opMargin),s:fP(last.opMargin-prev.opMargin)+'pp vs prior',c:clr(last.opMargin-prev.opMargin)},
    {l:'Total Costs',v:fK(last.costs),s:fX(last.revenue?last.costs/last.revenue*100:0)+' of revenue',c:'var(--amb)'},
  ].map(x=>`<div class="card kc"><div class="kl">${x.l}</div><div class="kv" style="color:${x.c}">${x.v}</div><div class="ks" style="color:${x.c==='var(--txt)'?'var(--mut)':x.c}">${x.s}</div></div>`).join('');

  const TABS=[{k:'trends',l:'Trends'},{k:'margins',l:'Margin Analysis'},{k:'costs',l:'Cost Structure'},{k:'anomalies',l:'Anomalies'},{k:'data',l:'Data Table'}];
  g('finTabBar').innerHTML=TABS.map(t=>`<button class="tab${t.k===finTab?' on-v':''}" onclick="switchFinTab('${t.k}')">${t.l}</button>`).join('');
  drawFinTab();

  S.chatHist=[];S.chatMode='fin';
  g('chatFab').style.background='linear-gradient(135deg,var(--pur),#6040CC)';
  g('chatFab').style.color='#fff';
}

function switchFinTab(k){
  finTab=k;
  document.querySelectorAll('#finTabBar .tab').forEach(t=>{const tk=t.getAttribute('onclick').match(/'([^']+)'/)?.[1];t.className='tab'+(tk===k?' on-v':'');});
  drawFinTab();
}

function drawFinTab(){
  if(!S.finReport)return;
  const{fin,insights}=S.finReport;
  const pd=fin.periodData,tc=g('finTabContent');

  if(finTab==='trends'){
    tc.innerHTML=`
    <div class="g2 mb20">
      <div class="card p20">
        <div class="slbl">Revenue vs Costs Trend</div>
        <div class="flex gap12 mb12 fs11 text-mut">
          <div class="flex aic gap5"><div style="width:10px;height:3px;border-radius:2px;background:var(--pur)"></div>Revenue</div>
          <div class="flex aic gap5"><div style="width:10px;height:3px;border-radius:2px;background:var(--red)"></div>Costs</div>
        </div>
        ${mkLine(pd.map(p=>p.period),[{data:pd.map(p=>p.revenue),color:'var(--pur)'},{data:pd.map(p=>p.costs),color:'var(--red)',dash:true}])}
      </div>
      <div class="card p20">
        <div class="slbl">Profit Trend</div>
        <div class="flex gap12 mb12 fs11 text-mut">
          <div class="flex aic gap5"><div style="width:10px;height:3px;border-radius:2px;background:var(--grn)"></div>Gross Profit</div>
          <div class="flex aic gap5"><div style="width:10px;height:3px;border-radius:2px;background:var(--acc)"></div>Operating Profit</div>
        </div>
        ${mkLine(pd.map(p=>p.period),[{data:pd.map(p=>p.grossProfit),color:'var(--grn)'},{data:pd.map(p=>p.operatingProfit),color:'var(--acc)'}])}
      </div>
    </div>
    <div class="card oh">
      <div class="p16" style="border-bottom:1px solid var(--bdr)"><span class="fw6 fs14">Period Summary</span></div>
      <div class="ox"><table><thead><tr><th>Period</th><th class="rr">Revenue</th><th class="rr">Gross Profit</th><th class="rr">Op Profit</th><th class="rr">Gross Margin</th><th class="rr">Op Margin</th></tr></thead><tbody>
      ${pd.map(p=>`<tr><td class="fw5">${esc(p.period)}</td><td class="rr mono">${fK(p.revenue)}</td><td class="rr mono" style="color:${clr(p.grossProfit)}">${fK(p.grossProfit)}</td><td class="rr mono" style="color:${clr(p.operatingProfit)}">${fK(p.operatingProfit)}</td><td class="rr" style="color:${clr(p.grossMargin)}">${fX(p.grossMargin)}</td><td class="rr" style="color:${clr(p.opMargin)}">${fX(p.opMargin)}</td></tr>`).join('')}
      </tbody></table></div>
    </div>`;
  }

  else if(finTab==='margins'){
    tc.innerHTML=`
    <div class="card p20 mb20">
      <div class="flex aic jcb mb16">
        <div class="slbl" style="margin-bottom:0">Margin Trend Over Time</div>
        <div class="flex gap12 fs11 text-mut">
          <div class="flex aic gap5"><div style="width:10px;height:3px;border-radius:2px;background:var(--grn)"></div>Gross Margin</div>
          <div class="flex aic gap5"><div style="width:10px;height:3px;border-radius:2px;background:var(--acc)"></div>Operating Margin</div>
        </div>
      </div>
      ${mkMarginLine(pd.map(p=>p.period),[{data:pd.map(p=>p.grossMargin),color:'var(--grn)'},{data:pd.map(p=>p.opMargin),color:'var(--acc)'}])}
    </div>
    <div class="card p22 mb20">
      <div class="slbl mb16">🔍 What's Draining Your Margins</div>
      ${(insights.marginInsights||[]).map(m=>{
        const lc=m.type==='red'?'var(--red)':m.type==='amb'?'var(--amb)':'var(--grn)';
        const bc=m.type==='red'?'rgba(255,64,96,.07)':m.type==='amb'?'rgba(255,176,32,.07)':'rgba(0,223,160,.07)';
        return`<div style="padding:12px 14px;border-radius:9px;background:${bc};border-left:3px solid ${lc};margin-bottom:10px">
          <div class="flex aic gap8 mb5"><div style="width:7px;height:7px;border-radius:50%;background:${lc}"></div><span class="fw6 fs11" style="color:${lc};text-transform:uppercase;letter-spacing:.06em">${esc(m.severity)}</span></div>
          <p class="fs13 lh">${esc(m.text)}</p></div>`;
      }).join('')}
    </div>
    <div class="card p22">
      <div class="slbl">Recommendations</div>
      <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(210px,1fr));gap:10px">
        ${(insights.recommendations||[]).map((r,i)=>`<div class="flex gap10" style="align-items:flex-start;padding:10px 12px;background:var(--surf);border-radius:8px;border:1px solid var(--bdr)"><div style="width:20px;height:20px;border-radius:50%;background:rgba(155,127,255,.15);border:1px solid rgba(155,127,255,.3);display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:700;color:var(--pur);flex-shrink:0">${i+1}</div><span class="fs13 lh">${esc(r)}</span></div>`).join('')}
      </div>
    </div>`;
  }

  else if(finTab==='costs'){
    const expE=fin.costAccounts.slice(0,8);
    const maxAmt=expE[0]?.total||1;
    tc.innerHTML=`
    <div class="g2 mb20">
      <div class="card p22">
        <div class="slbl">Cost as % of Revenue</div>
        <div class="flex fdc gap10">
          ${expE.map((c,i)=>{
            const pct=fin.totalRev?c.total/fin.totalRev*100:0;
            return`<div>
              <div class="flex aic jcb mb5"><span class="fs13 fw5">${esc(c.account)}</span><span class="mono fs12 fw6">${fX(pct)}</span></div>
              <div class="pbar"><div class="pfill" style="width:${Math.min(pct/40*100,100)}%;background:${PAL[i%PAL.length]}"></div></div>
            </div>`;
          }).join('')}
        </div>
      </div>
      <div class="card p20">
        <div class="slbl">Cost Mix</div>
        <div class="flex jcc mb12">${mkDonut(expE.map((c,i)=>({n:c.account,v:c.total})))}</div>
        <div class="flex fw gap8">
          ${expE.map((c,i)=>`<div class="flex aic gap6 fs11 text-mut"><div style="width:8px;height:8px;border-radius:2px;background:${PAL[i%PAL.length]}"></div>${esc(c.account)}</div>`).join('')}
        </div>
      </div>
    </div>
    <div class="card oh">
      <div class="p16" style="border-bottom:1px solid var(--bdr)"><span class="fw6 fs14">Account Analysis</span></div>
      <div class="ox"><table><thead><tr><th>Account</th><th>Category</th><th class="rr">Total</th><th class="rr">% Revenue</th><th>Trend</th></tr></thead><tbody>
      ${fin.accounts.slice(0,12).map(a=>{
        const vals=fin.periods.map(p=>a.byPeriod[p]||0);
        const trend=vals.length>=2?(vals[vals.length-1]>vals[0]?'↑ Growing':'↓ Declining'):'—';
        const tc2=trend.includes('↑')?'var(--grn)':trend.includes('↓')?'var(--red)':'var(--mut)';
        return`<tr><td class="fw5 fs12">${esc(a.account)}</td><td><span class="tag tpur" style="font-size:9px">${esc(a.category)}</span></td><td class="rr mono">${fK(a.total)}</td><td class="rr mono text-mut">${fX(fin.totalRev?a.total/fin.totalRev*100:0)}</td><td style="color:${tc2};font-size:12px">${trend}</td></tr>`;
      }).join('')}
      </tbody></table></div>
    </div>`;
  }

  else if(finTab==='anomalies'){
    tc.innerHTML=`
    <div class="card p22 mb20">
      <div class="flex aic gap8 mb16"><svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="var(--amb)" stroke-width="2"><path d="M10.29 3.86L1.82 18a2 2 0 0 0 1.71 3h16.94a2 2 0 0 0 1.71-3L13.71 3.86a2 2 0 0 0-3.42 0z"/><line x1="12" y1="9" x2="12" y2="13"/><line x1="12" y1="17" x2="12.01" y2="17"/></svg><span class="slbl" style="margin-bottom:0">Anomaly Detection</span></div>
      ${fin.anomalies.length===0
        ?'<div style="padding:10px 14px;border-radius:9px;background:rgba(0,223,160,.07);border-left:3px solid var(--grn);font-size:13px">✅ No significant anomalies detected. All line items are within normal variance ranges.</div>'
        :fin.anomalies.map(a=>`<div class="flex aic jcb mb8" style="padding:12px 14px;border-radius:9px;background:${Math.abs(a.change)>40?'rgba(255,64,96,.08)':'rgba(255,176,32,.08)'};border:1px solid ${Math.abs(a.change)>40?'rgba(255,64,96,.25)':'rgba(255,176,32,.25)'}">
          <div><div class="fw6 fs13">${esc(a.account)}</div><div class="text-mut fs12">${esc(a.category)}</div></div>
          <div style="text-align:right"><div class="fw7 fs14" style="color:${a.change>0?'var(--red)':'var(--grn)'}">${fP(a.change)}</div><div class="text-mut fs11">${fK(a.latest)} vs ${fK(a.prev)} prior</div></div>
        </div>`).join('')}
    </div>
    <div class="card oh">
      <div class="p16" style="border-bottom:1px solid var(--bdr)"><span class="fw6 fs14">Period-over-Period Growth</span></div>
      <div class="ox"><table><thead><tr><th>Metric</th><th class="rr">Latest</th><th class="rr">Prior</th><th class="rr">Growth</th></tr></thead><tbody>
      ${fin.growthRows.map(r=>`<tr><td class="fw5">${esc(r.name)}</td><td class="rr mono">${fK(r.latest)}</td><td class="rr mono text-mut">${fK(r.prior)}</td><td class="rr fw6" style="color:${r.name==='Total Costs'?clr(r.growth,true):clr(r.growth)}">${fP(r.growth)}</td></tr>`).join('')}
      </tbody></table></div>
    </div>`;
  }

  else if(finTab==='data'){
    tc.innerHTML=`
    <div class="card oh">
      <div class="p16" style="border-bottom:1px solid var(--bdr)"><span class="fw6 fs14">Data Table — ${fin.records.length} records</span></div>
      <div class="ox"><table><thead><tr><th>Account</th><th>Category</th><th class="rr">Amount</th><th>Period</th></tr></thead><tbody>
      ${fin.records.slice(0,30).map(r=>`<tr><td class="fw5 fs12">${esc(r.account)}</td><td><span class="tag tpur" style="font-size:9px">${esc(r.category)}</span></td><td class="rr mono">${fK(r.amount)}</td><td class="text-mut fs12">${esc(r.period)}</td></tr>`).join('')}
      </tbody></table></div>
      ${fin.records.length>30?`<div class="p16 tc text-mut fs12" style="border-top:1px solid var(--bdr)">Showing 30 of ${fin.records.length} records</div>`:''}
    </div>`;
  }
}

// ════════════════════════════════════════
// CHAT
// ════════════════════════════════════════
function openChat(mode){
  S.chatMode=mode||S.chatMode;
  g('chatPan').style.display='flex';
  g('chatFab').style.display='none';
  setTimeout(()=>g('chatIn')?.focus(),80);
}
function openChatFab(){g('chatPan').style.display='flex';g('chatFab').style.display='none';}
function closeChat(){g('chatPan').style.display='none';g('chatFab').style.display='flex';}

function addBub(txt,role){
  const d=document.createElement('div');
  d.className='bu bu-'+(role==='u'?'u':'a');
  d.textContent=txt;
  g('chatMsgs').appendChild(d);
  g('chatMsgs').scrollTop=9999;
}

async function sendChat(){
  const inp=g('chatIn'),msg=inp.value.trim();if(!msg)return;
  inp.value='';addBub(msg,'u');S.chatHist.push({role:'user',content:msg});
  // typing dots
  const typ=document.createElement('div');typ.className='bu bu-a';typ.id='typingDot';typ.innerHTML='<span style="display:flex;gap:4px;align-items:center">'+'<span style="width:5px;height:5px;border-radius:50%;background:var(--mut);animation:pulse 1.2s 0s infinite;display:inline-block"></span>'.repeat(3)+'</span>';
  g('chatMsgs').appendChild(typ);g('chatMsgs').scrollTop=9999;
  let ctx='';
  if(S.chatMode==='fpa'&&S.fpaReport){const k=S.fpaReport.analysis.kpis;ctx=`FP&A: Revenue var ${fP(k.revVarP)}, EBITDA var ${fP(k.ebVarP)}, Burn ${fK(k.burn)}/mo. ${S.fpaReport.commentary.executiveSummary}`;}
  if(S.chatMode==='fin'&&S.finReport){const l=S.finReport.fin.periodData[S.finReport.fin.periodData.length-1]||{};ctx=`Financial Analysis: Revenue ${fK(l.revenue)}, Gross Margin ${fX(l.grossMargin)}, Operating Margin ${fX(l.opMargin)}. ${S.finReport.insights.diagnostic}`;}
  const txt=await callAPI(`You are a concise professional financial analyst. 2-4 sentences max unless asked for more. Context: ${ctx}`,[...S.chatHist.slice(-8)].map(m=>m.content).join('\n'));
  g('typingDot')?.remove();
  const reply=txt||'The commentary engine is running in offline mode. Based on the data: '+ctx;
  S.chatHist.push({role:'assistant',content:reply});
  addBub(reply,'a');
}

// ════════════════════════════════════════
// TOAST
// ════════════════════════════════════════
function toast(msg,type='info'){
  const colors={success:'var(--grn)',error:'var(--red)',info:'var(--acc)'};
  const d=document.createElement('div');
  d.style.cssText=`background:${colors[type]||colors.info};color:#000;padding:9px 15px;border-radius:8px;font-size:13px;font-weight:600;box-shadow:0 4px 18px rgba(0,0,0,.4);animation:fadeUp .3s ease;max-width:280px;pointer-events:auto`;
  d.textContent=msg;g('toasts').appendChild(d);setTimeout(()=>d.remove(),3400);
}

// INIT
go('home');
</script>
</body>
</html>
