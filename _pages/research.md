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
    <p><strong>In this work, we make a substantial step forward towards understanding the distribution of passwords. </strong>By introducing a number of computational statistical techniques and based on fourteen large-scale datasets, which consist of 113.3 million real-world passwords, we for the first time show that Zipf's law natively exists in the popular (and thus vulnerable) part of human-generated password datasets. Further, we provide compelling evidence that this law is also highly likely to hold in the remaining part of human-generated passwords. (see more in our <u><a href="{{ site.url }}{{ site.baseurl }}/researches/ieeetifs17_final.pdf">IEEE TIFS'17 paper</a>; </u>and<u><a href="{{ site.url }}{{ site.baseurl }}/researches/esorics16_final.pdf"> its applications in ESORICS'16 paper</a></u>)</p>
  </div>
</article>

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/3618436.jpg" />
  </div>
  <div class="publication-card__body">
    <p><strong>We have conducted a systematic investigation into the characteristics, distribution and security of PINs chosen by English user and Chinese users.</strong> By employing NLP techniques, we have revealed that PINs follow a Zipf distribution; By adopting both statistic metrics and state-of-the-art cracking algorithms, we have highlighted that 6-digit PINs offer marginally improved security over 4-digit PINs. (see more in our <a href="{{ site.url }}{{ site.baseurl }}/researches/asiaccs17_v12.pdf" target="_blank"><u>ASIACCS'17 paper</u></a>)</p>
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
    <p><strong>In this work, we conduct an extensive empirical study of 50 password creation policies that are currently imposed on high-proﬁle web services,</strong> including 20 policies mainly from US and 30 ones from mainland China. Our results show that the policies enforced in leading sites largely fail to serve their purposes, especially vulnerable to targeted online guessing attacks.  (see more in <a href="{{ site.url }}{{ site.baseurl }}/researches/esorics15conf0827.pdf" target="_blank"><u>ESORICS'15 paper</u></a>)</p>
  </div>
</article>

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/4121880_orig.png" />
  </div>
  <div class="publication-card__body">
    <p><strong>We propose a simple yet effective password strength meter, fuzzyPSM,</strong> to give users reliable feedbacks when they select passwords. Inspired by a user survey on password practice, FuzzyPSM takes the ﬁrst step towards characterizing realistic user behaviors in password creation: Generally users do not build new passwords from scratch for a new service by combining segments of words, digits and/or symbols, instead they reuse or simply modify existing passwords for new services. (see more in <a href="{{ site.url }}{{ site.baseurl }}/researches/dsn16v9.pdf" target="_blank"><u>DSN'16 paper</u></a>)</p>
  </div>
</article>
</div>

### New two-factor authentication (2FA) schemes

<div class="publication-grid" markdown="0">

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/970052_orig.jpg" />
  </div>
  <div class="publication-card__body">
    <p>We propose a new 2FA scheme with provable security, and what we believe is most interesting is that superior security and privacy can be achieved at nearly no additional communication or computation cost. As far as we know, <strong>this work is the ﬁrst one that deﬁnes a formal model to capture the feature of user un-traceability</strong> and that highlights the damaging threat of de-synchronization attack on privacy-preserving two-factor authentication schemes. (see more in <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/infosci14.pdf" target="_blank"><u>INS'15 paper</u></a>)</p>
  </div>
</article>

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/3625851_orig.jpg" />
  </div>
  <div class="publication-card__body">
    <p><strong>We presented an  new 2FA scheme to cope with the various identiﬁed security defects without sacriﬁcing any desirable feature of Li et al.'s scheme.</strong> We conjecture that the strategy of only using symmetric-key techniques to achieve user anonymity is intrinsically infeasible, and pose its rigorous justiﬁcation as one interesting (and fundamental) open problem. (see more in <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/wcnc2014.pdf" target="_blank"><u>IEEE WCNC'14 paper</u></a>; <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/ieeesyst2015.pdf" target="_blank"><u>IEEE Systems Journal'16 paper</u></a>)</p>
  </div>
</article>
</div>

### Some principles for designing secure and privacy-preserving 2FA

<div class="publication-grid" markdown="0">

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/3349556.jpg" />
  </div>
  <div class="publication-card__body">
    <p><strong>Under the conditional non-tamper-resistance assumption of the smart cards, whether it is possible to construct a privacy-preserving two-factor authentication scheme by employing only light-weight symmetric cryptographic techniques, as most of the literature has done in the past?</strong> We give a negative answer to this question by empirically using two case studies and formally proving it in a widely accepted adversary model. (see more in <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/comnet14.pdf" target="_blank"><u>COMNET'14 paper</u></a>)</p>
  </div>
</article>

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/1824974.jpg" />
  </div>
  <div class="publication-card__body">
    <p><strong>In this work, we, for the first time, put forward three general principles that are vital for designing secure smart-card-based password authentication schemes: </strong> (i) public-key techniques are indispensable to resist against ofﬂine password guessing attack and to preserve user anonymity under the non-tamper resistance assumption of the smart card; (ii) there is an unavoidable trade-off when fulﬁlling the goals of local password update and resistance to smart card loss attack; and (iii) at least two exponentiation (respectively elliptic curve point multiplication) operations conducted on the server side are necessary for achieving forward secrecy. (see more in our <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/ijcs_online_version.pdf" target="_blank"><u>IJCS'14 ESI highly cited paper</u></a>)</p>
  </div>
</article>
</div>

### Investigations into the evaluation metrics for 2FA

<div class="publication-grid" markdown="0">

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/2532685.jpg" />
  </div>
  <div class="publication-card__body">
    <p>We further propose viable fixes and refinements to the state-of-the-art metric. The effectiveness of our refinements are tested by a comparative evaluation of 34 representative two-factor schemes. Particularly, <strong>we, for the ﬁrst time, provide a taxonomy of smart-card-loss attacks. </strong> We give a negative answer to this question by empirically using two case studies and formally proving it in a widely accepted adversary model. (see more in <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/asiaccs16v7.pdf" target="_blank"><u>ASIACCS'16 paper</u></a>; For a better metric and new scheme see our <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/ieeetdsc16_v11.pdf" target="_blank"><u>IEEE TDSC'16 paper</u></a>)</p>
  </div>
</article>

<article class="publication-card">
  <div class="publication-card__image">
    <img src="{{ site.url }}{{ site.baseurl }}/images/research/841544.jpg" />
  </div>
  <div class="publication-card__body">
    <p>Little attention has been given to the fundamental question: <strong>whether or not there are inherent limitations that prevent us from designing an “ideal” scheme that satisfies all the desirable goals?</strong> In this work, we aim to provide a deﬁnite answer to this question. (see more in our <a href="https://wangdingg.weebly.com/uploads/2/0/3/6/20366987/tdsc15.pdf" target="_blank"><u>IEEE TDSC'15 paper</u></a>)</p>
  </div>
</article>
</div>
