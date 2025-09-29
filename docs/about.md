---
layout: page
title: About
permalink: /about/
---

<section class="events-hero flow">
  <p class="eyebrow">Partnership • Interoperability • Trust</p>
  <h2 class="page-title">About ACCoRD</h2>
    <p class="lead">
      ACCoRD addresses the contracting challenges that currently hinder
      data from being accessed, moved and processed efficiently for ground-breaking research.
    </p>

    <p>
      A research data contract stipulates the terms under which data is shared for research purposes. It forms the foundation for
      the storage, management, transfer and use of data. However, the data contracting process is fraught with challenges, inefficiencies
      and uncertainty, which significantly delay or block innovative research.
    </p>

    <p>ACCoRD brings together experts in community engagement and data governance to deliver:</p>

    <ul class="deliverables-list">
      <li>the evidence, components and roadmap for a governance framework for data contracts in research, and</li>
      <li>a community to take that evidence forward</li>
    </ul>

    <p>
      Through stakeholder engagement and community development, we will understand the challenges and opportunities for
      data contracting, identify best practice models and produce solutions to unblock data for the UK’s Digital Research Infrastructure.
    </p>

  <p class="cta-row">
     <a class="btn btn-primary" href="https://forms.office.com/pages/responsepage.aspx?id=_oivH5ipW0yTySEKEdmlwvNrS4lV5ilIsuG4plfelThUNVkxRlZZTlhPOTU0NkZUQkVWNTBZUjUwVS4u&route=shorturl" target="_blank" rel="noopener">
    Join the community →
    </a>
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

<section class="funding-section flow">
  <h3>Funding & national impact</h3>
  <p>
    ACCoRD is funded through the 
    <a href="https://nfcs-networkplus.ac.uk/" target="_blank" rel="noopener">National Research Foundation for Collaborative Science (NFCS)</a>.
    What we develop will directly inform and contribute to the NFCS, ensuring that our work is not created in a vacuum but 
    instead delivers lasting value at a national scale. Our community’s insights and solutions will shape how data contracts 
    support research across the UK.
  </p>
</section>
