---
title: "Password Policy - Welcome to Ding Wang's Homepage -- Password Cryptography"
layout: publications
excerpt: ""
sitemap: false
permalink: /passwordpolicy/
---

<style>
  .password-policy-gallery {
    display: grid;
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 24px;
    align-items: center;
    margin: 1rem 0;
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
    margin: 1.5rem 0;
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

  .password-policy-intro {
    color: #8d2424;
    font-weight: normal;
  }

  .password-policy-caption {
    margin-top: 0.5rem;
    text-align: center;
  }

  @media (max-width: 700px) {
    .password-policy-gallery {
      grid-template-columns: 1fr;
    }

    .password-policy-gallery img:first-child,
    .password-policy-gallery img:last-child {
      justify-self: center;
    }
  }
</style>

<div class="password-policy-gallery">
  <img src="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/8854348_orig.png" alt="Password policy overview">
  <img src="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/7762123.png" alt="Password policy illustration">
</div>

<figure class="password-policy-figure password-policy-figure--center">
  <img src="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/1435760631.png" alt="Password policy research framework">
</figure>

<div class="password-policy-separator" aria-hidden="true">
  <hr>
  <hr>
</div>

<figure class="password-policy-figure password-policy-figure--right">
  <img src="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/1461227899.png" alt="A sketch of the debates in password practice">
  <figcaption class="password-policy-caption">Figure 5. A sketch of the <span style="color: #da4444;">debates in password practice</span></figcaption>
</figure>

<p class="password-policy-intro">This is a big project encouraged by some wonderful reviewers and of my personal interest: it will be useful for the community and industry. It may take 3 year or 5 years to finish. Currently, I am performing related research (e.g., my <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/esorics16full_v9.pdf">ESORICS'15 paper</a></u> on password policies of 100+ leading sites, <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/ccs16_final_v12.pdf">ACM CCS'16 paper</a></u> on targeted online guessing threat, <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/asiaccs17_v12.pdf">ACM ASIACCS'17 paper</a></u> on human-chosen PINs and <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/ndss18v7.pdf">NDSS'18 paper</a></u> on password storage) and collecting related materials (e.g., evidence for over 30+ debates from the literature). Thanks for the great help from my team members. I am also grateful to many constructive feedbacks.</p>

## 1. The problems in the current password policies

### 1.1. A quote from the famous writer Geoffrey A. Landis

> “It has to have upper case, lower case, special characters, and at least one numeral. Also, spaces aren't allowed. It's not enough to come up with *a* secure password. You have to come up with a secure password that follows the arcane rules, different for each site, and you have to change it every 90 days. Then you have to do this fifty more times, because you probably log into at least fifty sites and the worst thing you can do is re-use a password.”

High complexity + Not reuse + Frequent expiration = Not usable policy

### 1.2. What users actually do?

Circumvent high complexity + highly re-use + recycling/write down = common user practice

<span style="color: #8273da;">A user survey:</span>

- [http://www.sojump.com/jq/6443561.aspx](http://www.sojump.com/jq/6443561.aspx) (Chinese version)
- [http://www.sojump.com/jq/7005139.aspx](http://www.sojump.com/jq/7005139.aspx) (English version)

So far, we have got 500+ effective responses. Thanks for your participation!

### 1.3. The current crux

Despite many pioneering works, there is still a lack of both theoretic and empirical academic exploration:

- Threat [models]({{ site.url }}{{ site.baseurl }}/uploads/passwordpolicy/long_pw_recovered.jpg)
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
