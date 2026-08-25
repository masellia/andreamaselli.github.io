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
My research field concerns various theoretical aspects of gravitational theory: classical General Relativity and gravitational wave emission, electromagnetic signatures of gravitational interaction between astrophysical objects, extended theories of gravity.
<br>
<br>
My primary interest is strong gravity, which plays a crucial role in many astrophysical phenomena involving the most compact objects of our Universe, i.e. black-hole and neutron stars, as isolated and binary sources. These systems represent natural laboratories to test physics under extreme conditions, which cannot be reproduced with terrestrial experiments.
<br>
<br>
I am interested in the theoretical modelling of these objects in General Relativity and extension of it, in the study of their dynamic and stability, and of their phenomenology.

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
          <div class="research-highlight-overview">
            <p class="research-highlight-summary">{{ highlight.summary }}</p>

            {% if highlight.figures and highlight.figures.size > 0 %}
              <div class="research-highlight-figures">
                {% for figure in highlight.figures %}
                  <figure style="--research-figure-width: {{ figure.width | default: 280 }}px;">
                    <img src="{{ figure.src | relative_url }}" alt="{{ figure.alt }}">
                    {% if figure.caption %}<figcaption>{{ figure.caption }}</figcaption>{% endif %}
                  </figure>
                {% endfor %}
              </div>
            {% endif %}
          </div>

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

  <div class="research-collaborations-layout">
    <div class="research-collaborations-copy">
      <p class="research-collaborations-intro">
        I am currently a member of the INFN Specific Initiative <a href="https://web.infn.it/CSN4/index.php/it/17-esperimenti/195-teongrav-home" target="_blank" rel="noopener">TEONGRAV</a>, "Theory of Gravitational Wave Sources," as well as of the following international collaborations developing the science case for future gravitational-wave observatories and advancing strong-gravity research.
      </p>
    </div>

    <ul class="research-collaboration-list">
      <li>
        <figure class="research-collaboration-media research-collaboration-media-loaded research-collaboration-media-lisa">
          <img src="{{ '/assets/img/research/LISA_logo.jpg' | relative_url }}" alt="LISA logo" loading="lazy">
        </figure>
        <div class="research-collaboration-content">
          <a href="https://www.lisamission.org/" target="_blank" rel="noopener">LISA</a>
          <span> The first gravitational space-based gravitational-wave observatory with arm-length of 2.5 million km.</span>
        </div>
      </li>
      <li>
        <figure class="research-collaboration-media research-collaboration-media-loaded research-collaboration-media-et">
          <img src="{{ '/assets/img/research/ET_logo.jpg' | relative_url }}" alt="Einstein Telescope logo" loading="lazy">
        </figure>
        <div class="research-collaboration-content">
          <a href="https://einsteintelescope.eu/" target="_blank" rel="noopener">Einstein Telescope</a>
          <span>The future European third-generation ground-based gravitational-wave observatory.</span>
        </div>
      </li>
      <li>
        <figure class="research-collaboration-media research-collaboration-media-loaded research-collaboration-media-lgwa">
          <img src="{{ '/assets/img/research/lgwa_logo.jpg' | relative_url }}" alt="Lunar Gravitational-Wave Antenna logo" loading="lazy">
        </figure>
        <div class="research-collaboration-content">
          <a href="https://lgwa.unicam.it/" target="_blank" rel="noopener">Lunar Gravitational-Wave Antenna</a>
          <span>A new concept of Lunar gravitational wave observatory targeting signals emitted in the decihertz band.</span>
        </div>
      </li>
      <li>
        <div class="research-collaboration-media research-collaboration-media-empty" aria-hidden="true"></div>
        <div class="research-collaboration-content">
          <a href="https://masellia.github.io/strong-action/" target="_blank" rel="noopener">STRONG</a>
          <span> STRONG is a Marie Skłodowska-Curie Staff Exchange Action dedicated to investigating gravity 
in its most extreme regimes, where compact objects, high-energy phenomena, and fundamental fields interact, 
for which I serve as Principal Investigator.</span>
        </div>
      </li>
    </ul>
  </div>
</section>
