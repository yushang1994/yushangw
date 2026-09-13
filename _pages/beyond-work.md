---
layout: archive
permalink: /beyond-work/
title: "Beyond Work"
description: "Cats, pastry, and games — photo albums from life outside the office."
author_profile: true
redirect_from:
  - /other/
  - /publications/
---

{% comment %}
  Albums live in _data/albums.yml; styles in _sass/_custom.scss (.albums, .album-*).
{% endcomment %}

<p class="cv-intro">Life outside the office, in three albums. Pick one to see the photos.</p>

<div class="albums" id="albums">
  {% for album in site.data.albums %}
  <a class="album-card" href="#{{ album.id }}" data-album="{{ album.id }}">
    <span class="album-card__cover">
      {% assign cover_name = album.cover | split: "/" | last | split: "." | first %}
      <img src="{{ '/images/thumbs/' | append: cover_name | append: '.jpg' | relative_url }}" alt="">
    </span>
    <span class="album-card__body">
      <span class="album-card__title">{{ album.title }}</span>
      <span class="album-card__count">{{ album.photos | size }} photo{% if album.photos.size != 1 %}s{% endif %}</span>
    </span>
  </a>
  {% endfor %}
</div>

{% for album in site.data.albums %}
<section class="album{% if album.aspect == 'wide' %} album--wide{% endif %}" id="{{ album.id }}" data-album="{{ album.id }}" hidden>
  <h2 class="cv-section__title">{{ album.title }}</h2>
  <p class="album__description">{{ album.description }}</p>
  <div class="album__grid">
    {% for photo in album.photos %}
    {% assign thumb_name = photo.file | split: "/" | last | split: "." | first %}
    <a class="album__photo" href="{{ '/images/' | append: photo.file | relative_url }}" title="{{ photo.caption | escape }}">
      <img src="{{ '/images/thumbs/' | append: thumb_name | append: '.jpg' | relative_url }}" alt="{{ photo.alt | escape }}" loading="lazy">
      {% if photo.caption %}<span class="album__caption">{{ photo.caption }}</span>{% endif %}
    </a>
    {% endfor %}
  </div>
</section>
{% endfor %}

<script>
  (function () {
    var cards = document.querySelectorAll('.album-card');
    var albums = document.querySelectorAll('.album');
    var ids = Array.prototype.map.call(albums, function (a) { return a.dataset.album; });

    function show(id, scroll) {
      if (ids.indexOf(id) === -1) { id = ids[0]; }
      Array.prototype.forEach.call(albums, function (a) { a.hidden = a.dataset.album !== id; });
      Array.prototype.forEach.call(cards, function (c) {
        c.classList.toggle('is-active', c.dataset.album === id);
        c.setAttribute('aria-pressed', c.dataset.album === id ? 'true' : 'false');
      });
      if (scroll) {
        var el = document.getElementById(id);
        if (el && el.scrollIntoView) { el.scrollIntoView({ behavior: 'smooth', block: 'start' }); }
      }
    }

    Array.prototype.forEach.call(cards, function (c) {
      c.addEventListener('click', function (e) {
        e.preventDefault();
        if (history.replaceState) { history.replaceState(null, '', '#' + c.dataset.album); }
        show(c.dataset.album, true);
      });
    });
    window.addEventListener('hashchange', function () { show(location.hash.slice(1), true); });
    show(location.hash.slice(1), false);

    // One lightbox gallery per album (the theme's default puts every image on the page in one gallery).
    // The theme's scripts load after this page content, so wait for the window load event.
    window.addEventListener('load', function () {
      if (!(window.jQuery && jQuery.fn.magnificPopup)) { return; }
      jQuery('.album').each(function () {
        var links = jQuery(this).find('.album__photo');
        links.removeClass('image-popup').off('click.mfp');
        links.magnificPopup({
          type: 'image',
          gallery: { enabled: true, navigateByImgClick: true, preload: [0, 1] },
          image: { titleSrc: 'title' },
          removalDelay: 300,
          mainClass: 'mfp-zoom-in',
          closeOnContentClick: true,
          midClick: true
        });
      });
    });
  })();
</script>
