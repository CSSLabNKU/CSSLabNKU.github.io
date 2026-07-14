---
title: "FuzzyVerifier - Welcome to Ding Wang's Homepage -- Password Cryptography"
layout: publications
excerpt: ""
sitemap: false
permalink: /fuzzyverifier/
---

<style>
  .fuzzyverifier-archive {
    color: #2a2a2a;
    font-family: "Crimson Text", Georgia, serif;
    line-height: 1.5;
  }

  .fuzzyverifier-hero {
    width: 100%;
    margin: 0 0 26px;
    overflow: hidden;
    background: #fff;
  }

  .fuzzyverifier-hero img {
    display: block;
    width: 100%;
    height: auto;
    margin: 0;
    border-radius: 0;
  }

  .fuzzyverifier-archive .wsite-content-title {
    margin: 18px 0;
    color: #2a2a2a;
    font-weight: 600;
    line-height: 1.35;
  }

  .fuzzyverifier-related-paper {
    display: flex;
    flex-wrap: wrap;
    align-items: baseline;
    gap: 0 10px;
    margin: 18px 0;
    font-size: 14px;
    line-height: 1.5;
  }

  .fuzzyverifier-related-paper strong {
    font-size: 16px;
  }

  .fuzzyverifier-archive .paragraph {
    margin: 0;
    color: #2a2a2a;
  }

  .fuzzyverifier-archive .styled-hr {
    height: 1px;
    margin: 0;
    border: 0;
    background: #ddd;
  }

  .fuzzyverifier-archive .wsite-multicol-table {
    width: 100%;
    border-collapse: collapse;
    table-layout: fixed;
  }

  .fuzzyverifier-archive .wsite-multicol-col {
    vertical-align: top;
  }

  .fuzzyverifier-archive a {
    color: inherit;
  }

  @media (max-width: 767px) {
    .fuzzyverifier-archive {
      overflow-x: auto;
    }

    .fuzzyverifier-archive .wsite-multicol-table {
      min-width: 760px;
    }
  }
</style>

<figure class="fuzzyverifier-hero">
  <img src="{{ site.url }}{{ site.baseurl }}/images/1399478294.jpg" alt="Password-change problem in smart-card-based authentication and the proposed fuzzy verifier solution">
</figure>

<div class="fuzzyverifier-archive">
<div class="fuzzyverifier-related-paper"><strong color="#5a5a5a">Related paper:</strong> Two Birds with One Stone: Two-Factor Authentication with Security Beyond Conventional Bound <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/ieeetdsc16_v11.pdf">Main.pdf</a></u> <u><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/tdsc16_suppl0820.pdf">Appendix.pdf</a></u></div>
<hr class="styled-hr" style="width:100%;"/>

<div class="paragraph" style="text-align:left;"><strong color="#350df8">Ethics considerations:  </strong>Though the two password datasets (32.58 million Rockyou, 6.43 million CSDN) herein have been publicly disclosed and collectively used by a number of scientific works that study passwords (see the proceedings of IEEE S&amp;P 2012, ACM CCS 2013, ISOC NDSS 2014, etc.), this nevertheless creates an ethical conundrum: Should our research use passwords leaked publicly? Since this data has already been made public and is easily available, using it in our research does not increase the harm to the victims. We use these passwords (without any identifiable information such as user name, email) only for scientific use (e.g., train and test guessing algorithms to evaluate attackers' capabilities.). Furthermore, as attackers are likely to use these password sets as training sets or cracking dictionaries, our use of them to evaluate password strength implies our results are more likely to be of practical relevance to security administrators and common users.<br/></div>
<hr class="styled-hr" style="width:100%;"/>

<div class="paragraph" style="text-align:left;"><strong>Fuzzy Verifier: </strong>To overcome the dilemma of maintaining usability while achieving two-factor security even the smart card can be tampered, here we propose a tradeoff between security and usability: Instead of storing {h(PWi)} in the card memory, we store {h(PWi) mod N}, where PWi stands for user Ui's password, h() is a Hash function (e.g., SHA-1 in the following experiments), and N the balance factor (a moderate integer, e.g. N=256). Then, user Ui can change her password locally, yet this user-friendliness comes at the prices of security: the chances of an adversary to guess Ui's password is roughly 256t/D, where D is the password space from which each user's password is uniformed drawn and t is the number of adversary's online attempts. Generally, D is moderately limited, e.g., |D|=1000,000 [1,2]. That's to say, the modified protocol using this new method is able to meet the Level 1 security of NIST SP800-63-2 [3] even if the smart card has been compromised, which <b>guarantees that the success probability of one online guessing attempt by the adversary is no more than 1/1024</b>.As is well known, online guessing can be effectively thwarted by locking the account after several failed login attempts or by only allowing a probabilistic number of failed guesses [9].In two other cases, the security is improved: (1) the chances of an adversary to change Ui's password is 1/256; (2) the chances of Ui to accidentally make the card unusable is 1/256 when inputs an unintended new password in the password change phase, reduced to 1/65536 if users are required to type the new password twice.<br/>In the above analysis, the value of 256t/D is obtained on the basis of the assumption that, user passwords are uniformly distributed. However, in practice, this is generally not the case——user passwords have strong bias towards similarity! This can be evidenced by the following statistics. <b>For example, the top 20 most popular passwords from Rockyou dataset [4] account for 2.54% of the entire set. To evaluate the practical effectiveness of our proposed ``fuzzy verifier'' when user password space is greatly biased, </b>we use four real-life publicly available password datasets(i.e., top 1 million most popular passwords from 32 million Rockyou dataset, top 2 million most popular passwords from 32 million Rockyou dataset, top 1 million most popular passwords from 6.43 million CSDN dataset [5], top 1 million most popular passwords from 6.43 million CSDN) to carry out the following two explorations:<br/>
(<b>1</b>) How many passwords in D fall into the same password pool with PWi? As a complement, we say PWj falls into the same pool with PWi only if the value of <u style="color:rgb(134, 134, 134)">h(PWj) mod 256</u> equals h(PWi) mod 256. We say the resulting password pool is POOLi.<br/>(<b>2</b>) How many password finally remained if we remove these passwords from POOLi that are unlikely to be Ui's password PWi? Without any specific information about Ui's personal information (e.g., hobbies, name, birthday), it is really difficult (probably impossible) to accurately define what's the character(s) that are unlikely to be hold by Ui's password PWi. As a result, we can only use the statistical information of POOLi to detect whether there is any abnormality. An effective metric is the expected number of guesses required to find any password in POOLi if the attacker proceeds an optimal online attack (i.e., testing the most likely passwords first), known as guesswork or guessing entropy [2,6].<br/>
Admittedly, we have obtained two large dataset with user ID and password, yet such information is definitively sensitive, and may cause subtle sufferings to victims if such dataset are illustrated publicly, for users tend to reuse their IDs and passwords [7,8]. As far as we know, using guessing entropy to characterize a password dataset is currently the best strategy that can be adopted while corresponding user-specific information is unavailable (or cannot be appropriately used). Assume password pool POOLi includes <em>x</em> entries. Each of the entry is of the &lt;Password, Count, Popularity&gt; form, see POOL0 of the top 2 million CSDN dataset <u>0.txt</u>. Note that, the term "Count" stands for the popular count of the corresponding password. For example, if the password "shanshan" occurs 210 times in the entire 6 million CSDN dataset, we say the popular count of password "shanshan" is 210. The "Popularity" of password "shanshan" is 210/(total count in the current pool)=210/13262=0.0158347. For simplicity, we denote the popularities of each password pool in decreasing order P1, P2, P3, ...... P<em>x</em>. <br/>
Accordingly, we can determine the <b>guessing entropy</b> [2] of POOL0 by computing <em>E=</em>1 <em>* </em>P1 + 2 * P2 + 3 * P3 + ... + <em>x</em> * P<em>x</em> = 2492.49, which is larger than 1024. This means POOL0 is a valid pool, and the success probability of one online guessing attempt using password candidates in POOL0 by the adversary is 1/2492.49, no more than 1/1024. <br/>
<b>Our empirical results demonstrate that the distribution bias of password space D does not significantly degrade our proposed method, and it ensures the Level 1 security of NIST SP800-63-2.</b></div>
<hr class="styled-hr" style="width:100%;"/>

<div class="paragraph" style="text-align:left;"><strong><span style="color:#350df8">Experimental 1.</span> Results from top 1 million most popular passwords of Rockyou dataset</strong><br/>
Note: Since <u>h(123456) mod 256</u> = <u>(7C4A8D09CA3762AF61E59520943DC26494F8941B) mod 256</u> = <u>27</u>, the password pool of 123456 is denoted by 27.txt
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:12%; padding:0 15px;">
<div class="paragraph" style="text-align:left;">
<strong>Rank<br/>(top 20)</strong><br/>
1<br/>
2<br/>
3<br/>
4<br/>
5<br/>
6<br/>
7<br/>
8<br/>
9<br/>
10<br/>
11<br/>
12<br/>
13<br/>
14<br/>
15<br/>
16<br/>
17<br/>
18<br/>
19<br/>
20
</div>
</td> <td class="wsite-multicol-col" style="width:92%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:12.857142857143%; padding:0 15px;">
<div class="paragraph" style="text-align:justify;"><strong>Password</strong><br/><br/>
123456<br/>
12345<br/>
123456789<br/>
Password<br/>
iloveyou<br/>
princess
rockyou<br/>
1234567
12345678<br/>
abc123<br/>
Nicole<br/>
Daniel<br/>
babygirl<br/>
monkey<br/>
Jessica<br/>
Lovely<br/>
michael<br/>
Ashley<br/>
654321
Qwerty
</div>
</td> <td class="wsite-multicol-col" style="width:95%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:23.106927937363%; padding:0 15px;">
<div class="paragraph" style="text-align:left;"><strong>Total counts of passwords</strong><br/>
290731<br/>
79078<br/>
76790<br/>
61958<br/>
51622<br/>
35231<br/>
22588<br/>
21726<br/>
20553<br/>
17542<br/>
17168<br/>
16409<br/>
16094<br/>
15294<br/>
15162<br/>
14950<br/>
14898<br/>
14329<br/>
13984<br/>
13856
</div>
</td>
<td class="wsite-multicol-col" style="width:76%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:72.043010752688%; padding:0 15px;">
<div class="paragraph" style="text-align:left;"><strong>Hash value of the password (SHA-1)</strong><br/><br/>
7C4A8D09CA3762AF61E59520943DC26494F8941B<br/>
8CB2237D0679CA88DB6464EAC60DA96345513964<br/>
F7C3BC1D808E04732ADF679965CCC34CA7AE3448<br/>
8BE3C943B1609FFFBFC51AAD666D0A04ADF83C9D<br/>
EE8D8728F435FD550F83852AABAB5234CE1DA528<br/>
775BB961B81DA1CA49217A48E533C832C337154A<br/>
F1CF651CE1A2191A760C0B2F161234F7958E26E4<br/>
20EABE5D64B0E216796E834F52D61FD0B70332FC<br/>
7C222FB2927D828AF22F592134E8932480637C0D<br/>
6367C48DD193D56EA7B0BAAD25B19455E529F5EE<br/>
17305A2F2AED9D58C73FB12AD27831799DE28B90<br/>
7B37259E149636E3330D530CBF408F2B8C1EDA6A<br/>
B03B74363BBB6EE42CE248C7A5344E92FFE76CC7<br/>
AB87D24BDC7452E55738DEB5F868E1F16DEA5ACE<br/>
15D834B328BB637EEEF49B6624774BDED566B659<br/>
2B791F512C4F94B43153DA78FD70066BEE61D27B<br/>
17B9E1C64588C7FA6419B4D29DC1F4426279BA01<br/>
0B2D293306511D90B3A9F23424FB9836760018CC<br/>
DD5FEF9C1C1DA1394D6D34B248C51BE2AD740840<br/>
36810ED90AA5DE17CBC1B471B999EC6B53B7C602
</div>
</td>
<td class="wsite-multicol-col" style="width:28%; padding:0 15px;">
<div class="paragraph" style="text-align:left;"><strong>Password Pool</strong><br/><br/>
<u>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/27.txt" style="color: rgb(30, 42, 241);" title="">27.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/100.txt" style="color: rgb(30, 42, 241);" title="">100.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/72.txt" style="color: rgb(30, 42, 241);" title="">72.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/157.txt" style="color: rgb(30, 42, 241);" title="">157.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/40.txt" style="color: rgb(30, 42, 241);" title="">40.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/74.txt" style="color: rgb(30, 42, 241);" title="">74.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/228.txt" style="color: rgb(30, 42, 241);" title="">228.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/252.txt" style="color: rgb(30, 42, 241);" title="">252.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/13.txt" style="color: rgb(30, 42, 241);" title="">13.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/238.txt" style="color: rgb(30, 42, 241);" title="">238.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/144.txt" style="color: rgb(30, 42, 241);" title="">144.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/106.txt" style="color: rgb(30, 42, 241);" title="">106.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/199.txt" style="color: rgb(30, 42, 241);" title="">199.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/206.txt" style="color: rgb(30, 42, 241);" title="">206.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/88.txt" style="color: rgb(30, 42, 241);" title="">88.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/123.txt" style="color: rgb(30, 42, 241);" title="">123.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/1.txt" style="color: rgb(30, 42, 241);" title="">1.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/204.txt" style="color: rgb(30, 42, 241);" title="">204.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/64.txt" style="color: rgb(30, 42, 241);" title="">64.txt</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/2.txt" style="color: rgb(30, 42, 241);" title="">2.txt</a><br/>
</u>
<br/>
</div>
</td></tr>
</tbody>
</table>
</div></div></div>
</td> <td class="wsite-multicol-col" style="width:0.21647143419566%; padding:0 15px;">
</td> <td class="wsite-multicol-col" style="width:1.1293991086812%; padding:0 15px;">
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> </tr>
</tbody>
</table>
</div></div></div>
<div class="paragraph" style="text-align:left;"><strong>Guessing entropy computed from top 1 million most popular passwords of Rockyou dataset </strong></div>
<div class="paragraph" style="text-align:left;">(1) The minimum password number of the 256 password pools is 3739, and the maximum is 4141;<br/>
(2) The minimum guessing expectation (entropy) of the 256 password pools is 111.300, and the maximum is 750.603, which <b>fails to guarantee</b> that the success probability of one online guessing attempt using password candidate in any pool by the adversary is no more than 1/1024. <br/>
(3) Due to storage space constraints of this site, we only upload 10% of the password pool files.
</div>
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:47.090517241379%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:41.975308641975%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Password Pool<br/>(0~255)</strong><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/0.txt" title="">0</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/1.txt" title="">1</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/2.txt" title="">2</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/3.txt" title="">3</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/4.txt" title="">4</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/5.txt" title="">5</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/6.txt" title="">6</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/7.txt" title="">7</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/8.txt" title="">8</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/9.txt" title="">9</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/10.txt" title="">10</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/11.txt" title="">11</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/12.txt" title="">12</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/13.txt" title="">13</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/14.txt" title="">14</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/15.txt" title="">15</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/16.txt" title="">16</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/17.txt" title="">17</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/18.txt" title="">18</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/19.txt" title="">19</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/20.txt" title="">20</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/21.txt" title="">21</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/22.txt" title="">22</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/23.txt" title="">23</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/24.txt" title="">24</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/25.txt" title="">25</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/26.txt" title="">26</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/27.txt" title="">27</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/28.txt" title="">28</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/29.txt" title="">29</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/30.txt" title="">30</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/31.txt" title="">31</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/32.txt" title="">32</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/33.txt" title="">33</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/34.txt" title="">34</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/35.txt" title="">35</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/36.txt" title="">36</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/37.txt" title="">37</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/38.txt" title="">38</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/39.txt" title="">39</a><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/40.txt" title="">40</a><br/>
41<br/>42<br/>43<br/>44<br/>45<br/>46<br/>47<br/>48<br/>49<br/>50<br/>51<br/>52<br/>53<br/>54<br/>55<br/>56<br/>57<br/>58<br/>59<br/>60<br/>61<br/>62<br/>63<br/>64<br/>65<br/>66<br/>67<br/>68<br/>69<br/>70<br/>71<br/>72<br/>73<br/>74<br/>75<br/>76<br/>77<br/>78<br/>79<br/>80<br/>81<br/>82<br/>83<br/>84<br/>85<br/>86<br/>87<br/>88<br/>89<br/>90<br/>91<br/>92<br/>93<br/>94<br/>95<br/>96<br/>97<br/>98<br/>99<br/>100<br/>101<br/>102<br/>103<br/>104<br/>105<br/>106<br/>107<br/>108<br/>109<br/>110<br/>111<br/>112<br/>113<br/>114<br/>115<br/>116<br/>117<br/>118<br/>119<br/>120<br/>121<br/>122<br/>123<br/>124<br/>125<br/>126<br/>127<br/>128<br/>129<br/>130<br/>131<br/>132<br/>133<br/>134<br/>135<br/>136<br/>137<br/>138<br/>139<br/>140<br/>141<br/>142<br/>143<br/>144<br/>145<br/>146<br/>147<br/>148<br/>149<br/>150<br/>151<br/>152<br/>153<br/>154<br/>155<br/>156<br/>157<br/>158<br/>159<br/>160<br/>161<br/>162<br/>163<br/>164<br/>165<br/>166<br/>167<br/>168<br/>169<br/>170<br/>171<br/>172<br/>173<br/>174<br/>175<br/>176<br/>177<br/>178<br/>179<br/>180<br/>181<br/>182<br/>183<br/>184<br/>185<br/>186<br/>187<br/>188<br/>189<br/>190<br/>191<br/>192<br/>193<br/>194<br/>195<br/>196<br/>197<br/>198<br/>199<br/>200<br/>201<br/>202<br/>203<br/>204<br/>205<br/>206<br/>207<br/>208<br/>209<br/>210<br/>211<br/>212<br/>213<br/>214<br/>215<br/>216<br/>217<br/>218<br/>219<br/>220<br/>221<br/>222<br/>223<br/>224<br/>225<br/>226<br/>227<br/>228<br/>229<br/>230<br/>231<br/>232<br/>233<br/>234<br/>235<br/>236<br/>237<br/>238<br/>239<br/>240<br/>241<br/>242<br/>243<br/>244<br/>245<br/>246<br/>247<br/>248<br/>249<br/>250<br/>251<br/>252<br/>253<br/>254<br/>255<br/><br/></div>
</td> <td class="wsite-multicol-col" style="width:58.024691358025%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Password num<br/>in the corresponding pool</strong><br/>3931<br/>3875<br/>3782<br/>3881<br/>4030<br/>3852<br/>3901<br/>4001<br/>3877<br/>3788<br/>4025<br/>3881<br/>3848<br/>3969<br/>3815<br/>3953<br/>3874<br/>3902<br/>3907<br/>3873<br/>3894<br/>3964<br/>3839<br/>3861<br/>3818<br/>3914<br/>4141<br/>3927<br/>3858<br/>3914<br/>3955<br/>3920<br/>3869<br/>3791<br/>3860<br/>3849<br/>3917<br/>3939<br/>3844<br/>3829<br/>3828<br/>3749<br/>3867<br/>3924<br/>3874<br/>4015<br/>3883<br/>3908<br/>3896<br/>3935<br/>3861<br/>4010<br/>3876<br/>3927<br/>3927<br/>3941<br/>3840<br/>3987<br/>3884<br/>3905<br/>3830<br/>3923<br/>3849<br/>3923<br/>3928<br/>3874<br/>3927<br/>3933<br/>3949<br/>3941<br/>4027<br/>3946<br/>3928<br/>3949<br/>3885<br/>3832<br/>3970<br/>3926<br/>3856<br/>3896<br/>4017<br/>3957<br/>3908<br/>3901<br/>3809<br/>3836<br/>3983<br/>4009<br/>4080<br/>3950<br/>3913<br/>3876<br/>3887<br/>3984<br/>3909<br/>3883<br/>3933<br/>3999<br/>3846<br/>3844<br/>3869<br/>3972<br/>3955<br/>3887<br/>3862<br/>3850<br/>3815<br/>4040<br/>3822<br/>3928<br/>3947<br/>3853<br/>3962<br/>3961<br/>3998<br/>3918<br/>3949<br/>3931<br/>3889<br/>3941<br/>3925<br/>3884<br/>3964<br/>3815<br/>3883<br/>3962<br/>3925<br/>3875<br/>3857<br/>3847<br/>3859<br/>3866<br/>4021<br/>3902<br/>3927<br/>3951<br/>3951<br/>3871<br/>3848<br/>3923<br/>3848<br/>3919<br/>3886<br/>3869<br/>3978<br/>3813<br/>3884<br/>3910<br/>3800<br/>3855<br/>3900<br/>3932<br/>3901<br/>3963<br/>3961<br/>3883<br/>4036<br/>3924<br/>3828<br/>3873<br/>3835<br/>3857<br/>3774<br/>3981<br/>3912<br/>3890<br/>3980<br/>3910<br/>3836<br/>3923<br/>3906<br/>3937<br/>3892<br/>3929<br/>3986<br/>3853<br/>3817<br/>3973<br/>3880<br/>3850<br/>3861<br/>3912<br/>3841<br/>3823<br/>3843<br/>3950<br/>4004<br/>3948<br/>3843<br/>3939<br/>3889<br/>3883<br/>3876<br/>3975<br/>3906<br/>4027<br/>3967<br/>3943<br/>3846<br/>3739<br/>4030<br/>3855<br/>3847<br/>3944<br/>4009<br/>3865<br/>4027<br/>3880<br/>3983<br/>3905<br/>3913<br/>3927<br/>3978<br/>3898<br/>3911<br/>3930<br/>3858<br/>3907<br/>3915<br/>3937<br/>3845<br/>3834<br/>3991<br/>3861<br/>3926<br/>4005<br/>3897<br/>3960<br/>3995<br/>3892<br/>3783<br/>3963<br/>3938<br/>3841<br/>3873<br/>3839<br/>3828<br/>3892<br/>3821<br/>4019<br/>3847<br/>3993<br/>3869<br/>3909<br/>3814<br/>3846<br/>3759<br/>4011<br/>3931<br/>3898<br/>3856<br/>3854<br/>3972<br/>3986<br/>3983<br/>3925<br/></div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> <td class="wsite-multicol-col" style="width:52.909482758621%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:45.901639344262%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Guessing entropy of</strong><br/><strong>the pool</strong><br/>
456.066<br/>521.564<br/>498.563<br/>554.362<br/>472.87<br/>643.952<br/>574.169<br/>702.578<br/>596.034<br/>500.743<br/>682.818<br/>632.69<br/>647.824<br/>486.495<br/>608.904<br/>698.454<br/>597.571<br/>647.534<br/>598.177<br/>534.058<br/>664.992<br/>603.214<br/>474.044<br/>593.656<br/>607.935<br/>593.425<br/>664.88<br/>111.3<br/>572.974<br/>622.416<br/>501.364<br/>495.271<br/>464.473<br/>592.997<br/>692.832<br/>541.271<br/>625.334<br/>662.513<br/>634.925<br/>639.935<br/>311.414<br/>594.134<br/>608.478<br/>605.582<br/>653.44<br/>501.028<br/>655.739<br/>546.459<br/>677.766<br/>558.897<br/>663.958<br/>601.677<br/>608.394<br/>550.599<br/>559.54<br/>637.972<br/>631.933<br/>475.395<br/>597.019<br/>569.33<br/>636.877<br/>423.499<br/>573.829<br/>652.133<br/>451.094<br/>263.067<br/>571.743<br/>643.201<br/>594.527<br/>588.869<br/>554.366<br/>565.557<br/>575.827<br/>710.436<br/>399.675<br/>589.058<br/>750.603<br/>526.321<br/>603.976<br/>463.028<br/>708.205<br/>486.732<br/>570.216<br/>659.026<br/>507.314<br/>486.013<br/>669.729<br/>438.173<br/>618.926<br/>559.893<br/>490.117<br/>572.569<br/>662.192<br/>666.496<br/>507.759<br/>595.845<br/>428.416<br/>543.855<br/>461.857<br/>585.047<br/>232.813<br/>417.765<br/>516.289<br/>626.966<br/>580.481<br/>582.588<br/>581.895<br/>696.303<br/>604.468<br/>615.6<br/>680.602<br/>600.108<br/>523.174<br/>594.623<br/>599.626<br/>511.183<br/>529.86<br/>560.826<br/>623.315<br/>660.448<br/>547.043<br/>639.473<br/>608.662<br/>510.854<br/>690.687<br/>675.416<br/>573.798<br/>603.544<br/>642.477<br/>583.051<br/>543.291<br/>669.657<br/>591.792<br/>684.257<br/>537.564<br/>587.22<br/>459.759<br/>579.866<br/>608.875<br/>505.186<br/>631.696<br/>610.539<br/>624.757<br/>710.828<br/>601.756<br/>607.281<br/>569.825<br/>598.154<br/>537.823<br/>504.419<br/>562.327<br/>549.272<br/>605.497<br/>616.133<br/>538.165<br/>662.244<br/>550.988<br/>639.737<br/>542.163<br/>528.312<br/>608.581<br/>652.625<br/>594.604<br/>458.436<br/>530.653<br/>513.925<br/>617.109<br/>504.761<br/>549.107<br/>583.592<br/>545.297<br/>635.797<br/>632.178<br/>552.963<br/>568.902<br/>639.06<br/>600.586<br/>548.063<br/>630.309<br/>502.308<br/>597.059<br/>627.078<br/>552.114<br/>676.98<br/>639.281<br/>562.584<br/>489.626<br/>509.436<br/>651.086<br/>572.476<br/>558.431<br/>502.478<br/>630.916<br/>706.682<br/>567.064<br/>616.758<br/>589.749<br/>617.527<br/>494.735<br/>422.52<br/>669.813<br/>709.969<br/>556.276<br/>624.069<br/>661.869<br/>647.862<br/>566.016<br/>573.859<br/>658.469<br/>609.915<br/>587.225<br/>504.236<br/>547.315<br/>490.275<br/>   535.505<br/>540.023<br/>283.764<br/>491.886<br/>603.031<br/>583.232<br/>559.397<br/>574.724<br/>695.071<br/>701.263<br/>702.556<br/>540.569<br/>568.862<br/>565.412<br/>461.794<br/>504.16<br/>613.332<br/>592.394<br/>547.443<br/>571.479<br/>452.013<br/>729.95<br/>592.3<br/>591.438<br/>489.14<br/>573.706<br/>516.164<br/>445.698<br/>547.257<br/>510.122<br/>547.455<br/>597.447<br/>524.559<br/>561.081<br/>643.724<br/>661.723<br/>467.799<br/>467.906<br/>425.096<br/>627.084<br/>665.496<br/>633.988</div>
</td> <td class="wsite-multicol-col" style="width:54.098360655738%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Detailed information</strong><br/><strong>of the pool</strong><br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/0.txt">0.txt</a>(detailed explanation)<br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/1.txt">1.txt</a>(detailed explanation)<br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/2.txt">2.txt</a>(detailed explanation)<br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/3.txt">3.txt</a><br/>
4.txt<br/>
<a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/5.txt">5.txt</a><br/>
6.txt<br/>7.txt<br/>8.txt<br/>9.txt<br/>10.txt<br/>11.txt<br/>12.txt<br/>13.txt<br/>14.txt<br/>15.txt<br/>16.txt<br/>17.txt<br/>18.txt<br/>19.txt<br/>20.txt<br/>21.txt<br/>22.txt<br/>23.txt<br/>24.txt<br/>25.txt<br/>26.txt<br/>27.txt<br/>28.txt<br/>29.txt<br/>30.txt<br/>31.txt<br/>32.txt<br/>33.txt<br/>34.txt<br/>35.txt<br/>36.txt<br/>37.txt<br/>38.txt<br/>39.txt<br/>40.txt<br/>41.txt<br/>42.txt<br/>43.txt<br/>44.txt<br/>45.txt<br/>46.txt<br/>47.txt<br/>48.txt<br/>49.txt<br/>50.txt<br/>51.txt<br/>52.txt<br/>53.txt<br/>54.txt<br/>55.txt<br/>56.txt<br/>57.txt<br/>58.txt<br/>59.txt<br/>60.txt<br/>61.txt<br/>62.txt<br/>63.txt<br/>64.txt<br/>65.txt<br/>66.txt<br/>67.txt<br/>68.txt<br/>69.txt<br/>70.txt<br/>71.txt<br/>72.txt<br/>73.txt<br/>74.txt<br/>75.txt<br/>76.txt<br/>77.txt<br/>78.txt<br/>79.txt<br/>80.txt<br/>81.txt<br/>82.txt<br/>83.txt<br/>84.txt<br/>85.txt<br/>86.txt<br/>87.txt<br/>88.txt<br/>89.txt<br/>90.txt<br/>91.txt<br/>92.txt<br/>93.txt<br/>94.txt<br/>95.txt<br/>96.txt<br/>97.txt<br/>98.txt<br/>99.txt<br/>100.txt<br/>101.txt<br/>102.txt<br/>103.txt<br/>104.txt<br/>105.txt<br/>106.txt<br/>107.txt<br/>108.txt<br/>109.txt<br/>110.txt<br/>111.txt<br/>112.txt<br/>113.txt<br/>114.txt<br/>115.txt<br/>116.txt<br/>117.txt<br/>118.txt<br/>119.txt<br/>120.txt<br/>121.txt<br/>122.txt<br/>123.txt<br/>124.txt<br/>125.txt<br/>126.txt<br/>127.txt<br/>128.txt<br/>129.txt<br/>130.txt<br/>131.txt<br/>132.txt<br/>133.txt<br/>134.txt<br/>135.txt<br/>136.txt<br/>137.txt<br/>138.txt<br/>139.txt<br/>140.txt<br/>141.txt<br/>142.txt<br/>143.txt<br/>144.txt<br/>145.txt<br/>146.txt<br/>147.txt<br/>148.txt<br/>149.txt<br/>150.txt<br/>151.txt<br/>152.txt<br/>153.txt<br/>154.txt<br/>155.txt<br/>156.txt<br/>157.txt<br/>158.txt<br/>159.txt<br/>160.txt<br/>161.txt<br/>162.txt<br/>163.txt<br/>164.txt<br/>165.txt<br/>166.txt<br/>167.txt<br/>168.txt<br/>169.txt<br/>170.txt<br/>171.txt<br/>172.txt<br/>173.txt<br/>174.txt<br/>175.txt<br/>176.txt<br/>177.txt<br/>178.txt<br/>179.txt<br/>180.txt<br/>181.txt<br/>182.txt<br/>183.txt<br/>184.txt<br/>185.txt<br/>186.txt<br/>187.txt<br/>188.txt<br/>189.txt<br/>190.txt<br/>191.txt<br/>192.txt<br/>193.txt<br/>194.txt<br/>195.txt<br/>196.txt<br/>197.txt<br/>198.txt<br/>199.txt<br/>200.txt<br/>201.txt<br/>202.txt<br/>203.txt<br/>204.txt<br/>205.txt<br/>206.txt<br/>207.txt<br/>208.txt<br/>209.txt<br/>210.txt<br/>211.txt<br/>212.txt<br/>213.txt<br/>214.txt<br/>215.txt<br/>216.txt<br/>217.txt<br/>218.txt<br/>219.txt<br/>220.txt<br/>221.txt<br/>222.txt<br/>223.txt<br/>224.txt<br/>225.txt<br/>226.txt<br/>227.txt<br/>228.txt<br/>229.txt<br/>230.txt<br/>231.txt<br/>232.txt<br/>233.txt<br/>234.txt<br/>235.txt<br/>236.txt<br/>237.txt<br/>238.txt<br/>239.txt<br/>240.txt<br/>241.txt<br/>242.txt<br/>243.txt<br/>244.txt<br/>245.txt<br/>246.txt<br/>247.txt<br/>248.txt<br/>249.txt<br/>250.txt<br/>251.txt<br/>252.txt<br/>253.txt<br/>254.txt<br/>255.txt</div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> </tr>
</tbody>
</table>
</div></div></div>
<div><div style="height: 20px; overflow: hidden; width: 100%;"></div>
<hr class="styled-hr" style="width:100%;"/>
<div style="height: 20px; overflow: hidden; width: 100%;"></div></div>
<div class="paragraph" style="text-align:left;"><strong><span style="color:#350df8">Experimental 2.</span> Results from the top 1 million most popular passwords of CSDN dataset</strong><br/>
(1) Theminimumpassword numberof the 256 password pools is 3756, and themaximumis 4079;<br/>
(2) Theminimum guessing expectationof the 256 password pools is 39.799, themaximumis 1122.18, and the majority is below 1024, which fails toguarantee that the success probability of one online guessing attempt using password candidate in any pool by the adversary is no more than 1/1024.<br/>
(3) Due to storage space constraints of this site, we only upload 10% of the password pool files.
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:54.094827586207%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:47.300215982721%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Password Pool<br/>(0~255)</strong><br/>0<br/>1<br/>2<br/>3<br/>4<br/>5<br/>6<br/>7<br/>8<br/>9<br/>10<br/>11<br/>12<br/>13<br/>14<br/>15<br/>16<br/>17<br/>18<br/>19<br/>20<br/>21<br/>22<br/>23<br/>24<br/>25<br/>26<br/>27<br/>28<br/>29<br/>30<br/>31<br/>32<br/>33<br/>34<br/>35<br/>36<br/>37<br/>38<br/>39<br/>40<br/>41<br/>42<br/>43<br/>44<br/>45<br/>46<br/>47<br/>48<br/>49<br/>50<br/>51<br/>52<br/>53<br/>54<br/>55<br/>56<br/>57<br/>58<br/>59<br/>60<br/>61<br/>62<br/>63<br/>64<br/>65<br/>66<br/>67<br/>68<br/>69<br/>70<br/>71<br/>72<br/>73<br/>74<br/>75<br/>76<br/>77<br/>78<br/>79<br/>80<br/>81<br/>82<br/>83<br/>84<br/>85<br/>86<br/>87<br/>88<br/>89<br/>90<br/>91<br/>92<br/>93<br/>94<br/>95<br/>96<br/>97<br/>98<br/>99<br/>100<br/>101<br/>102<br/>103<br/>104<br/>105<br/>106<br/>107<br/>108<br/>109<br/>110<br/>111<br/>112<br/>113<br/>114<br/>115<br/>116<br/>117<br/>118<br/>119<br/>120<br/>121<br/>122<br/>123<br/>124<br/>125<br/>126<br/>127<br/>128<br/>129<br/>130<br/>131<br/>132<br/>133<br/>134<br/>135<br/>136<br/>137<br/>138<br/>139<br/>140<br/>141<br/>142<br/>143<br/>144<br/>145<br/>146<br/>147<br/>148<br/>149<br/>150<br/>151<br/>152<br/>153<br/>154<br/>155<br/>156<br/>157<br/>158<br/>159<br/>160<br/>161<br/>162<br/>163<br/>164<br/>165<br/>166<br/>167<br/>168<br/>169<br/>170<br/>171<br/>172<br/>173<br/>174<br/>175<br/>176<br/>177<br/>178<br/>179<br/>180<br/>181<br/>182<br/>183<br/>184<br/>185<br/>186<br/>187<br/>188<br/>189<br/>190<br/>191<br/>192<br/>193<br/>194<br/>195<br/>196<br/>197<br/>198<br/>199<br/>200<br/>201<br/>202<br/>203<br/>204<br/>205<br/>206<br/>207<br/>208<br/>209<br/>210<br/>211<br/>212<br/>213<br/>214<br/>215<br/>216<br/>217<br/>218<br/>219<br/>220<br/>221<br/>222<br/>223<br/>224<br/>225<br/>226<br/>227<br/>228<br/>229<br/>230<br/>231<br/>232<br/>233<br/>234<br/>235<br/>236<br/>237<br/>238<br/>239<br/>240<br/>241<br/>242<br/>243<br/>244<br/>245<br/>246<br/>247<br/>248<br/>249<br/>250<br/>251<br/>252<br/>253<br/>254<br/>255</div>
</td> <td class="wsite-multicol-col" style="width:52.699784017279%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong style="text-align: center;"> Password num<br/>in the corresponding pool</strong><br/>
3867<br/>3964<br/>3862<br/>3983<br/>3840<br/>3846<br/>4039<br/>3917<br/>3890<br/>3866<br/>3928<br/>4063<br/>3870<br/>3980<br/>3935<br/>3892<br/>3914<br/>3963<br/>3888<br/>3977<br/>3925<br/>3756<br/>3997<br/>3860<br/>3910<br/>3771<br/>3929<br/>4004<br/>3934<br/>3888<br/>3866<br/>3853<br/>3978<br/>3905<br/>3819<br/>3864<br/>3967<br/>4022<br/>3895<br/>3818<br/>3767<br/>3977<br/>3941<br/>3906<br/>3969<br/>3826<br/>3903<br/>3806<br/>3969<br/>3993<br/>3858<br/>3876<br/>3831<br/>3864<br/>3930<br/>3907<br/>3815<br/>3956<br/>3877<br/>3808<br/>3849<br/>3976<br/>3895<br/>3864<br/>3945<br/>3901<br/>4014<br/>3905<br/>3859<br/>3937<br/>3928<br/>3909<br/>3867<br/>3828<br/>3848<br/>3959<br/>3839<br/>3938<br/>3828<br/>3905<br/>3926<br/>3824<br/>3989<br/>3951<br/>3889<br/>3915<br/>3931<br/>3878<br/>3800<br/>3909<br/>3907<br/>4014<br/>3975<br/>3832<br/>3885<br/>3939<br/>3984<br/>3944<br/>3892<br/>4028<br/>3858<br/>3878<br/>3850<br/>3920<br/>3871<br/>3853<br/>3853<br/>3825<br/>3920<br/>3837<br/>3952<br/>3897<br/>3845<br/>3830<br/>3885<br/>3887<br/>3982<br/>3893<br/>3981<br/>3847<br/>3993<br/>2982<br/>3873<br/>3904<br/>4051<br/>3925<br/>3924<br/>4009<br/>3883<br/>3791<br/>3900<br/>3897<br/>3988<br/>3890<br/>3951<br/>3959<br/>3952<br/>3876<br/>3871<br/>3899<br/>3898<br/>3867<br/>3832<br/>3974<br/>3909<br/>3841<br/>3914<br/>4016<br/>3888<br/>3914<br/>3929<br/>3786<br/>3930<br/>3966<br/>3897<br/>3877<br/>3915<br/>3803<br/>3892<br/>3792<br/>3945<br/>3962<br/>3861<br/>3981<br/>3842<br/>3898<br/>3951<br/>3802<br/>3887<br/>3900<br/>3930<br/>3929<br/>3959<br/>3957<br/>4025<br/>3895<br/>3881<br/>4004<br/>3880<br/>3913<br/>3853<br/>3937<br/>3950<br/>3970<br/>3967<br/>3878<br/>3927<br/>3925<br/>3890<br/>3824<br/>3924<br/>3907<br/>3931<br/>3846<br/>3907<br/>3768<br/>3877<br/>3990<br/>3930<br/>3891<br/>3871<br/>3857<br/>3901<br/>3828<br/>3894<br/>3900<br/>3825<br/>4000<br/>4079<br/>3946<br/>3871<br/>3887<br/>3939<br/>3905<br/>3926<br/>3857<br/>3934<br/>3936<br/>3934<br/>3887<br/>4006<br/>3830<br/>3836<br/>3892<br/>3903<br/>3982<br/>3926<br/>3981<br/>3851<br/>4007<br/>3854<br/>3868<br/>3872<br/>3845<br/>3909<br/>3860<br/>3854<br/>3928<br/>3897<br/>3923<br/>3976<br/>3919<br/>3993<br/>3881<br/>3824<br/>3813<br/>4004<br/>3823<br/>3943<br/>3995<br/>3936<br/>3857<br/>3949<br/>3808<br/>3822<br/>3856
</div></td> </tr>
</tbody>
</table>
</div></div></div>
</td> <td class="wsite-multicol-col" style="width:45.905172413793%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Guessing entropy of</strong><br/><strong>the pool</strong><br/>1023.08<br/>1098.26<br/>925.523<br/>941.73<br/>794.435<br/>901.394<br/>1087.68<br/>972.911<br/>1009.77<br/>858.732<br/>999.082<br/>1109.14<br/>1049.21<br/>44.6363<br/>867.563<br/>920.604<br/>988.872<br/>1014.56<br/>830.814<br/>745.67<br/>1014.87<br/>965.85<br/>764.209<br/>941.439<br/>611.132<br/>829.924<br/>968.136<br/>799.307<br/>933.432<br/>848.446<br/>986.977<br/>895.338<br/>869.98<br/>960.332<br/>999.75<br/>1073.17<br/>863.53<br/>987.565<br/>1011.13<br/>946.33<br/>680.162<br/>907.832<br/>624.903<br/>808.396<br/>1053.7<br/>902.647<br/>945.085<br/>774.794<br/>719.332<br/>973.003<br/>949.001<br/>967.216<br/>998.753<br/>819.275<br/>585.703<br/>1040.53<br/>958.778<br/>954.395<br/>893.225<br/>899.602<br/>898.47<br/>866.772<br/>826.439<br/>356.453<br/>985.61<br/>39.799<br/>833.039<br/>1047.26<br/>961.809<br/>1052.69<br/>1003.16<br/>839.485<br/>865.656<br/>983.468<br/>908.574<br/>952.067<br/>950.681<br/>1009.26<br/>884.069<br/>909.355<br/>736.991<br/>1094.41<br/>1028.08<br/>1017.11<br/>992.073<br/>920.012<br/>930.292<br/>960.317<br/>934.424<br/>600.663<br/>831.663<br/>961.935<br/>1119.53<br/>908.274<br/>824.777<br/>952.701<br/>1009.26<br/>950.768<br/>1027.77<br/>1038.96<br/>828.609<br/>741.538<br/>803.875<br/>789.72<br/>898.089<br/>1068.52<br/>912.529<br/>934.853<br/>983.014<br/>865.35<br/>901.935<br/>903.448<br/>899.633<br/>1043.83<br/>903.039<br/>875.021<br/>872.072<br/>638.946<br/>851.745<br/>1122.18<br/>866.963<br/>804.427<br/>647.657<br/>951.451<br/>971.499<br/>958.3<br/>941.554<br/>662.393<br/>940.499<br/>934.895<br/>1025.51<br/>1020.02<br/>1100.26<br/>839.834<br/>785.791<br/>891.99<br/>661.061<br/>961.444<br/>975.089<br/>214.501<br/>1073.61<br/>1017.99<br/>966.581<br/>961.599<br/>909.897<br/>934.665<br/>326.428<br/>1021.39<br/>906.718<br/>966.049<br/>659.408<br/>765.57<br/>978.291<br/>905.503<br/>347.717<br/>992.109<br/>707.52<br/>1005.88<br/>947.792<br/>914.298<br/>910.566<br/>990.181<br/>963.387<br/>956.621<br/>930.853<br/>874.573<br/>984.39<br/>996.653<br/>938.229<br/>735.129<br/>849.921<br/>743.855<br/>1080.14<br/>982.268<br/>1051.92<br/>905.216<br/>895.464<br/>1108.33<br/>900.98<br/>796.451<br/>166.335<br/>1050.23<br/>891.338<br/>918.536<br/>108.176<br/>1015.28<br/>1026.36<br/>955.664<br/>   1006.5<br/>948.722<br/>776.401<br/>927.392<br/>995.856<br/>951.855<br/>881.966<br/>887.775<br/>887.982<br/>966.887<br/>772.4<br/>782.534<br/>984.967<br/>767.491<br/>983.269<br/>848.062<br/>788.417<br/>1018<br/>849.715<br/>1006<br/>961.384<br/>934.371<br/>973.616<br/>960.934<br/>1014.03<br/>994.589<br/>1048.58<br/>786.385<br/>752.627<br/>834.084<br/>868.844<br/>1058.02<br/>753.148<br/>979.968<br/>1046.12<br/>894.386<br/>827.192<br/>957.222<br/>905.089<br/>1056<br/>987.687<br/>938.495<br/>1006.82<br/>664.966<br/>727.424<br/>1034.63<br/>945.694<br/>877.16<br/>921.328<br/>910.01<br/>700.225<br/>872.794<br/>1035.42<br/>891.872<br/>831.549<br/>890.755<br/>975.506<br/>944.213<br/>688.494<br/>932.537<br/>902.889<br/>630.396<br/>892.572<br/>813.427<br/>733.097<br/>764.895<br/>1034.69<br/>932.788<br/></div>
</td> <td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Detailed information</strong><br/><strong>of the pool</strong><br/>0.txt(detailed explanation)<br/>1.txt(detailed explanation)<br/>2.txt(detailed explanation)<br/>3.txt<br/>4.txt<br/>5.txt<br/>6.txt<br/>7.txt<br/>8.txt<br/>9.txt<br/>10.txt<br/>11.txt<br/>12.txt<br/>13.txt<br/>14.txt<br/>15.txt<br/>16.txt<br/>17.txt<br/>18.txt<br/>19.txt<br/>20.txt<br/>21.txt<br/>22.txt<br/>23.txt<br/>24.txt<br/>25.txt<br/>26.txt<br/>27.txt<br/>28.txt<br/>29.txt<br/>30.txt<br/>31.txt<br/>32.txt<br/>33.txt<br/>34.txt<br/>35.txt<br/>36.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/37.txt">37</a>.txt<br/>38.txt<br/>39.txt<br/>40.txt<br/>41.txt<br/>42.txt<br/>43.txt<br/>44.txt<br/>45.txt<br/>46.txt<br/>47.txt<br/>48.txt<br/>49.txt<br/>50.txt<br/>51.txt<br/>52.txt<br/>53.txt<br/>54.txt<br/>55.txt<br/>56.txt<br/>57.txt<br/>58.txt<br/>59.txt<br/>60.txt<br/>61.txt<br/>62.txt<br/>63.txt<br/>64.txt<br/>65.txt<br/>66.txt<br/>67.txt<br/>68.txt<br/>69.txt<br/>70.txt<br/>71.txt<br/>72.txt<br/>73.txt<br/>74.txt<br/>75.txt<br/>76.txt<br/>77.txt<br/>78.txt<br/>79.txt<br/>80.txt<br/>81.txt<br/>82.txt<br/>83.txt<br/>84.txt<br/>85.txt<br/>86.txt<br/>87.txt<br/>88.txt<br/>89.txt<br/>90.txt<br/>91.txt<br/>92.txt<br/>93.txt<br/>94.txt<br/>95.txt<br/>96.txt<br/>97.txt<br/>98.txt<br/>99.txt<br/>100.txt<br/>101.txt<br/>102.txt<br/>103.txt<br/>104.txt<br/>105.txt<br/>106.txt<br/>107.txt<br/>108.txt<br/>109.txt<br/>110.txt<br/>111.txt<br/>112.txt<br/>113.txt<br/>114.txt<br/>115.txt<br/>116.txt<br/>117.txt<br/>118.txt<br/>119.txt<br/>120.txt<br/>121.txt<br/>122.txt<br/>123.txt<br/>124.txt<br/>125.txt<br/>126.txt<br/>127.txt<br/>128.txt<br/>129.txt<br/>130.txt<br/>131.txt<br/>132.txt<br/>133.txt<br/>134.txt<br/>135.txt<br/>136.txt<br/>137.txt<br/>138.txt<br/>139.txt<br/>140.txt<br/>141.txt<br/>142.txt<br/>143.txt<br/>144.txt<br/>145.txt<br/>146.txt<br/>147.txt<br/>148.txt<br/>149.txt<br/>150.txt<br/>151.txt<br/>152.txt<br/>153.txt<br/>154.txt<br/>155.txt<br/>156.txt<br/>157.txt<br/>158.txt<br/>159.txt<br/>160.txt<br/>161.txt<br/>162.txt<br/>163.txt<br/>164.txt<br/>165.txt<br/>166.txt<br/>167.txt<br/>168.txt<br/>169.txt<br/>170.txt<br/>171.txt<br/>172.txt<br/>173.txt<br/>174.txt<br/>175.txt<br/>176.txt<br/>177.txt<br/>178.txt<br/>179.txt<br/>180.txt<br/>181.txt<br/>182.txt<br/>183.txt<br/>184.txt<br/>185.txt<br/>186.txt<br/>187.txt<br/>188.txt<br/>189.txt<br/>190.txt<br/>191.txt<br/>192.txt<br/>193.txt<br/>194.txt<br/>195.txt<br/>196.txt<br/>197.txt<br/>198.txt<br/>199.txt<br/>200.txt<br/>201.txt<br/>202.txt<br/>203.txt<br/>204.txt<br/>205.txt<br/>206.txt<br/>207.txt<br/>208.txt<br/>209.txt<br/>210.txt<br/>211.txt<br/>212.txt<br/>213.txt<br/>214.txt<br/>215.txt<br/>216.txt<br/>217.txt<br/>218.txt<br/>219.txt<br/>220.txt<br/>221.txt<br/>222.txt<br/>223.txt<br/>224.txt<br/>225.txt<br/>226.txt<br/>227.txt<br/>228.txt<br/>229.txt<br/>230.txt<br/>231.txt<br/>232.txt<br/>233.txt<br/>234.txt<br/>235.txt<br/>236.txt<br/>237.txt<br/>238.txt<br/>239.txt<br/>240.txt<br/>241.txt<br/>242.txt<br/>243.txt<br/>244.txt<br/>245.txt<br/>246.txt<br/>247.txt<br/>248.txt<br/>249.txt<br/>250.txt<br/>251.txt<br/>252.txt<br/>253.txt<br/>254.txt<br/>255.txt</div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> </tr>
</tbody>
</table>
</div></div></div>
<hr class="styled-hr" style="width:100%;"/>
<br/>
<div class="paragraph" style="text-align:left;"><strong><span style="color:#350df8">Experimental 3.</span> Results from the top 2 million most popular passwords of Rockyou dataset</strong><br/>
<div class="paragraph" style="text-align:left;">
(1) The minimum password number of the 256 password pools is 7612, and the maximumis 8018;<br/>
(2) The minimum guessing expectation of the 256 password pools is247.935, the maximumis 1418.31, and about 16% of the pools are below 1024, which fails toguarantee that the success probability of one online guessing attempt using password candidate in any pool by the adversary is no more than 1/1024.<br/>
(3) Due to storage space constraints of this site, we only upload 10% of the password pool files.</div>
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:56.63430420712%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Password Pool</strong><br/><strong>(0~255)</strong><br/>0<br/>1<br/>2<br/>3<br/>4<br/>5<br/>6<br/>7<br/>8<br/>9<br/>10<br/>11<br/>12<br/>13<br/>14<br/>15<br/>16<br/>17<br/>18<br/>19<br/>20<br/>21<br/>22<br/>23<br/>24<br/>25<br/>26<br/>27<br/>28<br/>29<br/>30<br/>31<br/>32<br/>33<br/>34<br/>35<br/>36<br/>37<br/>38<br/>39<br/>40<br/>41<br/>42<br/>43<br/>44<br/>45<br/>46<br/>47<br/>48<br/>49<br/>50<br/>51<br/>52<br/>53<br/>54<br/>55<br/>56<br/>57<br/>58<br/>59<br/>60<br/>61<br/>62<br/>63<br/>64<br/>65<br/>66<br/>67<br/>68<br/>69<br/>70<br/>71<br/>72<br/>73<br/>74<br/>75<br/>76<br/>77<br/>78<br/>79<br/>80<br/>81<br/>82<br/>83<br/>84<br/>85<br/>86<br/>87<br/>88<br/>89<br/>90<br/>91<br/>92<br/>93<br/>94<br/>95<br/>96<br/>97<br/>98<br/>99<br/>100<br/>101<br/>102<br/>103<br/>104<br/>105<br/>106<br/>107<br/>108<br/>109<br/>110<br/>111<br/>112<br/>113<br/>114<br/>115<br/>116<br/>117<br/>118<br/>119<br/>120<br/>121<br/>122<br/>123<br/>124<br/>125<br/>126<br/>127<br/>128<br/>129<br/>130<br/>131<br/>132<br/>133<br/>134<br/>135<br/>136<br/>137<br/>138<br/>139<br/>140<br/>141<br/>142<br/>143<br/>144<br/>145<br/>146<br/>147<br/>148<br/>149<br/>150<br/>151<br/>152<br/>153<br/>154<br/>155<br/>156<br/>157<br/>158<br/>159<br/>160<br/>161<br/>162<br/>163<br/>164<br/>165<br/>166<br/>167<br/>168<br/>169<br/>170<br/>171<br/>172<br/>173<br/>174<br/>175<br/>176<br/>177<br/>178<br/>179<br/>180<br/>181<br/>182<br/>183<br/>184<br/>185<br/>186<br/>187<br/>188<br/>189<br/>190<br/>191<br/>192<br/>193<br/>194<br/>195<br/>196<br/>197<br/>198<br/>199<br/>200<br/>201<br/>202<br/>203<br/>204<br/>205<br/>206<br/>207<br/>208<br/>209<br/>210<br/>211<br/>212<br/>213<br/>214<br/>215<br/>216<br/>217<br/>218<br/>219<br/>220<br/>221<br/>222<br/>223<br/>224<br/>225<br/>226<br/>227<br/>228<br/>229<br/>230<br/>231<br/>232<br/>233<br/>234<br/>235<br/>236<br/>237<br/>238<br/>239<br/>240<br/>241<br/>242<br/>243<br/>244<br/>245<br/>246<br/>247<br/>248<br/>249<br/>250<br/>251<br/>252<br/>253<br/>254<br/>255</div>
</td> <td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Password num<br/>in the corresponding pool</strong><br/>7764<br/>7738<br/>7671<br/>7824<br/>8018<br/>7753<br/>7789<br/>7844<br/>7806<br/>7817<br/>7847<br/>7780<br/>7703<br/>7760<br/>7775<br/>7730<br/>7778<br/>7823<br/>7848<br/>7761<br/>7840<br/>7883<br/>7723<br/>7757<br/>7670<br/>7838<br/>7994<br/>7887<br/>7861<br/>7890<br/>7937<br/>7821<br/>7722<br/>7621<br/>7764<br/>7654<br/>7874<br/>7865<br/>7828<br/>7862<br/>7766<br/>7675<br/>7775<br/>7748<br/>7776<br/>7869<br/>7714<br/>7820<br/>7778<br/>7896<br/>7878<br/>7840<br/>7762<br/>7822<br/>7863<br/>7844<br/>7740<br/>7842<br/>7800<br/>7828<br/>7790<br/>7946<br/>7724<br/>7822<br/>7920<br/>7701<br/>7796<br/>7705<br/>7760<br/>7788<br/>7870<br/>7822<br/>7693<br/>7836<br/>7799<br/>7682<br/>7777<br/>7821<br/>7759<br/>7820<br/>7958<br/>7901<br/>7950<br/>7860<br/>7703<br/>7736<br/>7882<br/>7933<br/>7959<br/>7868<br/>7772<br/>   7895<br/>7830<br/>7811<br/>7876<br/>7827<br/>7901<br/>7969<br/>7666<br/>7848<br/>7840<br/>7913<br/>7872<br/>7811<br/>7829<br/>7684<br/>7761<br/>7876<br/>7773<br/>7932<br/>7837<br/>7818<br/>7864<br/>7805<br/>7949<br/>7884<br/>7926<br/>7903<br/>7848<br/>7714<br/>7756<br/>7789<br/>7761<br/>7720<br/>7901<br/>7958<br/>7817<br/>7817<br/>7809<br/>7666<br/>7718<br/>7723<br/>7970<br/>7886<br/>7854<br/>7855<br/>7698<br/>7859<br/>7859<br/>7908<br/>7836<br/>7929<br/>7796<br/>7716<br/>7859<br/>7679<br/>7754<br/>7856<br/>7644<br/>7698<br/>7796<br/>7820<br/>7806<br/>7721<br/>7851<br/>7817<br/>7937<br/>7729<br/>7616<br/>7785<br/>7795<br/>7768<br/>7619<br/>7947<br/>7833<br/>7818<br/>7945<br/>7781<br/>7612<br/>7803<br/>7766<br/>7939<br/>7812<br/>7895<br/>7898<br/>7647<br/>7764<br/>7802<br/>7842<br/>7776<br/>7937<br/>7840<br/>7726<br/>7681<br/>7689<br/>7911<br/>7902<br/>7867<br/>7745<br/>7936<br/>7656<br/>7789<br/>7748<br/>7949<br/>7845<br/>7929<br/>7838<br/>7733<br/>7750<br/>7630<br/>8015<br/>7757<br/>7758<br/>7826<br/>7925<br/>7841<br/>8017<br/>7763<br/>7919<br/>7895<br/>7881<br/>7907<br/>7823<br/>7891<br/>7842<br/>7815<br/>7711<br/>7818<br/>7729<br/>7784<br/>7789<br/>7705<br/>7880<br/>7893<br/>7912<br/>7922<br/>7821<br/>7883<br/>7925<br/>7774<br/>7779<br/>7779<br/>7823<br/>7728<br/>7835<br/>7690<br/>7752<br/>7795<br/>7730<br/>7937<br/>7711<br/>7778<br/>7692<br/>7668<br/>7797<br/>7835<br/>7684<br/>7820<br/>7823<br/>7803<br/>7811<br/>7836<br/>7688<br/>7927<br/> 7898<br/>7857</div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> <td class="wsite-multicol-col" style="width:43.36569579288%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:49.625935162095%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Guessing entropy of the pool</strong><br/>918.705<br/>1047.66<br/>1031.04<br/>1125.91<br/>960.567<br/>1281.81<br/>1148.27<br/>1353.54<br/>1204.09<br/>1056.31<br/>1313.91<br/>1260.43<br/>1284.16<br/>963.588<br/>1242.42<br/>1336.28<br/>1196.14<br/>1280.54<br/>1196.64<br/>1079.67<br/>1323.08<br/>1191.74<br/>964.332<br/>1192.62<br/>1221.79<br/>1186.49<br/>1258.99<br/>247.935<br/>1182.24<br/>1240.02<br/>1030.74<br/>1001.32<br/>939.1<br/>1190.93<br/>1372.64<br/>1075.58<br/>1245.19<br/>1304.3<br/>1285.03<br/>1318.66<br/>671.304<br/>1227.87<br/>1230.78<br/>1185.84<br/>1295.78<br/>991.927<br/>1285.14<br/>1095.93<br/>1323.08<br/>1125.93<br/>1341<br/>1182.15<br/>1209.92<br/>1105.43<br/>1134.15<br/>1253.48<br/>1268.94<br/>961.555<br/>1203.38<br/>1146.1<br/>1298.18<br/>883.748<br/>1152.49<br/>1273.02<br/>926.633<br/>562.318<br/>1137.47<br/>1244.44<br/>1160.52<br/>1166.77<br/>1089.3<br/>1116.49<br/>1130.84<br/>1382.29<br/>828.109<br/>1181.81<br/>1418.31<br/>1054.68<br/>1216.33<br/>949.734<br/>1384.67<br/>1000.26<br/>1173.87<br/>1301.27<br/>1041.68<br/>1002.37<br/>1298.91<br/>876.528<br/>1206.83<br/>1119.04<br/>981.857<br/>1186.88<br/>1321.74<br/>1293.58<br/>1034.63<br/>1203.07<br/>872.998<br/>1093.81<br/>942.375<br/>1207.78<br/>505.849<br/>863.928<br/>1029.43<br/>1269.98<br/>1171.16<br/>1154.01<br/>1190.54<br/>1324.54<br/>1237.48<br/>1257.97<br/>1318.27<br/>1222.94<br/>1049.29<br/>1163.29<br/>1194.3<br/>1048.6<br/>1081.33<br/>1130.92<br/>1257.09<br/>1270.85<br/>1085.62<br/>1278.54<br/>1183.47<br/>1048.98<br/>1395.01<br/>1340.32<br/>1143.36<br/>1211.04<br/>1288.2<br/>1158.95<br/>1091.42<br/>1321.2<br/>1176.55<br/>1354.4<br/>1085.79<br/>1173.28<br/>912.117<br/>1180.49<br/>1244.64<br/>1042.65<br/>1282.06<br/>1248.4<br/>1258.42<br/>1380.12<br/>1175.46<br/>1219.2<br/>1150.24<br/>1189.53<br/>1085.54<br/>1024.95<br/>1127.55<br/>1101.49<br/>1214.48<br/>1181.21<br/>1084.08<br/>1324.82<br/>1085.44<br/>1250.64<br/>1073.56<br/>1083.14<br/>1238.58<br/>1296.44<br/>1199.08<br/>938.505<br/>1069.08<br/>1048.7<br/>1221.22<br/>   1015.57<br/>1091.08<br/>1165.82<br/>1090.68<br/>1278.3<br/>1265.51<br/>1125.42<br/>1133.84<br/>1247.82<br/>1230.83<br/>1099.19<br/>1279.85<br/>1046.66<br/>1235.64<br/>1249.47<br/>1107.42<br/>1348.77<br/>1256.01<br/>1134.4<br/>992.791<br/>1038.36<br/>1298.98<br/>1160.41<br/>1094.23<br/>1018.41<br/>1248.52<br/>1385.79<br/>1149.58<br/>1196.9<br/>1159.48<br/>1202.37<br/>1008.23<br/>889.762<br/>1320.09<br/>1400.3<br/>1137.77<br/>1223.71<br/>1280.96<br/>1299.98<br/>1149.65<br/>1152.59<br/>1294.07<br/>1234.98<br/>1187.57<br/>1026.52<br/>1079.16<br/>1020.64<br/>1072.42<br/>1076.97<br/>594.755<br/>988.178<br/>1195.74<br/>1158.1<br/>1134.25<br/>1149.77<br/>1354.27<br/>1405.4<br/>1390.27<br/>1074.49<br/>1150.97<br/>1145.39<br/>932.713<br/>1029.92<br/>1263.71<br/>1168.54<br/>1094.46<br/>1146.77<br/>939.76<br/>1412.4<br/>1192.53<br/>1179.37<br/>1017.02<br/>1139.56<br/>1044.77<br/>895.022<br/>1103.16<br/>1018.9<br/>1140.86<br/>1224.55<br/>1083.94<br/>1088.94<br/>1261.51<br/>1301.6<br/>956.085<br/>963.337<br/>837.827<br/>1242.92<br/>1307.7<br/>1249.8</div>
</td> <td class="wsite-multicol-col" style="width:50.374064837905%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Detailed information</strong><br/><strong>of the pool</strong><strong></strong><br/><u><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/0.txt">0.txt</a></u>(detailedexplanation)<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/1.txt">1<u>.txt</u></a>(detailed explanation)<br/><u><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/0.txt">2.txt</a></u>(detailed explanation)<br/><u><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/3.txt">3.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/4.txt">4.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/5.txt">5.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/6.txt">6.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/7.txt">7.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/8.txt">8.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/9.txt">9.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/10.txt">10.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/11.txt">11.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/12.txt">12.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/13.txt">13.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/14.txt">14.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/15.txt">15.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/16.txt">16.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/17.txt">17.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/18.txt">18.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/19.txt">19.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/20.txt">20.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/21.txt">21.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/22.txt">22.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/23.txt">23.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/24.txt">24.txt</a><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/25.txt">25.txt</a></u><br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/26.txt">26</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/27.txt">27</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/28.txt">28</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/29.txt">29</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/30.txt">30</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/31.txt">31</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/32.txt">32</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/33.txt">33</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/34.txt">34</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/35.txt">35</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/36.txt">36</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/37.txt">37</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/38.txt">38</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/39.txt">39</a>.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/40.txt">40</a>.txt<br/>41.txt<br/>42.txt<br/>43.txt<br/>44.txt<br/>45.txt<br/>46.txt<br/>47.txt<br/>48.txt<br/>49.txt<br/>50.txt<br/>51.txt<br/>52.txt<br/>53.txt<br/>54.txt<br/>55.txt<br/>56.txt<br/>57.txt<br/>58.txt<br/>59.txt<br/>60.txt<br/>61.txt<br/>62.txt<br/>63.txt<br/>64.txt<br/>65.txt<br/>66.txt<br/>67.txt<br/>68.txt<br/>69.txt<br/>70.txt<br/>71.txt<br/>72.txt<br/>73.txt<br/>74.txt<br/>75.txt<br/>76.txt<br/>77.txt<br/>78.txt<br/>79.txt<br/>80.txt<br/>81.txt<br/>82.txt<br/>83.txt<br/>84.txt<br/>85.txt<br/>86.txt<br/>87.txt<br/>88.txt<br/>89.txt<br/>90.txt<br/>91.txt<br/>92.txt<br/>93.txt<br/>94.txt<br/>95.txt<br/>96.txt<br/>97.txt<br/>98.txt<br/>99.txt<br/>100.txt<br/>101.txt<br/>102.txt<br/>103.txt<br/>104.txt<br/>105.txt<br/>106.txt<br/>107.txt<br/>108.txt<br/>109.txt<br/>110.txt<br/>111.txt<br/>112.txt<br/>113.txt<br/>114.txt<br/>115.txt<br/>116.txt<br/>117.txt<br/>118.txt<br/>119.txt<br/>120.txt<br/>121.txt<br/>122.txt<br/>123.txt<br/>124.txt<br/>125.txt<br/>126.txt<br/>127.txt<br/>128.txt<br/>129.txt<br/>130.txt<br/>131.txt<br/>132.txt<br/>133.txt<br/>134.txt<br/>135.txt<br/>136.txt<br/>137.txt<br/>138.txt<br/>139.txt<br/>140.txt<br/>141.txt<br/>142.txt<br/>143.txt<br/>144.txt<br/>145.txt<br/>146.txt<br/>147.txt<br/>148.txt<br/>149.txt<br/>150.txt<br/>151.txt<br/>152.txt<br/>153.txt<br/>154.txt<br/>155.txt<br/>156.txt<br/>157.txt<br/>158.txt<br/>159.txt<br/>160.txt<br/>161.txt<br/>162.txt<br/>163.txt<br/>164.txt<br/>165.txt<br/>166.txt<br/>167.txt<br/>168.txt<br/>169.txt<br/>170.txt<br/>171.txt<br/>172.txt<br/>173.txt<br/>174.txt<br/>175.txt<br/>176.txt<br/>177.txt<br/>178.txt<br/>179.txt<br/>180.txt<br/>181.txt<br/>182.txt<br/>183.txt<br/>184.txt<br/>185.txt<br/>186.txt<br/>187.txt<br/>188.txt<br/>189.txt<br/>190.txt<br/>191.txt<br/>192.txt<br/>193.txt<br/>194.txt<br/>195.txt<br/>196.txt<br/>197.txt<br/>198.txt<br/>199.txt<br/>200.txt<br/>201.txt<br/>202.txt<br/>203.txt<br/>204.txt<br/>205.txt<br/>206.txt<br/>207.txt<br/>208.txt<br/>209.txt<br/>210.txt<br/>211.txt<br/>212.txt<br/>213.txt<br/>214.txt<br/>215.txt<br/>216.txt<br/>217.txt<br/>218.txt<br/>219.txt<br/>220.txt<br/>221.txt<br/>222.txt<br/>223.txt<br/>224.txt<br/>225.txt<br/>226.txt<br/>227.txt<br/>228.txt<br/>229.txt<br/>230.txt<br/>231.txt<br/>232.txt<br/>233.txt<br/>234.txt<br/>235.txt<br/>236.txt<br/>237.txt<br/>238.txt<br/>239.txt<br/>240.txt<br/>241.txt<br/>242.txt<br/>243.txt<br/>244.txt<br/>245.txt<br/>246.txt<br/>247.txt<br/>248.txt<br/>249.txt<br/>250.txt<br/>251.txt<br/>252.txt<br/>253.txt<br/>254.txt<br/>255.txt</div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> </tr>
</tbody>
</table>
</div></div></div>
<div><div style="height: 20px; overflow: hidden; width: 100%;"></div>
<hr class="styled-hr" style="width:100%;"/>
<div style="height: 20px; overflow: hidden; width: 100%;"></div></div>

<div class="paragraph" style="text-align:left;"><strong><span style="color:#350df8">Experimental 4.</span> Results from the top 2 million most popular passwords of CSDN dataset (Satisfactory results)</strong><br/>
<div class="paragraph" style="text-align:left;">(1) Theminimumpassword numberof the 256 password pools is 7584, and themaximumis 8146;<br/>(2) Theminimum guessing expectationof the 256 password pools is127.743, themaximumis 2600.56, and only about2.34%of the pools are below 1024. More specifically, six pools are "bad", i.e. POOL65 (127.743),POOL13(149.431), POOL184(343.376), POOL180(528.102), POOL139(652.968), POOL146(973.749).<strong>This means that, with anoverwhelming probability, a pool selected from these 256 pools can guarantee a Level 1 of security.</strong><strong>We further note that, if we eliminate only one most highly vulnerable password from each of these six bad pools (e.g., 123456 from POOL65, 123456789 from POOL65), then ﻿all ﻿the guess entropys of 256 password pools will have a guessing expectation larger than 1024.</strong>In practice, this can be achieved by using a blacklist and preventing the users from choosing these highly vulnerable passwords (e.g., 123456, 123456789).<br/>(3) Due to storage space constraints of this site, we only upload 10% of the password pool files.</div>
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:56.35775862069%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong style="text-align: center;">Password Pool<br/>(0~255)</strong><br/>0<br/>1<br/>2<br/>3<br/>4<br/>5<br/>6<br/>7<br/>8<br/>9<br/>10<br/>11<br/>12<br/>13<br/>14<br/>15<br/>16<br/>17<br/>18<br/>19<br/>20<br/>21<br/>22<br/>23<br/>24<br/>25<br/>26<br/>27<br/>28<br/>29<br/>30<br/>31<br/>32<br/>33<br/>34<br/>35<br/>36<br/>37<br/>38<br/>39<br/>40<br/>41<br/>42<br/>43<br/>44<br/>45<br/>46<br/>47<br/>48<br/>49<br/>50<br/>51<br/>52<br/>53<br/>54<br/>55<br/>56<br/>57<br/>58<br/>59<br/>60<br/>61<br/>62<br/>63<br/>64<br/>65<br/>66<br/>67<br/>68<br/>69<br/>70<br/>71<br/>72<br/>73<br/>74<br/>75<br/>76<br/>77<br/>78<br/>79<br/>80<br/>81<br/>82<br/>83<br/>84<br/>85<br/>86<br/>87<br/>88<br/>89<br/>90<br/>91<br/>92<br/>93<br/>94<br/>95<br/>96<br/>97<br/>98<br/>99<br/>100<br/>101<br/>102<br/>103<br/>104<br/>105<br/>106<br/>107<br/>108<br/>109<br/>110<br/>111<br/>112<br/>113<br/>114<br/>115<br/>116<br/>117<br/>118<br/>119<br/>120<br/>121<br/>122<br/>123<br/>124<br/>125<br/>126<br/>127<br/>128<br/>129<br/>130<br/>131<br/>132<br/>133<br/>134<br/>135<br/>136<br/>137<br/>138<br/>139<br/>140<br/>141<br/>142<br/>143<br/>144<br/>145<br/>146<br/>147<br/>148<br/>149<br/>150<br/>151<br/>152<br/>153<br/>154<br/>155<br/>156<br/>157<br/>158<br/>159<br/>160<br/>161<br/>162<br/>163<br/>164<br/>165<br/>166<br/>167<br/>168<br/>169<br/>170<br/>171<br/>172<br/>173<br/>174<br/>175<br/>176<br/>177<br/>178<br/>179<br/>180<br/>181<br/>182<br/>183<br/>184<br/>185<br/>186<br/>187<br/>188<br/>189<br/>190<br/>191<br/>192<br/>193<br/>194<br/>195<br/>196<br/>197<br/>198<br/>199<br/>200<br/>201<br/>202<br/>203<br/>204<br/>205<br/>206<br/>207<br/>208<br/>209<br/>210<br/>211<br/>212<br/>213<br/>214<br/>215<br/>216<br/>217<br/>218<br/>219<br/>220<br/>221<br/>222<br/>223<br/>224<br/>225<br/>226<br/>227<br/>228<br/>229<br/>230<br/>231<br/>232<br/>233<br/>234<br/>235<br/>236<br/>237<br/>238<br/>239<br/>240<br/>241<br/>242<br/>243<br/>244<br/>245<br/>246<br/>247<br/>248<br/>249<br/>250<br/>251<br/>252<br/>253<br/>254<br/>255</div>
</td> <td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong style="text-align: center;">Password num<br/>  in the corresponding pool</strong><br/>   7883<br/>7918<br/>7739<br/>7824<br/>7783<br/>7807<br/>7970<br/>7856<br/>7817<br/>7732<br/>7883<br/>7921<br/>7754<br/>7980<br/>7833<br/>7816<br/>7846<br/>7805<br/>7800<br/>7835<br/>7830<br/>7730<br/>7864<br/>7745<br/>7800<br/>7708<br/>7810<br/>8001<br/>7840<br/>7718<br/>7748<br/>7775<br/>7863<br/>7811<br/>7728<br/>7747<br/>7852<br/>7932<br/>7680<br/>7704<br/>7718<br/>7965<br/>7892<br/>7716<br/>8013<br/>7763<br/>7855<br/>7859<br/>7909<br/>7749<br/>7830<br/>7706<br/>7761<br/>7634<br/>7979<br/>7850<br/>7662<br/>7954<br/>7852<br/>7627<br/>7770<br/>7800<br/>7773<br/>7709<br/>7781<br/>7735<br/>7906<br/>7913<br/>7686<br/>7850<br/>7761<br/>7829<br/>7733<br/>7695<br/>7778<br/>7825<br/>7584<br/>7823<br/>7760<br/>7768<br/>7912<br/>7921<br/>7788<br/>7900<br/>7885<br/>7772<br/>7791<br/>7817<br/>7751<br/>7745<br/>7828<br/>7727<br/>7828<br/>7853<br/>7700<br/>7777<br/>7872<br/>7886<br/>7845<br/>7678<br/>8013<br/>7743<br/>7700<br/>7728<br/>7865<br/>7879<br/>7708<br/>7655<br/>7718<br/>7799<br/>7800<br/>7829<br/>7722<br/>7686<br/>7698<br/>7713<br/>7770<br/>7902<br/>7804<br/>7886<br/>7734<br/>7877<br/>7866<br/>7705<br/>7860<br/>7938<br/>7892<br/>7782<br/>8032<br/>7714<br/>7878<br/>7792<br/>7915<br/>7861<br/>7791<br/>7872<br/>7828<br/>7700<br/>7803<br/>7737<br/>7654<br/>7738<br/>7679<br/>7954<br/>7786<br/>7792<br/>7807<br/>7999<br/>7730<br/>7804<br/>7861<br/>7825<br/>7836<br/>7989<br/>7779<br/>7745<br/>7893<br/>7658<br/>7842<br/>7663<br/>7711<br/>7893<br/>7876<br/>7861<br/>7859<br/>7882<br/>7894<br/>7853<br/>7772<br/>7875<br/>7835<br/>7906<br/>7840<br/>7832<br/>7966<br/>7722<br/>7809<br/>7823<br/>7822<br/>7796<br/>7724<br/>7860<br/>7846<br/>7837<br/>7872<br/>7884<br/>7779<br/>7773<br/>7755<br/>7694<br/>7793<br/>7796<br/>7861<br/>7686<br/>7824<br/>7693<br/>7763<br/>7904<br/>7895<br/>7690<br/>7829<br/>7817<br/>7878<br/>7732<br/>7845<br/>7812<br/>7731<br/>7932<br/>8146<br/>7826<br/>7805<br/>7837<br/>7822<br/>7728<br/>7920<br/>7857<br/>7740<br/>7961<br/>7750<br/>7768<br/>7949<br/>7706<br/>7820<br/>7912<br/>7708<br/>7893<br/>7755<br/>7925<br/>7697<br/>7849<br/>7736<br/>7751<br/>7827<br/>7738<br/>7786<br/>7817<br/>7895<br/>7904<br/>7723<br/>7894<br/>7929<br/>7861<br/>7880<br/>7875<br/>7652<br/>7813<br/>7862<br/>7755<br/>7859<br/>7969<br/>7813<br/>7848<br/>7974<br/>7822<br/>7671<br/>7674</div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> <td class="wsite-multicol-col" style="width:43.64224137931%; padding:0 15px;">
<div><div class="wsite-multicol"><div class="wsite-multicol-table-wrap" style="margin:0 -15px;">
<table class="wsite-multicol-table">
<tbody class="wsite-multicol-tbody">
<tr class="wsite-multicol-tr">
<td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Guessing entropy of the pool</strong><br/>2492.49<br/>2579.67<br/>2296.24<br/>2259.22<br/>2063.63<br/>2279.34<br/>2531.83<br/>2373.23<br/>2433.03<br/>2152.14<br/>2410.49<br/>2548.3<br/>2501.83<br/>﻿149.431﻿<br/>2172.6<br/>2287.59<br/>2406.05<br/>2396.62<br/>2104.17<br/>1901.98<br/>2433.13<br/>2429.94<br/>1938.19<br/>2313.25<br/>1658.93<br/>2168.08<br/>2334.52<br/>2045.89<br/>2280.03<br/>2102.1<br/>2399.94<br/>2241.2<br/>2145.95<br/>2344.72<br/>2432.79<br/>2543.26<br/>2139.27<br/>2368.65<br/>2381.07<br/>2333.21<br/>1864.91<br/>2254.54<br/>1691.96<br/>2023.07<br/>2541.11<br/>2268.69<br/>2337.6<br/>2073.39<br/>1880.68<br/>2278.71<br/>2364.31<br/>2330.13<br/>2422.32<br/>2044.6<br/>1640.54<br/>2498.21<br/>2337.72<br/>2343.67<br/>2262.12<br/>2217.1<br/>2254.87<br/>2117.3<br/>2086.09<br/>1051.8<br/>2348.34<br/>﻿127.743﻿<br/>2083.03<br/>2539.55<br/>2312.98<br/>2499.91<br/>2376.25<br/>2132.02<br/>2168.81<br/>2369.19<br/>2251.13<br/>2304.26<br/>2270.72<br/>2413.42<br/>2220.25<br/>2232.27<br/>1951.99<br/>2570.2<br/>2448.16<br/>2422.05<br/>2385.26<br/>2258.31<br/>2267.15<br/>2323.96<br/>2277.5<br/>1662.81<br/>2108.01<br/>2318.99<br/>2552.5<br/>2215.18<br/>2105.23<br/>2325.58<br/>2435.1<br/>2295.89<br/>2448.32<br/>2437.44<br/>2097.57<br/>1934.18<br/>2032.76<br/>2025.48<br/>2241.76<br/>2586.39<br/>2242.08<br/>2261.55<br/>2392.72<br/>2172.62<br/>2275.08<br/>2213.7<br/>2198.72<br/>2487.24<br/>2231.2<br/>2160.63<br/>2173.56<br/>1703.89<br/>2136.2<br/>2600.56<br/>2178.71<br/>2029.4<br/>1708.16<br/>2294.11<br/>2370<br/>2288.76<br/>2325.59<br/>1746.71<br/>2312.23<br/>2273.67<br/>2481.08<br/>2449.06<br/>2573.22<br/>2143.61<br/>1983.9<br/>2210.14<br/>1746.2<br/>2313.03<br/>2389.22<br/>﻿﻿652.968﻿﻿<br/>2477.86<br/>2437.25<br/>2333.01<br/>2366.59<br/>2231.43<br/>2326.75<br/>﻿973.749﻿<br/>2461.9<br/>2220.65<br/>2331.09<br/>1757.1<br/>2058.41<br/>2347.33<br/>2274.99<br/>1028.43<br/>2372.34<br/>1884.36<br/>2417.59<br/>2339.53<br/>2280.01<br/>2185.06<br/>2393.79<br/>2389.29<br/>2307.7<br/>2344.2<br/>2221.08<br/>2391.29<br/>2484.44<br/>2294.73<br/>1945.62<br/>2134<br/>1947.36<br/>2530.77<br/>2355.78<br/>2495.01<br/>2218.59<br/>2229.88<br/>2532.13<br/>2251.4<br/>2022.26<br/>﻿528.102﻿<br/>2491.6<br/>2204.38<br/>2228.95<br/>﻿343.376﻿<br/>2485.31<br/>2423.89<br/>2303.37<br/>2413.59<br/>2318.98<br/>1983.78<br/>2282.79<br/>2410.65<br/>2314.79<br/>2198.74<br/>2246.29<br/>2197.7<br/>2331.07<br/>2000.11<br/>1969.36<br/>2406.52<br/>2021.61<br/>2402.89<br/>2153.66<br/>2034.37<br/>2453.37<br/>2170.14<br/>2413.26<br/>2370.65<br/>2271.2<br/>2384.69<br/>2363.41<br/>2416.1<br/>2360.53<br/>2514.61<br/>2061.25<br/>1900.22<br/>2147.4<br/>2136.34<br/>2502.94<br/>1945.03<br/>2374.02<br/>2549.79<br/>2271.35<br/>2063.53<br/>2319.73<br/>2192.53<br/>2512.58<br/>2381.02<br/>2254.14<br/>2440.66<br/>1772.53<br/>1922.27<br/>2476.02<br/>2299.99<br/>2213.99<br/>2341.53<br/>2266.92<br/>1826.75<br/>2186.95<br/>2468.67<br/>2219.94<br/>2082.09<br/>2241.88<br/>2354.06<br/>2378.36<br/>1789.43<br/>2317.02<br/>2238.31<br/>1694.76<br/>2200.24<br/>2115.07<br/>1956.37<br/>2034.19<br/>2473.39<br/>2273.04</div>
</td> <td class="wsite-multicol-col" style="width:50%; padding:0 15px;">
<div class="paragraph" style="text-align:center;"><strong>Detailed information</strong><br/><strong>of the pool</strong><strong></strong><br/>0.txt(detailedexplanation)<br/>1.txt(detailed explanation)<br/>2.txt(detailed explanation)<br/>3.txt<br/>4.txt<br/>5.txt<br/>6.txt<br/>7.txt<br/>8.txt<br/>9.txt<br/>10.txt<br/>11.txt<br/>12.txt<br/>13.txt<br/>14.txt<br/>15.txt<br/>16.txt<br/>17.txt<br/>18.txt<br/>19.txt<br/>20.txt<br/>21.txt<br/>22.txt<br/>23.txt<br/>24.txt<br/>25.txt<br/>26.txt<br/>27.txt<br/>28.txt<br/>29.txt<br/>30.txt<br/>31.txt<br/><a href="{{ site.url }}{{ site.baseurl }}/uploads/fuzzyverifier/32.txt">32</a>.txt<br/>33.txt<br/>34.txt<br/>35.txt<br/>36.txt<br/>37.txt<br/>38.txt<br/>39.txt<br/>40.txt<br/>41.txt<br/>42.txt<br/>43.txt<br/>44.txt<br/>45.txt<br/>46.txt<br/>47.txt<br/>48.txt<br/>49.txt<br/>50.txt<br/>51.txt<br/>52.txt<br/>53.txt<br/>54.txt<br/>55.txt<br/>56.txt<br/>57.txt<br/>58.txt<br/>59.txt<br/>60.txt<br/>61.txt<br/>62.txt<br/>63.txt<br/>64.txt<br/><u>65.txt</u><br/>66.txt<br/>67.txt<br/>68.txt<br/>69.txt<br/>70.txt<br/>71.txt<br/>72.txt<br/>73.txt<br/>74.txt<br/>75.txt<br/>76.txt<br/>77.txt<br/>78.txt<br/>79.txt<br/>80.txt<br/>81.txt<br/>82.txt<br/>83.txt<br/>84.txt<br/>85.txt<br/>86.txt<br/>87.txt<br/>88.txt<br/>89.txt<br/>90.txt<br/>91.txt<br/>92.txt<br/>93.txt<br/>94.txt<br/>95.txt<br/>96.txt<br/>97.txt<br/>98.txt<br/>99.txt<br/>100.txt<br/>101.txt<br/>102.txt<br/>103.txt<br/>104.txt<br/>105.txt<br/>106.txt<br/>107.txt<br/>108.txt<br/>109.txt<br/>110.txt<br/>111.txt<br/>112.txt<br/>113.txt<br/>114.txt<br/>115.txt<br/>116.txt<br/>117.txt<br/>118.txt<br/>119.txt<br/>120.txt<br/>121.txt<br/>122.txt<br/>123.txt<br/>124.txt<br/>125.txt<br/>126.txt<br/>127.txt<br/>128.txt<br/>129.txt<br/>130.txt<br/>131.txt<br/>132.txt<br/>133.txt<br/>134.txt<br/>135.txt<br/>136.txt<br/>137.txt<br/>138.txt<br/><u>139.txt</u><br/>140.txt<br/>141.txt<br/>142.txt<br/>143.txt<br/>144.txt<br/>145.txt<br/><u>146.txt</u><br/>147.txt<br/>148.txt<br/>149.txt<br/>150.txt<br/>151.txt<br/>152.txt<br/>153.txt<br/>154.txt<br/>155.txt<br/>156.txt<br/>157.txt<br/>158.txt<br/>159.txt<br/>160.txt<br/>161.txt<br/>162.txt<br/>163.txt<br/>164.txt<br/>165.txt<br/>166.txt<br/>167.txt<br/>168.txt<br/>169.txt<br/>170.txt<br/>171.txt<br/>172.txt<br/>173.txt<br/>174.txt<br/>175.txt<br/>176.txt<br/>177.txt<br/>178.txt<br/>179.txt<br/><u>180.txt</u><br/>181.txt<br/>182.txt<br/>183.txt<br/><u>184.txt</u><br/>185.txt<br/>186.txt<br/>187.txt<br/>188.txt<br/>189.txt<br/>190.txt<br/>191.txt<br/>192.txt<br/>193.txt<br/>194.txt<br/>195.txt<br/>196.txt<br/>197.txt<br/>198.txt<br/>199.txt<br/>200.txt<br/>201.txt<br/>202.txt<br/>203.txt<br/>204.txt<br/>205.txt<br/>206.txt<br/>207.txt<br/>208.txt<br/>209.txt<br/>210.txt<br/>211.txt<br/>212.txt<br/>213.txt<br/>214.txt<br/>215.txt<br/>216.txt<br/>217.txt<br/>218.txt<br/>219.txt<br/>220.txt<br/>221.txt<br/>222.txt<br/>223.txt<br/>224.txt<br/>225.txt<br/>226.txt<br/>227.txt<br/>228.txt<br/>229.txt<br/>230.txt<br/>231.txt<br/>232.txt<br/>233.txt<br/>234.txt<br/>235.txt<br/>236.txt<br/>237.txt<br/>238.txt<br/>239.txt<br/>240.txt<br/>241.txt<br/>242.txt<br/>243.txt<br/>244.txt<br/>245.txt<br/>246.txt<br/>247.txt<br/>248.txt<br/>249.txt<br/>250.txt<br/>251.txt<br/>252.txt<br/>253.txt<br/>254.txt<br/>255.txt</div>
</td> </tr>
</tbody>
</table>
</div></div></div>
</td> </tr>
</tbody>
</table>
</div></div></div>
<div><div style="height: 20px; overflow: hidden; width: 100%;"></div>
<hr class="styled-hr" style="width:100%;"/>
<div style="height: 20px; overflow: hidden; width: 100%;"></div></div>
<h2 class="wsite-content-title" style="text-align:left;">5. Subtletiesrevealed from the above four experiments</h2>
<div class="paragraph" style="text-align:left;">In the above four experiments, only top 2 million CSDN dataset canguaranteethateveryguessing entropy ofitspoolsislarger than 1024, while the top 1 million CSDN dataset is unable to provide such a security level. This implies that, to provide the expected level of security, theunderlyingpassword space of theseuser selected passwords shall be large enough. In addition, top 2 millionCSDN dataset is desired, whiletop 2millionRockYou dataset is insufficient. This implies that, besides a requirementfor search space size of the passwords,there is also a requirement for the strength ofindividual passwords. The difference in password strength between these two password dataset is mainly caused by the varied password creation policies. More specifically, Rockyou only enforces that a user selected password is of length no less than 5 characters, while CSDN requires that user passwords are at least 6 characters long. Another contributing factor is that Rockyou passwords are used to protect social networking accounts and its users are mainly non-professionals, while CSDN passwords are used to protect personal technical notes and blogs and its users are mainly programmers. <br/> After all, we have shown that, there do exist a real-life password dataset (i.e., the CSDN dataset) that satisfies a specified level of secuity, which further demonstrates the feasibility of our "Fuzzy Verifier".<br/></div>
<div><div style="height: 20px; overflow: hidden; width: 100%;"></div>
<hr class="styled-hr" style="width:100%;"/>
<div style="height: 20px; overflow: hidden; width: 100%;"></div></div>
<h2 class="wsite-content-title" style="text-align:left;">6. Acknowledgements</h2>
<div class="paragraph" style="text-align:left;">    We would like to acknowledge the contributions that Dr. Chen Zhu and Qianchen Gu made in thedevelopment of the password statistics software tool used in the analysis of password dataset in this paper. We are also grateful to Dr. Haibo Chen for some constructive suggestions.</div>
<h2 class="wsite-content-title" style="text-align:left;">7. References</h2>
<div class="paragraph" style="text-align:left;">[1] M. Dell’Amico, P. Michiardi, and Y. Roudier, “Password strength: anempirical analysis,” in Proc. INFOCOM 2010.IEEE, 2010, pp. 1–9.<br/>[2] J. Bonneau, “The science of guessing: Analyzing an anonymizedcorpus of 70 million passwords,” in Proc. IEEE S&amp;P 2012.IEEEComputer Society, 2012, pp. 538–552.<br/>[3]W.Burr, D.Dodson, R.Perlner, W.Polk, S.GuptaandE.Nabbus: NISTSP800-63-2 – electronic authentication guideline. Tech. rep., National Instituteof Standards and Technology, Reston, VA (August 2013), doi:http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-2.pdf<br/>[4]C. Allan, 32 million Rockyou passwords stolen, available at http://www.hardwareheaven.com/news.php?newsid=526 (Dec. 2009).<br/>[5]Dazzlepod Inc., CSDN 6 million cleartext passwords, online news, Available at http://dazzlepod.com/csdn/ (Mar. 2013).<br/>[6] J. L. Massey, “Guessing and Entropy,” in Proceedings of the1994 IEEE International Symposium on Information Theory,1994, p. 204-208.<br/>[7]D., Anupam, J. Bonneau, M. Caesar, A. Nikita and X.F.Wang.Tangled Web of Password Reuse. Proc. NDSS 2014,San Diego, CA, USA,23-26 February 2014.<br/>[8]D. Florencio, C. Herley, A large-scale study of web password habits, in: Proceedings ofWWW 2007, ACM, 2007, pp. 657–666.<br/>[9] M. Alsaleh, M. Mannan, and P. Van Oorschot, “Revisiting defensesagainst large-scale online password guessing attacks,” IEEE Trans.Depend. Secur. Comput., vol. 9, no. 1, pp. 128–141, 2012.</div>
<div><div style="height: 20px; overflow: hidden; width: 100%;"></div>
<hr class="styled-hr" style="width:100%;"/>
<div style="height: 20px; overflow: hidden; width: 100%;"></div></div>
</div>
</div></div></div>
