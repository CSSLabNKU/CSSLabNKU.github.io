# `home.md` 复查结果（更新版）

检查对象：`_pages/home.md`，当前共 533 行。  
本清单只记录当前仍存在的问题，不修改 `home.md`。

## 当前整体状态

- UTF-8 中文显示正常。
- `a`、`u`、`strong`、`span`、`em`、`div`、`figure` 标签数量全部配对。
- 所有使用 `site.baseurl` 的本地链接和图片目前都能在仓库中找到对应文件。
- 此前的 Zaikei 链接、错误序数词、被拆开的年份链接、`228-442`、`breakthough` 等问题已经修复。

## 一、建议优先处理

### 1. 第 57 行仍有明显编辑残留

```text
USENIX Security'23abc
IEEE TDSC'20 a~d
```

`abc` 和 `a~d` 会直接显示在首页。如果不是用于区分多篇论文的正式记法，建议删除或改成清楚的表达。

### 2. 第 90 行 Daily Mail 链接包含空格

URL 中有：

```text
Password-Researchers- warn-internet-users
```

`Researchers-` 后的空格可能导致链接被浏览器编码成 `%20`，从而打开错误地址。链接文字 `Dailmail` 也应为 `Daily Mail`。

### 3. 第 529–533 行仍是过时且重复的履历

第 529 行仍写：

```text
2018-today, PostDoc in Information Security at Peking University
```

这与顶部第 16 行的 `2019–Now, Professor, Nankai University` 冲突。建议删除第 528–533 行旧履历，或按顶部内容统一更新。

同一段还存在：

- `Supervised by and Cooperate with` 语法与时态不一致。
- `today` 与顶部使用的 `Now` 不一致。
- 第 532 行 `Yuango Guo` 建议核对姓名拼写。

### 4. 第 307 行会议年份不一致

当前为：

```text
21st EAI International Conference ... (SecureComm 2024)
```

但链接指向 `/2025/`，而第 316 行又单独列出了 `20th ... SecureComm 2024`。因此第 307 行很可能应显示 `SecureComm 2025`。

### 5. 首页与 publications 页面数据不一致

建议核对后统一：

- 第 62 行 IEEE S&P 2026 页码：`2977-2996`；publications 页面为 `1915-1934`。
- 第 65 行 USENIX Security 2025 页码：`1-24`；publications 页面为 `7799-7818`。
- 第 80 行 USENIX Security 2019 接受率：`113/719=15.7%`；publications 页面为 `112/719=15.6%`。
- 第 87 行写 CDF-Zipf 被 `120 studies` 采用；publications 页面写 `270 studies`。

## 二、明确的拼写与用词问题

- 第 18 行：`PhD.` 建议统一成 `Ph.D.` 或 `PhD`。
- 第 29 行：`related area` → `related areas`。
- 第 29 行：链接文字 `researches` 不自然，建议 `research` 或 `publications`。
- 第 57 行：`Our work gets 8000+ citations` → `Our work has received over 8,000 citations`。
- 第 69 行：`winter circle acceptance rate` 很可能应为 `winter cycle acceptance rate`。
- 第 72 行：`Covered by medias like` → `Covered by media outlets such as`。
- 第 83、92 行：`Github` → `GitHub`。
- 第 90 行：`200+ medias` → `200+ media outlets`。
- 第 90 行：`Dailmail` → `Daily Mail`。
- 第 92 行：`June 28-July 01` → 建议 `June 28–July 1`。
- 第 154 行：`10 Phd. recipients` → `10 Ph.D. recipients`。
- 第 500 行：`Intellegence Technology` → `Intelligence Technology`。

## 三、HTML 加粗范围或标点问题

### 第 96 行标题最后一个字母未加粗

当前为：

```html
<strong>... Attacks, Principle and Solution</strong>s.
```

最终的 `s` 在 `<strong>` 外，应把完整单词 `Solutions` 放入标签内。

### 第 97 行引号和结尾标点不自然

结尾为：

```text
Article Selection Celebrating Computer Science Research in China";)
```

分号、引号与右括号的排列比较突兀，建议整理为完整句子后再关闭括号。

### 第 94 行部分引文的标签嵌套不统一

`important observation` 后的逗号位于加粗区域内，而前两个引文的标点位置不同。不会破坏页面，但视觉样式略有差别。

### 第 370–371 行括号链接不对称

- 第 370 行：左括号在链接中，右括号在链接外。
- 第 371 行：右括号由一个内容只有 `)` 的单独链接实现。

不会造成标签损坏，但点击范围和下划线显示不自然。

## 四、内容表达建议

- 第 10 行：`27 mins from Beijing` 较口语。
- 第 16 行：`Deputy-director` 通常写作 `Deputy Director`。
- 第 23 行：`Minds are like parachutes, they only function when open.` 是逗号拼接句，建议改用分号或句号。
- 第 23 行：`working on related areas` 更自然的是 `working in related areas`。
- 第 23 行：`perform individually insurmountable experiments`、`have a visit` 表达不自然。
- 第 36 行：`Professors/ Associate Professors/...` 的斜杠空格不统一。
- 第 36 行：`PostDoc` 建议使用 `postdoctoral researchers`。
- 第 36 行：`Ph.D/ Master students` 建议 `Ph.D. and master's students`。
- 第 36 行：`We together do some great work` 表达不自然。
- 第 38 行：`NSF of China` 更正式的写法是 `the National Natural Science Foundation of China (NSFC)`。
- 第 81 行：`Arouse heated discussion` 建议 `Sparked extensive discussion`。
- 第 90 行关于 NIST 标准修订的英文句子语法较生硬，而且属于较强的因果表述，建议谨慎润色。

## 五、视觉一致性问题（可不改）

- 第 9 行中文名为 `汪 定`，中间有空格；如非刻意排版可改成 `汪定`。
- 第 12 行第一个邮箱的分号位于链接内，第二个邮箱却不是链接。
- 第 57 行 Google Scholar 同时出现文字链接和徽章链接，略显拥挤。
- 第 68 行直接展示很长的 Computer Society URL，可以改成 `publisher page` 或 `paper`。
- 第 87 行使用多层连续的 `<strong><span><u><a>`，强调样式较碎。
- 多处混用普通空格和不换行空格（NBSP）。浏览器显示通常正常，但源码维护较困难。
- `pp.1-16` 与 `pp. 1-16`、`Doi` 与 `DOI`、`USENIX` 与 `Usenix` 仍未完全统一。

## 建议处理顺序

1. 删除第 57 行的 `abc`、`a~d` 编辑残留。
2. 修复第 90 行 Daily Mail URL。
3. 删除或更新第 528–533 行旧履历。
4. 核对第 307 行 SecureComm 年份。
5. 统一首页与 publications 页的论文数据。
6. 其余英文和样式问题可以按需处理，不影响页面基本功能。
