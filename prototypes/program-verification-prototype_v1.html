<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Program Verification — prototype v1</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Mono:wght@400;500;600&family=IBM+Plex+Sans:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{
  --bg:#16181c; --chrome:#1f2329; --chrome2:#262b32; --panel:#1c2026;
  --line:#333a44; --line2:#2a3038; --viewport:#0c0e11;
  --text:#d8dde4; --muted:#8b939f; --faint:#5c636e;
  --blue:#4f83f0; --fileblue:#2f5cb0; --cyan:#39c0f0; --teal:#1fb6a6;
  --green:#34d399; --violet:#a78bfa; --red:#ff5d5d;
  --il:#eaf1f8;
  --ui:"IBM Plex Sans",system-ui,sans-serif;
  --mono:"IBM Plex Mono",ui-monospace,Menlo,monospace;
}
*{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%}
body{
  background:var(--bg);color:var(--text);font-family:var(--ui);font-size:13px;
  -webkit-font-smoothing:antialiased;overflow:hidden;
}
button,input,select{font-family:inherit}
.micro{font-size:10px;font-weight:600;letter-spacing:.8px;text-transform:uppercase;color:var(--faint)}
#login{
  height:100vh;display:flex;align-items:center;justify-content:center;
  background:
    radial-gradient(900px 420px at 18% 12%, rgba(79,131,240,.14), transparent 55%),
    radial-gradient(700px 380px at 88% 80%, rgba(57,192,240,.08), transparent 50%),
    var(--viewport);
}
.login-card{
  width:420px;background:var(--chrome);border:1px solid var(--line);border-radius:12px;
  box-shadow:0 28px 70px rgba(0,0,0,.55);overflow:hidden;
}
.login-card .head{padding:22px 24px 16px;border-bottom:1px solid var(--line2)}
.login-card .head h1{font-size:18px;font-weight:700;letter-spacing:.2px}
.login-card .head p{color:var(--muted);margin-top:6px;line-height:1.45}
.brand-row{display:flex;align-items:center;gap:10px;margin-bottom:10px}
.brand-row svg{width:22px;height:22px;filter:drop-shadow(0 1.2px 1.3px rgba(0,0,0,.5))}
.login-card .body{padding:20px 24px 24px}
.fld{display:block;margin-bottom:12px}
.fld span{display:block;margin-bottom:6px}
.fld input{
  width:100%;background:var(--viewport);border:1px solid var(--line);border-radius:6px;
  color:var(--text);padding:10px 11px;font-family:var(--mono);font-size:12px;
}
.fld input:focus{outline:none;border-color:var(--cyan)}
.btn{
  display:inline-flex;align-items:center;justify-content:center;gap:8px;
  border:1px solid transparent;border-radius:8px;padding:9px 14px;cursor:pointer;font-weight:600;
}
.btn-primary{background:var(--blue);color:#fff;width:100%;margin-top:6px}
.btn-primary:hover{filter:brightness(1.08)}
.btn-ghost{background:transparent;border-color:var(--line);color:var(--text)}
.btn-ghost:hover{border-color:#3a424f;background:#2c323a}
.btn-green{background:rgba(52,211,153,.12);border:1px solid rgba(52,211,153,.45);color:var(--green)}
#app{display:none;flex-direction:column;height:100vh}
#app.show{display:flex}
.titlebar{
  display:flex;align-items:center;height:34px;background:var(--chrome);
  border-bottom:1px solid var(--line);padding:0 12px;gap:14px;flex:none;
}
.titlebar .logo{display:flex;align-items:center;gap:8px;font-weight:700}
.titlebar .logo svg{width:16px;height:16px}
.titlebar .appname{color:var(--muted);font-size:12px}
.modebadge{
  display:inline-flex;align-items:center;gap:6px;font-size:11px;font-family:var(--mono);
  padding:2px 9px;border-radius:11px;border:1px solid rgba(57,192,240,.4);color:var(--cyan);
}
.modebadge .d{width:7px;height:7px;border-radius:50%;background:var(--cyan);box-shadow:0 0 6px var(--cyan)}
.winbtns{margin-left:auto;color:var(--faint);font-family:var(--mono);font-size:12px;display:flex;gap:14px}
.shell{display:flex;flex:1;min-height:0}
.rail{
  width:92px;background:var(--panel);border-right:1px solid var(--line);
  display:flex;flex-direction:column;align-items:center;padding:10px 0;gap:8px;flex:none;
}
.rbtn{
  position:relative;width:76px;height:72px;padding:8px 8px 8px 14px;border-radius:11px;
  display:flex;flex-direction:column;align-items:center;justify-content:flex-start;gap:4px;
  cursor:pointer;color:var(--text);font-size:10px;line-height:1.15;text-align:center;
  --acc:var(--muted);
  background:linear-gradient(158deg,#232833,#14171d 65%,#101318);
  border:1px solid #2c333e;
  box-shadow:inset 0 1px 0 rgba(255,255,255,.06),0 3px 8px rgba(0,0,0,.4);
}
.rbtn::before{
  content:"";position:absolute;left:4px;top:10px;bottom:10px;width:4px;border-radius:3px;
  background:var(--acc);box-shadow:0 0 9px var(--acc);
}
.rbtn .ic{width:28px;height:28px;display:grid;place-items:center}
.rbtn .ic svg{width:28px;height:28px;filter:drop-shadow(0 1.2px 1.3px rgba(0,0,0,.5))}
.rbtn:hover{border-color:#3a424f;background:linear-gradient(158deg,#2b313d,#181c23 65%,#12151b)}
.rbtn.active{box-shadow:inset 0 0 0 1px rgba(79,131,240,.45),inset 0 1px 0 rgba(255,255,255,.06),0 3px 8px rgba(0,0,0,.4)}
.rbtn.fam-view{--acc:var(--cyan)}
.rbtn.fam-produce{--acc:var(--blue)}
.rbtn.fam-file{--acc:var(--fileblue)}
.rbtn.fam-alert{--acc:var(--red)}
.rail .spacer{flex:1}
.main{flex:1;min-width:0;display:flex;flex-direction:column;background:var(--bg)}
.page{display:none;flex:1;min-height:0;overflow:auto;padding:16px 20px 20px}
.page.show{display:block}
.page-head{display:flex;align-items:flex-end;justify-content:space-between;gap:16px;margin-bottom:14px}
.page-head h2{font-size:18px;font-weight:700}
.page-head .sub{color:var(--muted);margin-top:4px}
.filters{display:flex;flex-wrap:wrap;gap:8px;margin-bottom:12px}
.filters input,.filters select{
  background:var(--viewport);border:1px solid var(--line);border-radius:6px;color:var(--text);
  padding:7px 9px;font-size:12px;
}
.filters input{min-width:180px;font-family:var(--mono)}
table.jobs{width:100%;border-collapse:collapse;font-size:12.5px}
table.jobs th{
  text-align:left;font-size:10px;letter-spacing:.7px;text-transform:uppercase;color:var(--faint);
  font-weight:600;padding:8px 10px;border-bottom:1px solid var(--line);
}
table.jobs td{padding:9px 10px;border-bottom:1px solid var(--line2);vertical-align:middle}
table.jobs tr{cursor:pointer}
table.jobs tbody tr:hover{background:#1a1e24}
table.jobs .name{color:var(--cyan);font-weight:600}
.mono{font-family:var(--mono);font-size:11.5px;color:var(--muted)}
.badges{display:flex;gap:4px}
.chip{
  font-family:var(--mono);font-size:10px;padding:2px 7px;border-radius:4px;border:1px solid var(--line2);
  color:var(--muted);
}
.chip.ok{color:var(--green);border-color:rgba(52,211,153,.4);background:rgba(52,211,153,.08)}
.chip.bad{color:var(--red);border-color:rgba(255,93,93,.4);background:rgba(255,93,93,.08)}
.chip.wait{color:var(--cyan);border-color:rgba(57,192,240,.35);background:rgba(57,192,240,.08)}
.chip.warn{color:#ffb4b4;border-color:rgba(255,93,93,.5)}
.stuck-row{box-shadow:inset 3px 0 0 var(--red)}
.grid-2{display:grid;grid-template-columns:1.1fr .9fr;gap:16px}
.card{background:var(--chrome);border:1px solid var(--line);border-radius:10px;padding:14px 16px}
.drop{
  border:1px dashed var(--line);border-radius:8px;background:var(--viewport);padding:14px;
  min-height:78px;display:flex;flex-direction:column;justify-content:center;gap:4px;
}
.drop.has{border-style:solid;border-color:rgba(52,211,153,.35)}
.drop .fn{font-family:var(--mono);font-size:11px;color:var(--green)}
.check{display:flex;align-items:center;gap:8px;margin:10px 0 4px;color:var(--muted)}
.pkg-preview{background:var(--viewport);border-radius:8px;padding:12px;min-height:280px}
.pkg-preview .ph{
  height:180px;border-radius:6px;border:1px solid var(--line);background:
    repeating-linear-gradient(45deg,#14171c,#14171c 8px,#101318 8px,#101318 16px);
  display:grid;place-items:center;color:var(--faint);font-size:11px;
}
.split{display:grid;grid-template-columns:280px 1fr;gap:16px}
.timeline{list-style:none}
.timeline li{position:relative;padding:0 0 16px 18px;border-left:1px solid var(--line2)}
.timeline li:last-child{border-left-color:transparent;padding-bottom:0}
.timeline li::before{
  content:"";position:absolute;left:-5px;top:4px;width:9px;height:9px;border-radius:50%;
  background:var(--cyan);box-shadow:0 0 8px var(--cyan);
}
.timeline li.fail::before{background:var(--red);box-shadow:0 0 8px var(--red)}
.timeline li.ok::before{background:var(--green);box-shadow:0 0 8px var(--green)}
.checks{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin:12px 0}
.checkcard{background:var(--viewport);border:1px solid var(--line);border-radius:8px;padding:12px}
.checkcard .k{font-size:11px;color:var(--muted)}
.checkcard .v{font-size:20px;font-weight:700;margin-top:4px}
.checkcard.ok .v{color:var(--green)}
.checkcard.bad .v{color:var(--red)}
.art-list{display:flex;flex-direction:column;gap:6px}
.art{
  display:flex;align-items:center;justify-content:space-between;gap:8px;
  background:var(--viewport);border:1px solid var(--line2);border-radius:6px;padding:8px 10px;
}
.mail{width:100%;border-collapse:collapse;font-size:12px;margin-top:8px}
.mail th,.mail td{text-align:left;padding:7px 8px;border-bottom:1px solid var(--line2)}
.mail th{font-size:10px;letter-spacing:.7px;text-transform:uppercase;color:var(--faint)}
.statusstrip{
  height:26px;background:var(--chrome);border-top:1px solid var(--line);
  display:flex;align-items:center;gap:16px;padding:0 14px;font-size:11px;color:var(--muted);flex:none;
}
.statusstrip b{color:var(--text);font-weight:600}
</style>
</head>
<body>
<div id="login">
  <div class="login-card">
    <div class="head">
      <div class="brand-row">
        <svg viewBox="0 0 24 24"><path d="M12 2.2l8.4 4.8v9.6L12 21.4 3.6 16.6V6.8z" fill="url(#gBl)" stroke="#eaf1f8" stroke-width="1.1" stroke-linejoin="round"/><circle cx="12" cy="12" r="1.6" fill="url(#gGr)" stroke="#eaf1f8" stroke-width=".7"/></svg>
        <span>AC&amp;E</span>
      </div>
      <h1>Program Verification</h1>
      <p>Plant portal — submit a machining package, CSR_Server checks it, you get pass/fail and a PDF.</p>
    </div>
    <div class="body">
      <label class="fld"><span class="micro">Email</span><input id="em" type="email" value="demo@spirit.aero"></label>
      <label class="fld"><span class="micro">Password</span><input id="pw" type="password" value="demo"></label>
      <button class="btn btn-primary" type="button" onclick="enterApp()">Continue</button>
    </div>
  </div>
</div>
<svg xmlns="http://www.w3.org/2000/svg" width="0" height="0" style="position:absolute">
  <defs>
    <linearGradient id="gCy" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#6fc9f0"/><stop offset="1" stop-color="#1f9cd8"/></linearGradient>
    <linearGradient id="gBl" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#8aa9ef"/><stop offset="1" stop-color="#3862dd"/></linearGradient>
    <linearGradient id="gLb" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#4670c6"/><stop offset="1" stop-color="#1e3f86"/></linearGradient>
    <linearGradient id="gGr" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#77e8b0"/><stop offset="1" stop-color="#13b072"/></linearGradient>
    <linearGradient id="gRd" x1="0" y1="0" x2="0" y2="1"><stop offset="0" stop-color="#ff9090"/><stop offset="1" stop-color="#e03b3b"/></linearGradient>
  </defs>
</svg>
<div id="app">
  <div class="titlebar">
    <div class="logo">
      <svg viewBox="0 0 24 24"><path d="M12 2.2l8.4 4.8v9.6L12 21.4 3.6 16.6V6.8z" fill="url(#gBl)" stroke="#eaf1f8" stroke-width="1.1" stroke-linejoin="round"/><circle cx="12" cy="12" r="1.6" fill="url(#gGr)" stroke="#eaf1f8" stroke-width=".7"/></svg>
      Program Verification
    </div>
    <div class="appname">Spirit / Boeing plant</div>
    <div class="modebadge"><span class="d"></span>demo@spirit.aero</div>
    <div class="winbtns">— □ ×</div>
  </div>
  <div class="shell">
    <nav class="rail">
      <button class="rbtn fam-view active" id="nav-status" type="button" onclick="show('status')">
        <span class="ic"><svg viewBox="0 0 24 24"><path d="M4.2 5.2h15.6v13.6H4.2z" fill="url(#gCy)" stroke="#eaf1f8" stroke-width="1.05" stroke-linejoin="round"/><path d="M7 9h10M7 12.2h10M7 15.4h6" stroke="#eaf1f8" stroke-width="1.1" stroke-linecap="round"/></svg></span>
        Status
      </button>
      <button class="rbtn fam-produce" id="nav-submit" type="button" onclick="show('submit')">
        <span class="ic"><svg viewBox="0 0 24 24"><path d="M9.7 3.6h4.6v6.1h6.1v4.6h-6.1v6.1H9.7v-6.1H3.6V9.7h6.1z" fill="url(#gBl)" stroke="#eaf1f8" stroke-width="1" stroke-linejoin="round"/></svg></span>
        New job
      </button>
      <button class="rbtn fam-file" type="button" onclick="show('status')">
        <span class="ic"><svg viewBox="0 0 24 24"><path d="M5 2.8h8L17.2 7v12.6H5z" fill="url(#gLb)" stroke="#eaf1f8" stroke-width="1" stroke-linejoin="round"/><path d="M13 2.8V7h4.2" fill="none" stroke="#eaf1f8" stroke-width=".95"/></svg></span>
        Package
      </button>
      <div class="spacer"></div>
      <button class="rbtn fam-alert" type="button" onclick="logout()">
        <span class="ic"><svg viewBox="0 0 24 24"><path d="M12 3.2v8.6" stroke="url(#gRd)" stroke-width="2.7" stroke-linecap="round"/><path d="M6.8 7a7.6 7.6 0 1 0 10.4 0" fill="none" stroke="url(#gRd)" stroke-width="2.7" stroke-linecap="round"/></svg></span>
        Sign out
      </button>
    </nav>
    <div class="main">
      <section class="page show" id="page-status">
        <div class="page-head">
          <div>
            <div class="micro">Home</div>
            <h2>Status</h2>
            <div class="sub">Past runs, live jobs, reports. Newest first.</div>
          </div>
          <button class="btn btn-primary" style="width:auto" type="button" onclick="show('submit')">New verification</button>
        </div>
        <div class="filters">
          <input placeholder="Project / part contains…">
          <select><option>All states</option><option>queued</option><option>verifying</option><option>complete</option><option>failed</option></select>
          <select><option>All results</option><option>pass</option><option>fail</option><option>unknown</option></select>
        </div>
        <table class="jobs">
          <thead>
            <tr><th>Project</th><th>Submitted</th><th>State</th><th>Probe / drill / trim</th><th>Shots</th><th>PDF</th><th>Mail</th></tr>
          </thead>
          <tbody>
            <tr class="stuck-row" onclick="openJob('stuck')">
              <td class="name">Door surround — DS-441</td>
              <td class="mono">Aug 27 08:12</td>
              <td><span class="chip warn">verifying · stuck</span></td>
              <td><div class="badges"><span class="chip">n/a</span><span class="chip">n/a</span><span class="chip">n/a</span></div></td>
              <td class="mono">2</td>
              <td class="mono">—</td>
              <td class="chip wait">queued</td>
            </tr>
            <tr onclick="openJob('cowl-fail')">
              <td class="name">Cowl 4 — WK061725</td>
              <td class="mono">Aug 27 15:19</td>
              <td><span class="chip bad">complete</span></td>
              <td><div class="badges"><span class="chip ok">probe</span><span class="chip bad">drill</span><span class="chip ok">trim</span></div></td>
              <td class="mono">1</td>
              <td class="chip ok">PDF</td>
              <td class="chip ok">sent</td>
            </tr>
            <tr onclick="openJob('pass')">
              <td class="name">Spar cap — SC-19</td>
              <td class="mono">Aug 26 11:04</td>
              <td><span class="chip ok">complete</span></td>
              <td><div class="badges"><span class="chip ok">probe</span><span class="chip ok">drill</span><span class="chip ok">trim</span></div></td>
              <td class="mono">3</td>
              <td class="chip ok">PDF</td>
              <td class="chip ok">sent</td>
            </tr>
            <tr>
              <td class="name">Floor grid — FG-02</td>
              <td class="mono">Aug 26 09:40</td>
              <td><span class="chip wait">queued</span></td>
              <td><div class="badges"><span class="chip">n/a</span><span class="chip">n/a</span><span class="chip">n/a</span></div></td>
              <td class="mono">1</td>
              <td class="mono">—</td>
              <td class="chip wait">received</td>
            </tr>
          </tbody>
        </table>
      </section>
      <section class="page" id="page-submit">
        <div class="page-head">
          <div>
            <div class="micro">Submit</div>
            <h2>New verification</h2>
            <div class="sub">Package lands in the SMB inbox. CSR_Server is not started on this click.</div>
          </div>
        </div>
        <div class="grid-2">
          <div class="card">
            <label class="fld"><span class="micro">Project / part name</span><input value="Cowl 4 — WK061725"></label>
            <label class="fld"><span class="micro">Notify emails</span><input value="demo@spirit.aero"></label>
            <div class="micro" style="margin:4px 0 8px">Artifacts</div>
            <div class="drop has"><span class="micro">CATPart</span><span class="fn">cowl.CATPart</span></div>
            <div class="drop has" style="margin-top:8px"><span class="micro">RMCD program</span><span class="fn">Test Case 4 Code.rmcd</span></div>
            <div class="drop has" style="margin-top:8px"><span class="micro">Tool list</span><span class="fn">tool_list.txt · T8 / T12 / T16</span></div>
            <div class="drop has" style="margin-top:8px"><span class="micro">Engineering tool request</span><span class="fn">Engineering Tool Request WK061725_V4.pdf</span></div>
            <div class="drop has" style="margin-top:8px"><span class="micro">Annotated screenshot</span><span class="fn">Cowl_WK061725_View 1 annotated.jpg</span></div>
            <label class="check"><input type="checkbox"> No visual exclusions</label>
            <button class="btn btn-primary" style="margin-top:12px" type="button" onclick="openJob('cowl-fail')">Submit package</button>
          </div>
          <div class="card">
            <div class="micro">Golden package preview</div>
            <div class="pkg-preview" style="margin-top:10px">
              <div class="ph">Annotated Cowl view (testdata/cowl-4-golden)</div>
              <p style="color:var(--muted);margin-top:10px;line-height:1.5">ETR: bottom 0.500" first ten holes from yellow origin, skip red-box holes; top 0.625" all except last five in the red box.</p>
            </div>
          </div>
        </div>
      </section>
      <section class="page" id="page-detail">
        <div class="page-head">
          <div>
            <div class="micro" id="d-kicker">Job</div>
            <h2 id="d-title">Cowl 4 — WK061725</h2>
            <div class="sub mono" id="d-id">job 7a55f48c · /jobs/7a55f48c</div>
          </div>
          <div style="display:flex;gap:8px">
            <button class="btn btn-green" type="button">Download PDF</button>
            <button class="btn btn-ghost" type="button" onclick="show('status')">Back to status</button>
          </div>
        </div>
        <div class="split">
          <div class="card">
            <div class="micro">Timeline</div>
            <ul class="timeline" id="d-tl" style="margin-top:12px"></ul>
          </div>
          <div>
            <div class="checks" id="d-checks"></div>
            <div class="card">
              <div class="micro">Package</div>
              <div class="art-list" id="d-arts" style="margin-top:10px"></div>
            </div>
            <div class="card" style="margin-top:12px">
              <div style="display:flex;justify-content:space-between;align-items:center">
                <div class="micro">Email log</div>
                <button class="btn btn-green" style="padding:6px 10px" type="button">Request quality review</button>
              </div>
              <table class="mail" id="d-mail"></table>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
  <div class="statusstrip">
    <span>Jobs <b>4</b></span>
    <span>Verifying <b>1</b></span>
    <span>Stuck <b style="color:var(--red)">1</b></span>
    <span>CSR_Server · SMB inbox</span>
    <span style="margin-left:auto;font-family:var(--mono)">https://progverif.plant.local</span>
  </div>
</div>
<script>
const JOBS = {
  'cowl-fail': {
    title: 'Cowl 4 — WK061725', id: '7a55f48c', kicker: 'complete · overall fail',
    checks: [{k:'Probe', v:'valid', cls:'ok'},{k:'Drill', v:'failed', cls:'bad'},{k:'Trim', v:'valid', cls:'ok'}],
    tl: [
      {t:'submitted', d:'15:19:31  package accepted', cls:''},
      {t:'queued', d:'15:19:33  inbox complete', cls:''},
      {t:'verifying', d:'15:19:41  CSR_Server lock', cls:''},
      {t:'complete', d:'15:22:04  drill failed checks', cls:'fail'}
    ],
    mail: [['job.received','demo@spirit.aero','sent'],['job.complete.fail','demo@spirit.aero, quality@spirit.aero','sent']]
  },
  pass: {
    title: 'Spar cap — SC-19', id: 'b4c0de12', kicker: 'complete · overall pass',
    checks: [{k:'Probe', v:'valid', cls:'ok'},{k:'Drill', v:'valid', cls:'ok'},{k:'Trim', v:'valid', cls:'ok'}],
    tl: [
      {t:'submitted', d:'11:04:02  package accepted', cls:''},
      {t:'queued', d:'11:04:05  inbox complete', cls:''},
      {t:'verifying', d:'11:04:11  CSR_Server lock', cls:''},
      {t:'complete', d:'11:07:40  all Test Result valid', cls:'ok'}
    ],
    mail: [['job.received','demo@spirit.aero','sent'],['job.complete.pass','demo@spirit.aero','sent']]
  },
  stuck: {
    title: 'Door surround — DS-441', id: 'ee22e73c', kicker: 'verifying · stuck (SLA 4h)',
    checks: [{k:'Probe', v:'n/a', cls:''},{k:'Drill', v:'n/a', cls:''},{k:'Trim', v:'n/a', cls:''}],
    tl: [
      {t:'submitted', d:'08:12:10  package accepted', cls:''},
      {t:'queued', d:'08:12:14  inbox complete', cls:''},
      {t:'verifying', d:'08:12:20  waiting on CSR_Server', cls:'fail'}
    ],
    mail: [['job.received','demo@spirit.aero','sent'],['job.stuck','ops@spirit.aero','sent']]
  }
};
function enterApp(){
  document.getElementById('login').style.display='none';
  document.getElementById('app').classList.add('show');
  show('status');
}
function logout(){
  document.getElementById('app').classList.remove('show');
  document.getElementById('login').style.display='flex';
}
function show(name){
  document.querySelectorAll('.page').forEach(function(p){ p.classList.remove('show'); });
  document.getElementById('page-'+name).classList.add('show');
  document.querySelectorAll('.rail .rbtn').forEach(function(b){ b.classList.remove('active'); });
  var nav = document.getElementById('nav-'+name);
  if(nav) nav.classList.add('active');
}
function openJob(key){
  var j = JOBS[key];
  document.getElementById('d-title').textContent = j.title;
  document.getElementById('d-id').textContent = 'job '+j.id+' · /jobs/'+j.id;
  document.getElementById('d-kicker').textContent = j.kicker;
  document.getElementById('d-tl').innerHTML = j.tl.map(function(x){ return '<li class="'+x.cls+'"><div class="micro">'+x.t+'</div><div>'+x.d+'</div></li>'; }).join('');
  document.getElementById('d-checks').innerHTML = j.checks.map(function(c){ return '<div class="checkcard '+c.cls+'"><div class="k">'+c.k+'</div><div class="v">'+c.v+'</div></div>'; }).join('');
  document.getElementById('d-arts').innerHTML = ['cowl.CATPart','Test Case 4 Code.rmcd','tool_list.txt','Engineering Tool Request WK061725_V4.pdf','Cowl_WK061725_View 1 annotated.jpg','ace_verification_results.txt'].map(function(n){ return '<div class="art"><span class="mono">'+n+'</span><span class="chip">download</span></div>'; }).join('');
  document.getElementById('d-mail').innerHTML = '<tr><th>Event</th><th>To</th><th>State</th></tr>'+j.mail.map(function(r){ return '<tr><td class="mono">'+r[0]+'</td><td>'+r[1]+'</td><td class="chip ok">'+r[2]+'</td></tr>'; }).join('');
  show('detail');
  document.querySelectorAll('.rail .rbtn').forEach(function(b){ b.classList.remove('active'); });
}
</script>
</body>
</html>
