---
layout: default
title: "Horizon Summary: 2026-10-03 (ZH)"
date: 2026-10-03
lang: zh
---

> 从 56 条内容中筛选出 6 条重要资讯。

---

1. [新型 AI 以少 34 倍的训练量击败顶尖 Stratego 棋手](#item-1) ⭐️ 9.0/10
2. [Greg Kroah-Hartman 驳斥 Anthropic Mythos 的 79 个内核 CVE](#item-2) ⭐️ 8.0/10
3. [博客探讨 Linux 在 Apple M4 芯片上的运行表现](#item-3) ⭐️ 7.0/10
4. [Meta 推出 Muse Gadgets SDK，让自制硬件接入其 AI 智能体](#item-4) ⭐️ 7.0/10
5. [AI 研究者 Thore Graepel 认为大语言模型并不真正具备推理能力](#item-5) ⭐️ 7.0/10
6. [NeurIPS 2026 论文聚焦动力系统重构中的拓扑域外泛化](#item-6) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [新型 AI 以少 34 倍的训练量击败顶尖 Stratego 棋手](https://arstechnica.com/science/2026/10/ai-finally-beat-the-best-stratego-player-in-history-and-did-it-on-a-budget/) ⭐️ 9.0/10

一套新型 AI 系统成为首个击败顶尖人类 Stratego 棋手的程序，相关成果已发表在《Nature》上，并在 arXiv 预印本（2511.07312）中给出细节。据报道，该系统的训练对局数比 DeepMind 在 2022 年提出的 DeepNash 少约 34 倍，但最终实力反而强得多。 Stratego 是一种不完全信息博弈，棋盘上的大部分状态对玩家是隐藏的，这使得国际象棋和围棋引擎常用的“向前搜索”方法从根本上不再适用。能在这种游戏上击败顶尖人类，说明结合强化学习与隐藏信息下搜索的方法已经成熟，而训练成本的大幅下降也让这类方法在涉及私有或未知信息的其他问题上更具实用价值。 DeepNash 在 2022 年的成果需要海量的自我对弈，而新智能体仅用约 34 倍更少的对局就实现收敛，说明其在隐藏信息搜索或信念建模方面实现了更高的样本效率。其具体架构、硬件开销以及所击败人类对手的水平，均在《Nature》论文和配套 arXiv 预印本中有详细说明。

hackernews · PaulHoule · 10月2日 14:11 · [社区讨论](https://news.ycombinator.com/item?id=49933740)

**背景**: Stratego 是一种双人棋盘游戏，棋盘为 10×10 的方格，中央有两个 2×2 的“湖泊”，棋子不能进入；双方各控制 40 枚代表不同军衔的军官与士兵棋子。其特殊之处在于对手棋子的军衔对你是隐藏的，只有当棋子交锋时你才知道它是什么，因此它是典型的不完全信息博弈——一步棋的好坏取决于你根本无从得知的信息。DeepMind 在 2022 年推出的 DeepNash 是首个能以人类专家水平玩 Stratego 的系统，采用的是无模型强化学习。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.deeplearning.ai/the-batch/deepnash-the-rl-system-that-plays-stratego-like-a-master">DeepNash, the RL System That Plays Stratego like a Master</a></li>
<li><a href="https://www.ultraboardgames.com/stratego/game-rules.php">How to play Stratego | Official Rules | UltraBoardGames</a></li>
<li><a href="https://strategus.appspot.com/rules.html">Stratego game rules</a></li>

</ul>
</details>

**社区讨论**: Hacker News 的评论者对这款游戏充满怀旧情绪，也对它长期难倒 AI 感到意外；被点赞最多的观点认为，训练对局数减少 34 倍才是真正的关键贡献，因为隐藏信息使得传统意义上的前瞻搜索根本无法进行。还有人分享了用做了暗记的棋子作弊的趣事，并调侃自己本来打算亲手做出一个能赢的 Stratego 机器人。

**标签**: `#AI`, `#game playing`, `#reinforcement learning`, `#imperfect information`, `#Stratego`

---

<a id="item-2"></a>
## [Greg Kroah-Hartman 驳斥 Anthropic Mythos 的 79 个内核 CVE](https://www.youtube.com/watch?v=NnV_cWeoo5Q) ⭐️ 8.0/10

在 Kernel Recipes 2026 的演讲中，Linux 内核稳定版维护者 Greg Kroah-Hartman 对 Anthropic 声称由其 Claude Mythos 模型发现的 79 个内核漏洞逐一进行了核查，认为其中大多数并非真正的新发现。他的幻灯片数据显示：24 个报告只写着“某个东西崩溃了”而毫无细节，14 个根本算不上漏洞，3 个数据是凭空捏造的，还有 15 个在最新版本中早已修复——真正需要修复的只剩约 20 个。 这一批评直接挑战了“大模型驱动的漏洞挖掘是软件安全领域的质变”这一营销叙事，而提出者又是开源维护领域最具公信力的人物之一。它还牵出一个伦理问题：据称 Anthropic 并未向那些早已修复过相关问题的内核开发者致谢，而模型的发现正是基于这些历史补丁的模式，这与此前针对 OpenAI 的同类署名批评如出一辙。 在 15 个早已修复的漏洞中，有 11 个是由其他开发者修补的，只有 4 个出自 Anthropic 之手；而在约 20 个真正需要修复的问题里，有 7 个的前提是“假设存在恶意文件系统镜像”，另有 2 个假设攻击者能够以在多数部署场景下并不现实的方式篡改某些内容。Kroah-Hartman 的核心技术论点是：Mythos 本质上是在对过去几十年内核补丁做模式匹配，再把这些修复机制套用到别处，看看它们是否被普遍应用了。

hackernews · usernomdeguerre · 10月2日 02:51 · [社区讨论](https://news.ycombinator.com/item?id=49929391)

**背景**: Greg Kroah-Hartman 是 Linux 内核稳定分支的维护者，也是内核开发领域资历最深的人物之一，因此他的评价在开源社区中分量极重。新闻中提到的漏洞是 CVE（Common Vulnerabilities and Exposures，通用漏洞披露），即用于编目已公开披露安全缺陷的标准编号体系。Anthropic 的 Claude Mythos 是该公司宣称在网络安全任务上表现突出的模型，曾被指自主发现了 OpenBSD、FFmpeg 等项目的零日漏洞，出于安全考虑目前仅向少数经过审核的合作伙伴开放。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://red.anthropic.com/2026/cvd/">Anthropic&#x27;s coordinated vulnerability disclosure dashboard</a></li>
<li><a href="https://www.anthropic.com/claude/mythos">Claude Mythos \ Anthropic</a></li>
<li><a href="https://en.wikipedia.org/wiki/Common_Vulnerabilities_and_Exposures">Common Vulnerabilities and Exposures - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论者几乎一边倒地赞赏 Kroah-Hartman 的坦率，并自行拆解了幻灯片数据，其中一位指出，整个“79 个漏洞”的营销攻势最终只相当于大约一小时的内核开发工作量。讨论的主线是 Anthropic 在“可能毁灭世界”的风险警告与不向原始补丁作者致谢之间的强烈反差；不过也有评论者认为，用内核专门知识训练的专用模型未来让漏洞发现更快、更准甚至做到以前不可能的事，并非天方夜谭。

**标签**: `#ai-security`, `#linux-kernel`, `#llm`, `#vulnerability-research`, `#open-source`

---

<a id="item-3"></a>
## [博客探讨 Linux 在 Apple M4 芯片上的运行表现](https://yuka.dev/blog-2026-10-02-linux-m4.html) ⭐️ 7.0/10

一篇题为《The Forgetful CPU \(Linux on M4\)》的博客文章探讨了 Linux 在 Apple M4 处理器上运行时的行为，在 Hacker News 上获得了 112 分和 38 条评论。文章聚焦于在 Apple 封闭芯片上运行开源系统时出现的某种具体异常，由此引发的讨论最终演变为关于 Apple 硬件开放性的争论。 它凸显了希望在 Apple Silicon 上运行 Linux 的用户所面临的实际阻力，而随着 Apple 芯片在笔记本性能上持续领先，这一需求群体还在扩大。相关讨论也延续了围绕开放硬件、厂商锁定，以及平台所有者对用户所购设备应有多大控制权的更大争论。 这篇文章是面向系统与开源爱好者的技术深挖，不过有观察者指出，Hacker News 上的讨论更多是观点表达而非技术层面的深入探讨。由于 Apple 并不官方支持在 Apple Silicon 上运行 Linux，这类报告通常来自社区逆向工程的成果，而非厂商文档。

hackernews · signa11 · 10月2日 14:22 · [社区讨论](https://news.ycombinator.com/item?id=49933869)

**背景**: Apple M4 是一款基于 ARM 架构的系统级芯片（SoC），集成了 CPU、GPU、神经网络处理单元和数字信号处理器，属于用于现代 Mac 的 Apple Silicon 系列。这些 Mac 出厂只搭载 macOS，且 Apple 很少公开底层硬件文档，因此要运行 Linux 就得依靠 Asahi Linux 这类社区项目去逆向工程启动流程、电源管理和外设驱动。像本文这样的博客正是在记录这一过程中不可避免会出现的各种 bug 与怪癖。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://asahilinux.org/">Asahi Linux</a></li>
<li><a href="https://en.wikipedia.org/wiki/Apple_M4">Apple M4 - Wikipedia</a></li>
<li><a href="https://www.notebookcheck.net/Apple-M4-10-cores-Processor-Benchmarks-and-Specs.835975.0.html">Apple M4 (10 cores) Processor - Benchmarks and Specs</a></li>

</ul>
</details>

**社区讨论**: 评论者主要关注 Apple 对开放硬件的态度，而非技术细节：有人称若 Apple 拥抱开放，规模本可以大得多，并一边称赞其硬件、一边批评 macOS 过于臃肿。另一位则质疑，为运行开源软件而购买一家“对任何开放事物都充满敌意”的公司的机器是否合逻辑；还有人好奇能否用 AI 来自动完成移植工作。

**标签**: `#Linux`, `#Apple Silicon`, `#M4`, `#CPU Architecture`, `#Systems`

---

<a id="item-4"></a>
## [Meta 推出 Muse Gadgets SDK，让自制硬件接入其 AI 智能体](https://gadgets.muse.ai/) ⭐️ 7.0/10

Meta 发布了 Muse Gadgets，这是一个开源 SDK 与固件项目，允许开发者把细分领域的创客硬件（例如 Seeed 的 reTerminal 以及基于 ESPHome 的设备）接入 Meta 的 Muse AI 智能体，并且把代码免费公开。TechCrunch 与 Engadget 的报道将其描述为 Meta 邀请开发者自行打造 Muse 驱动的设备，而不仅仅购买 Meta 自家产品。 这一举动表明 Meta 正在战略性地押注开放硬件实验，借此把自家 AI 智能体从手机和自有硬件扩展到更广的场景，并可能在智能家居与物联网开发者社区中站稳脚跟。它也再次凸显了行业内反复出现的矛盾：开发者工具本身确实有用，但生态锁定与隐私方面的担忧同样真实。 该项目刻意面向细分硬件——有评论者指出它覆盖了 Seeed reTerminal E1001，而此人此前已用 ESPHome 为其搭建晨间简报——因此目前覆盖面仅限于创客与爱好者级别的开发板，而非主流消费设备。Meta 免费分发该 SDK 与固件，并将其与自家首款 AI 智能体设备 Muse Charm 放在同一条产品线上。

hackernews · anant · 10月2日 19:26 · [社区讨论](https://news.ycombinator.com/item?id=49937504)

**背景**: Muse 是 Meta 面向个人 AI 智能体的品牌，其中包括可通过语音、触控和摄像头连接智能体的 Muse Charm 设备。ESPHome 是一个开源固件框架，可以用声明式配置的方式让廉价的 ESP32/ESP8266 微控制器接入 Home Assistant 等家庭自动化平台；Seeed 的 reTerminal 系列则是一类小巧、适合创客的 Linux 或电子墨水屏开发板。Muse Gadgets 实际上是把这些 DIY 层级与 Meta 云端智能体连接起来，思路与其他厂商通过开发者套件争夺智能家居助手入口的做法类似。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://techcrunch.com/2026/10/02/meta-wants-you-to-build-your-own-muse-gadget/">Meta wants your next gadget to be Muse-infused | TechCrunch</a></li>
<li><a href="https://www.engadget.com/2276312/meta-muse-gadgets-open-source-smart-home-link/">Meta Wants People To Build Their Own Muse Gadgets, Too</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的评论呈现两极分化：一部分人欢迎这一举动，认为这更像是某个内部团队对自家产品的热情，而不是重大的公司级战略动作；也有人认为 Meta 的一贯打法是靠承担其他公司不愿承担的风险来取胜。最主要的反对声音则是对生态的抵触——有人表示“要不是 Meta 做的，我肯定第一时间上手”，认为技术本身确实很酷，但用户最终会被“套牢”，还有人明确拒绝把 Meta 生态引入自己家中。

**标签**: `#Meta`, `#AI Agents`, `#Hardware Hacking`, `#Embedded/IoT`, `#Privacy`

---

<a id="item-5"></a>
## [AI 研究者 Thore Graepel 认为大语言模型并不真正具备推理能力](https://www.technologyreview.com/2026/10/02/1145639/dont-be-fooled-llms-dont-reason/) ⭐️ 7.0/10

在《麻省理工科技评论》发表的一篇新文章中，曾参与打造 AlphaGo 的 AI 研究者 Thore Graepel 提出，大语言模型并不具备真正的推理能力，并以 AlphaGo 在 2016 年首尔对局中的著名“第 37 手”作为对照。他回忆当时 AlphaGo 把棋子下在第五线上，这一手罕见得让解说员一度以为它下错了，而他把这一刻视为真正的机器推理应当达到的标准。 这篇文章正处在当前一场激烈争论的中心：语言模型的规模扩张究竟带来了真正的推理能力，还是只是更高级的模式匹配？这个问题直接影响企业、监管机构与研究者对 LLM 系统的信任程度。由于作者拥有深度强化学习的资历，他的观点对业界越来越普遍地将 LLM 描述为“推理引擎”的营销话术与基准测试结论构成了有力反驳。 该文属于观点评论而非技术论文，其论证依赖类比而非新的实验证据：AlphaGo 在一个规则明确、边界狭窄的棋类环境中，把搜索与学习到的价值网络、策略网络结合起来；而 LLM 则是在没有明确定义状态空间和显式搜索的情况下生成流畅文本。值得注意的是，Graepel 本人也指出第 37 手看上去像是失误，而这正是关键所在——它的价值只有通过棋局结果才得以显现。

rss · MIT Technology Review AI · 10月2日 08:00

**背景**: AlphaGo 是 DeepMind 开发的围棋系统，2016 年 3 月在首尔以 4 比 1 击败世界冠军李世石，成为里程碑事件，因为围棋巨大的分支因子长期令暴力搜索方法失效。第二局的第 37 手是在第五线上的“肩冲”，职业棋手认为极为罕见，李世石据称因惊讶而离开座位，这一手如今常被引为 AI 产生超越人类直觉的策略的范例。相比之下，大语言模型是在海量文本上训练来预测下一个 token，并越来越多地以思维链等推理基准来评估，这正是关于“真正推理”的争论焦点所在。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/AlphaGo_versus_Lee_Sedol">AlphaGo versus Lee Sedol - Wikipedia</a></li>
<li><a href="https://www.movethirtyseven.net/about">About — MOVE 37</a></li>

</ul>
</details>

**标签**: `#LLM reasoning`, `#AI criticism`, `#AlphaGo`, `#machine intelligence`, `#opinion`

---

<a id="item-6"></a>
## [NeurIPS 2026 论文聚焦动力系统重构中的拓扑域外泛化](https://www.reddit.com/r/MachineLearning/comments/1wvwodf/topological_outofdomain_generalization_in/) ⭐️ 7.0/10

一篇面向 NeurIPS 2026 的论文预印本《Topological Out-of-Domain Generalization in Dynamical Systems Reconstruction》（arXiv:2606.22969）从数学上指出了此前分层动力系统重构（DSR）模型的关键失效模式，这些缺陷使其无法正确学习系统的控制参数、更无法将参数外推到训练域之外。作者通过特征拆分（feature-splitting）和物理稀疏性先验修复了这些问题，改进后的分层模型在训练时完全不提供控制参数信息的情况下，仍能正确预测分岔点及分岔后的动力学行为，并在浅层 PLRNN 与 Neural ODE 上完成验证。 当前最先进的时间序列预测与 DSR 模型能够应对新的初始条件或统计特性变化，但一旦动力学机制本身发生质性改变便无能为力——而气候临界点、癫痫发作以及脓毒症等场景恰恰属于这类情况。让模型能够跨越这种机制变化进行外推，将使预测能力更接近人们对科学理论所期待的水平，并可能对气候科学、神经科学和临床早期预警系统产生实际影响。 作者强调该方法是通用的，同时适用于离散时间与连续时间的循环网络（实测对象为浅层 PLRNN 和 Neural ODE）；其核心难点在于，驱动系统跨越分岔的慢变控制参数通常并不精确已知，因此模型必须从数据中联合推断生成动力学与控制参数。该工作以拓扑视角衡量可靠性，也就是说，关键在于保持潜在吸引子的定性结构，而不仅仅是压低预测误差。

reddit · r/MachineLearning · /u/DangerousFunny1371 · 10月2日 15:25

**背景**: 动力系统重构（DSR）旨在学习生成观测时间序列的底层方程或隐动力学，其目标不止于短期预测，而是刻画长期行为；Takens 延迟嵌入定理等经典理论表明，系统的定性性质可以从这类数据中恢复。分岔是指系统参数的微小平滑变化引发行为突然发生质性改变的现象（例如从周期振荡转入混沌），自庞加莱以来，分岔理论一直在研究这类转变。域外泛化（OODG）通常指模型在与训练分布不同的数据上仍表现良好；而拓扑域外泛化则要求更高——必须仅靠改变控制参数，就正确刻画一个全新质性动力学机制下的系统行为。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2606.22969">[2606.22969] Topological Out - of - Domain Generalization in...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Bifurcation_%28dynamical_systems%29">Bifurcation (dynamical systems)</a></li>
<li><a href="https://en.wikipedia.org/wiki/Takens&#x27;s_theorem">Takens&#x27;s theorem - Wikipedia</a></li>

</ul>
</details>

**标签**: `#Dynamical Systems`, `#Out-of-Domain Generalization`, `#Topological Data Analysis`, `#Time Series Forecasting`, `#Machine Learning Research`

---