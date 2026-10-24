# 基督在他的筵席上丰丰富富地喂养我们的灵魂 · 马太福音26章 · 海德堡要理问答主日28
# Christ Richly Feeds Our Souls at His Table · Matthew 26 · Heidelberg Catechism LD 28

## 线上链接 / Live links

- GitHub Pages: https://08-ser-grok-je-personal-20261003.github.io/sermon-shengcan-weiyang-linghun-hc-ld28-mt26-20261024-v1-GROKser/
- Surge: https://sermon-shengcan-weiyang-linghun-hc-ld28-mt26-20261024-v1-grokser.surge.sh
- Repository: https://github.com/08-Ser-Grok-Je-Personal-20261003/sermon-shengcan-weiyang-linghun-hc-ld28-mt26-20261024-v1-GROKser

静态、无框架的多页中文网站（HTML / CSS / 原生 JS，无外部库、字体、图片或脚本）。
A static, framework-free, multi-page Chinese site (HTML / CSS / vanilla JS; no external libraries, fonts, images or scripts).

## 结构 / Structure

| 文件 / File | 内容 / Content |
|---|---|
| `index.html` | 总入口、30秒速记卡、站点地图、线上链接 / hub, 30-second memory card, site map |
| `sermon.html` | 完整讲章（一屏总览、背景与地图、本质、四个闭环、三点、多角度、讨论题、扩展、总结表）/ the full sermon |
| `creeds-read.html` | 三大普世信经：阅读模式与背诵模式（填空、逐句、自测）/ clean reading + memorize modes |
| `forms-read.html`, `hc.html`, `belgic.html`, `dort.html` | 三项联合信条全文，跳转与即时搜索 / full Three Forms with jump + live search |
| `compare.html` | 三信经、三信条比较；六份文件的矩阵、图、导图 / comparison of the six documents |
| `supper.html` | 圣餐资料卷：时间线、逾越节对照、四种圣餐观、HC 问78–82、比利时信条33/35 / Lord's Supper dossier |
| `memorize.html` | 闪卡、测验、间隔复习表、可打印摘要 / flashcards, quizzes, spaced list, printable sheet |
| `resources.html` | 出处与进一步阅读 / sources and further reading |
| `assets/` | `style.css`, `app.js`, `creeds.js`, `forms.js`, `memorize.js` |
| `src/` | 页面模板与 SVG 片段 / page templates and SVG snippets (`src/_inc/`) |
| `corpus/` | 信经与信条原文的 JSON 存档 / verbatim JSON corpus |
| `build.py` | 构建脚本 / the build script |
| `verify_verbatim.py` | 逐字校验 / verbatim verifier |
| `tools/check_links.py`, `tools/qa.py` | 链接检查；无头 Chrome 版面检查 / link check; headless-Chrome layout QA |

所有链接均为相对链接，可放在域名根目录或子路径下。
All links are relative, so the site works at a domain root or at a subpath.

## 如何重新生成 / How to regenerate

```bash
python3 build.py             # 由 src/ 与 corpus/ 生成全部 *.html
python3 verify_verbatim.py   # 逐字校验，必须全部 PASS
python3 tools/check_links.py # 内部链接与锚点
python3 tools/qa.py /tmp/shots --shots   # 需要 Python playwright 和 Chrome
```

- 模板里的 `{{HC 75}}`、`{{BC 35}}`、`{{DORT 5 14}}`、`{{CREED apostles}}`、`{{SENT ...}}`、`{{CPARA ...}}` 等指令由 `build.py` 从 `corpus/*.json` 取文。
- 查看某条的分句：`python3 build.py --sent HC 75 answer`。
- Template directives such as `{{HC 75}}`, `{{SENT ...}}` pull text from `corpus/*.json`; `python3 build.py --sent HC 75 answer` lists the sentences of a field.

## 逐字原则与出处 / Verbatim rule and credit

- 三大普世信经与三项联合信条（海德堡要理问答、比利时信条、多特信经）的每一处引文，都由构建脚本从 `corpus/` 载入，只做 HTML 转义；脚注标记 `^N` 显示为上标，引用经文列表紧随其后。
- `verify_verbatim.py` 独立解析生成的 HTML，逐块比对原始 JSON，并扫描作者文字中是否混入 ≥14 字的原文片段。
- 原文来源：**ccifellowship.org**（页面存档）；每处引文都附“原文”链接。
- 讲章的解说、讨论题、比较与图表为本站作者自撰；圣经经文只写大意，请对照圣经。
- 其他讲章、书籍与网站只作概述与链接，不转载全文；威斯敏斯特标准只作标明为概述的简短对照，不逐字引用。
- Every quotation of the three ecumenical creeds and the Three Forms of Unity comes from `corpus/` via `build.py` with HTML-escaping only. Source of the verbatim texts: ccifellowship.org. Commentary is the author's own; Bible passages are outlined, not quoted.

## 保留与限制 / Notes and limits

- 示意图（出埃及路线、耶路撒冷与马可楼、欧洲、时间线）均标明为示意图，非比例；马可楼位置、西奈山位置只是后世传统或推测。
- 年代与学界争论（出埃及早晚期、马太福音成书、约翰福音的受难周时序、茨温利观点、问80的成文过程）只作概略说明，不下定论。
- 圣诗与韵诗只列篇号，不转录歌词。
- 闪卡进度与阅读设置只保存在访问者浏览器的 localStorage 中。
