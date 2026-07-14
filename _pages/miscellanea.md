---
title: "Miscellanea - Welcome to Ding Wang's Homepage -- Password Cryptography"
layout: publications
excerpt: ""
sitemap: false
permalink: /miscellanea/
---

# 计算机各类期刊、会议总结

A. 信息安全国际学术会议讨论
 (Part of this blog is my personal opinion,  while part of it comes from http://loccs.sjtu.edu.cn/typecho/index.php/category/conf/.   部分为个人见解，部分转自：http://loccs.sjtu.edu.cn/typecho/index.php/category/conf/,  一介学生眼光，三五好友讨论结果，不妥不当之处难免，欢迎批评指正。 )
 
信息安全是一个比较复杂的主题，包括了传统的密码学、安全攻击等内容，同时又包括了大量和操作系统、网络、计算机体系结构、硬件（不仅限于计算机，包括各类计算设备，智能卡等等），甚至金融、法律相关的内容，因此，在这些领域，同样有很多顶级学术会议值得我们关注。众所周知，期刊会议的档次无法代表论文的质量，只是在一流会议中出现一流成果的可能性要大一些。很多有开创性的一流成果没有发表在一流会议上，在一流会议中也不并少见长像好看、但实际没什么意义的文章。无论如何，了解会议的大致水平和特点，对初学者还是很有用的 (The true value of this list, we hope, mainly lies in providing some preliminary guidance for NEW guys in Information Security, and particularly, for new students of our group.)。

首先是信息安全四大安全会议+ 三大密码会（美密，欧密，亚密）
S&P IEEE Symposium on Security and Privacy
每年11月截稿，第二年5月开会，永远在美国开会
CCS ACM Conference on Computer and Communications Security
每年5月截稿，同年10月开会，永远在美国开会
USENIX Security Usenix Security Symposium （System-oriented）
每年2月截稿，同年8月开会，永远在美国开会
NDSS ISOC Network and Distributed System Security （大陆迄今录用最少,  引用最好）
每年8月截稿，第二年2月开会，永远在美国开会

CRYPTO  International Cryptology Conference
美密会 每年2月截稿，同年8月开会，永远在美国开会
EUROCRYPT Annual International Conference on the Theory and Applications of Cryptographic Techniques
欧密会 每年10月截稿，翌年5月开会，永远在欧洲开会
ASIACRYPT Annual Int Conf on Theory and Application of Cryptology and Information Security （录用率比美密、欧密低）
亚密会 每年5月截稿，同年12月开会，永远在亚洲开会
虽然这些会议名称具有明显的地区性，但其中的文章则是开放的，像王小云老师的关于HASH方面著名成果就是首发在CRYPRO 2004上.

上面7个会议在不同的排名版本里，顺序可能不同，甚至是否算top 会议还有争论。基本没有争议的是 Top 6:  IEEE S&P, ACM CCS,   Eurocrypt , Crypto, USENIX Security  and   NDSS . 详见
http://jianying.space/conference-ranking.html    
https://mp.weixin.qq.com/s/6Bd5eg9TJw5PL_Qtpq8eLg 
http://faculty.cs.tamu.edu/guofei/sec_conf_stat.htm
​https://www.quora.com/What-are-the-top-computer-security-conferences


接下来，根据 http://jianying.space/conference-ranking.html    和 https://mp.weixin.qq.com/s/Zx3CsLvxnLDFFlDc4B_sIw的统计，我认为如下一些安全会议是很好的，刚好也是四个安全会+三个密码会：

ACSAC Annual Computer Security Applications Conference
ESORICS European Symposium on Research in Computer Security 
CHES Annual Conference on Cryptographic Hardware and Embedded Systems
DSN  IFIP/IEEE International Conference on Dependable Systems and Networks

 这4个会议目前每年的出席人数基本都稳定在200人以上，投稿量也比较大(200+)，说明大家都比较认可，有较强影响力，而且录用率也控制得很好：历年基本都在20%左右。其中ESORICS这个会永远在欧洲开，2017年投稿数达到330篇，创历史新高。

 
如果说上面这四个会偏向安全应用的话，下面这三个会则专注安全理论，里面文章的基础性、长期影响力来看比上面四个会甚至还要好一些：
CSF IEEE Computer Security Foundations Symposium
TCC IACR Theory of Cryptography Conference
PKC IACR International Conference on Practice and Theory of Public-Key Cryptography 

 介绍了上面14个会议，接下来的会议里面，排名最好的应该属于AsiaCCS、PETS和RAID。
AsiaCCS ACM Asia Conference on Information, Computer and Communications Security (2015年6月新更名为Aisa conference)
PETS Privacy Enhancing Technologies
RAID  International Symposium on Research in Attacks, Intrusions and Defenses

AsiaCCS 和 PETS 这两个会相对年轻，从与欧美同行朋友的了解情况看，AsiaCCS 和 PETS 貌似已稳步进入第二阵营。AsiaCCS是ACM近年在亚洲区力挺的一个会，看到一些大牛也在上面发文, 近两年的投稿量都在350+； PETS专注于隐私保护技术，随着人们对隐私的关注，圈子在快速扩大, 投稿量也快速上升，近两年投稿量300+，已显示很好的影响力。RAID 前几年投稿量低于100，近两年改名后（原名International Symposium on Recent Advances in Intrusion Detection)由USENIX出版，投稿量恢复到100以上。


接下来的安全会议在学术界比较知名（我见过的有名的安全研究人员大都愿意把在上面发表过的文章放在自己的主页上的）包括

FC International Conference on Financial Cryptography and Data Security​
ACNS Applied Cryptography and Network Security
FSE Fast Software Encryption
SOUPS ACM Symposium on Usable Privacy and Security 
WiSec ACM Conference on Security and Privacy in Wireless and Mobile Networks
DIMVA Detection of Intrusions and Malware and Vulnerability Assessment


这里面，FC由于密码货币的出现，近几年影响力上升很快；DIMVA在计算机安全攻防上很有影响力，但是由于圈子比较小，投稿篇数比较少(<100), 看上去录用率高一些，RAID引用率要稍微好一些。FSE近年投稿量越来越少，2015年创新低76篇，可能与这个圈子太封闭有关系；ACNS和FC录用率控制得很好，这两个会更偏向密码学一些, 在系统安全方面相对接受的几率相对比较低, ACNS 开会地点离我们较近些，不过这两年ACNS也开始离开亚洲去US、UK开了；WiSec属于后起之秀，投稿量虽然不过百，但论文质量很高，国内目前中的不多。

下面四个安全会中，ISC和SEC属于比较综合型的会议，SecureComm和ICICS 更偏重系统安全、应用安全一些,。ICICS由大陆卿斯汉老师发起，是大陆信息安全走出去的一个难得窗口，文章虽多来自大陆，也有不少引用率很高的文章，2018年的投稿量超过200。
ISC  Information Security Conference
SEC  IFIP International  Information Security and Privacy Conference
SecureComm Security and Privacy for Emerging Areas in Communication Networks 
ICICS International Conference on Information and Communications Security

下面这四个区域性召开的偏密码会议（也接收安全方向的论文），在密码学领域享有一定声誉，也不是很容易中，regular paper 为 LNCS 20页。ACISP是从澳洲发起的比较成功的一个会，每年在Australa 召开，过去有不少经典文章发表在这里，近两年投稿量超过150篇。中密会INSCRYPT近两年的投稿量在90篇左右，INDOCRYPT和ICISC近两年的投稿量在70篇左右。值得一提的是， INSCRYPT 是由信息安全国家重点实验室发起的在中国举办的密码年会。
ACISP Australasian Conference on Information Security and Privacy  澳密会
INSCRYPT International Conference on Information Security and Cryptology 中密会
INDOCRYPT   International Conference on Cryptology in India  印密会
ICISC International Conference on Information Security and Cryptology 韩密会

另外，近年有三个比较有潜力的会议面世，值得关注。尤其是IEEE EuroS&P，这两届论文质量相当不错的说。
 IEEE EuroS&P  IEEE European Symposium on Security and Privacy  (http://www.ieee-security.org/TC/EuroSP2017/)
 IEEE CNS  IEEE Conference on Communications and Network Security  (http://cns2017.ieee-cns.org/)
 ACM CODASPY ACM Conference on Data and Application Security and Privacy

 接下来的一些安全会议都比较小众，可能在中国计算机学会的排名上都出现较少，但是从我个人这几年阅读论文下来，发现这些会议的论文质量相对控制得比较好，而且比较专一，能够保证在某个特定领域的专注度和热门度：

 WOOT USENIX Workshop on Offensive Technologies
 LEET USENIX Workshop on Large-Scale Exploits and Emergent Threats
 HotSec USENIX Workshop on Hot Topics in Security （貌似从2013年开始已经不接受公开投稿）
 SACMAT ACM Symposium on Access Control Models and Technologies
 EUROSEC European Workshop on System Security


 此外，有一些专注于特定领域的学术会议，例如在逆向工程领域有一个最好的会议
 WCRE Working Conference on Reverse Engineerin

在电子取证方面最好的学术会议
 DFRWS Digital Forensics Research Conference

在移动和无线安全上有几个workshop也很好
 SPSM Annual ACM CCS Workshop on Security and Privacy in Smartphones and Mobile Devices（和CCS一起举行）
 MOST MOBILE SECURITY TECHNOLOGIES（和IEEE S&P一起举行）

 在云安全方面
 IEEE CLOUD: IEEE International Conference on Cloud Computing
 ACM SOCC: ACM Symposium on Cloud Computing
 HotCloud: USENIX Workshop on Hot Topics in Cloud Computing
 CCSW: The ACM Cloud Computing Security Workshop
 ICDCS-SPCC: ICDCS Workshop on Security and Privacy in Cloud Computing
 =============================================================
 讲完了安全会议，下面是另外一个重要的关注领域，在我这几年研读论文期间，发现有大量和安全研究密切相关的论文，发表在一些非常顶级的计算机传统领域学术会议上，我凭借读论文的印象将其整理出来，按照系里面毕业要求来排列。这些会议都是历经考验，质量非常过硬，引用率很高的学术会议

OSDI Operating Systems Design and Implementation
 SOSP ACM Symposium on Operating Systems Principles
 POPL ACM-SIGACT Symp on Principles of Prog Langs
 PLDI ACM-SIGPLAN Symp on Prog Lang Design & Impl
 ICSE Intl Conf on Software Engineering
 Mobicom The Annual International Conference on Mobile Computing and Networking
 ASPLOS Architectural Support for Programming Languages and Operating Systems
 NSDI USENIX Symposium on Networked System Design and Implementation
 FSE Foundations of Software Engineering
 PODC Symposium on Principles of Distributed Computing
 ISCA International Symposium on Computer Architecture
 USENIX ATC Usenix Annual Technical Conference
 EuroSys European Conference on Computer Systems
 CGO Code Generation and Optimization
 ISSTA International Symposium on Software Testing and Analysis
 FAST Conference on File and Storage Technologies
 ICDCS International Conference on Distributed Computing Systems
 VEE Virtual Execution Environments
 SAS International Static Analysis Symposium
CC International Conference on Compiler Construction

 例如今年Mobicom就有智能手机安全分析的论文，OSDI几乎每次都会有一些安全研究相关的设计论文，ICDCS在我们参会的时候也听到了很多security research，国外的顶级安全研究团队也经常在Usenix ATC、EuroSys、VEE、ISSTA上发文

 另外还有4个会议的比较，传统的Sigcomm和infocom；新兴的
 MobiSys International Conference on Mobile Systems, Applications and Services
 HotOS Workshop on Hot Topics in Operating Systems
 虽然sigcomm和infocom都是一篇论文就能毕业的要求，但是在文章质量上已经大不如前，而mobisys和hotOS虽然不在列表前列的，但是根据大量网上的讨论显示都已经是有很好的论文质量了。


B. 中国计算机学会CCF推荐国际学术会议和期刊目录
https://www.ccf.org.cn/Academic_Evaluation/NIS/
听业内人士的评价很不错，具有国际水准。现国内很多实验室都以这个为参照，以后就以这个为标准了，节省很多找期刊时间：）。



C .Top  Crypto  and Security Conferences Ranking 
有三个用数据说话、较为客观的信息安全会议排名：一个是I2R的Zhou Jianying老师维护的ranking list，一个是德州农工大学Guo guofei老师的ranking list； 还有一个是Eric Z Ma博士统计的一个会议引用排名的top 300。
。 这两个排名收集了大量的会议历史信息，并不断更新。
http://jianying.space/conference-ranking.html    
https://mp.weixin.qq.com/s/Zx3CsLvxnLDFFlDc4B_sIw
http://faculty.cs.tamu.edu/guofei/sec_conf_stat.htm
http://www.cs.cornell.edu/andru/csconf.html


D .  Security conference DDLs
Security and Privacy Conference Deadlines:   https://sec-deadlines.github.io/ 
Calendar of Events in Cryptology:   https://www.iacr.org/events/?order=submission
CCF Conference Deadlines:  https://ccfddl.github.io/



E.国内信息安全类EI期刊（个人整理，2013版）
1.中文期刊（同时也是一级学报）
《软件学报》
《计算机学报》
《电子学报》
《系统工程理论与实践》
《计算机研究与发展》
《电子与信息学报》
《通信学报》
 2.大学学报
《北京邮电大学学报》
《电子科技大学学报》
《西安电子科技大学学报》
《武汉大学学报（信息科学版）》
《大连理工大学学报》
3.英文期刊
《The Journal of China Universities of Posts and  Telecommunications（中国邮电高校学报）》
《Journal  of Systems Science and Complexity（系统科学与复杂性）》
《Journal of Systems Engineering  and Electronics（系统工程与电子技术）》
 《Journal of Computer Science and Technology》
《Frontiers of Computer Science》
《China Communications》