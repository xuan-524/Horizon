---
layout: default
title: "Horizon Summary: 2026-08-25 (ZH)"
date: 2026-08-25
lang: zh
---

> 从 58 条内容中筛选出 13 条重要资讯。

---

1. [seL4 在 AArch64 上的安全证明现已完成](#item-1) ⭐️ 9.0/10
2. [MS Paint 和 Photos 在本地 AI 图片中嵌入隐形 GUID 水印](#item-2) ⭐️ 8.0/10
3. [浏览器工具让你像玩电子游戏一样探索整个旧金山](#item-3) ⭐️ 8.0/10
4. [AI 依赖可能导致开发者编码专业能力崩溃](#item-4) ⭐️ 8.0/10
5. [将 AI 生成的 3D 物体视为可编程空间软件](#item-5) ⭐️ 8.0/10
6. [OpenAI 在 Kiro 发布 GPT-5.6，提升开发者性价比](#item-6) ⭐️ 7.0/10
7. [SELF 格式让 SQLite 数据库在 Linux 上可执行](#item-7) ⭐️ 7.0/10
8. [课堂中更智能使用聊天机器人的指南](#item-8) ⭐️ 7.0/10
9. [儿童仍比 AI 更会学习语言，原因依然成谜](#item-9) ⭐️ 7.0/10
10. [Unbounded Labs 发布 Bart：基于 1931 年前英语训练的复古大语言模型](#item-10) ⭐️ 7.0/10
11. [基于延迟校正 Bellman 算子与因果归因的约束强化学习](#item-11) ⭐️ 7.0/10
12. [OpenAI 评欧盟《行为准则》与人工智能在欧洲的未来](#item-12) ⭐️ 7.0/10
13. [阿里发布 Wan3.0 视频大模型：30 秒 PPT 变视频](#item-13) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [seL4 在 AArch64 上的安全证明现已完成](https://proofcraft.systems/news-2026/#2026-08-21) ⭐️ 9.0/10

Proofcraft 宣布，seL4 的正式安全证明现已在 AArch64 架构上完成。这标志着这一经过验证的微内核的安全定理首次覆盖 64 位 ARM 指令集。 这是形式化验证领域的一个重要里程碑，因为 AArch64 驱动着绝大多数现代移动和嵌入式设备。这使得 seL4 成为这些平台上汽车、航空航天和国防领域高安全等级系统的更有力候选。 目前的证明仅限于非 MCS（混合关键性系统）和单核（unicore）配置，且未处理时序侧信道攻击。该验证是 seL4 在 AArch64 上安全不变量的机器检查的正式证明。

hackernews · snvzz · 8月24日 11:32 · [社区讨论](https://news.ycombinator.com/item?id=49418255)

**背景**: seL4 是一个微内核，拥有世界上首个经过正式验证的操作系统内核，即其正确性通过交互式定理证明以数学上的严谨性得到证明。形式化验证不是测试单个用例，而是针对所有可能行为证明功能正确性和安全不变量等属性。AArch64 是 ARM 架构的 64 位执行状态，广泛用于智能手机、服务器和嵌入式系统。完成该架构的安全证明，将 seL4 的已验证保证扩展到这一占主导地位的现代平台。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sel4.systems/">The seL 4 Microkernel | seL 4</a></li>
<li><a href="https://en.wikipedia.org/wiki/Formal_verification">Formal verification</a></li>
<li><a href="https://en.wikipedia.org/wiki/L4_microkernel_family">L 4 microkernel family - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论区总体上认可这一里程碑，但强调了重要的注意事项：时序侧信道攻击仍可能使安全结果失效，且该证明仅限于非 MCS 单核配置。还有人讨论了 seL4 的实际采用情况，提到了 GenodeOS、LionsOS 以及某中国车企的虚拟机监控程序；另一位评论者则认为，seL4 需要原生 Linux 环境，才能诚实地宣称它比现代安全启动虚拟化平台更能改善系统安全性。

**标签**: `#formal verification`, `#seL4`, `#microkernel`, `#security`, `#AArch64`

---

<a id="item-2"></a>
## [MS Paint 和 Photos 在本地 AI 图片中嵌入隐形 GUID 水印](https://xusheng.dev/posts/reversing/mspaint_invisible_watermark/main/) ⭐️ 8.0/10

xusheng.dev 上的一篇逆向工程分析揭示，微软画图（MS Paint）和照片（Photos）应用会在图片中静默嵌入不可见的 GUID 水印，即使 AI 图像操作完全在本地设备上完成也不例外。该水印无法禁用，且会在用户不知情的情况下添加。 这一发现意义重大，因为它削弱了用户的匿名性和隐私：在这些应用中创建或编辑的图片可能通过 GUID 关联回 Microsoft 账户，从而被用于版权传票或个人数据请求。它还引发了关于企业监控和互联网匿名性侵蚀的更广泛担忧。 与可关闭的可见水印不同，这个不可见的 GUID 水印会在后台静默添加且无法禁用。目前尚不清楚背景移除等基础 AI 功能是否也会触发水印，有用户报告出现过误触发的情况；另有评论者指出，微软此前曾错误地为所有 Azure DevOps 提交打上 Copilot 水印，说明其实现可能并不严谨。

hackernews · ComputerGuru · 8月24日 15:28 · [社区讨论](https://news.ycombinator.com/item?id=49421158)

**背景**: 数字水印技术将不可感知的信号嵌入数字资产中，以便之后恢复其来源。隐形水印广泛用于版权保护和 AI 内容溯源，相关技术包括 C2PA 元数据和 Google 的 SynthID；GUID 本质上是一个唯一追踪码，可与用户或设备关联。欧盟《人工智能法案》以及 Meta 等平台正在推动 AI 生成内容加水印，但在本地生成的图片上静默添加此类标记则引发知情同意和隐私问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://theairankings.com/guides/what-is-ai-watermarking/">What Is AI Watermarking? How Token Watermarks Actually Work</a></li>
<li><a href="https://www.educba.com/invisible-watermarking/">Invisible Watermarking | Uses, Benefits, and Real-World Examples</a></li>
<li><a href="https://engineering.fb.com/2025/11/04/video-engineering/video-invisible-watermarking-at-scale/">Video Invisible Watermarking at Scale - Engineering at Meta</a></li>

</ul>
</details>

**社区讨论**: 评论区普遍感到震惊和担忧：有人指出 AI 角度其实是转移视线，真正的问题在于悄悄加入的唯一标识——只要有人不喜欢你的梗图，就可能通过传票从微软获取你的姓名、地址、邮箱和电话。也有评论者以微软此前在 Azure DevOps 中误加 Copilot 水印为例，认为其实现粗糙，并建议避免使用画图等启用 LLM 的应用；还有用户报告出现过误触发水印的情况。

**标签**: `#privacy`, `#watermarking`, `#microsoft`, `#security`, `#AI`

---

<a id="item-3"></a>
## [浏览器工具让你像玩电子游戏一样探索整个旧金山](https://sf.thijs.gg/) ⭐️ 8.0/10

位于 sf.thijs.gg 的交互式 3D 可视化项目在浏览器中渲染了整座旧金山，让用户像玩电子游戏一样探索该城市。该项目利用真实地图数据构建出一个完全可导航的 3D 城市景观。 这件事表明基于浏览器的 3D 图形和开放地理空间标准已经发展到相当高的水平，任何人都无需专门软件即可访问城市级数据。它也能引起市民的情感共鸣，并可能为未来城市规划、游戏和数字孪生工具带来启发。 该页面被标记为 3D 渲染、Web 开发、地图可视化和程序化生成，暗示它使用了算法技术来生成城市。部分 Safari 用户报告该标签页会让浏览器卡死，而评论者则建议添加街道名称、地址传送，以及结合街景图像的本地高分辨率版本。

hackernews · centrosphere · 8月24日 17:05 · [社区讨论](https://news.ycombinator.com/item?id=49422784)

**背景**: 3D Tiles 是一个开放标准，用于流式传输和渲染大规模异构 3D 地理空间数据（如建筑物、摄影测量和点云），能在浏览器和游戏引擎中实现实时可视化。程序化生成是一种通过算法而非手动创建数据的方法，常用于游戏和模拟中生成地形、建筑和纹理。这些技术结合起来，使得在浏览器中重现像旧金山这样的整座城市成为可能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cesium.com/why-cesium/3d-tiles/">3D Tiles – Cesium</a></li>
<li><a href="https://www.ogc.org/standards/3dtiles/">3D Tiles Standard – Streaming Massive 3D Geospatial Data</a></li>
<li><a href="https://en.wikipedia.org/wiki/Procedural_generation">Procedural generation</a></li>

</ul>
</details>

**社区讨论**: 评论者大多非常热情，一位前旧金山居民表示，在熟悉的老街区里走动让他们感到激动。常见的建议包括显示街道名称和地标、按地址传送、提供带街景的本地高分辨率版本，甚至做成多人线上游戏。少数 Safari 用户报告该页面会导致浏览器卡死，需要变通方法才能关闭标签页。

**标签**: `#3D rendering`, `#web development`, `#map visualization`, `#procedural generation`, `#san francisco`

---

<a id="item-4"></a>
## [AI 依赖可能导致开发者编码专业能力崩溃](https://larsfaye.com/articles/ai-coding-will-prevent-expertise) ⭐️ 8.0/10

本文作者 Lars Faye 认为，过度依赖 AI 编码工具会阻碍开发者培养深厚的专业技能，可能导致编码专长走向崩溃。这篇文章在社区引发了大量讨论，获得 426 个点赞和 425 条评论。 这一话题之所以重要，是因为 AI 编程助手正被广泛采用，而争论的焦点在于它们是否会损害软件工程师的长期技能培养。如果该论点成立，行业未来可能缺乏能够理解、审查和调试复杂代码的工程师。 讨论中涵盖了多种观点，包括企业在内部强制推行 AI 编码、&\#x27;vibe coding&\#x27;（随意式 AI 编码）与&\#x27;guided coding&\#x27;（引导式 AI 编码）之间的对比，以及技能形成过程中需要适当摩擦的观点。还有评论者指出，开发者生成代码的速度可能超过人类理解和审查的速度，这会带来风险。

hackernews · larsfaye · 8月24日 15:52 · [社区讨论](https://news.ycombinator.com/item?id=49421554)

**背景**: 大语言模型（LLM）是基于海量文本训练的人工智能模型，能够生成、总结、翻译和分析内容，也是许多现代编程助手的基础。随着这些工具越来越深入地融入开发流程，它们可以从自然语言提示中生成整个函数甚至完整功能，这改变了编程的本质，也引发了关于开发者如何建立和维持专业技能的思考。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Large_language_model">Large language model</a></li>
<li><a href="https://www.ibm.com/think/topics/large-language-models">What Are Large Language Models (LLMs)? | IBM</a></li>

</ul>
</details>

**社区讨论**: 社区的态度总体上偏向担忧：有评论者报告称，企业强制要求使用 AI 生成代码，速度已超过人类能够审查的范围；还有人警告说，基于 LLM 的开发正在形成&\#x27;蛇咬自己尾巴&\#x27;的恶性循环。不过，也有评论者为 AI 工具辩护，认为&\#x27;引导式编码&\#x27;（guided coding）既能达到与&\#x27;vibe coding&\#x27;相当的效率，又能产出更高质量的代码，而且乐于寻求挑战的工程师仍然能找到学习和成长的空间。

**标签**: `#AI`, `#Software Engineering`, `#Expertise`, `#Coding`, `#LLM`

---

<a id="item-5"></a>
## [将 AI 生成的 3D 物体视为可编程空间软件](https://www.reddit.com/r/MachineLearning/comments/1vxcc1h/r_using_ai_as_a_spatial_software_generator_to/) ⭐️ 8.0/10

研究人员提出一种方法，利用 LLM 将 3D 物体生成过程转化为可编程空间软件，而非静态网格，从而获得开箱即用的动画就绪和层次化结构模型。交互式演示可在 nova3d.xyz 上查看。 这种转变可能让 AI 生成的 3D 资产对游戏开发、工业设计、模拟以及 AR/VR/XR 等行业更加实用。由于物体从诞生之初就是软件，它们能适应弱计算环境和强计算环境，并支持自然关节运动。 生成的物体在创作时就包含逻辑部件、铰链/插座关节和层次化结构，并能根据计算能力调整外观。不过，该方法目前在复杂有机形状方面仍落后于传统 AI 3D 生成器。

reddit · r/MachineLearning · /u/mhb\_11 · 8月24日 19:10

**背景**: 传统 AI 3D 生成器通常输出难以动画或编辑的整体网格块。空间编程则把 3D 内容表示为代码或构造几何，这正是许多 CAD 和工程工具的工作方式。Sketchfab 等平台已支持“可编程”标签，CAD 库也常用铰链关节来实现可动部件。这项研究将这种可编程、基于代码的理念应用于 LLM 驱动的 3D 生成。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.spatial.com/">Spatial | Leading 3D Software Solutions to Create Engineering Application</a></li>
<li><a href="https://sketchfab.com/tags/programmable">Programmable 3D models - Sketchfab</a></li>
<li><a href="https://grabcad.com/library/tag/hinge">hinge - Recent models | 3D CAD Model Collection - GrabCAD</a></li>

</ul>
</details>

**标签**: `#AI`, `#3D generation`, `#LLM`, `#spatial programming`, `#research`

---

<a id="item-6"></a>
## [OpenAI 在 Kiro 发布 GPT-5.6，提升开发者性价比](https://openai.com/index/gpt-5-6-in-kiro) ⭐️ 7.0/10

OpenAI 已在 Kiro（其智能体编码与软件开发平台）中推出 GPT-5.6。此次发布旨在让开发者在规划、构建、审查和测试软件时获得更优的性价比。 这很重要，因为 GPT-5.6 将重大 AI 模型更新直接带入开发者工作流工具，可能降低软件团队成本并提高生产力。这也表明 AI 编程平台和模型提供商在能力与价格上的竞争正在加剧。 根据 Artificial Analysis 的评估，GPT-5.6 Sol 在 Artificial Analysis 智能指数中名列前茅，成本约为领先竞品的三分之一，并在 OpenAI 的 Codex 环境中领跑编码智能体指数。官方公告本身没有提供基准测试细节，但 Kiro 基于 Amazon Bedrock 构建，采用规范驱动开发，在编写代码前先将提示词转化为可执行的规范。

rss · OpenAI News · 8月24日 12:00

**背景**: GPT-5.6 是 OpenAI GPT-5 系列的新模型版本，OpenAI 称该系列在数学、科学、金融、法律等领域提供专家级别的智能。Kiro 是基于 Amazon Bedrock 构建的智能体编码服务，强调规范驱动开发，在编写代码前先将想法转化为清晰的计划。此次发布将 GPT-5.6 集成到 Kiro 的规划、编码、审查和测试工作流中，反映出将前沿模型部署到端到端开发者工具中的更广泛趋势。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://artificialanalysis.ai/articles/gpt-5-6-has-landed">GPT - 5 . 6 benchmarks across Intelligence, Speed... | Artificial Analysis</a></li>
<li><a href="https://kiro.dev/">Kiro: Move beyond AI coding to agentic engineering</a></li>
<li><a href="https://aws.amazon.com/documentation-overview/kiro/">Kiro Documentation - AWS - Amazon.com</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#GPT-5.6`, `#AI`, `#Developer Tools`, `#Price-Performance`

---

<a id="item-7"></a>
## [SELF 格式让 SQLite 数据库在 Linux 上可执行](https://simonwillison.net/2026/Aug/24/your-executable-is-a-sqlite-database/) ⭐️ 7.0/10

法里德·扎卡里亚（Farid Zakaria）提出了一种名为 SELF（Structured Executable &amp; Linkable Format）的 Linux 模式：将 ELF 可执行文件的组件存放到 SQLite 数据表中，并将文件头的应用程序 ID 设为“SELF”，从而使 SQLite 数据库文件本身成为可执行程序。配套的 self-exec 解释器可以提取并运行其中的 ELF 内容，而 binfmt\_misc 可让 Linux 内核自动识别并执行这类文件。 由于 SQLite 是随处可用的嵌入式数据库，而 ELF 是 Linux 的标准可执行文件格式，这个技巧模糊了数据与代码的界限，有可能催生新的分发方式：一个 SQLite 文件既能当数据库，也能作为程序直接运行。尽管这仍属小众玩法，它展示了 Linux binfmt\_misc 机制的灵活性，并可能启发更多“多格式文件”（polyglot file）的尝试。 SQLite 文件头偏移 68 字节处的 4 字节应用程序 ID 被设为 &\#x27;SELF&\#x27;；ELF 的各个组件按照 GitHub 上的 schema 分布到多张 SQLite 表中。通过 binfmt\_misc 注册规则 &\#x27;:self:M:68:SELF::/usr/local/bin/self-exec:&\#x27;，内核即可将匹配的文件交给 self-exec 解释器运行；原作者的演示环境是 NixOS。

rss · Simon Willison · 8月24日 11:38

**背景**: ELF（Executable and Linkable Format，可执行与可链接格式）是 Linux 上可执行文件和共享库的标准二进制格式。SQLite 数据库文件头有一个 application\_id 字段（位于偏移 68 字节处），应用程序可将其设置为唯一值，以便 file\(1\) 等工具识别具体文件类型。binfmt\_misc 是 Linux 内核的一项功能，允许识别自定义二进制格式并将其交给用户态解释器处理，常用于模拟器和虚拟机。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Executable_and_Linkable_Format">Executable and Linkable Format - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Binfmt_misc">binfmt _ misc - Wikipedia</a></li>
<li><a href="https://stackoverflow.com/questions/21929457/sqlite-how-to-use-pragma-application-id">SQLite: how to use PRAGMA application_id? - Stack Overflow</a></li>

</ul>
</details>

**标签**: `#linux`, `#sqlite`, `#executable`, `#elf`, `#binfmt\_misc`

---

<a id="item-8"></a>
## [课堂中更智能使用聊天机器人的指南](https://www.technologyreview.com/2026/08/24/1142630/ai-school-classroom-policies/) ⭐️ 7.0/10

《麻省理工科技评论》的文章为教育工作者概述了在课堂上鼓励负责任且有效使用 AI 聊天机器人的实用策略。文章回应了几年前学生开始在手机上携带聊天机器人所造成的冲击。 随着 AI 聊天机器人在教育环境中越来越普遍，明确的指导对于帮助教师高效整合它们并减少滥用和抄袭至关重要。这套实用框架可以影响学校和政策制定者对待教学中 AI 应用的方式。 这篇文章是《麻省理工科技评论》“让 AI 发挥作用”限量通讯的一部分，专注于在行业间应用大型语言模型。它提供了针对课堂环境的可操作策略，而非抽象理论。

rss · MIT Technology Review AI · 8月24日 14:20

**背景**: 大型语言模型（LLMs）是经过海量文本数据训练的 AI 系统，能够理解和生成类似人类的语言。这些模型可以回答问题、撰写内容、翻译语言以及执行许多其他语言任务。几年前，由 LLMs 驱动的聊天机器人通过智能手机广泛普及，令许多学校措手不及，从而催生了更新政策的必要。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ibm.com/think/topics/large-language-models">What are large language models (LLMs)? - IBM</a></li>
<li><a href="https://www.geeksforgeeks.org/artificial-intelligence/large-language-model-llm/">Large Language Model (LLM) - GeeksforGeeks</a></li>

</ul>
</details>

**标签**: `#AI in Education`, `#LLM`, `#Policy`, `#Teaching`, `#Chatbots`

---

<a id="item-9"></a>
## [儿童仍比 AI 更会学习语言，原因依然成谜](https://www.technologyreview.com/2026/08/24/1141740/kids-machines-language-learning/) ⭐️ 7.0/10

《麻省理工科技评论》于 2026 年 8 月 24 日发表文章指出，除了人类儿童之外，大语言模型已成为第二种能近乎完美掌握人类语言的存在。文章强调，尽管取得这一里程碑，科学家仍然不完全清楚儿童和 AI 模型究竟是如何学习语言的。 这个问题之所以重要，是因为弄清儿童如何从极少的数据中学会语言，可能催生样本效率高得多的 AI 模型，并重塑认知科学的争论。它也与“刺激贫乏论”相关，即语言能力是否部分来自先天机制。 这篇文章发表于知名科技媒体《麻省理工科技评论》，定位是分析性深度文章，而非报道某项新的实验突破。文中以“ChatGPT 发布后的短短四年”为时间锚点，将讨论置于基于大语言模型的聊天机器人快速演进的背景中。

rss · MIT Technology Review AI · 8月24日 09:00

**背景**: 像 ChatGPT 这样的大语言模型是基于海量文本训练、用于预测和生成语言的神经网络，随着规模扩大，有时会表现出无法提前预测的“涌现能力”。在语言学中，与乔姆斯基相关的“刺激贫乏论”认为，儿童接收到的语言数据并不充分，却能学会语言，这说明人类也许有某种先天语言倾向。与当前需要海量数据集的 AI 系统相比，儿童在样本效率上也高出许多，因此这种比较成为文章的核心。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Emergent_abilities_of_large_language_models">Emergent abilities of large language models</a></li>
<li><a href="https://en.wikipedia.org/wiki/Poverty_of_stimulus_argument">Poverty of stimulus argument</a></li>
<li><a href="https://arxiv.org/abs/2206.07682">[2206.07682] Emergent Abilities of Large Language Models</a></li>

</ul>
</details>

**标签**: `#AI`, `#language learning`, `#cognitive science`, `#machine learning`, `#education`

---

<a id="item-10"></a>
## [Unbounded Labs 发布 Bart：基于 1931 年前英语训练的复古大语言模型](https://www.reddit.com/r/MachineLearning/comments/1vx94er/bart_a_vintage_llm_r/) ⭐️ 7.0/10

Unbounded Labs 发布了 Bart（Bartholomew），一个从头训练的 2.82B 参数大语言模型，训练数据是 1931 年前写成的 201 亿 token 英语文本。此次发布包含模型权重、技术文章、演示、含 41.6 万道题的 SFT 数据集以及全部训练代码。 Bart 推动了“复古”或“时间胶囊”大语言模型这一新兴领域的发展，这些模型旨在检验仅用历史文本训练是否能还原过去的科学推理与知识。其开放资源为研究者提供了研究历史文本分析、基准设计和规模化数据清洗的具体起点。 该模型在单块 H100 上训练了约五天，MFU 约为 60%，总计算成本约 807 美元。团队将哈佛 Institutional Books 语料从 242B token 清洗至 23B token，创建了包含 20 个基准的 Vintage CORE 套件，并报告 Bart 在相似规模下优于 GPT-1900。技术文章还坦率讨论了训练中失败的消融实验和犯过的错误。

reddit · r/MachineLearning · /u/soggydoggy8 · 8月24日 17:20

**背景**: “复古”大语言模型（又称历史或时间胶囊大语言模型）是指仅用某个有界历史时期内的文本从头训练的模型，例如某日期之前写下的所有文字。这一思路由 Demis Hassabis 提出，用于探索大语言模型能否重新得出过去伟大科学家的结论，同时与认知型 AI、历史模拟和预测研究相关。Bart 是这一想法最早的开放示例之一，结合了精心清洗的历史语料与完整记录的训练流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://owainevans.github.io/talk-transcript.html">Vintage Large Language Models</a></li>
<li><a href="https://github.com/entanglr/awesome-vintage-llms">GitHub - entanglr/awesome-vintage-llms: A curated list of vintage large language models — also called historical or time-capsule LLMs — trained from scratch on text from bounded historical periods, along with the papers, datasets, demos, and discussions surrounding them.</a></li>
<li><a href="https://arxiv.org/html/2506.01732v1">Common Corpus: The Largest Collection of Ethical Data for LLM ...</a></li>

</ul>
</details>

**标签**: `#LLM`, `#pretraining`, `#historical text`, `#NLP`, `#research`

---

<a id="item-11"></a>
## [基于延迟校正 Bellman 算子与因果归因的约束强化学习](https://www.reddit.com/r/MachineLearning/comments/1vx11hz/delaycorrected_bellman_operator_causal/) ⭐️ 7.0/10

一篇 Reddit 帖子介绍了 CCPL（因果后果惩罚学习），它使用延迟校正的 Bellman 算子，在未知随机延迟下具有收缩性证明，并利用在结构因果模型标签上预训练的干预后果网络（ICN）将延迟后果正确归因于相应动作。 标准约束强化学习会惩罚违规行为之前的动作，当后果具有延迟性和随机性时会导致错误归因。这项工作通过提供收缩性理论保证和因果归因机制填补了一个重要空白，有望改进真实世界中存在延迟反馈的安全强化学习。 延迟校正的 Bellman 算子使用从后果延迟分布中学习的自适应有效折扣。ICN 目前需要访问环境的结构因果模型来生成预训练标签，这限制了在 SCM 未知或难以指定的基准场景之外的应用。

reddit · r/MachineLearning · /u/No\_Cauliflower7923 · 8月24日 12:11

**背景**: 在强化学习中，Bellman 算子定义了价值估计的更新方式，而收缩性保证算法收敛到唯一不动点。标准约束强化学习假设后果是即时且可归因的，但真实环境中的结果往往具有延迟性和随机性。因果归因方法旨在识别结果的真正原因，而不是依赖时间邻近性。像 ACPL 这样的方法也处理延迟后果约束，但可能缺乏因果归因或理论保证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://prismix.dev/news/f1072ba9e03c">Delay-corrected Bellman operator + causal attribution for ...</a></li>
<li><a href="https://github.com/sciencebanda09/ACPL-Adaptive-Consequence-Penalized-Learning">sciencebanda09/ACPL-Adaptive-Consequence-Penalized-Learning</a></li>
<li><a href="https://arxiv.org/abs/2506.05968">Gradual Transition from Bellman Optimality Operator to ... GitHub - motokiomura/annealed-q-learning: [ICML 2025 ... Markov Decision ProcessesLecture Notes 05 Value Iteration Lecture 17: Bellman Operators, Policy Iteration, and Value ... Bellman Operators are Contractions - cfml.se</a></li>

</ul>
</details>

**标签**: `#reinforcement-learning`, `#constrained-rl`, `#causal-attribution`, `#bellman-operator`, `#delay`

---

<a id="item-12"></a>
## [OpenAI 评欧盟《行为准则》与人工智能在欧洲的未来](https://news.google.com/rss/articles/CBMic0FVX3lxTE9LbGxGNGtLZFZqVS1aUXVaQmFaNF85NEhWekhmVUp3WjlRc0VVeXdISTVFVkpaZmk2UVIyUU44ZTB6U01OZk1qTzZVTTZFOUJwNXhQOFNNRjU0VzFJLV9pV2lDV2ljaUxoNnQxTVQ0STRCLWM?oc=5) ⭐️ 7.0/10

OpenAI 发布了一篇关于欧盟人工智能《行为准则》的官方评论，阐述了其对这一自愿性框架将如何影响欧洲人工智能发展未来的看法。 作为领先的人工智能开发商，OpenAI 的公开立场可能对欧盟正在进行的政策辩论和行业实践产生重大影响。该评论可能有助于影响自愿性标准的实施，这些标准将影响欧洲所有人工智能提供者和部署者。 欧盟《行为准则》是根据《人工智能法案》第 95 条推动的，该条款鼓励自愿遵守道德准则、环境可持续性、人工智能素养、包容性设计以及保护弱势群体等标准。OpenAI 的评论可能涉及这些自愿性措施如何与通用人工智能的强制性要求相衔接。

google\_news · OpenAI · 8月24日 08:09

**背景**: 欧盟《人工智能法案》建立了全面的人工智能监管框架，其中第 95 条特别鼓励为人工智能系统制定自愿性行为准则。这些准则旨在促进超出法律要求的道德准则和最佳实践。随着欧盟监管机构最终确定并实施《人工智能法案》，OpenAI 的评论是更广泛的行业参与的一部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-95">AI Act Service Desk - Article 95: Codes of conduct for ...</a></li>
<li><a href="https://artificialintelligenceact.eu/article/95/">Article 95: Codes of Conduct for Voluntary Application of ...</a></li>

</ul>
</details>

**标签**: `#AI`, `#EU regulation`, `#OpenAI`, `#policy`

---

<a id="item-13"></a>
## [阿里发布 Wan3.0 视频大模型：30 秒 PPT 变视频](https://news.google.com/rss/articles/CBMiZEFVX3lxTFBmWUQ0Rnd3QXZlVjVxVmlvaVZ5Qm9VUERrd0w1bUx5eUFYSS1SVS1sdk5QNHJ2WEM3ZmFfeGpqTXppbXJMYmZNV3hiNUI1SHJjX0NZRWgzTEZubjVzT1Z6RkV2M0E?oc=5) ⭐️ 7.0/10

阿里巴巴正式上线最新视频生成模型 Wan3.0，并进入公开测试阶段。该模型可单次生成最长 30 秒的 1080p 视频，并支持文本、图像、音频以及 PowerPoint 等办公文档的多模态输入。 Wan3.0 将单次生成视频时长扩展到 30 秒，比常见的几秒钟片段更具连贯叙事能力。支持将 PPT 等文档直接转化为视频，降低了企业和内容创作者制作视频素材的门槛。 Wan3.0 将此前 Wan2.7 所需的四个独立模型整合为一个模型，输出最高为 1080p，而非传闻中的 4K。它是 Wan 系列中首个直接接受 doc、xls、ppt、pdf、txt、key、pages 等办公文档格式作为输入源的模型。

google\_news · 新京报 · 8月24日 12:22

**背景**: 视频生成模型通常只能输出几秒钟的画面，只够一个镜头，无法构成完整故事。由阿里通义实验室研发的 Wan3.0 将单次生成时长扩展到 30 秒，并支持带音频的视频，除了文本和图像外，还能从文档和网页生成视频。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.alibabacloud.com/blog/wan3-0-30-second-ai-video-generation-from-any-input_603452">Wan3.0: 30-Second AI Video Generation from Any Input - Alibaba Cloud Community</a></li>
<li><a href="https://technode.global/2026/08/10/chinas-alibaba-releases-wan3-0-ai-video-model-in-public-beta-with-30s-clips-multimodal-inputs/">China&#x27;s Alibaba releases Wan3.0 AI video model in public beta with 30s clips, multimodal inputs - TNGlobal</a></li>
<li><a href="https://www.ngram.com/blog/wan-3-0-document-to-video-ai-model">Wan 3.0: Alibaba&#x27;s Document-to-Video AI Model Explained | ngram.com</a></li>

</ul>
</details>

**标签**: `#AI`, `#Video Generation`, `#Alibaba`, `#Generative AI`, `#Model Release`

---