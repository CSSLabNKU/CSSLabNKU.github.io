# `fuzzyverifier.md` 检查结果

检查对象：`D:\cssnku.github.io\_pages\fuzzyverifier.md`

说明：本次只检查，没有修改原文件。下面的行号对应当前版本。

## 总体结论

当前文件存在需要优先修复的 HTML 结构问题，暂时不建议直接视为“没有大问题”。表格、表格行、单元格、链接、`span`、粗体和下划线标签本身能够配对，本地图片、PDF 和文本文件也都存在；主要问题是多个段落和最外层容器缺少 `</div>`，浏览器只能依靠容错机制猜测页面结构，可能造成后续内容继承错误样式、布局错位，或者再次把闭合标签显示成普通文字。

## 一、必须处理：HTML 结构

### 1. 文件末尾仍有 15 个未闭合的 `<div>`

未闭合的开始标签位于：

- 第 93 行：最外层 `.fuzzyverifier-archive`。
- 第 94 行：`.fuzzyverifier-related-paper`。
- 第 97 行：`Ethics considerations` 段落。
- 第 101 行：`Fuzzy Verifier` 主说明段落。
- 第 108 行：`Experimental 1` 标题及说明段落。
- 第 268 行：实验 1 的 `Guessing entropy...` 标题段落。
- 第 360 行：`Experimental 2` 段落。
- 第 401、402 行：`Experimental 3` 的外层标题和正文段落。
- 第 443 行：`Experimental 4` 段落。
- 第 486、487 行：第 5 节标题和正文段落。
- 第 490、491 行：第 6 节标题和正文段落。
- 第 492 行：第 7 节标题/引用区域。

文件最后只有两个 `</div>`，不足以关闭上述容器。建议逐段在语义结束位置补齐，而不是把 15 个 `</div>` 全部堆到文件末尾，否则虽然数量能够相等，嵌套关系仍然不正确。

### 2. 横线和后续章节被包含进前一个段落

例如：

- 第 97 行的 Ethics 段落没有在第 98 行横线之前结束。
- 第 101 行的 Fuzzy Verifier 段落没有在第 106 行横线之前结束。
- 第 486–492 行的第 5、6、7 节互相嵌套，而不是三个并列章节。

这会让 `<hr>`、空白块和后续标题继承 `.paragraph` 的属性，并可能影响页面间距。

### 3. Related paper 容器未闭合

第 94 行的 `.fuzzyverifier-related-paper` 没有在论文标题和两个 PDF 链接之后关闭。这样 flex 布局可能继续影响后面的横线和正文。这也是页面顶部最容易出现异常换行或布局串联的位置。

## 二、明显的文字粘连和排版问题

以下内容看起来是从旧网页清理标签时把空格一起删掉了，建议恢复正常单词间距：

- 第 361 行：`Theminimumpassword numberof` → `The minimum password number of`；`themaximumis` → `the maximum is`。
- 第 362 行：`Theminimum guessing expectationof` → `The minimum guessing expectation of`；`themaximumis` → `the maximum is`；`fails toguarantee` → `fails to guarantee`。
- 第 487 行有多处：
  - `canguaranteethateveryguessing entropy ofitspoolsislarger`；
  - `theunderlyingpassword space`；
  - `theseuser selected passwords`；
  - `top 2 millionCSDN`；
  - `whiletop 2millionRockYou`；
  - `requirementfor`；
  - `strength ofindividual passwords`。
- 第 491 行：`inthedevelopment` → `in the development`。
- 第 495 行：`2012.IEEE` → `2012. IEEE`。
- 第 496 行：`W.Burr`、`D.Dodson`、`R.Perlner`、`W.Polk`、`S.GuptaandE.Nabbus`、`Instituteof` 均缺少空格。
- 第 500 行：`D., Anupam` 的作者姓名顺序/标点可疑；`X.F.Wang.Tangled`、`2014,San`、`USA,23-26` 缺少空格。
- 第 501 行：`Proceedings ofWWW` → `Proceedings of WWW`。
- 第 502 行：`defensesagainst`、`Trans.Depend.` 缺少空格。

## 三、英文语法、拼写和标点问题

以下只列较明显的项目，不涉及学术观点或数据核验：

- 第 101 行：`even the smart card can be tampered` 建议改为 `even if the smart card is tampered with`。
- 第 101 行：`comes at the prices of security` 应为 `comes at the price of security`。
- 第 101 行：`is uniformed drawn` 应为 `is uniformly drawn`。
- 第 101 行：`|D|=1000,000` 数字分组不规范，通常写为 `1,000,000`。
- 第 101 行：`</b>.As`、`[9].In` 两处句号后缺少空格。
- 第 102 行：`How many password finally remained` 建议为 `How many passwords finally remain`。
- 第 102 行：`what's the character(s) that are unlikely to be hold by` 语法不自然，建议整体重写。
- 第 103 行：`two large dataset` → `two large datasets`；`such dataset are` → `such datasets are`。
- 第 103 行：`Each of the entry` → `Each entry` 或 `Each of the entries`。
- 第 109 行：正文说明被固定为 `font-size:12px`，与“尽量采用网站默认字号”的标准不一致。
- 第 361–362 行：除了粘连问题，还有 `password candidate` 应考虑复数 `password candidates`。
- 第 446 行：`over whelming` → `overwhelming`；`guess entropys` → `guessing entropies`。
- 第 487 行：`password dataset` 多处应为 `password datasets`；`secuity` → `security`。
- 第 474 行：`detailedexplanation` → `detailed explanation`。
- 第 104 行：`dataset(i.e.,` 前缺少空格，应为 `dataset (i.e.,`。
- 文中使用了中文双破折号形式 `——` 连接英文句子；如果全文采用英文标点，建议统一为 em dash `—`。

## 四、实验 1 数据展示中疑似缺少换行

第 144–165 行的密码列里，以下项目之间缺少 `<br/>`，网页上会连在同一行：

- `princess` 与 `rockyou`；
- `1234567` 与 `12345678`；
- `654321` 与 `Qwerty`。

这会导致密码列与旁边的计数、哈希值和密码池链接发生纵向错位，属于实际布局问题。

## 五、样式与布局建议

### 1. 旧 Weebly 多层表格结构过重

当前有 16 张嵌套表格、103 个 `<div>`，并保留大量：

- `.wsite-multicol-*` 类名；
- `margin:0 -15px`；
- `padding:0 15px`；
- 很长的小数百分比宽度；
- 空白 `<td>`。

这些结构目前仍可表达多列数据，但维护困难，移动端主要依靠 `min-width: 760px` 和横向滚动。若以后继续整理，建议把每组实验改为较直接的四列表格，而不是多层表格套表格。

### 2. 行内样式仍然很多

文件中约有 138 处 `style=`。大部分是旧布局宽度、边距和对齐。颜色强调可以保留，但重复的 `text-align`、宽度和 padding 更适合收进统一 CSS 类。

### 3. 非标准 `color` 属性

- 第 94 行：`<strong color="#5a5a5a">`。
- 第 97 行：`<strong color="#350df8">`。

`color` 不是 `<strong>` 的标准 HTML 属性，浏览器通常不会按预期应用。应使用 CSS 或 `<span style="color: ...">`。这里只记录，不修改。

### 4. 标题语义不足

Experimental 1–4、第 5–7 节都使用普通 `<div><strong>...</strong>`，没有使用 Markdown 标题或 `<h2>/<h3>`。视觉上可以依赖粗体，但页面结构、可访问性和目录识别较弱。

### 5. Related paper 的固定字号

CSS 中 Related paper 正文为 `14px`、标签为 `18px`。如果完全遵循网站默认字号，可考虑删除这两个固定值；如果只是为了保持顶部一行的紧凑布局，则可以保留。

## 六、链接与资源检查

检查结果正常：

- 顶部图片 `images/1399478294.jpg` 存在。
- 两个 PDF 文件存在。
- 当前页面引用的本地 `.txt` 文件均存在。
- 111 个 `<a>` 开始/结束标签能够配对。
- 没有发现乱码替代字符 `�`。

需要人工确认但不一定是错误：

- 部分显示为 `26.txt`、`27.txt` 等的文本，只把数字放在链接内，`.txt` 位于链接外；视觉通常正常，但链接范围不统一。
- 很多 `41.txt`–`255.txt` 只是普通文字，没有链接。这与正文所说“只上传 10% 文件”可能一致，不应在未确认的情况下自动补链接。

## 建议处理顺序

1. 先逐段补齐 15 个未闭合的 `</div>`，确保章节并列、最外层容器只在末尾关闭。
2. 补回实验 1 密码列中缺失的三个换行。
3. 修复明显的英文单词粘连和拼写错误。
4. 再决定是否精简旧 Weebly 表格及 138 处行内样式。

