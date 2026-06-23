---
layout: section
title: Publications
permalink: /publications/
---

<div class="page-header">
  <div class="page-header-line"></div>

  <div class="page-header-title">
    PUBLICATIONS
  </div>
</div>

<div class="publications-intro">

  <p>
    Here is my publication list. You can also find my papers on

    <a href="https://inspirehep.net/authors/1189872" target="_blank">
      <img class="inline-icon"
           src="{{ '/assets/img/inspire.jpg' | relative_url }}"
           alt="INSPIRE">
    </a>

    and

    <a href="https://scholar.google.com/citations?user=fUBWIzgAAAAJ&hl=en" target="_blank">
      <img class="inline-icon"
           src="{{ '/assets/img/google-scholar.png' | relative_url }}"
           alt="Google Scholar">
    </a>.

    Click on the BibTeX button to copy a ready-to-paste citation.
  </p>

</div>

<section class="publications-page">

  {% assign pubs = site.data.publications %}

  {% for block in pubs %}
    <h2 class="pubs-year">{{ block.year }}</h2>

    {% for p in block.papers %}
      <article class="pub-item">

        <p class="pub-title">{{ p.title }}</p>

        {% if p.authors %}
          <div class="pub-authors">{{ p.authors }}</div>
        {% endif %}

        {% if p.journal %}
          <div class="pub-journal">{{ p.journal }}</div>
        {% endif %}

        <div class="pub-actions">
          {% if p.arxiv %}
            <a target="_blank" rel="noopener" href="https://arxiv.org/abs/{{ p.arxiv }}">arXiv</a>
          {% endif %}

          {% if p.doi %}
            <a target="_blank" rel="noopener" href="https://doi.org/{{ p.doi }}">DOI</a>
          {% endif %}

          {% if p.bibtex %}
            <button type="button"
                    data-bibtex="{{ p.bibtex | escape }}"
                    onclick="copyBibtex(this)">
              BibTeX
            </button>
            <span class="pub-status" data-bibtex-status></span>
          {% endif %}
        </div>

      </article>
    {% endfor %}
  {% endfor %}

</section>

<script>
async function copyBibtex(btnEl) {
  const statusEl = btnEl.parentElement.querySelector('[data-bibtex-status]');
  const bib = btnEl.getAttribute('data-bibtex') || '';
  const txt = new DOMParser().parseFromString(bib, "text/html").documentElement.textContent;

  try {
    if (statusEl) statusEl.textContent = "Copying...";
    await navigator.clipboard.writeText(txt);
    if (statusEl) statusEl.textContent = "Copied!";
    setTimeout(() => { if (statusEl) statusEl.textContent = ""; }, 2000);
  } catch (e) {
    if (statusEl) statusEl.textContent = "Copy failed";
    setTimeout(() => { if (statusEl) statusEl.textContent = ""; }, 2000);
  }
}
</script>
