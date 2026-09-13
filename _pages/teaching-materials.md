---
layout: archive
permalink: /teaching-materials/
title: "Course Materials"
author_profile: true
---

{% comment %}
  Content for this page lives in _data/course_materials.yml; styles in _sass/_custom.scss (.cv-*).
{% endcomment %}

{% assign materials = site.data.course_materials %}
{% if materials.intro %}<p class="cv-intro">{{ materials.intro }}</p>{% endif %}

{% for section in materials.sections %}
<section class="cv-section">
  <h2 class="cv-section__title" id="{{ section.course | slugify }}">{{ section.course }}</h2>

  {% for group in section.groups %}
  <h3 class="cv-group__title">{{ group.title }}</h3>
  {% for item in group.items %}
  <article class="cv-entry cv-entry--compact">
    <h4 class="cv-entry__title">
      {% if item.url %}<a href="{{ item.url }}">{{ item.title }}</a>{% elsif item.file %}<a href="{{ item.file | relative_url }}">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}
    </h4>
    {% if item.description %}<p class="cv-entry__meta">{{ item.description }}</p>{% endif %}
    {% if item.file %}
    <div class="cv-entry__links">
      <a href="{{ item.file | relative_url }}"><i class="fas fa-fw fa-file-pdf" aria-hidden="true"></i> PDF</a>
    </div>
    {% endif %}
  </article>
  {% endfor %}
  {% endfor %}
</section>
{% endfor %}
