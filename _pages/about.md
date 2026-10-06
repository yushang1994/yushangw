---
layout: archive
permalink: /
title: "About"
description: "Yushang Wei is a Lecturer in the Department of Economics at Auburn University. Applied microeconomics: health, transportation, and environmental economics."
author_profile: true
redirect_from:
  - /about/
  - /about.html
  - /cv/
  - /resume
---

{% comment %}
  Styles live in _sass/_custom.scss (.about-*, .cv-*). The CV PDF is files/pdf/cvyushang.pdf.
{% endcomment %}

<p class="about__lead">
  I am a Lecturer in the <a href="https://cla.auburn.edu/economics/">Department of Economics</a> at
  <a href="https://cla.auburn.edu/">Auburn University</a>. My research is in applied microeconomics,
  with a focus on health, transportation, and environmental economics.
</p>

<div class="about__actions">
  <a class="btn btn--primary" href="{{ '/files/pdf/cvyushang.pdf' | relative_url }}"><i class="fas fa-fw fa-file-pdf" aria-hidden="true"></i> Curriculum Vitae</a>
  <a class="btn btn--inverse" href="{{ '/research/' | relative_url }}">Research</a>
  <a class="btn btn--inverse" href="mailto:{{ site.author.email }}">Email me</a>
</div>

<section class="cv-section">
  <h2 class="cv-section__title" id="background">Background</h2>
  <div class="about__prose">
    <p>
      I received my Ph.D. in Economics from the
      <a href="https://arts-sciences.buffalo.edu/economics.html">University at Buffalo, The State University of New York</a>
      in 2024. Before that, I studied at <a href="https://www.purdue.edu/">Purdue University</a>, where I earned
      bachelor's degrees in both Economics and Applied Mathematics.
    </p>
    <p>
      My work asks how infrastructure and the built environment shape people's health and economic
      outcomes &mdash; from high-speed rail and road networks in China to roadway noise and nighttime
      light in the United States. At Auburn I teach principles of micro- and macroeconomics and
      intermediate microeconomics.
    </p>
  </div>
</section>

<section class="cv-section">
  <h2 class="cv-section__title" id="research-interests">Research Interests</h2>
  <ul class="about__tags">
    <li>Applied Microeconomics</li>
    <li>Health Economics</li>
    <li>Transportation Economics</li>
    <li>Environmental Economics</li>
  </ul>
</section>

<section class="cv-section">
  <h2 class="cv-section__title" id="education">Education</h2>
  <article class="cv-entry cv-entry--compact">
    <h3 class="cv-entry__title">Ph.D. in Economics <span class="cv-entry__status">2024</span></h3>
    <p class="cv-entry__meta">University at Buffalo, The State University of New York</p>
  </article>
  <article class="cv-entry cv-entry--compact">
    <h3 class="cv-entry__title">B.S. in Economics and B.S. in Applied Mathematics</h3>
    <p class="cv-entry__meta">Purdue University</p>
  </article>
</section>

<section class="cv-section">
  <h2 class="cv-section__title" id="beyond-work">Beyond Work</h2>
  <div class="about__cats">
    <a class="about__cat" href="{{ '/beyond-work/' | relative_url }}">
      <img src="{{ '/images/aboutme/rashba.jpg' | relative_url }}" alt="Drawing of Rashba, a British Shorthair cat">
      <span>Rashba</span>
    </a>
    <a class="about__cat" href="{{ '/beyond-work/' | relative_url }}">
      <img src="{{ '/images/aboutme/aubie.jpg' | relative_url }}" alt="Drawing of Aubie, a white kitten with blue eyes">
      <span>Aubie</span>
    </a>
    <a class="about__cat about__cat--memorial" href="{{ '/beyond-work/' | relative_url }}">
      <img src="{{ '/images/aboutme/sam.jpg' | relative_url }}" alt="Drawing of Sam, a grey Nebelung cat">
      <span>Sam <small>in loving memory</small></span>
    </a>
    <p class="about__prose">
      I share my home with two cats: Rashba, a 1-year-old British Shorthair who brings curiosity and
      youthful energy into every day, and Aubie, a 6-month-old kitten who is still discovering the world.
      Sam, my 18-year-old Nebelung and a calm, gentle presence for many years, passed away and is
      dearly missed. I also bake &mdash; a lot &mdash; and you can see the results on the
      <a href="{{ '/beyond-work/' | relative_url }}">Beyond Work</a> page.
    </p>
  </div>
</section>
