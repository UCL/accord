---
layout: page
title: Roadmap
permalink: /roadmap/
---

<link rel="stylesheet" href="{{ '/assets/css/roadmap.css' | relative_url }}">

<div id="accord-roadmap">
  <h2 class="roadmap-heading">ACCoRD Workstreams</h2>
  <p class="roadmap-subheading">Click any workstream to explore its scope, recommendations, and evidence.</p>
  <div class="roadmap-grid" id="roadmap-grid" role="list"></div>
</div>

<style>
  .rec-list { list-style:none; margin:0; padding:0; display:flex; flex-direction:column; gap:6px; }
  .rec-item { border:1px solid rgba(0,0,0,0.08); border-radius:8px; overflow:hidden; background:#fff; }

  .rec-header { display:flex; align-items:center; gap:10px; padding:10px 12px; cursor:default; user-select:none; }
  .rec-header.expandable { cursor:pointer; }
  .rec-header.expandable:hover { background:rgba(0,0,0,0.03); }
  .rec-dot { width:10px; height:10px; border-radius:50%; flex-shrink:0; border:2px solid #ccc; background:transparent; }
  .rec-dot.done { border-color:var(--tile-color,#888); background:var(--tile-color,#888); }
  .rec-label { flex:1; font-size:0.88rem; color:#333; font-weight:500; }
  .rec-item.done .rec-label { color:#555; }
  .rec-chevron { width:14px; height:14px; color:#888; flex-shrink:0; transition:transform 0.2s ease; }
  .rec-chevron svg { width:100%; height:100%; stroke:currentColor; fill:none; stroke-width:2.5; stroke-linecap:round; stroke-linejoin:round; }
  .rec-header[aria-expanded="true"] .rec-chevron { transform:rotate(90deg); }

  .rec-body { display:none; border-top:1px solid rgba(0,0,0,0.06); }
  .rec-body.open { display:block; }

  .summary-section { padding:10px 12px 10px 32px; }
  .summary-label { font-size:0.72rem; font-weight:600; text-transform:uppercase; letter-spacing:0.06em; color:#999; margin-bottom:6px; }
  .summary-list { list-style:none; display:flex; flex-direction:column; gap:5px; }
  .summary-item { background:#f7f7f7; border-radius:5px; padding:6px 10px; font-size:0.82rem; color:#444; line-height:1.5; }

  .export-bar { display:flex; align-items:center; justify-content:space-between; padding:8px 12px 10px 32px; border-top:1px solid rgba(0,0,0,0.05); gap:8px; }
  .raw-count { font-size:0.78rem; color:#888; }
  .raw-count strong { color:#555; }
  .export-btn { display:inline-flex; align-items:center; gap:5px; font-size:0.78rem; font-weight:600; color:var(--tile-color,#555); background:none; border:1px solid var(--tile-color,#ccc); border-radius:5px; padding:4px 10px; cursor:pointer; transition:background 0.15s,color 0.15s; white-space:nowrap; }
  .export-btn:hover { background:var(--tile-color,#555); color:#fff; }
  .export-btn svg { width:12px; height:12px; stroke:currentColor; fill:none; stroke-width:2.5; stroke-linecap:round; stroke-linejoin:round; }
</style>

<script>
(function () {

  const ICONS = {
    "shield-alert": `<svg viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>`,
    "message-square": `<svg viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>`,
    "graduation-cap": `<svg viewBox="0 0 24 24"><path d="M22 10v6M2 10l10-5 10 5-10 5-10-5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>`,
    "clipboard-list": `<svg viewBox="0 0 24 24"><rect x="8" y="2" width="8" height="4" rx="1" ry="1"/><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"/><line x1="12" y1="11" x2="16" y2="11"/><line x1="12" y1="16" x2="16" y2="16"/><line x1="8" y1="11" x2="8.01" y2="11"/><line x1="8" y1="16" x2="8.01" y2="16"/></svg>`,
    "settings": `<svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83-2.83l.06-.06A1.65 1.65 0 0 0 4.68 15a1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 2.83-2.83l.06.06A1.65 1.65 0 0 0 9 4.68a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 2.83l-.06.06A1.65 1.65 0 0 0 19.4 9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/></svg>`,
    "gavel": `<svg viewBox="0 0 24 24"><path d="m14 13-8.5 8.5a2.12 2.12 0 0 1-3-3L11 10"/><path d="m16 16 6-6"/><path d="m8 8 6-6"/><path d="m9 7 8 8"/><path d="m21 11-8-8"/></svg>`
  };

  const ARROW    = `<svg viewBox="0 0 24 24"><polyline points="9 18 15 12 9 6"/></svg>`;
  const CLOSE    = `<svg viewBox="0 0 24 24"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>`;
  const CHEVRON  = `<svg viewBox="0 0 24 24"><polyline points="9 18 15 12 9 6"/></svg>`;
  const DOWNLOAD = `<svg viewBox="0 0 24 24"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`;

  const DATA_URL = '{{ "/assets/data/roadmap-data.json" | relative_url }}';
  const grid = document.getElementById('roadmap-grid');

  let activeId = null;
  let activePanel = null;
  let data = [];

  function statusClass(s) {
    return s === 'In Progress' ? 'in-progress' : 'planning';
  }

  function exportRawData(streamTitle, recLabel, rawData) {
    if (!rawData || !rawData.length) return;
    const lines = rawData.map((d, i) => `[${i + 1}] ${d}`).join('\n\n');
    const content = `ACCoRD — Raw Evidence Export\nStream: ${streamTitle}\nRecommendation: ${recLabel}\nExported: ${new Date().toLocaleString()}\n${'─'.repeat(60)}\n\n${lines}`;
    const blob = new Blob([content], { type: 'text/plain' });
    const url  = URL.createObjectURL(blob);
    const a    = document.createElement('a');
    a.href     = url;
    a.download = `ACCoRD_${streamTitle.replace(/\W+/g, '_')}_${recLabel.slice(0, 30).replace(/\W+/g, '_')}.txt`;
    a.click();
    URL.revokeObjectURL(url);
  }

  function buildRecommendations(item) {
    const ul = document.createElement('ul');
    ul.className = 'rec-list';

    item.recommendations.forEach((rec, ri) => {
      const li = document.createElement('li');
      li.className = `rec-item${rec.done ? ' done' : ''}`;

      const hasSummary = rec.summaryPoints && rec.summaryPoints.length > 0;
      const hasRaw     = rec.rawData && rec.rawData.length > 0;
      const expandable = hasSummary || hasRaw;
      const bodyId     = `rec-body-${item.id}-${ri}`;

      const header = document.createElement('div');
      header.className = `rec-header${expandable ? ' expandable' : ''}`;
      if (expandable) {
        header.setAttribute('role', 'button');
        header.setAttribute('tabindex', '0');
        header.setAttribute('aria-expanded', 'false');
        header.setAttribute('aria-controls', bodyId);
      }
      header.innerHTML = `
        <span class="rec-dot${rec.done ? ' done' : ''}" style="${rec.done ? `--tile-color:${item.color}` : ''}"></span>
        <span class="rec-label">${rec.label}</span>
        ${expandable ? `<span class="rec-chevron">${CHEVRON}</span>` : ''}
      `;
      li.appendChild(header);

      if (expandable) {
        const body = document.createElement('div');
        body.className = 'rec-body';
        body.id = bodyId;

        if (hasSummary) {
          const sec = document.createElement('div');
          sec.className = 'summary-section';
          sec.innerHTML = `<div class="summary-label">Key findings</div>`;
          const sumUl = document.createElement('ul');
          sumUl.className = 'summary-list';
          rec.summaryPoints.forEach(pt => {
            const pli = document.createElement('li');
            pli.className = 'summary-item';
            pli.textContent = pt;
            sumUl.appendChild(pli);
          });
          sec.appendChild(sumUl);
          body.appendChild(sec);
        }

        const bar = document.createElement('div');
        bar.className = 'export-bar';
        bar.style.setProperty('--tile-color', item.color);
        const rawCount = rec.rawData ? rec.rawData.length : 0;
        bar.innerHTML = `
          <span class="raw-count">${rawCount > 0 ? `<strong>${rawCount}</strong> raw evidence item${rawCount !== 1 ? 's' : ''}` : 'No raw data attached yet'}</span>
          ${rawCount > 0 ? `<button class="export-btn" style="--tile-color:${item.color}">${DOWNLOAD} Export all raw data</button>` : ''}
        `;
        if (rawCount > 0) {
          bar.querySelector('.export-btn').addEventListener('click', e => {
            e.stopPropagation();
            exportRawData(item.title, rec.label, rec.rawData);
          });
        }
        body.appendChild(bar);
        li.appendChild(body);

        const toggle = () => {
          const open = body.classList.contains('open');
          body.classList.toggle('open', !open);
          header.setAttribute('aria-expanded', String(!open));
        };
        header.addEventListener('click', toggle);
        header.addEventListener('keydown', e => {
          if (e.key === 'Enter' || e.key === ' ') { e.preventDefault(); toggle(); }
        });
      }

      ul.appendChild(li);
    });
    return ul;
  }

  function buildPanel(item) {
    const wrapper = document.createElement('div');
    wrapper.className = 'panel-wrapper roadmap-panel';
    wrapper.id = `panel-${item.id}`;
    wrapper.setAttribute('role', 'region');
    wrapper.setAttribute('aria-label', item.title);
    const sc = statusClass(item.status);
    wrapper.innerHTML = `
      <button class="panel-close" aria-label="Close panel">${CLOSE}</button>
      <div class="panel-inner">
        <div>
          <div class="panel-header">
            <div class="panel-color-bar" style="background:${item.color}"></div>
            <div class="panel-title-block">
              <h3 class="panel-title">${item.title}</h3>
              <div class="panel-meta">
                <span class="panel-status ${sc}">${item.status}</span>
                <span class="panel-lead">Lead: ${item.lead}</span>
              </div>
            </div>
          </div>
          <p class="panel-summary">${item.summary}</p>
          <p class="panel-details">${item.details}</p>
        </div>
        <div>
          <p class="panel-milestones-title">Recommendations</p>
          <div class="rec-list-wrapper"></div>
        </div>
      </div>
    `;
    wrapper.querySelector('.rec-list-wrapper').appendChild(buildRecommendations(item));
    wrapper.querySelector('.panel-close').addEventListener('click', () => closePanel());
    return wrapper;
  }

  function closePanel() {
    if (activePanel) activePanel.remove();
    if (activeId) {
      const btn = grid.querySelector(`[data-id="${activeId}"]`);
      if (btn) { btn.classList.remove('active'); btn.setAttribute('aria-expanded', 'false'); }
    }
    activeId = null;
    activePanel = null;
  }

  function getComputedColumns() {
    const w = grid.offsetWidth;
    if (w < 400) return 1;
    if (w < 640) return 2;
    return 3;
  }

  function togglePanel(item, btn) {
    if (activeId === item.id) { closePanel(); return; }
    if (activePanel) {
      const oldBtn = grid.querySelector(`[data-id="${activeId}"]`);
      if (oldBtn) { oldBtn.classList.remove('active'); oldBtn.setAttribute('aria-expanded', 'false'); }
      activePanel.remove();
    }
    const tiles  = Array.from(grid.querySelectorAll('.roadmap-tile'));
    const idx    = tiles.indexOf(btn);
    const cols   = getComputedColumns();
    const rowEnd = Math.min(Math.ceil((idx + 1) / cols) * cols, tiles.length);
    const lastInRow = tiles[rowEnd - 1];
    const panel = buildPanel(item);
    lastInRow.after(panel);
    requestAnimationFrame(() => requestAnimationFrame(() => panel.classList.add('open')));
    btn.classList.add('active');
    btn.setAttribute('aria-expanded', 'true');
    activeId = item.id;
    activePanel = panel;
    setTimeout(() => panel.scrollIntoView({ behavior: 'smooth', block: 'nearest' }), 100);
  }

  let resizeTimer;
  window.addEventListener('resize', () => {
    clearTimeout(resizeTimer);
    resizeTimer = setTimeout(() => {
      if (activeId && activePanel) {
        const item = data.find(d => d.id === activeId);
        const btn  = grid.querySelector(`[data-id="${activeId}"]`);
        if (item && btn) {
          activePanel.remove(); activePanel = null; activeId = null;
          btn.classList.remove('active'); btn.setAttribute('aria-expanded', 'false');
          togglePanel(item, btn);
        }
      }
    }, 200);
  });

  function buildTile(item) {
    const btn = document.createElement('button');
    btn.className = 'roadmap-tile';
    btn.setAttribute('role', 'listitem');
    btn.setAttribute('aria-expanded', 'false');
    btn.setAttribute('aria-controls', `panel-${item.id}`);
    btn.dataset.id = item.id;
    btn.style.background = item.gradient;
    btn.innerHTML = `
      <div class="tile-status-dot ${statusClass(item.status)}" title="${item.status}"></div>
      <div class="tile-title">${item.title}</div>
      <div class="tile-icon">${ICONS[item.icon] || ''}</div>
      <div class="tile-arrow">${ARROW}</div>
    `;
    btn.addEventListener('click', () => togglePanel(item, btn));
    return btn;
  }

  fetch(DATA_URL)
    .then(r => { if (!r.ok) throw new Error('Failed to load roadmap data'); return r.json(); })
    .then(json => {
      data = json;
      json.forEach(item => grid.appendChild(buildTile(item)));
    })
    .catch(err => {
      grid.innerHTML = `<p style="color:#c00;grid-column:1/-1">Could not load roadmap data. (${err.message})</p>`;
    });

})();
</script>
