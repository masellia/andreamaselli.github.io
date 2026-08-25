---
layout: section
title: Me
permalink: /me/
---

<section id="travel" class="me-section me-travel-section">
  <header class="me-section-header me-section-header-right">
    <div class="me-section-line"></div>
    <h2>Travel &<br>Photography</h2>
  </header>

  <div class="me-section-copy me-copy-right">
    <p>
      Off the job, I am interested in any activity which surrounds me with wild landscapes. I like to visit remote places far apart from civilization, especially with my best friend Luca (we really like Ice). Photography is one of my greatest loves, and some of my pictures have been published on the Italian National Geographic website. Below and
      <a href="https://masellia.github.io/photos/" target="_blank" rel="noopener noreferrer">here</a>
      you can find some images of trips and (girl)friends.
    </p>
  </div>

  <div class="me-gallery">
    {% for photo in site.data.me.travel %}
      <figure class="me-gallery-item{% unless photo.image %} me-gallery-item-empty{% endunless %}">
        {% if photo.image %}
          <a href="#me-photo-{{ forloop.index }}">
            <img src="{{ photo.image | relative_url }}" alt="{{ photo.alt }}" loading="lazy">
          </a>
        {% else %}
          <div class="me-gallery-placeholder" aria-hidden="true"></div>
        {% endif %}
        {% if photo.caption %}<figcaption>{{ photo.caption }}</figcaption>{% endif %}
      </figure>

      {% if photo.image %}
        <div id="me-photo-{{ forloop.index }}" class="me-lightbox">
          <a class="me-lightbox-close" href="#travel" aria-label="Close image">×</a>
          <img src="{{ photo.image | relative_url }}" alt="{{ photo.alt }}">
          {% if photo.caption %}<p>{{ photo.caption }}</p>{% endif %}
        </div>
      {% endif %}
    {% endfor %}
  </div>
</section>

<section id="kung-fu" class="me-section me-section-dark">
  <header class="me-section-header me-section-header-left me-section-header-overlap">
    <h2>Kung Fu &<br>Philosophy</h2>
    <div class="me-section-line"></div>
  </header>

  <div class="me-section-copy me-copy-left">
    <p>
      In my spare time I like reading books, mostly
      <a href="https://www.marxists.org/archive/lenin/works/1917/staterev/" target="_blank" rel="noopener noreferrer">history</a>
      and philosophy. I am deeply interested in Eastern cultures, especially Chinese traditions. For more than ten years I have practised Hung Gar, a southern Chinese kung fu style. My
      <a href="https://kungfuhunggar.com/" target="_blank" rel="noopener noreferrer">traditional school in Rome</a>,
      and my Sifu Angelo Riolo, are a second family to me.
    </p>
  </div>
</section>

<section id="sunday" class="me-section me-sunday-section">
  <header class="me-section-header me-section-header-right">
    <div class="me-section-line"></div>
    <h2>Any Given<br>Sunday</h2>
  </header>

  <div class="me-sunday-content">
    <figure class="me-sunday-media{% unless site.data.me.packers.image %} me-sunday-media-empty{% endunless %}">
      {% if site.data.me.packers.image %}
        <img src="{{ site.data.me.packers.image | relative_url }}" alt="{{ site.data.me.packers.alt }}" loading="lazy">
      {% else %}
        <div class="me-sunday-placeholder" aria-hidden="true"></div>
      {% endif %}
      {% if site.data.me.packers.caption %}<figcaption>{{ site.data.me.packers.caption }}</figcaption>{% endif %}
    </figure>

    <div class="me-sunday-text">
      <p>
        Last but not least I am a big fan of American Football, and of the Green Bay Packers, the most historical team of the NFL (followers are also known as
        <a href="https://en.wikipedia.org/wiki/Cheesehead" target="_blank" rel="noopener noreferrer">cheeseheads</a>).
        Hopefully one day I'll be able to see a match at the iconic
        <a href="https://en.wikipedia.org/wiki/Lambeau_Field" target="_blank" rel="noopener noreferrer">Lambeau Field</a>.
        And since 2022 I am an actual
        <a href="https://shareholder.broadridge.com/gbp/" target="_blank" rel="noopener noreferrer">shareholder</a>
        of the Packers!
      </p>
    </div>
  </div>
</section>
