---
layout: page
title: About
permalink: /about/
---

<section class="events-hero flow">
  <p class="eyebrow">Community • Contracts • Clarity</p>
  <h2 class="page-title">About ACCoRD</h2>
  <p class="lead"> ACCoRD is building a community and a Governance Framework for Data Contracts to unlock safe, efficient research with external and sensitive data.
  </p>
  <p class="cta-row">
    <a class="btn btn-primary" href="{{ '/join/' | relative_url }}">Join the community →</a>
    <a class="btn btn-primary" href="{{ '/events/' | relative_url }}">View upcoming events →</a>
  </p>
</section>

<hr class="section-divider" />

<section class="flow what-we-do">
  <h3>What we do</h3>
  <ul class="feature-list">
    <li><strong>Engage</strong>: surveys, workshops, and interviews across stakeholders</li>
    <li><strong>Synthesise</strong>: turn insights into practical components for a framework</li>
    <li><strong>Sustain</strong>: hand over a living community and roadmap to long-term hosts</li>
  </ul>
</section>

<section class="members-section">
  <div class="members-intro">
    <h2>Our team</h2>
    <p>Researchers, stewards, and partners building fair, fast data contracts together.</p>
  </div>

  <div class="people-grid">
    {% for p in site.data.members %}
    <div class="person">
      <div class="person-media">
        {% if p.photo %}
          <img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">
        {% else %}
          <div class="avatar-placeholder" aria-hidden="true"></div>
        {% endif %}
      </div>

      <div class="person-content">
        <h3><strong>{{ p.name }}</strong></h3>
        <p><em>{{ p.role }}</em></p>
        {% if p.affiliation %}<p>{{ p.affiliation }}</p>{% endif %}
        {% if p.email %}<p><a href="mailto:{{ p.email }}">{{ p.email }}</a></p>{% endif %}
      </div>
    </div>
    {% endfor %}

  </div>
</section>
