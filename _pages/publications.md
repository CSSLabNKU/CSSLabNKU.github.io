---
title: "Allan Lab - Publications"
layout: gridlay
excerpt: "Allan Lab -- Publications."
sitemap: false
permalink: /publications/
---

<style>
  .publication-grid {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 24px;
    margin-top: 24px;
  }

  .publication-card {
    display: flex;
    min-width: 0;
    flex-direction: column;
    overflow: hidden;
    border: 1px solid #e2e2e2;
    border-radius: 4px;
    background: #fff;
  }

  .publication-card__image {
    display: flex;
    height: 240px;
    align-items: center;
    justify-content: center;
    padding: 16px;
    background: #f7f7f7;
  }

  .publication-card__image img {
    display: block;
    width: 100%;
    height: 100%;
    margin: 0;
    object-fit: contain;
  }

  .publication-card__body {
    display: flex;
    flex: 1;
    flex-direction: column;
    padding: 20px;
  }

  .publication-card__body pubtit {
    display: block;
    margin-bottom: 12px;
  }

  .publication-card__body p:last-child {
    margin-bottom: 0;
  }

  @media (max-width: 767px) {
    .publication-grid {
      grid-template-columns: 1fr;
    }

    .publication-card__image {
      height: 220px;
    }
  }
</style>

### Better understanding of user-chosen passwords

**At the end of this page, you can find the [full list of publications and patents](#full-list-of-publications). All papers are also available on [arXiv](https://arxiv.org/search/?searchtype=author&query=Allan%2C+M+P).**

<div class="publication-grid">
{% for publi in site.data.publist %}

{% if publi.highlight == 1 %}

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" alt="{{ publi.title | escape }}" />
  </div>
  <div class="publication-card__body">
    <pubtit>{{ publi.title }}</pubtit>
    <p>{{ publi.description }}</p>
    <p><em>{{ publi.authors }}</em></p>
    <p><strong><a href="{{ publi.link.url }}">{{ publi.link.display }}</a></strong></p>
    {% if publi.news1 %}<p class="text-danger"><strong>{{ publi.news1 }}</strong></p>{% endif %}
    {% if publi.news2 %}<p>{{ publi.news2 }}</p>{% endif %}
  </div>
</article>

{% endif %}
{% endfor %}
</div>

<p> &nbsp; </p>


## Patents
<em>Milan P Allan, S Gröblacher, RA Norte, M Leeuwenhoek</em><br />Novel atomic force microscopy probes with phononic crystals<br /> PCT/NL20-20/050797 (2020)

<em>Milan P Allan</em><br /> Methods of manufacturing superconductor and phononic elements <br /> <a href="https://patents.google.com/patent/US10439125B2/en?inventor=Milan+ALLAN&oq=inventor:(Milan+ALLAN)">US10439125B2 (2016)</a>

## Full List of publications

{% for publi in site.data.publist %}

  {{ publi.title }} <br />
  <em>{{ publi.authors }} </em><br /><a href="{{ publi.link.url }}">{{ publi.link.display }}</a>

{% endfor %}
