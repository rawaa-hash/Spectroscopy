<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Laser Spectroscopy — Lecture Notebook</title>
<meta name="description" content="Laser Spectroscopy M.Sc. lecture notebook — Institute of Laser for Postgraduate Studies, University of Baghdad">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@400;500;600;700&family=IBM+Plex+Serif:wght@400;600&family=IBM+Plex+Mono:wght@400;500;600&family=Noto+Naskh+Arabic:wght@400;600&display=swap" rel="stylesheet">
<style>
:root{
  --paper:#FCFBF9; --ink:#15181E; --muted:#5A6270; --line:#E6E2DA; --line2:#CFCABE;
  --indigo:#4338CA; --indigo-s:#EEF0FE;
  --teal:#0E7490;   --teal-s:#E4F4F8;
  --emerald:#047857;--emerald-s:#E3F5EC;
  --amber:#B45309;  --amber-s:#FDF3E2;
  --rose:#BE123C;   --rose-s:#FDECEF;
  --violet:#6D28D9; --violet-s:#F3EDFE;
  --sky:#0369A1;    --sky-s:#E6F2FB;
  --sans:"IBM Plex Sans","Segoe UI",system-ui,sans-serif;
  --serif:"IBM Plex Serif",Georgia,serif;
  --mono:"IBM Plex Mono",ui-monospace,Menlo,monospace;
  --ar:"Noto Naskh Arabic",serif;
  --body:var(--sans); --fs:100%;
}
:root{ --violet:#6D28D9 }
*{box-sizing:border-box}
html{font-size:var(--fs);scroll-behavior:smooth}
body{margin:0;background:var(--paper);color:var(--ink);font-family:var(--body);font-size:1rem;line-height:1.8;-webkit-text-size-adjust:100%}
.wrap{max-width:880px;margin:0 auto;padding:0 18px 90px}
a{color:var(--teal)}
.ar{font-family:var(--ar);direction:rtl;unicode-bidi:isolate}
.mono{font-family:var(--mono)}

/* ---------- bar ---------- */
.bar{position:sticky;top:0;z-index:50;background:rgba(252,251,249,.94);backdrop-filter:blur(10px);border-bottom:1px solid var(--line)}
.bar-in{max-width:880px;margin:0 auto;padding:9px 18px;display:flex;align-items:center;gap:10px}
.bar-in b{font-size:14.5px;font-weight:600;flex:1;overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.tool{border:1px solid var(--line2);background:#fff;color:var(--ink);border-radius:9px;padding:6px 12px;font-family:var(--sans);font-size:13px;cursor:pointer}
.tool:hover{background:#F3F0EA}

/* ---------- rail ---------- */
.rail{position:sticky;top:47px;z-index:40;background:rgba(252,251,249,.96);border-bottom:1px solid var(--line)}
.rail-in{max-width:880px;margin:0 auto;padding:8px 18px;display:flex;gap:6px;overflow-x:auto;scrollbar-width:none}
.rail-in::-webkit-scrollbar{display:none}
.rail-in a{flex:0 0 auto;width:40px;height:46px;border-radius:11px;border:1px solid var(--line2);background:#fff;
  display:flex;flex-direction:column;align-items:center;justify-content:center;gap:1px;text-decoration:none;
  color:var(--muted);font-size:14px;font-weight:600;font-family:var(--mono)}
.rail-in a small{font-size:8px;font-weight:400;letter-spacing:.04em}
.rail-in a.ready{color:#fff}
.rail-in a:hover{transform:translateY(-1px)}

/* ---------- cover ---------- */
.cover{border:1px solid var(--line);border-radius:18px;background:#fff;overflow:hidden;margin:22px 0 10px}
.cover .band{height:9px;background:linear-gradient(90deg,#4338CA,#0E7490,#047857,#B45309,#BE123C)}
.cover .in{padding:22px}
.cover .sup{font-size:12px;color:var(--muted);margin:0 0 6px;letter-spacing:.03em;text-transform:uppercase}
.cover h1{margin:0 0 6px;font-size:26px;line-height:1.3;font-weight:700;font-family:var(--serif)}
.cover .tag{font-size:14px;color:var(--muted);margin:0 0 16px}
.cover dl{display:grid;grid-template-columns:auto 1fr;gap:5px 18px;margin:0;font-size:14.5px}
.cover dt{color:var(--muted);font-size:12.5px;text-transform:uppercase;letter-spacing:.03em}
.cover dd{margin:0}
.blank{display:inline-block;min-width:180px;border-bottom:1px dotted var(--line2)}
.gate{display:flex;align-items:center;gap:12px;margin-top:18px;border:1px solid var(--teal);border-radius:12px;
  background:var(--teal-s);padding:12px 14px;text-decoration:none;color:var(--ink)}
.gate b{display:block;font-size:14.5px;color:var(--teal)}
.gate span{font-size:12.5px;color:var(--muted)}

/* ---------- week ---------- */
.week{margin-top:46px;scroll-margin-top:112px}
.week .hd{border-radius:14px;padding:16px 18px;color:#fff;margin-bottom:20px}
.week .hd .no{font-family:var(--mono);font-size:11.5px;opacity:.85;letter-spacing:.1em}
.week .hd h2{margin:3px 0 6px;font-size:23px;line-height:1.3;font-weight:700;font-family:var(--serif)}
.week .hd p{margin:0;font-size:14.5px;opacity:.93;max-width:64ch}
.soon{border:1px dashed var(--line2);border-radius:14px;padding:28px;text-align:center;color:var(--muted);font-size:14.5px;background:#fff}

/* ---------- sections ---------- */
h3.s{display:flex;align-items:center;gap:11px;margin:34px 0 12px;font-size:18px;font-weight:700;font-family:var(--serif)}
h3.s i{font-style:normal;font-family:var(--mono);font-size:13px;color:#fff;width:26px;height:26px;border-radius:8px;
  display:grid;place-items:center;flex:0 0 26px}
h4.t{margin:24px 0 8px;font-size:15px;font-weight:600}
p{margin:0 0 13px}
ul.p,ol.p{margin:0 0 14px;padding-left:22px}
ul.p li,ol.p li{margin-bottom:6px}
ul.chk{list-style:none;margin:0 0 14px;padding:0}
ul.chk li{position:relative;padding-left:28px;margin-bottom:9px;font-size:15px}
ul.chk li::before{content:"✔";position:absolute;left:0;top:0;color:var(--emerald);font-size:13px;font-weight:700}

/* equations */
.eq{font-family:var(--mono);font-size:13.5px;background:#fff;border:1px solid var(--line);
  border-left:3px solid var(--indigo);border-radius:8px;padding:11px 14px;margin:12px 0;overflow-x:auto;white-space:nowrap}
.eq b{float:right;color:var(--muted);font-weight:400;font-size:11.5px;padding-left:14px}

/* callouts */
.call{border-radius:13px;padding:14px 16px;margin:18px 0;border:1px solid}
.call .lbl{font-family:var(--mono);font-size:11px;letter-spacing:.09em;text-transform:uppercase;margin:0 0 7px;font-weight:600}
.call p:last-child{margin-bottom:0}
.call ol,.call ul{margin:8px 0 0;padding-left:20px}
.call li{margin-bottom:5px;font-size:14.5px}
.key{background:var(--indigo-s);border-color:#CBD2FB}    .key .lbl{color:var(--indigo)}
.warn{background:var(--amber-s);border-color:#EFD9AE}    .warn .lbl{color:var(--amber)}
.ex{background:var(--violet-s);border-color:#D9C9FA}     .ex .lbl{color:var(--violet)}
.try{background:var(--emerald-s);border-color:#B9E3CC}   .try .lbl{color:var(--emerald)}
.lab{background:var(--sky-s);border-color:#BEDCF2}       .lab .lbl{color:var(--sky)}
.res{margin-top:10px;padding-top:9px;border-top:1px dashed rgba(0,0,0,.14);font-size:14px}

/* ✗ / ✓ contrast */
.vs{display:grid;grid-template-columns:1fr 1fr;gap:11px;margin:18px 0}
.vs>div{border-radius:12px;padding:13px 15px;border:1px solid;font-size:14.5px}
.vs .bad{background:var(--rose-s);border-color:#F2C9D2}
.vs .good{background:var(--emerald-s);border-color:#B9E3CC}
.vs .mark{font-family:var(--mono);font-weight:700;font-size:13px;display:block;margin-bottom:5px}
.vs .bad .mark{color:var(--rose)} .vs .good .mark{color:var(--emerald)}
@media(max-width:600px){.vs{grid-template-columns:1fr}}

/* figures */
figure{margin:20px 0;border:1px solid var(--line);border-radius:14px;background:#0C1024;padding:15px}
figure svg{width:100%;height:auto;display:block}
figcaption{margin:11px 2px 0;font-size:12.5px;color:#9AA2C8;line-height:1.7}

/* tables */
.scroll{overflow-x:auto;margin:14px 0}
table{width:100%;border-collapse:collapse;font-size:14px;background:#fff;border:1px solid var(--line);border-radius:12px;overflow:hidden}
th{background:var(--indigo-s);color:var(--indigo);font-size:12px;font-weight:600;letter-spacing:.03em;text-transform:uppercase;
  text-align:left;padding:10px 10px;border-bottom:1px solid var(--line)}
td{padding:9px 10px;border-bottom:1px solid var(--line)}
tbody tr:nth-child(even){background:#FAF9F6}
tbody tr:last-child td{border-bottom:none}
td.m{font-family:var(--mono);font-size:13px}

/* glossary */
.gloss{background:#fff;border:1px solid var(--line);border-radius:13px;padding:4px 16px;margin:14px 0}
.gloss div{padding:11px 0;border-bottom:1px solid var(--line);font-size:14.5px;display:flex;gap:12px;flex-wrap:wrap;align-items:baseline}
.gloss div:last-child{border-bottom:none}
.gloss b{font-weight:600;flex:0 0 auto}
.gloss .ar{color:var(--teal);font-size:14px;flex:0 0 auto}
.gloss em{font-style:normal;color:var(--muted);font-size:13.5px;flex:1 1 220px}

/* questions */
.q{margin:0 0 20px;display:flex;gap:12px}
.q .n{flex:0 0 26px;height:26px;border-radius:50%;background:var(--indigo-s);color:var(--indigo);
  display:grid;place-items:center;font-family:var(--mono);font-size:12px;font-weight:600}
.q .body{flex:1;min-width:0}
.q p.stem{margin:0 0 8px;font-size:15px;font-weight:500}
.q ol{margin:0;padding-left:22px}
.q ol li{margin-bottom:4px;font-size:14.5px}
.lines{border-bottom:1px dotted var(--line2);height:27px;margin-top:7px}
.tf{display:flex;justify-content:space-between;gap:14px;align-items:baseline;padding:11px 0;border-bottom:1px dotted var(--line2);font-size:14.5px}
.tf span{flex:0 0 auto;font-family:var(--mono);font-size:12px;color:var(--muted)}

/* homework */
.hw{border:1px solid var(--line);border-left:4px solid var(--teal);border-radius:12px;background:#fff;padding:14px 16px;margin-bottom:11px}
.hw .top{display:flex;justify-content:space-between;align-items:baseline;gap:10px}
.hw h4{margin:0;font-size:15px;font-weight:600}
.hw .lvl{font-size:11px;border-radius:999px;padding:3px 10px;flex:0 0 auto;font-family:var(--mono);letter-spacing:.04em}
.lvl.b{background:var(--emerald-s);color:var(--emerald)}
.lvl.i{background:var(--amber-s);color:var(--amber)}
.lvl.a{background:var(--rose-s);color:var(--rose)}
.hw p{margin:9px 0 0;font-size:14.5px}
.hw .due{margin-top:10px;padding-top:9px;border-top:1px solid var(--line);font-size:13.5px}
.hw .due b{color:var(--teal)}

.navw{display:flex;justify-content:space-between;margin-top:26px;font-size:14px}
.endnote{text-align:center;color:var(--muted);font-size:13px;margin-top:32px;padding-top:16px;border-top:1px solid var(--line)}

/* font panel */
.fab{position:fixed;right:16px;bottom:16px;z-index:60;border-radius:999px;width:46px;height:46px;background:var(--ink);
  color:#fff;border:none;font-size:16px;cursor:pointer;box-shadow:0 4px 14px rgba(0,0,0,.18)}
.panel{position:fixed;right:16px;bottom:72px;z-index:60;background:#fff;border:1px solid var(--line2);border-radius:14px;
  padding:15px;width:240px;box-shadow:0 8px 26px rgba(0,0,0,.14);display:none}
.panel.on{display:block}
.panel h5{margin:0 0 3px;font-size:14.5px}
.panel p{margin:0 0 12px;font-size:12px;color:var(--muted);line-height:1.6}
.panel label{display:block;font-size:11.5px;color:var(--muted);margin:10px 0 5px;text-transform:uppercase;letter-spacing:.04em}
.opts{display:flex;gap:6px}
.opts button{flex:1;border:1px solid var(--line2);background:#fff;border-radius:8px;padding:7px 4px;font-size:13px;cursor:pointer;font-family:var(--sans)}
.opts button.on{border-color:var(--indigo);background:var(--indigo-s);color:var(--indigo)}
.size{display:flex;align-items:center;gap:8px}
.size button{width:34px;height:32px;border:1px solid var(--line2);background:#fff;border-radius:8px;font-size:15px;cursor:pointer}
.size span{flex:1;text-align:center;font-family:var(--mono);font-size:13px}

footer{text-align:center;color:var(--muted);font-size:12.5px;padding:24px 18px;border-top:1px solid var(--line)}

@media print{
  .bar,.rail,.fab,.panel,.gate{display:none!important}
  body{background:#fff;font-size:10.5pt;line-height:1.65}
  .wrap{max-width:none;padding:0}
  .week{page-break-before:always}
  .week:first-of-type{page-break-before:auto}
  .week .hd{color:#000;background:#fff!important;border:1.5pt solid #000;border-radius:0}
  .call,.hw,.gloss,.vs,figure,table{break-inside:avoid}
  figure{background:#fff;border-color:#bbb}
  figcaption{color:#444}
  a{color:#000;text-decoration:none}
}
@media(max-width:560px){.cover h1{font-size:22px}.week .hd h2{font-size:20px}}
</style>
</head>
<body>

<div class="bar">
  <div class="bar-in">
    <b>Laser Spectroscopy — Lecture Notebook</b>
    <button class="tool" onclick="window.print()">🖨 Print / PDF</button>
  </div>
</div>

<div class="rail"><div class="rail-in" id="rail"></div></div>

<div class="wrap">

<div class="cover">
  <div class="band"></div>
  <div class="in">
    <p class="sup">Republic of Iraq — Ministry of Higher Education and Scientific Research</p>
    <h1>Laser Spectroscopy</h1>
    <p class="tag">M.Sc. Programme · 3 Credit Hours · 15 Weeks · Lecture Notebook</p>
    <dl>
      <dt>Student</dt><dd><span class="blank"></span></dd>
      <dt>Institute</dt><dd>Institute of Laser for Postgraduate Studies — University of Baghdad</dd>
      <dt>Instructor</dt><dd>Asst. Prof. Dr. Rawaa Ahmed Faris</dd>
      <dt>Year</dt><dd>2026</dd>
    </dl>
    <a class="gate" href="pt/index.html">
      <div><b>Course platform →</b><span>Assignments · Grades · Announcements</span></div>
    </a>
  </div>
</div>

<!-- ===================== WEEK 1 ===================== -->
<section class="week" id="w1">
  <div class="hd" style="background:linear-gradient(120deg,#4338CA,#6D28D9)">
    <p class="no">WEEK 01</p>
    <h2>Foundations of Spectroscopy</h2>
    <p>Where a spectrum comes from, and how to read its position, intensity and shape. This lecture builds the base that every technique in the course stands on: spectroscopic units, the three Einstein processes, transition probability and selection rules.</p>
  </div>

  <div class="call key">
    <p class="lbl">Learning outcomes</p>
    <ul>
      <li>Convert fluently between nm, cm⁻¹, eV, THz and joules, and pick the unit that suits a spectral region.</li>
      <li>Derive the relations between the Einstein A and B coefficients from thermal equilibrium.</li>
      <li>Explain why spontaneous emission dominates in the optical region and stimulated emission in the microwave.</li>
      <li>Relate the transition dipole moment, A₂₁, oscillator strength and radiative lifetime.</li>
      <li>Apply electric-dipole selection rules to decide whether a transition is allowed.</li>
    </ul>
  </div>

  <h3 class="s"><i style="background:#4338CA">1</i>What a spectrum actually tells you</h3>
  <p>Spectroscopy measures how the exchange of energy between electromagnetic radiation and matter depends on frequency. Every spectrum answers three questions at once, and a good experiment is designed around the one you actually need.</p>
  <ul class="chk">
    <li><b>Line position</b> — energy-level structure, molecular geometry, chemical identity.</li>
    <li><b>Line intensity</b> — transition probability multiplied by the number of absorbers or emitters. This is the basis of all quantitative analysis.</li>
    <li><b>Line shape</b> — lifetime, temperature, pressure, velocity distribution and local fields. The whole of Week 3.</li>
  </ul>
  <p>The resonance condition is the same throughout the course:</p>
  <div class="eq"><b>(1.1)</b>h ν = E₂ − E₁ = ΔE</div>

  <figure><svg viewBox='0 0 720 150' xmlns='http://www.w3.org/2000/svg'><defs><linearGradient id='vis' x1='0' x2='1'><stop offset='0' stop-color='#7B2FF7'/><stop offset='.25' stop-color='#22C3D6'/><stop offset='.5' stop-color='#4ADE80'/><stop offset='.75' stop-color='#F5B301'/><stop offset='1' stop-color='#F2545B'/></linearGradient></defs><g font-family='IBM Plex Mono, monospace' text-anchor='middle'><rect x='40' y='52' width='92' height='24' fill='#4C1D95'/><rect x='132' y='52' width='92' height='24' fill='#6D28D9'/><rect x='224' y='52' width='92' height='24' fill='#4361EE'/><rect x='316' y='52' width='92' height='24' fill='url(#vis)'/><rect x='408' y='52' width='92' height='24' fill='#F59029'/><rect x='500' y='52' width='92' height='24' fill='#D93B62'/><rect x='592' y='52' width='92' height='24' fill='#7F1D3A'/><g font-size='11' fill='#E9EBF7'><text x='86' y='44'>gamma</text><text x='178' y='44'>X-ray</text><text x='270' y='44'>UV</text><text x='362' y='44'>visible</text><text x='454' y='44'>IR</text><text x='546' y='44'>microwave</text><text x='638' y='44'>radio</text></g><g font-size='9.5' fill='#9AA2C8'><text x='86' y='92'>&lt; 10 pm</text><text x='178' y='92'>0.01-10 nm</text><text x='270' y='92'>10-380 nm</text><text x='362' y='92'>380-750 nm</text><text x='454' y='92'>0.75-1000 um</text><text x='546' y='92'>1 mm - 30 cm</text><text x='638' y='92'>&gt; 30 cm</text></g><g font-size='9.5' fill='#6E77A0'><text x='86' y='112'>nuclear</text><text x='178' y='112'>inner shells</text><text x='270' y='112'>valence e-</text><text x='362' y='112'>valence e-</text><text x='454' y='112'>vibrations</text><text x='546' y='112'>rotations</text><text x='638' y='112'>spin (NMR)</text></g><g font-size='9.5' fill='#6E77A0'><text x='86' y='128'>MeV</text><text x='178' y='128'>keV</text><text x='270' y='128'>3-100 eV</text><text x='362' y='128'>1.6-3.3 eV</text><text x='454' y='128'>meV - eV</text><text x='546' y='128'>ueV</text><text x='638' y='128'>neV</text></g><line x1='40' y1='138' x2='684' y2='138' stroke='#2A3260'/><text x='362' y='18' font-size='10.5' fill='#22C3D6'>increasing photon energy   &#8592;</text></g></svg><figcaption>Figure 1.1 — Regions of the electromagnetic spectrum and the class of transition each one probes. This course lives between the far-IR and the near-UV, where tunable laser sources exist.</figcaption></figure>

  <div class="call key">
    <p class="lbl">Key idea</p>
    <p>Choosing a spectral region <b>is</b> choosing which degree of freedom of the sample you interrogate. Rotations need microwaves, vibrations the mid-IR, valence electrons the visible and UV. There is no such thing as a general-purpose spectrometer.</p>
  </div>

  <h3 class="s"><i style="background:#0E7490">2</i>Spectroscopic units and conversions</h3>
  <p>The wavenumber is preferred in atomic and vibrational spectroscopy because it is directly proportional to energy, so differences may be subtracted directly. That is not true of wavelength.</p>
  <div class="eq"><b>(1.2)</b>ν̃ [cm⁻¹] = 1 / λ[cm] = 10⁷ / λ[nm]</div>
  <div class="eq"><b>(1.3)</b>E [eV] = 1239.84 / λ[nm]</div>
  <div class="eq"><b>(1.4)</b>ν [THz] = 299792.458 / λ[nm]</div>

  <div class="scroll">
  <table>
    <thead><tr><th>Quantity</th><th>in eV</th><th>in cm⁻¹</th><th>in frequency</th></tr></thead>
    <tbody>
      <tr><td class="m">1 eV</td><td class="m">1</td><td class="m">8065.54</td><td class="m">241.799 THz</td></tr>
      <tr><td class="m">1 cm⁻¹</td><td class="m">1.23984×10⁻⁴</td><td class="m">1</td><td class="m">29.9792 GHz</td></tr>
      <tr><td class="m">1 THz</td><td class="m">4.13567×10⁻³</td><td class="m">33.356</td><td class="m">1 THz</td></tr>
      <tr><td class="m">kT at 300 K</td><td class="m">25.85 meV</td><td class="m">208.5</td><td class="m">6.25 THz</td></tr>
      <tr><td class="m">kT at 10 000 K</td><td class="m">0.862</td><td class="m">6952</td><td class="m">208 THz</td></tr>
    </tbody>
  </table>
  </div>

  <div class="vs">
    <div class="bad">
      <span class="mark">✗ Common mistake</span>
      A Raman shift of 1000 cm⁻¹ from 632.8 nm is <b>not</b> at 632.8 − something in nanometres. Subtracting wavelengths has no physical meaning, because wavelength is not linear in energy.
    </div>
    <div class="good">
      <span class="mark">✓ Correct</span>
      Convert first: 10⁷/632.8 = 15802.8 cm⁻¹. Subtract in wavenumbers: 15802.8 − 1000 = 14802.8 cm⁻¹. Convert back: 675.5 nm.
    </div>
  </div>

  <div class="call ex">
    <p class="lbl">Worked example 1.1</p>
    <p>Express the He–Ne laser line at 632.8 nm in cm⁻¹, eV, THz and joules.</p>
    <ol>
      <li>ν̃ = 10⁷ / 632.8 = 15802.8 cm⁻¹</li>
      <li>E = 1239.84 / 632.8 = 1.9594 eV</li>
      <li>ν = 299792.458 / 632.8 = 473.76 THz</li>
      <li>E = 1.9594 × 1.602177×10⁻¹⁹ = 3.139×10⁻¹⁹ J</li>
    </ol>
  </div>

  <div class="call warn">
    <p class="lbl">Remember two anchors</p>
    <p><b>1240 eV·nm</b> and <b>kT = 208 cm⁻¹ at room temperature</b>. From these you can rebuild every conversion under exam conditions, and the second tells you immediately which states are thermally populated.</p>
  </div>

  <h3 class="s"><i style="background:#047857">3</i>The three Einstein processes</h3>
  <p>Take a two-level system with energies E₁ and E₂, degeneracies g₁ and g₂ and populations N₁ and N₂, immersed in a radiation field of spectral energy density ρ(ν). Einstein showed in 1917 that three elementary processes are needed for consistency with thermodynamics.</p>

  <figure><svg viewBox='0 0 720 215' xmlns='http://www.w3.org/2000/svg'><g stroke='#E9EBF7' stroke-width='2'><line x1='45' y1='150' x2='195' y2='150'/><line x1='45' y1='62' x2='195' y2='62'/><line x1='265' y1='150' x2='415' y2='150'/><line x1='265' y1='62' x2='415' y2='62'/><line x1='485' y1='150' x2='635' y2='150'/><line x1='485' y1='62' x2='635' y2='62'/></g><defs><marker id='ah' markerWidth='7' markerHeight='7' refX='6' refY='3' orient='auto'><path d='M0,0 L7,3 L0,6 z' fill='#22C3D6'/></marker><marker id='ag' markerWidth='7' markerHeight='7' refX='6' refY='3' orient='auto'><path d='M0,0 L7,3 L0,6 z' fill='#F5B301'/></marker></defs><line x1='120' y1='150' x2='120' y2='70' stroke='#22C3D6' stroke-width='2' marker-end='url(#ah)'/><line x1='340' y1='62' x2='340' y2='142' stroke='#F5B301' stroke-width='2' marker-end='url(#ag)'/><line x1='560' y1='62' x2='560' y2='142' stroke='#F5B301' stroke-width='2' marker-end='url(#ag)'/><g stroke='#4ADE80' stroke-width='1.8' fill='none'><path d='M55,190 q6,-8 12,0 t12,0 t12,0' /><path d='M275,190 q6,-8 12,0 t12,0 t12,0'/><path d='M470,190 q6,-8 12,0 t12,0 t12,0'/><path d='M560,190 q6,-8 12,0 t12,0 t12,0'/><path d='M600,190 q6,-8 12,0 t12,0 t12,0'/></g><g font-family='IBM Plex Mono, monospace' font-size='10.5' fill='#9AA2C8'><text x='50' y='58'>E2, N2, g2</text><text x='50' y='168'>E1, N1, g1</text><text x='95' y='205' fill='#4ADE80'>in</text><text x='315' y='205' fill='#4ADE80'>out (random)</text><text x='505' y='205' fill='#4ADE80'>in + 2 out (coherent)</text></g><g font-family='IBM Plex Mono, monospace' font-size='11.5' fill='#E9EBF7' text-anchor='middle'><text x='120' y='30'>absorption</text><text x='340' y='30'>spontaneous</text><text x='560' y='30'>stimulated</text></g><g font-family='IBM Plex Mono, monospace' font-size='11' fill='#22C3D6' text-anchor='middle'><text x='120' y='46'>B12 rho(v) N1</text><text x='340' y='46'>A21 N2</text><text x='560' y='46'>B21 rho(v) N2</text></g></svg><figcaption>Figure 1.2 — Absorption, spontaneous emission and stimulated emission. Only the stimulated photon is emitted into the same mode as the incoming one: same frequency, direction, phase and polarisation.</figcaption></figure>

  <div class="eq"><b>(1.5)</b>absorption rate   = B₁₂ ρ(ν) N₁</div>
  <div class="eq"><b>(1.6)</b>spontaneous rate  = A₂₁ N₂</div>
  <div class="eq"><b>(1.7)</b>stimulated rate   = B₂₁ ρ(ν) N₂</div>
  <p>A₂₁ has units of s⁻¹ and is a property of the atom alone; the B coefficients describe the response to an external field. Spontaneous emission is isotropic and incoherent. Stimulated emission is coherent with the driving field: same frequency, direction, phase and polarisation. That single sentence is the physical basis of the laser.</p>

  <h3 class="s"><i style="background:#B45309">4</i>Derivation of the Einstein relations</h3>
  <p>Place the system in a cavity at temperature T in complete thermal equilibrium, where upward and downward rates must balance.</p>
  <div class="eq"><b>(1.8)</b>B₁₂ ρ(ν) N₁ = A₂₁ N₂ + B₂₁ ρ(ν) N₂</div>
  <div class="eq"><b>(1.9)</b>ρ(ν) = (A₂₁/B₂₁) / [ (N₁B₁₂)/(N₂B₂₁) − 1 ]</div>
  <p>In equilibrium the populations follow Boltzmann, N₁/N₂ = (g₁/g₂) exp(hν/kT). Substituting this into (1.9) and comparing term by term with the Planck law, which must be recovered at every temperature,</p>
  <div class="eq"><b>(1.10)</b>ρ(ν) = (8πhν³/c³) / [ exp(hν/kT) − 1 ]</div>
  <p>gives the two Einstein relations, which hold for the atom irrespective of any field:</p>
  <div class="eq"><b>(1.11)</b>g₁ B₁₂ = g₂ B₂₁    and    A₂₁ / B₂₁ = 8πhν³ / c³</div>

  <ul class="chk">
    <li>The first relation says absorption and stimulated emission are equally probable per atom once degeneracy is accounted for. <b>A two-level system can therefore never be inverted by optical pumping alone</b> — this is why real lasers need three or four levels.</li>
    <li>The second carries the ν³ factor that governs the entire design space of lasers.</li>
  </ul>

  <div class="call ex">
    <p class="lbl">Worked example 1.2</p>
    <p>Compare spontaneous and stimulated emission rates in a 300 K blackbody field, first at 10 GHz and then at 500 nm.</p>
    <ol>
      <li>From (1.10) and (1.11) the rate ratio is A₂₁ / (B₂₁ρ) = exp(hν/kT) − 1.</li>
      <li>At 10 GHz: hν/kT = 4.136×10⁻⁵ / 0.02585 = 1.6×10⁻³, so the ratio is 1.6×10⁻³. Stimulated emission wins by three orders of magnitude.</li>
      <li>At 500 nm: hν/kT = 2.48 / 0.02585 = 95.9, so the ratio is exp(95.9) ≈ 4×10⁴¹. Spontaneous emission is utterly dominant.</li>
    </ol>
    <p class="res">This one number explains why thermal sources in the visible are incoherent, why inversion must be created by an external pump, and why the maser was demonstrated before the laser.</p>
  </div>

  <figure><svg viewBox='0 0 720 230' xmlns='http://www.w3.org/2000/svg'><g stroke='#2A3260'><line x1='60' y1='20' x2='60' y2='195'/><line x1='60' y1='195' x2='680' y2='195'/><line x1='60' y1='182.9' x2='680' y2='182.9' stroke-dasharray='4 4'/></g><polyline points='60,189.6 160,187.9 260,186.1 360,184.2 410,181.8 460,178.9 510,170.5 560,143.6 610,58.9 640,30' fill='none' stroke='#22C3D6' stroke-width='2.5'/><line x1='160' y1='30' x2='160' y2='195' stroke='#F5B301' stroke-dasharray='3 4'/><line x1='630' y1='30' x2='630' y2='195' stroke='#F5B301' stroke-dasharray='3 4'/><g font-family='IBM Plex Mono, monospace' font-size='10.5' fill='#9AA2C8'><text x='96' y='24' fill='#F5B301'>microwave 10 GHz</text><text x='500' y='24' fill='#F5B301'>visible 500 nm</text><text x='66' y='179'>ratio = 1</text><text x='40' y='210' text-anchor='middle'>1e9</text><text x='360' y='210' text-anchor='middle'>1e12</text><text x='660' y='210' text-anchor='middle'>1e15</text><text x='370' y='226' text-anchor='middle' fill='#6E77A0'>frequency (Hz, log scale)</text></g><text transform='translate(22,140) rotate(-90)' font-family='IBM Plex Mono, monospace' font-size='10.5' fill='#6E77A0'>A21 / B21 rho  (log)</text></svg><figcaption>Figure 1.3 — Ratio of spontaneous to stimulated emission rate in a 300 K blackbody field. The crossover sits in the far-infrared near 6 THz, that is at kT/h.</figcaption></figure>

  <h3 class="s"><i style="background:#BE123C">5</i>Dipole moment, lifetime and oscillator strength</h3>
  <p>The Einstein coefficients are not free parameters. They follow from the matrix element of the electric dipole operator between the two states.</p>
  <div class="eq"><b>(1.12)</b>μ₂₁ = ⟨ψ₂| −e r |ψ₁⟩</div>
  <div class="eq"><b>(1.13)</b>A₂₁ = 16π³ν³ |μ₂₁|² / (3 ε₀ h c³)</div>
  <div class="eq"><b>(1.14)</b>τ = 1 / Σₖ A₂ₖ    N₂(t) = N₂(0) exp(−t/τ)</div>
  <p>Atomic spectroscopists quote the dimensionless <b>oscillator strength</b> f, defined by comparison with a classical electron oscillator. It is of order unity for strongly allowed transitions and very small for forbidden ones.</p>
  <div class="eq"><b>(1.15)</b>A₂₁ = (2π e² ν² / (ε₀ mₑ c³)) (g₁/g₂) f₁₂</div>
  <p>The same matrix element fixes the absorption cross-section, which is what connects this lecture to the Beer–Lambert law in Week 6.</p>
  <div class="eq"><b>(1.16)</b>∫ σ(ν) dν = (e² / (4 ε₀ mₑ c)) f₁₂</div>

  <div class="call ex">
    <p class="lbl">Worked example 1.3</p>
    <p>The sodium D2 line at 589.0 nm has f = 0.641, with g₁ = 2 (3s ²S₁/₂) and g₂ = 4 (3p ²P₃/₂). Find A₂₁, the radiative lifetime and the natural linewidth.</p>
    <ol>
      <li>ν = c/λ = 5.089×10¹⁴ Hz, so ν² = 2.590×10²⁹ Hz².</li>
      <li>2πe²/(ε₀mₑc³) = 7.42×10⁻²² in SI, so the prefactor is 7.42×10⁻²² × 2.590×10²⁹ = 1.921×10⁸ s⁻¹.</li>
      <li>A₂₁ = 1.921×10⁸ × (2/4) × 0.641 = 6.16×10⁷ s⁻¹.</li>
      <li>τ = 1/A₂₁ = 16.2 ns.</li>
      <li>Natural linewidth Δν = 1/(2πτ) = 9.8 MHz.</li>
    </ol>
    <p class="res">Compare 9.8 MHz with the Doppler width of the same line in a 500 K vapour, about 1.7 GHz — larger by a factor of 170. Recovering the natural linewidth from beneath the Doppler profile is exactly the task of the sub-Doppler methods in Week 13.</p>
  </div>

  <div class="call try">
    <p class="lbl">Try it yourself</p>
    <p>Open the NIST Atomic Spectra Database, look up the sodium D lines, and check the published A value against the 6.16×10⁷ s⁻¹ obtained above. Then repeat the calculation for the D1 line (g₂ = 2, f = 0.320) and explain why its A coefficient is smaller.</p>
  </div>

  <h3 class="s"><i style="background:#6D28D9">6</i>Selection rules</h3>
  <p>A transition is <b>allowed</b> when the dipole matrix element (1.12) does not vanish. Because the dipole operator is odd under inversion and carries one unit of angular momentum, the integral vanishes unless parity changes and angular momentum is conserved.</p>

  <div class="scroll">
  <table>
    <thead><tr><th>System</th><th>Rule</th><th>Comment</th></tr></thead>
    <tbody>
      <tr><td>One-electron atom</td><td class="m">Δl = ±1, Δm = 0, ±1</td><td>parity must change (Laporte rule)</td></tr>
      <tr><td>LS-coupled atom</td><td class="m">ΔS = 0, ΔL = 0, ±1, ΔJ = 0, ±1</td><td>J = 0 → J = 0 strictly forbidden</td></tr>
      <tr><td>Vibration</td><td class="m">Δv = ±1 (harmonic)</td><td>overtones appear through anharmonicity</td></tr>
      <tr><td>Rotation</td><td class="m">ΔJ = ±1</td><td>ΔJ = 0 (Q branch) for perpendicular bands</td></tr>
      <tr><td>IR activity</td><td class="m">∂μ/∂Q ≠ 0</td><td>N₂ and O₂ are IR inactive</td></tr>
      <tr><td>Raman activity</td><td class="m">∂α/∂Q ≠ 0</td><td>complementary to IR (Week 11)</td></tr>
    </tbody>
  </table>
  </div>

  <div class="vs">
    <div class="bad">
      <span class="mark">✗ Forbidden means impossible</span>
      A frequent misreading. If it were true, the green auroral line of atomic oxygen at 557.7 nm — a forbidden transition — could not exist at all.
    </div>
    <div class="good">
      <span class="mark">✓ Forbidden means weak</span>
      Magnetic-dipole and electric-quadrupole transitions are 10⁵–10⁸ times weaker. They dominate wherever collisions are rare enough for metastable states to survive: low-density plasmas, upper atmosphere, nebulae.
    </div>
  </div>

  <h3 class="s"><i style="background:#0369A1">7</i>Link to the laboratory</h3>
  <div class="call lab">
    <p class="lbl">Sessions 1 and 2</p>
    <ul>
      <li><b>Session 1</b> — laser safety classes and instrument tour. Relate every instrument you see to a region of Figure 1.1 and to the class of transition it probes.</li>
      <li><b>Session 2</b> — spectrometer calibration with Hg / Ne / Ar lamps. Record every line in both nm and cm⁻¹, and test the linearity of your calibration <b>in wavenumber, not in wavelength</b>.</li>
      <li>In your first report, quote every line with a stated uncertainty and identify which broadening mechanism limits the observed width. For a lamp on a grating spectrometer the answer is almost always instrumental.</li>
    </ul>
  </div>

  <h3 class="s"><i style="background:#15181E">8</i>Summary</h3>
  <ul class="chk">
    <li>A spectrum encodes position (levels), intensity (probability × population) and shape (dynamics and environment).</li>
    <li>Master the conversions: 1240 eV·nm, 10⁷ nm·cm⁻¹, kT = 208 cm⁻¹ at 300 K.</li>
    <li>Three processes, two relations: g₁B₁₂ = g₂B₂₁ and A₂₁/B₂₁ = 8πhν³/c³.</li>
    <li>The ν³ factor makes spontaneous emission dominant in the optical region, so inversion requires a pump and at least three levels.</li>
    <li>A₂₁, τ, f, μ₂₁ and σ are five expressions of one underlying matrix element.</li>
    <li>Selection rules follow from parity and angular momentum. Forbidden lines are weak, not absent.</li>
  </ul>

  <h3 class="s"><i style="background:#0E7490">9</i>Key terms</h3>
  <div class="gloss">
    <div><b>Wavenumber</b><span class="ar">العدد الموجي</span><em>Waves per centimetre; directly proportional to photon energy.</em></div>
    <div><b>Spontaneous emission</b><span class="ar">الانبعاث التلقائي</span><em>Decay with no external field, random in direction and phase.</em></div>
    <div><b>Stimulated emission</b><span class="ar">الانبعاث المحفَّز</span><em>A photon induces an identical photon; the basis of optical gain.</em></div>
    <div><b>Einstein coefficients</b><span class="ar">معاملات آينشتاين</span><em>A for spontaneous decay, B for absorption and stimulated emission.</em></div>
    <div><b>Population inversion</b><span class="ar">قلب الإشغال</span><em>Upper level more populated than lower; the condition for amplification.</em></div>
    <div><b>Transition dipole moment</b><span class="ar">عزم ثنائي القطب الانتقالي</span><em>The matrix element from which all transition probabilities derive.</em></div>
    <div><b>Oscillator strength</b><span class="ar">قوة المذبذب</span><em>Dimensionless measure of transition strength, near unity when allowed.</em></div>
    <div><b>Radiative lifetime</b><span class="ar">العمر الإشعاعي</span><em>Mean time in the excited state before radiative decay.</em></div>
    <div><b>Selection rules</b><span class="ar">قواعد الاختيار</span><em>Conditions under which the dipole matrix element is non-zero.</em></div>
    <div><b>Absorption cross-section</b><span class="ar">مقطع الامتصاص</span><em>Effective area the atom presents to a photon, in cm².</em></div>
    <div><b>Planck law</b><span class="ar">قانون بلانك</span><em>Spectral energy density of thermal radiation versus frequency.</em></div>
    <div><b>Boltzmann distribution</b><span class="ar">توزيع بولتزمان</span><em>Relative level populations at thermal equilibrium.</em></div>
  </div>

  <h3 class="s"><i style="background:#B45309">10</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>

  <div class="q"><span class="n">1</span><div class="body">
    <p class="stem">A wavenumber of 20 000 cm⁻¹ corresponds to a wavelength of:</p>
    <ol type="a"><li>500 nm</li><li>200 nm</li><li>2000 nm</li><li>50 nm</li></ol>
  </div></div>
  <div class="q"><span class="n">2</span><div class="body">
    <p class="stem">The ratio A₂₁/B₂₁ is proportional to:</p>
    <ol type="a"><li>ν</li><li>ν²</li><li>ν³</li><li>1/ν</li></ol>
  </div></div>
  <div class="q"><span class="n">3</span><div class="body">
    <p class="stem">The relation g₁B₁₂ = g₂B₂₁ leads directly to which conclusion?</p>
    <ol type="a"><li>A two-level system cannot be inverted by optical pumping</li><li>Spontaneous emission always dominates</li><li>Absorption is stronger than stimulated emission</li><li>A laser needs only two levels</li></ol>
  </div></div>
  <div class="q"><span class="n">4</span><div class="body">
    <p class="stem">An excited state with a 16 ns lifetime has a natural linewidth of approximately:</p>
    <ol type="a"><li>1 MHz</li><li>10 MHz</li><li>100 MHz</li><li>1 GHz</li></ol>
  </div></div>
  <div class="q"><span class="n">5</span><div class="body">
    <p class="stem">An electric-dipole transition from J = 0 to J = 0 is:</p>
    <ol type="a"><li>allowed and strong</li><li>allowed but weak</li><li>strictly forbidden</li><li>temperature dependent</li></ol>
  </div></div>

  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body">
    <p class="stem">A student measures the sodium line on a grating spectrometer of 0.1 nm resolution and reports the measured width as the Doppler width. Where is the error, and how would you verify it?</p>
    <div class="lines"></div><div class="lines"></div>
  </div></div>
  <div class="q"><span class="n">2</span><div class="body">
    <p class="stem">A researcher finds building a vacuum-ultraviolet laser far harder than a visible one. Explain the physical reason in terms of the Einstein coefficients.</p>
    <div class="lines"></div><div class="lines"></div>
  </div></div>
  <div class="q"><span class="n">3</span><div class="body">
    <p class="stem">Sodium vapour at 300 K shows no visible emission, yet emits strongly in a flame or plasma. Justify this numerically.</p>
    <div class="lines"></div><div class="lines"></div>
  </div></div>

  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body">
    <p class="stem">Derive the Einstein relations from thermal equilibrium and comparison with the Planck law, and explain why this derivation is a proof that stimulated emission must exist.</p>
  </div></div>
  <div class="q"><span class="n">2</span><div class="body">
    <p class="stem">Discuss the relationship between the transition dipole moment and each of A₂₁, the radiative lifetime, the oscillator strength and the absorption cross-section, showing that they are facets of one quantity.</p>
  </div></div>

  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. Stimulated emission produces a photon identical to the stimulating one in frequency, direction and phase.</div><span>T / F</span></div>
  <div class="tf"><div>2. Population inversion in a two-level system is achievable by optical pumping if the pump is strong enough.</div><span>T / F</span></div>
  <div class="tf"><div>3. At 300 K stimulated emission dominates in the microwave region and spontaneous emission in the visible.</div><span>T / F</span></div>
  <div class="tf"><div>4. Forbidden transitions never occur under any circumstances.</div><span>T / F</span></div>
  <div class="tf"><div>5. Wavenumber is directly proportional to photon energy.</div><span>T / F</span></div>

  <h3 class="s"><i style="background:#047857">11</i>Assignments</h3>

  <div class="hw">
    <div class="top"><h4>1 · Personal conversion table</h4><span class="lvl b">BASIC</span></div>
    <p>Take five laser sources available in the Institute (for example 1064, 532, 355, 633 and 10 600 nm) and convert each to cm⁻¹, eV and THz. State the spectral region and the class of transition each one is suited to.</p>
    <p class="due"><b>Deliverable:</b> a five-row table, with the full working shown for at least one row.</p>
  </div>

  <div class="hw">
    <div class="top"><h4>2 · Spontaneous versus stimulated</h4><span class="lvl b">BASIC</span></div>
    <p>Evaluate exp(hν/kT) − 1 at 300 K for 10.6 µm, 1064 nm and 400 nm, and plot the result on a logarithmic axis.</p>
    <p class="due"><b>Deliverable:</b> the three calculations, the plot, and two sentences interpreting the trend.</p>
  </div>

  <div class="hw">
    <div class="top"><h4>3 · From oscillator strength to lifetime</h4><span class="lvl i">INTERMEDIATE</span></div>
    <p>Select an atomic line from the NIST Atomic Spectra Database. Record f, g₁, g₂ and λ, then compute A₂₁, the radiative lifetime and the natural linewidth, and compare your A with the published value.</p>
    <p class="due"><b>Deliverable:</b> the chosen line with its source, the full calculation, and the percentage difference with a comment on its origin.</p>
  </div>

  <div class="hw">
    <div class="top"><h4>4 · Reading a research paper</h4><span class="lvl i">INTERMEDIATE</span></div>
    <p>Choose a paper published in the last three years in Spectrochimica Acta Part B or Applied Spectroscopy. Identify the technique used, the physical quantity extracted, and one equation from this lecture that the authors relied on.</p>
    <p class="due"><b>Deliverable:</b> one page — full reference, summary in your own words, and the equation with its place in the paper.</p>
  </div>

  <div class="navw"><span></span><a href="#w2">Next week →</a></div>
  <p class="endnote">End of Lecture 1 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w2">
  <div class="hd" style="background:linear-gradient(120deg,#5B21B6,#6D28D9)">
    <p class="no">WEEK 02</p>
    <h2>Atomic Spectra</h2>
    <p>From one electron to many: quantum numbers, term symbols, coupling schemes, and the fine, hyperfine, Zeeman and Stark structure that turns a single line into a pattern you can read.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Write term symbols for one- and many-electron configurations and identify the ground term with Hund rules.</li><li>Distinguish LS from jj coupling and state where each applies.</li><li>Explain the origin of fine and hyperfine structure and estimate their relative magnitudes.</li><li>Predict Zeeman and Stark splittings and use them to extract field strengths.</li><li>Assign lines in an atomic emission spectrum and identify the emitting element.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Quantum numbers and configurations</h3>
  <p>A single electron in an atom is labelled by four quantum numbers: n (shell), l (orbital angular momentum, 0…n−1), mₗ and mₛ. The configuration lists the occupied orbitals, for example Na in its ground state is 1s² 2s² 2p⁶ 3s¹. Spectroscopy is almost never about the configuration itself but about the <b>terms</b> the configuration generates.</p>
  <p>A closed shell contributes zero to both L and S, so only the valence electrons matter. That is why the alkali spectra look hydrogen-like and why the alkalis were the first testing ground for laser spectroscopy.</p>
  <div class="eq"><b>(2.1)</b>L = Σ lᵢ ,  S = Σ sᵢ ,  J = L + S</div>
  <h3 class="s"><i style="background:#0E7490">2</i>Term symbols and Hund rules</h3>
  <p>A term is written as a compact label carrying the total spin, orbital and angular momentum of the state:</p>
  <div class="eq"><b>(2.2)</b>²ˢ⁺¹L_J    with L = 0,1,2,3 → S,P,D,F</div>
  <p>The superscript 2S+1 is the multiplicity, the letter encodes L, and the subscript is J, which runs from L+S down to |L−S|. For the sodium ground state 3s¹: S = ½, L = 0, so the only term is ²S₁/₂. The first excited configuration 3p¹ gives ²P₁/₂ and ²P₃/₂ — the origin of the famous sodium doublet.</p>
  <ul class="chk"><li><b>Hund 1</b> — the term with the largest multiplicity lies lowest.</li><li><b>Hund 2</b> — among those, the largest L lies lowest.</li><li><b>Hund 3</b> — for a less than half-filled shell the smallest J lies lowest; for more than half-filled, the largest J.</li></ul>
  <div class="call ex"><p class="lbl">Worked example 2.1</p><p>Predict the ground term of carbon, configuration 1s² 2s² 2p².</p><ol><li>Two equivalent p electrons give the allowed terms ³P, ¹D and ¹S.</li><li>Hund 1: the highest multiplicity is the triplet, so ³P lies lowest.</li><li>Hund 3: the 2p shell is less than half filled, so the smallest J is lowest.</li><li>For ³P: S = 1, L = 1, so J = 0, 1, 2 and the ground term is ³P₀.</li></ol><p class="res">The same reasoning applied to oxygen (2p⁴, more than half filled) gives ³P₂ instead — the two atoms have the same terms but the inverted order.</p></div>
  <h3 class="s"><i style="background:#047857">3</i>LS versus jj coupling</h3>
  <p>LS (Russell–Saunders) coupling assumes the electrostatic repulsion between electrons is much stronger than the spin–orbit interaction, so the individual l and s couple separately into L and S. It works well for light atoms. In heavy atoms the spin–orbit interaction grows roughly as Z⁴ and eventually dominates, so each electron couples its own l and s into j first, and the j values then combine into J. That is jj coupling.</p>
  <div class="vs"><div class="bad"><span class="mark">✗ Assuming LS coupling always applies</span>Term symbols such as ³P₁ are still written for heavy atoms out of habit, but for lead or mercury the selection rule ΔS = 0 breaks down badly — which is exactly why the mercury 253.7 nm intercombination line is bright enough to power fluorescent lamps.</div><div class="good"><span class="mark">✓ Check where the atom sits</span>Light atoms (up to roughly the first transition row) are safely LS. Heavy atoms are intermediate or jj, and intercombination lines become allowed. Always ask which regime you are in before applying a selection rule.</div></div>
  <h3 class="s"><i style="background:#B45309">4</i>Fine and hyperfine structure</h3>
  <p>Fine structure is the splitting of a term by the spin–orbit interaction, which couples the electron magnetic moment to the field it sees from its own orbital motion. Hyperfine structure is a much smaller splitting caused by the coupling of the nuclear spin I to the electronic angular momentum, giving F = J + I.</p>
  <div class="eq"><b>(2.3)</b>E_so = (A/2)[ J(J+1) − L(L+1) − S(S+1) ]</div>
  <div class="eq"><b>(2.4)</b>F = J + I , J + I − 1 , … , |J − I|</div>
  <div class="scroll"><table><thead><tr><th>Effect</th><th>Typical size</th><th>Example</th></tr></thead><tbody><tr><td>Electronic transition</td><td class="m">10⁴ cm⁻¹</td><td class="m">Na 3s → 3p, 16 960 cm⁻¹</td></tr><tr><td>Fine structure</td><td class="m">10⁰–10² cm⁻¹</td><td class="m">Na D doublet, 17.2 cm⁻¹</td></tr><tr><td>Hyperfine structure</td><td class="m">10⁻³–10⁻² cm⁻¹</td><td class="m">Na 3s, 1.77 GHz</td></tr><tr><td>Natural linewidth</td><td class="m">10⁻⁴ cm⁻¹</td><td class="m">Na 3p, 9.8 MHz</td></tr></tbody></table></div>
  <div class="call key"><p class="lbl">Key idea</p><p>Read the table downwards and you have the resolution ladder of the whole course. A grating spectrometer resolves the first two rows. Hyperfine structure needs a Fabry–Perot or a narrow-linewidth laser, and the natural linewidth needs the sub-Doppler methods of Week 13.</p></div>
  <h3 class="s"><i style="background:#BE123C">5</i>Atoms in external fields: Zeeman and Stark</h3>
  <p>A magnetic field lifts the degeneracy in m_J. In the weak-field (anomalous Zeeman) limit each level splits into 2J+1 components spaced by the product of the Bohr magneton, the Landé factor and the field.</p>
  <div class="eq"><b>(2.5)</b>ΔE = μ_B g_J m_J B ,  μ_B/h = 13.996 GHz/T</div>
  <div class="eq"><b>(2.6)</b>g_J = 1 + [J(J+1) + S(S+1) − L(L+1)] / [2J(J+1)]</div>
  <p>An electric field produces the Stark effect: linear in hydrogen because of its degenerate levels, quadratic in most other atoms. In plasmas the Stark effect appears as a broadening rather than a splitting, because every emitter sees a different microfield — that is the basis of the electron-density measurement in Week 12.</p>
  <div class="call ex"><p class="lbl">Worked example 2.2</p><p>Estimate the Zeeman splitting of a ²S₁/₂ level in a 0.5 T field, and decide whether a 0.05 nm resolution spectrometer at 589 nm could resolve it.</p><ol><li>For ²S₁/₂: L = 0, S = ½, J = ½, so g_J = 2.</li><li>The two m_J = ±½ components separate by ΔE = g_J μ_B B = 2 × 13.996 GHz/T × 0.5 T = 14.0 GHz.</li><li>The spectrometer resolution at 589 nm: Δν = c Δλ/λ² = 2.998×10⁸ × 5×10⁻¹¹ / (5.89×10⁻⁷)² = 43 GHz.</li><li>The splitting is three times smaller than the instrumental resolution.</li></ol><p class="res">The line would simply look slightly broadened. To see the Zeeman components you need a scanning Fabry–Perot or a tunable single-mode laser.</p></div>
  <h3 class="s"><i style="background:#6D28D9">6</i>Reading an atomic emission spectrum</h3>
  <ul class="chk"><li>Identify the strongest lines first; these are usually resonance transitions to the ground term.</li><li>Look for characteristic patterns: alkali doublets, alkaline-earth singlet–triplet pairs, dense line forests for transition and rare-earth elements.</li><li>Check candidate assignments against a database (NIST ASD) using wavelength, relative intensity and the upper-level energy together — wavelength alone is never enough in a crowded spectrum.</li><li>Rare-earth spectra contain thousands of lines from partly filled 4f shells, which is why they are so useful as laser media and so painful to assign.</li></ul>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 3</b> — atomic emission: identify elements from line positions and relative intensities.</li><li>Record the Hg, Ne and Ar lamp lines from Session 2 and assign each to a transition using the database. Note the upper-level energy for every line you assign; you will reuse exactly this information for the Boltzmann plot in Week 12.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">7</i>Summary</h3>
  <ul class="chk"><li>Closed shells contribute nothing; only valence electrons generate terms.</li><li>The term symbol ²ˢ⁺¹L_J encodes spin, orbital and total angular momentum, and Hund rules order the terms.</li><li>LS coupling holds for light atoms, jj for heavy ones, where intercombination lines become allowed.</li><li>Fine structure comes from spin–orbit coupling, hyperfine from the nuclear spin; they differ by roughly three orders of magnitude.</li><li>Magnetic fields split levels in m_J; electric fields shift them and, in plasmas, broaden them.</li></ul>
  <h3 class="s"><i style="background:#0E7490">8</i>Key terms</h3>
  <div class="gloss"><div><b>Term symbol</b><span class="ar">رمز الحد</span><em>Compact label ²ˢ⁺¹L_J for the angular momentum of a state.</em></div><div><b>Multiplicity</b><span class="ar">التعددية</span><em>The value 2S+1, the number of fine-structure components of a term.</em></div><div><b>Hund rules</b><span class="ar">قواعد هوند</span><em>Empirical rules ordering the terms of a configuration in energy.</em></div><div><b>LS coupling</b><span class="ar">اقتران رَسل–ساوندرز</span><em>Scheme valid when electrostatic repulsion exceeds spin–orbit coupling.</em></div><div><b>jj coupling</b><span class="ar">الاقتران jj</span><em>Scheme for heavy atoms where spin–orbit coupling dominates.</em></div><div><b>Fine structure</b><span class="ar">البنية الدقيقة</span><em>Splitting of a term by the spin–orbit interaction.</em></div><div><b>Hyperfine structure</b><span class="ar">البنية فوق الدقيقة</span><em>Much smaller splitting caused by coupling to the nuclear spin.</em></div><div><b>Landé factor</b><span class="ar">عامل لاندي</span><em>The factor g_J setting the magnetic splitting of a level.</em></div><div><b>Zeeman effect</b><span class="ar">تأثير زيمان</span><em>Splitting of spectral lines in a magnetic field.</em></div><div><b>Stark effect</b><span class="ar">تأثير شتارك</span><em>Shift or splitting of levels in an electric field.</em></div><div><b>Resonance line</b><span class="ar">خط الرنين</span><em>Transition connecting an excited state to the ground term; usually the strongest.</em></div><div><b>Intercombination line</b><span class="ar">خط التداخل بين التعدديات</span><em>Transition violating ΔS = 0, weak in light atoms, strong in heavy ones.</em></div></div>
  <h3 class="s"><i style="background:#B45309">9</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">The term symbol ³P₂ describes a state with:</p><ol type="a"><li>S = 1, L = 1, J = 2</li><li>S = 3, L = 1, J = 2</li><li>S = 1, L = 2, J = 2</li><li>S = ½, L = 1, J = 2</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">The sodium D doublet arises from:</p><ol type="a"><li>fine-structure splitting of the 3p level</li><li>hyperfine structure of the 3s level</li><li>the Zeeman effect</li><li>two different isotopes</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">Spin–orbit coupling grows with atomic number roughly as:</p><ol type="a"><li>Z</li><li>Z²</li><li>Z⁴</li><li>independent of Z</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Hyperfine structure originates from:</p><ol type="a"><li>coupling of nuclear spin to electronic angular momentum</li><li>the spin–orbit interaction</li><li>collisions with other atoms</li><li>the finite lifetime of the state</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">In the weak-field Zeeman effect, a level with J = 1 splits into:</p><ol type="a"><li>2 components</li><li>3 components</li><li>4 components</li><li>it does not split</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A student assigns an unknown line in a plasma spectrum purely by matching its wavelength to a database entry, and gets the element wrong. List three additional pieces of information that would have prevented the error.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">Mercury lamps emit strongly at 253.7 nm even though that transition violates ΔS = 0. Explain why this intercombination line is nonetheless intense.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Explain the physical origin of fine and hyperfine structure and discuss what instrumental resolution is required to observe each in the sodium spectrum, referring to concrete numbers.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. Closed shells contribute zero to both L and S.</div><span>T / F</span></div>
  <div class="tf"><div>2. In jj coupling the individual orbital and spin momenta first couple into L and S.</div><span>T / F</span></div>
  <div class="tf"><div>3. Hyperfine structure is typically three orders of magnitude smaller than fine structure.</div><span>T / F</span></div>
  <div class="tf"><div>4. The Landé factor of a ²S₁/₂ level is exactly 2.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">10</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Term symbols for a series</h4><span class="lvl b">BASIC</span></div><p>Write the ground-state term symbol for Na, Mg, Al, Si and P, showing the reasoning from Hund rules in each case.</p><p class="due"><b>Deliverable:</b> A table with configuration, allowed terms and ground term for each element.</p></div>
  <div class="hw"><div class="top"><h4>2 · Assign a calibration lamp</h4><span class="lvl i">INTERMEDIATE</span></div><p>Take the Hg or Ne spectrum recorded in Lab Session 2, choose eight lines, and assign each to a transition using the NIST database, recording wavelength, upper-level energy, degeneracy and transition probability.</p><p class="due"><b>Deliverable:</b> A table of eight assigned lines with their database parameters, and one sentence on any line you could not assign confidently.</p></div>
  <div class="navw"><a href="#w1">← Previous</a><a href="#w3">Next →</a></div>
  <p class="endnote">End of Lecture 2 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w3">
  <div class="hd" style="background:linear-gradient(120deg,#6D28D9,#7C3AED)">
    <p class="no">WEEK 03</p>
    <h2>Line Shapes and Broadening</h2>
    <p>No spectral line is infinitely sharp. This lecture separates the mechanisms that give a line its width, shows how they combine, and explains how to decide which one dominates in a given experiment.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Distinguish homogeneous from inhomogeneous broadening and give an example of each.</li><li>Compute natural, Doppler and collisional widths and identify the dominant mechanism.</li><li>Recognise Gaussian, Lorentzian and Voigt profiles and fit them to measured data.</li><li>Separate instrumental width from physical width in a measured spectrum.</li><li>Use line shape as a diagnostic of temperature, pressure and density.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Homogeneous and inhomogeneous broadening</h3>
  <p>The distinction organises the whole subject. In <b>homogeneous</b> broadening every emitter has the same broadened response: natural and collisional broadening belong here, and both give a Lorentzian profile. In <b>inhomogeneous</b> broadening the emitters are individually narrow but distributed, so the observed line is the envelope of many shifted narrow lines: Doppler broadening and site-to-site variation in a solid belong here, and both give a Gaussian profile.</p>
  <div class="call key"><p class="lbl">Key idea</p><p>The practical consequence appears in Week 13. An inhomogeneous profile can be burned through with a saturating laser to reveal the underlying narrow response — a Lamb dip. A homogeneous profile cannot: saturating it simply reduces the whole line.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Natural (lifetime) broadening</h3>
  <p>A state of finite lifetime cannot have a perfectly defined energy. The uncertainty principle gives a Lorentzian profile of full width at half maximum:</p>
  <div class="eq"><b>(3.1)</b>Δν_N = 1 / (2π τ)</div>
  <div class="eq"><b>(3.2)</b>L(ν) = (Δν_N/2π) / [ (ν − ν₀)² + (Δν_N/2)² ]</div>
  <p>Typical allowed optical transitions have lifetimes of nanoseconds, giving widths of order 10 MHz. Forbidden transitions have far longer lifetimes and correspondingly narrower natural widths, which is why metastable states are attractive for optical clocks.</p>
  <h3 class="s"><i style="background:#047857">3</i>Doppler broadening</h3>
  <p>Emitters moving along the line of sight are shifted in frequency. A Maxwell–Boltzmann velocity distribution therefore produces a Gaussian profile whose width depends only on temperature and mass:</p>
  <div class="eq"><b>(3.3)</b>Δν_D = (2ν₀/c) √(2 k T ln2 / M) ≈ 7.16×10⁻⁷ ν₀ √(T/M)</div>
  <div class="eq"><b>(3.4)</b>G(ν) = (2/Δν_D)√(ln2/π) · exp[ −4 ln2 (ν−ν₀)²/Δν_D² ]</div>
  <div class="call ex"><p class="lbl">Worked example 3.1</p><p>Compute the Doppler width of the sodium D line (589 nm) in a 500 K vapour, and compare it with the natural width of 9.8 MHz.</p><ol><li>ν₀ = c/λ = 5.089×10¹⁴ Hz.</li><li>√(T/M) = √(500/23) = 4.663.</li><li>Δν_D = 7.16×10⁻⁷ × 5.089×10¹⁴ × 4.663 = 1.70×10⁹ Hz = 1.70 GHz.</li><li>The ratio to the natural width is 1.70×10⁹ / 9.8×10⁶ = 173.</li></ol><p class="res">Doppler broadening dominates by more than two orders of magnitude. Any measurement of the natural linewidth in this vapour must first defeat the Doppler profile — by cooling, by a collimated atomic beam, or by a sub-Doppler technique.</p></div>
  <h3 class="s"><i style="background:#B45309">4</i>Collisional and power broadening</h3>
  <p>Collisions interrupt the phase of the emitted wave and shorten the effective coherence time, broadening the line homogeneously and often shifting it. To a good approximation the width grows linearly with pressure:</p>
  <div class="eq"><b>(3.5)</b>Δν_c = (1/π τ_coll) ∝ p</div>
  <p>At atmospheric pressure collisional widths of a few GHz are typical, which is why atmospheric absorption lines are pressure broadened and why TDLAS measurements in Week 8 can retrieve pressure from line shape. A strong laser field adds a further homogeneous contribution, power broadening, which sets a floor on the resolution achievable with high intensities:</p>
  <div class="eq"><b>(3.6)</b>Δν_sat = Δν₀ √(1 + I/I_sat)</div>
  <div class="scroll"><table><thead><tr><th>Mechanism</th><th>Profile</th><th>Class</th><th>Depends on</th></tr></thead><tbody><tr><td>Natural</td><td class="m">Lorentzian</td><td class="m">homogeneous</td><td class="m">lifetime only</td></tr><tr><td>Collisional</td><td class="m">Lorentzian</td><td class="m">homogeneous</td><td class="m">pressure, partner gas</td></tr><tr><td>Power</td><td class="m">Lorentzian</td><td class="m">homogeneous</td><td class="m">laser intensity</td></tr><tr><td>Doppler</td><td class="m">Gaussian</td><td class="m">inhomogeneous</td><td class="m">temperature, mass</td></tr><tr><td>Instrumental</td><td class="m">often Gaussian</td><td class="m">inhomogeneous</td><td class="m">slit, grating, detector</td></tr></tbody></table></div>
  <h3 class="s"><i style="background:#BE123C">5</i>The Voigt profile and line-shape fitting</h3>
  <p>When a Gaussian and a Lorentzian mechanism act together — the usual case — the observed profile is their convolution, the Voigt profile. It has no closed analytical form and is evaluated numerically, but every fitting package provides it.</p>
  <div class="eq"><b>(3.7)</b>V(ν) = ∫ G(ν′) L(ν − ν′) dν′</div>
  <p>Fitting a Voigt profile returns both widths separately, and this is what makes line-shape analysis a quantitative diagnostic: the Gaussian part gives the temperature, the Lorentzian part gives the pressure or the electron density.</p>
  <div class="vs"><div class="bad"><span class="mark">✗ Fitting a Gaussian because the line looks symmetric</span>A Voigt profile is symmetric too. Forcing a Gaussian fit onto Voigt data returns a temperature that is systematically too high, because the Lorentzian wings are absorbed into the Gaussian width.</div><div class="good"><span class="mark">✓ Fit a Voigt and inspect the wings</span>Plot the residuals on a logarithmic scale. Lorentzian wings fall as 1/(Δν)² and stand far above a Gaussian, which falls exponentially. The wings, not the peak, carry the evidence.</div></div>
  <h3 class="s"><i style="background:#6D28D9">6</i>Instrumental width and deconvolution</h3>
  <p>Every spectrometer imposes its own profile. The measured width is a convolution of the true line with the instrument function, and if the two are comparable the physical width cannot be read off directly.</p>
  <div class="eq"><b>(3.8)</b>Δν_meas² ≈ Δν_true² + Δν_inst²   (Gaussian case)</div>
  <ul class="chk"><li>Measure the instrument function with a source known to be far narrower than the instrument — a stabilised laser, or a low-pressure lamp line.</li><li>If the measured width equals the instrument width within error, you have measured nothing about the sample.</li><li>Deconvolution amplifies noise. Never deconvolve beyond a factor of about two in width.</li></ul>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 12</b> — line-shape analysis: fit Gaussian, Lorentzian and Voigt profiles to your measured lines and report all three fits with their residuals.</li><li>Compare the fitted Gaussian width with the Doppler width predicted from the source temperature, and account for any difference.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">7</i>Summary</h3>
  <ul class="chk"><li>Homogeneous broadening (natural, collisional, power) gives Lorentzian profiles; inhomogeneous (Doppler, instrumental) gives Gaussian ones.</li><li>Δν_N = 1/(2πτ) and Δν_D = 7.16×10⁻⁷ ν₀√(T/M) are the two numbers to know by heart.</li><li>In a typical vapour cell the Doppler width exceeds the natural width by two orders of magnitude.</li><li>The Voigt profile separates the two contributions and turns line shape into a thermometer and a pressure gauge.</li><li>Always measure the instrument function before claiming a physical width.</li></ul>
  <h3 class="s"><i style="background:#0E7490">8</i>Key terms</h3>
  <div class="gloss"><div><b>Homogeneous broadening</b><span class="ar">الاتساع المتجانس</span><em>All emitters share the same broadened response; Lorentzian.</em></div><div><b>Inhomogeneous broadening</b><span class="ar">الاتساع غير المتجانس</span><em>Narrow emitters distributed in frequency; Gaussian envelope.</em></div><div><b>Natural linewidth</b><span class="ar">العرض الطبيعي</span><em>Width set by the finite lifetime of the state.</em></div><div><b>Doppler broadening</b><span class="ar">اتساع دوبلر</span><em>Broadening from the thermal velocity distribution.</em></div><div><b>Collisional broadening</b><span class="ar">الاتساع التصادمي</span><em>Phase-interrupting collisions; grows with pressure.</em></div><div><b>Power broadening</b><span class="ar">اتساع الإشباع</span><em>Extra homogeneous width caused by a strong driving field.</em></div><div><b>Voigt profile</b><span class="ar">مظهر فويغت</span><em>Convolution of a Gaussian and a Lorentzian.</em></div><div><b>FWHM</b><span class="ar">العرض عند نصف القمة</span><em>Full width at half maximum, the standard measure of line width.</em></div><div><b>Instrument function</b><span class="ar">دالة الجهاز</span><em>The profile the spectrometer imposes on an infinitely narrow line.</em></div><div><b>Deconvolution</b><span class="ar">فك الالتفاف</span><em>Numerical removal of the instrument function from measured data.</em></div><div><b>Resolving power</b><span class="ar">قدرة التحليل</span><em>R = λ/Δλ, the smallest resolvable separation relative to wavelength.</em></div><div><b>Optical depth</b><span class="ar">العمق البصري</span><em>Product of cross-section, density and path; large values distort line shape.</em></div></div>
  <h3 class="s"><i style="background:#B45309">9</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Reducing the pressure in a gas cell at constant temperature causes the total line width to:</p><ol type="a"><li>approach the Gaussian Doppler limit</li><li>increase in a Lorentzian manner</li><li>stay unchanged</li><li>become purely natural</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">The Voigt profile is:</p><ol type="a"><li>a convolution of Gaussian and Lorentzian</li><li>the sum of two Gaussians</li><li>the product of two Lorentzians</li><li>an approximate triangular profile</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">A 16 ns lifetime corresponds to a natural width of about:</p><ol type="a"><li>1 MHz</li><li>10 MHz</li><li>100 MHz</li><li>1 GHz</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Doppler broadening depends on:</p><ol type="a"><li>temperature and molecular mass</li><li>pressure and partner gas</li><li>laser intensity</li><li>the lifetime of the state</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">Lorentzian wings fall off with detuning as:</p><ol type="a"><li>1/Δν</li><li>1/Δν²</li><li>exponentially</li><li>as a Gaussian</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A measured line has a width equal, within uncertainty, to the instrument function of the spectrometer. What can and cannot be concluded about the sample?</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">You fit a measured profile with a pure Gaussian and obtain a temperature far above the known temperature of the source. Explain the most likely cause and how you would test it.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Compare the four broadening mechanisms treated in this lecture in terms of physical origin, profile shape, class and the experimental parameter each one measures, and describe an experiment in which each in turn dominates.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. Doppler broadening is homogeneous because every atom is identical.</div><span>T / F</span></div>
  <div class="tf"><div>2. Collisional broadening generally grows linearly with pressure.</div><span>T / F</span></div>
  <div class="tf"><div>3. A Voigt fit can return the Gaussian and Lorentzian widths separately.</div><span>T / F</span></div>
  <div class="tf"><div>4. Deconvolution can recover arbitrarily fine detail if the data are clean enough.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">10</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Broadening map</h4><span class="lvl b">BASIC</span></div><p>For the sodium D2 line, compute the natural, Doppler and collisional widths at 300 K, 1000 K and 2000 K, and at 1 mbar, 100 mbar and 1 bar. Present the results as a grid and mark the dominant mechanism in each cell.</p><p class="due"><b>Deliverable:</b> A 3×3 grid of total widths with the dominant mechanism identified in each cell, and the assumptions stated.</p></div>
  <div class="hw"><div class="top"><h4>2 · Fit real data</h4><span class="lvl i">INTERMEDIATE</span></div><p>Take a measured emission line from Lab Session 2 or 3 and fit it with Gaussian, Lorentzian and Voigt profiles in Origin, MATLAB or Python. Compare the reduced chi-squared values and the residual plots.</p><p class="due"><b>Deliverable:</b> The three fits overlaid on the data, a residual plot for each, and a justified statement of which model the data support.</p></div>
  <div class="navw"><a href="#w2">← Previous</a><a href="#w4">Next →</a></div>
  <p class="endnote">End of Lecture 3 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w4">
  <div class="hd" style="background:linear-gradient(120deg,#7C3AED,#0369A1)">
    <p class="no">WEEK 04</p>
    <h2>Molecular Spectroscopy I — Rotation</h2>
    <p>Molecules store energy in rotation as well as in electrons. Rotational spectra are the sharpest and most information-rich in all of spectroscopy, and they give bond lengths to four significant figures.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>State the Born–Oppenheimer approximation and explain why it allows energies to be separated.</li><li>Apply the rigid-rotor model and extract the rotational constant and bond length from a spectrum.</li><li>Account for centrifugal distortion in a non-rigid rotor.</li><li>Predict the intensity distribution of rotational lines using degeneracy and the Boltzmann factor.</li><li>Identify which molecules have a pure rotational spectrum and which do not.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>The Born–Oppenheimer separation</h3>
  <p>Nuclei are thousands of times heavier than electrons and move far more slowly. The electronic problem can therefore be solved at fixed nuclear positions, and the total energy separates into three nearly independent parts with a clear hierarchy of scales.</p>
  <div class="eq"><b>(4.1)</b>E_total ≈ E_elec + E_vib + E_rot</div>
  <div class="scroll"><table><thead><tr><th>Motion</th><th>Typical spacing</th><th>Spectral region</th></tr></thead><tbody><tr><td>Electronic</td><td class="m">10⁴–10⁵ cm⁻¹</td><td class="m">UV–visible</td></tr><tr><td>Vibrational</td><td class="m">10²–10⁴ cm⁻¹</td><td class="m">infrared</td></tr><tr><td>Rotational</td><td class="m">10⁰–10¹ cm⁻¹</td><td class="m">microwave, far-IR</td></tr></tbody></table></div>
  <div class="call key"><p class="lbl">Key idea</p><p>The separation of scales is why a vibrational band shows rotational fine structure, and why an electronic band shows vibrational structure that itself carries rotational structure. Each level of the hierarchy nests inside the one above it.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>The rigid rotor</h3>
  <p>A diatomic molecule treated as two masses at a fixed separation has quantised rotational energy levels governed by a single constant B, itself determined by the moment of inertia:</p>
  <div class="eq"><b>(4.2)</b>E_J = B J(J+1)   with J = 0, 1, 2, …</div>
  <div class="eq"><b>(4.3)</b>B = h / (8π² c I) ,  I = μ r² ,  μ = m₁m₂/(m₁+m₂)</div>
  <p>The selection rule ΔJ = ±1 then produces a spectrum of equally spaced lines separated by 2B, the most immediately recognisable pattern in molecular spectroscopy.</p>
  <div class="eq"><b>(4.4)</b>ν̃(J → J+1) = 2B(J+1) ,  spacing = 2B</div>
  <div class="call ex"><p class="lbl">Worked example 4.1</p><p>The pure rotational spectrum of CO shows lines separated by 3.845 cm⁻¹. Find the bond length.</p><ol><li>Spacing = 2B, so B = 1.9225 cm⁻¹.</li><li>I = h/(8π²cB) = 6.626×10⁻³⁴ / (8π² × 2.998×10¹⁰ × 1.9225) = 1.456×10⁻⁴⁶ kg·m².</li><li>μ for ¹²C¹⁶O = (12×16/28) × 1.6605×10⁻²⁷ = 1.139×10⁻²⁶ kg.</li><li>r = √(I/μ) = √(1.456×10⁻⁴⁶ / 1.139×10⁻²⁶) = 1.130×10⁻¹⁰ m = 113.0 pm.</li></ol><p class="res">This is why microwave spectroscopy is the gold standard for molecular geometry: a line-position measurement good to one part in 10⁶ gives a bond length good to one part in 10⁶.</p></div>
  <h3 class="s"><i style="background:#047857">3</i>Centrifugal distortion</h3>
  <p>A real bond stretches as the molecule spins faster, increasing the moment of inertia and lowering the level energies below the rigid-rotor prediction. A single correction term captures the effect well:</p>
  <div class="eq"><b>(4.5)</b>E_J = B J(J+1) − D J²(J+1)²</div>
  <p>D is typically 10⁻⁶ to 10⁻⁴ times B, so the effect is invisible at low J and unmistakable at high J: the line spacing slowly contracts as J increases. Fitting B and D together is standard practice, and D itself is related to the vibrational frequency, tying the rotational and vibrational pictures together.</p>
  <h3 class="s"><i style="background:#B45309">4</i>Intensities and the population distribution</h3>
  <p>Line intensity follows the population of the lower level, which is the product of the (2J+1)-fold degeneracy and the Boltzmann factor. The competition between a rising degeneracy and a falling exponential produces the characteristic intensity envelope that peaks at intermediate J.</p>
  <div class="eq"><b>(4.6)</b>N_J ∝ (2J+1) exp[ −B J(J+1) hc / kT ]</div>
  <div class="eq"><b>(4.7)</b>J_max ≈ √( kT / 2hcB ) − ½</div>
  <div class="call ex"><p class="lbl">Worked example 4.2</p><p>For CO at 300 K with B = 1.9225 cm⁻¹, find the most populated rotational level.</p><ol><li>kT in wavenumbers at 300 K is 208.5 cm⁻¹.</li><li>J_max = √(208.5 / (2 × 1.9225)) − ½ = √54.2 − 0.5.</li><li>J_max = 7.36 − 0.5 ≈ 6.9, so J = 7.</li></ol><p class="res">The envelope peaks near J = 7, and cooling the sample shifts the peak to lower J — which is exactly how rotational temperature is measured in a jet or a flame.</p></div>
  <h3 class="s"><i style="background:#BE123C">5</i>Which molecules show a rotational spectrum</h3>
  <p>A pure rotational transition requires a permanent electric dipole moment. Homonuclear diatomics such as N₂, O₂ and H₂ have none, so they are microwave-inactive — a fact with large consequences: the main constituents of the atmosphere are transparent in the microwave, while H₂O and CO₂ are not.</p>
  <div class="vs"><div class="bad"><span class="mark">✗ No rotational spectrum means no rotational information</span>N₂ has no pure rotational spectrum, yet its rotational constant is known precisely.</div><div class="good"><span class="mark">✓ Rotational structure appears in Raman and in electronic bands</span>Rotational Raman scattering requires only an anisotropic polarisability, which N₂ has. Rotational structure also appears within vibrational and electronic bands. There is almost always another route to the same constant.</div></div>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li>Rotational spectra themselves lie in the microwave, outside the instrumentation of this course, but their fingerprint is everywhere in the FTIR work of Session 6.</li><li>When you record the HCl or CO band in the mid-IR, the rotational lines within the band are governed by exactly the equations above. Measure the spacing, extract B, and compute the bond length as in Worked example 4.1.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>The Born–Oppenheimer approximation separates electronic, vibrational and rotational energies by orders of magnitude.</li><li>For a rigid rotor E_J = BJ(J+1) and the lines are equally spaced by 2B.</li><li>B gives the moment of inertia and hence the bond length to high precision.</li><li>Centrifugal distortion contracts the spacing at high J and is captured by the −DJ²(J+1)² term.</li><li>Intensity follows (2J+1)exp(−E_J/kT), peaking at an intermediate J that measures the temperature.</li><li>A permanent dipole moment is required for a pure rotational spectrum.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Born–Oppenheimer approximation</b><span class="ar">تقريب بورن–أوبنهايمر</span><em>Separation of nuclear and electronic motion by their mass difference.</em></div><div><b>Rigid rotor</b><span class="ar">الدوّار الصلب</span><em>Model of a molecule with fixed bond length.</em></div><div><b>Rotational constant</b><span class="ar">ثابت الدوران</span><em>B = h/8π²cI, the single parameter of the rigid rotor.</em></div><div><b>Moment of inertia</b><span class="ar">عزم القصور الذاتي</span><em>I = μr², the mass distribution about the rotation axis.</em></div><div><b>Reduced mass</b><span class="ar">الكتلة المختزلة</span><em>μ = m₁m₂/(m₁+m₂), the effective mass of the two-body problem.</em></div><div><b>Centrifugal distortion</b><span class="ar">التشوه الطارد المركزي</span><em>Bond stretching at high J, lowering level energies.</em></div><div><b>Degeneracy</b><span class="ar">التعددية</span><em>The 2J+1 states sharing a rotational energy.</em></div><div><b>Rotational temperature</b><span class="ar">درجة حرارة الدوران</span><em>Temperature extracted from the rotational intensity envelope.</em></div><div><b>Microwave inactive</b><span class="ar">غير فعّال في الموجات الدقيقة</span><em>Having no permanent dipole and hence no pure rotational spectrum.</em></div><div><b>Band</b><span class="ar">النطاق</span><em>A group of rotational lines belonging to one vibrational transition.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">The spacing between adjacent lines in the rigid-rotor spectrum is:</p><ol type="a"><li>B</li><li>2B</li><li>4B</li><li>B/2</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">The term −DJ²(J+1)² represents:</p><ol type="a"><li>centrifugal distortion</li><li>spin–orbit coupling</li><li>the Zeeman effect</li><li>Doppler broadening</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">Which molecule has no pure rotational spectrum?</p><ol type="a"><li>CO</li><li>HCl</li><li>N₂</li><li>H₂O</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">The rotational intensity envelope peaks at intermediate J because:</p><ol type="a"><li>degeneracy rises while the Boltzmann factor falls</li><li>the selection rule forbids low J</li><li>the detector is more sensitive there</li><li>centrifugal distortion enhances it</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">Doubling the reduced mass at fixed bond length changes B by a factor of:</p><ol type="a"><li>2</li><li>½</li><li>4</li><li>¼</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">You measure the rotational line spacing of a diatomic at two temperatures and find the same spacing but a different intensity envelope. Explain both observations.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">At high J the measured line spacing of a molecule contracts slightly. Identify the cause, and describe how you would extract both B and D from the data.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Explain how a rotational spectrum yields a bond length, and discuss the sources of uncertainty that limit the precision of the result.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The Born–Oppenheimer approximation relies on the large mass ratio between nuclei and electrons.</div><span>T / F</span></div>
  <div class="tf"><div>2. Homonuclear diatomic molecules show strong pure rotational absorption.</div><span>T / F</span></div>
  <div class="tf"><div>3. The rotational constant is inversely proportional to the moment of inertia.</div><span>T / F</span></div>
  <div class="tf"><div>4. Cooling a sample moves the peak of the rotational envelope to lower J.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Bond lengths from spacings</h4><span class="lvl b">BASIC</span></div><p>Given the rotational line spacings of HCl, HBr and CO from the literature, compute B, I and the bond length for each, and compare with published values.</p><p class="due"><b>Deliverable:</b> A table of B, I and r for the three molecules with the percentage difference from published values.</p></div>
  <div class="hw"><div class="top"><h4>2 · Rotational thermometer</h4><span class="lvl i">INTERMEDIATE</span></div><p>Using B = 1.9225 cm⁻¹ for CO, compute and plot the relative populations N_J for J = 0 to 30 at 100 K, 300 K and 1000 K, and mark J_max on each curve.</p><p class="due"><b>Deliverable:</b> The three population curves on one plot, the computed J_max values, and two sentences on how this is used as a thermometer.</p></div>
  <div class="navw"><a href="#w3">← Previous</a><a href="#w5">Next →</a></div>
  <p class="endnote">End of Lecture 4 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w5">
  <div class="hd" style="background:linear-gradient(120deg,#0369A1,#0E7490)">
    <p class="no">WEEK 05</p>
    <h2>Molecular Spectroscopy II — Vibration</h2>
    <p>Vibrational spectra identify functional groups, measure bond strengths, and provide the fingerprint region that makes infrared spectroscopy the most widely used analytical technique in chemistry.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Apply the harmonic oscillator model and extract the force constant from a measured frequency.</li><li>Explain anharmonicity, the Morse potential, and the appearance of overtone and combination bands.</li><li>Interpret P, Q and R branches in a rovibrational band.</li><li>Predict which vibrational modes are infrared active.</li><li>Describe how an FTIR spectrometer works and why it is preferred over a dispersive instrument.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>The harmonic oscillator</h3>
  <p>A chemical bond behaves near equilibrium like a spring. Solving the quantum harmonic oscillator gives equally spaced levels and a zero-point energy that never vanishes:</p>
  <div class="eq"><b>(5.1)</b>E_v = h c ν̃_e (v + ½) ,  v = 0, 1, 2, …</div>
  <div class="eq"><b>(5.2)</b>ν̃_e = (1 / 2πc) √(k / μ)</div>
  <p>The frequency rises with bond stiffness and falls with reduced mass. This single relation explains most of the group-frequency table used by every chemist: C–H stretches lie near 3000 cm⁻¹ because hydrogen is light, C=O near 1700 cm⁻¹ because the double bond is stiff, and C–Cl near 700 cm⁻¹ because chlorine is heavy.</p>
  <div class="call ex"><p class="lbl">Worked example 5.1</p><p>The fundamental of H³⁵Cl lies at 2886 cm⁻¹. Find the force constant.</p><ol><li>μ = (1 × 35 / 36) × 1.6605×10⁻²⁷ = 1.614×10⁻²⁷ kg.</li><li>2πcν̃ = 6.2832 × 2.998×10¹⁰ × 2886 = 5.436×10¹⁴ s⁻¹.</li><li>k = (2πcν̃)² μ = (5.436×10¹⁴)² × 1.614×10⁻²⁷.</li><li>k = 2.955×10²⁹ × 1.614×10⁻²⁷ = 477 N/m.</li></ol><p class="res">For comparison, a single C–C bond is near 450 N/m, a double bond near 950 N/m and a triple bond near 1600 N/m. The force constant is a direct measure of bond order.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Anharmonicity and the Morse potential</h3>
  <p>A real bond breaks if stretched far enough, so the potential must flatten at large separation. The Morse potential captures this and produces levels that converge as v increases:</p>
  <div class="eq"><b>(5.3)</b>V(r) = D_e [ 1 − exp(−a(r − r_e)) ]²</div>
  <div class="eq"><b>(5.4)</b>E_v = h c [ ν̃_e (v+½) − ν̃_e x_e (v+½)² ]</div>
  <ul class="chk"><li>The <b>fundamental</b> (v = 0 → 1) is strong and lies slightly below ν̃_e.</li><li><b>Overtones</b> (v = 0 → 2, 3) are formally forbidden in the harmonic model and appear only through anharmonicity, typically 10 to 100 times weaker. Near-IR spectroscopy of water and hydrocarbons lives entirely on these overtones.</li><li><b>Combination bands</b> involve two modes changing at once, and likewise borrow their intensity from anharmonicity.</li><li>Level spacing shrinks with v and reaches zero at dissociation, which allows the dissociation energy to be extracted by a Birge–Sponer extrapolation.</li></ul>
  <h3 class="s"><i style="background:#047857">3</i>Rovibrational structure: P, Q and R branches</h3>
  <p>A vibrational transition in the gas phase carries rotational structure, because ΔJ = ±1 accompanies Δv = ±1. This splits the band into two branches on either side of the missing band centre:</p>
  <div class="scroll"><table><thead><tr><th>Branch</th><th>ΔJ</th><th>Position</th><th>Appears when</th></tr></thead><tbody><tr><td>P</td><td class="m">−1</td><td class="m">below band centre</td><td class="m">always</td></tr><tr><td>Q</td><td class="m">0</td><td class="m">at band centre</td><td class="m">perpendicular bands, or unpaired electronic angular momentum</td></tr><tr><td>R</td><td class="m">+1</td><td class="m">above band centre</td><td class="m">always</td></tr></tbody></table></div>
  <p>The gap at the band centre in a molecule such as HCl is one of the most instructive features in all of vibrational spectroscopy: it is the direct visual proof that ΔJ = 0 is forbidden for a parallel band of a diatomic.</p>
  <div class="call key"><p class="lbl">Key idea</p><p>Line spacing within the branches is again about 2B, so an FTIR spectrum of a gas gives you the rotational constant, and hence the bond length, without any microwave equipment at all.</p></div>
  <h3 class="s"><i style="background:#B45309">4</i>Infrared activity and normal modes</h3>
  <p>A vibration absorbs infrared radiation only if it changes the electric dipole moment of the molecule. A non-linear molecule of N atoms has 3N−6 normal modes, and a linear one has 3N−5.</p>
  <div class="eq"><b>(5.5)</b>IR active  ⇔  ∂μ/∂Q ≠ 0</div>
  <div class="vs"><div class="bad"><span class="mark">✗ Every vibration shows up in the infrared</span>CO₂ has three fundamental modes but its symmetric stretch is completely absent from the IR spectrum, because the two C=O dipoles cancel throughout the motion.</div><div class="good"><span class="mark">✓ Symmetry decides activity</span>The symmetric stretch of CO₂ is IR inactive but Raman active. The bending and asymmetric stretching modes are IR active. This complementarity is the mutual exclusion rule of Week 11, and it is why the two techniques are run together.</div></div>
  <h3 class="s"><i style="background:#BE123C">5</i>FTIR: how the measurement is actually made</h3>
  <p>Modern infrared spectrometers do not disperse light. A Michelson interferometer modulates every wavelength at a different audio frequency, the detector records the resulting interferogram as a function of mirror displacement, and a Fourier transform recovers the spectrum.</p>
  <div class="eq"><b>(5.6)</b>I(x) = ∫ B(ν̃) cos(2π ν̃ x) dν̃   →   B(ν̃) = FT[ I(x) ]</div>
  <ul class="chk"><li><b>Fellgett (multiplex) advantage</b> — all wavelengths are measured at once, so the signal-to-noise ratio improves for a given measurement time.</li><li><b>Jacquinot (throughput) advantage</b> — no narrow slit is needed, so far more light reaches the detector.</li><li><b>Connes advantage</b> — the wavenumber scale is set by a reference HeNe laser, giving intrinsic and highly reproducible calibration.</li><li>Resolution is set by the maximum mirror travel: Δν̃ ≈ 1/(2 x_max).</li></ul>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 6</b> — FTIR: identify functional groups in solid and liquid samples.</li><li>Record a background before every sample and state in your report why this is necessary. Identify at least four group frequencies, and if you measure a gas-phase sample, extract B from the rotational structure and compute the bond length.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>E_v = hcν̃_e(v+½) for a harmonic oscillator; ν̃_e = (1/2πc)√(k/μ) links frequency to bond stiffness and mass.</li><li>Anharmonicity converges the levels and gives overtones and combination bands their intensity.</li><li>Rovibrational bands split into P and R branches, with a Q branch only under specific conditions.</li><li>A mode is IR active only if the dipole moment changes during the vibration; symmetry decides.</li><li>FTIR wins on throughput, multiplexing and calibration, which is why dispersive IR instruments have almost disappeared.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Harmonic oscillator</b><span class="ar">المذبذب التوافقي</span><em>Model with a parabolic potential and equally spaced levels.</em></div><div><b>Force constant</b><span class="ar">ثابت القوة</span><em>Stiffness k of the bond, in N/m; a measure of bond order.</em></div><div><b>Zero-point energy</b><span class="ar">طاقة النقطة الصفرية</span><em>The residual ½hcν̃ energy of the v = 0 level.</em></div><div><b>Anharmonicity</b><span class="ar">اللاتوافقية</span><em>Departure from the parabolic potential; converges the levels.</em></div><div><b>Morse potential</b><span class="ar">جهد مورس</span><em>Analytic potential that dissociates at large separation.</em></div><div><b>Fundamental</b><span class="ar">النطاق الأساسي</span><em>The v = 0 → 1 transition, the strongest vibrational band.</em></div><div><b>Overtone</b><span class="ar">النطاق التوافقي</span><em>A Δv > 1 transition, allowed only through anharmonicity.</em></div><div><b>Normal mode</b><span class="ar">النمط الطبيعي</span><em>One of the 3N−6 (or 3N−5) independent vibrations of a molecule.</em></div><div><b>P, Q, R branches</b><span class="ar">الفروع P وQ وR</span><em>Groups of rovibrational lines with ΔJ = −1, 0, +1.</em></div><div><b>Interferogram</b><span class="ar">مخطط التداخل</span><em>The raw FTIR signal as a function of mirror displacement.</em></div><div><b>Fellgett advantage</b><span class="ar">ميزة فلجيت</span><em>Signal-to-noise gain from measuring all wavelengths at once.</em></div><div><b>Fingerprint region</b><span class="ar">منطقة البصمة</span><em>The 600–1500 cm⁻¹ region, unique to each compound.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">The Q branch appears in a rovibrational band when:</p><ol type="a"><li>ΔJ = 0 is allowed</li><li>the molecule is homonuclear</li><li>there is no dipole moment</li><li>ΔJ = ±2</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">N₂ is infrared inactive because:</p><ol type="a"><li>∂μ/∂Q = 0</li><li>∂α/∂Q = 0</li><li>its mass is too large</li><li>its bond is triple</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">Overtone bands appear because of:</p><ol type="a"><li>anharmonicity</li><li>centrifugal distortion</li><li>Doppler broadening</li><li>the Zeeman effect</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Increasing the reduced mass at fixed force constant shifts the fundamental:</p><ol type="a"><li>to lower wavenumber</li><li>to higher wavenumber</li><li>not at all</li><li>out of the infrared entirely</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">The resolution of an FTIR spectrometer is set principally by:</p><ol type="a"><li>the maximum mirror travel</li><li>the slit width</li><li>the detector area</li><li>the source temperature</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A sample spectrum shows a weak band at almost exactly twice the wavenumber of a strong band. Identify the weak band and explain why it is weak.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">A student records an FTIR spectrum without a background scan and reports strong absorption near 2350 cm⁻¹ and 3600 cm⁻¹. What has happened, and what should be done?</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Explain how the force constant obtained from a vibrational spectrum relates to bond order, and discuss the limits of the harmonic approximation for real molecules.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The zero-point energy vanishes at absolute zero.</div><span>T / F</span></div>
  <div class="tf"><div>2. Overtones are formally forbidden in the harmonic oscillator model.</div><span>T / F</span></div>
  <div class="tf"><div>3. A linear molecule of N atoms has 3N−6 vibrational modes.</div><span>T / F</span></div>
  <div class="tf"><div>4. FTIR calibrates its wavenumber scale against an internal reference laser.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Force constants from spectra</h4><span class="lvl b">BASIC</span></div><p>From the fundamental wavenumbers of HF, HCl, HBr and HI, compute the reduced mass and force constant of each, and comment on the trend down the halogen group.</p><p class="due"><b>Deliverable:</b> A table of μ, k and ν̃ for the four molecules, with two sentences interpreting the trend.</p></div>
  <div class="hw"><div class="top"><h4>2 · Read a real FTIR spectrum</h4><span class="lvl i">INTERMEDIATE</span></div><p>Take the FTIR spectrum recorded in Lab Session 6 and assign at least six bands to functional groups, stating the evidence for each assignment and flagging any band you cannot assign.</p><p class="due"><b>Deliverable:</b> An annotated spectrum with a table of assignments, wavenumbers and the reasoning behind each.</p></div>
  <div class="navw"><a href="#w4">← Previous</a><a href="#w6">Next →</a></div>
  <p class="endnote">End of Lecture 5 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w6">
  <div class="hd" style="background:linear-gradient(120deg,#0E7490,#0F766E)">
    <p class="no">WEEK 06</p>
    <h2>Electronic Spectra and UV–Vis</h2>
    <p>Electronic transitions carry the largest energies in molecular spectroscopy and the least structure. This lecture turns an absorption curve into two hard numbers: a concentration and an optical band gap.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Apply the Franck–Condon principle to explain vibrational structure in an electronic band.</li><li>Read a Jablonski diagram and place absorption, fluorescence and phosphorescence on it.</li><li>Use the Beer–Lambert law quantitatively and recognise the conditions under which it fails.</li><li>Extract an optical band gap from a Tauc plot and state the transition type assumed.</li><li>Interpret the absorption spectrum of a nanoparticle colloid.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Electronic states and the Franck–Condon principle</h3>
  <p>An electronic transition redistributes the electron cloud in about a femtosecond, far faster than the nuclei can move. On a potential-energy diagram the transition is therefore drawn as a vertical line, and the intensity of each vibrational component is governed by the overlap of the two vibrational wavefunctions.</p>
  <div class="eq"><b>(6.1)</b>I ∝ | ⟨ χ_v′ | χ_v″ ⟩ |²   (Franck–Condon factor)</div>
  <div class="call key"><p class="lbl">Key idea</p><p>If the excited-state potential minimum lies at the same bond length as the ground state, the 0–0 band dominates and the spectrum is sharp. If the minimum is displaced — which happens when the excited electron is antibonding — a long vibrational progression appears, and if the displacement is extreme the transition leads straight to dissociation and the band becomes a structureless continuum.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>The Jablonski diagram</h3>
  <p>The Jablonski diagram organises every radiative and non-radiative process of a molecule onto one picture: singlet states S₀, S₁, S₂ and triplet states T₁, T₂, with vibrational manifolds on each.</p>
  <ul class="chk"><li><b>Absorption</b> — femtoseconds; takes the molecule to a vibrationally excited level of S₁ or S₂.</li><li><b>Vibrational relaxation</b> — picoseconds; loses the excess energy to the surroundings as heat.</li><li><b>Internal conversion</b> — S₂ → S₁, typically picoseconds; this is why emission almost always comes from S₁ (Kasha rule).</li><li><b>Fluorescence</b> — nanoseconds; S₁ → S₀, spin allowed.</li><li><b>Intersystem crossing</b> — S₁ → T₁, spin forbidden but enabled by spin–orbit coupling, and enhanced by heavy atoms.</li><li><b>Phosphorescence</b> — microseconds to seconds; T₁ → S₀, spin forbidden and therefore slow.</li></ul>
  <p>Vibrational relaxation before emission is the origin of the Stokes shift, treated quantitatively in Week 9.</p>
  <h3 class="s"><i style="background:#047857">3</i>The Beer–Lambert law</h3>
  <p>The workhorse relation of quantitative absorption spectroscopy states that absorbance is linear in concentration and path length:</p>
  <div class="eq"><b>(6.2)</b>A = log₁₀(I₀/I) = ε l c ,  T = 10⁻ᴬ</div>
  <div class="eq"><b>(6.3)</b>α = 2.303 A / d   (absorption coefficient of a film of thickness d)</div>
  <div class="call ex"><p class="lbl">Worked example 6.1</p><p>A dye solution of 5×10⁻⁵ M in a 1 cm cell gives A = 0.75. Find ε and the transmittance.</p><ol><li>ε = A / (l c) = 0.75 / (1 × 5×10⁻⁵) = 1.5×10⁴ L·mol⁻¹·cm⁻¹.</li><li>T = 10⁻⁰·⁷⁵ = 0.178, that is 17.8 % transmitted.</li><li>A value of ε near 10⁴ indicates a strongly allowed transition, consistent with f of order 0.1–1.</li></ol><p class="res">Note the practical window: absorbances between about 0.1 and 1.5 give the best precision. Below that the difference between I and I₀ is buried in noise; above it, stray light and detector nonlinearity dominate.</p></div>
  <div class="vs"><div class="bad"><span class="mark">✗ Beer–Lambert always holds</span>Deviations from linearity are routinely blamed on the instrument when the chemistry is at fault.</div><div class="good"><span class="mark">✓ It holds under stated conditions</span>Linearity requires dilute, non-scattering, non-aggregating samples, monochromatic light and no photochemistry. Aggregation at high concentration, stray light, and a bandwidth comparable with the absorption band all bend the calibration curve.</div></div>
  <h3 class="s"><i style="background:#B45309">4</i>Optical band gap and Tauc analysis</h3>
  <p>For a semiconductor the absorption coefficient near the edge follows a power law whose exponent identifies the type of transition. Plotting the appropriate power of (αhν) against photon energy gives a straight line whose intercept is the band gap.</p>
  <div class="eq"><b>(6.4)</b>(α h ν)^(1/n) = B ( h ν − E_g )</div>
  <div class="scroll"><table><thead><tr><th>Transition type</th><th>n</th><th>Plot</th><th>Example</th></tr></thead><tbody><tr><td>Direct allowed</td><td class="m">½</td><td class="m">(αhν)² vs hν</td><td class="m">ZnO, GaAs, CdSe</td></tr><tr><td>Direct forbidden</td><td class="m">3/2</td><td class="m">(αhν)^(2/3) vs hν</td><td class="m">some oxides</td></tr><tr><td>Indirect allowed</td><td class="m">2</td><td class="m">(αhν)^(1/2) vs hν</td><td class="m">Si, TiO₂ anatase</td></tr><tr><td>Indirect forbidden</td><td class="m">3</td><td class="m">(αhν)^(1/3) vs hν</td><td class="m">rare</td></tr></tbody></table></div>
  <div class="call ex"><p class="lbl">Worked example 6.2</p><p>A ZnO thin film shows an absorption edge at 376 nm. Estimate E_g and state the plot you would use.</p><ol><li>E_g ≈ 1239.84 / 376 = 3.30 eV.</li><li>ZnO is a direct allowed semiconductor, so n = ½ and the correct plot is (αhν)² against hν.</li><li>Extrapolating the linear region of that plot to (αhν)² = 0 gives E_g directly.</li></ol><p class="res">Quoting a band gap without stating which Tauc exponent was used is meaningless: the same data analysed with n = 2 instead of ½ can shift the reported gap by several tenths of an eV.</p></div>
  <h3 class="s"><i style="background:#BE123C">5</i>Absorption of nanostructured materials</h3>
  <p>At the nanoscale the absorption spectrum becomes a size measurement. Two distinct effects appear.</p>
  <ul class="chk"><li><b>Quantum confinement</b> — in semiconductor quantum dots the gap widens as the particle shrinks below the exciton Bohr radius, so the absorption edge blue-shifts with decreasing size. CdSe dots tune across the whole visible range by size alone.</li><li><b>Localised surface plasmon resonance</b> — in metal nanoparticles the conduction electrons oscillate collectively, giving an intense band whose position depends on size, shape and the surrounding medium. Spherical gold colloid absorbs near 520 nm; gold nanorods show a second, tunable band in the near-IR.</li><li>Both effects make UV–Vis the fastest quality check on any nanoparticle synthesis: a shifted or broadened peak signals a change in size or the onset of aggregation before any electron microscope is needed.</li></ul>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 4</b> — verify the Beer–Lambert law with a dye solution and determine the molar absorptivity from the slope of A against c.</li><li><b>Session 5</b> — record UV–Vis spectra of nanoparticle colloids and thin films, construct a Tauc plot and extract the band gap. State the exponent n you used and justify it from the material.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>Electronic transitions are vertical on a potential diagram; Franck–Condon factors set the vibrational intensities.</li><li>The Jablonski diagram places absorption, relaxation, fluorescence, intersystem crossing and phosphorescence on one map.</li><li>A = εlc is linear only for dilute, non-scattering samples measured with narrow bandwidth.</li><li>A Tauc plot gives the band gap, but only once the transition type fixes the exponent.</li><li>Confinement blue-shifts quantum-dot absorption; plasmon resonance dominates metal nanoparticle spectra.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Franck–Condon principle</b><span class="ar">مبدأ فرانك–كوندون</span><em>Electronic transitions are vertical because nuclei are slow.</em></div><div><b>Jablonski diagram</b><span class="ar">مخطط جابلونسكي</span><em>Energy-level map of radiative and non-radiative molecular processes.</em></div><div><b>Internal conversion</b><span class="ar">التحول الداخلي</span><em>Non-radiative relaxation between states of the same multiplicity.</em></div><div><b>Intersystem crossing</b><span class="ar">العبور بين الأنظمة</span><em>Non-radiative singlet-to-triplet transition.</em></div><div><b>Absorbance</b><span class="ar">الامتصاصية</span><em>A = log₁₀(I₀/I), the quantity linear in concentration.</em></div><div><b>Molar absorptivity</b><span class="ar">الامتصاصية المولارية</span><em>ε, the absorbance of a 1 M solution in a 1 cm cell.</em></div><div><b>Absorption coefficient</b><span class="ar">معامل الامتصاص</span><em>α, the attenuation per unit length inside the material.</em></div><div><b>Band gap</b><span class="ar">فجوة الطاقة</span><em>Energy separation between valence and conduction bands.</em></div><div><b>Tauc plot</b><span class="ar">مخطط تاوك</span><em>Linearised plot whose intercept gives the optical band gap.</em></div><div><b>Quantum confinement</b><span class="ar">الحصر الكمي</span><em>Widening of the gap when particle size falls below the exciton radius.</em></div><div><b>Surface plasmon resonance</b><span class="ar">رنين البلازمون السطحي</span><em>Collective electron oscillation in a metal nanoparticle.</em></div><div><b>Stray light</b><span class="ar">الضوء الشارد</span><em>Unwanted light reaching the detector; the main cause of high-A nonlinearity.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A transmittance of 1 % corresponds to an absorbance of:</p><ol type="a"><li>2</li><li>1</li><li>0.01</li><li>100</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">In Tauc analysis, (αhν)² is plotted against hν for a transition that is:</p><ol type="a"><li>direct allowed</li><li>indirect allowed</li><li>direct forbidden</li><li>indirect forbidden</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">The Franck–Condon principle rests on the fact that:</p><ol type="a"><li>electronic transitions are much faster than nuclear motion</li><li>nuclei move with the electrons instantaneously</li><li>vibrational energy is negligible</li><li>all transitions are vertical in time</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Emission almost always originates from S₁ regardless of which state was excited. This is:</p><ol type="a"><li>the Kasha rule</li><li>the Laporte rule</li><li>the Franck–Condon principle</li><li>the mutual exclusion rule</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">A gold nanoparticle colloid absorbs near 520 nm because of:</p><ol type="a"><li>localised surface plasmon resonance</li><li>quantum confinement</li><li>a direct band gap</li><li>vibrational overtones</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A calibration curve of A against concentration is linear up to A = 1 and then bends towards the concentration axis. Give two possible causes and an experiment to distinguish them.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">Two papers report band gaps of 3.2 eV and 3.6 eV for the same TiO₂ sample. Suggest the most likely methodological reason for the discrepancy.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Describe the full path from a raw UV–Vis transmission spectrum of a thin film to a reported band gap, identifying every point at which an assumption or a choice enters the analysis.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The Franck–Condon principle predicts that transitions are vertical on a potential-energy diagram.</div><span>T / F</span></div>
  <div class="tf"><div>2. Absorbance is linear in path length as well as in concentration.</div><span>T / F</span></div>
  <div class="tf"><div>3. The Tauc exponent depends on whether the transition is direct or indirect.</div><span>T / F</span></div>
  <div class="tf"><div>4. Plasmon resonance in metal nanoparticles is a quantum confinement effect.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Calibration curve</h4><span class="lvl b">BASIC</span></div><p>From the Session 4 data, plot A against concentration, fit a straight line, and report ε with its uncertainty from the fit. State the linear range you would trust.</p><p class="due"><b>Deliverable:</b> The plot with fit, the value of ε with uncertainty, and a statement of the valid range.</p></div>
  <div class="hw"><div class="top"><h4>2 · Two Tauc analyses</h4><span class="lvl i">INTERMEDIATE</span></div><p>Take one absorption spectrum of a nanomaterial and analyse it twice, once with n = ½ and once with n = 2. Report both band gaps and argue from the material which is correct.</p><p class="due"><b>Deliverable:</b> Both Tauc plots with the extrapolations shown, both gap values, and a justified choice.</p></div>
  <div class="navw"><a href="#w5">← Previous</a><a href="#w7">Next →</a></div>
  <p class="endnote">End of Lecture 6 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w7">
  <div class="hd" style="background:linear-gradient(120deg,#0F766E,#047857)">
    <p class="no">WEEK 07</p>
    <h2>Lasers as Spectroscopic Sources</h2>
    <p>What makes a laser a good spectroscopic source is rarely its power. This lecture works through tunability, linewidth and stability, surveys the source families, and ends at the optical frequency comb.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>State the properties required of a spectroscopic source and rank them for a given experiment.</li><li>Compare tunable dye, Ti:sapphire, OPO, diode and quantum-cascade lasers by range and linewidth.</li><li>Explain how a laser is frequency stabilised and why locking is necessary.</li><li>Describe the structure of an optical frequency comb and its role in absolute frequency measurement.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>What a spectroscopic source must provide</h3>
  <ul class="chk"><li><b>Tunability</b> — the frequency must be scanned across the line of interest, continuously and reproducibly.</li><li><b>Linewidth</b> — the laser must be narrower than the structure to be resolved. Resolving a 10 MHz natural width needs a laser far below 10 MHz.</li><li><b>Stability</b> — the frequency must stay where it is put for the duration of the scan; drift masquerades as line shape.</li><li><b>Power</b> — enough for signal-to-noise, but not so much as to saturate and power-broaden the transition.</li><li><b>Beam quality and coherence</b> — for interferometric and nonlinear techniques.</li></ul>
  <div class="call key"><p class="lbl">Key idea</p><p>These requirements pull against one another. High power broadens; wide tuning usually costs linewidth; narrow linewidth costs money and complexity. Choosing a source is choosing which compromise you can live with.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Families of tunable sources</h3>
  <div class="scroll"><table><thead><tr><th>Source</th><th>Typical range</th><th>Linewidth</th><th>Notes</th></tr></thead><tbody><tr><td>Dye laser</td><td class="m">400–900 nm</td><td class="m">MHz to GHz</td><td class="m">broad tuning, messy chemistry, largely superseded</td></tr><tr><td>Ti:sapphire</td><td class="m">700–1000 nm</td><td class="m">kHz to MHz</td><td class="m">workhorse for ultrafast and high resolution</td></tr><tr><td>OPO</td><td class="m">400 nm–4 µm</td><td class="m">MHz</td><td class="m">nonlinear conversion, very wide reach</td></tr><tr><td>Diode (ECDL)</td><td class="m">400 nm–3 µm</td><td class="m">kHz to MHz</td><td class="m">compact, cheap, the standard for TDLAS</td></tr><tr><td>Quantum cascade</td><td class="m">3–25 µm</td><td class="m">kHz to MHz</td><td class="m">opened the mid-IR fingerprint region</td></tr><tr><td>Frequency comb</td><td class="m">broadband</td><td class="m">Hz-level teeth</td><td class="m">absolute frequency reference</td></tr></tbody></table></div>
  <p>The parametric sources obey energy conservation between pump, signal and idler, which is what gives them such wide reach:</p>
  <div class="eq"><b>(7.1)</b>1/λ_p = 1/λ_s + 1/λ_i</div>
  <h3 class="s"><i style="background:#047857">3</i>Linewidth and frequency stabilisation</h3>
  <p>The fundamental limit on laser linewidth is set by spontaneous emission into the lasing mode, the Schawlow–Townes limit. In practice real lasers are far broader than this because of acoustic, thermal and mechanical noise, so the frequency must be actively controlled.</p>
  <div class="eq"><b>(7.2)</b>Δν_ST = 2π h ν (Δν_c)² / P</div>
  <ul class="chk"><li><b>Reference cavity locking</b> — the laser is locked to a resonance of a stable Fabry–Perot cavity, usually by the Pound–Drever–Hall technique. Excellent short-term stability.</li><li><b>Atomic or molecular locking</b> — the laser is locked to a sub-Doppler feature in a reference gas cell. Excellent long-term accuracy, since atoms do not drift.</li><li><b>Comb locking</b> — the laser is referenced to a frequency comb, itself referenced to an atomic clock. Gives absolute accuracy.</li></ul>
  <div class="vs"><div class="bad"><span class="mark">✗ A narrow specification on the data sheet means narrow in the experiment</span>A quoted linewidth of 100 kHz is usually measured over a millisecond. Over the several seconds of a real scan, thermal drift can move the frequency by tens of MHz.</div><div class="good"><span class="mark">✓ Ask over what time</span>Always ask what averaging time the linewidth refers to, and specify separately the stability you need over the duration of a whole scan. Free-running lasers drift; that is what locking is for.</div></div>
  <h3 class="s"><i style="background:#B45309">4</i>The optical frequency comb</h3>
  <p>A mode-locked femtosecond laser emits a pulse train whose spectrum is a set of perfectly evenly spaced narrow lines. Two radio-frequency numbers fully determine every optical frequency in the comb:</p>
  <div class="eq"><b>(7.3)</b>f_n = f_ceo + n · f_rep</div>
  <p>Here f_rep is the pulse repetition rate, f_ceo the carrier-envelope offset, and n an integer of order 10⁶. Because both f_rep and f_ceo are radio frequencies that can be counted against an atomic clock, the comb transfers microwave accuracy directly into the optical domain. This solved a problem that had defeated frequency metrology for decades, and it is why the 2005 Nobel Prize went to Hall and Hänsch.</p>
  <div class="call key"><p class="lbl">Key idea</p><p>For the spectroscopist the comb has two uses: as a ruler, to measure the absolute frequency of any laser locked to a transition, and as a source, in dual-comb spectroscopy, where a broadband spectrum is acquired in microseconds with no moving parts at all.</p></div>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li>The Institute instrumentation for this course uses fixed-frequency and diode sources rather than a comb, but the concepts transfer directly.</li><li>When you calibrate a spectrometer in Session 2, you are performing by hand — against known atomic lines — the same job the comb performs automatically and about a million times more accurately.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">5</i>Summary</h3>
  <ul class="chk"><li>Tunability, linewidth, stability and power are the four axes on which a spectroscopic source is judged, and they trade against each other.</li><li>Diode and quantum-cascade lasers dominate practical absorption spectroscopy; Ti:sapphire dominates ultrafast work; OPOs extend the reach.</li><li>Real linewidths are set by technical noise, not the Schawlow–Townes limit, so active stabilisation is essential.</li><li>The frequency comb links optical frequencies to radio frequencies through f_n = f_ceo + n f_rep, delivering absolute accuracy.</li></ul>
  <h3 class="s"><i style="background:#0E7490">6</i>Key terms</h3>
  <div class="gloss"><div><b>Tunability</b><span class="ar">قابلية التوليف</span><em>The range over which the output frequency can be scanned.</em></div><div><b>Linewidth</b><span class="ar">عرض الخط</span><em>The spectral width of the laser emission itself.</em></div><div><b>Mode hop</b><span class="ar">قفزة النمط</span><em>Abrupt jump between cavity modes, breaking a continuous scan.</em></div><div><b>ECDL</b><span class="ar">ليزر ثنائي بتجويف خارجي</span><em>External-cavity diode laser, the standard narrow tunable source.</em></div><div><b>Quantum cascade laser</b><span class="ar">ليزر الشلال الكمي</span><em>Intersubband semiconductor laser covering the mid-infrared.</em></div><div><b>OPO</b><span class="ar">مذبذب بارامتري بصري</span><em>Nonlinear device converting one pump wavelength into two tunable outputs.</em></div><div><b>Schawlow–Townes limit</b><span class="ar">حد شاولو–تاونز</span><em>Fundamental laser linewidth set by spontaneous emission.</em></div><div><b>Pound–Drever–Hall lock</b><span class="ar">قفل باوند–دريفر–هول</span><em>Standard technique for locking a laser to a reference cavity.</em></div><div><b>Frequency comb</b><span class="ar">مشط الترددات</span><em>Evenly spaced optical spectrum from a mode-locked laser.</em></div><div><b>Carrier-envelope offset</b><span class="ar">إزاحة الحامل عن الغلاف</span><em>The offset f_ceo that fixes the absolute position of the comb teeth.</em></div><div><b>Repetition rate</b><span class="ar">تردد التكرار</span><em>Pulse rate of a mode-locked laser; equals the comb tooth spacing.</em></div><div><b>Dual-comb spectroscopy</b><span class="ar">الطيفية بمشطين</span><em>Broadband spectroscopy using two combs of slightly different spacing.</em></div></div>
  <h3 class="s"><i style="background:#B45309">7</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">For Doppler-free high-resolution spectroscopy the essential property of the source is:</p><ol type="a"><li>narrow linewidth and tunability</li><li>high power only</li><li>femtosecond pulse duration</li><li>multimode operation</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">In a frequency comb f_n = f_ceo + n f_rep, the quantity f_rep is:</p><ol type="a"><li>the pulse repetition rate</li><li>the carrier-envelope offset</li><li>an atomic resonance frequency</li><li>the total bandwidth</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">Quantum cascade lasers are important mainly because they:</p><ol type="a"><li>reach the mid-infrared fingerprint region</li><li>produce the highest peak power</li><li>have the widest visible tuning</li><li>need no cooling</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Locking a laser to a sub-Doppler feature in a reference cell gives principally:</p><ol type="a"><li>long-term absolute accuracy</li><li>higher output power</li><li>wider tuning</li><li>shorter pulses</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">In an OPO the pump, signal and idler wavelengths satisfy:</p><ol type="a"><li>1/λp = 1/λs + 1/λi</li><li>λp = λs + λi</li><li>λp = λs − λi</li><li>λp λs = λi</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A scan across an absorption line is repeated three times and the line centre appears at a slightly different position each time. Identify the most likely cause and the remedy.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">You must measure a transition at 4.6 µm in a gas mixture. Choose a source family and justify the choice against the alternatives.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Discuss how the optical frequency comb changed optical frequency metrology, explaining what problem it solved and how it is used in modern spectroscopy.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. Higher laser power always improves the quality of a high-resolution measurement.</div><span>T / F</span></div>
  <div class="tf"><div>2. The Schawlow–Townes limit is usually the dominant contribution to a real laser linewidth.</div><span>T / F</span></div>
  <div class="tf"><div>3. The comb tooth spacing equals the repetition rate of the mode-locked laser.</div><span>T / F</span></div>
  <div class="tf"><div>4. An OPO produces two tunable outputs from a single fixed pump.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">8</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Choose a source</h4><span class="lvl b">BASIC</span></div><p>For each of these tasks, choose a laser source and justify it in two sentences: (a) sub-Doppler spectroscopy of rubidium at 780 nm, (b) methane detection at 3.3 µm, (c) transient absorption with 100 fs resolution, (d) Raman excitation of a coloured solid.</p><p class="due"><b>Deliverable:</b> Four short justified choices, each naming the decisive property.</p></div>
  <div class="hw"><div class="top"><h4>2 · Linewidth versus structure</h4><span class="lvl i">INTERMEDIATE</span></div><p>For the sodium D2 line, tabulate the natural width, hyperfine splitting and Doppler width, and determine the maximum laser linewidth that would allow each to be resolved.</p><p class="due"><b>Deliverable:</b> A table of the three structures with the corresponding laser linewidth requirement, and a comment on which sources qualify.</p></div>
  <div class="navw"><a href="#w6">← Previous</a><a href="#w8">Next →</a></div>
  <p class="endnote">End of Lecture 7 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w8">
  <div class="hd" style="background:linear-gradient(120deg,#047857,#4D7C0F)">
    <p class="no">WEEK 08</p>
    <h2>Laser Absorption Spectroscopy</h2>
    <p>Absorption is the most direct measurement in spectroscopy and the hardest to push to high sensitivity, because it asks you to measure a small difference between two large numbers. Everything here is about defeating that problem.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Apply the Beer–Lambert law in its cross-section form and compute a detection limit.</li><li>Explain why direct absorption is limited by laser intensity noise and how modulation defeats it.</li><li>Describe wavelength and frequency modulation with lock-in detection.</li><li>Explain cavity ring-down spectroscopy and calculate an absorption coefficient from a ring-down time.</li><li>Select an absorption technique appropriate to a stated sensitivity requirement.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Direct absorption and its limits</h3>
  <p>In the cross-section form the Beer–Lambert law reads:</p>
  <div class="eq"><b>(8.1)</b>I = I₀ exp(−σ N L)  ,  A_e = σ N L</div>
  <p>For weak absorption the fractional change in transmitted intensity is simply σNL. Detecting a fractional change of 10⁻³ is easy; 10⁻⁵ is difficult; 10⁻⁷ is impossible by direct measurement, because the laser intensity itself fluctuates by more than that. Two strategies exist, and both are essentially about noise rather than about absorption.</p>
  <ul class="chk"><li><b>Increase L</b> — multipass cells (White, Herriott) give tens to hundreds of metres; optical cavities give kilometres.</li><li><b>Reduce the noise</b> — move the measurement to a frequency where the laser is quiet, using modulation and phase-sensitive detection.</li></ul>
  <h3 class="s"><i style="background:#0E7490">2</i>Modulation and lock-in detection</h3>
  <p>Laser intensity noise has a 1/f character: it is enormous at low frequency and small above a few kilohertz. If the laser wavelength is dithered across the absorption line at a frequency f, the absorption signal appears at f and its harmonics, far away from the noisy region, and a lock-in amplifier recovers it with a very narrow effective bandwidth.</p>
  <div class="eq"><b>(8.2)</b>ν(t) = ν̄ + a cos(2π f t)   →   signal at f, 2f, 3f …</div>
  <ul class="chk"><li>The <b>1f</b> signal approximates the first derivative of the line shape.</li><li>The <b>2f</b> signal approximates the second derivative, peaks at line centre, and is nearly free of sloping background — which is why 2f detection is the standard in TDLAS.</li><li>Optimum modulation depth is roughly 2.2 times the line half-width; larger modulation broadens the recovered line.</li></ul>
  <div class="call key"><p class="lbl">Key idea</p><p>Wavelength modulation typically buys two to three orders of magnitude in sensitivity over direct absorption, for the cost of a function generator and a lock-in amplifier. It is the cheapest large gain available anywhere in this course.</p></div>
  <h3 class="s"><i style="background:#047857">3</i>Cavity-enhanced methods and CRDS</h3>
  <p>Placing the sample inside a high-finesse optical cavity multiplies the effective path length by roughly 2/(1−R). With mirrors of 99.99 % reflectivity a 50 cm cavity delivers about 10 km of path.</p>
  <div class="eq"><b>(8.3)</b>L_eff ≈ 2L / (1 − R)</div>
  <p>Cavity ring-down spectroscopy goes further and removes the intensity dependence entirely. The laser is switched off and the decay of light leaking from the cavity is timed. Absorption shortens the decay, and since the measurement is of a time constant rather than an intensity, laser power fluctuations cancel out completely.</p>
  <div class="eq"><b>(8.4)</b>I(t) = I₀ exp(−t/τ) ,  α = (1/c)(1/τ − 1/τ₀)</div>
  <div class="call ex"><p class="lbl">Worked example 8.1</p><p>An empty cavity has a ring-down time of 10 µs. With sample gas it falls to 8 µs. Find the absorption coefficient.</p><ol><li>1/τ = 1/8×10⁻⁶ = 1.25×10⁵ s⁻¹.</li><li>1/τ₀ = 1/10×10⁻⁶ = 1.00×10⁵ s⁻¹.</li><li>Difference = 2.5×10⁴ s⁻¹.</li><li>α = 2.5×10⁴ / 2.998×10⁸ = 8.3×10⁻⁵ m⁻¹ = 8.3×10⁻⁷ cm⁻¹.</li></ol><p class="res">An empty-cavity ring-down of 10 µs corresponds to about 3 km of effective path. Detecting α at the 10⁻⁷ cm⁻¹ level is routine for CRDS and utterly out of reach for a single-pass measurement.</p></div>
  <h3 class="s"><i style="background:#B45309">4</i>Detection limits and technique selection</h3>
  <p>The minimum detectable absorption determines the minimum detectable concentration through the cross-section and the path length. Comparisons between techniques are usually quoted as noise-equivalent absorption per unit bandwidth.</p>
  <div class="eq"><b>(8.5)</b>N_min = A_min / (σ L_eff)</div>
  <div class="scroll"><table><thead><tr><th>Technique</th><th>Typical α_min (cm⁻¹)</th><th>Complexity</th><th>Best used for</th></tr></thead><tbody><tr><td>Direct single pass</td><td class="m">10⁻³</td><td class="m">low</td><td class="m">strong absorbers, teaching labs</td></tr><tr><td>Multipass cell</td><td class="m">10⁻⁵</td><td class="m">moderate</td><td class="m">field gas sensing</td></tr><tr><td>WMS / TDLAS 2f</td><td class="m">10⁻⁶</td><td class="m">moderate</td><td class="m">industrial process monitoring</td></tr><tr><td>Cavity enhanced</td><td class="m">10⁻⁸</td><td class="m">high</td><td class="m">trace gas analysis</td></tr><tr><td>CRDS</td><td class="m">10⁻⁹–10⁻¹⁰</td><td class="m">high</td><td class="m">isotope ratios, ultra-trace</td></tr></tbody></table></div>
  <div class="vs"><div class="bad"><span class="mark">✗ Choosing the most sensitive technique available</span>CRDS on a strongly absorbing sample wastes money and time, and saturates rather than measures.</div><div class="good"><span class="mark">✓ Matching sensitivity to the problem</span>Estimate σNL first. If it exceeds 10⁻³, direct absorption is adequate and far more robust. Reserve cavity methods for the cases that genuinely demand them.</div></div>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li>The absorption work in this course is single-pass, in Sessions 4 and 5, where the absorbances are large and direct measurement is the right choice.</li><li>When you report a detection limit from that data, compute it as 3σ of your baseline noise divided by the calibration slope — the same definition used for all the techniques in the table above.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">5</i>Summary</h3>
  <ul class="chk"><li>Direct absorption measures a small difference between two large numbers and is limited by laser intensity noise near 10⁻³.</li><li>Wavelength modulation with 2f lock-in detection moves the measurement away from 1/f noise and gains two to three orders of magnitude.</li><li>Optical cavities multiply path length by 2/(1−R), reaching kilometres in a table-top device.</li><li>CRDS measures a decay time rather than an intensity, so laser power fluctuations cancel entirely.</li><li>Choose the technique from the required detection limit, not from what is most impressive.</li></ul>
  <h3 class="s"><i style="background:#0E7490">6</i>Key terms</h3>
  <div class="gloss"><div><b>Cross-section</b><span class="ar">المقطع العرضي</span><em>σ, the effective area presented by one absorber.</em></div><div><b>Optical density</b><span class="ar">الكثافة البصرية</span><em>The product σNL appearing in the exponent.</em></div><div><b>Multipass cell</b><span class="ar">خلية متعددة المرور</span><em>Mirror arrangement folding a long path into a small volume.</em></div><div><b>TDLAS</b><span class="ar">طيفية الامتصاص بالليزر الثنائي</span><em>Tunable diode laser absorption spectroscopy.</em></div><div><b>Wavelength modulation</b><span class="ar">التضمين بالطول الموجي</span><em>Dithering the laser frequency to shift the signal above 1/f noise.</em></div><div><b>Lock-in amplifier</b><span class="ar">مضخم القفل الطوري</span><em>Phase-sensitive detector recovering a signal at a known frequency.</em></div><div><b>2f detection</b><span class="ar">الكشف عند التوافقي الثاني</span><em>Detection at twice the modulation frequency; background free.</em></div><div><b>Finesse</b><span class="ar">الدقة الطيفية للتجويف</span><em>Measure of cavity quality, set mainly by mirror reflectivity.</em></div><div><b>Ring-down time</b><span class="ar">زمن الاضمحلال</span><em>τ, the decay constant of light leaking from a cavity.</em></div><div><b>CRDS</b><span class="ar">طيفية الاضمحلال في التجويف</span><em>Cavity ring-down spectroscopy; intensity independent.</em></div><div><b>Detection limit</b><span class="ar">حد الكشف</span><em>Smallest concentration distinguishable from the blank, usually at 3σ.</em></div><div><b>Baseline</b><span class="ar">الخط القاعدي</span><em>The signal recorded with no absorber present.</em></div></div>
  <h3 class="s"><i style="background:#B45309">7</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">CRDS extracts its analytical information from:</p><ol type="a"><li>the decay time of light in the cavity</li><li>the absolute laser intensity</li><li>the laser polarisation</li><li>the repetition rate</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">The main benefit of wavelength modulation with lock-in detection is:</p><ol type="a"><li>moving the measurement away from 1/f noise</li><li>increasing laser power</li><li>widening the tuning range</li><li>reducing Doppler broadening</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">For mirrors of reflectivity 99.99 %, the effective path enhancement is about:</p><ol type="a"><li>2×10⁴</li><li>100</li><li>10</li><li>2</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">2f detection is preferred over 1f mainly because it:</p><ol type="a"><li>peaks at line centre and rejects sloping background</li><li>gives a larger raw signal</li><li>needs no lock-in amplifier</li><li>eliminates Doppler broadening</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">A ring-down time falling from 20 µs to 10 µs indicates an absorption coefficient of about:</p><ol type="a"><li>1.7×10⁻⁴ m⁻¹</li><li>1.7×10⁻⁶ m⁻¹</li><li>3.3×10⁻² m⁻¹</li><li>zero</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A direct absorption measurement shows a noise floor of 10⁻³ in fractional transmission that does not improve with longer averaging. Diagnose the cause and propose a fix.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">You need to detect a trace gas at 1 ppb with a cross-section of 10⁻¹⁹ cm² at atmospheric pressure. Estimate the required effective path length and name a suitable technique.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Compare direct absorption, wavelength-modulation and cavity ring-down spectroscopy in terms of physical principle, sensitivity, cost and robustness, and describe a measurement problem best suited to each.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. CRDS is insensitive to shot-to-shot laser power fluctuations.</div><span>T / F</span></div>
  <div class="tf"><div>2. Laser intensity noise generally increases towards low frequencies.</div><span>T / F</span></div>
  <div class="tf"><div>3. A multipass cell improves sensitivity by reducing the cross-section.</div><span>T / F</span></div>
  <div class="tf"><div>4. The optimum wavelength modulation depth is roughly twice the line half-width.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">8</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Detection limit calculation</h4><span class="lvl b">BASIC</span></div><p>For an absorber of cross-section 10⁻¹⁸ cm² measured with α_min = 10⁻⁶ cm⁻¹, compute the minimum detectable number density and convert it to ppm at atmospheric pressure and 300 K.</p><p class="due"><b>Deliverable:</b> The calculation with all unit conversions shown, and the result in both cm⁻³ and ppm.</p></div>
  <div class="hw"><div class="top"><h4>2 · Design an absorption experiment</h4><span class="lvl i">INTERMEDIATE</span></div><p>Choose a gas of interest to environmental monitoring in Iraq, find a suitable absorption line from the HITRAN database, and specify a complete measurement scheme: source, path length, technique, and expected detection limit.</p><p class="due"><b>Deliverable:</b> A one-page design with the chosen line, its parameters and source, and a justified estimate of the detection limit.</p></div>
  <div class="navw"><a href="#w7">← Previous</a><a href="#w9">Next →</a></div>
  <p class="endnote">End of Lecture 8 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w9">
  <div class="hd" style="background:linear-gradient(120deg,#4D7C0F,#A16207)">
    <p class="no">WEEK 09</p>
    <h2>Fluorescence and Luminescence</h2>
    <p>Fluorescence is measured against a dark background rather than against a bright one, and that single fact makes it thousands of times more sensitive than absorption — sensitive enough to see a single molecule.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Distinguish excitation from emission spectra and explain the Stokes shift.</li><li>Define and measure quantum yield, both absolutely and relative to a standard.</li><li>Distinguish static from dynamic quenching using Stern–Volmer analysis with lifetime data.</li><li>Interpret the photoluminescence spectrum of a semiconductor or quantum dot.</li><li>Design a laser-induced fluorescence measurement and identify its main artefacts.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Why fluorescence is so sensitive</h3>
  <p>Absorption asks you to detect a small decrease in a large signal. Fluorescence asks you to detect photons arriving where there should be none. The background is set by scattering and stray light rather than by the source intensity, and with good filtering it approaches zero.</p>
  <div class="call key"><p class="lbl">Key idea</p><p>This is why single-molecule detection is routine in fluorescence and impossible in absorption, and why fluorescence dominates the life sciences. The price is that only a minority of molecules fluoresce usefully, whereas everything absorbs.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Excitation and emission spectra, and the Stokes shift</h3>
  <p>An <b>emission</b> spectrum fixes the excitation wavelength and scans the detection wavelength. An <b>excitation</b> spectrum does the reverse, and normally reproduces the absorption spectrum — if it does not, the sample contains more than one emitting species.</p>
  <p>Emission is red-shifted from absorption because the molecule relaxes vibrationally in the excited state before emitting, and lands on a vibrationally excited level of the ground state. The gap between the absorption and emission maxima is the Stokes shift, and it is what makes fluorescence practical: it allows the excitation light to be filtered out.</p>
  <ul class="chk"><li>A small Stokes shift means difficult filtering and re-absorption of the emission by the sample.</li><li>The mirror-image rule: emission often looks like a reflection of absorption, because the vibrational structures of the two states are similar.</li><li>A large solvent-dependent Stokes shift indicates a large change in dipole moment on excitation, which is the basis of solvatochromic probes.</li></ul>
  <h3 class="s"><i style="background:#047857">3</i>Quantum yield and lifetime</h3>
  <p>The fluorescence quantum yield is the fraction of absorbed photons that are re-emitted, and it is set by the competition between the radiative rate and all non-radiative channels:</p>
  <div class="eq"><b>(9.1)</b>Φ_F = k_r / (k_r + k_nr) = τ / τ_r</div>
  <div class="eq"><b>(9.2)</b>τ = 1 / (k_r + k_nr)</div>
  <p>The observed lifetime τ is always shorter than the purely radiative lifetime τ_r, and the two coincide only when Φ_F = 1. Measuring Φ and τ together separates k_r from k_nr, which is the real goal in photophysics: k_r is a property of the transition, while k_nr reports on the environment.</p>
  <div class="call ex"><p class="lbl">Worked example 9.1</p><p>A dye has Φ_F = 0.25 and a measured lifetime of 2.0 ns. Find k_r, k_nr and the radiative lifetime.</p><ol><li>k_r + k_nr = 1/τ = 5.0×10⁸ s⁻¹.</li><li>k_r = Φ_F/τ = 0.25 / 2.0×10⁻⁹ = 1.25×10⁸ s⁻¹.</li><li>k_nr = 5.0×10⁸ − 1.25×10⁸ = 3.75×10⁸ s⁻¹.</li><li>τ_r = 1/k_r = 8.0 ns.</li></ol><p class="res">Three quarters of the excitation is lost non-radiatively. If the same dye is measured in a rigid matrix at low temperature and Φ rises towards 1 while τ approaches 8 ns, the loss was due to conformational motion.</p></div>
  <h3 class="s"><i style="background:#B45309">4</i>Quenching and Stern–Volmer analysis</h3>
  <p>A quencher reduces fluorescence intensity. Two mechanisms produce the same linear intensity plot but are distinguished by lifetime.</p>
  <div class="eq"><b>(9.3)</b>I₀/I = 1 + K_SV [Q] = 1 + k_q τ₀ [Q]</div>
  <div class="scroll"><table><thead><tr><th></th><th>Dynamic (collisional)</th><th>Static (complex)</th></tr></thead><tbody><tr><td>Mechanism</td><td class="m">collision during the excited state</td><td class="m">non-fluorescent ground-state complex</td></tr><tr><td>Intensity plot I₀/I</td><td class="m">linear</td><td class="m">linear</td></tr><tr><td>Lifetime plot τ₀/τ</td><td class="m">linear, same slope</td><td class="m">flat, equal to 1</td></tr><tr><td>Temperature</td><td class="m">quenching increases</td><td class="m">quenching decreases</td></tr><tr><td>Diagnostic</td><td class="m">k_q approaches the diffusion limit</td><td class="m">k_q would exceed the diffusion limit</td></tr></tbody></table></div>
  <div class="call ex"><p class="lbl">Worked example 9.2</p><p>A fluorophore with τ₀ = 10 ns shows I₀/I = 1.5 at a quencher concentration of 0.01 M, and its lifetime is unchanged. Identify the mechanism.</p><ol><li>K_SV = (1.5 − 1)/0.01 = 50 M⁻¹.</li><li>If dynamic, k_q = K_SV/τ₀ = 50 / 10⁻⁸ = 5×10⁹ M⁻¹s⁻¹, which is at the diffusion limit and therefore physically possible.</li><li>But the measured lifetime did not change, and collisional quenching necessarily shortens the lifetime.</li><li>Therefore the quenching is static: a non-fluorescent complex forms in the ground state.</li></ol><p class="res">This example is the reason lifetime measurement is worth its cost. The intensity data alone are consistent with both mechanisms; the lifetime settles it in one measurement.</p></div>
  <h3 class="s"><i style="background:#BE123C">5</i>Photoluminescence of semiconductors and nanomaterials</h3>
  <p>In a semiconductor, photoluminescence near the band gap reports on the electronic quality of the material. Emission below the gap comes from defect and trap states, and the ratio of band-edge to defect emission is a standard quality metric — in ZnO, for example, the near-UV band-edge peak against the broad green defect band.</p>
  <ul class="chk"><li>Quantum dots emit at a wavelength set by size, with narrow symmetric bands and high quantum yields.</li><li>Surface states dominate non-radiative loss at the nanoscale, which is why core–shell structures raise the yield so dramatically.</li><li>Concentration quenching and inner-filter effects distort spectra at high optical density; keep A below about 0.1 at the excitation wavelength.</li></ul>
  <div class="vs"><div class="bad"><span class="mark">✗ A brighter sample is a better emitter</span>Intensity depends on how much light was absorbed, on geometry and on detector response, so raw brightness compares nothing.</div><div class="good"><span class="mark">✓ Compare quantum yields, not intensities</span>Measure against a standard of known yield under identical conditions, correcting for absorbance and refractive index, or use an integrating sphere for an absolute value.</div></div>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 7</b> — laser-induced fluorescence and photoluminescence: record excitation and emission spectra, determine the Stokes shift and a relative quantum yield.</li><li><b>Session 8</b> — fluorescence quenching: construct a Stern–Volmer plot, extract K_SV and k_q, and state whether the mechanism is static or dynamic with your evidence.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>Fluorescence is measured against a dark background, which is the origin of its extreme sensitivity.</li><li>The Stokes shift arises from vibrational relaxation and makes filtering possible.</li><li>Φ_F = k_r/(k_r+k_nr) = τ/τ_r; measuring Φ and τ together separates radiative from non-radiative rates.</li><li>Static and dynamic quenching give identical intensity plots and are distinguished by lifetime.</li><li>In nanomaterials, defect and surface states control the quantum yield.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Fluorescence</b><span class="ar">التفلور</span><em>Spin-allowed radiative decay from S₁, on a nanosecond scale.</em></div><div><b>Phosphorescence</b><span class="ar">الفسفرة</span><em>Spin-forbidden radiative decay from T₁, much slower.</em></div><div><b>Excitation spectrum</b><span class="ar">طيف الإثارة</span><em>Emission at fixed wavelength recorded while scanning excitation.</em></div><div><b>Stokes shift</b><span class="ar">إزاحة ستوكس</span><em>Separation between absorption and emission maxima.</em></div><div><b>Quantum yield</b><span class="ar">حاصل الكم</span><em>Fraction of absorbed photons re-emitted as fluorescence.</em></div><div><b>Radiative rate</b><span class="ar">المعدل الإشعاعي</span><em>k_r, the rate of photon emission from the excited state.</em></div><div><b>Non-radiative rate</b><span class="ar">المعدل اللاإشعاعي</span><em>k_nr, the combined rate of all loss channels.</em></div><div><b>Stern–Volmer plot</b><span class="ar">مخطط شترن–فولمر</span><em>I₀/I against quencher concentration; slope gives K_SV.</em></div><div><b>Dynamic quenching</b><span class="ar">الإخماد الديناميكي</span><em>Collisional quenching that shortens the lifetime.</em></div><div><b>Static quenching</b><span class="ar">الإخماد الساكن</span><em>Ground-state complex formation; lifetime unchanged.</em></div><div><b>Inner-filter effect</b><span class="ar">أثر المرشح الداخلي</span><em>Distortion from re-absorption at high optical density.</em></div><div><b>Core–shell</b><span class="ar">البنية القلب-الغلاف</span><em>Passivating shell that suppresses surface non-radiative loss.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">If K_SV is finite but the lifetime is unchanged, the quenching is:</p><ol type="a"><li>static</li><li>dynamic</li><li>equally mixed</li><li>absent</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">The Stokes shift arises mainly from:</p><ol type="a"><li>vibrational relaxation before emission</li><li>the Zeeman effect</li><li>collisional broadening</li><li>intersystem crossing</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">A quantum yield of 0.25 with a 2 ns lifetime implies a radiative lifetime of:</p><ol type="a"><li>8 ns</li><li>0.5 ns</li><li>2 ns</li><li>0.25 ns</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Fluorescence is more sensitive than absorption principally because:</p><ol type="a"><li>it is measured against a dark background</li><li>fluorophores absorb more strongly</li><li>the detector is faster</li><li>it needs no laser</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">The green emission band of ZnO is usually attributed to:</p><ol type="a"><li>defect and trap states</li><li>band-edge recombination</li><li>plasmon resonance</li><li>Raman scattering</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">An excitation spectrum does not match the absorption spectrum of the same sample. Give two possible explanations and an experiment to distinguish them.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">A concentrated dye solution shows an emission maximum that is red-shifted and weaker than the dilute solution. Explain and state how to avoid the artefact.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Explain how quantum yield and lifetime measurements together separate radiative from non-radiative processes, and discuss what this reveals about the environment of a fluorophore.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. Static quenching shortens the fluorescence lifetime.</div><span>T / F</span></div>
  <div class="tf"><div>2. The observed lifetime is always shorter than or equal to the radiative lifetime.</div><span>T / F</span></div>
  <div class="tf"><div>3. Dynamic quenching becomes more efficient as temperature rises.</div><span>T / F</span></div>
  <div class="tf"><div>4. An excitation spectrum normally resembles the absorption spectrum.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Stern–Volmer analysis</h4><span class="lvl b">BASIC</span></div><p>From the Session 8 data, plot I₀/I against quencher concentration, extract K_SV and compute k_q using the measured τ₀. State whether k_q is physically plausible.</p><p class="due"><b>Deliverable:</b> The plot with fit, values of K_SV and k_q with units, and a conclusion on the mechanism.</p></div>
  <div class="hw"><div class="top"><h4>2 · Relative quantum yield</h4><span class="lvl i">INTERMEDIATE</span></div><p>Determine the relative quantum yield of a sample against a standard of known yield, correcting for absorbance at the excitation wavelength and for refractive index. List every assumption you make.</p><p class="due"><b>Deliverable:</b> The full calculation with the correction terms shown, the resulting yield, and a list of assumptions and their likely effect on the result.</p></div>
  <div class="navw"><a href="#w8">← Previous</a><a href="#w10">Next →</a></div>
  <p class="endnote">End of Lecture 9 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w10">
  <div class="hd" style="background:linear-gradient(120deg,#A16207,#B45309)">
    <p class="no">WEEK 10</p>
    <h2>Time-Resolved and Ultrafast Spectroscopy</h2>
    <p>Steady-state spectra show where the energy goes. Time-resolved spectra show how fast, and in what order. This lecture covers nanosecond lifetime measurement through to femtosecond pump–probe.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Explain time-correlated single photon counting and extract a lifetime from a decay curve.</li><li>Account for the instrument response function in lifetime fitting.</li><li>Describe the pump–probe configuration and interpret a transient absorption map.</li><li>Relate pulse duration to spectral bandwidth through the time–bandwidth product.</li><li>Interpret carrier dynamics in a nanostructured material.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Time-correlated single photon counting</h3>
  <p>TCSPC does not measure a decay curve directly. It measures, for a single detected photon per excitation pulse, the delay between excitation and detection, and builds a histogram of millions of such events. That histogram is the decay curve.</p>
  <div class="eq"><b>(10.1)</b>I(t) = I₀ exp(−t/τ)   →   ln I(t) linear with slope −1/τ</div>
  <ul class="chk"><li>Photon counts must stay below about one photon per hundred pulses, or the histogram is biased towards early arrivals — the pile-up artefact.</li><li>The time resolution is set by the detector timing jitter, not by the pulse duration; modern detectors reach tens of picoseconds.</li><li>Multi-exponential decays are common and physically meaningful: two lifetimes usually mean two emitting species or two environments.</li></ul>
  <h3 class="s"><i style="background:#0E7490">2</i>The instrument response function</h3>
  <p>The measured decay is the convolution of the true decay with the instrument response function, obtained by measuring a scattering sample with no fluorescence.</p>
  <div class="eq"><b>(10.2)</b>I_meas(t) = ∫ IRF(t′) I_true(t − t′) dt′</div>
  <p>Fitting by iterative reconvolution allows lifetimes several times shorter than the IRF width to be recovered reliably. Fitting the tail alone and ignoring the IRF is a common shortcut that systematically overestimates short lifetimes.</p>
  <div class="vs"><div class="bad"><span class="mark">✗ Fitting only the tail of the decay</span>It looks safe, since the IRF has died away. But it discards most of the photons, inflates the uncertainty, and hides any fast component entirely.</div><div class="good"><span class="mark">✓ Reconvolution fitting</span>Measure the IRF, fit the whole curve by iterative reconvolution, and always inspect the weighted residuals. Structure in the residuals means a component is missing from the model.</div></div>
  <h3 class="s"><i style="background:#047857">3</i>Pump–probe and transient absorption</h3>
  <p>To reach below the nanosecond, electronics are abandoned in favour of optics. One pulse (the pump) excites the sample; a second, delayed pulse (the probe) measures its absorption. The delay is set by the extra distance the probe travels, so time is measured with a translation stage.</p>
  <div class="eq"><b>(10.3)</b>Δt = 2 Δx / c   (double-pass delay line: 1 µm ↔ 6.67 fs)</div>
  <div class="eq"><b>(10.4)</b>ΔA(t, λ) = A_pump-on − A_pump-off</div>
  <ul class="chk"><li><b>Ground-state bleach</b> — negative ΔA where the ground state has been depleted.</li><li><b>Stimulated emission</b> — negative ΔA, red-shifted, decaying with the excited-state lifetime.</li><li><b>Excited-state absorption</b> — positive ΔA where the excited state absorbs further.</li><li>A transient absorption map ΔA(t, λ) is read as a picture of the whole relaxation cascade.</li></ul>
  <h3 class="s"><i style="background:#B45309">4</i>Ultrafast pulses and the time–bandwidth product</h3>
  <p>A short pulse cannot be spectrally narrow. For a Gaussian pulse the minimum product of duration and bandwidth is fixed:</p>
  <div class="eq"><b>(10.5)</b>Δν · Δt ≥ 0.441   (Gaussian transform limit)</div>
  <div class="call ex"><p class="lbl">Worked example 10.1</p><p>What spectral bandwidth, in nm at 800 nm, does a 100 fs transform-limited Gaussian pulse require?</p><ol><li>Δν = 0.441 / 100×10⁻¹⁵ = 4.41×10¹² Hz.</li><li>Δλ = λ² Δν / c = (800×10⁻⁹)² × 4.41×10¹² / 2.998×10⁸.</li><li>Δλ = 6.4×10⁻¹³ × 4.41×10¹² / 2.998×10⁸ = 9.4×10⁻⁹ m.</li><li>Δλ ≈ 9.4 nm.</li></ol><p class="res">This is the fundamental tension of ultrafast spectroscopy: better time resolution necessarily costs spectral resolution. A 10 fs pulse at 800 nm spans about 94 nm and cannot resolve any structure narrower than that.</p></div>
  <p>Pulses are characterised by autocorrelation, FROG or SPIDER, since no electronic detector is fast enough to measure them directly. Dispersion in every optical element stretches the pulse, so compensation with prism or chirped-mirror pairs is a routine part of the alignment.</p>
  <h3 class="s"><i style="background:#BE123C">5</i>Carrier dynamics in nanostructures</h3>
  <p>In a semiconductor nanostructure the relaxation cascade after excitation has several well-separated stages, and ultrafast spectroscopy is the only way to watch them.</p>
  <div class="scroll"><table><thead><tr><th>Process</th><th>Timescale</th><th>Signature</th></tr></thead><tbody><tr><td>Carrier thermalisation</td><td class="m">10–100 fs</td><td class="m">spectral reshaping of the bleach</td></tr><tr><td>Carrier cooling</td><td class="m">0.1–10 ps</td><td class="m">narrowing towards the band edge</td></tr><tr><td>Trapping at surface states</td><td class="m">1–100 ps</td><td class="m">loss of band-edge bleach</td></tr><tr><td>Radiative recombination</td><td class="m">1–100 ns</td><td class="m">decay of emission</td></tr><tr><td>Auger recombination</td><td class="m">10–100 ps</td><td class="m">intensity-dependent fast decay</td></tr></tbody></table></div>
  <div class="call key"><p class="lbl">Key idea</p><p>Auger recombination is the reason quantum-dot lasers are difficult: at the high excitation densities needed for gain, multiply excited dots decay non-radiatively in tens of picoseconds, faster than they can be made to lase.</p></div>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li>The Institute does not run a femtosecond pump–probe experiment in this course, but the lifetime concepts appear directly in Session 7.</li><li>When you record a photoluminescence decay, fit it with a single exponential and then with two, and use the residuals to decide which model the data actually support.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>TCSPC builds a decay histogram from single photons; pile-up must be avoided by keeping count rates low.</li><li>Always fit with the instrument response function by reconvolution rather than fitting the tail alone.</li><li>Pump–probe converts a distance on a delay stage into femtosecond time resolution.</li><li>A transient absorption map contains bleach, stimulated emission and excited-state absorption together.</li><li>ΔνΔt ≥ 0.441 sets the unavoidable trade between time and spectral resolution.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>TCSPC</b><span class="ar">عدّ الفوتون المفرد المرتبط زمنياً</span><em>Lifetime measurement by histogramming single-photon arrival times.</em></div><div><b>Instrument response function</b><span class="ar">دالة استجابة الجهاز</span><em>The measured response to an infinitely short pulse.</em></div><div><b>Reconvolution fitting</b><span class="ar">الملاءمة بإعادة الالتفاف</span><em>Fitting the decay model convolved with the IRF.</em></div><div><b>Pile-up</b><span class="ar">التكدّس</span><em>Bias towards early photons when the count rate is too high.</em></div><div><b>Pump–probe</b><span class="ar">الضخّ والجس</span><em>Two-pulse technique with optical delay setting the time axis.</em></div><div><b>Transient absorption</b><span class="ar">الامتصاص العابر</span><em>Change in absorbance induced by the pump pulse.</em></div><div><b>Ground-state bleach</b><span class="ar">تبييض الحالة الأرضية</span><em>Negative ΔA from depletion of the ground state.</em></div><div><b>Excited-state absorption</b><span class="ar">امتصاص الحالة المثارة</span><em>Positive ΔA from further absorption by excited molecules.</em></div><div><b>Time–bandwidth product</b><span class="ar">حاصل ضرب الزمن والنطاق</span><em>Minimum product of pulse duration and spectral width.</em></div><div><b>Chirp</b><span class="ar">التغريد</span><em>Time dependence of the instantaneous frequency within a pulse.</em></div><div><b>Auger recombination</b><span class="ar">إعادة اتحاد أوجيه</span><em>Non-radiative three-carrier process, dominant at high excitation.</em></div><div><b>Autocorrelation</b><span class="ar">الارتباط الذاتي</span><em>Optical method of estimating pulse duration.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">TCSPC measures:</p><ol type="a"><li>the distribution of single-photon arrival times</li><li>total fluorescence intensity</li><li>the absorption spectrum</li><li>pulse polarisation</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">In pump–probe, the delay is normally produced by:</p><ol type="a"><li>an optical delay line</li><li>changing the wavelength</li><li>changing the laser power</li><li>rotating a polariser</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">A negative ΔA signal at the absorption wavelength usually indicates:</p><ol type="a"><li>ground-state bleach</li><li>excited-state absorption</li><li>detector saturation</li><li>scattering</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">The transform limit for a Gaussian pulse is:</p><ol type="a"><li>ΔνΔt ≥ 0.441</li><li>ΔνΔt ≥ 1</li><li>ΔνΔt ≥ 0.1</li><li>no limit exists</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">Pile-up in TCSPC is avoided by:</p><ol type="a"><li>keeping the count rate well below one photon per pulse</li><li>increasing laser power</li><li>using a slower detector</li><li>widening the spectral window</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A decay fitted with a single exponential leaves clear structure in the weighted residuals at early times. What does this indicate and how should the analysis proceed?</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">A colleague reports a 20 ps lifetime measured with an instrument whose IRF is 200 ps wide, fitting only the tail. Comment on the reliability of the result.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Explain how pump–probe spectroscopy achieves femtosecond time resolution with no fast electronics, and describe how a transient absorption map is interpreted in terms of the relaxation cascade of a nanomaterial.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The time resolution of TCSPC is limited mainly by detector timing jitter.</div><span>T / F</span></div>
  <div class="tf"><div>2. A 10 fs pulse at 800 nm has a bandwidth of only a few nanometres.</div><span>T / F</span></div>
  <div class="tf"><div>3. Auger recombination becomes more important at high excitation density.</div><span>T / F</span></div>
  <div class="tf"><div>4. The instrument response function should be measured with a scattering sample.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Fit a decay</h4><span class="lvl b">BASIC</span></div><p>Using the photoluminescence decay from Session 7, fit single- and double-exponential models, report the lifetimes with uncertainties, and compare the reduced chi-squared and residuals of the two fits.</p><p class="due"><b>Deliverable:</b> Both fits overlaid on the data, the residual plots, and a justified choice of model.</p></div>
  <div class="hw"><div class="top"><h4>2 · Design a pump–probe experiment</h4><span class="lvl i">INTERMEDIATE</span></div><p>Specify a pump–probe measurement of carrier dynamics in a semiconductor nanomaterial of your choice: pump wavelength, probe range, delay range and step, and the processes you expect to resolve at each timescale.</p><p class="due"><b>Deliverable:</b> A one-page experimental design with a table of expected processes and their timescales.</p></div>
  <div class="navw"><a href="#w9">← Previous</a><a href="#w11">Next →</a></div>
  <p class="endnote">End of Lecture 10 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w11">
  <div class="hd" style="background:linear-gradient(120deg,#B45309,#C2410C)">
    <p class="no">WEEK 11</p>
    <h2>Raman Spectroscopy</h2>
    <p>Raman measures a scattering process rather than an absorption, which frees it from the water problem, lets it work through glass, and makes it the natural partner of infrared spectroscopy.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Explain Raman scattering classically through the polarisability and quantum-mechanically through virtual states.</li><li>Account for the intensity ratio of Stokes and anti-Stokes lines and use it as a thermometer.</li><li>Apply the mutual exclusion rule and predict Raman activity from symmetry.</li><li>Describe resonance Raman, SERS and CARS and state what each is for.</li><li>Recognise and suppress the fluorescence background in a Raman measurement.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>The classical picture: modulated polarisability</h3>
  <p>An incident field induces a dipole in the molecule. If the polarisability itself oscillates as the molecule vibrates, the induced dipole acquires sidebands at the sum and difference of the optical and vibrational frequencies, and it is those sidebands that are the Raman lines.</p>
  <div class="eq"><b>(11.1)</b>p = α E ,  α(t) = α₀ + (∂α/∂Q) Q₀ cos(2π ν_vib t)</div>
  <div class="eq"><b>(11.2)</b>ν̃_scattered = ν̃₀ ∓ ν̃_vib   (Stokes − , anti-Stokes +)</div>
  <p>The condition for Raman activity follows immediately: the polarisability must change during the vibration.</p>
  <div class="eq"><b>(11.3)</b>Raman active  ⇔  ∂α/∂Q ≠ 0 ;  I ∝ ν⁴</div>
  <div class="call key"><p class="lbl">Key idea</p><p>The Raman shift is a difference, so it is independent of the excitation wavelength. A band at 1000 cm⁻¹ appears 1000 cm⁻¹ from the laser line whether you excite at 532 nm or 785 nm. This is why Raman shifts are universally tabulated in wavenumbers.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Stokes, anti-Stokes and temperature</h3>
  <p>Anti-Stokes scattering starts from a vibrationally excited level, whose population follows Boltzmann. The intensity ratio therefore measures the temperature of the sample directly, with no calibration and no contact.</p>
  <div class="eq"><b>(11.4)</b>I_aS / I_S = [(ν̃₀+ν̃_v)/(ν̃₀−ν̃_v)]⁴ · exp(−h c ν̃_v / kT)</div>
  <div class="call ex"><p class="lbl">Worked example 11.1</p><p>For a 1000 cm⁻¹ mode excited at 532 nm (18 797 cm⁻¹) at 300 K, compute the anti-Stokes to Stokes ratio.</p><ol><li>Boltzmann factor: exp(−1000/208.5) = exp(−4.796) = 8.24×10⁻³.</li><li>Frequency factor: [(18797+1000)/(18797−1000)]⁴ = (19797/17797)⁴ = (1.1124)⁴ = 1.531.</li><li>Ratio = 1.531 × 8.24×10⁻³ = 1.26×10⁻².</li></ol><p class="res">Anti-Stokes is about eighty times weaker at room temperature, which is why spectra are almost always recorded on the Stokes side. At 1000 K the Boltzmann factor rises to 0.24 and anti-Stokes becomes easily measurable — the basis of non-contact Raman thermometry in flames and plasmas.</p></div>
  <h3 class="s"><i style="background:#047857">3</i>Symmetry, selection rules and mutual exclusion</h3>
  <p>Infrared activity requires a changing dipole moment, Raman activity a changing polarisability. In a molecule with a centre of symmetry these two conditions are mutually exclusive: no mode can be both IR and Raman active.</p>
  <div class="vs"><div class="bad"><span class="mark">✗ Raman and IR give the same information</span>They are often described as interchangeable vibrational techniques, which leads people to run only one.</div><div class="good"><span class="mark">✓ They are complementary by symmetry</span>CO₂ has an IR-inactive symmetric stretch that is strongly Raman active, and IR-active bending and asymmetric modes that are Raman inactive. Running both is the only way to see all the fundamentals of a centrosymmetric molecule.</div></div>
  <ul class="chk"><li>Symmetric, non-polar vibrations tend to be strong in Raman: C–C, C=C, S–S, ring breathing modes.</li><li>Polar bonds tend to be strong in IR: O–H, C=O, C–F.</li><li>Water is a weak Raman scatterer and a ferocious IR absorber, which is why Raman is the technique of choice for aqueous and biological samples.</li></ul>
  <h3 class="s"><i style="background:#B45309">4</i>Enhanced and nonlinear variants</h3>
  <div class="scroll"><table><thead><tr><th>Technique</th><th>Principle</th><th>Gain</th><th>Cost</th></tr></thead><tbody><tr><td>Resonance Raman</td><td class="m">excite within an electronic band</td><td class="m">10³–10⁶</td><td class="m">fluorescence, photodamage</td></tr><tr><td>SERS</td><td class="m">plasmonic field enhancement at a metal surface</td><td class="m">10⁶–10⁸</td><td class="m">substrate reproducibility</td></tr><tr><td>CARS</td><td class="m">coherent four-wave mixing</td><td class="m">large, directional</td><td class="m">complex laser system</td></tr><tr><td>Micro-Raman</td><td class="m">confocal microscope objective</td><td class="m">spatial, ~1 µm</td><td class="m">small sampling volume</td></tr></tbody></table></div>
  <p>Spontaneous Raman is extraordinarily weak — of order one scattered photon in 10⁸ — so every practical advance in the field has been about enhancement. SERS pushed detection to the single-molecule level by exploiting the intense local fields at nanoscale metal features, and it is the direct link between this lecture and the nanomaterials work of the Institute.</p>
  <h3 class="s"><i style="background:#BE123C">5</i>The fluorescence problem</h3>
  <p>The single most common reason a Raman measurement fails is a fluorescence background from the sample or its impurities, which can exceed the Raman signal by orders of magnitude. Because fluorescence occurs at fixed wavelengths while the Raman shift is fixed relative to the laser, changing the excitation wavelength separates them.</p>
  <ul class="chk"><li><b>Move to longer excitation</b> — 785 or 1064 nm usually falls below the electronic absorption. The cost is the ν⁴ intensity loss.</li><li><b>Photobleach</b> — illuminate before measuring, at the risk of damaging the sample.</li><li><b>Shifted-excitation Raman difference</b> — record at two slightly different excitation wavelengths and subtract; the fluorescence cancels, the Raman shifts.</li><li><b>Baseline correction</b> — acceptable for a smooth background, but never a substitute for a good measurement.</li></ul>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 9</b> — Raman spectroscopy of standard samples: assign the modes and compare directly with the FTIR spectra from Session 6.</li><li>For at least one sample, identify a mode that appears in one technique and not the other, and explain the difference from the symmetry of the vibration. If you meet a fluorescence background, state which of the strategies above you used and why.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>Raman scattering arises from the modulation of polarisability, so activity requires ∂α/∂Q ≠ 0.</li><li>The Raman shift is independent of excitation wavelength; intensity scales as ν⁴.</li><li>The anti-Stokes to Stokes ratio is a direct, non-contact thermometer.</li><li>In centrosymmetric molecules IR and Raman activity are mutually exclusive, making the techniques complementary.</li><li>Resonance Raman, SERS and CARS all address the fundamental weakness of the spontaneous effect.</li><li>Fluorescence background is the usual practical obstacle, and changing excitation wavelength is the usual cure.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Raman scattering</b><span class="ar">تشتت رامان</span><em>Inelastic scattering shifted by a vibrational frequency.</em></div><div><b>Rayleigh scattering</b><span class="ar">تشتت رايلي</span><em>Elastic scattering at the laser wavelength; must be filtered out.</em></div><div><b>Stokes line</b><span class="ar">خط ستوكس</span><em>Scattered light at lower frequency than the laser.</em></div><div><b>Anti-Stokes line</b><span class="ar">خط مضاد ستوكس</span><em>Scattered light at higher frequency; weaker, temperature sensitive.</em></div><div><b>Polarisability</b><span class="ar">قابلية الاستقطاب</span><em>α, the ease with which the electron cloud is distorted by a field.</em></div><div><b>Mutual exclusion rule</b><span class="ar">قاعدة الاستبعاد المتبادل</span><em>In centrosymmetric molecules no mode is both IR and Raman active.</em></div><div><b>Resonance Raman</b><span class="ar">رامان الرنيني</span><em>Enhancement obtained by exciting within an electronic absorption band.</em></div><div><b>SERS</b><span class="ar">رامان المعزّز سطحياً</span><em>Surface-enhanced Raman using plasmonic metal nanostructures.</em></div><div><b>CARS</b><span class="ar">رامان المضاد لستوكس المترابط</span><em>Coherent anti-Stokes Raman scattering; strong and directional.</em></div><div><b>Notch filter</b><span class="ar">مرشح الحزّ</span><em>Filter blocking the laser line while passing the Raman shifts.</em></div><div><b>Raman shift</b><span class="ar">إزاحة رامان</span><em>Difference in wavenumber between laser and scattered light.</em></div><div><b>Photobleaching</b><span class="ar">التبييض الضوئي</span><em>Destruction of fluorescent species by prolonged illumination.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">The mutual exclusion rule applies to molecules that:</p><ol type="a"><li>possess a centre of symmetry</li><li>are linear</li><li>contain heavy atoms</li><li>are polar</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">Anti-Stokes lines are weaker than Stokes lines because:</p><ol type="a"><li>excited vibrational levels are less populated</li><li>they carry less energy</li><li>nonlinear effects forbid them</li><li>detectors are blind to them</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">Raman scattered intensity scales approximately as:</p><ol type="a"><li>ν⁴</li><li>ν</li><li>ν²</li><li>1/ν</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Changing the excitation wavelength from 532 nm to 785 nm moves a Raman band:</p><ol type="a"><li>not at all in wavenumber shift</li><li>to a different Raman shift</li><li>out of the spectrum</li><li>to the anti-Stokes side</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">SERS achieves its enhancement mainly through:</p><ol type="a"><li>plasmonic local field enhancement</li><li>higher laser power</li><li>longer integration times</li><li>cooling the sample</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">A Raman spectrum recorded at 532 nm is swamped by a smooth rising background. Identify the cause and give two distinct experimental remedies with their drawbacks.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">A vibrational mode of a molecule appears strongly in the FTIR spectrum and is completely absent from the Raman spectrum. What does this tell you about the molecule and the mode?</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Discuss the complementarity of infrared and Raman spectroscopy from the standpoint of symmetry, and explain why a complete vibrational analysis of a centrosymmetric molecule requires both.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The Raman shift depends on the excitation wavelength.</div><span>T / F</span></div>
  <div class="tf"><div>2. Water interferes far less in Raman than in infrared spectroscopy.</div><span>T / F</span></div>
  <div class="tf"><div>3. The anti-Stokes to Stokes ratio can be used to measure temperature.</div><span>T / F</span></div>
  <div class="tf"><div>4. Spontaneous Raman scattering is an intrinsically weak process.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · IR and Raman side by side</h4><span class="lvl b">BASIC</span></div><p>For CO₂, H₂O and N₂, list every fundamental mode and mark it IR active, Raman active, both or neither, with the symmetry reasoning for each.</p><p class="due"><b>Deliverable:</b> A table of modes with activities and a one-line justification per mode.</p></div>
  <div class="hw"><div class="top"><h4>2 · Raman thermometry</h4><span class="lvl i">INTERMEDIATE</span></div><p>Derive the anti-Stokes to Stokes ratio as a function of temperature for a 1332 cm⁻¹ mode excited at 532 nm, plot it from 300 K to 1500 K, and state the temperature range over which the method is practical.</p><p class="due"><b>Deliverable:</b> The derivation, the plot, and a justified statement of the usable range with its limiting factors.</p></div>
  <div class="navw"><a href="#w10">← Previous</a><a href="#w12">Next →</a></div>
  <p class="endnote">End of Lecture 11 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w12">
  <div class="hd" style="background:linear-gradient(120deg,#C2410C,#BE123C)">
    <p class="no">WEEK 12</p>
    <h2>Laser-Induced Breakdown Spectroscopy</h2>
    <p>A single focused pulse ablates a microgram of any material, creates a plasma, and lets you read its elemental composition from the emission. No sample preparation, no vacuum, and it works at a distance.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Describe plasma formation and evolution after a nanosecond laser pulse.</li><li>Construct a Boltzmann plot and extract the plasma temperature.</li><li>Determine electron density from Stark broadening.</li><li>Test the assumption of local thermodynamic equilibrium with the McWhirter criterion.</li><li>Distinguish calibration-based from calibration-free LIBS and state when each applies.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Plasma formation and temporal evolution</h3>
  <p>A pulse of 10⁹ W/cm² or more focused onto a surface ablates material, ionises the vapour and forms a plasma at 10 000 to 20 000 K. The plasma then evolves rapidly, and the timing of the measurement matters as much as any optical parameter.</p>
  <div class="scroll"><table><thead><tr><th>Delay after pulse</th><th>Dominant emission</th><th>Use</th></tr></thead><tbody><tr><td>0–100 ns</td><td class="m">continuum (bremsstrahlung, recombination)</td><td class="m">avoid: no line information</td></tr><tr><td>0.5–5 µs</td><td class="m">ionic and atomic lines</td><td class="m">the analytical window</td></tr><tr><td>5–20 µs</td><td class="m">neutral atomic lines, cooling plasma</td><td class="m">low-excitation species</td></tr><tr><td>> 50 µs</td><td class="m">molecular bands, condensation</td><td class="m">molecular LIBS</td></tr></tbody></table></div>
  <div class="call key"><p class="lbl">Key idea</p><p>This is why an ICCD with nanosecond gating is essential rather than convenient. Recording without a gate integrates the intense early continuum and buries every analytical line under it.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Plasma temperature from the Boltzmann plot</h3>
  <p>If the level populations follow Boltzmann, the emitted intensity of a line carries the upper-level energy in its exponent. Rearranging gives a straight line whose slope is the inverse temperature.</p>
  <div class="eq"><b>(12.1)</b>I_ki = (h c / 4π λ) A_ki N_k ,  N_k ∝ g_k exp(−E_k/kT)</div>
  <div class="eq"><b>(12.2)</b>ln( I λ / g A ) = − E_k / (k_B T) + C</div>
  <div class="call ex"><p class="lbl">Worked example 12.1</p><p>Two Al I lines are measured: 394.4 nm (E = 3.14 eV, gA = 1.87×10⁸ s⁻¹, I = 1200) and 309.3 nm (E = 4.02 eV, gA = 2.32×10⁸ s⁻¹, I = 300). Find the plasma temperature.</p><ol><li>Form the ratio R = (I₁λ₁ g₂A₂)/(I₂λ₂ g₁A₁) = (1200 × 394.4 × 2.32)/(300 × 309.3 × 1.87).</li><li>Numerator = 1200 × 394.4 = 4.733×10⁵; × 2.32 = 1.098×10⁶.</li><li>Denominator = 300 × 309.3 = 9.279×10⁴; × 1.87 = 1.735×10⁵.</li><li>R = 6.33, so ln R = 1.845, and ΔE = 4.02 − 3.14 = 0.88 eV.</li><li>T = ΔE / (k ln R) = 0.88 / (8.617×10⁻⁵ × 1.845) = 5.5×10³ K.</li></ol><p class="res">Two lines give a number; they do not give a check. Use six or more lines spanning at least 2 eV of upper-level energy, plot them, and judge the fit by its scatter. A poor straight line is itself the result: it means the plasma is not in equilibrium.</p></div>
  <ul class="chk"><li>Choose lines from the same element and the same ionisation stage.</li><li>Span as wide a range of upper-level energies as possible; a narrow span makes the slope hopelessly uncertain.</li><li>Avoid resonance lines, which are prone to self-absorption and will flatten your plot.</li><li>Use transition probabilities from a single reliable source; mixing databases introduces scatter that looks like physics.</li></ul>
  <h3 class="s"><i style="background:#047857">3</i>Electron density from Stark broadening</h3>
  <p>Charged particles in the plasma produce fluctuating microfields that broaden the lines. For non-hydrogenic lines the Stark width is essentially proportional to the electron density, with the electron-impact parameter w tabulated for common lines.</p>
  <div class="eq"><b>(12.3)</b>Δλ_Stark ≈ 2 w ( N_e / 10¹⁶ )   [nm]</div>
  <p>The measured width must first be corrected for the instrumental and Doppler contributions, which is exactly the Voigt deconvolution of Week 3. The hydrogen Balmer alpha and beta lines are the standard choice where hydrogen is present, since their Stark parameters are known with high accuracy.</p>
  <h3 class="s"><i style="background:#B45309">4</i>Local thermodynamic equilibrium</h3>
  <p>Everything above assumes local thermodynamic equilibrium: that collisions are frequent enough to keep the level populations Boltzmann-distributed at a single temperature. The McWhirter criterion sets a necessary minimum electron density for this to hold.</p>
  <div class="eq"><b>(12.4)</b>N_e ≥ 1.6×10¹² T^(1/2) (ΔE)³   [cm⁻³, K, eV]</div>
  <div class="vs"><div class="bad"><span class="mark">✗ Reporting a temperature without checking LTE</span>A Boltzmann plot always yields a slope, and therefore always yields a number that can be called a temperature, whether or not the plasma is in equilibrium.</div><div class="good"><span class="mark">✓ Test, then report</span>Check the McWhirter criterion with your measured N_e, confirm the plot is linear across a wide energy span, and state both checks in the report. A necessary condition is not sufficient, so also confirm that the plasma is optically thin.</div></div>
  <h3 class="s"><i style="background:#BE123C">5</i>Quantitative analysis: calibration and calibration-free LIBS</h3>
  <p>Conventional quantitative LIBS uses matrix-matched standards to build a calibration curve of line intensity against concentration. This works well but requires standards resembling the unknown, which is often impossible for archaeological, geological or forensic samples.</p>
  <p>Calibration-free LIBS instead uses the Boltzmann plot itself: with T and N_e known, and assuming stoichiometric ablation, optical thinness and LTE, the intercepts of the Boltzmann plots for each element give the relative concentrations without any standard at all.</p>
  <ul class="chk"><li><b>Stoichiometric ablation</b> — the plasma composition must match the sample; requires sufficient irradiance.</li><li><b>Optical thinness</b> — check by comparing the measured intensity ratio of two lines from the same upper level with their transition probability ratio.</li><li><b>Self-absorption</b> — a flat-topped or dipped strong line is the classic warning sign; drop that line from the analysis.</li></ul>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 10</b> — LIBS of metallic alloys: qualitative elemental identification from line positions.</li><li><b>Session 11</b> — plasma diagnostics: construct a Boltzmann plot for the electron temperature and use Stark broadening for the electron density. Report both with uncertainties and include the McWhirter check.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>The plasma evolves in microseconds; gated detection in the 0.5–5 µs window is essential.</li><li>A Boltzmann plot of ln(Iλ/gA) against E_k has slope −1/kT and gives the plasma temperature.</li><li>Stark broadening gives the electron density after correcting for instrumental and Doppler widths.</li><li>The McWhirter criterion is a necessary check on LTE and must be reported alongside the temperature.</li><li>Calibration-free LIBS removes the need for matrix-matched standards at the cost of several strong assumptions.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Ablation</b><span class="ar">الاجتثاث</span><em>Removal of material from a surface by an intense laser pulse.</em></div><div><b>Bremsstrahlung</b><span class="ar">إشعاع الكبح</span><em>Continuum radiation from electrons decelerating near ions.</em></div><div><b>Gate delay</b><span class="ar">تأخير البوابة</span><em>Time between laser pulse and start of detector acquisition.</em></div><div><b>Boltzmann plot</b><span class="ar">مخطط بولتزمان</span><em>Linearised intensity plot whose slope gives the temperature.</em></div><div><b>Transition probability</b><span class="ar">احتمالية الانتقال</span><em>A_ki, needed for every quantitative LIBS calculation.</em></div><div><b>Stark broadening</b><span class="ar">اتساع شتارك</span><em>Line broadening by plasma microfields; measures electron density.</em></div><div><b>Electron density</b><span class="ar">كثافة الإلكترونات</span><em>N_e, the number of free electrons per unit volume.</em></div><div><b>LTE</b><span class="ar">الاتزان الحراري الموضعي</span><em>Local thermodynamic equilibrium; populations Boltzmann at one temperature.</em></div><div><b>McWhirter criterion</b><span class="ar">شرط ماكويرتر</span><em>Necessary minimum electron density for LTE to hold.</em></div><div><b>Self-absorption</b><span class="ar">الامتصاص الذاتي</span><em>Reabsorption of emitted light within the plasma, flattening strong lines.</em></div><div><b>Optically thin</b><span class="ar">رقيق بصرياً</span><em>Condition in which emitted radiation escapes without reabsorption.</em></div><div><b>Calibration-free LIBS</b><span class="ar">LIBS بلا معايرة</span><em>Quantitative analysis from plasma parameters without standards.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">In a Boltzmann plot the plasma temperature is obtained from:</p><ol type="a"><li>the slope</li><li>the intercept</li><li>the peak area</li><li>the line width</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">Stark broadening in LIBS is used principally to determine:</p><ol type="a"><li>electron density</li><li>temperature</li><li>absolute concentration</li><li>refractive index</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">The McWhirter criterion checks:</p><ol type="a"><li>whether LTE can hold</li><li>the linearity of calibration</li><li>the wavelength calibration</li><li>detector health</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">An ICCD is preferred in LIBS because it allows:</p><ol type="a"><li>nanosecond time gating</li><li>lower cost</li><li>infrared sensitivity</li><li>higher spectral resolution</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">A strong line with a flattened or dipped top most likely indicates:</p><ol type="a"><li>self-absorption</li><li>Stark broadening</li><li>poor focus</li><li>detector saturation only</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Your Boltzmann plot has considerable scatter and the fitted temperature has an uncertainty of 40 %. List three concrete causes and the corresponding remedies.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">You measure the same alloy with two different gate delays and obtain two different temperatures. Explain why this is expected rather than an error.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Set out the complete chain of reasoning and assumptions that leads from a set of measured LIBS line intensities to a reported elemental composition, identifying the point at which each assumption could fail.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The continuum emission is strongest immediately after the laser pulse.</div><span>T / F</span></div>
  <div class="tf"><div>2. Lines used in a Boltzmann plot should come from different elements for better coverage.</div><span>T / F</span></div>
  <div class="tf"><div>3. The McWhirter criterion is a sufficient condition for local thermodynamic equilibrium.</div><span>T / F</span></div>
  <div class="tf"><div>4. Calibration-free LIBS assumes stoichiometric ablation.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Boltzmann plot from real data</h4><span class="lvl i">INTERMEDIATE</span></div><p>Using at least six lines of one element from the Session 11 spectrum, build a Boltzmann plot, fit it, and report the temperature with an uncertainty derived from the fit. Tabulate every line with its λ, E_k, g and A and cite the database used.</p><p class="due"><b>Deliverable:</b> The line table with sources, the Boltzmann plot with its fit, and T with its uncertainty.</p></div>
  <div class="hw"><div class="top"><h4>2 · Full plasma diagnostic</h4><span class="lvl a">ADVANCED</span></div><p>For the same spectrum, determine N_e from the Stark width of a suitable line after correcting for instrumental broadening, then test the McWhirter criterion using your measured T and the largest energy gap in your line set.</p><p class="due"><b>Deliverable:</b> The corrected width, N_e with uncertainty, the McWhirter evaluation, and a clear statement of whether LTE is supported.</p></div>
  <div class="navw"><a href="#w11">← Previous</a><a href="#w13">Next →</a></div>
  <p class="endnote">End of Lecture 12 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w13">
  <div class="hd" style="background:linear-gradient(120deg,#BE123C,#9F1239)">
    <p class="no">WEEK 13</p>
    <h2>Nonlinear and High-Resolution Spectroscopy</h2>
    <p>Doppler broadening hides three orders of magnitude of detail. This lecture covers the techniques that defeat it, and the nonlinear processes that open transitions and spectral regions no single-photon method can reach.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Explain saturation spectroscopy and the origin of the Lamb dip.</li><li>Describe polarisation spectroscopy and its advantage in signal-to-noise.</li><li>Explain how counter-propagating two-photon excitation eliminates Doppler broadening entirely.</li><li>Describe photoacoustic and photothermal detection and state when they are preferred.</li><li>State the phase-matching condition for second-harmonic and sum-frequency generation.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Saturation spectroscopy and the Lamb dip</h3>
  <p>In a Doppler-broadened sample, a monochromatic laser at frequency ν interacts only with the velocity group whose Doppler shift brings it into resonance. A strong pump beam depletes that group — it burns a hole in the velocity distribution. A counter-propagating weak probe at the same frequency addresses the opposite velocity group, so normally it sees an unbleached sample.</p>
  <p>The exception is at line centre. There both beams address the same group, those with essentially zero velocity along the beam. The probe then finds the sample already saturated and is absorbed less, producing a narrow dip at the centre of the Doppler profile — the Lamb dip, whose width approaches the natural linewidth.</p>
  <div class="eq"><b>(13.1)</b>I_sat = h ν / (σ τ) ;  dip width → Δν_N</div>
  <div class="call key"><p class="lbl">Key idea</p><p>The improvement is dramatic: a sodium line 1.7 GHz wide by Doppler yields a Lamb dip of about 10 MHz, a gain of more than two orders of magnitude in resolution — enough to resolve hyperfine structure that is completely invisible in the Doppler profile.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Polarisation spectroscopy</h3>
  <p>A refinement of saturation spectroscopy. A circularly polarised pump makes the sample birefringent for the counter-propagating probe, but only for the zero-velocity group. The probe is placed between crossed polarisers, so the detector sees darkness except exactly on resonance.</p>
  <ul class="chk"><li>The measurement is background free, so the signal-to-noise is far better than in saturation spectroscopy.</li><li>The line shape is dispersive, giving a natural zero crossing at line centre — ideal as an error signal for locking a laser.</li><li>It requires less pump power than saturation spectroscopy for the same signal.</li></ul>
  <h3 class="s"><i style="background:#047857">3</i>Two-photon and multiphoton spectroscopy</h3>
  <p>When an atom absorbs two counter-propagating photons simultaneously, the two Doppler shifts have opposite signs and cancel exactly in the sum. Every atom in the sample contributes to the same resonance, whatever its velocity.</p>
  <div class="eq"><b>(13.2)</b>ν₁(1 − v/c) + ν₂(1 + v/c) = ν₁ + ν₂   for ν₁ = ν₂</div>
  <p>The result is a Doppler-free signal from the whole sample rather than from a single velocity group, which recovers much of the intensity lost in saturation methods. Two-photon transitions also obey different selection rules — parity is preserved rather than changed — so they reach states that single-photon spectroscopy simply cannot address, such as S → S and S → D transitions.</p>
  <div class="vs"><div class="bad"><span class="mark">✗ Nonlinear spectroscopy just means using a stronger laser</span>Power alone gives power broadening and photodamage, not resolution.</div><div class="good"><span class="mark">✓ It means using geometry and polarisation</span>The resolution in every technique here comes from the counter-propagating arrangement and the polarisation selection, not from intensity. Intensity is what enables the effect; the geometry is what defeats the Doppler width.</div></div>
  <h3 class="s"><i style="background:#B45309">4</i>Photoacoustic and photothermal detection</h3>
  <p>Instead of measuring the transmitted light, these methods measure what the absorbed energy does to the sample. Modulated absorption produces periodic heating, which generates a pressure wave detected by a microphone, or a refractive-index gradient detected by a probe beam.</p>
  <ul class="chk"><li>The signal is proportional to absorbed power, so it is zero when there is no absorption — a genuinely background-free measurement, in contrast to direct absorption.</li><li>Ideal for weakly absorbing, scattering or opaque samples where transmission measurements fail.</li><li>Quartz-enhanced photoacoustic spectroscopy replaces the microphone with a quartz tuning fork, giving a very high quality factor and excellent immunity to environmental noise.</li></ul>
  <h3 class="s"><i style="background:#BE123C">5</i>Second-harmonic and sum-frequency generation</h3>
  <p>In a medium without inversion symmetry the polarisation acquires a term quadratic in the field, generating light at the sum of the input frequencies. Efficient conversion requires that the fundamental and generated waves stay in phase throughout the crystal.</p>
  <div class="eq"><b>(13.3)</b>P = ε₀( χ⁽¹⁾E + χ⁽²⁾E² + χ⁽³⁾E³ + … )</div>
  <div class="eq"><b>(13.4)</b>Δk = 2k_ω − k_2ω = 0   (phase matching)</div>
  <p>Because χ⁽²⁾ vanishes in centrosymmetric media, second-harmonic and sum-frequency generation are intrinsically surface sensitive: the signal comes only from the interface where symmetry is broken. Sum-frequency generation spectroscopy is therefore one of the very few techniques able to record the vibrational spectrum of a single monolayer at a buried interface.</p>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li>These techniques are beyond the instrumentation of this course, but two of their ingredients appear in it directly.</li><li>The line-shape fitting of Session 12 is what tells you how much of a measured width is instrumental, Doppler and natural — precisely the decomposition that motivates every sub-Doppler technique here.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>Saturation spectroscopy burns a hole in the velocity distribution and reveals a Lamb dip of near-natural width at line centre.</li><li>Polarisation spectroscopy makes the same measurement background free and provides a dispersive locking signal.</li><li>Counter-propagating two-photon excitation cancels the Doppler shift for every atom, not just one velocity group.</li><li>Photoacoustic detection measures absorbed energy directly and is background free.</li><li>Second-order nonlinear processes require broken inversion symmetry and phase matching, which makes them surface specific.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Saturation spectroscopy</b><span class="ar">طيفية الإشباع</span><em>Pump–probe technique revealing sub-Doppler features.</em></div><div><b>Lamb dip</b><span class="ar">انخفاض لامب</span><em>Narrow dip at line centre in a saturated Doppler profile.</em></div><div><b>Hole burning</b><span class="ar">حرق الثقب</span><em>Depletion of a single velocity group by a strong beam.</em></div><div><b>Saturation intensity</b><span class="ar">شدة الإشباع</span><em>I_sat, the intensity at which the transition begins to bleach.</em></div><div><b>Polarisation spectroscopy</b><span class="ar">طيفية الاستقطاب</span><em>Background-free sub-Doppler method using induced birefringence.</em></div><div><b>Two-photon absorption</b><span class="ar">الامتصاص ثنائي الفوتون</span><em>Simultaneous absorption of two photons; Doppler free when counter-propagating.</em></div><div><b>Photoacoustic spectroscopy</b><span class="ar">الطيفية الضوئية الصوتية</span><em>Detection of absorption through the generated pressure wave.</em></div><div><b>Photothermal deflection</b><span class="ar">الانحراف الحراري الضوئي</span><em>Detection through the refractive-index gradient caused by heating.</em></div><div><b>Susceptibility</b><span class="ar">القابلية</span><em>χ⁽ⁿ⁾, the coefficients of the nonlinear polarisation expansion.</em></div><div><b>Phase matching</b><span class="ar">تطابق الطور</span><em>Condition Δk = 0 for efficient nonlinear conversion.</em></div><div><b>SHG</b><span class="ar">توليد التوافقي الثاني</span><em>Second-harmonic generation; frequency doubling.</em></div><div><b>SFG</b><span class="ar">توليد تردد المجموع</span><em>Sum-frequency generation; intrinsically surface specific.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">The Lamb dip appears:</p><ol type="a"><li>at the centre of the Doppler profile</li><li>in the far wings</li><li>at twice the resonance frequency</li><li>only above saturation everywhere</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">Doppler-free two-photon excitation requires the beams to be:</p><ol type="a"><li>counter-propagating and of equal frequency</li><li>co-propagating</li><li>orthogonally polarised only</li><li>of different wavelengths</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">Polarisation spectroscopy improves on saturation spectroscopy mainly by:</p><ol type="a"><li>being background free</li><li>needing more power</li><li>having wider tuning</li><li>requiring no probe beam</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Second-harmonic generation is forbidden in the bulk of:</p><ol type="a"><li>centrosymmetric media</li><li>all crystals</li><li>all liquids</li><li>anisotropic crystals</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">Photoacoustic spectroscopy detects:</p><ol type="a"><li>the pressure wave produced by absorbed energy</li><li>transmitted light</li><li>scattered light</li><li>the laser polarisation</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Explain why saturation spectroscopy narrows an inhomogeneous line but cannot narrow a purely homogeneous one.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">A student wants to record the spectrum of a strongly scattering powder and finds transmission measurements useless. Recommend a technique and justify the choice.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Compare saturation, polarisation and two-photon spectroscopy in terms of physical mechanism, resolution, signal-to-noise and experimental complexity, and identify a measurement best suited to each.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The Lamb dip width approaches the natural linewidth of the transition.</div><span>T / F</span></div>
  <div class="tf"><div>2. Two-photon spectroscopy obeys the same selection rules as single-photon spectroscopy.</div><span>T / F</span></div>
  <div class="tf"><div>3. Photoacoustic detection is a background-free measurement.</div><span>T / F</span></div>
  <div class="tf"><div>4. Phase matching is required for efficient second-harmonic generation.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Resolution gain</h4><span class="lvl b">BASIC</span></div><p>For the sodium D2 line at 500 K, compute the Doppler width, the natural width and the ratio between them, and state what hyperfine structure becomes visible once the Doppler width is defeated.</p><p class="due"><b>Deliverable:</b> The two widths, their ratio, and a statement of which structure each resolution level reveals.</p></div>
  <div class="hw"><div class="top"><h4>2 · Design a sub-Doppler experiment</h4><span class="lvl a">ADVANCED</span></div><p>Design a saturation spectroscopy setup for a rubidium vapour cell at 780 nm: specify the source and its required linewidth, the beam geometry, the pump and probe powers relative to I_sat, the detection scheme, and the expected feature width.</p><p class="due"><b>Deliverable:</b> A labelled schematic with a justified specification for each component and a predicted spectrum sketch.</p></div>
  <div class="navw"><a href="#w12">← Previous</a><a href="#w14">Next →</a></div>
  <p class="endnote">End of Lecture 13 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w14">
  <div class="hd" style="background:linear-gradient(120deg,#9F1239,#831843)">
    <p class="no">WEEK 14</p>
    <h2>Instrumentation and Data Analysis</h2>
    <p>A spectrum is not data until it has been calibrated, corrected and fitted. This lecture covers the hardware that produces it and the analysis that turns it into a defensible number.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Compute the resolving power and dispersion of a grating spectrometer.</li><li>Select a detector appropriate to a given wavelength range, speed and sensitivity requirement.</li><li>Identify the dominant noise source and predict how signal-to-noise scales with integration time.</li><li>Perform wavelength and intensity calibration correctly.</li><li>Apply baseline correction, smoothing and peak fitting without distorting the result.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Gratings, dispersion and resolving power</h3>
  <p>A diffraction grating separates wavelengths by interference. The grating equation and the resolving power follow directly from the geometry and the number of illuminated grooves.</p>
  <div class="eq"><b>(14.1)</b>d (sin θ_i + sin θ_d) = m λ</div>
  <div class="eq"><b>(14.2)</b>R = λ / Δλ = m N   (N = illuminated grooves)</div>
  <div class="eq"><b>(14.3)</b>linear dispersion  dλ/dx = d cos θ_d / (m f)</div>
  <div class="call ex"><p class="lbl">Worked example 14.1</p><p>A 1200 grooves/mm grating is illuminated over 25 mm and used in first order at 500 nm. Find the theoretical resolving power and resolution.</p><ol><li>N = 1200 × 25 = 30 000 illuminated grooves.</li><li>R = mN = 1 × 30 000 = 30 000.</li><li>Δλ = λ/R = 500/30 000 = 0.0167 nm.</li><li>In frequency: Δν = cΔλ/λ² = 2.998×10⁸ × 1.67×10⁻¹¹ / (5×10⁻⁷)² = 20 GHz.</li></ol><p class="res">Real instruments fall well short of this because slit width, aberrations and detector pixel size all contribute. The theoretical value is an upper bound, never a specification — always measure the instrument function instead of trusting the calculation.</p></div>
  <ul class="chk"><li>Higher order m improves resolution but reduces free spectral range and demands order-sorting filters.</li><li>Longer focal length improves linear dispersion at the cost of throughput and instrument size.</li><li>Narrowing the entrance slit improves resolution only until the diffraction limit is reached, after which it just loses light.</li></ul>
  <h3 class="s"><i style="background:#0E7490">2</i>Detectors</h3>
  <div class="scroll"><table><thead><tr><th>Detector</th><th>Range</th><th>Speed</th><th>Best for</th></tr></thead><tbody><tr><td>PMT</td><td class="m">200–900 nm</td><td class="m">ns</td><td class="m">photon counting, TCSPC, weak signals</td></tr><tr><td>Si photodiode</td><td class="m">200–1100 nm</td><td class="m">ns–µs</td><td class="m">strong signals, absorption</td></tr><tr><td>CCD</td><td class="m">200–1100 nm</td><td class="m">ms</td><td class="m">multichannel spectra, long integration</td></tr><tr><td>ICCD</td><td class="m">200–900 nm</td><td class="m">ns gating</td><td class="m">LIBS, time-resolved emission</td></tr><tr><td>InGaAs array</td><td class="m">900–2600 nm</td><td class="m">ms</td><td class="m">near-IR spectroscopy</td></tr><tr><td>MCT (HgCdTe)</td><td class="m">2–16 µm</td><td class="m">ns–µs</td><td class="m">FTIR and mid-IR, needs cooling</td></tr><tr><td>DTGS pyroelectric</td><td class="m">2–25 µm</td><td class="m">slow</td><td class="m">routine FTIR, room temperature</td></tr></tbody></table></div>
  <div class="call key"><p class="lbl">Key idea</p><p>The choice is almost always dictated by two questions before any other: what wavelength, and do you need time gating? Everything else — sensitivity, cost, cooling — follows from those two answers.</p></div>
  <h3 class="s"><i style="background:#047857">3</i>Noise and signal-to-noise ratio</h3>
  <p>Three noise sources dominate in practice, and knowing which one you are in determines whether averaging will help.</p>
  <ul class="chk"><li><b>Shot noise</b> — the Poisson statistics of photon arrival. Noise scales as √N while signal scales as N, so SNR ∝ √N. This is the fundamental limit.</li><li><b>Detector noise</b> — dark current and readout noise, independent of signal. It dominates in weak-signal measurements and is reduced by cooling.</li><li><b>Source flicker</b> — proportional to the signal itself, with a 1/f character. Averaging does not help; this is what modulation techniques in Week 8 are designed to escape.</li></ul>
  <div class="eq"><b>(14.4)</b>SNR ∝ √(t)   (shot- or detector-noise limited averaging)</div>
  <div class="vs"><div class="bad"><span class="mark">✗ Averaging longer always improves the result</span>Doubling the integration time from 1 to 2 hours to gain a factor of 1.4 is a poor trade when the measurement is flicker limited, in which case it gains nothing at all.</div><div class="good"><span class="mark">✓ Identify the regime first</span>Plot noise against integration time. If it falls as 1/√t you are shot or detector limited and averaging works. If it flattens, you are flicker limited and you need modulation, a reference channel or a better source.</div></div>
  <h3 class="s"><i style="background:#B45309">4</i>Calibration</h3>
  <p>Two calibrations are needed and they are entirely distinct. <b>Wavelength calibration</b> fixes the horizontal axis, using atomic lines from a discharge lamp fitted to a polynomial. <b>Intensity calibration</b> fixes the vertical axis, using a standard lamp of known spectral radiance to correct for the combined wavelength response of grating, optics and detector.</p>
  <ul class="chk"><li>Fit the wavelength calibration in wavenumber where the dispersion is more nearly linear, and always report the residuals of the fit.</li><li>Never extrapolate a calibration beyond the range of the reference lines used.</li><li>Intensity calibration is mandatory before any Boltzmann plot, any quantum yield and any band-intensity ratio. Line positions survive without it; intensities do not.</li><li>Recalibrate after any change to the optical alignment, grating position or slit width.</li></ul>
  <h3 class="s"><i style="background:#BE123C">5</i>Processing: baseline, smoothing and fitting</h3>
  <p>The processing chain is where good data are most often ruined. Each step should be applied deliberately, in order, and reported.</p>
  <ul class="chk"><li><b>Baseline correction</b> — model the background with a low-order polynomial or an asymmetric least-squares method over regions free of peaks. Never subtract a baseline drawn through the peaks themselves.</li><li><b>Smoothing</b> — Savitzky–Golay preserves peak height and width better than a moving average, but any smoothing window comparable with the peak width will broaden the peak and reduce its amplitude. If in doubt, do not smooth; fit instead.</li><li><b>Peak fitting</b> — choose the profile from the physics (Week 3), not from what fits best. Report the model, the fitted parameters with uncertainties, and the residuals.</li><li><b>Deconvolution</b> — only with a measured instrument function and only by a modest factor.</li></ul>
  <p>When many spectra must be compared, chemometric methods take over: principal component analysis to find the directions of real variation, and partial least squares to build a quantitative calibration from whole spectra rather than single peaks. These are standard in industrial and biomedical spectroscopy.</p>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 14</b> — data processing workshop in Origin, MATLAB or Python: baseline correction, smoothing and peak fitting on your own recorded spectra.</li><li>Produce a documented script rather than a sequence of mouse clicks. A script is reproducible, can be checked by someone else, and can be rerun when you find an error — which you will.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>R = mN gives the theoretical resolving power; real resolution is always worse and must be measured.</li><li>Detector choice follows from wavelength range and the need for time gating.</li><li>SNR improves as √t only when shot or detector limited; flicker noise requires modulation instead.</li><li>Wavelength and intensity calibration are separate, and intensity calibration is mandatory before any quantitative intensity work.</li><li>Baseline, smoothing and fitting choices must be justified from the physics and reported in full.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Grating equation</b><span class="ar">معادلة المحزوز</span><em>Relation between groove spacing, angles, order and wavelength.</em></div><div><b>Resolving power</b><span class="ar">قدرة التحليل</span><em>R = λ/Δλ = mN for a grating.</em></div><div><b>Linear dispersion</b><span class="ar">التشتت الخطي</span><em>Wavelength interval per unit distance in the focal plane.</em></div><div><b>Free spectral range</b><span class="ar">المدى الطيفي الحر</span><em>Wavelength span before orders overlap.</em></div><div><b>PMT</b><span class="ar">المضاعف الضوئي</span><em>Photomultiplier tube; fast and sensitive in the visible and UV.</em></div><div><b>ICCD</b><span class="ar">كاميرا CCD معززة</span><em>Intensified CCD with nanosecond gating, essential for LIBS.</em></div><div><b>Shot noise</b><span class="ar">ضجيج التصويب</span><em>Fundamental noise from the Poisson statistics of photons.</em></div><div><b>Dark current</b><span class="ar">التيار المظلم</span><em>Detector signal in the absence of light; reduced by cooling.</em></div><div><b>Flicker noise</b><span class="ar">ضجيج الوميض</span><em>Source noise proportional to signal, with 1/f spectrum.</em></div><div><b>Intensity calibration</b><span class="ar">معايرة الشدة</span><em>Correction for the wavelength-dependent response of the system.</em></div><div><b>Savitzky–Golay filter</b><span class="ar">مرشح سافيتزكي–غولاي</span><em>Polynomial smoothing that preserves peak shape.</em></div><div><b>Chemometrics</b><span class="ar">الكيمياء القياسية</span><em>Multivariate statistical analysis of spectral data sets.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">The resolving power of a grating in first order is set by:</p><ol type="a"><li>the number of illuminated grooves</li><li>the slit width alone</li><li>the source intensity</li><li>the exposure time</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">In the shot-noise limit the signal-to-noise ratio scales with the number of detected photons as:</p><ol type="a"><li>√N</li><li>N</li><li>1/N</li><li>log N</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">An ICCD is chosen for LIBS mainly because of its:</p><ol type="a"><li>nanosecond gating capability</li><li>low cost</li><li>infrared response</li><li>high resolving power</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Intensity calibration is essential before:</p><ol type="a"><li>constructing a Boltzmann plot</li><li>measuring a line position</li><li>counting the number of peaks</li><li>checking the slit width</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">Smoothing with a window comparable to the peak width will:</p><ol type="a"><li>broaden the peak and reduce its height</li><li>sharpen the peak</li><li>leave the peak unchanged</li><li>shift the peak position only</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Your noise does not decrease when you double the integration time. Diagnose the regime you are in and state what to do instead.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">A colleague reports relative line intensities from a spectrum recorded without intensity calibration. Explain what is wrong and estimate the size of the effect qualitatively.</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Describe the complete path from photons entering a spectrometer to a fitted peak parameter with an uncertainty, identifying at each stage what can distort the result and how it is controlled.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. Theoretical resolving power is an upper bound rarely achieved in practice.</div><span>T / F</span></div>
  <div class="tf"><div>2. Flicker noise can be removed by longer averaging.</div><span>T / F</span></div>
  <div class="tf"><div>3. Wavelength and intensity calibration are two separate procedures.</div><span>T / F</span></div>
  <div class="tf"><div>4. A Savitzky–Golay filter preserves peak shape better than a moving average.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Spectrometer specification</h4><span class="lvl b">BASIC</span></div><p>For the spectrometer used in Session 2, compute the theoretical resolving power and linear dispersion from its grating and focal length, then compare with the resolution you actually measured.</p><p class="due"><b>Deliverable:</b> The calculation, the measured value, and a discussion of the discrepancy with at least two named causes.</p></div>
  <div class="hw"><div class="top"><h4>2 · Processing pipeline</h4><span class="lvl i">INTERMEDIATE</span></div><p>Write a documented script that loads a raw spectrum, corrects the baseline, fits the main peaks with a justified profile and outputs the parameters with uncertainties. Run it on two different spectra.</p><p class="due"><b>Deliverable:</b> The script with comments, its output for both spectra, and a short note on the choices you made and why.</p></div>
  <div class="navw"><a href="#w13">← Previous</a><a href="#w15">Next →</a></div>
  <p class="endnote">End of Lecture 14 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>

<section class="week" id="w15">
  <div class="hd" style="background:linear-gradient(120deg,#831843,#831843)">
    <p class="no">WEEK 15</p>
    <h2>Applications and Seminars</h2>
    <p>The closing week puts the whole course to work: choosing a technique for a real problem, and defending the choice. Environmental monitoring, biomedical diagnosis, nanomaterials and cultural heritage.</p>
  </div>
  <div class="call key"><p class="lbl">Learning outcomes</p><ul><li>Select the appropriate spectroscopic technique for a stated analytical problem and justify it.</li><li>Estimate detection limits and state the assumptions behind them.</li><li>Describe applications of laser spectroscopy to water quality, biomedical diagnosis and materials characterisation.</li><li>Present technical results orally and defend them under questioning.</li></ul></div>
  <h3 class="s"><i style="background:#4338CA">1</i>Choosing a technique</h3>
  <p>Every technique in this course answers a different question. The selection follows from what you need to know, not from what is available in the laboratory.</p>
  <div class="scroll"><table><thead><tr><th>Question</th><th>Technique</th><th>Why</th></tr></thead><tbody><tr><td>Which elements are present?</td><td class="m">LIBS, atomic emission</td><td class="m">elemental, no preparation, standoff capable</td></tr><tr><td>Which functional groups?</td><td class="m">FTIR, Raman</td><td class="m">vibrational fingerprint</td></tr><tr><td>How much of this molecule?</td><td class="m">UV–Vis, TDLAS, fluorescence</td><td class="m">quantitative, calibrated</td></tr><tr><td>How pure or how bright?</td><td class="m">Photoluminescence</td><td class="m">quantum yield and defect emission</td></tr><tr><td>How fast does it relax?</td><td class="m">TCSPC, pump–probe</td><td class="m">time domain</td></tr><tr><td>What is the exact frequency?</td><td class="m">Sub-Doppler, comb</td><td class="m">metrological accuracy</td></tr><tr><td>What is the band gap?</td><td class="m">UV–Vis with Tauc analysis</td><td class="m">absorption edge</td></tr></tbody></table></div>
  <div class="call key"><p class="lbl">Key idea</p><p>Two questions settle most cases: does the problem need elemental or molecular information, and is it qualitative or quantitative? Answer those before considering any instrument.</p></div>
  <h3 class="s"><i style="background:#0E7490">2</i>Environmental and water quality monitoring</h3>
  <p>Water quality is a pressing problem in Iraq, and spectroscopy addresses several parts of it. Heavy metals in water and sediment are detected by LIBS and by atomic absorption or emission; organic pollutants by UV–Vis and fluorescence; dissolved gases and atmospheric trace species by TDLAS.</p>
  <ul class="chk"><li>Fluorescence excitation–emission matrices fingerprint dissolved organic matter and can distinguish industrial from agricultural sources.</li><li>LIBS on dried residue or on filter membranes reaches parts-per-million for many metals without digestion chemistry.</li><li>Photocatalytic degradation studies follow the disappearance of a dye by UV–Vis absorbance against time, which is a direct application of Week 6.</li><li>For any environmental claim, the detection limit and the blank must be reported. A number without a blank is not a measurement.</li></ul>
  <h3 class="s"><i style="background:#047857">3</i>Biomedical and materials applications</h3>
  <p>In biomedicine, Raman and fluorescence dominate because they work in water and are non-destructive. Raman distinguishes malignant from healthy tissue by its molecular fingerprint; fluorescence lifetime imaging maps the metabolic state of cells; near-infrared spectroscopy penetrates tissue for oximetry.</p>
  <p>In materials, the sequence of characterisation techniques is by now standard, and this course covers all of it: UV–Vis for the band gap, photoluminescence for defects and quality, Raman for phase and crystallinity, FTIR for surface chemistry and residual ligands, and LIBS or atomic emission for composition. A single nanomaterial paper typically uses four of the five.</p>
  <div class="vs"><div class="bad"><span class="mark">✗ One technique proves the result</span>A single UV–Vis peak is taken as proof that nanoparticles of a given size were synthesised.</div><div class="good"><span class="mark">✓ Convergent evidence proves the result</span>The absorption peak gives a size estimate, photoluminescence confirms the electronic quality, Raman confirms the phase, and microscopy confirms the morphology. Referees ask for the combination because each technique alone has an alternative explanation.</div></div>
  <h3 class="s"><i style="background:#B45309">4</i>Detection limits, blanks and honest reporting</h3>
  <p>Every quantitative claim rests on a calibration and a blank. The standard definitions should be used and stated explicitly.</p>
  <div class="eq"><b>(15.1)</b>LOD = 3 σ_blank / S ,  LOQ = 10 σ_blank / S</div>
  <div class="eq"><b>(15.2)</b>I = S · C + I₀   (calibration line, S the sensitivity)</div>
  <ul class="chk"><li>State the number of replicate blank measurements used for σ.</li><li>State the linear range and never report a concentration obtained by extrapolating beyond it.</li><li>Report uncertainties from the fit, not from the last digit the software displayed.</li><li>Matrix effects are the usual reason a validated method fails on a real sample; check with a spike recovery.</li></ul>
  <h3 class="s"><i style="background:#BE123C">5</i>Seminar and term project</h3>
  <p>The course closes with student presentations. The project is either a focused literature review or an experimental measurement on Institute instrumentation, and the seminar is assessed on the clarity of the argument as much as on the result.</p>
  <ul class="chk"><li><b>Frame the question first</b> — one sentence stating what you set out to determine.</li><li><b>Justify the technique</b> — say why this method and not the obvious alternative.</li><li><b>Show the raw data</b> — at least one uncorrected spectrum, before any processing.</li><li><b>State the uncertainty</b> — a result without an uncertainty is an opinion.</li><li><b>Name the limitation</b> — every measurement has one, and naming it yourself is stronger than being asked about it.</li></ul>
  <div class="call lab"><p class="lbl">In the laboratory</p><ul><li><b>Session 13</b> — term project measurements and data acquisition.</li><li><b>Session 15</b> — project presentation and laboratory examination. Bring your raw data as well as your processed results; you may be asked to reprocess a spectrum during the examination.</li></ul></div>
  <h3 class="s"><i style="background:#15181E">6</i>Summary</h3>
  <ul class="chk"><li>Technique selection follows from the question: elemental or molecular, qualitative or quantitative.</li><li>Water quality, biomedical diagnosis and nanomaterials characterisation each use several course techniques together.</li><li>LOD = 3σ_blank/S; a quantitative result requires a blank, a linear range and a stated uncertainty.</li><li>Convergent evidence from several techniques is what makes a materials characterisation defensible.</li><li>A good seminar states the question, justifies the method, shows raw data, and names its own limitation.</li></ul>
  <h3 class="s"><i style="background:#0E7490">7</i>Key terms</h3>
  <div class="gloss"><div><b>Detection limit</b><span class="ar">حد الكشف</span><em>LOD = 3σ_blank/S, the smallest detectable concentration.</em></div><div><b>Limit of quantification</b><span class="ar">حد القياس الكمي</span><em>LOQ = 10σ_blank/S, the smallest reliably measurable concentration.</em></div><div><b>Blank</b><span class="ar">العينة الصفرية</span><em>Measurement with no analyte, defining the baseline and its noise.</em></div><div><b>Sensitivity</b><span class="ar">الحساسية</span><em>The slope S of the calibration line.</em></div><div><b>Linear range</b><span class="ar">المدى الخطي</span><em>Concentration span over which the calibration stays linear.</em></div><div><b>Matrix effect</b><span class="ar">أثر المصفوفة</span><em>Change in response caused by the sample environment.</em></div><div><b>Spike recovery</b><span class="ar">استرداد الإضافة</span><em>Validation test adding a known amount to a real sample.</em></div><div><b>Standoff detection</b><span class="ar">الكشف عن بُعد</span><em>Measurement at a distance without contacting the sample.</em></div><div><b>Excitation–emission matrix</b><span class="ar">مصفوفة الإثارة والانبعاث</span><em>Fluorescence map used to fingerprint complex mixtures.</em></div><div><b>Non-destructive analysis</b><span class="ar">التحليل غير الإتلافي</span><em>Measurement leaving the sample intact; essential in heritage work.</em></div></div>
  <h3 class="s"><i style="background:#B45309">8</i>Review questions</h3>
  <p style="color:var(--muted);font-size:14px">No answers given. Work them yourself; solutions are discussed in the next lecture.</p>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">For rapid in-situ elemental analysis of a metal alloy, the most suitable technique is:</p><ol type="a"><li>LIBS</li><li>FTIR</li><li>TCSPC</li><li>UV–Vis</li></ol></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">The limit of detection is conventionally defined as:</p><ol type="a"><li>3σ_blank / S</li><li>σ_blank / S</li><li>10σ_blank / S²</li><li>S / σ_blank</li></ol></div></div>
  <div class="q"><span class="n">3</span><div class="body"><p class="stem">Raman is preferred over FTIR for aqueous biological samples because:</p><ol type="a"><li>water is a weak Raman scatterer</li><li>Raman is faster</li><li>water has no vibrational modes</li><li>Raman needs no laser</li></ol></div></div>
  <div class="q"><span class="n">4</span><div class="body"><p class="stem">Confirming the size of synthesised quantum dots is best done by:</p><ol type="a"><li>combining UV–Vis, photoluminescence and microscopy</li><li>a single UV–Vis spectrum</li><li>FTIR alone</li><li>LIBS alone</li></ol></div></div>
  <div class="q"><span class="n">5</span><div class="body"><p class="stem">A quantitative result reported without a blank measurement is:</p><ol type="a"><li>not a valid measurement</li><li>acceptable if the peak is strong</li><li>valid if replicated</li><li>valid within the linear range</li></ol></div></div>
  <h4 class="t">Scenario questions — short answer</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">You are asked to determine whether a water sample from a marshland contains heavy metals above a regulatory threshold. Outline a measurement plan naming the technique, the calibration strategy and how you would establish the detection limit.</p><div class="lines"></div><div class="lines"></div></div></div>
  <div class="q"><span class="n">2</span><div class="body"><p class="stem">A colleague presents nanoparticle synthesis supported only by a UV–Vis absorption peak. What additional evidence would you request, and what alternative explanation are you guarding against?</p><div class="lines"></div><div class="lines"></div></div></div>
  <h4 class="t">Essay questions</h4>
  <div class="q"><span class="n">1</span><div class="body"><p class="stem">Choose one application area treated in this lecture and discuss, with reference to specific techniques from the course, how a complete analytical answer is assembled and what its limitations are.</p></div></div>
  <h4 class="t">True or false</h4>
  <div class="tf"><div>1. The limit of quantification is higher than the limit of detection.</div><span>T / F</span></div>
  <div class="tf"><div>2. Matrix effects are a common reason a validated method fails on real samples.</div><span>T / F</span></div>
  <div class="tf"><div>3. A single technique is normally sufficient to characterise a new nanomaterial.</div><span>T / F</span></div>
  <div class="tf"><div>4. Standoff detection is one of the practical advantages of LIBS.</div><span>T / F</span></div>
  <h3 class="s"><i style="background:#047857">9</i>Assignments</h3>
  <div class="hw"><div class="top"><h4>1 · Technique selection exercise</h4><span class="lvl b">BASIC</span></div><p>For five analytical problems of your choice drawn from Iraqi environmental or industrial practice, select a technique, state the expected detection limit and name the main interference in each case.</p><p class="due"><b>Deliverable:</b> A table of five problems with technique, expected detection limit and main interference, with brief justifications.</p></div>
  <div class="hw"><div class="top"><h4>2 · Term project</h4><span class="lvl a">ADVANCED</span></div><p>Carry out either a focused literature review or an experimental measurement on Institute instrumentation, and present it in a seminar. The written report must follow the structure of a journal article.</p><p class="due"><b>Deliverable:</b> A report in journal format with abstract, method, results with uncertainties, discussion and references, plus the seminar presentation.</p></div>
  <div class="navw"><a href="#w14">← Previous</a><span></span></div>
  <p class="endnote">End of Lecture 15 — Asst. Prof. Dr. Rawaa Ahmed Faris ★</p>
</section>
</div>

<button class="fab" id="fab" aria-label="Reading settings">Aa</button>
<div class="panel" id="panel">
  <h5>Read comfortably</h5>
  <p>Your choice is saved on this device and applies to every week.</p>
  <label>Typeface</label>
  <div class="opts" id="faceOpts">
    <button data-face="sans" class="on">Sans</button>
    <button data-face="serif">Serif</button>
  </div>
  <label>Size</label>
  <div class="size">
    <button id="minus">−</button><span id="pct">100%</span><button id="plus">+</button>
  </div>
  <div class="opts" style="margin-top:10px"><button id="reset">Reset</button></div>
</div>

<footer>© 2026 Asst. Prof. Dr. Rawaa Ahmed Faris · Institute of Laser for Postgraduate Studies, University of Baghdad</footer>

<script>
const TITLES = ['Foundations of Spectroscopy','Atomic Spectra','Line Shapes and Broadening',
 'Molecular Spectroscopy I — Rotation','Molecular Spectroscopy II — Vibration',
 'Electronic Spectra and UV–Vis','Lasers as Spectroscopic Sources','Laser Absorption Spectroscopy',
 'Fluorescence and Luminescence','Time-Resolved and Ultrafast Spectroscopy','Raman Spectroscopy',
 'Laser-Induced Breakdown Spectroscopy','Nonlinear and High-Resolution Spectroscopy',
 'Instrumentation and Data Analysis','Applications and Seminars'];
const COLORS = ['#4338CA','#5B21B6','#6D28D9','#7C3AED','#0369A1','#0E7490','#0F766E','#047857',
 '#4D7C0F','#A16207','#B45309','#C2410C','#BE123C','#9F1239','#831843'];

const rail = document.getElementById('rail');
TITLES.forEach((t, i) => {
  const a = document.createElement('a');
  a.href = '#w' + (i + 1);
  a.innerHTML = (i + 1) + '<small>READY</small>';
  a.className = 'ready'; a.style.background = COLORS[i]; a.style.borderColor = COLORS[i];
  a.title = 'Week ' + (i + 1) + ' — ' + t;
  rail.appendChild(a);
});

const panel = document.getElementById('panel');
document.getElementById('fab').onclick = e => { e.stopPropagation(); panel.classList.toggle('on'); };
document.addEventListener('click', e => { if (!panel.contains(e.target)) panel.classList.remove('on'); });

let size = 100, face = 'sans';
function apply() {
  document.documentElement.style.setProperty('--fs', size + '%');
  document.documentElement.style.setProperty('--body', face === 'serif' ? 'var(--serif)' : 'var(--sans)');
  document.getElementById('pct').textContent = size + '%';
  document.querySelectorAll('#faceOpts button').forEach(b => b.classList.toggle('on', b.dataset.face === face));
  try { localStorage.setItem('lsn-read', JSON.stringify({ size, face })); } catch (e) {}
}
try {
  const s = JSON.parse(localStorage.getItem('lsn-read') || '{}');
  if (s.size) size = s.size;
  if (s.face) face = s.face;
} catch (e) {}
document.getElementById('plus').onclick = () => { size = Math.min(150, size + 10); apply(); };
document.getElementById('minus').onclick = () => { size = Math.max(80, size - 10); apply(); };
document.getElementById('reset').onclick = () => { size = 100; face = 'sans'; apply(); };
document.querySelectorAll('#faceOpts button').forEach(b => b.onclick = () => { face = b.dataset.face; apply(); });
apply();
</script>
</body>
</html>
