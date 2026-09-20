---
layout: default
title: "Horizon Summary: 2026-09-20 (ZH)"
date: 2026-09-20
lang: zh
---

> 从 53 条内容中筛选出 5 条重要资讯。

---

1. [陶哲轩：数学应重视直觉，而非只推崇证明](#item-1) ⭐️ 8.0/10
2. [Hacker News 排序算法解析：投票、时间衰减与争议惩罚](#item-2) ⭐️ 7.0/10
3. [非自回归 RL 决策模型引发 HN 对创新性与品牌营销的争论](#item-3) ⭐️ 7.0/10
4. [PlanetScale 推出面向 Postgres 的 TIN 全文搜索](#item-4) ⭐️ 7.0/10
5. [ProgramAsWeights 将英文功能描述编译为可在本地运行的神经程序](#item-5) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [陶哲轩：数学应重视直觉，而非只推崇证明](https://terrytao.wordpress.com/2026/09/18/if-math-is-more-than-proof-we-need-to-better-celebrate-the-rest-of-it/) ⭐️ 8.0/10

陶哲轩（Terry Tao）发表了一篇文章，主张数学界应当更好地推崇形式化证明之外的数学实践——直觉、合作与阐述，而不应把证明当作唯一的价值标准。他把这视为一种迫切的文化纠偏，因为人工智能正在对以证明为核心的学术工作流程施加压力。 这篇文章触及数学家的聘用、晋升与评奖机制，因为终身教职与学术声望在很大程度上仍取决于能否产出高难度证明。如果人工智能越来越多地代劳证明的寻找过程，整个行业可能需要重新评估直觉、教学与阐述的价值——这一转变将影响学术生涯、科研经费以及数学的教学方式。 这篇文章是文化层面的论述，而非技术成果，也没有提出用于奖励非证明类工作的具体评价指标。周围的大量讨论集中在一点上：制度性激励——尤其是终身教职的考核要求和设有年龄上限的菲尔兹奖等奖项——是否真的能够被重新设计，以契合陶哲轩所描述的价值取向。

hackernews · num42 · 9月19日 06:28 · [社区讨论](https://news.ycombinator.com/item?id=49763928)

**背景**: 陶哲轩是当今最杰出的数学家之一，也是菲尔兹奖得主，因此他关于数学文化与数学实践的文章在学界具有超乎寻常的分量。在学术数学中，严谨的证明历来是确立新知识的最终成果，而职业晋升也围绕着产出证明来构建。能够协助甚至自动生成数学论证的人工智能系统的兴起，对这一格局构成了挑战，也引发了关于人类数学家应当做出哪些不可替代贡献的疑问。

**社区讨论**: 评论者普遍认同数学界已从重视直觉转向重视证明：有人援引 1900 年庞加莱与希尔伯特的那场著名争论，感叹中学与应用型大学已经丢失了直觉这一面。也有人认为数学界如今遭遇的人工智能冲击比软件开发者所经历的更为猛烈，因为对许多数学家而言，可被自动化的任务正是他们工作的本体；还有人指出，菲尔兹奖的年龄上限实际上更偏向原始智力而非更深层的理解。此外，有观点提到，算出更多位圆周率或发现新的梅森素数这类计算壮举虽被当作“数学新闻”，却引不起在职数学家的兴趣。

**标签**: `#mathematics`, `#AI`, `#academia`, `#Terry Tao`, `#proof`

---

<a id="item-2"></a>
## [Hacker News 排序算法解析：投票、时间衰减与争议惩罚](https://www.righto.com/2013/11/how-hacker-news-ranking-really-works.html) ⭐️ 7.0/10

Ken Shirriff（Hacker News 用户 kens）于 2013 年发表的一篇解析 Hacker News 排序算法的技术文章再次登上 HN，获得 138 分和 69 条评论。作者本人也现身评论区打招呼，讨论主要围绕这套系统在 13 年间的演变展开。 排序算法决定了数百万用户最终能看到哪些内容，因此这篇基于数据分析、详细拆解投票、时间衰减与版主惩罚机制的文章，对任何构建信息流、论坛或推荐系统的人都是极具价值的参考。文章还揭示了一种与现代“最大化互动量”平台相反的设计取向：争议性帖子会被刻意降权，而不是被推上首页。 根据该分析，HN 的帖子得分大致为 \(得分 - 1\) / \(发布小时数 + 2\)^1.8，因此时间衰减会迅速削弱较老帖子的排名；此外系统还会对评论数远超投票数的“争议帖”以及某些域名施加额外惩罚。需要注意的是，这只是 2013 年的快照，评论者和作者都认为如今线上系统几乎肯定更加复杂，而且在高 karma 区间，发帖获得的 karma 与点赞数并非线性关系。

hackernews · theanonymousone · 9月19日 21:30 · [社区讨论](https://news.ycombinator.com/item?id=49770293)

**背景**: Hacker News 是由创业孵化器 Y Combinator 运营的链接聚合与讨论网站，用户提交链接并进行点赞或反对。与 Reddit 的“Hot”排序类似，其首页排名由帖子的净投票数与时间衰减因子共同决定，从而让新鲜且得票高的内容有机会超越更早、更热门的帖子。文章作者 Ken Shirriff 是知名的硬件与逆向工程博主，他的这篇文章是最早尝试从公开数据中反推 HN 评分公式的作品之一。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=6799854">How Hacker News ranking really works: scoring, controversy , and...</a></li>
<li><a href="https://medium.com/hacking-and-gonzo/how-hacker-news-ranking-algorithm-works-1d9b0cf2c08d">How Hacker News ranking algorithm works | by Amir... | Medium</a></li>
<li><a href="https://jkchu.com/2016/02/17/designing-and-implementing-a-ranking-algorithm/">Designing and Implementing a Ranking Algorithm ... // jkchu.com</a></li>

</ul>
</details>

**社区讨论**: 评论者深入探讨了算法的设计意图：Liftyee 追问将争议帖降权是为了防止骂战达到临界规模，还是为了避免 HN 被视为一个充满争吵的论坛。compiler-guy 介绍了由版主运营、用于打捞被忽视帖子的“二次机会池”；zdw 反映在 karma 超过约 10 万后，帖子获得的点赞不再与 karma 一比一对应；tptacek 则总结说，如今这套系统比 2013 年的模型“复杂得多得多”。

**标签**: `#hacker-news`, `#ranking-algorithms`, `#recommender-systems`, `#community-moderation`, `#social-media`

---

<a id="item-3"></a>
## [非自回归 RL 决策模型引发 HN 对创新性与品牌营销的争论](https://laya.convaiinnovations.com/) ⭐️ 7.0/10

一位一年前就用 PPO 在序列表示之上构建非自回归决策模型的作者，对某前沿实验室（Jev/Typesafe）以自家 RLCD（Reinforcement Learning for Calibrated Decisions）框架发布高度相似概念、并称之为&quot;突破&quot;一事作出回应；该产品定价为每百万输入 token 0.042 美元，响应时间约 150 毫秒。由此引发的 Hacker News 讨论帖（1079 分、262 条评论）同时争论了技术新颖性以及营销在概念传播中的作用。 这一事件凸显了 AI 领域反复出现的张力：功劳应归于已部署、包装良好的产品，还是其背后的已发表研究，以及&quot;突破&quot;式措辞如何掩盖某想法早已被探索过的事实。它也表明，非自回归的并行决策模型正成为分类与决策任务中 LLM 方案的竞争性替代。 评论者指出，Jev 发布时没有技术论文、开放权重或公开训练数据集，一位实测者称它本质上就是&quot;数据更多的 BERT&quot;——比 LLM 更快更便宜、一致性不错，但谈不上突破。原作者模型则通过 PPO 输出垂直销售对话中逐轮转换轨迹（0.0 到 1.0 之间的概率）。

hackernews · nandakishor\_ml · 9月19日 10:46 · [社区讨论](https://news.ycombinator.com/item?id=49765348)

**背景**: 自回归模型（如 GPT）逐元素生成输出，每个元素依赖前一个；而非自回归模型则并行生成所有元素，可提升推理速度但可能降低质量。PPO 等强化学习技术被用于训练模型趋于期望的行为或决策结果。Jev（后与 Typesafe 之名一同被提及）正是这场对比中被拿来比较的品牌化产品。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dev.to/nandakishor_m_6cc0adfde9f/i-built-non-autoregressive-decision-models-a-year-ago-then-a-frontier-lab-called-it-a-18me">I Built Non-Autoregressive Decision Models a Year Ago. Then a Frontier Lab Called It a &quot;Breakthrough&quot;. - DEV Community</a></li>
<li><a href="https://www.linkedin.com/posts/tayefur-rahman_autoregressive-vs-non-autoregressive-model-activity-7373698446244880385-T0pn">Autoregressive vs Non - Autoregressive Models : NLP... | LinkedIn</a></li>

</ul>
</details>

**社区讨论**: 社区情绪褒贬不一但整体偏向质疑其技术新颖性：有评论者认为 Jev 的宣传语（&quot;突破&quot;、&quot;两年秘密研发&quot;、&quot;不会产生幻觉&quot;）读起来像戏仿或营销话术，也有人主张品牌与清晰表达本就与产品同等重要。一位实测者认为它本质上只是更快更便宜的 BERT 式分类器而非突破，另一位则认为考虑到该领域共享的研究脉络，原作者的抱怨显得有些幼稚。

**标签**: `#reinforcement-learning`, `#non-autoregressive-models`, `#AI/ML`, `#Hacker News`, `#model-announcement`

---

<a id="item-4"></a>
## [PlanetScale 推出面向 Postgres 的 TIN 全文搜索](https://planetscale.com/blog/introducing-tin) ⭐️ 7.0/10

PlanetScale 推出了 TIN，这是一个面向 Postgres 的全功能全文搜索索引，可直接在数据库内部提供 BM25 排序和倒排索引搜索能力。该功能以其云平台上的托管服务形式提供，同时在 GitHub 上发布的本地扩展（planetscale/lead）主要用于让开发者测试查询语法。 此次发布让 Postgres 搜索扩展生态又多了一个新成员，此前已有 ParadeDB 的 pg\_search、Timescale 的 pg\_textsearch 以及 Neon 的 pg\_search 等，这表明全文搜索正逐渐成为托管 Postgres 服务的标配能力。这也凸显了托管数据库长期存在的一个矛盾：最佳性能可能只在厂商云端可用，而自托管或本地部署无法获得。 据社区成员指出，开源的本地扩展在性能上并不等同于云服务——它被描述为主要用于测试的语法兼容版本，这意味着开发者无法在 PlanetScale 的基础设施之外复现生产环境的性能表现。PlanetScale 的发布说明主要依赖厂商自测的基准数据，因此独立验证仍有待进行。

hackernews · ksec · 9月19日 13:52 · [社区讨论](https://news.ycombinator.com/item?id=49766611)

**背景**: Postgres 自带基于 tsvector、tsquery 和 ts\_rank 的全文搜索能力，支持函数索引和查询优化，但常被认为相关性排序较弱、索引体积偏大。较新的扩展通过实现 BM25（由 Lucene/Elasticsearch 普及的排序算法）以及倒排索引和更丰富的查询语法来弥补这些不足。托管数据库厂商通常在自有基础设施上运行存储和查询引擎，因此能够进行本地安装的扩展无法实现的性能调优。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://planetscale.com/blog/introducing-tin">Introducing TIN: full-text search for Postgres — PlanetScale</a></li>
<li><a href="https://planetscale.com/changelog/tin-text-search">TIN: Postgres full-text search — PlanetScale</a></li>
<li><a href="https://neon.tech/docs/extensions/pg_search">The pg_ search extension - Neon Docs</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍认为，这一波新的 Postgres 搜索工具反映了 AI 辅助编码在现实世界带来的生产力提升，并列举了 ParadeDB、Timescale、Neon 和 Databricks 等并行项目。最尖锐的批评是本地扩展只提供语法兼容，而非云服务的性能；还有多位用户质疑，在 Postgres 已有成熟内置全文搜索的情况下，为何要采用一个第三方、可能属于“vibecoded”的扩展。也有人指出 SQLite 的 FTS 在执行 Lucene 风格查询时性能出色，并好奇 Postgres 为何不能采用类似方案。

**标签**: `#PostgreSQL`, `#full-text search`, `#PlanetScale`, `#databases`, `#search`

---

<a id="item-5"></a>
## [ProgramAsWeights 将英文功能描述编译为可在本地运行的神经程序](https://www.reddit.com/r/MachineLearning/comments/1wl13eu/programasweights_compile_english_function/) ⭐️ 7.0/10

滑铁卢大学的一位研究者发布了开源项目 ProgramAsWeights（PAW），它可以把一段英文的文本功能描述编译成一个可复用的“神经程序”，随后在本地运行，甚至能在 CPU 上跑，调用方式类似 paw.compile\_and\_load\(&quot;Classify urgent emails&quot;\) 这样的简单 Python 调用。其标准编译器是一个微调过的 Qwen3-4B 模型，为冻结的 Qwen3-0.6B“解释器”生成 LoRA 适配器；生成的程序包含该适配器、清理后的任务描述以及少量输入输出示例，因此编译只做一次，而推理始终在本地并可重复执行。 PAW 为基于 LLM 的文本功能提出了一种“编译/推理分离”的思路：一次性地摊销昂贵的部分（理解任务），然后在本地反复运行廉价的部分，不需要 API 密钥、不产生按次调用费用，也不依赖网络。在其 FuzzyBench 基准上，搭配 0.6B 解释器的 PAW 达到 73.4% 的精确匹配准确率，而直接提示 Qwen3-32B 只有 68.7%，这表明在狭窄且固定的任务上，小型专用程序可以胜过规模大得多的通用模型。 编译只需几秒，程序生成之后就不再需要大型编译器模型；冻结的 0.6B 解释器基础权重始终不变，变化的只是所加载的适配器。程序可以保存、分发，并能与普通代码组合；此外还有一种名为“Compile by Training”的后续模式，利用教师模型合成任务专属示例，对生成的适配器再微调约 100 步（约一分钟），在更难的 FuzzyBench-Hard 子集上取得更高准确率。该工作仍属于早期研究项目帖子，未经同行评审，且自行托管编译器需要 GPU。

reddit · r/MachineLearning · /u/yuntiandeng · 9月19日 23:35

**背景**: 传统上，若要用大语言模型处理一个固定的文本任务，就得把每次输入都发往托管的 API，按调用次数付费并依赖网络。PAW 借用了经典编译器的类比：程序的含义在编译期一次性确定，之后被反复执行。在技术上它使用 LoRA（低秩适配），这是一种给冻结模型附加小型可训练权重更新的方法，其适配器生成机制类似 text-to-LoRA（Charakorn 等，2025）。人们常把它与 TypeSafe AI 的快速“System One”结构化输出模型 Jev 相提并论，后者同样是用快速、狭窄的决策来替代通用文本生成。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/programasweights/programasweights-python">GitHub - programasweights/programasweights-python: Python SDK for ProgramAsWeights — compile natural language specs into neural programs that run locally</a></li>
<li><a href="https://programasweights.com/">PAW — Define functions in English, run them locally</a></li>
<li><a href="https://github.com/programasweights/programasweights-js">GitHub - programasweights/programasweights-js: Browser SDK for ProgramAsWeights — run neural programs in the browser via WebAssembly</a></li>

</ul>
</details>

**标签**: `#neural-programs`, `#natural-language-to-code`, `#local-inference`, `#compilation`, `#LLM`

---