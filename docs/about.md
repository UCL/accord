---
layout: page
title: About
permalink: /about/
---

## About ACCoRD

ACCoRD is building a community and a Governance Framework for Data Contracts to unlock safe, efficient research with external and sensitive data.

### What we do

- **Engage**: surveys, workshops, and interviews across stakeholders
- **Synthesise**: turn insights into practical components for a framework
- **Sustain**: hand over a living community and roadmap to long‑term hosts

<div class="spacer-sm"></div>
---
<div class="spacer-sm"></div>

## ACCoRD members

<div class="people-grid">
  {% for p in site.data.members %}
  <div class="person">
    <h3>{{ p.name }}</h3>
    <p><em>{{ p.role }}</em></p>
    {% if p.affiliation %}<p>{{ p.affiliation }}</p>{% endif %}
    {% if p.email %}<p><a href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
  </div>
  {% endfor %}
</div>
