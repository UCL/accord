---
layout: page
title: Roadmap
permalink: /roadmap/
---

<link rel="stylesheet" href="{{ '/assets/css/roadmap.css' | relative_url }}">

<div id="accord-roadmap">
  <h2 class="roadmap-heading">ACCoRD Workstreams</h2>
  <p class="roadmap-subheading">Click any workstream to explore its scope, recommendations, and status.</p>
  <div class="roadmap-grid" id="roadmap-grid" role="list">
    <!-- Tiles injected by JS -->
  </div>
</div>

<style>
  .rec-list { list-style:none; margin:0; padding:0; display:flex; flex-direction:column; gap:6px; }
  .rec-item { border:1px solid rgba(0,0,0,0.08); border-radius:8px; overflow:hidden; background:#fff; }
  .rec-header { display:flex; align-items:center; gap:10px; padding:10px 12px; cursor:default; user-select:none; }
  .rec-header.has-data { cursor:pointer; }
  .rec-header.has-data:hover { background:rgba(0,0,0,0.03); }
  .rec-dot { width:10px; height:10px; border-radius:50%; flex-shrink:0; border:2px solid #ccc; background:transparent; }
  .rec-dot.done { border-color:var(--tile-color,#888); background:var(--tile-color,#888); }
  .rec-label { flex:1; font-size:0.88rem; color:#333; font-weight:500; }
  .rec-item.done .rec-label { color:#555; }
  .rec-data-badge { font-size:0.72rem; font-weight:600; color:#666; background:#f0f0f0; border-radius:20px; padding:2px 8px; white-space:nowrap; }
  .rec-download-all { display:inline-flex; align-items:center; gap:4px; font-size:0.75rem; font-weight:600; color:var(--tile-color,#555); background:none; border:1px solid var(--tile-color,#ccc); border-radius:4px; padding:2px 7px; cursor:pointer; flex-shrink:0; transition:background 0.15s,color 0.15s; }
  .rec-download-all:hover { background:var(--tile-color,#555); color:#fff; }
  .rec-download-all svg { width:11px; height:11px; stroke:currentColor; fill:none; stroke-width:2.5; stroke-linecap:round; stroke-linejoin:round; }
  .rec-chevron { width:14px; height:14px; color:#888; flex-shrink:0; transition:transform 0.2s ease; }
  .rec-chevron svg { width:100%; height:100%; stroke:currentColor; fill:none; stroke-width:2.5; stroke-linecap:round; stroke-linejoin:round; }
  .rec-header[aria-expanded="true"] .rec-chevron { transform:rotate(90deg); }
  .rec-datapoints { display:none; padding:0 12px 10px 32px; border-top:1px solid rgba(0,0,0,0.06); }
  .rec-datapoints.open { display:block; }
  .dp-list { list-style:none; margin:8px 0 0; padding:0; display:flex; flex-direction:column; gap:5px; }
  .dp-item { background:#f7f7f7; border-radius:5px; padding:6px 10px; font-size:0.82rem; color:#444; }
</style>

<script>
(function () {
  /* ── Icon paths (Lucide-style SVG) ── */
  const ICONS = {
    "shield-alert": `<svg viewBox="0 0 24 24"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/><line x1="12" y1="8" x2="12" y2="12"/><line x1="12" y1="16" x2="12.01" y2="16"/></svg>`,
    "message-square": `<svg viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg>`,
    "graduation-cap": `<svg viewBox="0 0 24 24"><path d="M22 10v6M2 10l10-5 10 5-10 5-10-5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>`,
    "gavel": `<svg viewBox="0 0 24 24"><path d="m14 13-8.5 8.5a2.12 2.12 0 0 1-3-3L11 10"/><path d="m16 16 6-6"/><path d="m8 8 6-6"/><path d="m9 7 8 8"/><path d="m21 11-8-8"/></svg>`,
    "clipboard-list": `<svg viewBox="0 0 24 24"><rect x="8" y="2" width="8" height="4" rx="1" ry="1"/><path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2"/><line x1="12" y1="11" x2="16" y2="11"/><line x1="12" y1="16" x2="16" y2="16"/><line x1="8" y1="11" x2="8.01" y2="11"/><line x1="8" y1="16" x2="8.01" y2="16"/></svg>`,
    "settings": `<svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 0 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 0 1-2.83-2.83l.06-.06A1.65 1.65 0 0 0 4.68 15a1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 0 1 2.83-2.83l.06.06A1.65 1.65 0 0 0 9 4.68a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 0 1 2.83 2.83l-.06.06A1.65 1.65 0 0 0 19.4 9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/></svg>`,
    "git-merge": `<svg viewBox="0 0 24 24"><circle cx="18" cy="18" r="3"/><circle cx="6" cy="6" r="3"/><path d="M6 21V9a9 9 0 0 0 9 9"/></svg>`,
    "lightbulb": `<svg viewBox="0 0 24 24"><line x1="9" y1="18" x2="15" y2="18"/><line x1="10" y1="22" x2="14" y2="22"/><path d="M15.09 14c.18-.98.65-1.74 1.41-2.5A4.65 4.65 0 0 0 18 8 6 6 0 0 0 6 8c0 1 .23 2.23 1.5 3.5A4.61 4.61 0 0 1 8.91 14"/></svg>`
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

  function buildTile(item) {
    const btn = document.createElement('button');
    btn.className = 'roadmap-tile';
    btn.setAttribute('role', 'listitem');
    btn.setAttribute('aria-expanded', 'false');
    btn.setAttribute('aria-controls', `panel-${item.id}`);
    btn.dataset.id = item.id;
    btn.style.background = item.gradient;

    const dotClass = statusClass(item.status);
    btn.innerHTML = `
      <div class="tile-status-dot ${dotClass}" title="${item.status}"></div>
      <div class="tile-title">${item.title}</div>
      <div class="tile-icon">${ICONS[item.icon] || ''}</div>
      <div class="tile-arrow">${ARROW}</div>
    `;
    btn.addEventListener('click', () => togglePanel(item, btn));
    return btn;
  }

  /* ── Download all data points for a recommendation ── */
  function downloadAllDataPoints(streamTitle, recLabel, dataPoints) {
    const lines = dataPoints.map((dp, i) => `Data Point ${i + 1}:\n${dp}`).join('\n\n');
    const content = `Stream: ${streamTitle}\nRecommendation: ${recLabel}\n\n${lines}`;
    const blob = new Blob([content], { type: 'text/plain' });
    const url  = URL.createObjectURL(blob);
    const a    = document.createElement('a');
    a.href     = url;
    a.download = `${streamTitle.replace(/\s+/g, '_')}_${recLabel.replace(/\s+/g, '_')}.txt`;
    a.click();
    URL.revokeObjectURL(url);
  }

  /* ── Build recommendation list ── */
  function buildRecommendations(item) {
    const ul = document.createElement('ul');
    ul.className = 'rec-list';

    item.recommendations.forEach((rec, ri) => {
      const li = document.createElement('li');
      li.className = `rec-item${rec.done ? ' done' : ''}`;

      const hasData = rec.dataPoints && rec.dataPoints.length > 0;
      const bodyId  = `rec-body-${item.id}-${ri}`;

      const header = document.createElement('div');
      header.className = `rec-header${hasData ? ' has-data' : ''}`;
      header.setAttribute('aria-expanded', 'false');
      if (hasData) {
        header.setAttribute('aria-controls', bodyId);
        header.setAttribute('role', 'button');
        header.setAttribute('tabindex', '0');
      }
      header.innerHTML = `
        <span class="rec-dot${rec.done ? ' done' : ''}" style="${rec.done ? `--tile-color:${item.color}` : ''}"></span>
        <span class="rec-label">${rec.label}</span>
        ${hasData ? `<span class="rec-data-badge">${rec.dataPoints.length} data point${rec.dataPoints.length !== 1 ? 's' : ''}</span>` : ''}
        ${hasData ? `<button class="rec-download-all" style="--tile-color:${item.color}" title="Export all data points">${DOWNLOAD} Export data</button>` : ''}
        ${hasData ? `<span class="rec-chevron">${CHEVRON}</span>` : ''}
      `;
      li.appendChild(header);

      if (hasData) {
        /* Download all button — stop propagation so it doesn't toggle the dropdown */
        header.querySelector('.rec-download-all').addEventListener('click', e => {
          e.stopPropagation();
          downloadAllDataPoints(item.title, rec.label, rec.dataPoints);
        });

        const body = document.createElement('div');
        body.className = 'rec-datapoints';
        body.id = bodyId;

        const dpUl = document.createElement('ul');
        dpUl.className = 'dp-list';
        const MAX_VISIBLE = 5;
        const visible = rec.dataPoints.slice(0, MAX_VISIBLE);
        visible.forEach(dp => {
          const dpLi = document.createElement('li');
          dpLi.className = 'dp-item';
          dpLi.textContent = dp;
          dpUl.appendChild(dpLi);
        });
        if (rec.dataPoints.length > MAX_VISIBLE) {
          const overflow = document.createElement('li');
          overflow.className = 'dp-item dp-overflow';
          overflow.textContent = `+ ${rec.dataPoints.length - MAX_VISIBLE} more - export to see all data points`;
          dpUl.appendChild(overflow);
        }
        body.appendChild(dpUl);
        li.appendChild(body);

        const toggle = () => {
          const isOpen = body.classList.contains('open');
          body.classList.toggle('open', !isOpen);
          header.setAttribute('aria-expanded', String(!isOpen));
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
    if (activePanel) {
      activePanel.remove();
    }
    if (activeId) {
      const btn = grid.querySelector(`[data-id="${activeId}"]`);
      if (btn) {
        btn.classList.remove('active');
        btn.setAttribute('aria-expanded', 'false');
      }
    }
    activeId = null;
    activePanel = null;
  }

  function togglePanel(item, btn) {
    if (activeId === item.id) {
      closePanel();
      return;
    }

    // Close existing
    if (activePanel) {
      const oldBtn = grid.querySelector(`[data-id="${activeId}"]`);
      if (oldBtn) { oldBtn.classList.remove('active'); oldBtn.setAttribute('aria-expanded', 'false'); }
      activePanel.classList.remove('open');
      activePanel.remove();
    }

    // Find which row this tile is on to insert panel after the row
    const tiles = Array.from(grid.querySelectorAll('.roadmap-tile'));
    const tileIndex = tiles.indexOf(btn);
    const cols = getComputedColumns();
    const rowEnd = Math.min(Math.ceil((tileIndex + 1) / cols) * cols, tiles.length);
    const lastInRow = tiles[rowEnd - 1];

    const panel = buildPanel(item);
    lastInRow.after(panel);

    // Force reflow then open
    requestAnimationFrame(() => {
      requestAnimationFrame(() => { panel.classList.add('open'); });
    });

    btn.classList.add('active');
    btn.setAttribute('aria-expanded', 'true');

    activeId = item.id;
    activePanel = panel;

    // Scroll into view
    setTimeout(() => {
      panel.scrollIntoView({ behavior: 'smooth', block: 'nearest' });
    }, 100);
  }

  function getComputedColumns() {
    const w = grid.offsetWidth;
    if (w < 480) return 1;
    if (w < 800) return 2;
    return 4;
  }

  // Re-insert panel on resize so it's always after the correct row
  let resizeTimer;
  window.addEventListener('resize', () => {
    clearTimeout(resizeTimer);
    resizeTimer = setTimeout(() => {
      if (activeId && activePanel) {
        const item = data.find(d => d.id === activeId);
        const btn = grid.querySelector(`[data-id="${activeId}"]`);
        if (item && btn) {
          activePanel.remove();
          activePanel = null;
          activeId = null;
          btn.classList.remove('active');
          btn.setAttribute('aria-expanded', 'false');
          togglePanel(item, btn);
        }
      }
    }, 200);
  });

  // Load data and render
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
