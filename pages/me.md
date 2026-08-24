---
layout: section
title: Me
permalink: /me/
---

<div class="page-header">
  <div class="page-header-line"></div>
  <div class="page-header-title">ME</div>
</div>

<div class="me-jump-links">
  <a href="#travel">Travel & Photography</a>
  <a href="#kung-fu">Kung Fu & Philosophy</a>
  <a href="#sunday">Any Given Sunday</a>
</div>

<section id="travel" class="me-section me-travel-section">
  <header class="me-section-header me-section-header-right">
    <div class="me-section-line"></div>
    <h2>Travel &<br>Photography</h2>
  </header>

  <div class="me-intro">
    <p>
      Off the job, I am interested in any activity which surrounds me with wild landscapes. I like to visit remote places far apart from civilization, especially with my best friend Luca (we really like Ice). Photography is one of my greatest loves, and some of my pictures have been published on the Italian National Geographic website. Below and
      <a href="https://masellia.github.io/photos/" target="_blank" rel="noopener noreferrer">here</a>
      you can find some images of trips and (girl)friends.
    </p>

    <div class="me-actions">
      <a href="https://masellia.github.io/photos/" target="_blank" rel="noopener noreferrer">Full photography site</a>
      <a href="https://www.instagram.com/starquake85/" target="_blank" rel="noopener noreferrer">Instagram</a>
    </div>
  </div>

  {% if site.data.me.travel and site.data.me.travel.size > 0 %}
    <div class="me-gallery">
      {% for photo in site.data.me.travel %}
        <figure class="me-gallery-item">
          <a href="#me-photo-{{ forloop.index }}">
            <img src="{{ photo.image | relative_url }}" alt="{{ photo.alt }}" loading="lazy">
          </a>
          {% if photo.caption %}<figcaption>{{ photo.caption }}</figcaption>{% endif %}
        </figure>

        <div id="me-photo-{{ forloop.index }}" class="me-lightbox">
          <a class="me-lightbox-close" href="#travel" aria-label="Close image">×</a>
          <img src="{{ photo.image | relative_url }}" alt="{{ photo.alt }}">
          {% if photo.caption %}<p>{{ photo.caption }}</p>{% endif %}
        </div>
      {% endfor %}
    </div>
  {% endif %}
</section>

<section id="kung-fu" class="me-section me-section-dark">
  <header class="me-section-header me-section-header-left me-section-header-overlap">
    <h2>Kung Fu &<br>Philosophy</h2>
    <div class="me-section-line"></div>
  </header>

  <div class="me-story{% unless site.data.me.kung_fu.image %} me-story-no-media{% endunless %}">
    {% if site.data.me.kung_fu.image %}
      <figure class="me-story-media">
        <img src="{{ site.data.me.kung_fu.image | relative_url }}" alt="{{ site.data.me.kung_fu.alt }}" loading="lazy">
        {% if site.data.me.kung_fu.caption %}<figcaption>{{ site.data.me.kung_fu.caption }}</figcaption>{% endif %}
      </figure>
    {% endif %}

    <div class="me-story-text">
      <p>
        In my spare time I like reading books, mostly history and philosophy. I am deeply interested in Eastern cultures, especially Chinese traditions. For more than ten years I have practised Hung Gar, a southern Chinese kung fu style. My traditional school in Rome, and my Sifu Angelo Riolo, are a second family to me.
      </p>
      <a class="me-story-link" href="https://kungfuhunggar.com/" target="_blank" rel="noopener noreferrer">Visit the Hung Gar school</a>
    </div>
  </div>
</section>

<section id="sunday" class="me-section me-sunday-section">
  <header class="me-section-header me-section-header-right">
    <div class="me-section-line"></div>
    <h2>Any Given<br>Sunday</h2>
  </header>

  <div class="me-story me-story-reverse{% unless site.data.me.packers.image %} me-story-no-media{% endunless %}">
    {% if site.data.me.packers.image %}
      <figure class="me-story-media">
        <img src="{{ site.data.me.packers.image | relative_url }}" alt="{{ site.data.me.packers.alt }}" loading="lazy">
        {% if site.data.me.packers.caption %}<figcaption>{{ site.data.me.packers.caption }}</figcaption>{% endif %}
      </figure>
    {% endif %}

    <div class="me-story-text">
      <p>
        Last but not least, I am a big fan of American football and the Green Bay Packers, one of the NFL's most historic teams. Their followers are also known as
        <a href="https://en.wikipedia.org/wiki/Cheesehead" target="_blank" rel="noopener noreferrer">cheeseheads</a>.
        I still hope to see a game at the iconic Lambeau Field. Since 2022, I have also been a Packers shareholder.
      </p>
      <a class="me-story-link" href="https://shareholder.broadridge.com/gbp/" target="_blank" rel="noopener noreferrer">Packers shareholders</a>
    </div>
  </div>
</section>
