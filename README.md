<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>Wireless Billing Management | Hyundai AutoEver</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Figtree:wght@300..900&family=Sora:wght@400..800&family=Instrument+Sans:wght@400..700&display=swap');

:root{
  --canvas:#F3F5F9;
  --surface:#FFFFFF;
  --surface-2:#F7F8FB;
  --ink:#2B3445;
  --ink-2:#5B6577;
  --ink-3:#8790A1;
  --line:#E4E8EF;
  --line-2:#EEF1F5;
  --pool:#7BA7DB; --lagoon:#67BDBA; --sage:#82BE9C; --pistachio:#A9C978; --honey:#EDC468;
  --peach:#F2A587; --blush:#E79BB8; --iris:#A797DE; --orchid:#C59BD6;
  --up:#2F8F66; --down:#C95A50;
  --font:'Figtree',ui-sans-serif,system-ui,-apple-system,'Segoe UI',Roboto,'Helvetica Neue',Arial,sans-serif;
  --c:var(--pool);
}
*{box-sizing:border-box}
html,body{margin:0;padding:0}
body{background:var(--canvas);color:var(--ink);font:15px/1.45 var(--font);-webkit-font-smoothing:antialiased;font-variant-numeric:tabular-nums}
button,select,input{font:inherit;color:inherit}
a{color:inherit}
:focus-visible{outline:2px solid var(--pool);outline-offset:2px;border-radius:8px}
.sr{position:absolute;width:1px;height:1px;overflow:hidden;clip:rect(0 0 0 0)}

/* ---------- App frame ---------- */
.app{display:grid;grid-template-columns:262px minmax(0,1fr);min-height:100vh}
.side{position:sticky;top:0;height:100vh;overflow-y:auto;background:var(--surface);border-right:1px solid var(--line);padding:22px 14px 18px;display:flex;flex-direction:column}
.brand{display:flex;align-items:center;gap:12px;padding:0 8px 14px;text-decoration:none}
.mark{display:grid;grid-template-columns:repeat(2,12px);gap:3px;flex:none}
.mark i{width:12px;height:12px;border-radius:4px;display:block}
.brand-name{font-weight:760;font-size:16px;letter-spacing:-.015em;line-height:1.15}
.brand-sub{font-size:12.5px;color:var(--ink-3);margin-top:2px}
.nav-link svg{flex:none}
.trow{display:flex;align-items:center;gap:2px}
.trow>.nav-link{flex:1;min-width:0}
.twist{flex:none;width:28px;height:28px;border:0;background:none;border-radius:8px;color:var(--ink-3);cursor:pointer;display:grid;place-items:center}
.twist:hover{background:var(--surface-2);color:var(--ink)}
.twist svg{width:14px;height:14px;transition:transform .15s ease}
.tgroup.open>.trow>.twist svg{transform:rotate(90deg)}
.tgroup:not(.open)>.tkids{display:none}
.tgroup.sec{margin-top:10px}
.nav-link.lvl3{color:var(--ink);font-weight:700}
.nav-link.lvl3 svg{color:var(--ink-3)}
.nav-link.lvl3.active svg{color:currentColor}
.sec>.tkids{margin:2px 0 2px 10px}
.nav-link.lvl4{font-size:14px;padding:7px 10px}
.nav-link.lvl4.active:not(.here){background:color-mix(in srgb,var(--c) 10%,white)}
.nav-link{display:flex;align-items:center;gap:11px;width:100%;padding:8px 10px;border-radius:11px;border:0;background:none;text-align:left;cursor:pointer;color:var(--ink-2);font-weight:560;font-size:14.5px;text-decoration:none}
.nav-link:hover{background:var(--surface-2);color:var(--ink)}
.nav-link .dot{width:10px;height:10px;border-radius:3.5px;background:var(--c);flex:none}
.nav-link.active{background:color-mix(in srgb,var(--c) 17%,white);color:color-mix(in srgb,var(--c) 38%,var(--ink));font-weight:680}
.nav-sub{margin:2px 0 8px 15px;padding-left:12px;border-left:2px solid color-mix(in srgb,var(--c) 35%,white)}
.nav-sub a{display:block;padding:6px 10px;border-radius:8px;font-size:13.5px;color:var(--ink-2);text-decoration:none}
.nav-sub a:hover{background:var(--surface-2);color:var(--ink)}
.nav-sub a.active{color:var(--ink);font-weight:680;background:var(--surface-2)}
.side-foot{margin-top:auto;padding-top:18px;display:grid;gap:4px}
.side-foot .nav-link{font-size:14px}

.main{min-width:0;padding:24px 34px 64px}
.wrap{max-width:1320px;margin:0 auto}
.topbar{display:none}
.scrim{display:none}

/* ---------- Page header ---------- */
.crumb-row{display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap}
.crumbs{display:flex;flex-wrap:wrap;gap:6px;align-items:center;font-size:13px;color:var(--ink-3)}
.crumbs a{color:var(--ink-2);text-decoration:none}
.crumbs a:hover{color:var(--ink);text-decoration:underline}
.crumbs .sep{opacity:.55}
.sample{font-size:12.5px;font-weight:650;color:color-mix(in srgb,var(--honey) 35%,var(--ink));background:color-mix(in srgb,var(--honey) 22%,white);padding:3px 10px;border-radius:999px}
.head{display:flex;justify-content:space-between;gap:24px;align-items:center;margin-top:16px}
.title-row{display:flex;gap:14px;align-items:center;min-width:0}
.glyph{width:46px;height:46px;border-radius:14px;background:color-mix(in srgb,var(--c) 24%,white);color:color-mix(in srgb,var(--c) 34%,var(--ink));display:grid;place-items:center;font-weight:800;font-size:14.5px;flex:none;letter-spacing:.02em}
h1{font-size:28px;line-height:1.15;letter-spacing:-.022em;margin:0;font-weight:760}
.chart-host.auto.table-mode{max-height:320px}
.dt{width:100%;border-collapse:collapse;font-size:12.5px}
.dt th{position:sticky;top:0;z-index:1;background:var(--surface-2);text-align:left;font-weight:680;color:var(--ink-2);padding:7px 10px;border-bottom:1px solid var(--line);white-space:nowrap}
.dt td{padding:6px 10px;border-bottom:1px solid var(--line-2);white-space:nowrap;color:var(--ink)}
.dt .n{text-align:right}
.dt tbody tr:hover td{background:#F7F9FC}
.dt tr.total td{font-weight:700;background:#FAFBFD}
.dt+.tbl-cap{margin-top:8px}
.tbl-cap{font-size:12px;font-weight:700;color:var(--ink-2);padding:9px 10px 5px}

.card.tbd .tbd-body{flex:1;min-height:240px;margin-top:14px;border:1.5px dashed #D3D9E3;border-radius:14px;display:grid;place-items:center;text-align:center;padding:22px;background:var(--surface-2)}
.tbd-body strong{display:block;font-size:15px;font-weight:700;margin:10px 0 4px}
.tbd-body p{margin:0;font-size:13px;color:var(--ink-3);max-width:30ch}
.tbd-ico{width:42px;height:42px;border-radius:12px;display:grid;place-items:center;margin:0 auto;background:color-mix(in srgb,var(--c) 18%,white);color:color-mix(in srgb,var(--c) 40%,var(--ink))}

/* split + stacked hosts */
.split-host{display:grid;grid-template-columns:minmax(96px,38%) minmax(0,1fr);gap:14px;align-items:center}
.split-host>.sub{position:relative;height:100%;min-width:0}
.split-host>.sub.rows{height:auto;max-width:440px}
.stack-host{display:flex;flex-direction:column;gap:12px}
.stack-host>.sub{position:relative;min-height:0}
.stack-host>.sub.grow{flex:1}

/* ---------- SVG chart styling ---------- */
svg.chart{display:block;overflow:visible;touch-action:pan-y}
.grid-line{stroke:#EDF0F4;stroke-width:1}
.base-line{stroke:#D9DEE7;stroke-width:1}
.axis-t{font-size:11.5px;fill:var(--ink-3);font-family:var(--font)}
.x-t{font-size:11.5px;fill:var(--ink-3);font-family:var(--font)}
.band-hl{fill:#F1F3F7}
path.stk{stroke:#fff;stroke-width:1.5}
.guide{stroke:#A9B1BF;stroke-width:1;stroke-dasharray:3 3;pointer-events:none}
.cross{stroke:#A9B1BF;stroke-width:1;pointer-events:none}
.axis-pill,.tag,.pill2,.ref-tag,.hdot,.seg-t,.side-n,.side-v,.leader{pointer-events:none}
.axis-pill-t{font-size:11.5px;font-weight:720;fill:var(--ink);font-family:var(--font)}
.trend{fill:none;stroke-width:2;stroke-linecap:round;stroke-linejoin:round;pointer-events:none}
.trend-halo{fill:none;stroke:#fff;stroke-width:5;stroke-linecap:round;opacity:.85;pointer-events:none}
.trend-dot{fill:#fff;stroke-width:1.6;pointer-events:none}
.ln{fill:none;stroke-linejoin:round;stroke-linecap:round;pointer-events:none}
  .topbar{display:flex;align-items:center;justify-content:space-between;margin:-6px 0 14px}
  .topbar .brand{padding:0}
  .main{padding:18px 16px 48px}
  .grid{grid-template-columns:minmax(0,1fr)}
  .card,.card.s3,.card.s4,.card.s6{grid-column:auto}
  .tickers{grid-template-columns:repeat(2,minmax(0,1fr))}
  .val-cards{grid-template-columns:1fr}
  .head{flex-direction:column;align-items:flex-start}
  .quote-value{font-size:38px}
}
@media (max-width:520px){
  .tickers{grid-template-columns:1fr}
  .val-card{grid-template-columns:1fr}
  .pager-count{display:none}
}

/* ==========================================================================
   Shared chrome: command palette button, concept switch, palette overlay
   ========================================================================== */
kbd{font:inherit;font-size:11px;font-weight:700;color:var(--ink-3);background:var(--surface);border:1px solid var(--line);border-bottom-width:2px;border-radius:6px;padding:0 6px;line-height:1.6;white-space:nowrap}
.pal-btn{display:inline-flex;align-items:center;gap:8px;border:1px solid var(--line);background:var(--surface);border-radius:11px;padding:6px 7px 6px 10px;font-size:13.5px;font-weight:600;color:var(--ink-3);cursor:pointer;white-space:nowrap}
.pal-btn:hover{border-color:#CDD4DF;color:var(--ink)}
.pal-btn svg{width:15px;height:15px;flex:none}
.side .pal-btn{width:100%;margin:0 0 4px}
.side .pal-btn span{flex:1;text-align:left}
.cswitch{display:inline-flex;align-items:center;gap:2px;background:var(--surface-2);border:1px solid var(--line-2);border-radius:12px;padding:3px}
.cswitch .cs-l{font-size:11.5px;font-weight:650;color:var(--ink-3);padding:0 6px 0 5px}
.cswitch button{border:0;background:none;border-radius:9px;padding:5px 9px;font-size:12px;color:var(--ink-3);cursor:pointer;display:inline-flex;gap:5px;align-items:baseline;line-height:1.2}
.cswitch button b{font-weight:780}
.cswitch button .cs-n{font-weight:600}
.cswitch button:hover{color:var(--ink)}
.cswitch button.on{background:var(--surface);color:var(--ink);box-shadow:0 1px 2px rgba(43,52,69,.1)}
.cswitch.compact .cs-n{display:none}
.cswitch.compact .cs-l{display:none}
.cswitch.stacked{display:grid;grid-template-columns:repeat(3,1fr);width:100%}
.cswitch.stacked .cs-l{grid-column:1/-1;padding:2px 6px 4px}
.cswitch.stacked button{flex-direction:column;align-items:center;gap:1px;padding:6px 4px}
.cswitch.stacked .cs-n{font-size:11px}
.cswitch.vertical{flex-direction:column;padding:3px;gap:2px}
body.concept-b{background:#fff;--disp:'Sora','Figtree',ui-sans-serif,system-ui,sans-serif}
.b-top{position:sticky;top:12px;z-index:30;display:flex;align-items:center;gap:16px;width:calc(100% - 32px);max-width:1380px;margin:12px auto 0;padding:8px 10px 8px 16px;background:rgba(255,255,255,.84);backdrop-filter:blur(14px) saturate(1.3);-webkit-backdrop-filter:blur(14px) saturate(1.3);border:1px solid var(--line);border-radius:20px;box-shadow:0 8px 30px rgba(43,52,69,.06)}
.b-brand{text-decoration:none;flex:none}
.b-brand .brand{padding:0}
.b-brand .brand-name{font-family:var(--disp);font-size:14.5px;font-weight:650}
.b-secs{display:flex;gap:3px;margin:0 auto;padding:4px;background:var(--surface-2);border-radius:14px;overflow-x:auto}
.b-secs a{padding:7px 14px;border-radius:11px;font-weight:650;font-size:14px;color:var(--ink-2);text-decoration:none;white-space:nowrap}
.b-secs a:hover{color:var(--ink)}
.b-secs a.active{background:#fff;color:var(--ink);box-shadow:0 1px 3px rgba(43,52,69,.1)}
.b-tools{display:flex;align-items:center;gap:8px;flex:none}
.b-tools .icon-btn{margin:0}
.b-dock{display:flex;gap:8px;overflow-x:auto;width:calc(100% - 32px);max-width:1380px;margin:12px auto 0;padding:2px 0 4px;scrollbar-width:none}
.b-chip{display:inline-flex;align-items:center;gap:8px;padding:8px 14px;border-radius:999px;background:color-mix(in srgb,var(--c) 11%,white);font-size:13.5px;font-weight:650;color:var(--ink-2);text-decoration:none;white-space:nowrap}
.b-chip .dot{width:9px;height:9px;border-radius:50%;background:var(--c)}
.b-chip:hover{background:color-mix(in srgb,var(--c) 20%,white);color:var(--ink)}
.b-chip.active{background:color-mix(in srgb,var(--c) 32%,white);color:color-mix(in srgb,var(--c) 28%,var(--ink))}
.b-main{width:calc(100% - 32px);max-width:1380px;margin:0 auto;padding:24px 0 72px}
.b-head{display:flex;justify-content:space-between;align-items:flex-end;gap:20px}
.b-title{font-family:var(--disp);font-size:46px;line-height:1.05;letter-spacing:-.035em;font-weight:700;margin:10px 0 6px}
.b-pager{display:flex;align-items:center;gap:10px;font-size:13px;font-weight:650;color:var(--ink-3);flex:none}
.b-round{width:46px;height:46px;border-radius:50%;border:1px solid var(--line);background:#fff;display:grid;place-items:center;cursor:pointer;color:var(--ink-2)}
.b-round:hover:not(:disabled){background:color-mix(in srgb,var(--c) 20%,white);border-color:transparent;color:var(--ink)}
.b-round:disabled{opacity:.35;cursor:default}
.b-round svg{width:18px;height:18px}
.b-tabs{display:flex;gap:6px;margin:16px 0 0;overflow-x:auto}
.b-tabs .tab{border-radius:999px;background:var(--surface-2);padding:8px 16px}
.b-tabs .tab.active{background:color-mix(in srgb,var(--c) 28%,white);color:color-mix(in srgb,var(--c) 30%,var(--ink))}
.b-hero{display:flex;justify-content:space-between;align-items:flex-end;gap:20px;flex-wrap:wrap;margin-top:18px;padding:28px 32px;border-radius:30px;background:color-mix(in srgb,var(--c) 26%,white)}
.b-hero .quote-value{font-family:var(--disp);font-size:64px;letter-spacing:-.045em}
.b-hero .quote-meta{color:var(--ink-2)}
.b-hero-side{display:flex;flex-direction:column;align-items:flex-end;gap:10px}
.b-hero .sel{background-color:rgba(255,255,255,.8);border-color:transparent}
.bento{display:grid;grid-template-columns:repeat(12,minmax(0,1fr));gap:16px;margin-top:16px}
.concept-b .card{border:0;border-radius:26px;padding:22px 22px 18px;background:color-mix(in srgb,var(--c) 11%,white)}
  const k = stacked ? 1 : S.length, gap = stacked ? 0 : Math.max(1.5, Math.min(5, groupW * 0.07));
  const bw = (groupW - gap * (k - 1)) / k, rad = Math.min(7, bw / 3.2);
  const cx = i => pad.l + band * i + band / 2;
  const col = (s, i) => (s.colors ? s.colors[i] : s.color);
  L.forEach((_, i) => {
    const x0 = cx(i) - groupW / 2, delay = Math.min(i * (n > 20 ? 14 : 45), 480) + 'ms';
    if (stacked) {
      let acc = 0, top = -1; S.forEach((s, j) => { if ((s.data[i] || 0) > 0) top = j; });
      S.forEach((s, j) => {
        const v = s.data[i] || 0; if (v <= 0) return;
        const yt = y(acc + v), yb = y(acc), h = yb - yt;
        const p = sv('path', { d: j === top ? roundTop(x0, yt, groupW, h, rad) : rectP(x0, yt, groupW, h), fill: col(s, i), class: 'bar' + (S.length > 1 ? ' stk' : '') }, gB);
        p.style.animationDelay = delay; acc += v;
      });
    } else {
      S.forEach((s, j) => {
        const v = s.data[i] || 0, x = x0 + j * (bw + gap), yt = y(v);
        const p = sv('path', { d: roundTop(x, yt, bw, y(0) - yt, rad), fill: col(s, i), class: 'bar' }, gB);
        p.style.animationDelay = delay;
      });
    }
    if (o.diffMarkers && S.length >= 2) {
      const a = S[0].data[i], b = S[1].data[i], d = (b - a) / a * 100, lb = (d >= 0 ? '+' : '−') + Math.abs(d).toFixed(1) + '%';
      if (band >= lb.length * 6.2 + 16) tagPill(svg, cx(i), y(Math.max(a, b)) - 14, lb);
      else if (band >= lb.length * 5.4 + 4) stext(svg, cx(i), y(Math.max(a, b)) - 10, lb, 'tag-t tag-sm', { 'text-anchor': 'middle' });
    }
    if (o.topDonuts) { const rr = Math.max(7, Math.min(15, band * 0.3)); miniDonut(svg, cx(i), 6 + rr, rr, o.topDonuts[i]); }
  });
  if (o.ref) {
    const yy = q(y(o.ref.value)) + 0.5;
    sv('line', { x1: pad.l, x2: pad.l + pw, y1: yy, y2: yy, class: 'ref' }, svg);
    const g = sv('g', { class: 'ref-tag' }, svg); const lb = fmt(o.ref.value); const w = lb.length * 6.3 + 12;
    sv('rect', { x: pad.l + pw + 3, y: yy - 9, width: w, height: 18, rx: 5 }, g);
    stext(g, pad.l + pw + 3 + w / 2, yy + 4, lb, 'ref-t', { 'text-anchor': 'middle' });
  }
  if (trend) {
    const pts = trend.map((v, i) => [cx(i), y(v)]), d = linePath(pts, true), tc = o.trend.color || '#5B6577';
    sv('path', { d, class: 'trend-halo' }, svg);
    sv('path', { d, class: 'trend', stroke: tc }, svg);
    if (n <= 24) pts.forEach(p => sv('circle', { cx: q(p[0]), cy: q(p[1]), r: 2.6, class: 'trend-dot', stroke: tc }, svg));
  }
 }

/* ==========================================================================
   Reconciliation: source column, component stack, allocated stack, with
   proportional flows between the two stacks
   ========================================================================== */
function reconcile(host, o) {
  if (cap('reconcile', o)) return;
  const { W, H, tip } = prep(host);
  const pad = { l: 6, r: 6, t: 16, b: 44 };
  const pw = W - pad.l - pad.r, ph = H - pad.t - pad.b;
  const band = pw / 3, bw = Math.min(band * 0.42, 92);
  const cx = [0, 1, 2].map(i => pad.l + band * i + band / 2);
  const src = o.source.value, compTot = sum(o.comp.segments.map(s => s.value));
  const y = v => pad.t + ph - v / (src * 1.02) * ph;
  const svg = sv('svg', { width: W, height: H, viewBox: `0 0 ${W} ${H}`, class: 'chart' + (o.animate ? ' anim' : '') }, host);
  sv('line', { x1: pad.l, x2: pad.l + pw, y1: q(y(0)) + 0.5, y2: q(y(0)) + 0.5, class: 'base-line' }, svg);
  let ac = 0, at = 0; const tags = [];
  o.comp.segments.forEach((s, j) => {
    const t = o.target.segments[j];
    const c0 = y(ac), c1 = y(ac + s.value), t0 = y(at), t1 = y(at + t.value);
    const xa = cx[1] + bw / 2, xb = cx[2] - bw / 2, xm = (xa + xb) / 2;
    sv('path', { d: `M${q(xa)},${q(c1)}C${q(xm)},${q(c1)} ${q(xm)},${q(t1)} ${q(xb)},${q(t1)}L${q(xb)},${q(t0)}C${q(xm)},${q(t0)} ${q(xm)},${q(c0)} ${q(xa)},${q(c0)}Z`, fill: s.color, 'fill-opacity': 0.2, class: 'flow' }, svg);
    tags.push({ x: xm, y: ((c0 + c1) / 2 + (t0 + t1) / 2) / 2, up: (t.value / s.value - 1) * 100 });
    ac += s.value; at += t.value;
  });
  const ttl = (col, s) => tipHTML(col.name + (col.sub ? ' ' + col.sub : ''), [{ name: s.name, color: s.color, value: o.fmt(s.value) }]);
  drawStack(svg, cx[0], bw, [{ name: o.source.name, label: o.source.label || '', value: src, color: o.source.color }], y, { delay: '0ms', host, tip, hover: s => ttl(o.source, s) });
  drawStack(svg, cx[1], bw, o.comp.segments, y, { labels: true, delay: '90ms', host, tip, hover: (s, j) => tipHTML(s.name, [{ name: o.comp.name + ' ' + (o.comp.sub || ''), color: s.color, value: o.fmt(s.value) }, { name: o.target.name + ' ' + (o.target.sub || ''), color: s.color, value: o.fmt(o.target.segments[j].value) }]) });
  drawStack(svg, cx[2], bw, o.target.segments, y, { labels: true, delay: '180ms', host, tip, hover: (s, j) => tipHTML(s.name, [{ name: 'Allocated', color: s.color, value: o.fmt(s.value) }, { name: 'From ' + o.comp.name + ' ' + (o.comp.sub || ''), color: s.color, value: o.fmt(o.comp.segments[j].value) }, { name: 'Uplift', color: s.color, value: '+' + ((s.value / o.comp.segments[j].value - 1) * 100).toFixed(1) + '%' }]) });
    mapota: { daily: 3.3, vins: 390e3, vinGrowth: 0.2, drift: 0.00042, weekend: 1.05, noise: 0.1, spikes: 0.012,
            splits: [{ name: '3+', share: 0.58, color: C.pistachio }, { name: '3\u2212', share: 0.42, color: C.lagoon }] },
  ecuota: { daily: 4.5, vins: 740e3, vinGrowth: 0.15, drift: 0.00035, weekend: 1.02, noise: 0.1, spikes: 0.015,
            splits: [{ name: 'Warranty', share: 0.37, color: C.honey }, { name: 'Enhancement', share: 0.63, color: C.peach }] },
  mota:   { daily: 1.95, vins: 380e3, vinGrowth: 0.18, drift: 0.0004, weekend: 1.0, noise: 0.08,
            splits: [{ name: 'Cache', share: 0.46, color: C.blush }, { name: 'SPD', share: 0.54, color: C.iris }] }
};
const MOD_DATA = {};
function genModule(key) {
  if (MOD_DATA[key]) return MOD_DATA[key];
  const c = GEN[key], r = rng('m:' + key);
  const total = new Array(ND), vins = new Array(ND);
  const sp = c.splits, sn = sp ? sp.length : 0;
  const shares = sp ? sp.map(() => new Array(ND)) : null;
  let lvl = 0.8, camp = 0, campSplit = 0;
  for (let i = 0; i < ND; i++) {
    const d = DAYS[i];
    lvl *= 1 + c.drift + (r() - 0.5) * 0.006;
    lvl += (0.8 * Math.exp(c.drift * i) - lvl) * 0.01;
    const dow = d.getDay(), wk = (dow === 0 || dow === 6) ? c.weekend : 1 + (1 - c.weekend) * 0.4;
    if (c.spikes && camp <= 0.05 && r() < c.spikes) { camp = 0.7 + r() * 1.1; campSplit = Math.floor(r() * sn); }
    const spk = 1 + Math.max(0, camp);
    const noise = 1 + (r() - 0.5) * c.noise;
    total[i] = c.daily * lvl * wk * spk * noise;
    vins[i] = c.vins * (1 + c.vinGrowth * (i / 365)) * (1 + (r() - 0.5) * 0.004);
    if (sp) {
      const raw = sp.map((s, j) => s.share * (1 + 0.1 * Math.sin(i / 57 + j * 2.1)) * (1 + (r() - 0.5) * 0.1) * (camp > 0.05 && j === campSplit ? 1 + camp * 0.8 : 1));
      const t = sum(raw); raw.forEach((w, j) => { shares[j][i] = w / t; });
    }
    camp = camp > 0 ? camp * 0.7 - 0.03 : 0;
  }
  const D = { key, c, total, vins, shares, perVin: i => total[i] * 1e6 / vins[i] };
  D.monthly = MONTHS.map(mo => {
    const ids = monthDayIdx(mo);
    const perVin = sum(ids.map(i => D.perVin(i)));
    return {
      perVin, days: ids.length, dailyPerVin: perVin / ids.length,
      total: sum(ids.map(i => total[i])), vins: sum(ids.map(i => vins[i])) / ids.length,
      split: sp ? sp.map((_, j) => sum(ids.map(i => D.perVin(i) * shares[j][i]))) : null,
      splitTotal: sp ? sp.map((_, j) => sum(ids.map(i => total[i] * shares[j][i]))) : null
    };
  });
  MOD_DATA[key] = D;
  return D;
}
    kpi: st => {
      const g = genSplit(pk, base, st.filter);
      if (st.view === 'Compare') return { value: F.signed(pch(g.g3, g.g2)), label: 'Gen 3 vs Gen 2' };
      return { value: F.tb(g.g2 + g.g3), label: 'per day, all generations' };
    },
    legend: () => [{ name: 'Gen 2', color: GEN_COLORS.g2 }, { name: 'Gen 3', color: GEN_COLORS.g3 }],
    render: (host, ctx) => {
      const g = genSplit(pk, base, ctx.st.filter);
      const s2 = { name: 'Gen 2', label: '2', value: g.g2, color: GEN_COLORS.g2 }, s3 = { name: 'Gen 3', label: '3', value: g.g3, color: GEN_COLORS.g3 };
      if (ctx.st.view === 'Compare') compareBars(host, { bars: [{ name: 'Gen 2', segments: [s2] }, { name: 'Gen 3', segments: [s3] }], diff: { a: 0, b: 1, label: '\u0394 Gen 3 vs Gen 2', pctOf: 0, color: GEN_COLORS.g3 }, inLabels: false, fmt: F.tb, axisFmt: A.tb, animate: ctx.animate });
      else compareBars(host, { bars: [{ name: 'All generations', segments: [s2, s3] }], sideLabels: true, fmt: F.tb, axisFmt: A.tb, animate: ctx.animate });
    }
  };
}
function vehicleCard(pk, base, opts) {
  opts = opts || {};
  const top = n => modelVals(pk, base).sort((a, b) => b.value - a.value).slice(0, n).sort((a, b) => a.value - b.value);
  return {
    title: 'Vehicle model (daily avg)', span: opts.span || 2,
    sub: opts.copy ? 'Same chart as TMS Data' : 'Average daily usage by vehicle model',
    controls: [{ type: 'toggle', key: 'view', options: ['Ranked', 'Stacked'], def: 'Ranked' }, { type: 'select', key: 'top', label: 'Show', options: [{ value: '5', label: 'Top 5' }, { value: '8', label: 'Top 8' }, { value: 'tbd', label: 'Full list TBD', disabled: true }], def: '5' }],
    kpi: st => { const v = top(+st.top), lead = v[v.length - 1]; return { value: lead.name, label: `highest at ${F.tb(lead.value)} per day` }; },
    legend: () => [],
    render: (host, ctx) => {
      const v = top(+ctx.st.top);
      if (ctx.st.view === 'Stacked') compareBars(host, { bars: [{ name: 'Top ' + v.length + ' models', segments: v.slice().reverse() }], sideLabels: true, fmt: F.tb, axisFmt: A.tb, animate: ctx.animate });
      else barChart(host, { labelName: 'Vehicle model', labels: v.map(m => m.name), series: [{ name: 'Daily avg', color: C.pool, colors: v.map(m => m.color), data: v.map(m => m.value) }], arrow: true, fmt: F.tb, axisFmt: A.tb, shortLabel: l => l.replace('Model ', ''), tipTitle: l => l, animate: ctx.animate });
    },
    note: 'Full model list and filter combinations are still TBD.'
  };
}
        { name: 'By pairing', segments: [{ name: 'A1 + A1/2', label: '', value: d.a1 + d.a12, color: AC.a1 }, { name: 'A0 + A0/1', label: '', value: d.a0 + d.a01, color: AC.a0 }], groups: [{ from: 0, to: 0, label: 'A1 + A1/2', color: AC.a1 }, { from: 1, to: 1, label: 'A0 + A0/1', color: AC.a0 }] }
      ], fmt: F.tb, animate: ctx.animate }); } },
    { title: '3 APN timeseries', span: 2, sub: '3A next to AR, with the monthly difference',
      controls: [{ type: 'range', key: 'range', options: ['6M', 'YTD', '1Y'], def: '6M' }],
      kpi: () => ({ value: F.signed(pch(D[lastM].ar, D[lastM].ra)), label: 'AR vs 3A, Sep 2026' }),
      legend: () => [{ name: '3A (RDD)', color: AC.a2 }, { name: 'AR (APN report)', color: AC.ar }],
      render: (host, ctx) => { const idx = monthRangeIdx(ctx.st.range); barChart(host, { labels: idx.map(i => MONTHS[i]), series: [{ name: '3A (RDD)', color: AC.a2, data: idx.map(i => D[i].ra) }, { name: 'AR (APN report)', color: AC.ar, data: idx.map(i => D[i].ar) }], mode: 'grouped', diffMarkers: true, fmt: F.tb, axisFmt: A.tb, xFmt: mShort, tipTitle: mo => mLong(mo), animate: ctx.animate }); } },
    { title: '1 APN total over time', span: 2, sub: 'Monthly 1 APN total (A0/1 and A1/2)',
      controls: [{ type: 'range', key: 'range', options: ['6M', 'YTD', '1Y'], def: '6M' }],
      kpi: () => ({ value: F.tb(D[lastM].one), label: '1 APN, Sep 2026', change: pch(D[lastM].one, D[lastM - 1].one), changeNote: 'vs Aug' }),
      legend: () => [{ name: '1 APN total', color: AC.a01 }],
      render: (host, ctx) => { const idx = monthRangeIdx(ctx.st.range); barChart(host, { labels: idx.map(i => MONTHS[i]), series: [{ name: '1 APN total', color: AC.a01, data: idx.map(i => D[i].one) }], fmt: F.tb, axisFmt: A.tb, xFmt: mShort, tipTitle: mo => mLong(mo), animate: ctx.animate }); } },
    { title: 'Combined timeseries', span: 2, sub: 'RDD total next to APN report total, 3 APN and 1 APN',
      controls: [{ type: 'range', key: 'range', options: ['6M', 'YTD', '1Y'], def: '6M' }],
      kpi: () => { const d = D[lastM]; return { value: F.signed(pch(d.ar + d.oneRep, d.ra + d.one)), label: 'report vs RDD, Sep 2026' }; },
      legend: () => [{ name: 'RDD total', color: C.iris }, { name: 'APN report total', color: AC.ar }],
      render: (host, ctx) => { const idx = monthRangeIdx(ctx.st.range); barChart(host, { labels: idx.map(i => MONTHS[i]), series: [{ name: 'RDD total', color: C.iris, data: idx.map(i => D[i].ra + D[i].one) }, { name: 'APN report total', color: AC.ar, data: idx.map(i => D[i].ar + D[i].oneRep) }], mode: 'grouped', fmt: F.tb, axisFmt: A.tb, xFmt: mShort, tipTitle: mo => mLong(mo), animate: ctx.animate }); } }
  ];
}
function rddHero(p) {
  const i = monthIdx(p.month), d = VAL.rdd[i], pv = VAL.rdd[i - 1];
  const g = pch(d.ar, d.ra), gp = pch(pv.ar, pv.ra), dp = g - gp;
  return { label: 'APN report above 3 APN RDD', value: F.signed(g), changeText: (dp >= 0 ? '+' : '\u2212') + Math.abs(dp).toFixed(1) + ' pts', tone: Math.abs(g) <= Math.abs(gp) ? 'up' : 'down', changeNote: 'vs prior month', meta: `${mLong(MONTHS[i])} billing month. Total diff value ${F.tb(d.ar - d.ra)}. ${AS_OF_TEXT}.` };
}

/* ---------------- TMS data ---------------- */
function tmsCards() {
  const key = 'tms', D = genModule(key), sp = D.c.splits, mod = MODS.tms, base = baseFor(key);
  const years = [2024, 2025, 2026];
  const yearAvg = y => { const ms = D.monthly.filter((_, i) => MONTHS[i].y === y); return sp.map((_, j) => sum(ms.map(m => m.split[j])) / ms.length); };
  return [
    { title: 'Per VIN usage (daily)', span: 3, sub: 'Average usage per subscriber on each day of the month',
      controls: [{ type: 'select', key: 'month', label: 'Choose month', options: MONTH_OPTS, def: LATEST }],
      kpi: st => { const mi = monthIdx(st.month), M = D.monthly[mi], P = D.monthly[mi - 1]; return { html: `<div class="kpi-pair"><div><span class="kpi-v">${F.mb(M.dailyPerVin)}</span><span class="kpi-l">avg per subscriber per day <span class="pill ${M.dailyPerVin >= P.dailyPerVin ? 'up' : 'down'}">${F.signed(pch(M.dailyPerVin, P.dailyPerVin))}</span></span></div><div><span class="kpi-v">${F.n(M.vins)}</span><span class="kpi-l"># of subs <span class="pill ${M.vins >= P.vins ? 'up' : 'down'}">${F.signed(pch(M.vins, P.vins))}</span></span></div></div>` }; },
        { id: 'carrier-apn1', mod: 'carrier', tab: 'APN 1 vs Internal Data', blurb: 'APN 1 bucket compared with internal CDN data', desc: 'Chapter 3.2. APN 1 bucket compared with internal CDN data.', pageMonth: true, hero: cv32Hero, cards: cv32Cards },
  { id: 'tms', mod: 'tms', parent: true, tab: 'Overview', desc: 'Per-VIN usage plus the generation and vehicle model mix.', hero: tmsHero, cards: tmsCards },
  { id: 'tms-detail', mod: 'tms', tab: 'Detail', desc: 'Generation, model, provisioning and protocol detail.', hero: () => detailHero(baseFor('tms')),
    cards: () => { const b = baseFor('tms'); return [genTypeCard('tms', b, { copy: true }), vehicleCard('tms', b, { copy: true }), provCard('tms-d', b), SW(), MAPV(), serviceCard('tms-d', b)]; } },
  { id: 'vtwin', mod: 'vtwin', parent: true, tab: 'Overview', desc: 'Total, daily and monthly usage per VIN.', hero: () => summaryHero('vtwin'), cards: () => summaryCards('vtwin') },
  { id: 'vtwin-detail', mod: 'vtwin', tab: 'Detail', desc: 'Vehicle model, provisioning and version detail.', hero: () => detailHero(baseFor('vtwin'), null, VT_NOTE),
    cards: () => { const b = baseFor('vtwin'); return [vehicleCard('vtwin', b, { copy: true, span: 3 }), provCard('vtwin', b, { span: 3 }), tbdCard('SW version', 'Software version mix', 3), tbdCard('Map version', 'Map version mix', 3)]; } },
  { id: 'vcrm-summary', mod: 'vcrm', tab: 'Summary', desc: 'Total, daily and monthly usage per VIN.', hero: () => summaryHero('vcrm'), cards: () => summaryCards('vcrm') },
  { id: 'vcrm-detail', mod: 'vcrm', tab: 'Detail', desc: 'Vehicle model, provisioning and version detail.', hero: () => detailHero(baseFor('vcrm'), null, VT_NOTE),
    cards: () => { const b = baseFor('vcrm'); return [vehicleCard('vcrm', b, { copy: true, span: 3 }), provCard('vcrm', b, { span: 3 }), tbdCard('SW version', 'Software version mix', 3), tbdCard('Map version', 'Map version mix', 3)]; } },
  { id: 'rdsp-summary', mod: 'rdsp', tab: 'Summary', desc: 'Total, daily and monthly usage per VIN.', hero: () => summaryHero('rdsp'), cards: () => summaryCards('rdsp') },
  { id: 'map-ota-summary', mod: 'mapota', tab: 'Summary', desc: 'Map OTA usage split by 3+ and 3\u2212.', hero: () => summaryHero('mapota'), cards: () => summaryCards('mapota') },
  { id: 'map-ota-3plus', mod: 'mapota', tab: '3+', desc: 'Detail for MAP-OTA 3+.', hero: () => detailHero(baseFor('mapota', 0.58), 'VINs in MAP-OTA 3+, Sep 2026'),
    cards: () => { const b = baseFor('mapota', 0.58); return [genTypeCard('map3p', b, { copy: true }), vehicleCard('map3p', b, { copy: true }), provCard('map3p', b), tbdCard('SW version', 'Software version mix', 3), tbdCard('Map version', 'Map version mix', 3)]; } },
  { id: 'map-ota-3minus', mod: 'mapota', tab: '3\u2212', desc: 'Detail for MAP-OTA 3\u2212.', hero: () => detailHero(baseFor('mapota', 0.42), 'VINs in MAP-OTA 3\u2212, Sep 2026'),
    cards: () => { const b = baseFor('mapota', 0.42); return [genTypeCard('map3m', b, { copy: true }), vehicleCard('map3m', b, { copy: true }), provCard('map3m', b), tbdCard('SW version', 'Software version mix', 3), tbdCard('Map version', 'Map version mix', 3)]; } },
  { id: 'ecu-ota-summary', mod: 'ecuota', tab: 'Summary', desc: 'ECU OTA usage split by warranty and enhancement.', hero: () => summaryHero('ecuota'), cards: () => summaryCards('ecuota') },
  { id: 'ecu-ota-warranty', mod: 'ecuota', tab: 'Warranty', desc: 'Detail for ECU OTA warranty updates.', hero: () => detailHero(baseFor('ecuota', 0.37), 'VINs with warranty updates, Sep 2026'),
    cards: () => { const b = baseFor('ecuota', 0.37); return [genTypeCard('ecuw', b, { copy: true }), vehicleCard('ecuw', b, { copy: true }), provCard('ecuw', b), tbdCard('SW version', 'Software version mix', 3), tbdCard('Map version', 'Map version mix', 3)]; } },
  { id: 'ecu-ota-enhancement', mod: 'ecuota', tab: 'Enhancement', desc: 'Detail for ECU OTA enhancement updates.', hero: () => detailHero(baseFor('ecuota', 0.63), 'VINs with enhancement updates, Sep 2026'),
    cards: () => { const b = baseFor('ecuota', 0.63); return [genTypeCard('ecue', b, { copy: true }), vehicleCard('ecue', b, { copy: true }), provCard('ecue', b), tbdCard('SW version', 'Software version mix', 3), tbdCard('Map version', 'Map version mix', 3)]; } },
  { id: 'm-ota-summary', mod: 'mota', tab: 'Summary', desc: 'Online map OTA usage split by cache and SPD.', hero: () => summaryHero('mota'), cards: () => summaryCards('mota') },
  { id: 'subscription-summary', mod: 'sub', tab: 'Summary', desc: 'Active subscriptions for HMA and GMA, and whether their trends match.', hero: subHero, cards: subCards },
  { id: 'subscription-detail', mod: 'sub', tab: 'Detail', desc: 'Subscription type, generation, model, version and provisioning detail.',
    hero: () => { const d = SUBS[lastM], p = SUBS[lastM - 1]; return detailHero({ vins: d.hma + d.gma, prevVins: p.hma + p.gma }, 'Subscribed VINs, Sep 2026'); },
    cards: () => { const d = SUBS[lastM], p = SUBS[lastM - 1]; const b = { dailyTB: baseFor('tms').dailyTB * 0.82, vins: d.hma + d.gma, prevVins: p.hma + p.gma }; return [tbdCard('Subscription type', 'Mix of subscription plans'), genTypeCard('subd', b, { copy: true }), vehicleCard('subd', b, { copy: true }), SW(), MAPV(), provCard('subd', b)]; } }
];
  return t;
}

/* ---------- on-screen table ---------- */
function cellText(v, kind) {
  if (v == null || v === '') return '';
  if (kind === 'text') return xesc(v);
  if (kind === 'int') return Math.round(v).toLocaleString('en-US');
  if (kind === 'pct') return v.toLocaleString('en-US', { minimumFractionDigits: 1, maximumFractionDigits: 1 }) + '%';
  return v.toLocaleString('en-US', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
}
function renderTables(host, tables) {
  host.innerHTML = tables.map(t => `${t.caption ? `<div class="tbl-cap">${xesc(t.caption)}</div>` : ''}<table class="dt"><thead><tr>${t.columns.map(c => `<th class="${c.kind === 'text' ? '' : 'n'}" scope="col">${xesc(c.name)}</th>`).join('')}</tr></thead><tbody>${t.rows.map(r => `<tr${r.total ? ' class="total"' : ''}>${r.map((v, i) => `<td class="${t.columns[i].kind === 'text' ? '' : 'n'}">${cellText(v, t.columns[i].kind)}</td>`).join('')}</tr>`).join('')}</tbody></table>`).join('');
}

/* ---------- .xlsx writer (no library needed) ---------- */
const CRC_T = (() => { const t = new Uint32Array(256); for (let n = 0; n < 256; n++) { let c = n; for (let k = 0; k < 8; k++) c = c & 1 ? 0xEDB88320 ^ (c >>> 1) : c >>> 1; t[n] = c >>> 0; } return t; })();
function crc32(b) { let c = 0xFFFFFFFF; for (let i = 0; i < b.length; i++) c = CRC_T[(c ^ b[i]) & 255] ^ (c >>> 8); return (c ^ 0xFFFFFFFF) >>> 0; }
function zipStore(files) {
  const enc = new TextEncoder(), parts = [], central = [];
  const u16 = v => [v & 255, (v >>> 8) & 255], u32 = v => [v & 255, (v >>> 8) & 255, (v >>> 16) & 255, (v >>> 24) & 255];
  const dosDate = ((AS_OF.getFullYear() - 1980) << 9) | ((AS_OF.getMonth() + 1) << 5) | AS_OF.getDate();
  let off = 0;
  files.forEach(f => {
    const nm = enc.encode(f.name), d = enc.encode(f.text), crc = crc32(d);
    const head = Uint8Array.from([...u32(0x04034b50), ...u16(20), ...u16(0), ...u16(0), ...u16(0), ...u16(dosDate), ...u32(crc), ...u32(d.length), ...u32(d.length), ...u16(nm.length), ...u16(0)]);
    parts.push(head, nm, d);
    central.push(Uint8Array.from([...u32(0x02014b50), ...u16(20), ...u16(20), ...u16(0), ...u16(0), ...u16(0), ...u16(dosDate), ...u32(crc), ...u32(d.length), ...u32(d.length), ...u16(nm.length), ...u16(0), ...u16(0), ...u16(0), ...u16(0), ...u32(0), ...u32(off)]), nm);
    off += head.length + nm.length + d.length;
  });
  const cdSize = central.reduce((a, b) => a + b.length, 0);
  const end = Uint8Array.from([...u32(0x06054b50), ...u16(0), ...u16(0), ...u16(files.length), ...u16(files.length), ...u32(cdSize), ...u32(off), ...u16(0)]);
  return new Blob([...parts, ...central, end], { type: 'application/vnd.openxmlformats-officedocument.spreadsheetml.sheet' });
}
  const sheetName = xesc(meta.sheet.replace(/[\[\]:*?\/\\]/g, ' ').slice(0, 31).trim() || 'Data');
  return zipStore([
    { name: '[Content_Types].xml', text: `${X}<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types"><Default Extension="rels" ContentType="application/vnd.openxmlformats-package.relationships+xml"/><Default Extension="xml" ContentType="application/xml"/><Override PartName="/xl/workbook.xml" ContentType="application/vnd.openxmlformats-officedocument.spreadsheetml.sheet.main+xml"/><Override PartName="/xl/worksheets/sheet1.xml" ContentType="application/vnd.openxmlformats-officedocument.spreadsheetml.worksheet+xml"/><Override PartName="/xl/styles.xml" ContentType="application/vnd.openxmlformats-officedocument.spreadsheetml.styles+xml"/></Types>` },
    { name: '_rels/.rels', text: `${X}<Relationships xmlns="http://schemas.openxmlformats.org/package/2006/relationships"><Relationship Id="rId1" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument" Target="xl/workbook.xml"/></Relationships>` },
    { name: 'xl/workbook.xml', text: `${X}<workbook xmlns="http://schemas.openxmlformats.org/spreadsheetml/2006/main" xmlns:r="http://schemas.openxmlformats.org/officeDocument/2006/relationships"><sheets><sheet name="${sheetName}" sheetId="1" r:id="rId1"/></sheets></workbook>` },
    { name: 'xl/_rels/workbook.xml.rels', text: `${X}<Relationships xmlns="http://schemas.openxmlformats.org/package/2006/relationships"><Relationship Id="rId1" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/worksheet" Target="worksheets/sheet1.xml"/><Relationship Id="rId2" Type="http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles" Target="styles.xml"/></Relationships>` },
    { name: 'xl/styles.xml', text: styles },
    { name: 'xl/worksheets/sheet1.xml', text: sheet }
  ]);
}
function filterText(card, st, page, pst) {
  const parts = [];
  if (page.pageMonth) { const op = MONTH_OPTS.find(x => x.value === pst.month); parts.push('Billing month ' + (op ? op.label : pst.month)); }
  (card.controls || []).forEach(c => {
    if (c.show && !c.show(st)) return;
    const v = st[c.key];
    if (c.type === 'select') { const op = c.options.find(x => x.value === v); parts.push((c.label || 'Filter') + ' ' + (op ? op.label : v)); }
    else parts.push((c.type === 'range' ? 'Range ' : 'View ') + v);
  });
  return 'Filters: ' + (parts.length ? parts.join(', ') : 'none');
}
function downloadCard(page, card, st, pst) {
  const tables = cardTables(card, { st, pst, animate: false, big: false, page });
  const mod = MODS[page.mod], path = [secOfMod(page.mod).name, mod.name].concat(page.parent ? [] : [page.tab]).join(' / ');
  const blob = buildXlsx({ title: card.title, sheet: card.title, lines: [path, filterText(card, st, page, pst), AS_OF_TEXT + '. Sample data.'] }, tables);
  const name = `${mod.name} ${page.parent ? '' : page.tab + ' '}- ${card.title}`.replace(/[\\/:*?"<>|]+/g, '-').replace(/\s+/g, ' ').trim() + '.xlsx';
  const url = URL.createObjectURL(blob), a = document.createElement('a');
  a.href = url; a.download = name; document.body.appendChild(a); a.click();
  setTimeout(() => { URL.revokeObjectURL(url); a.remove(); }, 2000);
  return name;
}

/* ==========================================================================
   App shell: three interchangeable design concepts over the same dashboards
   A = Sidebar (tree navigation), B = Bento (top bar + color-blocked grid),
   C = Focus (icon rail + section panel, featured chart, KPI strip)========================================================================== */
const ICON = {
  expand: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M9.5 2.5h4v4M6.5 13.5h-4v-4M13.5 2.5 9 7M2.5 13.5 7 9"/></svg>',
  close: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round"><path d="M4 4l8 8M12 4l-8 8"/></svg>',
  left: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M10 3 5 8l5 5"/></svg>',
  right: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M6 3l5 5-5 5"/></svg>',
  menu: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round"><path d="M2.5 4.5h11M2.5 8h11M2.5 11.5h11"/></svg>',
  home: '<svg viewBox="0 0 16 16" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linejoin="round"><path d="M2.5 7.2 8 2.8l5.5 4.4v6H9.6V9.6H6.4v3.6H2.5z"/></svg>',
  out: '<svg viewBox="0 0 16 16" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M6 2.5H3.5v11H6M10 5l3 3-3 3M13 8H6.5"/></svg>',
  chev: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round"><path d="M6 3.5 10.5 8 6 12.5"/></svg>',
  finance: '<svg viewBox="0 0 16 16" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linejoin="round"><rect x="1.8" y="4" width="12.4" height="8.5" rx="2"/><circle cx="8" cy="8.25" r="1.9"/></svg>',
  validation: '<svg viewBox="0 0 16 16" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="8" cy="8" r="5.9"/><path d="M5.4 8.2 7.2 10l3.4-3.7"/></svg>',
  monitoring: '<svg viewBox="0 0 16 16" width="16" height="16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"><path d="M1.6 8.6h2.7l1.7-4.3 2.7 7.6 1.9-4.6h3.8"/></svg>',
  table: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linejoin="round"><rect x="2" y="2.8" width="12" height="10.4" rx="2"/><path d="M2 6.3h12M2 9.7h12M6.4 6.3v6.9"/></svg>',
  chart: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round"><path d="M3 13.2V8.5M6.3 13.2V4.2M9.7 13.2V6.6M13 13.2V2.8"/></svg>',
  download: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M8 2.5v7.6M4.8 7.2 8 10.4l3.2-3.2M2.8 12.8h10.4"/></svg>',
  search: '<svg viewBox="0 0 16 16" fill="none" stroke="currentColor" stroke-width="1.7" stroke-linecap="round"><circle cx="7.2" cy="7.2" r="4.6"/><path d="m10.6 10.6 3 3"/></svg>',
  play: '<svg viewBox="0 0 16 16" fill="currentColor"><path d="M5 3.4v9.2c0 .5.5.8.9.5l7-4.6a.6.6 0 0 0 0-1l-7-4.6c-.4-.3-.9 0-.9.5z"/></svg>',
  pencil: '<svg viewBox="0 0 20 20" width="20" height="20" fill="none" stroke="currentColor" stroke-width="1.6" stroke-linecap="round" stroke-linejoin="round"><path d="M3.5 16.5h13M5 12.8 13.2 4.6a1.7 1.7 0 0 1 2.4 2.4L7.4 15.2 4.2 16z"/></svg>'
};
      <p class="fine">Prototype: any email and password will work.</p>
    </form>
  </main>`;
  document.getElementById('loginForm').addEventListener('submit', e => { e.preventDefault(); go('home'); });
}

/* ==========================================================================
   Concept A: sidebar tree
   ========================================================================== */
function twist(node, name, open) {
  return `<button class="twist" type="button" data-twist="${node}" aria-expanded="${open}" aria-label="Show or hide ${esc(name)} pages">${ICON.chev}</button>`;
}
function shellA(route) {
  const page = pageById(route), activeMod = page ? page.mod : null;
  const isOpen = (node, def) => (state.open.has(node) ? state.open.get(node) : def);
  let nav = `<a class="nav-link lvl2${route === 'home' ? ' active' : ''}" style="--c:${C.pool}" href="#/home">${ICON.home}<span>Home</span></a>`;
  SECTIONS.forEach(sec => {
    const open = isOpen(sec.id, true), hasKids = sec.mods.length > 0;
    nav += `<div class="tgroup sec${open ? ' open' : ''}"><div class="trow"><a class="nav-link lvl3${route === sec.id ? ' active' : ''}" style="--c:${sec.color}" href="#/${sec.id}">${ICON[sec.id]}<span>${sec.name}</span></a>${hasKids ? twist(sec.id, sec.name, open) : ''}</div>`;
    if (hasKids) {
      nav += '<div class="tkids">';
      sec.mods.forEach(k => {
        const m = MODS[k], ps = pagesOf(k), kids = ps.filter(p => !p.parent), on = k === activeMod, mOpen = isOpen(k, on);
        nav += `<div class="tgroup mod${mOpen ? ' open' : ''}"><div class="trow"><a class="nav-link lvl4${on ? ' active' : ''}${on && page.parent ? ' here' : ''}" style="--c:${m.color}" href="#/${ps[0].id}"${on && page.parent ? ' aria-current="page"' : ''}><span class="dot"></span><span>${m.name}</span></a>${kids.length ? twist(k, m.name, mOpen) : ''}</div>`;
        if (kids.length) nav += `<div class="tkids nav-sub" style="--c:${m.color}">${kids.map(p => `<a href="#/${p.id}" class="${p.id === route ? 'active' : ''}"${p.id === route ? ' aria-current="page"' : ''}>${p.tab}</a>`).join('')}</div>`;
        nav += '</div>';
      });
      nav += '</div>';
    }
    nav += '</div>';
  });
}
function selectHTML(opts, val, cls, label, attr) {
  return `<select class="${cls}" aria-label="${esc(label || 'Choose')}"${attr ? ' ' + attr : ''}>${opts.map(o => `<option value="${o.value}"${o.value === val ? ' selected' : ''}${o.disabled ? ' disabled' : ''}>${esc(o.label)}</option>`).join('')}</select>`;
}
function pageInfo(page) {
  const pst = state.page[page.id] || (state.page[page.id] = { month: LATEST });
  return { mod: MODS[page.mod], ps: pagesOf(page.mod), i: PAGES.indexOf(page), sec: secOfMod(page.mod), pst, h: page.hero(pst) };
}
const crumbsHTML = (page, I) => `<nav class="crumbs" aria-label="Breadcrumb"><a href="#/home">Home</a><span class="sep">›</span><a href="#/${I.sec.id}">${I.sec.name}</a><span class="sep">›</span>${page.parent ? `<span>${I.mod.name}</span>` : `<a href="#/${I.ps[0].id}">${I.mod.name}</a><span class="sep">›</span><span>${page.tab}</span>`}</nav>`;
function quoteHTML(h) {
  const [hv, hu] = splitUnit(h.value);
  return `<div class="quote-label">${h.label}</div><div class="quote-main"><span class="quote-value">${hv}${hu ? `<small>${hu}</small>` : ''}</span>${changeHTML(h, 'chg')}</div><div class="quote-meta">${h.meta}</div>`;
}
const monthSel = I => `<label class="sel-wrap">Billing month ${selectHTML(MONTH_OPTS, I.pst.month, 'sel', 'Billing month', 'data-pmonth')}</label>`;
const tabsHTML = (page, I, cls) => (I.ps.length > 1 ? `<nav class="${cls}" aria-label="${I.mod.name} views">${I.ps.map(p => `<a class="tab${p.id === page.id ? ' active' : ''}" href="#/${p.id}"${p.id === page.id ? ' aria-current="page"' : ''}>${p.tab}</a>`).join('')}</nav>` : '');
const cardsOf = page => page._cards || (page._cards = page.cards());
function bindPage(view, page, I, rerender) {
  view.querySelectorAll('[data-prev]').forEach(b => { b.disabled = I.i === 0; b.onclick = () => go(PAGES[I.i - 1].id); });
  view.querySelectorAll('[data-next]').forEach(b => { b.disabled = I.i === PAGES.length - 1; b.onclick = () => go(PAGES[I.i + 1].id); });
  view.querySelectorAll('[data-pmonth]').forEach(s => { s.onchange = () => { I.pst.month = s.value; const y = window.scrollY; rerender(page); window.scrollTo(0, y); }; });
}

/* ---------- concept A page ---------- */
function pageA(page) {
  const I = pageInfo(page), view = document.getElementById('view');
  view.style.setProperty('--c', I.mod.color);
  view.innerHTML = `
    <div class="crumb-row">${crumbsHTML(page, I)}<span class="sample">Sample data</span></div>
    <div class="head">
      <div class="title-row"><span class="glyph">${I.mod.short}</span><div><h1>${I.mod.name}</h1><p class="page-sub">${page.desc}</p></div></div>
      <div class="pager">
        <button class="btn" data-prev aria-label="Previous dashboard">${ICON.left}Previous</button>
        <span class="pager-count">${I.i + 1} of ${PAGES.length}</span>
        <button class="btn" data-next aria-label="Next dashboard">Next${ICON.right}</button>
      </div>
    </div>
    <section class="quote" aria-label="Headline metric"><div>${quoteHTML(I.h)}</div>${page.pageMonth ? `<div class="quote-ctl">${monthSel(I)}</div>` : ''}</section>
    ${tabsHTML(page, I, 'tabs')}
    <section class="grid" id="grid"></section>`;
  bindPage(view, page, I, pageA);
  const grid = view.querySelector('#grid');
  cardsOf(page).forEach((card, k) => mountCard(page, card, k, grid));
}
    <aside class="c-panel" aria-label="Dashboards in this section"><div class="c-app">Wireless Billing Management<span>Hyundai AutoEver</span></div>${panel}</aside>
    <main class="c-main"><div id="view"></div></main>
  </div>`;
}
function pageC(page) {
  const I = pageInfo(page), view = document.getElementById('view');
  view.style.setProperty('--c', I.mod.color);
  view.innerHTML = `
    <div class="c-toolbar">${crumbsHTML(page, I)}<div class="c-tb-r">${page.pageMonth ? monthSel(I) : ''}${paletteBtn()}<div class="c-pager"><button class="btn" data-prev aria-label="Previous dashboard">${ICON.left}</button><span>${I.i + 1} of ${PAGES.length}</span><button class="btn" data-next aria-label="Next dashboard">${ICON.right}</button></div></div></div>
    <header class="c-head"><span class="glyph">${I.mod.short}</span><div><h1>${I.mod.name}</h1><p class="page-sub">${page.desc}</p></div><span class="sample">Sample data</span></header>
    ${tabsHTML(page, I, 'c-tabs')}
    <div class="c-strip" id="strip" role="list" aria-label="Key numbers on this page"></div>
    <section class="c-grid" id="grid"></section>`;
  bindPage(view, page, I, pageC);
  const cards = cardsOf(page), grid = view.querySelector('#grid'), feat = !cards[0].tbd;
  const rest = feat ? cards.length - 1 : cards.length;
  const restSpans = { 0: [], 1: [12], 2: [6, 6], 3: [4, 4, 4], 4: [6, 6, 6, 6], 5: [4, 4, 4, 6, 6], 6: [4, 4, 4, 4, 4, 4] }[rest] || Array(rest).fill(4);
  cards.forEach((card, k) => mountCard(page, card, k, grid, { cls: 'g' + (feat ? (k === 0 ? 12 : restSpans[k - 1]) : restSpans[k]), feat: feat && k === 0 }));
  const strip = view.querySelector('#strip');
  const refresh = () => {
    strip.innerHTML = `<div class="c-chip hero" role="listitem"><span class="t">${I.h.label}</span><span class="v">${I.h.value}</span>${changeHTML(I.h, 'pill')}</div>` +
      [...grid.children].map((el, k) => {
        const v = el.querySelector('.card-kpi .kpi-v'); if (!v) return '';
        const p = el.querySelector('.card-kpi .pill'), tone = p ? (p.classList.contains('up') ? 'up' : p.classList.contains('down') ? 'down' : 'flat') : '';
        return `<button type="button" class="c-chip" role="listitem" data-k="${k}" title="Go to ${esc(el.querySelector('h3').textContent)}"><span class="t">${esc(el.querySelector('h3').textContent)}</span><span class="v">${v.textContent}</span>${p ? `<span class="pill ${tone}">${p.textContent}</span>` : ''}</button>`;
      }).join('');
    strip.querySelectorAll('[data-k]').forEach(b => b.onclick = () => { const el = grid.children[+b.dataset.k]; el.scrollIntoView({ behavior: 'smooth', block: 'center' }); el.classList.add('ping'); setTimeout(() => el.classList.remove('ping'), 1400); });
  };
  refresh();
  grid.addEventListener('kpichange', () => { cancelAnimationFrame(strip._raf); strip._raf = requestAnimationFrame(refresh); });
}
        w.querySelector('select').onchange = e => { st[c.key] = e.target.value; draw(true); };
        ctlEl.appendChild(w);
      }
    });
  };
  const drawKpi = () => {
    if (!card.kpi) { kpiEl.style.display = 'none'; return; }
    const v = card.kpi(st, pst);
    kpiEl.innerHTML = v.html ? v.html : `<span class="kpi-v">${v.value}</span><span class="kpi-l">${v.label || ''}</span>${changeHTML(v, 'pill')}`;
    el.dispatchEvent(new CustomEvent('kpichange', { bubbles: true }));
  };
  const drawLegend = () => {
    const items = card.legend ? card.legend(st, pst) : [];
    legEl.innerHTML = items.map(it => `<span><i class="${it.type === 'line' ? 'ln' : it.type === 'dash' ? 'dash' : ''}" style="background:${it.color || 'transparent'}"></i>${it.name}</span>`).join('');
  };
  const baseCls = 'chart-host' + (card.auto ? ' auto' : ''), viewBtn = el.querySelector('[data-view]');
  const drawChart = animate => {
    const ctx = { st, pst, animate, big, page }, tv = st._view === 'table';
    host.className = baseCls + (tv ? ' table-mode' : '');
    el.classList.toggle('tview', tv);
    viewBtn.innerHTML = tv ? ICON.chart + '<span>Chart</span>' : ICON.table + '<span>Table</span>';
    viewBtn.setAttribute('aria-pressed', tv);
    viewBtn.title = tv ? 'Back to the chart' : 'Show the data behind this chart as a table';
    if (tv) { renderTables(host, cardTables(card, ctx)); host.setAttribute('tabindex', '0'); host.setAttribute('aria-label', card.title + ' data table'); }
    else { host.removeAttribute('tabindex'); host.removeAttribute('aria-label'); card.render(host, ctx); }
  };
  viewBtn.onclick = () => { st._view = st._view === 'table' ? 'chart' : 'table'; drawChart(true); };
  el.querySelector('[data-dl]').onclick = () => downloadCard(page, card, st, pst);
  const draw = animate => { drawCtl(); drawKpi(); drawLegend(); drawChart(animate); };
  host._redraw = () => drawChart(false);
  el._draw = draw;
  draw(true);
  if (!card.auto) ro.observe(host);
  const ex = el.querySelector('[data-expand]');
  if (ex) ex.onclick = () => openModal(page, card, k, el);
  const cl = el.querySelector('[data-close]');
  if (cl) cl.onclick = () => closeModal();
  return el;
}
  const c = el.querySelector('[data-close]'); if (c) c.focus();
}
function closeModal(silent) {
  const m = document.getElementById('modal');
  if (!m || !m.classList.contains('open')) return;
  m.classList.remove('open'); m.innerHTML = ''; document.body.style.overflow = '';
  if (modalSrc && !silent) { modalSrc._draw(false); const b = modalSrc.querySelector('[data-expand]'); if (b) b.focus(); }
  modalSrc = null;
}

/* ---------- command palette ---------- */
function paletteItems() {
  const items = [{ label: 'Home', hint: 'Overview of every dashboard', route: 'home', color: C.pool }];
  SECTIONS.forEach(s => items.push({ label: s.name, hint: 'Section', route: s.id, color: s.color }));
  PAGES.forEach(p => { const m = MODS[p.mod]; items.push({ label: p.parent ? m.name : p.mod === 'carrier' ? p.tab : `${m.name} ${p.tab}`, hint: secOfMod(p.mod).name + (p.parent ? '' : ' / ' + m.name), route: p.id, color: m.color }); });
  return items;
}
let palReturn = null;
function openPalette() {
  const P = document.getElementById('palette'); if (!P || P.classList.contains('open')) return;
  palReturn = document.activeElement;
  P.innerHTML = `<div class="pal-box" role="dialog" aria-modal="true" aria-label="Jump to a dashboard"><div class="pal-in">${ICON.search}<input type="text" placeholder="Jump to a dashboard, module or section" aria-label="Search dashboards" aria-controls="palList" autocomplete="off" spellcheck="false"><kbd>Esc</kbd></div><ul class="pal-list" id="palList" role="listbox" aria-label="Matching dashboards"></ul><div class="pal-foot">Arrow keys to move, Enter to open</div></div>`;
  P.classList.add('open'); document.body.style.overflow = 'hidden';
  const inp = P.querySelector('input'), list = P.querySelector('ul'), all = paletteItems();
  let shown = all, sel = 0;
  const mark_ = () => { [...list.children].forEach((li, i) => { li.classList.toggle('on', i === sel); li.setAttribute('aria-selected', i === sel); }); const on = list.children[sel]; if (on) on.scrollIntoView({ block: 'nearest' }); };
  const draw = () => { list.innerHTML = shown.length ? shown.map((it, i) => `<li role="option" data-i="${i}"><span class="dot" style="background:${it.color}"></span><b>${esc(it.label)}</b><span>${esc(it.hint)}</span></li>`).join('') : '<li class="none" role="option" aria-disabled="true">No dashboards match that search</li>'; mark_(); };
  const VAL_SERIES = {
  'carrier-rdd': { s: () => VAL.rdd.map(d => pch(d.ar, d.ra)), signed: true },
  'carrier-tbd': { s: () => VAL.cv31.map(d => d.gap * 100) },
  'carrier-apn1': { s: () => VAL.cv32.map(d => d.gap * 100) }
};
function modMetric(k) {
  if (k === 'sub') { const d = SUBS[lastM], p = SUBS[lastM - 1]; return { metric: 'Active subscriptions', val: F.n(d.hma + d.gma), chg: pch(d.hma + d.gma, p.hma + p.gma), series: SUBS.slice(-12).map(x => x.hma + x.gma) }; }
  const D = genModule(k);
  if (k === 'tms') { const M = D.monthly, s = []; for (let i = ND - 90; i < ND; i++) s.push(D.perVin(i)); return { metric: 'Avg per VIN per day', val: F.mb(M[lastM].dailyPerVin), chg: pch(M[lastM].dailyPerVin, M[lastM - 1].dailyPerVin), series: s }; }
  const t = totalState(D, '1M'); return { metric: 'Usage, last 30 days', val: F.tb(t.cur), chg: pch(t.cur, t.prev), series: D.total.slice(ND - 90) };
}
function valMetric(id) {
  const cfg = VAL_SERIES[id], s = cfg.s().slice(-12), v = s[11], pv = s[10];
  return { text: cfg.signed ? F.signed(v) : v.toFixed(1) + '%', delta: v - pv, better: Math.abs(v) <= Math.abs(pv), series: s };
}
const ptsText = d => (d >= 0 ? '+' : '\u2212') + Math.abs(d).toFixed(1) + ' pts';
const secOfMonitoring = () => SECTIONS.find(x => x.id === 'monitoring');
const SEC_NOTE = { finance: 'Not defined yet', validation: 'Gap for the Sep 2026 billing month, last 12 months shown', monitoring: 'Last 30 days compared with the 30 days before' };

function financeHTML() {
  return `<div class="fin-card" role="link" tabindex="0" data-go="finance" style="--c:${C.honey}"><span class="glyph">${ICON.finance}</span><div><h3>Finance dashboards are TBD</h3><p>Mockups, data model and data files are still to be defined.</p></div></div>`;
}
function valCard(p, cls) {
  return `<div class="${cls}" role="link" tabindex="0" data-go="${p.id}" style="--c:${MODS.carrier.color}">
      <div><h3>${p.tab}</h3><p>${p.blurb}</p><div class="tk-val" data-vval="${p.id}"></div></div>
      <div class="tk-spark" data-vspark="${p.id}"></div></div>`;
}
const valHTML = () => `<div class="val-cards">${pagesOf('carrier').map(p => valCard(p, 'val-card')).join('')}</div>`;
function tickerItem(k, cls) {
  const m = MODS[k], ps = pagesOf(k);
  return `<div class="${cls}" role="link" tabindex="0" data-go="${ps[0].id}" style="--c:${m.color}">
      <div class="tk-top"><span class="glyph">${m.short}</span><div><div class="tk-name">${m.name}</div><div class="tk-metric" data-metric="${k}"></div></div></div>
      <div class="tk-val" data-val="${k}"></div>
      <div class="tk-spark" data-spark="${k}"></div>
      <div class="tk-links">${ps.map(p => `<a class="chip" href="#/${p.id}">${p.tab}</a>`).join('')}</div>
    </div>`;
}
    <div class="crumb-row"><nav class="crumbs" aria-label="Breadcrumb"><span>Home</span></nav><span class="sample">Sample data</span></div>
    <h1 class="hello">${greeting()}</h1>
    <p class="hello-sub">Usage across connected-vehicle services as of Oct 5, 2026. Open any dashboard, then use Previous and Next or the arrow keys to click through all ${PAGES.length}.</p>
    ${SECTIONS.map(sec => `<div class="sec-h"><h2><a href="#/${sec.id}">${sec.name}</a></h2><p>${SEC_NOTE[sec.id]}</p></div>${body[sec.id]()}`).join('')}`;
  hydrate(view);
}
function sectionA(sec) {
  const view = document.getElementById('view');
  view.style.setProperty('--c', sec.color);
  const body = sec.id === 'finance' ? `<section class="grid">${financeBig(sec)}</section>`
    : sec.id === 'validation' ? `<div class="sec-h"><h2><a href="#/${pagesOf('carrier')[0].id}">Carrier Validation</a></h2><p>${SEC_NOTE.validation}</p></div>${valHTML()}`
    : `<div class="sec-h"><h2>All monitoring dashboards</h2><p>${SEC_NOTE.monitoring}</p></div>${tickersHTML()}`;
  view.innerHTML = `
    <div class="crumb-row"><nav class="crumbs" aria-label="Breadcrumb"><a href="#/home">Home</a><span class="sep">›</span><span>${sec.name}</span></nav><span class="sample">Sample data</span></div>
    <div class="head"><div class="title-row"><span class="glyph sec-glyph">${ICON[sec.id]}</span><div><h1>${sec.name}</h1><p class="page-sub">${sec.desc}</p></div></div></div>
    <div class="sec-body">${body}</div>`;
  hydrate(view);
}

/* B: bento home + section */
const bSecH = id => { const s = SECTIONS.find(x => x.id === id); return `<div class="g12 b-sec-h"><h2><a href="#/${id}">${s.name}</a></h2><p>${SEC_NOTE[id]}</p></div>`; };
const bVal = () => pagesOf('carrier').map(p => valCard(p, 'tile g4 vt')).join('');
const bMon = () => secOfMonitoring().mods.map(k => tickerItem(k, 'tile g3 mt')).join('');
const bFin = cls => `<div class="tile ${cls} fin" role="link" tabindex="0" data-go="finance" style="--c:${C.honey}"><span class="glyph">${ICON.finance}</span><h3>Finance</h3><p>Dashboards TBD. Mockups, data model and data files are still to be defined.</p></div>`;
function homeB() {
  const view = document.getElementById('view');
  view.innerHTML = `<section class="bento b-home">
    <div class="tile g8 greet" style="--c:${C.iris}">
      <span class="sample">Sample data</span>
      <h1 class="b-title">${greeting()}</h1>
      <p>Wireless data usage and billing across ${PAGES.length} dashboards, as of Oct 5, 2026.</p>
      <div class="greet-actions"><button type="button" class="b-cta" data-tour>${ICON.play}Start walkthrough</button><button type="button" class="b-ghost" data-palette>${ICON.search}Jump to a dashboard<kbd>${KBD}</kbd></button></div>
    </div>
    ${bFin('g4')}${bSecH('validation')}${bVal()}${bSecH('monitoring')}${bMon()}
  </section>`;
  hydrate(view);
}
function hydrateWatch(view) {
  view.querySelectorAll('[data-wv]').forEach(el => {
    const id = el.dataset.wv;
    if (VAL_SERIES[id]) {
      const M = valMetric(id);
      el.textContent = M.text;
      view.querySelector(`[data-wc="${id}"]`).innerHTML = `<span class="pill ${M.better ? 'up' : 'down'}">${ptsText(M.delta)}</span>`;
      sparkline(view.querySelector(`[data-ws="${id}"]`), M.series, M.better ? UP_C : DOWN_C, { animate: true });
    } else {
      const M = modMetric(id), good = M.chg >= 0;
      el.textContent = M.val; view.querySelector(`[data-wm="${id}"]`).textContent = M.metric;
      view.querySelector(`[data-wc="${id}"]`).innerHTML = `<span class="pill ${good ? 'up' : 'down'}">${F.signed(M.chg)}</span>`;
      sparkline(view.querySelector(`[data-ws="${id}"]`), M.series, good ? UP_C : DOWN_C, { animate: true });
    }
  });
  bindGo(view);
}
function homeC() {
  const view = document.getElementById('view');
  view.style.setProperty('--c', C.pool);
  view.innerHTML = `<div class="c-toolbar"><nav class="crumbs" aria-label="Breadcrumb"><span>Home</span></nav><div class="c-tb-r">${paletteBtn()}</div></div>
    <header class="c-head"><span class="glyph sec-glyph">${ICON.home}</span><div><h1>${greeting()}</h1><p class="page-sub">Every dashboard at a glance, as of Oct 5, 2026. Select a row to open it.</p></div><button type="button" class="btn" data-tour>${ICON.play}Start walkthrough</button></header>
    <div class="c-sec-h"><h2>Watchlist</h2><span class="sample">Sample data</span></div>
    ${watchlist(SECTIONS)}`;
  hydrateWatch(view);
}
function sectionC(sec) {
  const view = document.getElementById('view');
  view.style.setProperty('--c', sec.color);
  view.innerHTML = `<div class="c-toolbar"><nav class="crumbs" aria-label="Breadcrumb"><a href="#/home">Home</a><span class="sep">›</span><span>${sec.name}</span></nav><div class="c-tb-r">${paletteBtn()}</div></div>
    <header class="c-head"><span class="glyph sec-glyph">${ICON[sec.id]}</span><div><h1>${sec.name}</h1><p class="page-sub">${sec.desc}</p></div><span class="sample">Sample data</span></header>
    ${sec.id === 'finance' ? `<section class="c-grid">${financeBig(sec)}</section>` : watchlist([sec])}`;
  hydrateWatch(view);
}

/* ---------- boot ---------- */
render(currentId());

</script>
</body>
</html>
