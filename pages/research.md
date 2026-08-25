---
layout: section
title: Research
permalink: /research/
---

<div class="page-header">
  <div class="page-header-line"></div>
  <div class="page-header-title">RESEARCH</div>
</div>

<div class="research-intro">
  <p>
    My research activity focuses on theoretical gravitational physics, with particular emphasis on the modelling and phenomenology of compact objects in classical General Relativity and extended theories of gravity. I study gravitational-wave emission, electromagnetic signatures and the dynamics of relativistic binaries, including systems embedded in dense astrophysical environments. Black holes and neutron stars are natural laboratories for probing gravity and matter under conditions inaccessible to terrestrial experiments. My work relies primarily on perturbation theory and analytical approximation techniques to solve gravitational field equations in the strong-gravity regime and connect theoretical models with observations.
  </p>
</div>

<section class="research-highlights" aria-labelledby="research-highlights-title">
  <div class="research-section-header research-section-header-left">
    <div class="research-section-line"></div>
    <h2 id="research-highlights-title">Recent Highlights</h2>
  </div>

  <div class="research-highlight-grid">
    {% for highlight in site.data.research_highlights %}
      <details class="research-highlight">
        <summary>
          <span>{{ highlight.title }}</span>
          <span class="research-highlight-toggle" aria-hidden="true"></span>
        </summary>

        <div class="research-highlight-content">
          <p class="research-highlight-summary">{{ highlight.summary }}</p>

          <div class="research-highlight-papers">
            <h3>Selected Papers</h3>
            <ul>
              {% for paper_id in highlight.papers %}
                {% for publication_year in site.data.publications %}
                  {% for paper in publication_year.papers %}
                    {% if paper.arxiv == paper_id %}
                      <li>
                        <a href="https://arxiv.org/abs/{{ paper.arxiv }}" target="_blank" rel="noopener">{{ paper.title }}</a>
                        <span>{{ paper.authors }} ({{ publication_year.year }})</span>
                      </li>
                    {% endif %}
                  {% endfor %}
                {% endfor %}
              {% endfor %}
            </ul>
          </div>

          {% if highlight.figures and highlight.figures.size > 0 %}
            <div class="research-highlight-figures">
              {% for figure in highlight.figures %}
                <figure>
                  <img src="{{ figure.src | relative_url }}" alt="{{ figure.alt }}">
                  {% if figure.caption %}<figcaption>{{ figure.caption }}</figcaption>{% endif %}
                </figure>
              {% endfor %}
            </div>
          {% endif %}
        </div>
      </details>
    {% endfor %}
  </div>
</section>

<section class="research-collaborations" aria-labelledby="research-collaborations-title">
  <div class="research-section-header research-section-header-right">
    <div class="research-section-line"></div>
    <h2 id="research-collaborations-title">Collaborations</h2>
  </div>

  <p class="research-collaborations-intro">
    I contribute to international collaborations developing the science case for future gravitational-wave observatories and advancing strong-gravity research.
  </p>

  <ul class="research-collaboration-list">
    <li>
      <a href="https://www.lisamission.org/" target="_blank" rel="noopener">LISA</a>
      <span>Space-based gravitational-wave observatory.</span>
    </li>
    <li>
      <a href="https://einsteintelescope.eu/" target="_blank" rel="noopener">Einstein Telescope</a>
      <span>Third-generation underground gravitational-wave observatory.</span>
    </li>
    <li>
      <a href="https://lgwa.unicam.it/" target="_blank" rel="noopener">Lunar Gravitational-Wave Antenna</a>
      <span>Lunar observatory targeting decihertz gravitational waves.</span>
    </li>
    <li>
      <a href="https://masellia.github.io/strong-action/" target="_blank" rel="noopener">STRONG</a>
      <span>Marie Skłodowska-Curie Staff Exchange project on strong gravity and fundamental physics, for which I serve as Principal Investigator.</span>
    </li>
  </ul>
</section>
