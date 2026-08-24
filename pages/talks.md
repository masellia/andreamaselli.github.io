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

<p class="talks-intro">
  A chronological archive of invited seminars and talks, and contributed presentations at conferences and workshops.
</p>

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
