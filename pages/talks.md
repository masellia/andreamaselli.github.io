---
layout: section
title: Talks
permalink: /talks/
---

<div class="page-header">
  <div class="page-header-line"></div>
  <div class="page-header-title">TALKS</div>
</div>

<div class="talks-jump-links">
  <a href="#invited">Invited</a>
  <a href="#contributed">Contributed</a>
</div>

<section id="invited" class="talks-section">
  <header class="talks-section-header talks-section-header-right">
    <div class="talks-section-line"></div>
    <div class="talks-section-heading">
      <p>Seminars and talks</p>
      <h2>Invited</h2>
    </div>
  </header>

  <div class="talks-list">
    {% for talk in site.data.talks.invited %}
      <article class="talk-entry">
        <div class="talk-meta">
          <time>{{ talk.date }}</time>
          <span>[{{ talk.code | remove_first: 'I' }}]</span>
        </div>
        <div class="talk-content">
          <h3>{{ talk.title }}</h3>
          <p>{{ talk.details }}</p>
          {% if talk.note %}<span class="talk-note">{{ talk.note }}</span>{% endif %}
        </div>
      </article>
    {% endfor %}
  </div>
</section>

<section id="contributed" class="talks-section talks-section-dark">
  <header class="talks-section-header talks-section-header-left">
    <div class="talks-section-heading">
      <p>Conferences and workshops</p>
      <h2>Contributed</h2>
    </div>
    <div class="talks-section-line"></div>
  </header>

  <div class="talks-list">
    {% for talk in site.data.talks.contributed %}
      <article class="talk-entry">
        <div class="talk-meta">
          <time>{{ talk.date }}</time>
          <span>[{{ talk.code | remove_first: 'C' }}]</span>
        </div>
        <div class="talk-content">
          <h3>{{ talk.title }}</h3>
          <p>{{ talk.details }}</p>
          {% if talk.note %}<span class="talk-note">{{ talk.note }}</span>{% endif %}
        </div>
      </article>
    {% endfor %}
  </div>
</section>

<section class="talks-map-section">
  <header class="talks-map-header">
    <div class="talks-map-line"></div>
    <h2>Where I Spoke</h2>
  </header>

  <div class="talks-map">
    <iframe
      src="https://www.google.com/maps/d/u/0/embed?mid=1_nfRlZlS8TxrF-kj-RTmhKskPXSFDT8&amp;ehbc=2E312F"
      title="Map of places where Andrea Maselli has given talks"
      loading="lazy"
      referrerpolicy="no-referrer-when-downgrade">
    </iframe>
  </div>

  <p class="talks-map-link">
    <a href="https://www.google.com/maps/d/viewer?mid=1_nfRlZlS8TxrF-kj-RTmhKskPXSFDT8" target="_blank" rel="noopener noreferrer">
      Open the map in Google Maps
    </a>
  </p>
</section>
