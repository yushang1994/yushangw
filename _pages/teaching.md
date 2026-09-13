---
layout: archive
permalink: /teaching/
title: "Teaching"
author_profile: true
---

{% comment %}
  Content for this page lives in _data/teaching.yml; styles in _sass/_custom.scss (.cv-*).
{% endcomment %}

{% for section in site.data.teaching %}
<section class="cv-section">
  <h2 class="cv-section__title" id="{{ section.institution | append: '-' | append: section.role | slugify }}">
    {{ section.institution }}<span class="cv-section__role">{{ section.role }}</span>
  </h2>

  {% for course in section.items %}
  <article class="cv-entry">
    <h3 class="cv-entry__title cv-entry__title--course">
      <span class="cv-entry__code">{{ course.code }}</span><span>{{ course.title }}</span>
    </h3>
    {% if course.terms %}<p class="cv-entry__meta">{{ course.terms | join: " · " }}</p>{% endif %}
    {% if course.links %}
    <div class="cv-entry__links">
      {% for link in course.links %}<a href="{{ link.file | relative_url }}"><i class="fas fa-fw fa-file-pdf" aria-hidden="true"></i> {{ link.label }}</a>{% endfor %}
    </div>
    {% endif %}
  </article>
  {% endfor %}
</section>
{% endfor %}
