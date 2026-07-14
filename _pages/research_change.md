# `research.md` 检查清单

检查对象：`_pages/research.md`（当前共 186 行）  
说明：本文件只记录建议，没有修改 `research.md`。

## 当前整体状态

- UTF-8 编码正常，没有乱码。
- `a`、`u`、`strong`、`div`、`article`、`p`、`style` 标签数量全部配对。
- CSS 网格结构完整，移动端会切换为单列。
- 10 张研究图片在仓库中均存在。

## 一、建议优先处理

### 1. 第 82–114 行的 5 个论文链接路径错误

这些链接目前写成 `/researches/*.pdf`，但文件实际位于 `/uploads/researches/`，当前链接会产生 404。

| 行号 | 当前路径 | 建议路径 |
|---|---|---|
| 82 | `/researches/ieeetifs17_final.pdf` | `/uploads/researches/ieeetifs17_final.pdf` |
| 82 | `/researches/esorics16_final.pdf` | `/uploads/researches/esorics16_final.pdf` |
| 91 | `/researches/asiaccs17_v12.pdf` | `/uploads/researches/asiaccs17_v12.pdf` |
| 105 | `/researches/esorics15conf0827.pdf` | `/uploads/researches/esorics15conf0827.pdf` |
| 114 | `/researches/dsn16v9.pdf` | `/uploads/researches/dsn16v9.pdf` |

建议保持现有 Liquid 前缀，只补上 `/uploads`：

```html
href="{{ site.url }}{{ site.baseurl }}/uploads/researches/文件名.pdf"
```

### 2. 第 114、128、137、151、160、174、183 行仍依赖旧 Weebly 域名

这些外链将页面资源依赖于 `wangdingg.weebly.com`。相应文件在当前仓库的 `/uploads/researches/` 中都有本地副本，建议改为本站链接：

| 行号 | 旧外链文件 | 本地路径 |
|---|---|---|
| 114 | `dsn16v9.pdf` | `/uploads/researches/dsn16v9.pdf` |
| 128 | `infosci14.pdf` | `/uploads/researches/infosci14.pdf` |
| 137 | `wcnc2014.pdf` | `/uploads/researches/wcnc2014.pdf` |
| 137 | `ieeesyst2015.pdf` | `/uploads/researches/ieeesyst2015.pdf` |
| 151 | `comnet14.pdf` | `/uploads/researches/comnet14.pdf` |
| 160 | `ijcs_online_version.pdf` | `/uploads/researches/ijcs_online_version.pdf` |
| 174 | `asiaccs16v7.pdf` | `/uploads/researches/asiaccs16v7.pdf` |
| 174 | `ieeetdsc16_v11.pdf` | `/uploads/researches/ieeetdsc16_v11.pdf` |
| 183 | `tdsc15.pdf` | `/uploads/researches/tdsc15.pdf` |

第 114 行已经同时存在错误的本站链接和 Weebly 链接；修复本站链接后即可删除对 Weebly 的依赖。

### 3. 所有研究图片都缺少 `alt` 文本

第 79、88、102、111、125、134、148、157、171、180 行的 `<img>` 都没有 `alt` 属性。

这会影响无障碍阅读，也会在图片加载失败时缺少说明。建议根据每张图的主题添加简短描述，例如：

```html
<img src="..." alt="Comparison of password distribution models">
```

### 4. 第 174 行疑似复制了不相关的句子

这一段先介绍 2FA 评价指标和 smart-card-loss attack taxonomy，随后突然出现：

```text
We give a negative answer to this question by empirically using two case studies and formally proving it in a widely accepted adversary model.
```

本段前面并没有提出对应问题，而且该句与第 151 行几乎完全相同，很像复制残留。建议核对原意；若无关应删除。

## 二、明确的语法和拼写问题

### 第 91 行

当前：

```text
PINs chosen by English user and Chinese users
```

建议：

```text
PINs chosen by English-speaking and Chinese users
```

同一行还有：

- 分号后的 `By adopting` 不应大写，可改为 `by adopting`。
- `statistic metrics` 应为 `statistical metrics`。

### 第 105 行

- `20 policies mainly from US` → `20 policies mainly from the US`
- `30 ones from mainland China` → `30 from mainland China`
- `fail to serve their purposes, especially vulnerable to ...` 缺少连接结构，可改为 `fail to serve their intended purposes and are especially vulnerable to ...`

### 第 114 行

- `reliable feedbacks` → `reliable feedback`，此处 `feedback` 通常不可数。
- 名称同时写作 `fuzzyPSM` 和 `FuzzyPSM`，建议统一大小写。
- 冒号后的 `Generally` 不必大写。
- `..., instead they reuse ...` 是逗号拼接句，建议在 `instead` 前使用分号或句号。

### 第 128 行

- `the ﬁrst one that deﬁnes` 可更自然地写成 `the first work to define`。
- `user un-traceability` 通常写作 `user untraceability`。
- `de-synchronization attack` 通常写作 `desynchronization attacks` 或根据论文原文统一。

### 第 137 行

```text
an  new 2FA scheme
```

应为：

```text
a new 2FA scheme
```

其中还包含两个连续空格。

### 第 151 行

加粗内容目前是一个不自然的间接疑问句：

```text
Under ..., whether it is possible to construct ...?
```

建议直接改成问题：

```text
Under the conditional non-tamper-resistance assumption for smart cards, is it possible to construct ...?
```

另外：

- `light-weight` 通常写作 `lightweight`。
- `by empirically using two case studies` 不自然，可用 `through two empirical case studies`。

### 第 160 行

- `resist against ofﬂine password guessing attack` → `resist offline password-guessing attacks`。
- `non-tamper resistance assumption` 建议统一为 `non-tamper-resistance assumption`。
- `at least two exponentiation ... operations` 应为 `at least two exponentiation operations`。
- `respectively elliptic curve point multiplication` 的括号结构不自然，建议根据论文原意重写。

### 第 174 行

```text
The effectiveness of our refinements are tested
```

主语是单数 `effectiveness`，应为：

```text
The effectiveness of our refinements is tested
```

更自然的版本是：

```text
We evaluate the effectiveness of these refinements by comparing 34 representative two-factor authentication schemes.
```

另外：

- `Particularly` 在这里建议使用 `In particular`。
- `For a better metric and new scheme see our ...` 建议在 `scheme` 后加逗号。

### 第 183 行

```text
the fundamental question: whether or not ...?
```

冒号后如果保留间接疑问句，末尾不宜使用问号；或者将其改成直接问题：

```text
the following fundamental question: Are there inherent limitations ...?
```

## 三、标题、URL 与命名问题

### 页面名称使用 `Researches`

第 2 行标题是：

```text
Researches - Welcome ...
```

英文导航或栏目名称通常使用不可数名词 `Research`，建议改为：

```text
Research - Welcome ...
```

第 6 行 permalink 为 `/researches/`。这不属于语法错误，而且修改 URL 可能破坏现有链接；如果要改成 `/research/`，建议同时设置重定向或保留旧地址。

### 自定义元素 `pubtit` 没有实际使用

CSS 第 53–56 行定义了：

```css
.publication-card__body pubtit
```

但正文中没有 `<pubtit>` 元素，因此这段规则当前不起作用，可以删除，或者实际使用相应元素。更推荐使用标准 HTML 类，而不是自定义 `pubtit` 标签。

## 四、视觉与无障碍建议

- 第 79 行 `<img .../>`，其余图片使用 `<img ... />`；只是不一致，不影响显示。
- 第 82 行链接结构为 `<u><a>...</a>; </u>and<u><a>...</a></u>`，分号和 `and` 的下划线范围不一致，视觉上会断开。
- 多个论文链接使用 `target="_blank"`，但没有 `rel="noopener noreferrer"`。现代浏览器风险较低，但仍建议补充。
- 所有卡片正文都是一个很长的段落。移动端能正常显示，但可以考虑把论文链接单独放在段落末尾或卡片底部，提高可扫描性。
- `.publication-card__image` 使用固定高度 `290px`，移动端为 `260px`；图片比例差异大时会出现较多留白，但 `object-fit: contain` 能避免裁剪，因此不算功能错误。
- 标题用 Markdown `###`，卡片没有独立标题元素。若考虑语义结构和屏幕阅读器，可以给每张卡片增加 `<h4>` 标题。

## 五、Unicode 合字

第 105、114、128、137、160、174、183 行含有 `ﬁ` 或 `ﬂ` 合字，例如：

- `high-proﬁle`
- `ﬁrst`
- `deﬁnes`
- `identiﬁed`
- `sacriﬁcing`
- `ofﬂine`
- `fulﬁlling`
- `deﬁnite`

网页通常能正常显示，但会影响全文搜索、复制和字体兼容性。建议替换成普通的 `fi`、`fl`。

## 六、可以暂时不处理

以下不会影响页面基本功能：

- `TIFS'17`、`ESORICS'16` 等会议/期刊缩写的引号风格。
- `2FA scheme` 与 `two-factor authentication scheme` 混用。
- `smart-card-based`、`smart card loss` 等复合词连字符风格不统一。
- 图片卡片之间文字长度不一致，导致同一行卡片高度不同；CSS Grid 会正常处理。

## 建议处理顺序

1. 把 5 个 `/researches/*.pdf` 修成 `/uploads/researches/*.pdf`。
2. 将 Weebly PDF 外链替换为已有的本站副本。
3. 给 10 张图片添加 `alt` 文本。
4. 核对并删除第 174 行疑似复制残留的句子。
5. 修复第 91、105、114、128、137、151、160、174、183 行的英文问题。
6. 最后再处理 `Researches`、Unicode 合字和视觉一致性。
