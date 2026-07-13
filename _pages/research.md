---
title: "Researches - Welcome to Ding Wang's Homepage -- Password Cryptography"
layout: gridlay
excerpt: ""
sitemap: false
permalink: /researches/
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
    height: 290px;
    align-items: center;
    justify-content: center;
    padding: 16px;
    background: #f7f7f7;
  }

  #gridid .publication-card__image img {
    display: block;
    width: 100%;
    height: 100%;
    margin: 0;
    border-radius: 0;
    box-shadow: none;
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
      height: 260px;
    }
  }
</style>

### Better understanding of user-chosen passwords

<div class="publication-grid" markdown="0">

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/our-cdf-zipf-model-performs-much-better-in-characterizing-password-distributions-as_orig.png"/>
  </div>
  <div class="publication-card__body">
    <p><strong>In this work, we make a substantial step forward towards understanding the distribution of passwords. </strong>By introducing a number of computational statistical techniques and based on fourteen large-scale datasets, which consist of 113.3 million real-world passwords, we for the first time show that Zipf's law natively exists in the popular (and thus vulnerable) part of human-generated password datasets. Further, we provide compelling evidence that this law is also highly likely to hold in the remaining part of human-generated passwords. (see more in our <u><a href="/uploads/2/0/3/6/20366987/ieeetifs17_final.pdf">IEEE TIFS'17 paper</a>; </u>and<u><a href="/uploads/2/0/3/6/20366987/esorics16_final.pdf"> its applications in ESORICS'16 paper</a></u>)</p>
  </div>
</article>

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/3618436.jpg" />
  </div>
  <div class="publication-card__body">
    <p><strong>We have conducted a systematic investigation into the characteristics, distribution and security of PINs chosen by English user and Chinese users.</strong> By employing NLP techniques, we have revealed that PINs follow a Zipf distribution; By adopting both statistic metrics and state-of-the-art cracking algorithms, we have highlighted that 6-digit PINs offer marginally improved security over 4-digit PINs. (see more in our <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/asiaccs17_v12.pdf" target="_blank"><u>ASIACCS'17 paper</u></a>) </p>
  </div>
</article>
</div>

### Understanding and improving password creation policies

<div class="publication-grid" markdown="0">

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/8259798.jpg" />
  </div>
  <div class="publication-card__body">
    <p><strong>In this work, we conduct an extensive empirical study of 50 password creation policies that are currently imposed on high-proﬁle web services,</strong> including 20 policies mainly from US and 30 ones from mainland China. Our results show that the policies enforced in leading sites largely fail to serve their purposes, especially vulnerable to targeted online guessing attacks.  (see more in <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/esorics15conf0827.pdf" target="_blank"><u>ESORICS'15 paper</u></a>)</p>
  </div>
</article>

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/4121880_orig.png" />
  </div>
  <div class="publication-card__body">
    <p><strong>We propose a simple yet effective password strength meter, fuzzyPSM,</strong> to give users reliable feedbacks when they select passwords. Inspired by a user survey on password practice, FuzzyPSM takes the ﬁrst step towards characterizing realistic user behaviors in password creation: Generally users do not build new passwords from scratch for a new service by combining segments of words, digits and/or symbols, instead they reuse or simply modify existing passwords for new services. (see more in <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/dsn16v9.pdf" target="_blank"><u>DSN'16 paper</u></a>)</p>
  </div>
</article>
</div>
