---
title: "Publications Preview - Welcome to Ding Wang's Homepage"
layout: publications
excerpt: "YAML-driven publications page preview"
sitemap: false
permalink: /publications-preview/
---

<style>
  .publications-preview {
    max-width: 980px;
    margin: 38px auto 64px;
    color: #25242a;
  }

  .publications-preview .preview-heading {
    margin: 0 0 6px;
    font-size: 30px;
    font-weight: 700;
    letter-spacing: -0.02em;
  }

  .publications-preview .preview-intro {
    margin: 0 0 34px;
    color: #6b6873;
    font-size: 15px;
  }

  .publications-preview .pub-year h2 {
    margin: 0 0 14px;
    padding-bottom: 8px;
    border-bottom: 2px solid #5040ae;
    color: #5040ae;
    font-size: 24px;
  }

  .publications-preview .pub-items {
    margin: 0;
    padding: 0;
    list-style: none;
    counter-reset: publication;
  }

  .publications-preview .pub-item {
    position: relative;
    margin: 0;
    padding: 18px 20px 18px 54px;
    border-bottom: 1px solid #e8e6ed;
    counter-increment: publication;
  }

  .publications-preview .pub-item::before {
    position: absolute;
    top: 19px;
    left: 8px;
    width: 30px;
    color: #9a96a4;
    content: counter(publication) ".";
    font-size: 14px;
    text-align: right;
  }

  .publications-preview .pub-item:hover {
    background: #faf9fd;
  }

  .publications-preview .pub-authors {
    margin-bottom: 3px;
    color: #55515e;
    font-size: 15px;
  }

  .publications-preview .pub-title {
    margin-bottom: 4px;
    color: #1f1d24;
    font-size: 17px;
    font-weight: 700;
    line-height: 1.45;
  }

  .publications-preview .pub-meta {
    color: #4f4b56;
    line-height: 1.5;
  }

  .publications-preview .pub-venue {
    color: #5040ae;
    font-weight: 600;
  }

  .publications-preview .pub-footer {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 10px;
    margin-top: 9px;
  }

  .publications-preview .pub-link {
    display: inline-block;
    padding: 3px 10px;
    border: 1px solid #5040ae;
    border-radius: 3px;
    color: #5040ae;
    font-size: 12px;
    font-weight: 700;
    letter-spacing: 0.04em;
    text-decoration: none;
  }

  .publications-preview .pub-link:hover {
    background: #5040ae;
    color: #fff;
  }

  .publications-preview .pub-note {
    color: #77727e;
    font-size: 13px;
    font-style: italic;
  }

  @media screen and (max-width: 576px) {
    .publications-preview {
      margin-top: 24px;
    }

    .publications-preview .preview-heading {
      font-size: 25px;
    }

    .publications-preview .pub-item {
      padding-right: 4px;
      padding-left: 36px;
    }

    .publications-preview .pub-item::before {
      left: 0;
      width: 24px;
    }
  }
</style>

<div class="publications-preview">
  <h1 class="preview-heading">Publications</h1>
  <p class="preview-intro">Preview of the YAML-driven layout. This page currently contains the 2026 publications only.</p>

  {% include publication-list-preview.html %}
</div>
