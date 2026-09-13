---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% comment %}
  Content for this page lives in _data/research.yml; styles in _sass/_custom.scss (.cv-*).
{% endcomment %}

{% for section in site.data.research %}
<section class="cv-section">
  <h2 class="cv-section__title" id="{{ section.title | slugify }}">{{ section.title }}</h2>

  {% for item in section.items %}
  <article class="cv-entry">
    <h3 class="cv-entry__title">
      {% if item.url %}<a href="{{ item.url }}">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}
      {% if item.status %}<span class="cv-entry__status">{{ item.status }}</span>{% endif %}
    </h3>

    {% if item.authors %}<p class="cv-entry__meta">{{ item.authors | markdownify | remove: '<p>' | remove: '</p>' }}</p>{% endif %}
    {% if item.venue %}<p class="cv-entry__meta cv-entry__venue">{{ item.venue | markdownify | remove: '<p>' | remove: '</p>' }}</p>{% endif %}
    {% if item.note %}<p class="cv-entry__meta cv-entry__note">{{ item.note }}</p>{% endif %}

    {% if item.pdf or item.poster %}
    <div class="cv-entry__links">
      {% if item.pdf %}<a href="{{ item.pdf | relative_url }}"><i class="fas fa-fw fa-file-pdf" aria-hidden="true"></i> Paper</a>{% endif %}
      {% if item.poster %}<a href="{{ item.poster | relative_url }}"><i class="fas fa-fw fa-image" aria-hidden="true"></i> Poster</a>{% endif %}
    </div>
    {% endif %}
    {% if item.abstract %}
    <details class="cv-entry__abstract">
      <summary>Abstract</summary>
      <p>{{ item.abstract }}</p>
    </details>
    {% endif %}
  </article>
  {% endfor %}
</section>
{% endfor %}
