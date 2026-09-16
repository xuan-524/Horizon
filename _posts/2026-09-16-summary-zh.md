---
layout: default
title: "Horizon Summary: 2026-09-16 (ZH)"
date: 2026-09-16
lang: zh
---

> 从 68 条内容中筛选出 9 条重要资讯。

---

1. [谷歌 DeepMind 发布 Gemini 3.8 Live 与扩展思考版本](#item-1) ⭐️ 9.0/10
2. [System One Models 与 Jev：以通用生成换取快速类型化推理](#item-2) ⭐️ 8.0/10
3. [Show HN：一款电子墨水画框聆听鸟鸣并用 19 世纪插画风格绘制鸟儿](#item-3) ⭐️ 8.0/10
4. [Wayback Machine 遭大规模抓取流量冲击，互联网档案馆加装防护措施](#item-4) ⭐️ 8.0/10
5. [莱茵金属公开 Battlesuite 武器系统协议 API 文档](#item-5) ⭐️ 8.0/10
6. [IBM Research 追问：AI 智能体能否稳定复现成功任务](#item-6) ⭐️ 7.0/10
7. [SHADOW-50M：4400 万参数三值量化大模型仅 19.8MB，CPU 上跑出约 1900 tok/s](#item-7) ⭐️ 7.0/10
8. [TabPFN-3.5 发布，成为新的 SOTA 表格基础模型](#item-8) ⭐️ 7.0/10
9. [工信部印发《“人工智能+软件”专项行动实施方案》，2028 年覆盖 2 万家规上企业](#item-9) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [谷歌 DeepMind 发布 Gemini 3.8 Live 与扩展思考版本](https://deepmind.google/blog/introducing-gemini-3-8-live-and-3-8-live-extended-thinking/) ⭐️ 9.0/10

谷歌 DeepMind 发布了 Gemini 3.8 Live 和 Gemini 3.8 Live Extended Thinking，并将其称为“迄今最先进的实时对话模型”。此次发布延续了今年 3 月推出的 3.1 Flash Live，将后台推理、实时视觉上下文和后台任务执行能力引入实时语音对话中。 语音正在成为 AI 助手的主要交互入口，而给实时音频模型加入扩展推理能力，意味着助手可以在对话过程中直接解决多步骤问题，而不只是闲聊或做简单查询。这将直接影响构建语音智能体的开发者，以及使用 Gemini Live 和 Gmail 等谷歌产品的普通用户，因为新模型正在这些场景中落地。 根据谷歌的官方文档，Gemini 3.8 Live Extended Thinking 是一款高推理能力的音频到音频模型，适用于实时语音交互中需要较高后台推理能力的复杂多步骤问题求解。这些模型的设计目标是在不打断对话流畅性的前提下完成推理和后台任务执行。

rss · Google DeepMind · 9月15日 17:05

**背景**: “扩展思考”指的是推理阶段的计算扩展，即模型在给出答案前先消耗额外算力生成内部的思维链，这一技术在近期的大语言模型中显著提升了复杂推理任务的表现。Gemini Live 是谷歌的实时对话模式，而“音频到音频”模型是直接把语音处理为语音、而非先转写成文字，因此有助于降低延迟并保留语音细节。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-8-live-gemini-3-8-live-extended-thinking/">Gemini 3.8 Live &amp; Gemini 3.8 Live Extended Thinking</a></li>
<li><a href="https://ai.google.dev/gemini-api/docs/models/gemini-3.8-live-extended-thinking">Gemini 3.8 Live Extended Thinking | Gemini API | Google AI for...</a></li>
<li><a href="https://9to5google.com/2026/09/15/gemini-3-8-live-announced/">Gemini 3.8 Live Extended Thinking powers Gemini Live , Gmail</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的评论整体对 Gemini 的语音与语言能力评价积极：有用户称赞它能应对浓重口音、声音悦耳且延迟较低；还有用户表示它在南非荷兰语上表现出色，已成为自己最享受的大模型使用场景。其他人则强调它的创意写作能力和对本地语境的捕捉，但一位长期用户提醒说，它在非创意类任务上幻觉频繁、深度研究结果不可靠；也有人质疑谷歌虽有数据、TPU 硬件和广告收入，却是否能真正超越其他前沿实验室。

**标签**: `#Gemini`, `#Google DeepMind`, `#large language models`, `#AI announcements`, `#extended thinking`

---

<a id="item-2"></a>
## [System One Models 与 Jev：以通用生成换取快速类型化推理](https://typesafe.ai/blog/introducing-system-one-models-and-jev) ⭐️ 8.0/10

typesafe.ai 团队发布博客，介绍了 System One Models 与 Jev：一种用快速“类型化推理”取代通用生成的方案，即模型输出直接符合预先声明的类型，而不是自由形式的文本。该消息在 Hacker News 上获得 743 分和 254 条评论，成为当天讨论热度最高的 AI 基础设施类帖子之一。 目前大多数生产级 LLM 流水线即使在处理分类、抽取或路由这类任务时，仍要承担自回归逐 token 生成的开销；如果 Jev 能在 p95 延迟下以个位数毫秒/秒级给出可靠的结构化结果，就有可能取代 agent 系统中缓慢的多工具调用链。同时它也融入了快速增长的“结构化生成”生态（如 Outlines 这类基于语法/模式约束解码的工具），在这类场景中可靠性与延迟比开放式创造力更重要。 评论者对速度对比的表述提出质疑：他们指出，能够输出图灵完备语言代码的生成模型原则上可以完成计算机能做的一切，而 Jev 只能生成结构化输出——这是一项真实的限制，而不只是性能调优。另有评论者认为它看起来像是“产品化的 conformal prediction（保形预测）”，还有人提问它是否是一种马尔可夫/扩散式模型，并配有某种外部 Engram 记忆。

hackernews · albelfio · 9月15日 19:25 · [社区讨论](https://news.ycombinator.com/item?id=49717558)

**背景**: 自回归 LLM 一次只生成一个 token，因而通用性强，但速度慢且容易出现格式错误；结构化生成则在解码阶段施加约束，使输出必须符合某个模式或语法。所谓“类型化推理”进一步把模型的任务定义为产出某个已声明类型的值，这对分类、抽取和路由非常有用，但无法生成任意的开放式文本。讨论中提到的 conformal prediction（保形预测）是一种统计框架，它把预测包装成带有覆盖率保证的预测集合，这也是读者觉得两者相似的原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=49717558">Introducing System One Models and Jev | Hacker News</a></li>
<li><a href="https://github.com/dottxt-ai/outlines">GitHub - dottxt-ai/outlines: Structured Outputs</a></li>
<li><a href="https://huggingface.co/learn/cookbook/structured_generation">RAG with source highlighting using Structured generation · Hugging Face</a></li>

</ul>
</details>

**社区讨论**: 整体氛围是好奇且偏正面的，多位读者认为这是真正新颖且有前景的工作；但最尖锐的讨论质疑了标题与速度对比，认为把受模式限制的系统与通用生成器相比是“苹果比橘子”。有人把它类比为保形预测，有人追问它是否是带外部记忆的马尔可夫/扩散模型，还有一位正在开发 AI 视频编辑器的开发者表示，Gemini 的多工具调用延迟超过 30 秒，如果 Jev 能把 p95 降到个位数，将是颠覆性的改变。另有评论者指出，Jev 与他已在其 SymbolicAI 项目中实现的“契约式设计（design-by-contract）”模式结合起来会很有潜力。

**标签**: `#AI`, `#LLM`, `#typed inference`, `#structured generation`, `#Hacker News`

---

<a id="item-3"></a>
## [Show HN：一款电子墨水画框聆听鸟鸣并用 19 世纪插画风格绘制鸟儿](https://github.com/arnegiacomo/fugleramme) ⭐️ 8.0/10

一位开发者在 GitHub 上发布了名为“fugleramme”的项目：一个电子墨水画框，它持续聆听周围的鸟鸣，用 BirdNET 识别鸟的种类，然后把每只被识别出的鸟渲染成 19 世纪风格的插画显示在屏幕上。该 Show HN 帖子获得了约 1300 个赞和 181 条评论，作者同时提到此前一个名为“Avian Visitors”的相关项目。 这个项目展示了便宜的电子墨水硬件加上音频分类器，如何把普通家居物品变成低功耗、充满“魔法感”的环境交互设备，也引发了 HN 上关于 DIY 鸟类科技、替代数据来源以及复用旧电子墨水设备的广泛讨论。它同时凸显了 BirdNET 作为一款成熟、易用的生物声学工具——爱好者可以直接在其上二次开发，而非依赖通用大语言模型。 底层分类器 BirdNET 是一个专门用于鸟声识别的传统神经网络（其方法发表在 2021 年《Ecological Informatics》论文中），而并非大语言模型，可识别数千种鸟类。社区成员指出，不装麦克风的替代方案是利用 eBird API 拉取本地已观测到的鸟类并配上学名，同时旧电子墨水设备可以通过 TRMNL 等 BYOD 方案重新利用。

hackernews · arnemunthekaas · 9月15日 12:31 · [社区讨论](https://news.ycombinator.com/item?id=49711544)

**背景**: 电子墨水（E Ink，电子纸）屏幕由微小的色素胶囊组成，通过移动黑白粒子来成像，因此只有刷新时耗电，且能在无背光的情况下无限期保持静态画面。BirdNET 由康奈尔大学鸟类学实验室参与开发，是一款免费的 AI 模型与手机应用，能根据鸣叫识别超过 3000 种鸟类，广泛应用于保护生物学和生态监测。这个项目把两者结合起来：持续聆听的分类器判断出当前是哪只鸟，随后生成插画步骤把识别结果变成印刷风格的图像。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://birdnet.cornell.edu/app/">BirdNET App - Identify Birds by Sound</a></li>
<li><a href="https://www.eink.com/tech/detail/How_it_works">Electronic Ink｜E Ink Technology</a></li>

</ul>
</details>

**社区讨论**: 社区反响极为热烈，评论者称这是近来 HN 上最鼓舞人心的项目，赞赏其多种想法的融合营造出“魔法般”的效果。技术讨论澄清了 BirdNET 是传统神经网络而非 LLM，建议用 eBird API 作为无需麦克风的入门方案、用 TRMNL 硬件玩电子墨水，并提到 birdnet-go 等相关项目；还有几位用户分享了自己单次充电即可运行多年的低功耗电子墨水装置。

**标签**: `#Show HN`, `#e-ink`, `#BirdNET`, `#audio-classification`, `#hardware-diy`

---

<a id="item-4"></a>
## [Wayback Machine 遭大规模抓取流量冲击，互联网档案馆加装防护措施](https://blog.archive.org/2026/09/15/an-update-on-wayback-machine-access/) ⭐️ 8.0/10

互联网档案馆在 9 月 15 日发布的一篇博客文章中表示，Wayback Machine 遭遇了一波又一波的高流量自动化访问，该机构已部署新的防护措施以维持服务运行。文章还提到，受此类滥用行为影响，已有部分网站选择退出被存档。 Wayback Machine 是承载超过 1 万亿个网页快照的关键公共网络基础设施，持续不断的抓取压力会威胁记者、研究人员、维基百科编辑以及普通用户的免费匿名访问。如果滥用行为持续，可能有更多网站所有者选择退出存档，从而侵蚀开放网络的历史记录。 文章将该流量描述为一波波高强度的自动化请求，但并未说明具体采用了哪些缓解机制。评论者反映访问表现并不一致，例如某些网络下持续出现 HTTP 429 限流错误，而其他连接却一切正常；也有人指出，互联网档案馆仍可通过 Tor 匿名访问，无需经过中心化的把关方。

hackernews · ChrisArchitect · 9月15日 17:52 · [社区讨论](https://news.ycombinator.com/item?id=49716176)

**背景**: Wayback Machine 是由互联网档案馆运营的万维网数字存档项目；该档案馆是 1996 年由 Brewster Kahle 在旧金山创立的非营利机构，使命是“实现对所有知识的普遍访问”。Wayback Machine 于 2001 年 10 月 25 日向公众开放，让用户可以查看网站过去的样子，目前保存了超过 1 万亿个网页快照和逾 99 PB 的数据。网页抓取（即用机器人或爬虫自动获取并提取网站数据）常被用来绕过原始网站设置的封锁，此次事件似乎正是如此。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Wayback_Machine">Wayback Machine</a></li>
<li><a href="https://en.wikipedia.org/wiki/Internet_Archive">Internet Archive</a></li>
<li><a href="https://en.wikipedia.org/wiki/Web_scraping">Web scraping</a></li>

</ul>
</details>

**社区讨论**: 评论者总体持支持态度，称赞互联网档案馆是不可或缺的基础设施并呼吁捐款，还有人认为 AI 公司应为访问支付数十亿美元。评论者 simonw 推测这些流量来自试图绕过原始网站封锁、转而抓取 Wayback 副本的抓取程序，并称这种行为“令人愤慨”；BeetleB 提到令人费解的、依网络环境而异的 429 错误，robotmay 则分享了自己用存档找回 2000 年代初游戏评测网站的怀旧经历。

**标签**: `#Internet Archive`, `#Wayback Machine`, `#Web Scraping`, `#Digital Preservation`, `#Open Access`

---

<a id="item-5"></a>
## [莱茵金属公开 Battlesuite 武器系统协议 API 文档](https://rheinmetall.github.io/onboardapi-documentation/9.10.0/index.html) ⭐️ 8.0/10

德国防务承包商莱茵金属（Rheinmetall）公开发布了其 Battlesuite 互联武器系统平台 Onboard API 的带版本号文档（9.10.0 版本），对外披露了 Battlesuite 各组件之间交换数据所使用的协议接口。该文档托管在莱茵金属的公开 GitHub Pages 站点上，而非客户专属门户，因此外部开发者首次可以查阅这一接口。 在防务科技领域，公开武器系统集成协议的文档极为罕见，这类接口通常属于专有技术并受出口管制，因此此举有望降低第三方及盟国系统与 Battlesuite 集成的门槛。这也表明防务厂商开始借鉴商业软件的开源 API 打法，以吸引集成商和合作伙伴。 该协议基于 DDS（数据分发服务）构建，这是 OMG 制定、广泛应用于航空航天和防务领域的发布-订阅中间件标准；批评者指出 DDS 较为笨重，在缺乏动态内存分配的嵌入式系统上实现起来相当吃力。此次公开的是 9.10.0 版本的 API 文档，即接口规范，而非武器系统本身的实现源代码。

hackernews · summarity · 9月15日 21:07 · [社区讨论](https://news.ycombinator.com/item?id=49718928)

**背景**: Battlesuite 是莱茵金属于 2025 年 5 月发布的数字化战场平台，用于连接传感器、武器、无人机和指挥系统，使各作战单元共享同一幅持续更新的态势图。DDS 是 OMG 制定的机器对机器中间件标准，采用发布-订阅模式，让应用通过一个虚拟全局数据空间交换数据，是众多实时航空航天与防务系统的底层支撑。公开 API 规范可使软件厂商在无法接触内部源代码的情况下编写兼容插件，这种模式在商业平台中很常见，但在武器系统中并不寻常。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.rheinmetall.com/en/products/digital-forces/battlesuite">Battlesuite – The interoperable military ecosystem of the future | Rheinmetall</a></li>
<li><a href="https://en.wikipedia.org/wiki/Data_Distribution_Service">Data Distribution Service - Wikipedia</a></li>
<li><a href="https://thedefensepost.com/2025/05/27/rheinmetall-battlesuite-link-battlefield/">Rheinmetall Launches ‘Battlesuite’ to Link Weapons, Drones, and Data on Battlefield</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上具备领域背景的评论者将 Battlesuite 的做法与既有标准进行了对比：有人将其类比为同样采用 DDS 的战术微电网标准（MIL-STD-3071），并希望能有一种类似 DDS、但针对实时性保证和无动态内存分配的嵌入式系统优化的协议；也有人提到开放任务系统（OMS），以及分布式仿真中使用的 DIS（IEEE 1278）与 HLA（IEEE 1516）联邦对象模型架构。一种反复出现的情绪是：最初的兴奋因该协议依赖 DDS 而打了折扣，多位评论者认为 DDS 过于笨重。

**标签**: `#defense-tech`, `#DDS`, `#open-source`, `#protocols`, `#weapons-systems`

---

<a id="item-6"></a>
## [IBM Research 追问：AI 智能体能否稳定复现成功任务](https://huggingface.co/blog/ibm-research/altk-evolve-consistency) ⭐️ 7.0/10

IBM Research 在 Hugging Face 上发布了一篇题为《Your Agent Aced the Task. Will It Do It Again?》的博客文章，把智能体评估的重心从&quot;一次性任务成功&quot;转向&quot;一致性&quot;——即一次做对的智能体能否稳定地再做对。该文与标记为 ALTK / evolve-consistency 的工作相关，将可复现性提升为智能体系统的一等评估目标，而非事后补充。 当前基准排行榜几乎只反映单次运行的成功率，因此一次通过任务的智能体在生产环境中仍可能随机失败；一致性把这部分被隐藏的波动变成可测量、可比较的指标。随着智能体工作流进入编程、科研和企业自动化场景，采购方与平台团队需要的是可靠性信号，而不只是峰值准确率。 一致性通常通过用完全相同的输入重复执行同一任务、统计结果稳定出现的比例来衡量，这会暴露由采样温度、工具调用顺序以及可变的环境或记忆状态带来的不确定性。重复运行比单次评估昂贵得多，而且完全确定性的智能体往往既难实现也未必可取，因此真正有价值的问题变成：对某个具体部署而言，多大的波动是可以接受的。

rss · Hugging Face Blog · 9月15日 16:00

**背景**: AI 智能体是由大模型驱动、通过多步规划与工具调用来完成任务而非只输出一段文本的系统。由于每一步都可能涉及采样随机性、外部 API，或不断变化的文件与网页状态，智能体评估比传统的大模型评估更难——后者大多只是把一次输出与参考答案做比较。近期诸如 Holistic Agent Leaderboard 的可靠性仪表盘以及关于智能体评估的学术综述都指出，仅看准确率并不足够，并提出了一致性、鲁棒性与可预测性等维度；这篇博客正属于这一新兴方向。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2507.21504v1">Evaluation and Benchmarking of LLM Agents: A Survey - arXiv</a></li>
<li><a href="https://hal.cs.princeton.edu/reliability/">HAL Reliability Dashboard - Holistic Agent Leaderboard</a></li>
<li><a href="https://galileo.ai/blog/ai-agent-reliability-metrics">8 AI Agent Metrics That Go Beyond Accuracy | Galileo</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#LLM evaluation`, `#reliability`, `#consistency`, `#Hugging Face`

---

<a id="item-7"></a>
## [SHADOW-50M：4400 万参数三值量化大模型仅 19.8MB，CPU 上跑出约 1900 tok/s](https://www.reddit.com/r/MachineLearning/comments/1wgzpli/i_trained_a_44m_parameter_quantized_llm_from/) ⭐️ 7.0/10

一位开发者发布了 SHADOW-50M——尽管名字叫 50M，实际是 4400 万参数的大语言模型，从零开始用 450 亿 token 训练，采用 \{-1, 0, +1\} 三值权重，并用固定的 512 位指纹表示 73880 个 token 的词表，取代了传统的可训练嵌入表。完整模型仅 19.8 MB，附带 159 KB 编译内核，可完全离线运行，在笔记本电脑 CPU 上达到约 1900 tok/s，同一内核编译为 WebAssembly 后在浏览器标签页中约 500 tok/s。 这是一个颇具说服力的概念验证：一个具备推理与检索能力的完整模型可以压缩到 20MB 以内，并在普通 CPU 上离线运行，这对端侧 AI、隐私保护的本地推理以及没有 GPU 显存和网络的边缘部署场景意义重大。其混合设计还表明，把符号计算电路注入 token 流，可以弥补超小量化模型在推理上的短板。 作者坦承 SHADOW 在标准基准上不敌 51.8M 参数的 bf16 Llama 式基线模型 Supra-50M-Reasoning（ARC-Easy 0.307 对 0.435，PIQA 0.570 对 0.600，WikiText-2 困惑度 186 对 165），但在算术、日期和检索类提示上反而胜出，原因是固定电路接管了 \[calc\]…\[eq\] 片段，并能从磁盘读回已存储的注意力状态。归档以 1 bit（每 token 288 字节）保存注意力状态，索引为每 token 22 字节，全部内存映射，因此 1 亿 token 的归档仅占用约 28MB 内存；被使用的记录会在索引中得到强化，使实测 top-1 检索准确率从 0.571 提升到 0.743，且无需重新训练模型。

reddit · r/MachineLearning · /u/Final-Data-1410 · 9月15日 12:59

**背景**: 三值量化把模型权重限制为 -1、0、+1 三个取值，使矩阵乘法退化为廉价的加法运算，显存占用也大幅下降，这一思路因 BitNet 以及“1.58 位”大模型等工作而广为人知。传统大模型则需要学习一个庞大的浮点嵌入表，把每个词表 token 映射为向量，对几万词表的小模型来说这是体积的主要来源；SHADOW 改用每个 token 固定的 512 位指纹来替代。另一方面，小模型在精确算术和日期推算上表现极差，因此 SHADOW 在输出端接入一个符号电路，把正确的数字直接填入生成的 token 流中，无需工具调用或计算器 API。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/1.58-bit_large_language_model">1.58-bit large language model - Wikipedia</a></li>
<li><a href="https://arxiv.org/abs/2509.23809">Trapping-free Ternary Quantization for Large Language Models - arXiv</a></li>

</ul>
</details>

**标签**: `#LLM`, `#quantization`, `#on-device-inference`, `#efficient-ml`, `#from-scratch-training`

---

<a id="item-8"></a>
## [TabPFN-3.5 发布，成为新的 SOTA 表格基础模型](https://www.reddit.com/r/MachineLearning/comments/1wh4xhy/tabpfn35_is_released_as_the_next_sota_tabular/) ⭐️ 7.0/10

Prior Labs 发布了新的表格基础模型 TabPFN-3.5，该模型目前在 TabArena 和 BeyondArena 两个排行榜上均排名第一，并支持最多 100 万行、2 万个特征的数据集。此次发布包含三个版本：TabPFN-3.5-Fast（比基础模型快 6 倍，处于 alpha 阶段）、TabPFN-3.5-Thinking（用更多算力换取更高精度，通过 API 提供）以及 TabPFN-3.5-Plus。 表格数据依然是绝大多数真实工业机器学习任务的基础，而梯度提升树长期是默认选择；一个能够在公开、经过精心整理的基准上稳定领先的基础模型，有可能改变从业者的默认选型习惯。以基准评测的标准来看，这次提升幅度相当大——在 BeyondArena 上比此前最强基线高出约 250 Elo——因此对表格机器学习社区而言，这是一次实质性的进展，而非小修小补。 在 BeyondArena 上，TabPFN-3.5 在文本丰富、高基数和高维数据上领先，比此前最强基线高出 250 Elo，比此前总榜第一高出 150 Elo；而 Thinking 版本相对基础模型在 BeyondArena 上再提升 20 Elo，在 TabArena 上再提升 44 Elo。值得注意的是：公告声称可扩展到 2 万个特征，而此前关于 TabPFN-3 的文档描述为最多支持 100 万行和 200 个特征；此外 Fast 版本目前仍处于 alpha 阶段。

reddit · r/MachineLearning · /u/tuanacelik · 9月15日 16:18

**背景**: TabPFN（Tabular Prior-data Fitted Network，表格先验数据拟合网络）是一种基于 Transformer 的模型，用于表格数据上的监督分类与回归，最早于 2022 年提出。与传统模型不同，它采用上下文学习（in-context learning），直接根据输入中给出的带标签样本进行预测，无需进一步更新参数，因此不需要针对每个数据集单独训练。TabArena 是一个“活的”表格机器学习基准，持续纳入经过筛选的数据集、实现规范的模型以及更新的评测方法；BeyondArena 则是更广泛统一的基准，覆盖 IID、时序和分组任务，并横跨更大的规模与维度范围——这些正是传统表格基准常常忽略的场景。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/TabPFN">TabPFN</a></li>
<li><a href="https://github.com/PriorLabs/TabPFN">GitHub - PriorLabs/ TabPFN : TabPFN : Foundation Model for Tabular...</a></li>
<li><a href="https://arxiv.org/abs/2506.16791">TabArena : A Living Benchmark for Machine Learning on Tabular Data</a></li>

</ul>
</details>

**标签**: `#tabular-data`, `#foundation-models`, `#machine-learning`, `#TabPFN`, `#benchmarks`

---

<a id="item-9"></a>
## [工信部印发《“人工智能+软件”专项行动实施方案》，2028 年覆盖 2 万家规上企业](https://news.google.com/rss/articles/CBMiV0FVX3lxTE9WMWtpcWVIaVNaTHJ5a2lyTGtBTUJXUVplZU0waUt2dVE1ZDBzaUhfc3lOTXZTUUxrVFVsT2lrbXluanlDajRzcDE5YUdPOFFSUkd0cEJ5bw?oc=5) ⭐️ 7.0/10

中国工业和信息化部印发了《“人工智能+软件”专项行动实施方案》，明确提出到 2028 年覆盖 2 万家规模以上企业。这意味着人工智能在中国软件行业的落地，正从市场自发行为转向由中央层面统一部署的产业政策推动。 该方案把目标落在“覆盖多少家企业”而非论文或技术指标上，因此很可能转化为具体的采购需求、试点项目和厂商订单，直接拉动中国软件产业的 AI 化需求。AI 编程助手、企业级 AI 平台以及行业软件厂商有望受益，而外资软件与 AI 供应商在中国市场则可能同时面临机会与本地化替代压力。 该方案被明确界定为“人工智能+软件”专项行动，说明政策重心是把 AI 嵌入软件开发流程与软件产品本身，而不是 AI 硬件或通用大模型。目前可获取到的信息仅为指向 AgeClub 报道的标题链接，因此关于资金安排、标准体系、细分行业划分以及“规上企业”统计口径等具体细节，在现有材料中尚未得到确认。

google\_news · AgeClub · 9月16日 00:59

**背景**: 工信部（工业和信息化部）是中国负责产业政策的政府部门，软件和信息技术服务业正是其主管领域之一。在中国官方统计口径中，“规模以上企业”（规上企业）指年主营业务收入超过一定门槛的企业，因此“2 万家规上企业”指的是大型、正规、纳入统计体系的企业，而非初创公司或小微企业。方案的“人工智能+”提法延续了中国推动 AI 与实体经济融合的“人工智能+”总体部署，本次则是把这一框架具体落到软件行业上。

**标签**: `#AI Policy`, `#China`, `#Software Industry`, `#AI Adoption`, `#Government Initiative`

---