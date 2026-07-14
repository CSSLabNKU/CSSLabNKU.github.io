---
title: "FuzzyVerifier - Welcome to Ding Wang's Homepage -- Password Cryptography"
layout: publications
excerpt: ""
sitemap: false
permalink: /fuzzyverifier/
---

<style>
  .fuzzyverifier-page {
    line-height: 1.7;
  }

  .fuzzyverifier-page h2 {
    margin-top: 38px;
    padding-bottom: 8px;
    border-bottom: 1px solid #e2e2e2;
  }

  .fuzzyverifier-page h3 {
    margin-top: 28px;
  }

  .fuzzyverifier-hero {
    width: 100%;
    margin: 0 0 28px;
    overflow: hidden;
    border: 1px solid #e2e2e2;
    border-radius: 4px;
    background: #fff;
  }

  .fuzzyverifier-hero img {
    display: block;
    width: 100%;
    height: auto;
    margin: 0;
    border-radius: 0;
  }

  .fuzzyverifier-callout {
    margin: 22px 0;
    padding: 16px 18px;
    border-left: 4px solid #6555c2;
    border-radius: 3px;
    background: #f7f5fc;
  }

  .fuzzyverifier-summary {
    width: 100%;
    margin: 18px 0 24px;
    border-collapse: collapse;
    font-size: 0.92em;
  }

  .fuzzyverifier-summary th,
  .fuzzyverifier-summary td {
    padding: 10px 12px;
    border: 1px solid #ddd;
    text-align: left;
    vertical-align: top;
  }

  .fuzzyverifier-summary th {
    background: #f7f7f7;
  }

  .fuzzyverifier-downloads {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    margin-top: 12px;
  }

  .fuzzyverifier-downloads a {
    display: inline-block;
    min-width: 58px;
    padding: 5px 9px;
    border: 1px solid #ddd;
    border-radius: 3px;
    background: #fafafa;
    text-align: center;
    text-decoration: none;
  }

  .fuzzyverifier-downloads a:hover,
  .fuzzyverifier-downloads a:focus {
    border-color: #6555c2;
    color: #5040ae;
  }

  @media (max-width: 767px) {
    .fuzzyverifier-summary {
      display: block;
      overflow-x: auto;
    }
  }
</style>

<div class="fuzzyverifier-page" markdown="1">

<figure class="fuzzyverifier-hero">
  <img src="{{ site.url }}{{ site.baseurl }}/images/1399478294.jpg" alt="Password-change problem in smart-card-based authentication and the proposed fuzzy verifier solution">
</figure>

# Fuzzy Verifier

**Related paper:** Ding Wang, Debiao He, Ping Wang, and Chao-Hsien Chu, “Two Birds with One Stone: Two-Factor Authentication with Security Beyond Conventional Bound.”

[Main paper]({{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/ieeetdsc16_v11.pdf) · [Appendix]({{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/tdsc16_suppl0820.pdf)

<div class="fuzzyverifier-callout" markdown="1">

**Ethics considerations.** The two password datasets used in this study—32.58 million RockYou passwords and 6.43 million CSDN passwords—had already been publicly disclosed and had been used collectively by a number of scientific studies. Using leaked passwords nevertheless presents an ethical concern. We use the datasets without identifiable information such as usernames or email addresses and only for scientific purposes, including training and testing guessing algorithms to evaluate attackers’ capabilities. Because attackers are also likely to use these datasets as training sets or cracking dictionaries, studying them can provide practically relevant guidance to security administrators and users.

</div>

## Method

The fuzzy verifier addresses the tension between usability and two-factor security when a smart card may be compromised. Instead of storing the full verifier `h(PW_i)` in card memory, the method stores:

```text
h(PW_i) mod N
```

Here, `PW_i` is user `U_i`’s password, `h()` is a hash function (SHA-1 in the original experiments), and `N` is a balance factor such as 256. This construction allows a user to change a password locally while limiting the information exposed by a compromised card.

Under a uniform password-space assumption, the probability of a successful adversarial guess is approximately `256t/D`, where `D` is the password space and `t` is the number of online attempts. Online guessing can additionally be constrained by account lockout or probabilistic throttling.

Real password distributions are not uniform, however. To evaluate the method under realistic distribution bias, the study uses four subsets drawn from the RockYou and CSDN datasets:

1. The top 1 million RockYou passwords.
2. The top 1 million CSDN passwords.
3. The top 2 million RockYou passwords.
4. The top 2 million CSDN passwords.

Passwords are assigned to one of 256 pools according to `h(PW) mod 256`. For example, because the SHA-1 value of `123456` is congruent to 27 modulo 256, it belongs to `POOL27`.

For each pool, the study calculates the expected number of guesses required by an optimal online attacker. This value is referred to as *guesswork* or *guessing entropy*. If a pool contains `x` password entries with probabilities `P₁ ≥ P₂ ≥ ... ≥ Pₓ`, its guessing entropy is:

```text
E = 1 × P₁ + 2 × P₂ + ... + x × Pₓ
```

A value greater than 1,024 meets the target used in the original study: the success probability of a single online guess is no greater than `1/1024`.

## Experimental results

<table class="fuzzyverifier-summary">
  <thead>
    <tr>
      <th>Experiment</th>
      <th>Passwords</th>
      <th>Pool size</th>
      <th>Guessing entropy</th>
      <th>Result</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Top 1 million RockYou</td>
      <td>3,739–4,141</td>
      <td>111.300–750.603</td>
      <td>Does not meet the 1,024 threshold.</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Top 1 million CSDN</td>
      <td>3,756–4,079</td>
      <td>39.799–1,122.18</td>
      <td>Most pools remain below the threshold.</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Top 2 million RockYou</td>
      <td>7,612–8,018</td>
      <td>247.935–1,418.31</td>
      <td>About 16% of pools remain below the threshold.</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Top 2 million CSDN</td>
      <td>7,584–8,146</td>
      <td>127.743–2,600.56</td>
      <td>Only about 2.34% of pools remain below the threshold.</td>
    </tr>
  </tbody>
</table>

### Experiment 1: Top 1 million RockYou passwords

The 256 pools contain between 3,739 and 4,141 passwords. Guessing entropy ranges from 111.300 to 750.603, so the experiment does not guarantee that every pool limits a single online guess to a success probability of at most `1/1024`.

### Experiment 2: Top 1 million CSDN passwords

The pools contain between 3,756 and 4,079 passwords. Guessing entropy ranges from 39.799 to 1,122.18, with most pools below 1,024. This dataset therefore does not meet the target for every pool.

### Experiment 3: Top 2 million RockYou passwords

The pools contain between 7,612 and 8,018 passwords. Guessing entropy ranges from 247.935 to 1,418.31. Approximately 16% of the pools remain below 1,024, so this dataset also fails to meet the target for every pool.

### Experiment 4: Top 2 million CSDN passwords

The pools contain between 7,584 and 8,146 passwords. Guessing entropy ranges from 127.743 to 2,600.56, and only about 2.34% of pools fall below 1,024. The six pools identified below are the exceptions:

- `POOL13`: 149.431
- `POOL65`: 127.743
- `POOL139`: 652.968
- `POOL146`: 973.749
- `POOL180`: 528.102
- `POOL184`: 343.376

The original study observes that excluding a single highly vulnerable password from each of these pools—for example, by enforcing a small blacklist—raises the guessing entropy of every pool above 1,024.

## Available pool data

Due to storage constraints, only a subset of the 256 pool files is provided. Each text file contains detailed information for the corresponding pool. A machine-readable list is also available in [download_urls.txt]({{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/download_urls.txt).

<div class="fuzzyverifier-downloads">
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/0.txt">0.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/1.txt">1.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/2.txt">2.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/3.txt">3.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/4.txt">4.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/5.txt">5.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/6.txt">6.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/7.txt">7.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/8.txt">8.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/9.txt">9.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/10.txt">10.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/11.txt">11.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/12.txt">12.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/13.txt">13.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/14.txt">14.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/15.txt">15.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/16.txt">16.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/17.txt">17.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/18.txt">18.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/19.txt">19.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/20.txt">20.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/21.txt">21.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/22.txt">22.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/23.txt">23.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/24.txt">24.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/25.txt">25.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/26.txt">26.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/27.txt">27.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/28.txt">28.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/29.txt">29.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/30.txt">30.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/31.txt">31.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/32.txt">32.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/33.txt">33.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/34.txt">34.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/35.txt">35.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/36.txt">36.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/37.txt">37.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/38.txt">38.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/39.txt">39.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/40.txt">40.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/64.txt">64.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/72.txt">72.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/74.txt">74.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/88.txt">88.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/100.txt">100.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/106.txt">106.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/123.txt">123.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/144.txt">144.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/157.txt">157.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/199.txt">199.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/204.txt">204.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/206.txt">206.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/228.txt">228.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/238.txt">238.txt</a>
  <a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/252.txt">252.txt</a>
</div>

## Subtleties revealed by the experiments

The experiments indicate that the size of the underlying password space must be sufficiently large to provide the target security level. Dataset composition also matters: the top 2 million CSDN passwords produce substantially stronger pools than the top 2 million RockYou passwords.

The difference may partly reflect their password-creation policies. RockYou required passwords of at least five characters, whereas CSDN required at least six. The services also had different user populations and use cases. RockYou passwords protected social-networking accounts used largely by non-professionals, while CSDN passwords protected technical notes and blogs used mainly by programmers.

Overall, the experiments demonstrate that a real-world password dataset can satisfy the specified security target and support the feasibility of the fuzzy verifier approach.

## Acknowledgements

We acknowledge the contributions of Dr. Chen Zhu and Qianchen Gu to the password-statistics software used in this study. We are also grateful to Dr. Haibo Chen for constructive suggestions.

## References

1. M. Dell’Amico, P. Michiardi, and Y. Roudier, “Password strength: An empirical analysis,” in *Proceedings of IEEE INFOCOM*, 2010, pp. 1–9.
2. J. Bonneau, “The science of guessing: Analyzing an anonymized corpus of 70 million passwords,” in *Proceedings of the IEEE Symposium on Security and Privacy*, 2012, pp. 538–552.
3. W. Burr, D. Dodson, R. Perlner, W. Polk, S. Gupta, and E. Nabbus, *NIST SP 800-63-2: Electronic Authentication Guideline*, National Institute of Standards and Technology, August 2013.
4. C. Allan, “32 million RockYou passwords stolen,” December 2009.
5. Dazzlepod Inc., “CSDN 6 million cleartext passwords,” March 2013.
6. J. L. Massey, “Guessing and entropy,” in *Proceedings of the 1994 IEEE International Symposium on Information Theory*, 1994, pp. 204–208.
7. A. Das, J. Bonneau, M. Caesar, N. Borisov, and X. Wang, “The tangled web of password reuse,” in *Proceedings of NDSS*, 2014.
8. D. Florêncio and C. Herley, “A large-scale study of web password habits,” in *Proceedings of WWW*, 2007, pp. 657–666.
9. M. Alsaleh, M. Mannan, and P. C. van Oorschot, “Revisiting defenses against large-scale online password guessing attacks,” *IEEE Transactions on Dependable and Secure Computing*, vol. 9, no. 1, pp. 128–141, 2012.

</div>
