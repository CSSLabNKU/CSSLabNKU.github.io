---
title: "Password Policy"
layout: publications
excerpt: ""
sitemap: false
permalink: /password-policy/
---

<style>
  .password-policy-page {
    max-width: 920px;
    margin: 0 auto;
    line-height: 1.7;
  }

  .password-policy-page-title {
    margin: 0 0 1.5rem;
    text-align: left;
  }

  .password-policy-hero {
    display: grid;
    grid-template-columns: 504px 416px;
    width: 100%;
    min-height: 348px;
    margin: 0 auto 30px;
    border-top: 1px solid #d4d4d4;
    border-bottom: 1px solid #d4d4d4;
    background: #f6f6f6;
    box-sizing: border-box;
  }

  .password-policy-hero__visual {
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 14px 10px;
    background: #eee;
    box-sizing: border-box;
  }

  .password-policy-hero__visual img {
    display: block;
    width: 472px;
    max-width: 100%;
    height: auto;
    border: 6px solid #fff;
    box-sizing: border-box;
  }

  .password-policy-hero__copy {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 15px 25px;
    box-sizing: border-box;
  }

  .password-policy-hero__copy h2,
  .password-policy-hero__copy h3 {
    margin: 0;
    padding: 0;
    color: #5a5a5a;
    font-size: 32px;
    font-weight: normal;
    line-height: 1;
  }

  .password-policy-hero__quotes {
    margin: 0;
    padding: 20px 0;
    color: #868686;
    font-size: 16px;
    line-height: 1.4;
  }

  .password-policy-hero__button {
    align-self: flex-start;
    display: inline-block;
    min-height: 41px;
    padding: 0 22px;
    border: 1px solid #777;
    border-radius: 4px;
    color: #fff !important;
    background: linear-gradient(#aaa, #777);
    font-weight: 600;
    line-height: 41px;
    text-decoration: none !important;
    box-shadow: inset 0 1px 0 rgba(255, 255, 255, 0.35);
  }

  .password-policy-hero__button:hover {
    background: linear-gradient(#999, #666);
  }

  .password-policy-gallery {
    display: flex !important;
    flex-wrap: nowrap;
    gap: 30px;
    align-items: center;
    justify-content: center;
    margin: 10px 0;
  }

  .password-policy-gallery__item {
    display: flex;
    flex: 0 1 50%;
    align-items: center;
    min-width: 0;
  }

  .password-policy-gallery img,
  .password-policy-figure img {
    display: block;
    width: auto;
    max-width: 100%;
    height: auto;
  }

  .password-policy-gallery__item:first-child {
    justify-content: flex-end;
  }

  .password-policy-gallery__item:last-child {
    justify-content: center;
  }

  .password-policy-figure {
    margin: 20px 0;
  }

  .password-policy-figure--center {
    display: flex;
    width: 100%;
    justify-content: center;
  }

  .password-policy-figure--center img {
    margin: 0 !important;
  }

  .password-policy-figure--right img {
    margin-left: auto;
  }

  .password-policy-separator {
    margin: 20px 0;
  }

  .password-policy-separator hr {
    margin: 20px 0;
    border: 0;
    border-top: 1px solid #ddd;
  }

  .password-policy-caption {
    margin-top: 0.5rem;
    text-align: center;
  }

  .password-policy-intro {
    color: #8d2424;
    font-weight: normal;
  }

  .password-policy-emphasis {
    font-weight: 600;
    text-align: center;
  }

  .password-policy-arrow {
    margin: 0.5rem 0;
    text-align: center;
    line-height: 1.1;
  }

  @media (max-width: 920px) {
    .password-policy-hero {
      grid-template-columns: minmax(0, 55fr) minmax(0, 45fr);
    }
  }

  @media (max-width: 700px) {
    .password-policy-hero {
      grid-template-columns: 1fr;
    }

    .password-policy-gallery {
      flex-wrap: wrap;
    }

    .password-policy-gallery__item {
      flex-basis: 100%;
      justify-content: center !important;
    }

    .password-policy-hero__copy {
      padding: 24px;
    }

    .password-policy-hero__copy h2,
    .password-policy-hero__copy h3 {
      font-size: 20px;
      line-height: 1.15;
    }

    .password-policy-figure--right img {
      margin-right: auto;
    }
  }
</style>

<div class="password-policy-page" markdown="0">

<section class="password-policy-hero" aria-label="Password policy introduction">
  <div class="password-policy-hero__visual">
    <img src="{{ site.url }}{{ site.baseurl }}/images/1435750564.jpg" alt="A character saying that 12345 is the password on his luggage">
  </div>
  <div class="password-policy-hero__copy">
    <h3>Building sensible password policies for the emperor</h3>
    <p class="password-policy-hero__quotes">“Self-chosen passwords are often surprisingly easy to guess.” — Jerome H., Comm. ACM, 1974<br>“The only secure password is the one you can’t remember.” — Troy Hunt, Blog, 2011.<br>“Example of cyber resilience. Password policy too complex couldn't be bothered to comment on blog.” — A tweet by Gamingworks, June, 2015.</p>
    <a class="password-policy-hero__button" href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/esorics15conf0827.pdf" target="_blank" rel="noopener">Password policy: A real world problem</a>
  </div>
</section>

<div class="password-policy-gallery">
  <div class="password-policy-gallery__item">
    <img src="{{ site.url }}{{ site.baseurl }}/images/8854348_orig.png" alt="A humorous example of an easily guessed password">
  </div>
  <div class="password-policy-gallery__item">
    <img src="{{ site.url }}{{ site.baseurl }}/images/7762123_orig.png" alt="Worst passwords of 2015">
  </div>
</div>

<figure class="password-policy-figure password-policy-figure--center">
  <img src="{{ site.url }}{{ site.baseurl }}/images/1435760631.png" alt="A cartoon illustrating password composition rules">
</figure>

<div class="password-policy-separator" aria-hidden="true">
  <hr>
  <hr>
</div>

<figure class="password-policy-figure password-policy-figure--right">
  <img src="{{ site.url }}{{ site.baseurl }}/images/1461227899.png" alt="A sketch of the debates in password practice">
  <figcaption class="password-policy-caption">Figure 5. A sketch of the <span style="color: #da4444;">debates in password practice</span></figcaption>
</figure>

<p class="password-policy-intro">This is a big project encouraged by some wonderful reviewers and of my personal interest: it will be useful for the community and industry. It may take 3 year or 5 years to finish. Currently, I am performing related research (e.g., my <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/esorics16full_v9.pdf">ESORICS'15 paper</a></u> on password policies of 100+ leading sites, <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/ccs16_final_v12.pdf">ACM CCS'16 paper</a></u> on targeted online guessing threat, <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/asiaccs17_v12.pdf">ACM ASIACCS'17 paper</a></u> on human-chosen PINs and <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/ndss18v7.pdf">NDSS'18 paper</a></u> on password storage) and collecting related materials (e.g., evidence for over 30+ debates from the literature). Thanks for the great help from my team members. I am also grateful to many constructive feedbacks.</p>

<h3>1. The problems in the current password policies</h3>

<h4>1.1. A quote from the famous writer Geoffrey A. Landis</h4>

<p>“It has to have upper case, lower case, special characters, and at least one numeral. Also, spaces aren't allowed. It's not enough to come up with <em>a</em> secure password. You have to come up with a secure password that follows the arcane rules, different for each site, and you have to change it every 90 days. Then you have to do this fifty more times, because you probably log into at least fifty sites and the worst thing you can do is re-use a password.”</p>

<div class="password-policy-arrow" aria-hidden="true">||<br>∨</div>

<p class="password-policy-emphasis">High complexity + Not reuse + Frequent expiration = Not usable policy</p>

<h4>1.2. What users actually do?</h4>

<p class="password-policy-emphasis">Circumvent high complexity + highly re-use + recycling/write down = common user practice</p>

<p><span style="color: #8273da;">A user survey:</span></p>

<ul>
  <li><a href="http://www.sojump.com/jq/6443561.aspx">http://www.sojump.com/jq/6443561.aspx</a> (Chinese version)</li>
  <li><a href="http://www.sojump.com/jq/7005139.aspx">http://www.sojump.com/jq/7005139.aspx</a> (English version)</li>
</ul>

<p>So far, we have got 500+ effective responses. Thanks for your participation!</p>

<h4>1.3. The current crux</h4>

<p>Despite many pioneering works, there is still a lack of both theoretic and empirical academic exploration:</p>

<ul>
  <li>Threat <a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/long_pw_recovered.jpg">models</a></li>
  <li>Risk analysis</li>
  <li>Basic metrics</li>
  <li>Debates</li>
  <li>Fundamental issues</li>
  <li>A whole picture about the password ecosystem......</li>
</ul>

<h5>1.3.1. Known results</h5>

<ul>
  <li>Password strength metrics</li>
  <li>True strength of user passwords</li>
  <li>Password probability distribution function</li>
  <li>Rational user</li>
  <li>Password reuse behavior</li>
  <li>(Dis)advantages of password expiration</li>
  <li>Effects of specific password composition rule</li>
  <li>Effects of password strength meter</li>
</ul>

<h5>1.3.2. Unknown results</h5>

<ul>
  <li>User security budget</li>
  <li>Risks on the server</li>
  <li>Stochastic process of password evolution</li>
</ul>

<h3>2. Evidence-grounded recommendations</h3>

<h4>2.1. Recommendations for password composition rules</h4>

<h4>2.2. Sensible algorithms for password strength meters</h4>

<h4>2.3. Source codes for password strength meters</h4>

<p>Under constructing......</p>

</div>
