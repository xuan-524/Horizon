---
layout: default
title: "Horizon Summary: 2026-10-16 (ZH)"
date: 2026-10-16
lang: zh
---

> 从 64 条内容中筛选出 11 条重要资讯。

---

1. [Meta 发布 Muse Spark Open：面向本地部署的 816B 开放权重模型](#item-1) ⭐️ 8.0/10
2. [Citizen Lab 揭露 AdFection：定向广告沦为“零点击”间谍软件的投放管道](#item-2) ⭐️ 8.0/10
3. [Libreboot 26.10“Ominous Olive”发布，新增 UEFI/EDK2 与 233 款 Chromebook 支持](#item-3) ⭐️ 8.0/10
4. [GNOME 开发者探讨用 AI 逆向工程硬件](#item-4) ⭐️ 8.0/10
5. [谷歌量子 AI 在 Willow 芯片上突破关键资源瓶颈](#item-5) ⭐️ 8.0/10
6. [HuggingFace Transformers v5.20.0 新增 Muse Spark Open 与 Ling 3.0 支持](#item-6) ⭐️ 7.0/10
7. [Google DeepMind 用 Antigravity 智能体加速抗菌肽发现](#item-7) ⭐️ 7.0/10
8. [IBM Granite Switch 4.1：单一端点集成对话、决策与语音](#item-8) ⭐️ 7.0/10
9. [Simon Willison 的 Chirp Pong 用音频啁啾在手机间传输游戏状态](#item-9) ⭐️ 7.0/10
10. [Anthropic 向投资者披露第三季度营收达 168 亿美元，IPO 在即](#item-10) ⭐️ 7.0/10
11. [MIT 报道的 PNAS 论文：随机连接的类神经元单元可自组织出学习回路](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Meta 发布 Muse Spark Open：面向本地部署的 816B 开放权重模型](https://research.meta.ai/blog/muse-spark-open) ⭐️ 8.0/10

Meta 发布了 Muse Spark Open，这是一个 816B 参数的混合专家（MoE）模型，其 Hugging Face 仓库名 Muse-Spark-Open-816B-A42B 表明每次推理大约激活 42B 参数；模型权重已开放下载，并附带了本地部署指南。9to5Mac 在 2026 年 10 月 15 日的报道指出，该模型专门针对 Mac Studio 等硬件做了运行优化，Meta 还发布了文档，说明其已在多种推理框架上获得支持。 这次发布使 Meta 在与 Qwen、GLM 等中国实验室的开放权重竞赛中继续保持存在感，而此时可下载的前沿级模型正成为那些不愿或无法支付 API 费用的团队的首选。由于权重可以在工作站上本地运行，它把一部分先进 AI 能力从托管 API 转移到拥有合适硬件的企业、研究者和爱好者手中。 该模型采用的是开放权重而非真正意义上的开源许可：有评论者指出其中含有一条限制条款，若被许可方及其关联公司的总营收超过 2000 万美元，则不得将模型以“模型即服务”（Model as a Service）的形式对外提供，这限制了商业化的 API 转售。讨论中引用的第三方对比（Artificial Analysis）显示其成绩低于 Qwen3.8 Flash Next 和 GLM 5.3 Flash——据称后两者可单卡 B300 运行；而且该对比只在最高推理档位提供，许多生产用户认为这在实际场景中并不实用。

hackernews · bigwheels · 10月15日 17:47 · [社区讨论](https://news.ycombinator.com/item?id=50107379)

**背景**: 开放权重模型会公开训练好的神经网络参数，任何人都可以下载、微调并自行部署，这与同时公开训练代码和数据的“开源模型”不同；这一区别很关键，因为许可协议仍可能限制商业用途。Muse Spark Open 是一个混合专家（MoE）模型，这类架构虽然存储了极其庞大的总参数量，但每个 token 只经过其中一小部分专家，因此真正决定推理成本和显存压力的是“激活参数”数量（此处约为 42B），而不是 816B 这个标题数字。正是总参数与激活参数之间的差距，使这种规模的模型有可能运行在高端消费级或工作站硬件上，而不必依赖数据中心集群。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tokenclimate.com/en/course/active-parameters-mixture-of-experts">Active Parameters and Mixture-of-Experts - TokenClimate</a></li>
<li><a href="https://benchlm.ai/best/open-source">Open - Source LLM Leaderboard 2026: 95 Models Ranked | BenchLM.ai</a></li>
<li><a href="https://www.mindstudio.ai/blog/mixture-of-experts-architecture-glm-5-2-active-parameters">Mixture of Experts Architecture Explained: How GLM 5.2 Runs ...</a></li>

</ul>
</details>

**社区讨论**: 评论区观点分化：一些人认为由于那条 2000 万美元营收门槛的“模型即服务”条款，该模型算不上真正开放权重；另一些人则称赞 Meta 的工程投入，使其几乎支持从 Unsloth 到 MLX 的所有推理运行器，并指出这种生态黏性本身就是平台护城河。持怀疑态度的评论者认为 Meta 现在只是在追赶而非领先，理由是 Qwen3.8 Flash Next 和 GLM 5.3 Flash 表现更好，也有人抱怨公开的对比只覆盖最高、实际难以使用的推理档位。还有一条更宏观的战略讨论认为，智能已经商品化，决定选择的是价格而非能力，因此开放权重才是理性之举。

**标签**: `#AI`, `#open-weight models`, `#Meta`, `#LLM licensing`, `#benchmarks`

---

<a id="item-2"></a>
## [Citizen Lab 揭露 AdFection：定向广告沦为“零点击”间谍软件的投放管道](https://citizenlab.ca/research/how-discover-tech-turned-targeted-ads-into-a-pipeline-for-spyware/) ⭐️ 8.0/10

Citizen Lab 发布了一项名为“AdFection”的攻击活动研究报告，指出一家在以色列注册的广告公司 Discover Tech 涉嫌滥用定向广告基础设施，在用户毫无交互的情况下向其设备投放雇佣兵式间谍软件。据称该活动波及逾 7 万个应用和 12 万个网站，《卫报》和 The Verge 均转载了这一发现。 这一事件表明，几乎覆盖所有移动应用和网站、监管相对宽松的广告网络层，可能被改造成大规模监控的投放渠道，从而打破“仅展示广告无害”的假设。它把问责焦点推向广告中间商和 SDK 供应商，并向默认集成第三方广告代码的平台提出了严峻问题。 报告详细描述了投放与命令控制（C&amp;C）基础设施，但对真正实现“零点击”激活的漏洞利用链描述较为模糊；Discover Tech 被描述为一家广告公司，其服务器与某间谍软件厂商存在关联。Citizen Lab 将此次行动归因于商业雇佣兵间谍软件生态，而非指明某个政府客户。

hackernews · jcomp · 10月15日 10:43 · [社区讨论](https://news.ycombinator.com/item?id=50101813)

**背景**: Citizen Lab 是多伦多大学蒙克全球事务与公共政策学院下设的跨学科研究实验室，成立于 2001 年，长期研究信息管控问题，并多次揭露针对记者、活动人士和政客的间谍软件。所谓“零点击”间谍软件，是指完全无需用户任何操作即可感染设备的恶意程序，通常利用消息、浏览器或媒体解析代码中的内存破坏漏洞。而广告技术（AdTech）生态是一条由广告交易平台、供给方与需求方平台以及中介 SDK 组成的密集链条，这使得责任很难归咎于某个单一的“广告提供商”。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.wired.com/story/nightmare-scenario-zero-click-spyware-is-infecting-phones-via-targeted-ads/">‘Nightmare Scenario’: Zero-Click Spyware Is ... - WIRED</a></li>
<li><a href="https://tech-insider.org/adfection-spyware-ad-networks-2026/">AdFection Spyware Hit 70,000 Apps via Ads [2026]</a></li>

</ul>
</details>

**社区讨论**: 评论区观点明显分化：一位自称有 13 年从业经验的广告技术人员认为“零点击”的说法有哗众取宠之嫌，并指出在高度碎片化的供应链中并不存在单一的“广告提供商”；另一些人则讨论以色列为何能成为网络强国，以及以色列安全厂商能否被信任、独立于国家行事。还有用户提醒大家应阅读 Citizen Lab 的原始报告，而非只看新闻报道。

**标签**: `#security`, `#spyware`, `#adtech`, `#privacy`, `#nation-state-actors`

---

<a id="item-3"></a>
## [Libreboot 26.10“Ominous Olive”发布，新增 UEFI/EDK2 与 233 款 Chromebook 支持](https://libreboot.org/news/libreboot2610.html) ⭐️ 8.0/10

代号“Ominous Olive”的 Libreboot 26.10 正式发布，新增了 UEFI/EDK2 支持，并从 MrChromebox 的 coreboot 发行版中导入了目前全部 233 款受支持的 Chromebook。此次发布大幅扩充了 Libreboot 支持的设备列表，并旨在让未来的主板移植工作显著简化。 对自由固件社区而言这是一次质的飞跃：一个长期只支持少量老旧 ThinkPad 的项目，如今设备支持数量成倍增长，而 UEFI/EDK2 的整合也降低了新增机型的工程成本。这同时也壮大了 coreboot 周边的共享上游生态——由 MrChromebox 率先完成的 Chromebook 移植，如今可以回流到 Libreboot 以及 Heads 等其他发行版中。 本版本中的 Chromebook 支持仅提供源码，用户必须自行编译固件，官方未提供任何二进制文件；基于 Baytrail 的 ChromeOS 设备（“Kip”主板）已通过测试，其余型号仍待验证。此次发布还附带了一项针对大语言模型辅助贡献的严格政策，其依据是 Libreboot 源码仓库中公开的 AGENTS 文件。

hackernews · iamnothere · 10月15日 12:52 · [社区讨论](https://news.ycombinator.com/item?id=50102923)

**背景**: Libreboot 是一个基于 coreboot 的自由开源固件项目，目标是在受支持的 x86-64 与 AArch64 机器上替换专有的 BIOS/UEFI 固件；它相当于 coreboot 的一个发行版，就像 Debian 之于 Linux。EDK II（EFI Development Kit II）是 TianoCore 项目对 UEFI 的开源参考实现，因此整合它等于为 Libreboot 提供了符合标准的 UEFI 固件栈。MrChromebox.tech 为 ChromeOS 设备提供定制的、基于 coreboot 的固件，本次导入的 Chromebook 移植正是源自该项目已有的成果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Libreboot">Libreboot - Wikipedia</a></li>
<li><a href="https://mrchromebox.tech/">MrChromebox .tech</a></li>
<li><a href="https://tuxownia.pl/en/blog/hello-world-with-edk-ii-first-steps-with-uefi/">Hello World with EDK II - First Steps with UEFI - Tuxownia</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍认为 UEFI/EDK2 整合与 Chromebook 导入才是真正的重点，有人称其“意义重大”，因为它成倍增加了可用设备并简化了未来的移植。一位 Heads 项目的贡献者表示，基于 MrChromebox 代码的首个 ChromeOS 移植 PR 已被合并，另有两个移植正在进行；其他人则围绕严格的反 LLM 贡献政策展开讨论（总体持欢迎态度），也有用户指出 Chromebook 支持目前仅为源码形式。

**标签**: `#coreboot`, `#open-source-firmware`, `#UEFI`, `#Chromebook`, `#AI-policy`

---

<a id="item-4"></a>
## [GNOME 开发者探讨用 AI 逆向工程硬件](https://blogs.gnome.org/uraeus/2026/10/15/aiandreverseengineerhardware/) ⭐️ 8.0/10

一位 GNOME 开发者在 GNOME 博客平台（2026 年 10 月 15 日）发表文章，分享了用 AI 逆向工程硬件的亲身经验，认为这一方法对日常设备而言已经具备实用价值。该文在 Hacker News 上引发了 107 条评论的讨论，其中充满了关于逆向消费电子产品的具体案例。 如果 AI 能显著降低理解未公开固件和协议的成本，它可能赋能业余爱好者、维修店和中小硬件厂商，但同时也会让发现封闭设备漏洞变得更容易。这也加剧了整个行业的焦虑——一位经营小型专业音频公司的评论者就表示，他担心 AI 会让竞争对手轻易复制或超越自己多年积累的专有 DSP 成果。 评论者们给出了非常具体的实践结果：逆向任何 USB 口不止用于充电的设备、为老旧的 Onn-x5 播放器编写自定义固件、导出并全面控制 Rodecaster 的状态，以及生成新驱动让老打印机兼容 macOS 27。需要注意的是，像手机这类高度锁定的设备仍然难得多；另有评论者指出 AI 工具的能力提升极快——2025 年底 Claude 写 GTK4 应用几乎没什么用，但到 9 月已经能写出质量不错的 GTK4 代码。

hackernews · ErenayDev · 10月15日 14:35 · [社区讨论](https://news.ycombinator.com/item?id=50104299)

**背景**: 硬件逆向工程指的是在没有官方文档或源代码的情况下，分析设备的固件、协议和行为，弄清它是如何工作的——这传统上是一项缓慢且高度专业化的技能。如今大语言模型可以通过识别二进制数据、反汇编代码和串口通信中的模式来提供帮助，从而降低了门槛。这对&quot;维修权&quot;运动和安全研究都很重要，因为未公开的固件往往既隐藏着可维修性限制，也藏着可被利用的漏洞。该文章发布在 blogs.gnome.org/uraeus，这是一位资深 GNOME 贡献者的个人博客。

**社区讨论**: 社区反应既有热情也有不安：一些评论者分享了自己的成功项目（MP3 播放器自定义固件、控制 Rodecaster、让老打印机复活），另一些人则把目光放得更远，呼吁用这项技术移除智能电视里的广告和&quot;住宅代理&quot;僵尸网络功能。最引人注目的声音来自一位小型专业音频公司老板，他说自己已经连续三天处于无声的恐慌之中，担心 AI 驱动的竞争会让自己公司的专有混响和延迟算法一文不值。

**标签**: `#AI`, `#reverse engineering`, `#hardware`, `#security`, `#right-to-repair`

---

<a id="item-5"></a>
## [谷歌量子 AI 在 Willow 芯片上突破关键资源瓶颈](https://news.google.com/rss/articles/CBMiYEFVX3lxTE9hWW80VEtHNHlmR0NXVEFrOUxkZEJwbTRIcUFMbGhnV2dXbks4a3ZWck1lMk1ZdExObWtvSTFzaHFSSlpEb09CZ1NldnFNRDN2UEU0dGw2a2g3MGRaRllTag?oc=5) ⭐️ 8.0/10

谷歌量子人工智能（Google Quantum AI）宣布一项量子计算重大进展：其团队在《Science》期刊发表论文，展示了一种名为&quot;魔法态培养&quot;（magic state cultivation）的技术，并在自家的 Willow 超导量子处理器上成功运行，破解了困扰该领域约 20 年的工程瓶颈——如何高效制备容错量子计算所需的关键量子态。东方财富将其报道为突破关键资源瓶颈的进展。 魔法态是实现非 Clifford 操作（例如 T 门）的前提，而这类操作正是量子计算机真正算力的来源；长期以来，制备魔法态所需的高昂资源开销一直是规模化扩展的主要障碍。降低这一开销使容错型大规模量子计算距离实用化明显更近一步，也可能影响未来量子硬件的设计思路与资源预算。 该成果建立在 Willow 之上——Willow 是谷歌于 2024 年 12 月发布的超导处理器，首次实现了低于阈值的表面码纠错；而此次新工作的重点在于资源效率而非单纯的量子比特数量，即降低每个魔法态所需的物理量子比特与操作数量。仍需注意几点局限：真正实用的容错量子计算机依旧需要比现有硬件多得多的高质量量子比特和更低的错误率；此外，谷歌此前基于随机线路采样宣称的&quot;量子优越性&quot;也曾受到部分专家的质疑。

google\_news · 东方财富 · 10月15日 18:29

**背景**: 量子纠错（QEC）是一类通过把多个物理量子比特编码为一个逻辑量子比特，从而保护脆弱量子信息免受退相干和其他噪声影响的技术，被普遍视为实用量子计算机的基础。Willow 是谷歌量子人工智能于 2024 年 12 月发布的超导量子芯片，其成果显示随着物理量子比特数量增加，错误率可以呈指数级下降。除了纠错之外，容错量子计算机还需要&quot;魔法态&quot;才能执行非 Clifford 门；而如何以足够低的成本制备这些状态一直是长期存在的资源瓶颈，&quot;魔法态培养&quot;正是为更高效地生成魔法态而提出的技术路线。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/quantum-computing/magic-state-cultivation-quantum-computing/">Bringing the magic: Google breaks open a bottleneck in ...</a></li>
<li><a href="https://www.businesstoday.in/technology/story/20-year-old-bottleneck-solved-what-google-quantum-ais-latest-scientific-breakthrough-means-561934-2026-10-16">20-year-old bottleneck solved: What Google Quantum AI&#x27;s ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Willow_processor">Willow processor - Wikipedia</a></li>

</ul>
</details>

**标签**: `#quantum-computing`, `#google-quantum-ai`, `#error-correction`, `#willow-chip`, `#hardware`

---

<a id="item-6"></a>
## [HuggingFace Transformers v5.20.0 新增 Muse Spark Open 与 Ling 3.0 支持](https://github.com/huggingface/transformers/releases/tag/v5.20.0) ⭐️ 7.0/10

HuggingFace Transformers v5.20.0 正式原生支持一批新模型，其中最引人注目的是 Meta 的 Muse Spark Open——一个 816B 参数的多模态混合专家（MoE）模型，每 token 激活 42B 参数，文本、图像、音频和视频共享最长 1,048,576 token 的上下文窗口——以及 InclusionAI 的 Ling 3.0 Flash。本次发布还集成了 Aleph Alpha 的 Kolibri 1、OpenBMB 的 MiniCPM-V 4.7、百度的 3B 参数 UnlimitedOcr 以及 UltraBERT 系列。 由于这些架构是直接合入主线库、而非依赖社区的 remote code，开发者现在可以用标准 Transformers API 和稳定接口直接加载前沿规模的多模态与 MoE 权重，显著减少了评估和部署时的集成工作量。816B 参数 MoE 模型与 NVFP4 量化权重的加入，也说明超大参数、多模态模型正日益成为该生态中的一等公民。 Muse Spark Open 针对多文件编辑、调试和工具调用等 agentic 编码任务训练，权重同时提供 BF16 和 NVFP4 两种格式；Ling 3.0 Flash 以 \`BailingHybridForCausalLM\` 原生加载，无需再设置 \`trust\_remote\_code=True\`，其解码器将五个 Kimi Delta Attention 层与一个 Multi-head Latent Attention 层组合。UnlimitedOcr 用 Reference Sliding Window Attention 替换全部解码器注意力层，使解码过程中 KV 缓存保持恒定；MiniCPM-V 4.7 则引入 &quot;canvas M-RoPE&quot;，把每个视觉 token 放到二维画布上并赋予 \(temporal, height, width\) 位置。

github · vasqu · 10月15日 18:05

**背景**: HuggingFace Transformers 是加载和运行预训练模型事实上的标准 Python 库，因此新架构一旦合入上游即可直接使用，无需自己写代码。混合专家（MoE）模型把每层的前馈计算拆分为众多“专家”子网络，并只把每个 token 路由到其中少数几个，从而在总参数量极大的同时让每 token 激活的参数少得多——这正是本文中 816B/42B 结构的原理。NVFP4 是随 NVIDIA Blackwell GPU 架构引入的 4 位浮点格式，它以每 16 个 FP4 数值为一组共享一个 E4M3 缩放因子，从而降低量化误差。Agentic coding（智能体式编码）指的是不仅用 LLM 补全代码，而是让智能体自主完成编辑文件、运行测试、调试等多步骤开发任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.nvidia.com/blog/introducing-nvfp4-for-efficient-and-accurate-low-precision-inference/">Introducing NVFP4 for Efficient and Accurate Low-Precision ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Block_floating_point">Block floating point - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Agentic_coding">Agentic coding</a></li>

</ul>
</details>

**标签**: `#transformers`, `#huggingface`, `#multimodal`, `#mixture-of-experts`, `#model-release`

---

<a id="item-7"></a>
## [Google DeepMind 用 Antigravity 智能体加速抗菌肽发现](https://deepmind.google/blog/accelerating-antimicrobial-discovery/) ⭐️ 7.0/10

Google DeepMind 发布博客文章，介绍其如何利用 Google Antigravity——这一具备自主性的 AI 编程平台——来加速新型抗菌肽（antimicrobial peptides）的发现。文章把 Antigravity 定位为一款“面向科学研究”的工具，用能够编写、运行并测试代码的自主 AI 智能体来服务抗菌药物发现流程。 抗菌素耐药性是最紧迫的公共卫生威胁之一，而新型抗生素类别极度匮乏，因此任何能在多肽发现上带来可信提速的进展都可能具有临床意义。此事也反映出一种更广泛的趋势：厂商的智能体编程平台正被用于科学研究流程，而不再局限于普通软件工程。 这篇博文本身非常简短，没有提供任何技术细节——没有除 Antigravity 之外的模型名称、没有肽数据集、没有候选分子，也没有实验验证结果。Google Antigravity 于 2025 年 11 月 18 日与 Gemini 3 一同发布，使用 Google 的 Gemini 模型并支持 Anthropic 和 OpenAI 的第三方模型，并在 2026 年 5 月新增了独立桌面应用、命令行工具（CLI）和 SDK。

rss · Google DeepMind · 10月15日 16:08

**背景**: 抗菌肽（AMPs），又称宿主防御肽，是长度通常为 10 至 50 个氨基酸的短多肽，属于各类生物先天免疫应答的一部分。它们能够杀死革兰氏阴性菌、革兰氏阳性菌、包膜病毒和真菌，其作用方式往往是通过破坏微生物细胞膜，而非采用传统抗生素的机制，因此被视为颇具吸引力的新型治疗类别。相比之下，Google Antigravity 是一款由 AI 驱动的集成开发环境（IDE），其中的 AI 智能体可在不同程度的自主性下编写、运行并测试代码，DeepMind 正是把这种智能体能力用于抗菌肽的搜索问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Google_Antigravity">Google Antigravity</a></li>
<li><a href="https://en.wikipedia.org/wiki/Antimicrobial_peptides">Antimicrobial peptides</a></li>
<li><a href="https://antigravity.google/">Google Antigravity</a></li>

</ul>
</details>

**标签**: `#AI for Science`, `#Drug Discovery`, `#Antimicrobial Peptides`, `#Google DeepMind`, `#Machine Learning`

---

<a id="item-8"></a>
## [IBM Granite Switch 4.1：单一端点集成对话、决策与语音](https://huggingface.co/blog/ibm-granite/granite-switch-4-1) ⭐️ 7.0/10

IBM 于 2026 年 10 月 15 日发布 Granite Switch 4.1，推出 8B 与 30B 两种参数规模的模块化模型，将 Granite 4.1 基础模型与通用决策适配器、安全适配器以及语音编码器组合在一起，并通过单一托管端点对外服务。据 IBM 介绍，同一套部署即可在自然语言对话、通用及专用决策、安全审查和语音转文本任务之间切换，无需再调用多个独立模型。 通过把对话、决策与语音转文本收敛到同一个端点，Granite Switch 4.1 有望让企业团队用一套托管服务替代多个模型部署，从而降低集成、推理服务和运维成本。这也表明 IBM 正试图通过瞄准实际业务负载，而非单纯比拼通用基准成绩，来让采用 Apache 2.0 开源许可的 Granite 系列与通用大模型形成差异化。 IBM 表示，所集成的 ASR 组件是 OpenASR 排行榜上速度最快的模型，而其基于稠密架构的 Granite 4.1 基础模型在工具调用、指令遵循、代码编写和数学推理方面相较 Granite 4.0 均有提升。由于这些能力以可替换适配器而非独立模型的形式提供，该设计在部署简便性上有所得，但在部分专项性能上可能有所取舍；4.1 的版本号也说明这是一次增量式改进，而非全新架构。

rss · Hugging Face Blog · 10月15日 20:34

**背景**: IBM Granite 是 IBM 于 2023 年 9 月 7 日发布的一系列 decoder-only 人工智能基础模型，定位为面向企业的开放模型，以 Apache 2.0 许可证发布，覆盖语言、视觉、语音和护栏等任务。在这里，“适配器”（adapter）指的是附加在共享基础模型之上的一小组额外权重，使模型无需重新训练整个网络即可完成特定专项任务；而 ASR（自动语音识别）指的就是语音转文本任务。OpenASR 排行榜是一个公开榜单，用于从准确率和速度两方面比较语音识别模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/ibm-granite/granite-switch-4-1">Granite Switch 4.1: Chat, Decisions, and Speech from One Endpoint</a></li>
<li><a href="https://www.unite.ai/ibm-releases-modular-granite-switch-4-1-models-in-8b-and-30b-sizes/">IBM Releases Modular Granite Switch 4.1 Models in 8B and 30B ...</a></li>
<li><a href="https://www.ibm.com/granite/docs/models/granite4-1">Granite 4.1 | IBM Granite</a></li>

</ul>
</details>

**标签**: `#AI`, `#LLM`, `#IBM Granite`, `#Speech`, `#Model Release`

---

<a id="item-9"></a>
## [Simon Willison 的 Chirp Pong 用音频啁啾在手机间传输游戏状态](https://simonwillison.net/2026/Oct/15/chirp-pong/) ⭐️ 7.0/10

Simon Willison 发布了 Chirp Pong：一款基于浏览器的双人 Pong 类游戏，以静态 HTML 形式在两台彼此靠近的手机上运行，所有游戏状态都通过扬声器发出的音频噪声传输，并由对方麦克风接收，完全不用 Wi-Fi、蓝牙或服务器。他用 Claude Code 中的 Claude Opus 5.5 生成代码，提示词要求做出带图形与玩法创新的竞技型 Pong 游戏，并表示这种基于啁啾的联网方式“看起来可行”。 这个实验说明，手机之间的本地多人游戏完全可以不依赖网络协议栈、配对握手或后端服务，只靠扬声器、麦克风和 Web API 就能跑起来，为离线、临时、注重隐私的设备间交互提供了有趣的替代方案。同时，它也是一个简洁的例证：像 Claude Code 这样的智能体式编程工具，能让单个开发者在一次会话内就做出一个古怪却完整的原型。 声学数据传输的带宽天然很低——标准 Chirp 式可听与超声协议的速率分别约为 100 bps 和 200 bps——因此游戏每次啁啾只能编码极少量的状态，并依赖 Web Audio API 的 getUserMedia 麦克风采集来解码。由于页面是没有任何服务端组件的静态 HTML，两台设备必须靠得足够近，让麦克风能听清扬声器，而环境噪声或回声都可能削弱这条链路。

rss · Simon Willison · 10月15日 19:47

**背景**: Chirp 式的声学数据传输把数字信息编码成可听或超声的音调，供附近的麦克风解码，因此它更适合物联网配对这类短距离、低功耗场景，而不是高带宽链路。在浏览器中，Web Audio API（通过 getUserMedia）让 JavaScript 能够采集原始麦克风音频，并在时域和频域上进行分析，这正是 Chirp Pong 读取传入游戏数据的机制。Claude Code 是 Anthropic 的智能体式编程工具，能够读懂代码库、编写与修改文件并从终端执行命令，Simon Willison 正是用它配合 Claude Opus 5.5 模型生成了这个项目。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.techzine.eu/news/applications/129433/chirp-tool-sends-data-between-devices-with-different-audio-tones/">Chirp tool sends data between devices with different audio tones</a></li>
<li><a href="https://discovery.ucl.ac.uk/id/eprint/10090651/1/Mehrabi2019_Article_EvaluatingTheUserExperienceOfA.pdf">Evaluating the user experience of acoustic data transmission</a></li>
<li><a href="https://code.claude.com/">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>

</ul>
</details>

**标签**: `#game-design`, `#generative-ai`, `#web-audio`, `#networking`, `#experimental`

---

<a id="item-10"></a>
## [Anthropic 向投资者披露第三季度营收达 168 亿美元，IPO 在即](https://simonwillison.net/2026/Oct/15/anthropic-tells-investors/) ⭐️ 7.0/10

Anthropic 周三向投资者披露，其第三季度（7 月至 9 月）营收达到 168 亿美元，较第二季度的 115 亿美元增长近 50%，约为第一季度“约 48 亿美元”的 3.5 倍，公司正在为计划中的 IPO 做准备。公司同时表示，每支出 1 美元算力可获得 1.70 美元收入，剔除股权激励后的调整后营业利润率为 11%，并已在第三季度“大幅”削减来自竞争对手蒸馏其模型所带来的收入。 这些数字表明 Anthropic 的营收增速在企业软件行业极为罕见——单季 168 亿美元意味着年化约 670 亿美元——这使其计划中的 IPO 成为检验前沿 AI 实验室能否把巨额算力投入转化为可持续业务的最受关注案例之一。而披露竞争对手曾向 Anthropic 支付数亿美元来训练自家模型，也凸显出 AI 实验室之间的竞争既高度相互依赖，又充满法律与合规争议。 蒸馏（即竞争对手用更先进模型的输出来训练自家模型）曾占 Anthropic 收入的 5%至 7%，后在第三季度被削减；按 Simon Willison 的粗略估算，这意味着未具名的其他实验室仅第二季度就花费了超过 5 亿美元来蒸馏 Anthropic 的模型。值得注意的是，Anthropic 似乎已不再在投资者沟通中使用“年化运行率收入”这一口径，转而直接公布季度营收数字。

rss · Simon Willison · 10月15日 13:04

**背景**: Anthropic 是 Claude 系列模型背后的 AI 实验室，主要通过 API 和订阅服务对外销售模型能力。公司正在筹备 IPO（首次公开募股），即把股票放到公开交易所上市，在此之前必须让私募投资者相信其增长速度和单位经济模型。机器学习中的“蒸馏”通常指把大型“教师”模型的知识迁移到较小的“学生”模型，是一种正当的模型压缩技术；而此处的用法更具争议，指竞争对手用前沿实验室的模型输出训练自家模型，这通常违反服务条款，并可通过异常的 API 高频调用被识别。每美元算力收入、调整后营业利润率等指标，是算力密集型企业向投资者展示 GPU 投入转化为利润效率的方式。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Knowledge_distillation">Knowledge distillation</a></li>
<li><a href="https://www.ibm.com/think/topics/knowledge-distillation">What is knowledge distillation? - IBM</a></li>

</ul>
</details>

**标签**: `#anthropic`, `#ai-industry`, `#ipo`, `#business`, `#llm`

---

<a id="item-11"></a>
## [MIT 报道的 PNAS 论文：随机连接的类神经元单元可自组织出学习回路](https://www.reddit.com/r/MachineLearning/comments/1x6hmyg/how_artificial_neural_networks_build_their_own/) ⭐️ 7.0/10

2026 年 10 月 9 日发表于 PNAS 的论文《How Biological Synapses Self-Assemble Gradient Learning》报告称，由共享的局部可塑性规则支配、且随机互联的类神经元单元能够自发组装出“学习基元（learning motifs）”，并据此完成模式识别与图像分类任务。据 MIT 于 2026 年 10 月 13 日的报道，其表现与用于对比的反向传播训练网络相当。 这一结果重新定义了“学习机制从何而来”的问题：与其直接设计学习电路，不如只规定局部规则，让学习机制自行组织形成。这与类脑可塑性学习研究直接相关，也呼应了长期以来寻找反向传播替代或补充方案的探索，因为局部可塑性规则更接近真实突触的工作方式。 作者明确提醒，自组织现象并不能证明大脑确实采用该机制；该工作的动机在于生物合理性，而非为大规模模型提供反向传播的即插即用替代方案。评估该结果时值得关注的两个开放问题是：学习到的基元在不同初始连接条件下是否稳定，以及该方法能否扩展到论文所展示的模式识别与图像分类任务之外。

reddit · r/MachineLearning · /u/Dorian182 · 10月15日 10:01

**背景**: 标准深度学习使用反向传播训练网络，它把误差信号反向传遍整个网络，由于真实突触只能获取局部信息，因此常被认为缺乏生物合理性。相比之下，局部可塑性规则让每个连接只依据该突触可获取的信号进行更新，这与 Hebbian 式思路一脉相承；而 Kohonen 自组织映射等自组织网络则表明，有用的结构可以从竞争性的局部动力学中涌现，而不必依赖误差修正。这篇论文正处在两条研究脉络的交汇处，追问仅靠局部规则能否自发形成具备类梯度学习能力的学习回路。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2010.08262">[2010.08262] Local plasticity rules can learn deep ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Self-organizing_map">Self-organizing map - Wikipedia</a></li>
<li><a href="https://www.geeksforgeeks.org/machine-learning/ann-self-organizing-neural-network-sonn/">ANN - Self Organizing Neural Network (SONN) - GeeksforGeeks</a></li>

</ul>
</details>

**标签**: `#neural-networks`, `#self-organization`, `#plasticity`, `#backpropagation`, `#computational-neuroscience`

---