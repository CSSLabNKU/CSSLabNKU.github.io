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

  .password-policy-hero__copy h2 {
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
    font-size: 1.1em;
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
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 30px;
    align-items: center;
    margin: 10px 0;
  }

  .password-policy-gallery img,
  .password-policy-figure img {
    display: block;
    width: auto;
    max-width: 100%;
    height: auto;
  }

  .password-policy-gallery img:first-child {
    justify-self: end;
  }

  .password-policy-gallery img:last-child {
    justify-self: center;
  }

  .password-policy-figure {
    margin: 20px 0;
  }

  .password-policy-figure--center img {
    margin: 0 auto;
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
    .password-policy-hero,
    .password-policy-gallery {
      grid-template-columns: 1fr;
    }

    .password-policy-hero__copy {
      padding: 24px;
    }

    .password-policy-hero__copy h2 {
      font-size: 26px;
      line-height: 1.15;
    }

    .password-policy-gallery img:first-child,
    .password-policy-gallery img:last-child {
      justify-self: center;
    }

    .password-policy-figure--right img {
      margin-right: auto;
    }
  }
</style>

<div class="password-policy-page" markdown="1">

<section class="password-policy-hero" aria-label="Password policy introduction">
  <div class="password-policy-hero__visual">
    <img src="{{ '/images/1435750564.jpg' | relative_url }}" alt="A character saying that 12345 is the password on his luggage">
  </div>
  <div class="password-policy-hero__copy">
    <h2>Building sensible password policies for the emperor</h2>
    <p class="password-policy-hero__quotes">“Self-chosen passwords are often surprisingly easy to guess.” — Jerome H., Comm. ACM, 1974<br><br>“The only secure password is the one you can’t remember.” — Troy Hunt, Blog, 2011.<br><br>“Example of cyber resilience. Password policy too complex couldn't be bothered to comment on blog.” — A tweet by Gamingworks, June, 2015.</p>
    <a class="password-policy-hero__button" href="{{ '/uploads/passwordpolicy/esorics15conf0827.pdf' | relative_url }}" target="_blank" rel="noopener">Password policy: A real world problem</a>
  </div>
</section>

<div class="password-policy-gallery">
  <img src="{{ '/images/8854348_orig.png' | relative_url }}" alt="A humorous example of an easily guessed password">
  <img src="{{ '/images/7762123_orig.png' | relative_url }}" alt="Worst passwords of 2015">
</div>

<figure class="password-policy-figure password-policy-figure--center">
  <img src="{{ '/images/1435760631.png' | relative_url }}" alt="A cartoon illustrating password composition rules">
</figure>

<div class="password-policy-separator" aria-hidden="true">
  <hr>
  <hr>
</div>

<figure class="password-policy-figure password-policy-figure--right">
  <img src="{{ '/images/1461227899.png' | relative_url }}" alt="A sketch of the debates in password practice">
  <figcaption class="password-policy-caption">Figure 5. A sketch of the <span style="color: #da4444;">debates in password practice</span></figcaption>
</figure>

<p class="password-policy-intro">This is a big project encouraged by some wonderful reviewers and of my personal interest: it will be useful for the community and industry. It may take 3 year or 5 years to finish. Currently, I am performing related research (e.g., my <u><a href="{{ '/uploads/passwordpolicy/esorics16full_v9.pdf' | relative_url }}">ESORICS'15 paper</a></u> on password policies of 100+ leading sites, <u><a href="{{ '/uploads/passwordpolicy/ccs16_final_v12.pdf' | relative_url }}">ACM CCS'16 paper</a></u> on targeted online guessing threat, <u><a href="{{ '/uploads/passwordpolicy/asiaccs17_v12.pdf' | relative_url }}">ACM ASIACCS'17 paper</a></u> on human-chosen PINs and <u><a href="{{ '/uploads/passwordpolicy/ndss18v7.pdf' | relative_url }}">NDSS'18 paper</a></u> on password storage) and collecting related materials (e.g., evidence for over 30+ debates from the literature). Thanks for the great help from my team members. I am also grateful to many constructive feedbacks.</p>

## 1. The problems in the current password policies

### 1.1. A quote from the famous writer Geoffrey A. Landis

“It has to have upper case, lower case, special characters, and at least one numeral. Also, spaces aren't allowed. It's not enough to come up with *a* secure password. You have to come up with a secure password that follows the arcane rules, different for each site, and you have to change it every 90 days. Then you have to do this fifty more times, because you probably log into at least fifty sites and the worst thing you can do is re-use a password.”

<div class="password-policy-arrow" aria-hidden="true">||<br>∨</div>

<p class="password-policy-emphasis">High complexity + Not reuse + Frequent expiration = Not usable policy</p>

### 1.2. What users actually do?

<p class="password-policy-emphasis">Circumvent high complexity + highly re-use + recycling/write down = common user practice</p>

<span style="color: #8273da;">A user survey:</span>

- [http://www.sojump.com/jq/6443561.aspx](http://www.sojump.com/jq/6443561.aspx) (Chinese version)
- [http://www.sojump.com/jq/7005139.aspx](http://www.sojump.com/jq/7005139.aspx) (English version)

So far, we have got 500+ effective responses. Thanks for your participation!

### 1.3. The current crux

Despite many pioneering works, there is still a lack of both theoretic and empirical academic exploration:

- Threat [models]({{ '/uploads/passwordpolicy/long_pw_recovered.jpg' | relative_url }})
- Risk analysis
- Basic metrics
- Debates
- Fundamental issues
- A whole picture about the password ecosystem......

#### 1.3.1. Known results

- Password strength metrics
- True strength of user passwords
- Password probability distribution function
- Rational user
- Password reuse behavior
- (Dis)advantages of password expiration
- Effects of specific password composition rule
- Effects of password strength meter

#### 1.3.2. Unknown results

- User security budget
- Risks on the server
- Stochastic process of password evolution

## 2. Evidence-grounded recommendations

### 2.1. Recommendations for password composition rules

### 2.2. Sensible algorithms for password strength meters

### 2.3. Source codes for password strength meters

Under constructing......

</div>
