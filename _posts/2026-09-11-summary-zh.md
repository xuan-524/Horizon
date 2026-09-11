---
layout: default
title: "Horizon Summary: 2026-09-11 (ZH)"
date: 2026-09-11
lang: zh
---

> 从 61 条内容中筛选出 8 条重要资讯。

---

1. [OpenAI 的 Navier-Stokes 发布包含 Lean 4 形式化证明](#item-1) ⭐️ 9.0/10
2. [DeepSeek 发布 V4.1 Flash，缓存命中价格低至每百万 token 0.003 美元](#item-2) ⭐️ 9.0/10
3. [Shopify 将移动应用从 React Native 迁回原生 Swift 与 Kotlin](#item-3) ⭐️ 8.0/10
4. [研究者能否信任 OpenAI 处理未发表数学成果引发争议](#item-4) ⭐️ 8.0/10
5. [OpenAI 推出集成 GPT-6 Astra 的金融服务业版 ChatGPT](#item-5) ⭐️ 8.0/10
6. [trynix.dev 借助 qemu-wasm 在浏览器里启动任意 Nix 包](#item-6) ⭐️ 8.0/10
7. [AI 的电力瓶颈在于电网架构，而非发电量](#item-7) ⭐️ 7.0/10
8. [真实果蝇连接组学不会《Pong》，而审计失败原因才是重点](#item-8) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [OpenAI 的 Navier-Stokes 发布包含 Lean 4 形式化证明](https://www.johndcook.com/blog/2026/09/09/formal-method-revolution/) ⭐️ 9.0/10

John D. Cook 的博客文章指出，OpenAI 关于 Navier-Stokes 的发布内容中包含了一份 Lean 4 形式化证明，这一消息在 Hacker News 上引发了大规模讨论（约 136 个赞、132 条评论）。评论者围绕验证耗时、生成 Lean 代码所需 AI 智能体的成本，以及这样一份可机器检验的证明究竟意味着什么展开了争论。 如果 AI 系统如今能够产出被 Lean 4 这类证明助手真正检验通过的证明，那么 AI 生成数学结果的可信度标准就被改写了：结论不再只依赖模型的“一家之言”，而是建立在可机器验证的产物之上。这也意味着形式化方法正从冷门的学术实践进入前沿 AI 研究的标准流程，对数学家、形式验证工程师以及大规模形式化工作的成本都有实际影响。 评论者强调了其中惊人的计算规模：据说验证与费马大定理同量级的结果耗时约 15 小时、占用 230GB 内存，而生成相应 Lean 代码则花了约 11 天；智能体集群的成本估计约为 4000 万美元，而按人力每小时 150 美元计算，等价工作量约为 88 万小时、即约 1.32 亿美元，因此被广泛引用的“快四个数量级”说法并不成立。也有人质疑 Lean 本身还能优化到什么程度，因为速度与“内核必须足够简单、可被审计”之间存在矛盾。

hackernews · ibobev · 9月10日 21:22 · [社区讨论](https://news.ycombinator.com/item?id=49650326)

**背景**: Lean 4 是一个开源证明助手兼函数式编程语言，基于归纳构造演算（Calculus of Inductive Constructions），人们用它书写数学证明，再由一个体积很小的可信内核进行机器检验。形式化验证则是以数学严格性证明某个系统或命题满足形式化规范的通用做法，在数学领域通常被称为交互式或自动定理证明。Navier-Stokes 方程描述流体运动，而其解的存在性与光滑性问题属于数学中最著名的未解难题之一，这正是该领域出现形式化证明会引发如此关注的原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Lean_theorem_prover">Lean theorem prover</a></li>
<li><a href="https://en.wikipedia.org/wiki/Formal_verification">Formal verification</a></li>
<li><a href="https://en.wikipedia.org/wiki/Automated_theorem_proving">Automated theorem proving - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 社区情绪在惊叹与质疑之间：多位评论者认为通用程序能解决如此量级的问题令人震惊，也有人希望看到该模型是否能给出更直接或归纳式的证明。另一些人则反驳相关叙事，认为成本对比是“关公战秦琼”，并指出大多数讨论都忽略了真正的数学结果；还有一条评论质疑为何该帖标题在发布后被改动。一个反复出现的观点是，随着 Lean 证明自动化能力的提升，过去“每页四十小时”的形式化经验法则已经过时。

**标签**: `#Lean 4`, `#formal verification`, `#AI theorem proving`, `#Navier-Stokes`, `#OpenAI`

---

<a id="item-2"></a>
## [DeepSeek 发布 V4.1 Flash，缓存命中价格低至每百万 token 0.003 美元](https://twitter.com/deepseek_ai/status/2097930608790167907) ⭐️ 9.0/10

DeepSeek 正式发布 DeepSeek-V4.1-Flash，官方称其是新架构家族中体积最小的模型，并具备原生多模态视觉理解能力，同时在 HuggingFace 上配套发布了详细的技术报告。DeepSeek 引用的多方测试显示，V4.1-Flash 在性能、成本、速度和总运行时间上均超过更大的 V4-Pro；公司表示将逐步淘汰 V4-Pro，自 2026 年 9 月 14 日 04:00 UTC 起，所有 deepseek-v4-pro 请求将按 V4.1-Flash 的价格路由到 V4.1-Flash。 这次发布延续了 DeepSeek 的一贯做法：在推出前沿规模模型的同时公布极其透明的技术报告，这对那些主要发布安全导向系统卡片的闭源实验室构成了持续压力。极低的缓存命中价格还引出了智能体编程时代的一个更宏观的问题：当缓存 token 价格低至每百万 0.003 美元时，通过网络传输上下文的成本可能很快会超过推理本身的成本。 缓存命中的价格仅为每百万 token 0.003 美元；社区测算指出该模型总参数量已增至约 552B，而此前的 V4-Flash 预览版为 284B（本身是采用 Mixture-of-Experts 架构、激活参数 13B、支持 100 万 token 上下文的模型），这意味着“Flash”这一命名对希望本地部署的用户已不再贴切。技术报告包含大量架构与训练细节而非仅有基准测试表格，但真正的考验在于这些基准分数的大幅提升能否在基准优化的评测环境之外同样成立。

hackernews · Liwink · 9月10日 06:11 · [社区讨论](https://news.ycombinator.com/item?id=49639090)

**背景**: DeepSeek 是一家中国 AI 实验室，以发布开放权重的大语言模型并附上异常坦诚的技术文档而闻名。前沿规模模型是能力最强、体量最大的一类大语言模型，训练算力成本极高，西方实验室通常对其保持闭源。本次发布重点依赖的提示缓存（prompt caching）技术，允许 API 复用输入前缀对应的内部计算结果，因此“缓存命中”的计费远低于全新的“缓存未命中”；厂商通常对写入缓存收取溢价、对读取缓存给予折扣。而像 DeepSeek 采用的 Mixture-of-Experts（MoE）架构，每个 token 只激活一小部分参数，因此即使总参数量非常大，推理成本仍然可以保持较低。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.deepseek.com/en/news/deepseek-v4-1-flash/">DeepSeek | Introducing DeepSeek-V4.1-Flash: smarter, faster, more efficient.</a></li>
<li><a href="https://api-docs.deepseek.com/updates/">Change Log | DeepSeek API Docs</a></li>
<li><a href="https://ollama.com/library/deepseek-v4-flash">deepseek-v4-flash</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的评论总体对 DeepSeek 的技术报告评价很高，认为相比 Anthropic 式、被他们形容为以安全和“模型福祉”内容为主的系统卡片，这份报告内容实在得多；还有评论者感叹 DeepSeek 敢于在接近前沿的规模上押注新颖的训练思路，实在“无所畏惧”。另一些人则聚焦经济性与规模：有人指出每百万缓存 token 0.003 美元的价格，可能让网络传输上下文而非推理本身成为 447 轮智能体编程任务中的主要成本；也有人注意到参数量达到 552B 后它已算不上能在本地运行的“Flash”，并怀疑基准分数提升中有多少只是“刷榜”。

**标签**: `#LLM`, `#DeepSeek`, `#model-release`, `#inference-cost`, `#AI-research`

---

<a id="item-3"></a>
## [Shopify 将移动应用从 React Native 迁回原生 Swift 与 Kotlin](https://shopify.engineering/back-to-native) ⭐️ 8.0/10

Shopify 工程团队发布文章，说明公司正在将移动应用从 React Native 迁回完全原生的代码，即 iOS 使用 Swift、Android 使用 Kotlin。这一决定引发了大量讨论，Hacker News 相关帖子获得了 763 分和 512 条评论，聚焦于 AI 辅助迁移与跨平台方案的取舍。 Shopify 是 React Native 最知名的公开用户之一，因此它的“回撤”成为反对“单一跨平台代码库永远是长期最优解”这一观点的重要例证。此举可能促使其他大型产品团队重新评估原生开发，尤其是在 AI 编码工具降低了维护两套代码库的感知成本之后。 评论者指出，这次迁移在很大程度上依赖 AI 编码智能体：一位工程师称自己借助 Codex 和 Maestro 测试自动化工具，在一夜之间就把约 15 到 20 个页面转换成了 Android 与 iOS 版本；另一位则表示自己参与的那次 React Native 转原生重写大部分工作是在 LLM 辅助出现之前完成的。也有人提醒，AI 加快的是写代码，而不是读代码和手动测试，而后两者才是大型成熟产品真正的瓶颈。

hackernews · fnthawar2 · 9月10日 14:09 · [社区讨论](https://news.ycombinator.com/item?id=49643982)

**背景**: React Native 是 Meta 创建的开源框架，允许开发者用 JavaScript 和 React UI 库构建 iOS 与 Android 应用，并在多个平台间共享大量代码；Meta、微软和 Shopify 都在生产环境中使用它。其代价是共享代码往往需要针对性能、原生 API 和界面体验做平台特化的变通处理，因此一些团队最终转向分别编写 Swift（iOS）与 Kotlin（Android）应用，即所谓原生开发。近年来，基于 LLM 的编码智能体通过自动化重复性的重写、重构和平台迁移工作，让大规模代码转换变得更可行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/React_Native">React Native</a></li>
<li><a href="https://research.google/blog/accelerating-code-migrations-with-ai/">Accelerating code migrations with AI - Google Research</a></li>
<li><a href="https://snowmanlabs.com/insights/ai-assisted-code-migration">AI-Assisted Code Migration: An Enterprise Playbook</a></li>

</ul>
</details>

**社区讨论**: 整体情绪偏向支持转向原生，许多对 React Native 持怀疑态度的人感到自己的判断得到印证，并认为 AI 会让成本收益天平进一步倒向原生。也有评论者对“只有 LLM 才让这次迁移变得负担得起”的说法提出异议，分享了他们在 LLM 出现之前完成的重写经历；还有人提醒，AI 几乎无法降低阅读代码和手动测试的成本，也无法取代产品成熟后所需的专职平台工程师。

**标签**: `#React Native`, `#Shopify`, `#Mobile Development`, `#Native Development`, `#AI-assisted coding`

---

<a id="item-4"></a>
## [研究者能否信任 OpenAI 处理未发表数学成果引发争议](https://mathstodon.xyz/@andreasthom/117240535270608201) ⭐️ 8.0/10

Mathstodon 用户 @andreasthom 发布的一则帖子（并同步转发至 X 与 Bluesky）引发广泛讨论，质疑研究者能否放心把未发表的数学成果交给 OpenAI——有说法称，与 OpenAI 模型合作的研究者所分享的想法，未经署名便出现在 OpenAI 公布的成果之中。该话题在 Hacker News 上获得 654 分、624 条评论，形成一场规模可观的讨论。 这场争议触及 AI 实验室获取知识的根本方式：如果合作过程中分享的未发表洞见可以被悄然吸收进模型或研究成果而无需署名，学术界可能不再愿意把早期工作交给 AI 公司。这关系到数学家的切身利益、期刊与预印本体系中关于优先权与署名的规范，也关系到前沿实验室能否被当作可信的科研伙伴。 评论者指出，从技术上很难证明责任归属：超大规模预训练模型可能保留合作对话的隐性痕迹，而在可验证数学任务上配合海量算力进行强化学习，也可能独立地重新发现某些技巧。有评论提到，OpenAI reportedly 在一个仍在训练中的模型上生成了 3000 亿个输出 token，而时间点正是在得知某个重大数学证明很可能存在于该模型训练数据之后，该评论者认为这样的时机颇为可疑。

hackernews · pred\_ · 9月10日 06:49 · [社区讨论](https://news.ycombinator.com/item?id=49639408)

**背景**: Mathstodon.xyz 是一个面向数学爱好者的 Mastodon（联邦宇宙）实例，支持 LaTeX 渲染，因此这类讨论常在此发酵；该帖也通过注重隐私的 Twitter 前端 xcancel 同步到 X，并发布到使用去中心化标识符（DID）的 Bluesky 上。问题的根源在于，前沿 AI 模型先在海量语料上预训练，再通过强化学习精调，使得“从公开文本学到的东西”“从私人对话中吸收的内容”和“模型自己真正发现的东西”之间的界限变得模糊。而在数学界，优先权与署名由预印本、引用和以发现者命名的定理等长期规范约束，因此任何关于 AI 实验室未经署名使用未发表想法的说法都会被严肃对待。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://mathstodon.xyz/">About - Mathstodon</a></li>
<li><a href="https://discuss.privacyguides.net/t/recommend-xcancel-com-twitter-frontend/21177">Recommend xcancel.com (Twitter Frontend) - Tool Suggestions ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Bluesky">Bluesky - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍认同此事确实涉及伦理问题，但对因果关系看法不一：一种主流观点认为，如果 OpenAI 是一位人类合作者，那么沿着合作方向发表成果却不署名就是明显不道德的；另一种观点则认为两者可以同时成立——在对话数据上预训练提升了模型的潜在直觉，而在可验证数学上配合巨大算力做强化学习，也能独立发现与具体对话无关的超人技巧。有用户批评 OpenAI 迟迟不发表明确否认，称这种沉默“有点尴尬”，还有人怀疑 3000 亿 token 的生成意味着未发表证明被吸收。也有一种质疑声音问：AI 真的在快速解决开放问题，还是我们被蒙蔽了——毕竟 OpenAI 向大量研究者提供免费访问，而这些研究者自然会不断向它投喂新问题。

**标签**: `#OpenAI`, `#AI ethics`, `#research integrity`, `#mathematics`, `#AI training data`

---

<a id="item-5"></a>
## [OpenAI 推出集成 GPT-6 Astra 的金融服务业版 ChatGPT](https://openai.com/index/introducing-chatgpt-financial-services) ⭐️ 8.0/10

OpenAI 发布了 ChatGPT for Financial Services，这一专用产品将内置金融数据与新一代 GPT-6 Astra 模型结合起来，用于研究分析、财务建模以及生成可直接交付客户的材料。这标志着 OpenAI 再次将 ChatGPT 打包为面向特定行业的垂直方案，而非通用型助手。 此举把 ChatGPT 直接推向华尔街的核心工作流——研究、建模和 pitchbook 制作，这些长期以来都是初级银行分析师的主要工作，可能改变金融机构配置人力和自动化核心分析任务的方式。同时，这也体现出前沿实验室正基于旗舰模型构建行业专用产品的趋势，将加剧其与面向企业的 AI 厂商之间的竞争。 GPT-6 Astra 在 OpenAI API 中以 gpt-6-astra 的名称提供，同时可通过 Microsoft Azure 和 Amazon Bedrock 使用，标准 API 定价为每百万输入 token 10 美元、每百万输出 token 50 美元，缓存读写另按不同费率计费。不过，本次金融服务发布本身几乎没有披露技术细节，例如内置了哪些金融数据源，以及该模型在金融专用基准测试上的表现如何。

rss · OpenAI News · 9月10日 07:00

**背景**: GPT-6 Astra 是 OpenAI 最新的旗舰模型，被定位为面向职场任务的下一代系统，例如按照公司模板和语气生成格式正确的演示文稿。金融服务业是数据最密集、合规要求最严格的行业之一，分析师传统上要花费大量时间提取市场数据、搭建估值模型并为客户制作 pitchbook。OpenAI 此前已推出面向企业的 ChatGPT Enterprise 以及金融服务业解决方案页面，因此这次发布是在既有企业战略上的延伸，而非从零开始。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-chatgpt-financial-services/">Introducing ChatGPT for Financial Services | OpenAI</a></li>
<li><a href="https://openai.com/index/gpt-6-astra/">GPT - 6 Astra : A new generation of intelligence | OpenAI</a></li>
<li><a href="https://openai.com/solutions/industries/financial-services/">AI for Financial Services | OpenAI</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#ChatGPT`, `#Financial Services`, `#GPT-6 Astra`, `#AI in Finance`

---

<a id="item-6"></a>
## [trynix.dev 借助 qemu-wasm 在浏览器里启动任意 Nix 包](https://simonwillison.net/2026/Sep/10/trynix/) ⭐️ 8.0/10

Farid Zakaria 发布了 trynix.dev，它利用 qemu-wasm 在浏览器中完整运行一台 x86\_64 Linux 虚拟机，并能启动过去 13 年间的任意 Nix 包，每个环境都可以通过可分享的 URL 访问，例如 https://trynix.dev/?pkg=python3%403.6.2。他还推出了 trynix-preview——一个 GitHub Action，会在 pull request 下评论一条链接，让评审者直接在浏览器中启动该 PR 的构建结果，全程无需服务器。 它把 Nix 十多年来固定的包版本存档变成了即时可用、可复现、以 URL 定位的环境，无需服务器、容器或本地安装，对文档、教学、复现旧 bug 都很有价值，也带来了“直接启动 PR 来评审”这一新颖工作流。如果这条路走得通，运行遗留或小众软件的门槛将被降到只是打开一个网页。 所有计算都在浏览器客户端完成，因此启动耗时、Wasm 虚拟机与包的下载体积以及浏览器可用内存，决定了哪些包能被舒适地运行。由于 URL 精确锁定了包的版本，任何人打开同一链接都会得到同一环境，这正是分享机制有价值的原因。

rss · Simon Willison · 9月10日 23:44

**背景**: Nix 是由 Eelco Dolstra 于 2003 年创建的跨平台纯函数式包管理器，它把软件包视为不可变的值并存储于唯一路径中，因此多年之后旧版本依然可以构建和复现。WebAssembly（Wasm）是一种面向栈式虚拟机的可移植二进制指令格式，2017 年发布、2019 年成为 W3C 推荐标准，使接近原生性能的代码可以在浏览器中运行。qemu-wasm 是 ktock 将 QEMU 系统模拟器实验性移植到浏览器的项目，它借助 QEMU 的 TCG（微型代码生成器）在 Wasm 中模拟 CPU 指令，这正是能在一个标签页里启动完整 x86\_64 Linux 虚拟机的原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ktock/qemu-wasm">GitHub - ktock/qemu-wasm: QEMU on browser · GitHub</a></li>
<li><a href="https://en.wikipedia.org/wiki/Nix_%28package_manager%29">Nix (package manager)</a></li>
<li><a href="https://en.wikipedia.org/wiki/WebAssembly">WebAssembly</a></li>

</ul>
</details>

**标签**: `#nix`, `#webassembly`, `#qemu`, `#virtualization`, `#browser`

---

<a id="item-7"></a>
## [AI 的电力瓶颈在于电网架构，而非发电量](https://www.technologyreview.com/2026/09/10/1141649/powering-ai-is-an-architecture-problem/) ⭐️ 7.0/10

《麻省理工科技评论》的一篇分析文章指出，AI 数据中心不断攀升的用电需求暴露的是电网架构上的结构性弱点，而不仅仅是发电容量不足的问题。文章以弗吉尼亚州阿什本（全球最大数据中心集群所在地）的事故为例：2026 年 7 月 22 日一条输电线路故障在数秒内让超过 3 吉瓦的负荷脱离电网；而两年前，仅一个失效的避雷器就同时使约 60 座弗吉尼亚设施、约 1500 兆瓦负荷掉线。 如果 AI 产能的瓶颈在于电网架构而非单纯的电力供应，那么制约 AI 扩张的关键就不只是多建电厂，而是重新设计电网如何承载巨大且快速波动的负荷。这会影响超大规模云厂商、电力公司、电网运营商和监管机构，也把 AI 基础设施规划重新定位为能源系统工程问题。 文中列举的事件表明，单个元件失效或线路故障就可能在数秒内级联成吉瓦级的负荷损失，而且同一地区已不止一次发生。文章把问题定性为结构与架构层面，意味着冗余设计、保护配合和甩负荷策略——而不只是发电装机兆瓦数——决定了电网能安全承接多少 AI 负荷。

rss · MIT Technology Review AI · 9月10日 11:00

**背景**: 电网架构（grid architecture）是一门把系统架构、网络理论与控制理论应用于电力系统的学科，用以高层级地描述发电、输电、配电与控制之间的复杂交互，已被美国电力研究院（EPRI）等机构采纳为电网现代化规划的基础。避雷器（surge arrester）是一种保护装置，通过把浪涌电流导入大地来限制输配电设备上的电压尖峰，因此一旦失效就可能触发更大范围的保护动作。输电线路故障是线路上的异常状态，保护系统必须迅速检测并隔离，有时会引发自动重合闸和甩负荷，正如文中这些事故所呈现的。与大多数负荷不同，数据中心的负荷高度集中，且可在近乎瞬间内掉落或恢复数百兆瓦，这对电网稳定性的冲击是传统规划方法未曾充分预料的。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gridarchitecture.pnnl.gov/">PNNL: Grid Architecture</a></li>
<li><a href="https://en.wikipedia.org/wiki/Surge_arrester">Surge arrester</a></li>
<li><a href="https://en.wikipedia.org/wiki/Electrical_fault">Electrical fault - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI infrastructure`, `#data centers`, `#energy grid`, `#power systems`, `#sustainability`

---

<a id="item-8"></a>
## [真实果蝇连接组学不会《Pong》，而审计失败原因才是重点](https://www.reddit.com/r/MachineLearning/comments/1wc67ci/i_tried_to_make_a_real_fly_connectome_learn_to/) ⭐️ 7.0/10

一位开发者尝试用多巴胺式可塑性，让新发布的 MaleCNS v1.0 果蝇连接组（16.6 万个神经元、真实电子显微镜重建）的一个小型真实子图学会玩《Pong》，结果它完全没有学会——在多个随机种子下，开启学习与关闭学习得到的输出逐比特完全相同，尽管底层权重确实在变化。作者把失败追溯到几个具体缺陷：neuPrint 的正则表达式使用了全匹配而非子串匹配语义，悄悄把两个完整神经元群体清零；最初的神经元选取根本不存在从感光细胞到其他任何节点的通路；四个运动神经元中有一半与任何感觉通路都没有突触连接，因此无论学习规则如何都永远不会放电。 这一结果直接挑战了近期走红的“果蝇大脑玩《Doom》《Minecraft》《Beat Saber》”视频：作者查阅了这些项目自己的代码仓库，发现它们自认失败——Doom 项目称其经六轮迭代后未通过自设的验证门槛；Minecraft 模组的局限性章节承认真实运动检测通路始终沉默、行为是手工注入的；Beat Saber 作者也承认其过拟合到单一曲目且把回放数据混入了输入。文章主张，经过严谨审计的负面结果——以及由此暴露的连接性缺陷——比一个在宽容游戏引擎里“看起来活着”的演示更有价值，这对从事连接组仿真或计算神经科学的人尤其重要。 作者重新搭建的回路只有在把威胁检测通路换成与求偶追逐中的视觉目标追踪相关的通路后，才首次与关闭学习产生差异，而这一字面上的生物学假设本身也被数据推翻，直到找到另一个真正端到端连通的下降神经元。即便如此，效果更像是学习规则把整个系统整体压静，而非技能提升：由于失误多于命中，惩罚占主导，从而缩小了运动响应。

reddit · r/MachineLearning · /u/oPeraza2007 · 9月10日 02:28

**背景**: 连接组是神经系统中每个神经元与突触的接线图，通过连续切片电子显微镜成像并逐个追踪细胞重建而成。MaleCNS v1.0 由 HHMI Janelia 的 FlyEM 团队联合剑桥大学、MRC 分子生物学实验室和 Google Research 于 2026 年 6 月 8 日以 CC-BY 4.0 许可发布，包含雄果蝇大脑和中枢神经系统中超过 16.6 万个神经元与约 1.25 亿个突触连接。neuPrint 是 Janelia 提供的开放获取 API 与网页工具，用于查询这些电镜连接组；而多巴胺式可塑性指由神经调质性的奖赏或惩罚信号来调整突触权重的学习规则，是生物回路强化学习模型中常见的机制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://male-cns.janelia.org/">Male CNS Connectome - MaleCNS connectome</a></li>
<li><a href="https://neuprint.janelia.org/help/api">neuPrintExplorer - Janelia Research Campus</a></li>
<li><a href="https://hothardware.com/news/google-mapped-a-fruit-fly-brain-so-engineers-taught-it-to-play-doom">Google Mapped A Fruit Fly Brain, So Engineers Taught It To Play Doom</a></li>

</ul>
</details>

**标签**: `#connectome`, `#computational-neuroscience`, `#reinforcement-learning`, `#negative-results`, `#fly-brain`

---