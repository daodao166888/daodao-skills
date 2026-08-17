# 去 AI 味开源工具大全（2026-08 版）

> 整理：daodao166888 · 数据截至 2026-08-17
> 覆盖 GitHub 上主流的「去 AI 味 / Humanize / 降 AI 味」工具共 16 个，逐一深读 SKILL.md 后汇总。
> 所有星标为实时抓取数据，非搜索摘要。

---

## 一、30 秒选型（按你的场景）

| 你的场景 | 推荐 | 理由 |
|---|---|---|
| **中文内容**（X/公众号/小红书） | `anti-vibe-writing` | 内置 X/微博/公众号场景预设，3 种 voice 模式 |
| **中文最主流、最稳** | `op7418/Humanizer-zh` | 1.5 万星，24 种痕迹 + 5 维 50 分评分 |
| **强保真改写**（不新增任何事实） | `qu-ai-wei` | 凭证门检 + 信息账本，边界最严 |
| **英文内容** | `blader/humanizer` | 3.6 万星，去 AI 味「祖师爷」，33 类痕迹 |
| **MBA/学术论文** | `humanize-mba-text-skill` | 唯一带完整 Python 检测链，五章节专项规则 |
| **本地离线、零依赖** | `swaylq/humanize-chinese` | 纯 Python，零 LLM 零 API，95% 准确率自称 |
| **结构化检测引擎** | `avoid-ai-writing` | 62 类痕迹 + 112 词三档替换表 + 0-100 计分 |
| **研究背书** | `harshaneel/humanize` | 50+ 篇论文 grounding，9 大信号 + 量化硬规则 |

---

## 二、完整工具清单

### 2.1 中文系（简体 / 繁体）

| 仓库 | 星标 | 痕迹数 | 核心方法 | 安装 | 亮点 |
|---|---|---|---|---|---|
| [op7418/Humanizer-zh](https://github.com/op7418/Humanizer-zh) | 15,460 | 24 种 / 4 大类 | 基于维基百科「Signs of AI writing」；内容/语言语法/风格/交流四类逐条清理 | `npx skills add https://github.com/op7418/Humanizer-zh.git` | 5 维 50 分评分 + AI 高频词警示表 |
| [LifelongLazyLearner/qu-ai-wei](https://github.com/LifelongLazyLearner/qu-ai-wei) | 424 | 8 个模式族 + 10 类结构 | 8 模式族（内容真实性/证据强度/篇章组织/句法语序/词汇搭配/修辞节奏/体裁平台/来源引用） | `npx skills add https://github.com/LifelongLazyLearner/qu-ai-wei` | 凭证门检 + 信息账本/论证图 + 真人文本停手机制 + 三段式输出 |
| [weijt606/anti-vibe-writing](https://github.com/weijt606/anti-vibe-writing) | 105 | 词汇/句式/结构/语气四层 | 中文重点清互联网黑话、虚动词、无源权威铺垫、三连排比；英文清 em-dash 等 | git clone 后复制到 skills 目录 | **X/公众号/小红书场景预设** + 3 种 voice + 文风学习 |
| [0xtresser/cn-humanizer](https://github.com/0xtresser/cn-humanizer) | 11 | 18 种 + 100+ 词库 + 12 种翻译腔 | 词汇三级分级（铁证/可疑/套话短语）；统计信号表（句长 CV 人类 0.4-0.8 vs AI 0.1-0.3） | `curl ... install.sh \| bash` | 纯 Markdown 零依赖，翻译去腔双模式 |
| [yyx20202020/natural-writing-skill](https://github.com/yyx20202020/natural-writing-skill) | 13 | 4 类高影响症状 | 空框架/表演性意义/机械句法/假人类质感四类聚类 | `npx skills add yyx20202020/natural-writing-skill` | **两组独立参数**（力度×范围）+ `check_protected_spans.py` 事实保护 |
| [B1lli/remove-ai-flavor-writing-skill](https://github.com/B1lli/remove-ai-flavor-writing-skill) | 217 | 7 类结构壳 | 只去「模型组织答案」的结构外壳（二分对照/机械顺序/本质拔高/假互动结尾等），**不做同义词替换** | `mkdir -p ~/.codex/skills && cp -R ...` | `audit_ai_flavor.py` 回归审计 + 6 类场景 fixture |
| [moli238/humanizer-zh-moli](https://github.com/moli238/humanizer-zh-moli) | 26 | 36 类（33 原版 + 3 中文专属） | 新增动词名词化、机关腔/商务黑话、英译式代词过密三个中文专属模式 | `npx skills add . --global` | **有意删除了量化评分**（认为诱导机械改句），4 种调用模式 |
| [kevintsai1202/Humanizer-zh-TW](https://github.com/kevintsai1202/Humanizer-zh-TW) | 702 | ~28 节（繁中） | 繁体中文版，保留「个性与灵魂」章节 + voice calibration | `npx skills add kevintsai1202/Humanizer-zh-TW` | 支持 8 种 agent 安装参数 |
| [yelban/humanizer.tw](https://github.com/yelban/humanizer.tw) | 13 | — | 繁体台湾版，重点处理时代开场白、连接词滥用、互联网黑话 | git clone 到 `~/.claude/skills/` | `/humanizer-tw` 触发 |
| [Show-Chan97/Humanizer-zh](https://github.com/Show-Chan97/Humanizer-zh) | 12 | 29 种 | 基于维基指南 v2.5.1 的中文升级版 | `npx skills add` | 内容/语言语法/风格/交流四类修复 |

### 2.2 英文系（元老 / 通用）

| 仓库 | 星标 | 痕迹数 | 核心方法 | 安装 | 亮点 |
|---|---|---|---|---|---|
| [blader/humanizer](https://github.com/blader/humanizer) | 36,039 | 33 类 | 维基百科「Signs of AI writing」正典；**no-fabrication 铁律**（不新增原文没有的事实/姓名/数字/引语） | `npx skills add blader/humanizer --global` | draft→audit→final 两遍流程 + voice calibration + Personality and Soul 注入 |
| [conorbronsdon/avoid-ai-writing](https://github.com/conorbronsdon/avoid-ai-writing) | 3,050 | 62 类（引擎 48 type） | 零依赖 Node 检测引擎 + 112 词三档替换表 + 0-100 计分 | git clone 到 `~/.claude/skills/` | `detector/validate.js` 保真校验 + 自带 CI 自检；明确「signals, not proof」立场 |
| [stephenturner/skill-deslop](https://github.com/stephenturner/skill-deslop) | 349 | 4 个 reference 文件 | 学术写作向：公式化结构 + AI tropes 目录；**被动语态/领域术语不算 tell**，business buzzwords 算 | 下载 ZIP / `.skill` 文件 | 5 维 × 1-10 评分（<35/50 重改） |
| [harshaneel/humanize](https://github.com/harshaneel/humanize) | 362 | 9 大信号/杠杆 | 50+ 篇论文 grounding；9 个 humanization levers + 7 条量化硬规则（句长跨度 ≥20 词等） | `./install.sh all` | **诚实标注天花板**：静态规则骗不过 GPTZero/Grammarly 这类 learned classifier |

### 2.3 论文 / 学术系

| 仓库 | 星标 | 特点 | 安装 | 亮点 |
|---|---|---|---|---|
| [stephenlzc/humanize-mba-text-skill](https://github.com/stephenlzc/humanize-mba-text-skill) | 39 | 中国 MBA 毕业论文专用 | git clone + `pip install transformers torch`（可选） | **三层检测**：regex 规则 → 散文统计 5 维（句长 CV）→ 语义链 10 维；五章节专项规则（绪论/理论/分析/建议/结论） |
| [swaylq/humanize-chinese](https://github.com/swaylq/humanize-chinese) | 13 | 纯 Python 本地，零 LLM 零 API | git clone | 20+ 规则 + 8 个统计特征（句长 CV/GLTR/Binoculars 等）+ best-of-N 改写 + 学术降重（知网/维普/万方）。⚠️ **MIT Non-Commercial，禁商用** |
| [whh110112/human-writing-skills](https://github.com/whh110112/human-writing-skills) | 1 | 长文连续性 + 文体纪律 + 保真 | git clone + `pip install .` | 30+ deep-trace 模块 + claim ledger 保真 + 7 种文体 skill |

---

## 三、去 AI 味通用方法论（综合 16 个工具提炼）

> 所有工具看似不同，底层共享同一套「AI 痕迹清单」。以下是从中提取的**最大公约数**。

### 3.1 AI 痕迹的四大类别

| 类别 | 具体痕迹 |
|---|---|
| **内容模式** | 意义拔高（历史性/关键时刻）、模糊归因（研究表明/专家指出）、宣传语言、万能挑战展望段 |
| **语言语法** | AI 高频词、系动词回避、**否定式排比（不是 X 而是 Y）**、三段式法则（rule of three）、同义词循环、虚假范围（从 X 到 Y） |
| **风格** | 破折号滥用、粗体/emoji 堆叠、内联标题列表、弯引号、过多感叹号 |
| **交流/填充** | 协作口吻（下面我们来）、谄媚（希望这能帮到你）、填充短语、过度限定、通用积极结论 |

### 3.2 高频词清单（综合各工具词库）

**中文必清词（多工具共同点名）：**
`赋能` `助力` `打造` `抓手` `闭环` `底层逻辑` `颗粒度` `顶层设计` `深耕` `聚焦` `引领`
`致力于` `通过…的方式` `进一步` `不仅…更…` `不是…而是…` `值得注意的是` `由此可见` `综上所述` `总而言之`
`在当今…的时代` `随着…的不断发展` `从某种意义上说` `需要指出的是`

**英文高频词（delve 家族）：**
`delve` `tapestry` `vibrant` `pivotal` `serves as` `testament` `landscape` `underscores` `nuanced` `leverage` `ecosystem`

### 3.3 改写铁律（所有主流工具的共同边界）

1. **不新增事实** — 姓名/数字/日期/案例/引语，原文没有的坚决不补（no-fabrication）
2. **信息优先于形状** — 信息可以重组，实质内容不能漏
3. **删填充、破公式、变节奏** — 填充词删掉、对仗打破一组、长句短句交替
4. **收尾说人话** — 金句式总结改成大白话
5. **用「我」不用「你」** — 第一人称陈述经历，不用第二人称教训人

### 3.4 质量自检法

- **两遍改写**（blader 首创）：第一遍去明显 AI 模式 → 第二遍「反 AI 审计」再抓残留
- **5 维评分**：直接性 / 节奏 / 信任度 / 真实性 / 精炼度（各 1-10，低于 35/50 重改）
- **句长 CV**：人类 0.4-0.8，AI 0.1-0.3（句式越均匀越可疑）
- **保真校验器**：改写前后比对，代码块/表格/URL/数字动了就报错（avoid-ai-writing 的 validate.js）

---

## 四、演进脉络（一张图看懂生态）

```
blader/humanizer（3.6万★，英文正典，维基 33 类痕迹）
├── op7418/Humanizer-zh（1.5万★，简体中文翻译+评分）
│   ├── kevintsai1202/Humanizer-zh-TW（702★，繁体）
│   ├── yelban/humanizer.tw（13★，繁体台湾）
│   └── moli238/humanizer-zh-moli（26★，迭代分支，删除评分）
├── conorbronsdon/avoid-ai-writing（3k★，引擎化：62类+计分）
├── stephenturner/skill-deslop（349★，学术向）
└── harshaneel/humanize（362★，论文 grounding + 量化规则）

独立派（中文原生，非翻译）：
├── qu-ai-wei（424★，工程化最完整，边界最严）
├── anti-vibe-writing（105★，X/公众号场景预设）
├── remove-ai-flavor-writing-skill（217★，只去结构壳）
└── humanize-mba-text-skill / humanize-chinese（本地/论文专用）
```

---

## 五、安装方式速查

| 方式 | 命令 |
|---|---|
| skills.sh 一键装 | `npx skills add <owner>/<repo>` |
| Claude Code 手动 | `git clone <repo> ~/.claude/skills/<name>` |
| Codex | `mkdir -p ~/.codex/skills && cp -R <name> ~/.codex/skills/` |
| 全工具通用 | `./install.sh all`（humanize 支持多端同时装） |

---

## 六、注意事项

1. **这些工具是「写作风格校正层」，不是「AI 检测绕过器」** — 多数工具明确声明不承诺绕过检测，且强烈反对伪造事实
2. **静态规则有天花板** — 改得再「人味」也骗不过 GPTZero 这类 learned classifier（harshaneel 诚实标注了这点）
3. **去 AI 味只是及格线，加「人味」才是满分** — blader 的「Personality and Soul」章节：干净但没灵魂的写作，跟 AI 写的一样明显。观点、节奏变化、第一人称、承认复杂性，才是真·人味
4. **许可证注意** — `humanize-chinese` 是 MIT Non-Commercial（禁商用），其余主流工具均为 MIT

---

*数据来源：16 个仓库的 README + SKILL.md 逐一深读，星标为 2026-08-17 实时数据。*
