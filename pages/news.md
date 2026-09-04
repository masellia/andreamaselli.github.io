---
layout: section
title: News
description: News, milestones, and events from Andrea Maselli's research group.
permalink: /news/
---

<section class="news-page" aria-labelledby="news-page-title">
  <header class="news-masthead">
    <div class="news-masthead-line"></div>
    <div class="news-masthead-copy">
      <p>From the group</p>
      <h1 id="news-page-title">NEWS</h1>
      <div>Milestones, events, and updates from our research community.</div>
    </div>
  </header>

  {% if site.data.news and site.data.news.size > 0 %}
    <div class="news-archive">
      <header class="news-archive-header">
        <span>Latest first</span>
        <h2>Group Notes</h2>
      </header>

      {% assign news_items = site.data.news | sort: 'date' | reverse %}
      {% for item in news_items %}
        <article class="news-entry{% if item.image %} news-entry-with-image{% endif %}" aria-labelledby="news-entry-{{ forloop.index }}">
          <div class="news-entry-meta">
            {% if item.category %}<span>{{ item.category }}</span>{% endif %}
            {% if item.date %}<time datetime="{{ item.date }}">{{ item.date | date: '%-d %B %Y' }}</time>{% endif %}
          </div>

          <div class="news-entry-copy">
            <h3 id="news-entry-{{ forloop.index }}">{{ item.title }}</h3>
            {% if item.text %}<div class="news-entry-text">{{ item.text | markdownify }}</div>{% endif %}
            {% if item.url %}
              <a href="{% if item.url contains '://' %}{{ item.url }}{% else %}{{ item.url | relative_url }}{% endif %}"{% if item.url contains '://' %} target="_blank" rel="noopener"{% endif %}>
                {{ item.link_label | default: 'Read more' }}
              </a>
            {% endif %}
          </div>

          {% if item.image %}
            <figure class="news-entry-media">
              <img src="{{ item.image | relative_url }}" alt="{{ item.image_alt }}" loading="lazy">
              {% if item.image_caption %}<figcaption>{{ item.image_caption }}</figcaption>{% endif %}
            </figure>
          {% endif %}
        </article>
      {% endfor %}
    </div>
  {% else %}
    <p class="news-empty">The first group update will appear here.</p>
  {% endif %}
</section>
