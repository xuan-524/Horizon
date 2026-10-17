---
layout: default
title: "Horizon Summary: 2026-10-17 (ZH)"
date: 2026-10-17
lang: zh
---

> 从 61 条内容中筛选出 8 条重要资讯。

---

1. [Claude 破解 NIST ECDSA 曲线种子来源：出自 C 库 lrand48 随机数生成器](#item-1) ⭐️ 9.0/10
2. [Jake Archibald 对比 Web 场景下的 JPEG XL 与 AVIF](#item-2) ⭐️ 8.0/10
3. [Mercor 研究：美国 90% 的工作时长缺乏 AI 基准测试覆盖](#item-3) ⭐️ 8.0/10
4. [研究人员利用 OpenBSD 存在 37 年的内核漏洞](#item-4) ⭐️ 8.0/10
5. [ORL 与 dlmrt 让扩散语言模型在单张 RTX 5090 上达到 2,788 tokens/s](#item-5) ⭐️ 8.0/10
6. [NVIDIA 与 Hugging Face 发布 2.8 万亿 Token 的印度语言预训练语料及开放数据流水线](#item-6) ⭐️ 7.0/10
7. [圆桌对话：AI 设计病毒创造者访谈](#item-7) ⭐️ 7.0/10
8. [Rust 框架 DenseCore 实现与 PyTorch nanoGPT 训练结果逐位一致](#item-8) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Claude 破解 NIST ECDSA 曲线种子来源：出自 C 库 lrand48 随机数生成器](https://www.anthropic.com/research/ecdsa-curve-origins) ⭐️ 9.0/10

Anthropic 报告称，其模型 Claude 在不到半小时内逆向破解了 NIST 椭圆曲线（P-192、P-224、P-256、P-384 和 P-521）种子的来源，发现它们并非文档所称的某种哈希算法的输出，而是 C 标准库 lrand48 伪随机数生成器以 Unix 时间戳为种子生成的输出。 这解开了一桩延续数十年的密码学悬案，基本消解了长期以来关于 NSA 故意选择 NIST 曲线以植入隐藏后门的怀疑；同时也表明 AI 模型能够开展真正具有原创性的密码学研究，而不只是总结已有成果。 值得注意的是，这一发现只证实了种子是如何生成的，而非曲线是如何被选中的：由于被丢弃的候选值不可见，仍不能排除当初是通过遍历时间戳来搜索具有特定性质的曲线的可能性。第五个二进制种子 B-163 仍然无法匹配 Claude 尝试的任何方法，一些观察者认为这是从生成到发布过程中某处出现录入笔误所致。

hackernews · ahlCVA · 10月16日 18:55 · [社区讨论](https://news.ycombinator.com/item?id=50122800)

**背景**: NIST 在 2000 年发布的 FIPS 186-2 中公布了 ECDSA 所用的标准椭圆曲线，这些曲线于 1997 年生成，种子据称由 NSA 提供；按照文档描述的方法，应取一个任意种子、用 SHA-1 哈希，再由输出推导出参数，从而满足 ANSI X9.62 所说的“可验证随机”。由于无人能复现这些种子，加上 2007 年 Dual\_EC\_DRBG 后门丑闻，社区中许多人怀疑曲线本身是被刻意操纵的。lrand48 是 Unix C 库中采用 48 位整数运算的线性同余生成器，通常用 srand48\(\) 设置种子，而 Filippo Valsorda 曾悬赏 1.2 万美元征集这些种子的来源。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/research/ecdsa-curve-origins">Claude reveals ECDSA curve origins \ Anthropic</a></li>
<li><a href="https://words.filippo.io/dispatches/seeds-bounty/">Announcing the $12k NIST Elliptic Curves Seeds Bounty</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/bounty-offered-for-secret-nsa-seeds-behind-nist-elliptic-curves-algo/">Bounty offered for secret NSA seeds behind NIST elliptic curves algo</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的评论（662 分、265 条评论）总体持赞赏态度，有人称这一结果“太漂亮了”，并调侃当年那位 NSA 员工大概是随手用了 srand48\(time\(NULL\)\)，然后偷笑了 25 年。最主要的实质性反驳是：确认生成方法并不能说明选择偏差，因为被丢弃的候选值无法被检查；也有人指出，无法解释的 B-163 种子最简单的解释就是录入笔误。还有不少人表示，这对整整一代 NIST 密码学阴谋论来说是个毁灭性的消息。

**标签**: `#cryptography`, `#ECDSA`, `#NIST-curves`, `#AI-research`, `#random-number-generators`

---

<a id="item-2"></a>
## [Jake Archibald 对比 Web 场景下的 JPEG XL 与 AVIF](https://jakearchibald.com/2026/jpeg-xl-vs-avif/) ⭐️ 8.0/10

Web 性能专家 Jake Archibald 发布了一篇针对真实 Web 图片场景的 JPEG XL 与 AVIF 详细对比，涵盖压缩效率、编码速度、工具链成熟度以及实际取舍。该文引发了 143 条评论的讨论，开发者们分享了基准测试数据、编码器参数设置以及对新格式炒作的警示。 图片通常是网页体积中占比最大的资源，因此 JPEG XL 与 AVIF 之间的取舍会直接影响几乎每个网站的加载速度、带宽成本和 Core Web Vitals 表现。由于浏览器支持仍不均衡——尤其是 Chromium 决定不内置 JPEG XL——这篇对比能帮助团队判断当下究竟该部署哪种格式，而不只是看纸面数据谁更优。 根据讨论，libjxl 的最高压缩档位速度极慢：相比默认档位，照片文件只小 2–7%，截图和插画约小 25%，但耗时 9–46 秒，是默认档位的 50–180 倍；而据称一个名为 jixel 的工具能在几秒内取得相同效果。评论者还指出 AVIF 会明显抹掉精细的高光细节（以一张 F1 赛车图为例），用看似合理的纹理将其替代。

hackernews · farlight · 10月16日 16:12 · [社区讨论](https://news.ycombinator.com/item?id=50120224)

**背景**: JPEG XL 是由联合图像专家组（JPEG）与 Google、Cloudinary 共同开发的下一代图像格式，同时支持有损与无损压缩、动画、Alpha 透明通道，以及将现有 JPEG 无损重新压缩。AVIF（AV1 Image File Format）是一种开放、免版税的格式，使用由开放媒体联盟（AOMedia）开发的 AV1 编解码器压缩图像，而 AV1 同时也是新一代视频流媒体所用的编解码器。两种格式都旨在通过同等视觉质量下更小的文件来取代传统的 JPEG 和 WebP，但在编码器成熟度、工具链和浏览器支持方面各有差异。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/JPEG_XL">JPEG XL - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/AVIF">AVIF - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/AV1">AV1 - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 整体情绪褒贬不一但偏向谨慎：一些开发者称赞 AVIF 在生产环境中的表现，并分享了能让文件缩小 10 倍以上、同时保留 PNG 透明通道的 ffmpeg 命令行；另一些人则警告这些编解码器尚未成熟，并以漫长而混乱的 MP3/LAME 时代以及当年对 WebP 的夸大宣传为例，认为不应过早宣布胜负。一个引人注目的反驳观点认为，文中的 F1 赛车基准图恰恰暴露了 AVIF 的缺陷，因为其高光细节不是被保留而是被破坏。

**标签**: `#JPEG XL`, `#AVIF`, `#image compression`, `#web performance`, `#codecs`

---

<a id="item-3"></a>
## [Mercor 研究：美国 90% 的工作时长缺乏 AI 基准测试覆盖](https://www.mercor.com/research/labor-index/benchmark-map/) ⭐️ 8.0/10

Mercor 在其 Labor Index 中发布了一份“基准测试地图”（benchmark map）分析，发现美国大约 90% 的工作时长都花在现有 AI 基准测试几乎或完全没有覆盖的任务上。该研究把基准测试的题目与 O\*NET 职业任务及工资数据对应起来，并在 Hacker News 上引发了热烈讨论（393 分、329 条评论）。 基准测试是宣称模型进步、判断 AI 系统是否“足够好用、可以部署”的主要标尺；如果它们漏掉了大多数劳动者实际执行的任务，那么能力宣称和岗位替代预测都可能严重失准。对 AI 实验室、企业和政策制定者而言，这会削弱“基准分数提升等同于真实经济价值”的信心。 该分析使用按职业工资总额加权的 O\*NET 任务数据，并指出即便控制 AI 暴露度之后，高薪职业的任务在基准测试题目中仍被明显过度代表。评论者则质疑其方法：仅凭某个任务出现约 13 道题目就判定为“覆盖良好”，其实混淆了“有所覆盖”和“覆盖良好”两个概念。

hackernews · speckx · 10月16日 17:08 · [社区讨论](https://news.ycombinator.com/item?id=50121179)

**背景**: AI 基准测试是一套标准化评测集（如推理、编程或智能体基准），用固定的一批题目来比较不同语言模型的能力。O\*NET 是美国劳工部的职业数据库，列出了数百种职业所需的任务、技能与知识，因此常被用来把 AI 暴露度映射到真实岗位上。Mercor 是一家 AI 数据公司，为前沿实验室连接各领域专家，从事 RLHF 数据采集、模型评测等工作，因此基准测试与真实工作的匹配程度与其业务直接相关。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.welcome.ai/company/mercor">Mercor - AI Company Profile | Welcome. AI</a></li>
<li><a href="https://annotation.academy/glossary/what-is-mercor-ai-company">What Is Mercor AI ? Definition &amp; Platform... | Annotation Academy</a></li>
<li><a href="https://www.evidentlyai.com/blog/ai-benchmarks">25 AI benchmarks: examples of AI models evaluation</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍认同这一差距确实存在，但对其解读有分歧：有人以“门卫谬误”（Doorman Fallacy）作比，指出自动化一个显性任务可能会破坏客户体验等看不见却关键的功能；也有人认为该研究实际上说明高薪的“好工作”在基准题目中被过度代表。还有人把论点延伸到个人层面的鲍莫尔成本病——编码效率提升 20 倍的程序员，时间仍被演示、Jira 和 QA 占满；也有人引用 Karpathy 的估计，称 AI 目前只能处理约 2–5% 的工作，且重度使用者与轻度使用者之间的差距正在拉大。

**标签**: `#AI benchmarks`, `#AI evaluation`, `#labor economics`, `#future of work`, `#Hacker News discussion`

---

<a id="item-4"></a>
## [研究人员利用 OpenBSD 存在 37 年的内核漏洞](https://calif.io/research/big-fish) ⭐️ 8.0/10

安全研究团队 Calif 发布了名为 &quot;Big Fish&quot; 的研究报告，详细描述了如何利用 OpenBSD 中一个可追溯到约 37 年前原始 BSD 源码的内核漏洞。该漏洞的根源是一个共享内存附加计数器被定义为有符号 16 位 short 类型，从而导致可被利用的整数溢出原语，出现在一个经受了严格审计的操作系统中。 这一发现意义重大，因为 OpenBSD 被普遍认为是业界最注重安全、审查最严格的代码库之一，一个漏洞能存活近四十年，动摇了&quot;长期人工审计足以保证安全&quot;的假设。它也引发了更广泛的疑问：在支撑现代基础设施的 BSD 衍生代码库以及其他 C 代码中，还潜伏着多少类似的古老缺陷。 该漏洞源于一个被定义为有符号 16 位 short 类型的共享内存附加计数器，这意味着在附加次数足够多后该值会溢出，从而为攻击者提供可控的利用原语。值得注意的是，同样的代码在 1999 年 8 月 NetBSD 的重写过程中被顺带修复，属于&quot;意外修复&quot;，当时并没有任何 CVE 或协调披露与之关联。

hackernews · rs\_rs\_rs\_rs\_rs · 10月16日 14:44 · [社区讨论](https://news.ycombinator.com/item?id=50118977)

**背景**: OpenBSD 是由 Theo de Raadt 于 1995 年从 NetBSD 1.0 分叉出来的、以安全为核心的类 Unix 操作系统，其项目强调主动安全与代码正确性，OpenSSH 等被广泛使用的工具正源自这里。它与最初的伯克利软件发行版（BSD）同宗同源，这意味着老代码与老的设计决策可能跨越数十年、在多个衍生项目中延续。共享内存附加计数器是内核用于记录有多少进程或映射引用某个共享内存段的记账字段，因此这类计数器一旦整数宽度设置不当，就可能被利用来破坏内核状态。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://calif.io/research/big-fish">Big Fish: Exploiting a 37 - Year - Old Kernel Bug in OpenBSD | Calif</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenBSD">OpenBSD - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论者称赞该报告采用了 OpenBSD 发布风格的配图，并期待配套的主题曲，但讨论的核心仍是技术问题：有人指出该漏洞在 1999 年 8 月 NetBSD 重写代码时被意外修复，另有人评论说，一个漏洞能在如此严格审计的代码库中存活 37 年，说明某些内核漏洞仅靠代码审查极难发现。讨论中提出的开放问题是：模糊测试或静态分析是否真有可能发现这一类漏洞，还是必须依靠人去思考利用原语。

**标签**: `#security`, `#openbsd`, `#kernel`, `#vulnerability`, `#exploit`

---

<a id="item-5"></a>
## [ORL 与 dlmrt 让扩散语言模型在单张 RTX 5090 上达到 2,788 tokens/s](https://www.reddit.com/r/MachineLearning/comments/1x7qgr0/research_2788_tokenss_on_a_single_rtx_5090_with_a/) ⭐️ 8.0/10

研究者发布了 ORL（On-Policy Residual Learning，同策略残差学习）以及专为扩散语言模型打造的推理引擎 dlmrt，并报告 LLaDA-2.1-mini + ORL 在 NVFP4 下于单张 RTX 5090 上达到 2,788 tokens/s，DiffusionGemma 26B MoE + ORL 在 8× B200 上达到 7,708 tokens/s。他们还报告 QwenDLM-4B 的端到端吞吐提升最高约 6.9 倍、单次前向生成的 token 数提升最高 6.2 倍，HumanEval pass@1 从 82.9% 提升到 89.6%，并且模型、训练代码、评测流程与推理引擎全部开源。 扩散语言模型理论上可以并行解码多个 token，但长期受限于收敛速度慢和推理基础设施不成熟，因此这项研究直指阻碍其成为自回归解码实际替代方案的核心瓶颈。如果所报告的加速能够被复现，那么在消费级与数据中心 GPU 上进行的单请求、低延迟扩散解码，就有可能与运行在 vLLM 上的 DFlash、EAGLE3 等投机解码方案正面竞争。 所有亮眼数字都来自 batch size 为 1 的单请求解码，且是特定基准上的峰值结果而非任意提示词上的平均值；据称 LLaDA-2.1-mini 上的 ORL 后训练仅需 420 万自生成 token 和 36 个 H100 GPU 小时，而在单张 H100 上 QwenDLM-4B + ORL 达到 1,298 tokens/s，实测精度相近时 DFlash 为 746 tokens/s、EAGLE3 为 405 tokens/s。该对比属于端到端系统级比较（dlmrt 对比 vLLM），dlmrt 将整个去噪循环捕获进 CUDA graph，并宣称在单张 H100 上比 SGLang/vLLM 快 1.2–1.6 倍；此外该工作尚未经过同行评审。

reddit · r/MachineLearning · /u/arty\_photography · 10月16日 20:03

**背景**: 自回归大模型逐 token 从左到右生成文本，这限制了 GPU 可发挥的并行度。扩散语言模型借鉴图像扩散模型的思路，从带噪声或被掩码的序列出发，一次性对多个 token 位置迭代去噪与修正，因此“收敛所需的前向次数”成为衡量效率的关键指标。推理引擎的重要性不亚于模型本身——同样的权重、同样的 GPU，因 kernel 实现与调度方式不同，吞吐可能相差巨大，这正是 SGLang、vLLM、TensorRT-LLM 在这一层竞争的原因，也是 ORL 作者自研 dlmrt 引擎、把整个去噪循环留在 GPU 上执行的原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Diffusion_model">Diffusion model</a></li>
<li><a href="https://www.emergentmind.com/topics/diffusion-llm">Diffusion - LLM : Principles &amp; Architectures</a></li>
<li><a href="https://www.truefoundry.com/blog/sglang-vs-vllm-vs-tensorrt-llm">SGLang vs vLLM vs TensorRT-LLM: Choosing an Inference Engine</a></li>

</ul>
</details>

**标签**: `#diffusion-LLM`, `#inference-optimization`, `#open-source`, `#LLM`, `#NVIDIA-GPU`

---

<a id="item-6"></a>
## [NVIDIA 与 Hugging Face 发布 2.8 万亿 Token 的印度语言预训练语料及开放数据流水线](https://huggingface.co/blog/nvidia/scaling-indic-pretraining) ⭐️ 7.0/10

Hugging Face 与 NVIDIA 联合发布博客，介绍了一个规模达 2.8 万亿 token 的印度语言（Indic）预训练语料库，并同时开源了一套用于生成多语言训练数据的流水线。该发布将超大规模的精选数据集与可复用、可复现的数据生成流程结合在一起，面向印度诸语言的建模需求。 印度诸语言的使用人口超过十亿，但在大多数大模型的预训练数据中占比极低；因此这一规模的语料库加上开放的数据生成流水线，大幅降低了构建 Indic 模型及其他低资源多语言模型的门槛。这也表明主要厂商正持续把开放的多语言数据投入作为大模型差异化竞争的重要方向。 核心数字是 2.8 万亿 token 的预训练数据，第二个交付物是数据生成流水线本身——它是公开而非专有保留的。其重点在于数据规模与多语言覆盖度的同步扩展；不过作为一篇技术博客公告，它属于数据与工具层面的发布，而非新的模型架构或训练方法。

rss · Hugging Face Blog · 10月16日 01:44

**背景**: 预训练是大语言模型在任何针对特定任务的微调或对齐之前，从海量原始文本中学习通用语言规律的阶段。印地语、孟加拉语、泰米尔语、泰卢固语等印度语言使用多种文字体系，且高质量数字化文本远少于英语，因此在自然语言处理中被称为低资源语言。缩小这一差距的常见做法是构建超大规模的精选语料库，并搭建能够过滤、去重并合成扩充多语言文本的流水线，而本次发布提供的正是这些内容。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/anoopkunchukuttan/indic_nlp_library">GitHub - anoopkunchukuttan/indic_nlp_library: Resources and ...</a></li>
<li><a href="https://indicnlp.github.io/">IndicNLP</a></li>
<li><a href="https://www.emergentmind.com/topics/synthetic-multilingual-pretraining-data">Synthetic Multilingual Pretraining Data</a></li>

</ul>
</details>

**标签**: `#Indic NLP`, `#pretraining`, `#multilingual models`, `#open data`, `#LLM scaling`

---

<a id="item-7"></a>
## [圆桌对话：AI 设计病毒创造者访谈](https://www.technologyreview.com/2026/10/16/1146224/roundtables-a-conversation-with-the-creator-of-ai-designed-viruses/) ⭐️ 7.0/10

MIT Technology Review 发布了一场圆桌对话，嘉宾是斯坦福大学博士生 Samuel King，他在 2025 年使用生成式 AI 模型提出了微型病毒的基因蓝图。对话探讨了 AI 能否设计新的生命形式，并指出这还不是 AI 生成的生命，但可能是下一步。 这项工作标志着利用生成式 AI 编写功能性病毒基因组迈出了一步，模糊了计算设计与生命系统之间的界限。它对合成生物学、药物开发和生物安全具有重大影响，因为同样的工具可能被滥用来制造有害病原体。 这些 AI 设计的病毒是噬菌体（感染细菌的病毒），其基因组被合成并在实验室中进行了测试，但该新闻本身只是视频/音频会话的简短宣传预告，因此技术方法和安全评估并未详述。圆桌形式表明讨论更侧重于生物伦理与治理，而非新的实验结果。

rss · MIT Technology Review AI · 10月16日 18:00

**背景**: 合成生物学是一门跨学科领域，应用工程原理来设计或重新设计生物系统。生成式 AI 模型在大规模基因序列数据集上训练后，如今能够提出可能折叠成功能性蛋白质或病毒基因组的新 DNA 或 RNA 序列。生物安全指旨在防止有害生物（无论是自然出现还是人为制造）传播的措施，是 AI 设计生命相关争论的核心。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nature.com/articles/d41586-025-03055-y">World’s first AI-designed viruses a step towards AI-generated ...</a></li>
<li><a href="https://www.bbc.com/news/articles/c5y3j3ngevmo">Artificial Intelligence used to design brand new viruses - BBC</a></li>
<li><a href="https://betanews.com/article/ai-designed-viruses-stanford-arc-institute/">Scientists design first fully AI-generated viruses - BetaNews</a></li>

</ul>
</details>

**标签**: `#AI`, `#synthetic-biology`, `#biosecurity`, `#generative-models`, `#bioethics`

---

<a id="item-8"></a>
## [Rust 框架 DenseCore 实现与 PyTorch nanoGPT 训练结果逐位一致](https://www.reddit.com/r/MachineLearning/comments/1x7ojxo/p_my_rust_framework_trains_nanogpt_with_the_exact/) ⭐️ 7.0/10

一名计算机专业学生用 Rust 写了小型深度学习框架 DenseCore，并提供类似 PyTorch 的 Python API；在完全不改动 Karpathy 的 nanoGPT 的前提下，它跑出的初始权重、损失、梯度与权重在测试的全部 50 个训练步中都与 PyTorch 逐位（bit-for-bit）完全相同，即使开启 dropout 也是如此，属于精确复现而非近似接近。作者在过程中还逆向出若干 PyTorch CPU 上未公开的行为，例如 CPU 注意力走的并非教科书公式而是 flash-attention 风格的内核，并且在开启 dropout 时会切换到另一条代码路径。 这项工作是数值可移植性（numerical portability）方面一个具体且可复现的案例研究，而数值可移植性正是所有需要确定性训练流程的人——CI 流水线、serverless 推理、受监管或科研场景——的共同痛点，在这些场景中“相同随机种子、相同结果”是正确性要求而非附加项。作者发现同一版本的 PyTorch 在 macOS 与 Linux x86 之间，26 个测试算子中只有 1 个能给出完全相同的比特位，这说明即便不更换硬件类型、不改动代码，框架层面的逐位复现也只是幻觉。 该实现复现了多个细节怪癖，例如 Adam 在每个线程所处理分块的尾部元素上舍入方式不同（源于编译器对尾部循环的融合），以及 clip\_grad\_norm\_ 内部实际执行的是 reciprocal\(\) \* max\_norm 而非真正的除法。主要限制在于可移植性：DenseCore 只在 Apple Silicon Mac 上与 PyTorch 逐位一致，也就是说它的比特级精度绑定了特定平台；不过框架本身体积很小，约 2 MB，而 PyTorch 约 580 MB。

reddit · r/MachineLearning · /u/Mental-Feature-2377 · 10月16日 18:49

**背景**: nanoGPT 是 Andrej Karpathy 编写的极简、易读的 GPT 架构实现，常被用作训练和微调 GPT 类模型的小规模参考代码。Flash attention 是一种 IO 感知的注意力算法，通过分块（tiling）与算子融合来减少显存/内存读写，框架即使在 CPU 上也可能会把注意力计算导向这类内核，而不采用朴素公式。逐位可复现指的是两次运行产生完全相同的浮点输出，而这通常做不到，原因包括归约顺序不确定、融合乘加指令以及编译器优化；RepDL 之类的项目正是为了强制正确舍入和固定计算顺序来恢复这种可复现性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/karpathy/nanoGPT">GitHub - karpathy/nanoGPT: The simplest, fastest repository ...</a></li>
<li><a href="https://www.emergentmind.com/topics/repdl">RepDL: Bit-Level Reproducible Deep Learning</a></li>
<li><a href="https://123ofai.com/articles/blogs/flash-attention-explained">Flash Attention Explained: How IO-Awareness Solved the... | 123ofAI</a></li>

</ul>
</details>

**标签**: `#rust`, `#deep-learning-frameworks`, `#pytorch`, `#numerical-reproducibility`, `#gpu-kernels`

---