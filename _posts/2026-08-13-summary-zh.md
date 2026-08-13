---
layout: default
title: "Horizon Summary: 2026-08-13 (ZH)"
date: 2026-08-13
lang: zh
---

> 从 68 条内容中筛选出 11 条重要资讯。

---

1. [DeepSeek V4 Pro 0813 通过 API 发布](#item-1) ⭐️ 9.0/10
2. [Tailscale 将数据库损坏追溯到 16 年前的 SQLite WAL 重置 Bug](#item-2) ⭐️ 8.0/10
3. [Qwen 发布 Qwen3.8-2.4T：拥有 950 亿激活参数的巨型 MoE 模型](#item-3) ⭐️ 8.0/10
4. [xAI 发布 Grok 4.6，引发基准测试与 API 争议](#item-4) ⭐️ 8.0/10
5. [谷歌 DeepMind 推出 SL2T 将手语 AI 带入消费设备](#item-5) ⭐️ 8.0/10
6. [Adam 的逐坐标缩放破坏隐式低秩偏置，而 Muon 保持该特性](#item-6) ⭐️ 8.0/10
7. [Florian Herrengt 警告：AI 辅助编码可能导致代码库无人能维护](#item-7) ⭐️ 7.0/10
8. [按目的地质量而非声望排名的 CS 会议排名工具](#item-8) ⭐️ 7.0/10
9. [消融一个注意力头使 Chessformer 无法识别弃后](#item-9) ⭐️ 7.0/10
10. [中科院推出全球海洋智能预报大模型“琅琊”](#item-10) ⭐️ 7.0/10
11. [传 Anthropic 拟以 60 亿美元收购 AI 初创公司 Decart AI](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [DeepSeek V4 Pro 0813 通过 API 发布](https://openrouter.ai/deepseek/deepseek-v4-pro-0813) ⭐️ 9.0/10

DeepSeek 已发布 DeepSeek V4 Pro 0813 模型，目前可通过 OpenRouter 上的 API 使用。这款混合专家（MoE）模型拥有 1.6T 总参数（49B 激活参数），支持 100 万 token 的上下文窗口，定价为每百万输入 token 0.435 美元，每百万输出 token 0.87 美元。 此次发布在 Hacker News 上引发了热烈的社区讨论（829 分、326 条评论），早期用户反馈该模型在开发任务上以低成本带来了显著的性能提升。鉴于 DeepSeek 一贯开源模型权重的做法，未来可能发布开源版本，这将进一步重塑大语言模型的竞争格局。 该模型目前仅提供 API 调用，且 DeepSeek 没有发布专门的公告页面，因此使用了 OpenRouter 的链接。此前 4 月份的 DeepSeek-V4-Pro 和 7 月份的 DeepSeek-V4-Flash-0731 权重均已在 Hugging Face 上开放，表明本次发布也有可能开放模型权重。

hackernews · explosion-s · 8月12日 16:04 · [社区讨论](https://news.ycombinator.com/item?id=49274600)

**背景**: DeepSeek 是一家中国人工智能公司，2025 年 1 月其 R1 聊天机器人在美国 iOS App Store 上超越 ChatGPT 成为下载量最大的免费应用，引起全球关注，并以其开放权重模型和高效的 MoE 架构而闻名。V4 系列延续了这一模式，采用 Mixture-of-Experts（混合专家）设计，每个 token 仅激活一部分参数，从而以较低推理成本实现大模型容量。新款 Pro 模型还支持 100 万 token 的上下文窗口，可以处理超长文档或大型代码库。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/DeepSeek_%28product%29">DeepSeek (product)</a></li>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4-Pro">deepseek-ai/DeepSeek-V4-Pro · Hugging Face</a></li>
<li><a href="https://openrouter.ai/deepseek/deepseek-v4-pro">DeepSeek V4 Pro - API Pricing &amp; Benchmarks | OpenRouter</a></li>

</ul>
</details>

**社区讨论**: 用户整体情绪积极：monster\_truck 报告在分布式物理引擎上花费约 12.50 美元处理 20 亿 token（50% 缓存命中），取得了显著收益且未引入新问题；alecsm 称赞 DeepSeek Flash 的低成本能胜任繁重开发任务，并期待新款模型。jeffmcjunkin 分享了 Artificial Analysis 的基准测试页面，simonw 发布了一个有趣的 SVG 渲染器测试，而 Palmik 则批评 OpenRouter 链接缺乏信息，建议改用官方 API 文档和基准测试帖子。

**标签**: `#AI`, `#DeepSeek`, `#LLM`, `#model release`, `#machine learning`

---

<a id="item-2"></a>
## [Tailscale 将数据库损坏追溯到 16 年前的 SQLite WAL 重置 Bug](https://tailscale.com/blog/sqlite-wal-reset-bug) ⭐️ 8.0/10

Tailscale 发布了一篇事后调查，揭示了一个罕见的 SQLite WAL 重置 Bug——检查点与写事务之间的数据竞争——一直在损坏其数据库，而这个问题直到 Tailscale 资助了一个新的开源 VFS shim（tmstmpvfs）后才被定位。SQLite 于 2026-03-03 在 3.51.3 版本中修复了该 Bug。 SQLite 被嵌入到无数应用中，这个存在了 16 年的 Bug 可能在写密集负载下静默地损坏数据库。此案例还表明，为开源项目提供商业支持合同可以惠及所有人，直接提升可靠性。 该 Bug 自 2010 年起存在，当一次写入恰好在检查点进行到特定时刻发生时，检查点进程会误以为页面已从 WAL 复制到主数据库文件。Tailscale 资助的 tmstmpvfs shim 为 VFS 操作添加了时间戳，为 SQLite 团队提供了定位竞争条件所需的额外日志。

hackernews · ropbear · 8月12日 14:22 · [社区讨论](https://news.ycombinator.com/item?id=49272832)

**背景**: SQLite 使用预写式日志（WAL）来提高并发性，写入先进入 WAL 文件，随后检查点将这些更改合并到主数据库。VFS shim 是 SQLite 操作系统接口的薄包装层，可以添加插桩或功能；例如，checksum VFS shim 为每个页面添加校验和。Tailscale 使用一个 Go 进程独占访问数据库作为其控制平面，这正是 SQLite 预期的单写者用法，但竞争条件仍然发生了。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.sqlite.org/wal.html">Write-Ahead Logging</a></li>
<li><a href="https://tailscale.com/blog/sqlite-wal-reset-bug">How Tailscale helped find the SQLite WAL-Reset bug</a></li>
<li><a href="https://sqlite.org/vfs.html">The SQLite OS Interface or &quot;VFS&quot;</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的评论者称赞 Tailscale 资助开源开发，其中一人指出这是公司为特定调试工具付费的好例子。也有人对 SQLite 的 Bug 能登上头版新闻印象深刻，还有人质疑在单写者设计下竞争是如何发生的。一位评论者提到 SQLite 有 9200 万行测试，并引用 Dijkstra 的话：测试只能证明 Bug 的存在，而不能证明其不存在。

**标签**: `#SQLite`, `#database`, `#debugging`, `#open-source`, `#Tailscale`

---

<a id="item-3"></a>
## [Qwen 发布 Qwen3.8-2.4T：拥有 950 亿激活参数的巨型 MoE 模型](https://huggingface.co/Qwen/Qwen3.8-2.4T-A95B) ⭐️ 8.0/10

Qwen 发布了 Qwen3.8-2.4T-A95B，这是一个总参数达 2.4 万亿、激活参数为 950 亿的混合专家（MoE）模型，目前在 Hugging Face 上提供 BF16 和 FP8 两种格式。模型卡宣称其性能介于 Opus 4.8 与 Fable 5 之间。 此次发布加剧了开放权重大型 MoE 模型之间的竞争，使 Qwen 与 Kimi k3 和 DeepSeek V4 形成直接对标。其巨大的硬件需求以及量化部署选项，将影响关于前沿模型本地运行可行性的讨论。 官方仅发布了 BF16 和 FP8 权重，且没有提供用于 4 位量化的量化感知训练（QAT），因此低比特量化可能需要外部团队完成。据称，unsloth 的 1 比特量化版本仅需约 397GB 空间，而完整的无损 BF16 检查点约为 4.9TB。

hackernews · Philpax · 8月12日 15:01 · [社区讨论](https://news.ycombinator.com/item?id=49273478)

**背景**: 混合专家（MoE）是一种将模型划分为多个专门子模型（即“专家”）的架构，每个 token 只激活其中一部分参数，从而在保持巨大总参数量的同时降低计算成本。在 MoE 模型中，总参数与激活参数不同：激活参数是每次前向传播实际使用的参数，二者的比例会显著影响吞吐量和内存占用。FP8 量化是一种 8 位浮点格式，可以减小模型体积并加速推理，同时比整数量化保留更大的动态范围。这些概念有助于理解为什么 Qwen3.8-2.4T 总参数达 2.4T 但仅激活 95B，以及为什么量化版本对实际部署至关重要。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ibm.com/think/topics/mixture-of-experts">What is mixture of experts? | IBM</a></li>
<li><a href="https://www.emergentmind.com/topics/fp8-quantization">FP8 Quantization in Deep Neural Networks</a></li>
<li><a href="https://www.f22labs.com/blogs/active-vs-total-parameters-whats-the-difference/">Active vs Total Parameters: What&#x27;s the Difference?</a></li>

</ul>
</details>

**社区讨论**: 评论者指出，Qwen3.8-2.4T 是个“大块头”，由于仅提供 BF16 和 FP8 且没有 4 位 QAT，发布初期将比 Kimi k3 更难部署。一些人对量化版本持乐观态度，认为 unsloth 的 397GB 1 比特量化模型能把 Opus 4.5 级别性能带到消费级硬件上；另一些人则推测何时能买到足够便宜的硬件来运行它。还有评论者提到 DeepSeek V4-Pro-0813 刚公布的基准测试结果，为竞争格局提供了更多背景。

**标签**: `#AI`, `#LLM`, `#Qwen`, `#MoE`, `#model-release`

---

<a id="item-4"></a>
## [xAI 发布 Grok 4.6，引发基准测试与 API 争议](https://x.ai/news/grok-4-6) ⭐️ 8.0/10

xAI 发布了新的前沿 AI 模型 Grok 4.6。根据社区讨论，Artificial Analysis 的早期分析显示，该模型接近 Fable 级别的智能，并在大多数基准测试上超过 GPT-5.6-Sol。 此次发布加强了领先 AI 实验室之间的竞争，并以有竞争力的价格为用户提供了强大、快速的替代选择。然而，社区对基准测试有效性和 API 异常的质疑，可能会削弱对 xAI 声称能力的信任。 社区用户报告称，xAI API 会添加默认系统提示，覆盖用户指令，有时还会拒绝讨论系统提示。该模型在 Fable 发布仅两个月内就达到“Fable 级”表现，这一时机让一些人怀疑存在基准测试作弊或蒸馏。

hackernews · iLuddite · 8月12日 15:32 · [社区讨论](https://news.ycombinator.com/item?id=49274027)

**背景**: 前沿 AI 模型是当前最先进的多用途模型，经过大规模训练，在多个领域超越现有技术水平。基准测试是研究人员比较这些模型的主要方式，但基准可能被操纵——研究人员已证明，智能体可以黑掉基准测试，在不解决实际任务的情况下取得近乎完美的分数。API 异常（如注入系统提示）也是大语言模型部署中已知的问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://epoch.ai/benchmarks">AI Capabilities and Benchmarking Hub | Epoch AI</a></li>
<li><a href="https://rdi.berkeley.edu/blog/trustworthy-benchmarks-cont/">How We Broke Top AI Agent Benchmarks - Berkeley RDI</a></li>
<li><a href="https://www.nvidia.com/en-us/glossary/frontier-models/">What Are Frontier AI Models and How They Work | NVIDIA Glossary</a></li>

</ul>
</details>

**社区讨论**: 社区反应不一。一些用户对 API 默认系统提示覆盖指令表示不满，而另一些人则质疑所有主要实验室如何在两个月内突然达到 Fable 级模型，暗示存在基准测试作弊或蒸馏。也有正面评论称赞 Grok 相比 GPT 和 Claude 更简洁、快速的回复，不过也有人指出 Grok 两极分化的声誉可能限制其采用。

**标签**: `#AI`, `#Grok`, `#xAI`, `#LLM`, `#benchmarks`

---

<a id="item-5"></a>
## [谷歌 DeepMind 推出 SL2T 将手语 AI 带入消费设备](https://deepmind.google/blog/putting-sign-language-ai-into-users-hands/) ⭐️ 8.0/10

谷歌 DeepMind 发布了 SL2T 手语转文本模型，该模型现已在 Pixel 11 设备上为 Gboard 和 Live Transcribe 提供新的手语转文本功能。该模型由谷歌 DeepMind 与 Android 团队联合开发。 这标志着手语 AI 首次真正进入消费产品领域，显著提升了聋人和听障人士的可及性。这也代表着 AI 在弥合实际应用中长期存在的无障碍差距方面迈出了重要一步。 SL2T 最初在 Pixel 11 上支持美国手语（ASL），未来将逐步支持更多设备和语言。这些功能无需额外付费，是谷歌 DeepMind 与 Android 团队的合作成果。

rss · Google DeepMind · 8月12日 14:01

**背景**: 手语 AI 通过识别手势、面部表情和身体动作，将其转换为书面语言。此前这类模型大多停留在研究阶段，而 SL2T 将实时手语转文本能力带入了 Gboard 和 Live Transcribe 等日常消费工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/blog/putting-sign-language-ai-into-users-hands/">Putting sign language AI into users’ hands — Google DeepMind</a></li>
<li><a href="https://interestingengineering.com/ai-robotics/google-sign-language-model-body-landmarks">Google&#x27;s new model turns sign language into text for web searches</a></li>
<li><a href="https://cryptobriefing.com/google-deepmind-sl2t-sign-language-text-model/">Google DeepMind &#x27;s SL 2 T model brings sign language recognition to...</a></li>

</ul>
</details>

**标签**: `#AI`, `#Accessibility`, `#Sign Language`, `#DeepMind`, `#NLP`

---

<a id="item-6"></a>
## [Adam 的逐坐标缩放破坏隐式低秩偏置，而 Muon 保持该特性](https://www.reddit.com/r/MachineLearning/comments/1vmjb3p/the_loss_does_not_see_the_basis_but_adam_does_r/) ⭐️ 8.0/10

一篇在 r/MachineLearning 上展示的新 arXiv 论文（2608.05136）证明，在因子分解模型 W=UV^T 中，Adam 依赖于基的逐坐标缩放会破坏梯度下降的隐式低秩偏置，而共享标量 Adam、Muon 和 Shampoo 则能保持该偏置。实验在匹配训练损失下比较了欠定矩阵感知任务上的九种更新规则，结果形成两个清晰的分组。 这项研究将自适应优化器与梯度下降之间普遍存在的差距背后的机制加以定位：问题不在于自适应性本身，而在于逐坐标的各向异性。这可为矩阵分解和深度线性网络中依赖低秩解实现泛化的优化器设计提供指导。 在一个将 Adam 的分母从逐坐标插值为单一共享标量的单参数族上，恢复误差单调改善，从而把问题定位到各向异性而非自适应性。Muon 在真正低秩目标上表现精确，但加入谱尾后衰减最快，并在约 4%谱尾能量处出现交叉而被梯度下降超越；论文中报告的高光谱数据收益在按各方法调优学习率后会缩小，且理论仅覆盖无记忆更新规则。

reddit · r/MachineLearning · /u/EtherealGlyph · 8月12日 16:39

**背景**: 在深度矩阵分解中，损失只依赖于 W=UV^T，因此对因子做旋转 \(U,V\)→\(UQ,VQ\) 不会改变损失；梯度下降利用这一对称性，尤其在小初始化条件下会形成偏向低秩解的隐式偏置。Adam 这类自适应优化器会按每个坐标的历史梯度方差的平方根进行逐坐标缩放，这是一种依赖基的操作，因而破坏了旋转不变性。Muon 是一种面向神经网络隐层权重矩阵的矩阵结构化、几何感知优化器，采用正交化风格的更新而非逐坐标缩放。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://kellerjordan.github.io/posts/muon/">Muon : An optimizer for hidden layers in neural networks</a></li>
<li><a href="https://www.emergentmind.com/topics/implicit-bias-of-gradient-descent">Implicit Bias of Gradient Descent</a></li>
<li><a href="https://arxiv.org/pdf/2011.13772">Gradient Descent for Deep Matrix Factorization</a></li>

</ul>
</details>

**标签**: `#optimization`, `#Adam`, `#matrix factorization`, `#low-rank bias`, `#machine learning`

---

<a id="item-7"></a>
## [Florian Herrengt 警告：AI 辅助编码可能导致代码库无人能维护](https://simonwillison.net/2026/Aug/12/florian-herrengt/) ⭐️ 7.0/10

Florian Herrengt 在其博客文章《AI 正在移除软件工程的中产阶级》中描绘了一个场景：依赖 Claude 等 AI 编码助手的团队逐渐失去对代码库的理解，最终产生无人能修复的复杂 Bug。 这段引用凸显了软件开发中日益增长的认知债务和对生成式 AI 过度依赖的担忧。如果开发者无法理解自己发布的代码，软件系统的可维护性和可靠性将面临风险。 Herrengt 特别提到 AI 编码工具 Fable 和 Claude，展示了开发者让 AI 修复 Bug 却不了解底层数据流的场景。项目变得“如此复杂”，以至于团队中没有人能够开始理解它。

rss · Simon Willison · 8月12日 15:08

**背景**: 诸如 GitHub Copilot、Claude 和 Fable 之类的 AI 辅助编程工具可以根据自然语言提示生成代码，使开发者能够快速推进。然而，当开发者在不完全理解的情况下接受 AI 建议时，代码库会积累“认知债务”——即人类缺乏对代码的理解，使得未来的调试和维护变得极其困难。分享这段引用的 Simon Willison 经常讨论 AI 的滥用及其对软件工程的影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/claude/fable">Claude Fable \ Anthropic</a></li>
<li><a href="https://www.ibm.com/think/topics/claude-ai">What Is Claude AI ? | IBM</a></li>

</ul>
</details>

**标签**: `#AI`, `#software-engineering`, `#code-quality`, `#developer-productivity`

---

<a id="item-8"></a>
## [按目的地质量而非声望排名的 CS 会议排名工具](https://www.reddit.com/r/MachineLearning/comments/1vmbdk6/i_built_an_honest_cs_conference_ranking_sorted_by/) ⭐️ 7.0/10

作者构建了 honestcsrankings.org，对约 540 个即将召开的 CORE 排名会议进行映射，并按照目的地质量（天气、安全、成本、可达性和城市氛围）而非仅学术声望进行排序。该网站还设有“Upsets”标签，专门列出位于较差目的地的 A\*会议。 这解决了研究人员的实际需求——他们在选择投稿地点时，除了学术评分，也常会考虑旅行体验。它能让学术声望与目的地之间的权衡变得更加透明，并可能影响学术界选择会议的方式。 该排名使用会议当月的真实气候数据、全球和平指数（安全）、世界银行价格水平（成本）以及可达性和城市氛围评分。用户可按领域、CORE 等级或截止日期过滤；可设置家乡城市按距离排序；可将截止日期导出为.ics 文件；还可与合著者分享深层链接。部分会议缺失（ICML/ICLR 2027 未公布，COLM 尚未被 CORE 排名），而从 WikiCFP 抓取的小型会议可能存在错误。

reddit · r/MachineLearning · /u/JohnAZoidberg77 · 8月12日 11:23

**背景**: CORE 会议排名是计算领域广泛使用的会议质量排名，分为 A\*、A、B、C 等等级，常影响研究人员为职业发展选择投稿地点。但它并不考虑举办城市。该工具在 CORE 排名之上叠加了目的地因素。WikiCFP 是一个社区驱动的征文（call-for-papers）数据库，为工具提供了部分长尾会议数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://portal.core.edu.au/conf-ranks/">portal. core .edu.au/conf- ranks</a></li>
<li><a href="https://www.resurchify.com/conference-ranking">Core Conference Ranking /Rating | Top Conferences ... | Resurchify</a></li>
<li><a href="http://www.wikicfp.com/cfp/servlet/event.showcfp?eventid=70041&amp;copyownerid=93970">WikiCFP : Call For Papers of Conferences, Workshops and Journals</a></li>

</ul>
</details>

**标签**: `#CS conferences`, `#academic travel`, `#ranking tool`, `#research community`, `#CORE ranking`

---

<a id="item-9"></a>
## [消融一个注意力头使 Chessformer 无法识别弃后](https://www.reddit.com/r/MachineLearning/comments/1vmvl4w/chessformer_lens_demo_ablating_1_of_a_chess/) ⭐️ 7.0/10

Reddit 上的一个演示显示，对一个名为 Chessformer 的国际象棋 transformer 中的 128 个注意力头之一进行消融，会导致模型停止识别 Morphy 著名的弃后（queen sacrifice）。该帖子包含 GIF 和 GitHub 笔记本，供他人复现实验。 这表明单个注意力头可能编码特定的高级国际象棋模式，为机械可解释性研究提供了佐证。理解此类电路有助于解释和控制 transformer 在棋类游戏及其他推理任务中的行为。 该实验精确地消融了 128 个注意力头中的一个，并观察到模型找到 Morphy 弃后（出自 1858 年的歌剧对局）的能力急剧下降。该帖子是一个分析有限的演示，但提供了可复现的笔记本。

reddit · r/MachineLearning · /u/Weird-Asparagus4136 · 8月13日 00:29

**背景**: 机械可解释性（mechanistic interpretability）旨在通过识别神经网络所实现的具体算法和电路来对其逆向工程。注意力头消融是一种常用技术，通过将某个头的输出置零来测试其因果贡献。国际象棋 transformer 是基于人类棋谱训练的 transformer 模型；这里的 Chessformer 可能源自开源的 chess-transformers 库。Morphy 弃后是 1858 年歌剧对局中一个著名的战术组合，常被用作国际象棋 AI 的测试案例。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Mechanistic_interpretability">Mechanistic interpretability</a></li>
<li><a href="https://williamslater2003.medium.com/a-technical-walkthrough-of-attention-head-ablation-in-transformers-f3e1148fd8d6">A Technical Walkthrough of Attention Head Ablation in... | Medium</a></li>
<li><a href="https://github.com/sgrvinod/chess-transformers">GitHub - sgrvinod/ chess - transformers : Teaching transformers to...</a></li>

</ul>
</details>

**标签**: `#interpretability`, `#transformers`, `#chess`, `#attention heads`, `#ML`

---

<a id="item-10"></a>
## [中科院推出全球海洋智能预报大模型“琅琊”](https://news.google.com/rss/articles/CBMiZEFVX3lxTFAyWWRocWRPenV5blNkd1ptbkVWR1M2c1ZlUTE2N3NBUmE3bW5fV3JNU0dlejN2Ui1KQkotdHpDdWVYc0xIMXVfeTFsQ0xkYzV6cE1oeEl5TVMtbmFidXZZTGZjRnc?oc=5) ⭐️ 7.0/10

中国科学院海洋研究所的科研人员在第四届中国数字地球大会上正式发布了全球海洋现象智能预报大模型“琅琊”2.0 版。该模型可预报海洋温度、盐度和海流，未来还将支持台风、降雨、风暴潮和海冰的预报。 这标志着大型人工智能模型在海洋科学领域的应用迈出重要一步，为传统数值预报提供了更快、更准确的替代方案。它有望推动气候研究、海洋航行、灾害预警以及全球海洋动力过程认知的进步。 “琅琊”模型能够以每天 1/12°的高分辨率进行未来 1 至 7 天的跨时空预报，覆盖海水温度、盐度和海流等要素。2.0 版本实现了更快、更准确且可交互的全球海洋现象预报。

google\_news · 中国科学院 · 8月13日 02:52

**背景**: 传统海洋预报依赖求解物理方程的数值模型，计算成本高且分辨率常受限。大型人工智能模型通过从历史海洋数据中学习规律，能够更快地生成预报。“琅琊”模型是“AI for Science”趋势的一部分，此前已有 XiHe 全球涡分辨率海洋预报模型等工作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2412.18097">LangYa : Revolutionizing Cross-Spatiotemporal</a></li>
<li><a href="https://www.chinadaily.com.cn/a/202605/21/WS6a0ecce4a310d6866eb49f99.html">Decoding ocean mysteries: China&#x27;s LangYa large model set for major...</a></li>
<li><a href="https://www.aibase.com/news/28723">Predicting Complex Phenomena from Basic Variables! The Global ...</a></li>

</ul>
</details>

**标签**: `#ocean forecasting`, `#AI for science`, `#large model`, `#climate research`

---

<a id="item-11"></a>
## [传 Anthropic 拟以 60 亿美元收购 AI 初创公司 Decart AI](https://news.google.com/rss/articles/CBMiYkFVX3lxTE9LdEpQNkU5M2VOUE1jX0luZ3VxcklwRVdId0RSZWM3SnBVNVpxX0FOc3RqU0R5VGVCU3ZpRFkyUHFvRmQ5Y0dIWkVPbldMOVowQm9QWG1XUl9CQmtnM1JkZlJ3?oc=5) ⭐️ 7.0/10

据观点网报道，Anthropic 正洽谈以 60 亿美元收购 AI 初创公司 Decart AI。两家公司均未公开证实该交易。 若交易完成，这将成为迄今规模最大的 AI 收购之一，使 Anthropic 在低延迟 AI 基础设施和实时世界建模领域占据强势地位。这可能加剧与 OpenAI 和谷歌等主要 AI 实验室的竞争。 该交易目前仍属传闻，尚未获得官方确认，具体条款也未披露。Decart AI 专注于构建低延迟 AI 系统的基础设施，由 Radical Ventures 领投，其产品线包括 DOS。

google\_news · 观点网 · 8月13日 01:50

**背景**: Anthropic 是一家以 Claude 大型语言模型著称的 AI 安全与研究公司。根据其官网，Decart AI 正在为下一代低延迟 AI 系统构建基础设施，包括实时世界模型，旗下产品线包括 DOS。随着各大 AI 实验室竞相获取人才、技术和算力基础设施以保持竞争力，AI 领域的收购正在加速。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://decart.ai/">Decart AI Lab | Real-Time World Models</a></li>

</ul>
</details>

**标签**: `#AI`, `#acquisition`, `#Anthropic`, `#Decart AI`, `#industry news`

---