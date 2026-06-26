---
layout: page
title: Roadmap
permalink: /roadmap/
---

<link rel="stylesheet" href="{{ '/assets/css/roadmap.css' | relative_url }}">

<div id="accord-roadmap">
  <h2 class="roadmap-heading">ACCoRD Recommendation Pillars</h2>
  <p class="roadmap-subheading">Nine recommendation pillars form the ACCoRD roadmap, divided into three sub groupings.

    <ul>
    <li><b>ACCoRD-R1: </b>Firstly <b>national strategy and governance</b> recommendations focus on enabling research data contracting in the long term, addressing the high level systemic approach that will ensure that improvements to data contracting are sustained in the long term.  These include establishing a national advisory service and a new research technical professional, as well as ensuring that ACCoRD takes account of the fact that Digital Research Infrastructure is evolving and will continue to do so.  Automation forms the fourth element of this group – while our work shows that research data contracting will never be fully automatable, use of Large Language Models in contracting can provide benefits, leaving the experts to focus on those elements of a contract that cannot be automated.</li>
    <li><b>ACCoRD-R2:</b> Our second group of recommendations delivers the </b>national and institutional enablers</b> underpinning ACCoRD – i.e. these are the catalysts without which the more practical recommendations arising from the project cannot be delivered.   The four interlinked recommendations within this group cover policy, such as the use of templates and developing better understanding of institutional risk and liabilities, people – both in terms of the resources required to remove contracting bottlenecks and those required to continue the ACCoRD community work and deliver on the roadmap, professional development (training and guidance) to ensure that all stakeholders are appropriately skilled and have access to relevant information in a timely manner, and provisioning – providing the funding required to deliver on the roadmap, to develop templates, training and much more. </li>
    <li><b>ACCoRD-R3:</b> The final group of recommendations relate to <b>standardisation and institutional processes and governance</b> and cover the delivery of key approaches to facilitate contracting on a day-to-day basis, within institutions; these include a robust triage process, the use of templates for contracting terms and a clearly defined technical audit and compliance process post-contract signature.</li>
    </ul>

<br>  The diagram shows how they connect: a triage and information-gathering process feeds into modular contract templates, which in turn inform technical audits and compliance - all supported by an advisory service and automation capabilities, enabling policy, professional development, provisioning and a growing community. Click any segment or card to explore the recommendations and evidence behind each pillar.</p>

  <!-- ── Interactive pillar diagram ── -->
  <div class="diagram-wrapper">
    <p class="diagram-caption">How the pillars interrelate - click a segment to jump to that pillar</p>
    <div class="diagram-scroll">
      <svg class="accord-diagram" viewBox="0 0 820 470" xmlns="http://www.w3.org/2000/svg"
           role="img" aria-label="ACCoRD recommendation pillars diagram">
        <defs>
          <marker id="arr" markerWidth="7" markerHeight="7" refX="5" refY="3.5" orient="auto">
            <polygon points="0 0, 7 3.5, 0 7" fill="rgba(255,255,255,0.55)"/>
          </marker>
          <marker id="arr-soft" markerWidth="7" markerHeight="7" refX="5" refY="3.5" orient="auto">
            <polygon points="0 0, 7 3.5, 0 7" fill="rgba(255,255,255,0.3)"/>
          </marker>
          <filter id="glow" x="-20%" y="-20%" width="140%" height="140%">
            <feGaussianBlur stdDeviation="4" result="blur"/>
            <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
          </filter>
        </defs>

        <!-- ── Outer donut segments ── -->

        <!-- NW: Policy #6B38C8 -->
        <path class="diag-seg" data-pillar="policy" tabindex="0" role="button" aria-label="Policy pillar"
          d="M 245 235 A 165 165 0 0 1 410 70 L 410 145 A 90 90 0 0 0 320 235 Z"
          fill="#6B38C8"/>

        <!-- NE: Professional Development #228A50 -->
        <path class="diag-seg" data-pillar="professional-development" tabindex="0" role="button" aria-label="Professional Development and Guidance pillar"
          d="M 410 70 A 165 165 0 0 1 575 235 L 500 235 A 90 90 0 0 0 410 145 Z"
          fill="#228A50"/>

        <!-- SE: People #1E68CC -->
        <path class="diag-seg" data-pillar="people-community" tabindex="0" role="button" aria-label="People – Community and Resourcing pillar"
          d="M 575 235 A 165 165 0 0 1 410 400 L 410 325 A 90 90 0 0 0 500 235 Z"
          fill="#1E68CC"/>

        <!-- SW: Provisioning #C02898 -->
        <path class="diag-seg" data-pillar="provisioning" tabindex="0" role="button" aria-label="Provisioning and Funding pillar"
          d="M 410 400 A 165 165 0 0 1 245 235 L 320 235 A 90 90 0 0 0 410 325 Z"
          fill="#C02898"/>

        <!-- ── Inner circle: top semi-circle Advisory Service ── -->
        <path class="diag-seg" data-pillar="advisory-service" tabindex="0" role="button" aria-label="Advisory Service pillar"
          d="M 321 235 A 89 89 0 0 1 499 235 Z"
          fill="#a8b4c8" fill-opacity="0.2"/>
        <path d="M 321 235 A 89 89 0 0 1 499 235 Z"
          fill="none" stroke="#8899bb" stroke-width="2" stroke-dasharray="5 4" stroke-opacity="0.55"/>

        <!-- ── Inner circle: bottom semi-circle Automation ── -->
        <path class="diag-seg" data-pillar="automation" tabindex="0" role="button" aria-label="Automation pillar"
          d="M 321 235 A 89 89 0 0 0 499 235 Z"
          fill="#a8b4c8" fill-opacity="0.2"/>
        <path d="M 321 235 A 89 89 0 0 0 499 235 Z"
          fill="none" stroke="#8899bb" stroke-width="2" stroke-dasharray="5 4" stroke-opacity="0.55"/>

        <!-- Semi-circle dividing line -->
        <line x1="321" y1="235" x2="499" y2="235"
          stroke="rgba(255,255,255,0.35)" stroke-width="1.5" stroke-dasharray="4 3"/>

        <!-- ── Templates centre box ── -->
        <rect class="diag-seg" data-pillar="templates" tabindex="0" role="button" aria-label="Templates pillar"
          x="341" y="203" width="138" height="64" rx="9"
          fill="#1BAAA0"/>

        

        <!-- ── External boxes ── -->

        <!-- Triage (left) -->
        <rect class="diag-seg" data-pillar="triage" tabindex="0" role="button" aria-label="Triage pillar"
          x="165" y="203" width="138" height="64" rx="11"
          fill="#E8522A"/>

        <!-- Technical Audits (right) -->
        <rect class="diag-seg" data-pillar="technical-audits" tabindex="0" role="button" aria-label="Technical Audits and Compliance pillar"
          x="540" y="203" width="138" height="64" rx="11"
          fill="#C8387A"/>

        <!-- ── Arrows drawn last so they sit in front of everything ── -->
        <!-- Triage → Templates -->
        <line x1="304" y1="235" x2="338" y2="235"
              stroke="white" stroke-width="2.5" stroke-opacity="0.75" marker-end="url(#arr)"/>
        <!-- Templates → Technical Audits -->
        <line x1="480" y1="235" x2="537" y2="235"
              stroke="white" stroke-width="2.5" stroke-opacity="0.75" marker-end="url(#arr)"/>

        <!-- ── Segment text labels ── -->

        <!-- Policy (NW) — midpoint (320, 145) -->
        <text x="320" y="149" text-anchor="middle" class="seg-label" font-size="13" fill="white" pointer-events="none">Policy</text>

        <!-- Professional Dev (NE) — midpoint (500, 145) -->
        <text x="500" y="139" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">Professional</text>
        <text x="500" y="155" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">Dev. &amp; Guidance</text>

        <!-- People (SE) — midpoint (500, 325) -->
        <text x="500" y="315" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">People –</text>
        <text x="500" y="331" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">Community &amp;</text>
        <text x="500" y="347" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">Resourcing</text>

        <!-- Provisioning (SW) — midpoint (320, 325) -->
        <text x="320" y="319" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">Provisioning</text>
        <text x="320" y="335" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">&amp; Funding</text>

        <!-- Advisory Service (top semi-circle) — above Templates box -->
        <text x="410" y="177" text-anchor="middle" class="seg-label advisory-label" font-size="12" fill="#2AB8E0" pointer-events="none">Advisory</text>
        <text x="410" y="191" text-anchor="middle" class="seg-label advisory-label" font-size="12" fill="#2AB8E0" pointer-events="none">Service</text>

        <!-- Automation (bottom semi-circle) — below Templates box -->
        <text x="410" y="285" text-anchor="middle" class="seg-label automation-label" font-size="13" fill="#E08030" pointer-events="none">Automation</text>

        <!-- Templates (centre box) — box centre y=235 -->
        <text x="410" y="229" text-anchor="middle" class="seg-label" font-size="13" fill="white" font-weight="700" pointer-events="none">Template</text>
        <text x="410" y="246" text-anchor="middle" class="seg-label" font-size="13" fill="white" font-weight="700" pointer-events="none">"Modules"</text>

        <!-- Triage (left box) — box centre y=235 -->
        <text x="234" y="229" text-anchor="middle" class="seg-label" font-size="13" fill="white" pointer-events="none">Triage /</text>
        <text x="234" y="246" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">Info Gathering</text>

        <!-- Technical Audits (right box) — box centre y=235 -->
        <text x="609" y="221" text-anchor="middle" class="seg-label" font-size="13" fill="white" pointer-events="none">Technical</text>
        <text x="609" y="237" text-anchor="middle" class="seg-label" font-size="13" fill="white" pointer-events="none">Audits &amp;</text>
        <text x="609" y="253" text-anchor="middle" class="seg-label" font-size="12" fill="white" pointer-events="none">Compliance</text>

        <!-- ── Hover pulse ring (hidden by default, shown via JS) ── -->
        <circle id="diag-pulse" cx="410" cy="235" r="170"
          fill="none" stroke="white" stroke-width="0" stroke-opacity="0" pointer-events="none"/>
      </svg>
    </div>
  </div>

  <!-- ── Pillar tiles grid ── -->
  <div class="roadmap-grid" id="roadmap-grid" role="list"></div>

  <div class="export-all-bar">
    <button id="export-all-btn" class="export-all-btn" disabled>
      <svg viewBox="0 0 24 24"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>
      Export All Data
    </button>
  </div>
</div>

<script>
(function () {

  const ICONS = {
    "filter": `<svg viewBox="0 0 24 24"><polygon points="22 3 2 3 10 12.46 10 19 14 21 14 12.46 22 3"/></svg>`,
    "layout": `<svg viewBox="0 0 24 24"><rect x="3" y="3" width="18" height="18" rx="2"/><line x1="3" y1="9" x2="21" y2="9"/><line x1="9" y1="21" x2="9" y2="9"/></svg>`,
    "check-square": `<svg viewBox="0 0 24 24"><polyline points="9 11 12 14 22 4"/><path d="M21 12v7a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V5a2 2 0 0 1 2-2h11"/></svg>`,
    "life-buoy": `<svg viewBox="0 0 24 24"><circle cx="12" cy="12" r="10"/><circle cx="12" cy="12" r="4"/><line x1="4.93" y1="4.93" x2="9.17" y2="9.17"/><line x1="14.83" y1="14.83" x2="19.07" y2="19.07"/><line x1="14.83" y1="9.17" x2="19.07" y2="4.93"/><line x1="4.93" y1="19.07" x2="9.17" y2="14.83"/></svg>`,
    "book-open": `<svg viewBox="0 0 24 24"><path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z"/><path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z"/></svg>`,
    "graduation-cap": `<svg viewBox="0 0 24 24"><path d="M22 10v6M2 10l10-5 10 5-10 5-10-5z"/><path d="M6 12v5c3 3 9 3 12 0v-5"/></svg>`,
    "package": `<svg viewBox="0 0 24 24"><path d="M16.5 9.4l-9-5.19M21 16V8a2 2 0 0 0-1-1.73l-7-4a2 2 0 0 0-2 0l-7 4A2 2 0 0 0 3 8v8a2 2 0 0 0 1 1.73l7 4a2 2 0 0 0 2 0l7-4A2 2 0 0 0 21 16z"/><polyline points="3.27 6.96 12 12.01 20.73 6.96"/><line x1="12" y1="22.08" x2="12" y2="12"/></svg>`,
    "users": `<svg viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>`,
    "zap": `<svg viewBox="0 0 24 24"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"/></svg>`
  };

  const ARROW    = `<svg viewBox="0 0 24 24"><polyline points="9 18 15 12 9 6"/></svg>`;
  const CLOSE    = `<svg viewBox="0 0 24 24"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>`;
  const CHEVRON  = `<svg viewBox="0 0 24 24"><polyline points="9 18 15 12 9 6"/></svg>`;
  const DOWNLOAD = `<svg viewBox="0 0 24 24"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="7 10 12 15 17 10"/><line x1="12" y1="15" x2="12" y2="3"/></svg>`;

  const DATA_URL = '{{ "/assets/data/roadmap-data.json" | relative_url }}';
  const grid = document.getElementById('roadmap-grid');
  const exportAllBtn = document.getElementById('export-all-btn');

  let activeId = null;
  let activePanel = null;
  let data = [];

  // ── Diagram click → scroll to tile ──
  document.querySelectorAll('.diag-seg').forEach(seg => {
    const activate = () => {
      const pillarId = seg.dataset.pillar;
      const tile = grid.querySelector(`[data-id="${pillarId}"]`);
      if (!tile) return;
      // Flash the segment
      seg.classList.add('diag-active');
      setTimeout(() => seg.classList.remove('diag-active'), 600);
      // Scroll tile into view then open its panel
      tile.scrollIntoView({ behavior: 'smooth', block: 'center' });
      setTimeout(() => {
        if (activeId !== pillarId) tile.click();
      }, 350);
    };
    seg.addEventListener('click', activate);
    seg.addEventListener('keydown', e => { if (e.key === 'Enter' || e.key === ' ') { e.preventDefault(); activate(); } });
  });

  function statusClass(s) {
    return s === 'In Progress' ? 'in-progress' : 'planning';
  }

  function exportRawData(streamTitle, recLabel, rawData) {
    if (!rawData || !rawData.length) return;
    const lines = rawData.map((d, i) => `[${i + 1}] ${d}`).join('\n\n');
    const content = `ACCoRD — Raw Evidence Export\nPillar: ${streamTitle}\nRecommendation: ${recLabel}\nExported: ${new Date().toLocaleString()}\n${'─'.repeat(60)}\n\n${lines}`;
    const blob = new Blob([content], { type: 'text/plain' });
    const url  = URL.createObjectURL(blob);
    const a    = document.createElement('a');
    a.href     = url;
    a.download = `ACCoRD_${streamTitle.replace(/\W+/g, '_')}_${recLabel.slice(0, 30).replace(/\W+/g, '_')}.txt`;
    a.click();
    URL.revokeObjectURL(url);
  }

  function exportAllData() {
    const sections = [];
    let totalItems = 0;
    data.forEach(stream => {
      const streamSections = [];
      stream.recommendations.forEach(rec => {
        if (rec.rawData && rec.rawData.length > 0) {
          const lines = rec.rawData.map((d, i) => `  [${i + 1}] ${d}`).join('\n');
          streamSections.push(`  Recommendation: ${rec.label}\n${lines}`);
          totalItems += rec.rawData.length;
        }
      });
      if (streamSections.length > 0) {
        sections.push(`${'═'.repeat(60)}\nPILLAR: ${stream.title}\n${'═'.repeat(60)}\n\n${streamSections.join('\n\n')}`);
      }
    });
    if (totalItems === 0) { alert('No raw data attached to any pillar yet.'); return; }
    const header = [`ACCoRD — Full Raw Evidence Export`, `Exported: ${new Date().toLocaleString()}`, `Total items: ${totalItems} across ${sections.length} pillar${sections.length !== 1 ? 's' : ''}`, '─'.repeat(60), ''].join('\n');
    const blob = new Blob([header + '\n' + sections.join('\n\n')], { type: 'text/plain' });
    const url  = URL.createObjectURL(blob);
    const a    = document.createElement('a');
    a.href     = url;
    a.download = `ACCoRD_All_Raw_Evidence_${new Date().toISOString().slice(0,10)}.txt`;
    a.click();
    URL.revokeObjectURL(url);
  }

  exportAllBtn.addEventListener('click', exportAllData);

  function buildRecommendations(item) {
    const ul = document.createElement('ul');
    ul.className = 'rec-list';
    item.recommendations.forEach((rec, ri) => {
      const li = document.createElement('li');
      li.className = `rec-item${rec.done ? ' done' : ''}`;
      const hasSummary = rec.subRecommendations && rec.subRecommendations.length > 0;
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
        <span class="rec-num${rec.done ? ' done' : ''}" style="${rec.done ? `--tile-color:${item.color}` : ''}">${ri + 1}.</span>
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
          sec.innerHTML = `<div class="summary-label">Sub-recommendations</div>`;
          const sumUl = document.createElement('ul');
          sumUl.className = 'summary-list';
          rec.subRecommendations.forEach(pt => {
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
          ${rawCount > 0 ? `<button class="export-btn" style="--tile-color:${item.color}">${DOWNLOAD} Export raw data</button>` : ''}
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
        header.addEventListener('keydown', e => { if (e.key === 'Enter' || e.key === ' ') { e.preventDefault(); toggle(); } });
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
                <!--<span class="panel-status ${sc}">${item.status}</span> -->
                <!--<span class="panel-lead">Lead: ${item.lead}</span> -->
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
    if (w < 780) return 2;
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
      const hasAnyRaw = json.some(s => s.recommendations.some(r => r.rawData && r.rawData.length > 0));
      exportAllBtn.disabled = !hasAnyRaw;
    })
    .catch(err => {
      grid.innerHTML = `<p style="color:#c00;grid-column:1/-1">Could not load roadmap data. (${err.message})</p>`;
    });

})();
</script>
