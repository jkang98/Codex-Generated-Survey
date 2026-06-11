# Alibaba Ranking and CTR Papers

这是一份围绕 Alibaba 体系公开论文整理的 ranking / CTR 读书笔记。范围以
阿里妈妈、淘宝、天猫、AliExpress、Lazada 等生产系统中的排序、广告 CTR、
CVR、多目标 LTR、长序列兴趣建模和页面级优化为主；Taobao & Tmall Group
近年的搜索/推荐/广告系统论文单独重点跟踪；召回、匹配、图嵌入等论文只有
在它们直接影响排序或 CTR 建模时才作为背景提到。

这不是完整 bibliographic census，而是面向推荐/广告排序系统的主线梳理：
Alibaba 的公开工作很清楚地展示了一条从 `Embedding & MLP` 到兴趣建模、长
序列检索、跨域统一建模、多目标可控排序和全页优化的工业演进路径。

## Reading Map

```text
Alibaba ranking / CTR papers
|-- CTR and user-interest modeling
|   |-- DIN: target-aware local activation over user behaviors
|   |-- DIEN: latent interest extraction and evolution
|   |-- DSIN: session-aware interest structure
|   |-- BST: Transformer sequence modeling in Taobao
|   |-- MIMN/UIC: long-sequence modeling with serving-system co-design
|   |-- SIM: search-based lifelong behavior retrieval
|   |-- DMIN: multiple latent interests for CTR
|   |-- ETA-Net: end-to-end efficient long-behavior retrieval
|   |-- ULIM: thousand-scale long-behavior retrieval for Taobao recommendation
|   |-- MUSE / MIM: multimodal search-based & content-interest long-behavior modeling
|   |-- HeMix: query-mixed multi-interest CTR with heterogeneous interaction and scaling
|-- Feature, domain, calibration, and parameter adaptation
|   |-- CAN: explicit feature co-action
|   |-- STAR / AdaSparse / HC^2 / Maria: multi-domain and multi-scenario CTR
|   |-- APG: instance-wise adaptive parameter generation
|   |-- KEEP / Rec4Ad: industrial pretraining and sample-selection-bias mitigation
|   |-- JRC: joint ranking and calibration for CTR prediction
|   |-- CLID: calibration-compatible listwise distillation
|   |-- CRB: coupled position/ranking-bias mitigation
|   |-- Taobao multimodal ads / EST / LoopCTR / LUM: multimodal and scalable CTR modeling
|   |-- MOON / Scaling Transformers: multimodal representation and generative-pretraining CTR scaling
|-- CVR, delayed feedback, and post-click objectives
|   |-- ESMM: entire-space multitask CVR estimation
|   |-- ESDF / DEFER / DEFUSE: false negatives and delayed conversion
|   |-- AutoHERI / HDR / ECAD: post-click, historical data reuse, and attribution delay
|   |-- MAL / MAC: multi-attribution CVR learning and benchmark
|   |-- TESLA / CASCADE / READER / TRACE: NetCVR and GMV with delayed feedback
|   |-- TranSUN / ChoirRec: retransformation-bias-free regression ranking and LLM user grouping for CVR
|   |-- Video LTV: long-term value prediction in ranking
|-- Ranking, LTR, and page optimization
|   |-- CLOES: cascade ranking for e-commerce search efficiency
|   |-- RL to Rank: search-session MDP for Taobao ranking
|   |-- Dynamic Ad Allocation: whole-page sponsored/organic allocation
|   |-- DC-LTR: online controllable multi-objective learning to rank
|   |-- COPR: coarse-to-fine consistency in pre-ranking
|   |-- MIREC / MPAD / SORT-Gen: Taobao feed allocation and list reranking
|   |-- PRECTR: unified search relevance and CTR prediction
|   |-- SERAL / KARMA / RecGPT-Mobile: LLM-enhanced Taobao search and feed recommendation
|   |-- Bid2X: adjacent foundation model for online advertising bidding dynamics
|   |-- TARQ / BAR / AIF: pre-ranking target attention, bidding-aware retrieval, async inference
|   |-- AliBoostV2: CTR-growth balanced ecological boosting for cold items
|   |-- GUIDE / LLM-Auction: generative auto-bidding and LLM-native ad auction
|   |-- LLM search & generative ranking: RecGPT / RecGPT-V2 / URM / SIGMA / RankGR / NEZHA / DSIRM / LEAPS / AIGQ / TaoSR-AGRL
```

## Papers

| Year | Paper | Venue | Theme | Short summary |
| --- | --- | --- | --- | --- |
| 2017 | [Cascade Ranking for Operational E-commerce Search](https://www.kdd.org/kdd2017/papers/view/cascade-ranking-for-operational-e-commerce-search) | KDD | Search ranking efficiency | CLOES 把大规模电商搜索排序拆成级联过滤和重排，在效果、延迟、结果规模、CPU 成本之间做联合权衡，是淘宝/阿里搜索工业排序系统的早期代表。 |
| 2018 | [Deep Interest Network for Click-Through Rate Prediction](https://www.kdd.org/kdd2018/accepted-papers/view/deep-interest-network-for-click-through-rate-prediction) | KDD | CTR, target attention | DIN 的核心是 local activation：用户历史行为不是压成一个固定向量，而是针对当前候选广告/商品动态激活相关兴趣。它基本奠定了后续工业 CTR “target-aware behavior attention” 的范式。 |
| 2018 | [Entire Space Multi-Task Model: An Effective Approach for Estimating Post-Click Conversion Rate](https://arxiv.org/abs/1804.07931) | SIGIR | CVR, multitask | ESMM 从 `impression -> click -> conversion` 的链路出发，在 entire space 上联合建模 CTR、CTCVR 和 CVR，缓解只在点击样本上训练 CVR 带来的 sample selection bias 和稀疏性问题。 |
| 2018 | [Reinforcement Learning to Rank in E-Commerce Search Engine](https://www.kdd.org/kdd2018/accepted-papers/view/reinforcement-learning-to-rank-in-e-commerce-search-engine-formalization-an) | KDD | LTR, RL | 将一次搜索 session 看成多步 MDP，排序目标不只是单页即时点击，而是 session 累积收益；这篇适合和 slate/list-level RL 放在一起读。 |
| 2018 | [The Whole-Page Optimization via Dynamic Ad Allocation](https://ir.webis.de/anthology/2018.wwwconf_conference-2018c.280/) | WWW Companion | Whole-page ads/search | 在搜索结果页里动态决定展示多少广告，把 sponsored 和 organic 结果的页面级收益/体验放到一个优化问题中。 |
| 2019 | [Deep Interest Evolution Network for Click-Through Rate Prediction](https://ojs.aaai.org/index.php/AAAI/article/view/4545) | AAAI | CTR, interest evolution | DIEN 在 DIN 之后更进一步：用辅助监督抽取 latent interest，再用带 attention 的序列结构建模兴趣随时间演化，解决“行为本身不等于兴趣”的问题。 |
| 2019 | [Deep Session Interest Network for Click-Through Rate Prediction](https://www.ijcai.org/Proceedings/2019/0319.pdf) | IJCAI | CTR, session modeling | DSIN 把长行为序列按 session 结构切分：session 内兴趣同质，session 间兴趣演化。它适合处理电商中一次浏览/比较/购买意图形成的局部结构。 |
| 2019 | [Behavior Sequence Transformer for E-commerce Recommendation in Alibaba](https://arxiv.org/abs/1905.06874) | DLP-KDD | CTR, Transformer | BST 把 Transformer 用到淘宝推荐 CTR 预估中，强调行为序列的顺序信号；可以看作 Alibaba 体系把自注意力引入工业推荐排序的早期实践。 |
| 2019 | [Practice on Long Sequential User Behavior Modeling for Click-Through Rate Prediction](https://arxiv.org/abs/1905.09248) | KDD | CTR, long sequence, system co-design | MIMN/UIC 的重点不是单纯换模型，而是把最重的用户兴趣更新从在线 request 中解耦出来，用 User Interest Center 增量维护长期兴趣状态。它是“模型结构 + serving 架构一起设计”的经典工业案例。 |
| 2020 | [Deep Match to Rank Model for Personalized Click-Through Rate Prediction](https://ojs.aaai.org/index.php/AAAI/article/view/5346) | AAAI | CTR, matching-to-ranking | DMR 把 matching 思想显式引入 CTR ranking：用 user-to-item 和 item-to-item relevance 表达用户与目标商品的匹配强度，再进入排序预测。 |
| 2020 | [Deep Multi-Interest Network for Click-through Rate Prediction](https://dblp.org/rec/conf/cikm/XiaoYJWHW20) | CIKM | CTR, multi-interest | DMIN 假设用户同一时刻可能有多个 latent interests，用 self-attention refinement 和 multi-interest extraction 分别提炼行为表示和多个兴趣向量。 |
| 2020 | [Search-based User Interest Modeling with Lifelong Sequential Behavior Data for Click-Through Rate Prediction](https://ir.webis.de/anthology/2020.cikm_conference-2020.338/) | CIKM | CTR, lifelong behavior search | SIM 解决 MIMN 继续扩长后的精度和效率问题：先用 general search 从超长行为中取出和 target 相关的子序列，再用 exact search/attention 精排兴趣。它把 CTR 里的行为建模问题变成了“从用户历史里检索相关证据”。 |
| 2020 | [CAN: Feature Co-Action Network for Click-Through Rate Prediction](https://arxiv.org/abs/2011.05625) | arXiv | CTR, feature interaction | CAN 重新强调 raw feature co-action 的价值，用轻量 co-action unit 显式建模目标特征和用户/上下文特征之间的交互。相比只依赖深层 MLP 隐式学习，它更贴近广告 CTR 里大量稀疏交叉特征的工业习惯。 |
| 2020 | [Delayed Feedback Modeling for the Entire Space Conversion Rate Prediction](https://arxiv.org/abs/2011.11826) | arXiv | CVR, delayed feedback | ESDF 试图同时处理 CVR 中的 sample selection bias、稀疏性和 delayed feedback；适合和 ESMM 一起读，理解 post-click conversion 在在线训练中为什么难。 |
| 2021 | [One Model to Serve All: Star Topology Adaptive Recommender for Multi-Domain CTR Prediction](https://arxiv.org/abs/2101.11427) | CIKM | CTR, multi-domain | STAR 用中心共享参数和 domain-specific 参数组成星形拓扑，让一个 CTR 模型服务多个业务域，同时保留共性迁移和场景差异。 |
| 2021 | [Enhancing E-commerce Recommender System Adaptability with Online Deep Controllable Learning-To-Rank](https://ojs.aaai.org/index.php/AAAI/article/view/17785) | AAAI | Online LTR, multi-objective | DC-LTR 面向 AliExpress 和 Lazada 的在线多目标排序：大促前后目标可能从加购、GMV 切到 CTR，系统需要实时可控地切换业务目标。 |
| 2021 | [Capturing Delayed Feedback in Conversion Rate Prediction via Elapsed-Time Sampling](https://arxiv.org/abs/2012.03245) | AAAI | CVR, delayed feedback | 这条线关注在线 CVR 训练里的“暂时未转化不等于负样本”，用 elapsed-time sampling 处理转化延迟造成的标签污染。 |
| 2021 | [Real Negatives Matter: Continuous Training with Real Negatives for Delayed Feedback Modeling](https://arxiv.org/abs/2104.14121) | KDD | CVR, delayed feedback | DEFER 把 delayed feedback 中“暂时未转化”的假负样本和已经过转化窗口的真负样本分开处理，用 continuous training 和 real negatives 缓解 CVR 在线训练中的标签污染。 |
| 2021 | [AutoHERI: Automated Hierarchical Representation Integration for Post-Click Conversion Rate Estimation](https://dl.acm.org/doi/10.1145/3459637.3482061) | CIKM | CVR, post-click, multitask | AutoHERI 用自动化结构搜索来整合不同层级的 post-click 表征，面向电商 CVR 里 CTR、CTCVR、CVR 等任务之间的层级依赖。 |
| 2022 | [APG: Adaptive Parameter Generation Network for Click-Through Rate Prediction](https://arxiv.org/abs/2203.16218) | NeurIPS | CTR, adaptive parameters | APG 让深度 CTR 模型的参数随 instance 动态生成，缓解静态参数难以覆盖不同用户/场景分布的问题，同时通过低秩化控制线上成本。 |
| 2022 | [Asymptotically Unbiased Estimation for Delayed Feedback Modeling via Label Correction](https://arxiv.org/abs/2202.06472) | WWW | CVR, delayed feedback | DEFUSE 把 delayed feedback 看成带噪标签估计问题，通过 label correction 做渐近无偏估计，是 DEFER 之后阿里妈妈后链路预估的重要补充。 |
| 2022 | [AdaSparse: Learning Adaptively Sparse Structures for Multi-Domain Click-Through Rate Prediction](https://arxiv.org/abs/2206.13108) | CIKM | CTR, multi-domain, sparse network | AdaSparse 让不同业务域动态选择不同稀疏子网络，用 domain-aware gate 控制参数共享粒度；它和 STAR 一起构成阿里妈妈多域广告 CTR 的主线。 |
| 2022 | [KEEP: An Industrial Pre-Training Framework for Online Recommendation via Knowledge Extraction and Plugging](https://arxiv.org/abs/2208.10174) | CIKM | Online recommendation, industrial pretraining | KEEP 从 super-domain 抽取 user/item/interaction knowledge，再通过 plug-in network 注入在线推荐/广告模型；重点在工业在线增量训练和 Alibaba display ads 部署，是后面多模态/大模型接入 CTR 系统的前置思路。 |
| 2022 | [Towards Understanding the Overfitting Phenomenon of Deep Click-Through Rate Prediction Models](https://arxiv.org/abs/2209.06053) | CIKM | CTR training dynamics, one-epoch overfitting | 这篇不是新结构模型，但很关键：它系统分析 Alibaba display ads 中 CTR 模型“一到第二个 epoch 就掉点”的 one-epoch overfitting 现象，解释为什么工业 CTR 训练和通用深度学习训练不一样。 |
| 2022 | [Efficient Long Sequential User Data Modeling for Click-Through Rate Prediction](https://arxiv.org/abs/2209.12212) | DLP-KDD / arXiv | CTR, long-sequence retrieval | ETA-Net 把长行为检索和 CTR 模型端到端训练，用 hashing-based efficient target attention 降低标准 target attention 对长序列的线性成本。 |
| 2023 | [Joint Optimization of Ranking and Calibration with Contextualized Hybrid Model](https://arxiv.org/abs/2208.06164) | KDD | CTR, ranking calibration | JRC 直接解决 CTR 模型里 pointwise calibration 和 pair/listwise ranking objective 的冲突：用 click / non-click 两个 logits 统一概率解释，同时加入 listwise-like ranking loss；论文报告已在 Alibaba display advertising 上线。 |
| 2023 | [Capturing Conversion Rate Fluctuation during Sales Promotions: A Novel Historical Data Reuse Approach](https://arxiv.org/abs/2305.12837) | KDD | CVR, historical data reuse, promotion | HDR 面向大促等分布突变场景，把历史活动数据复用为当前 CVR 预估的辅助信号，解决单次大促样本少、转化延迟和分布漂移带来的冷启动问题；论文报告已在 Alibaba display advertising 上线。 |
| 2023 | [Rec4Ad: A Free Lunch to Mitigate Sample Selection Bias for Ads CTR Prediction in Taobao](https://arxiv.org/abs/2306.03527) | arXiv | Ads CTR, sample selection bias | Rec4Ad 用自然推荐样本作为 “free lunch” 缓解广告 CTR 的 sample selection bias：广告曝光由广告系统选择，自然推荐曝光由推荐系统选择，但共享用户决策机制；通过表示对齐和解耦提升 Taobao display ads CTR/RPM。 |
| 2023 | [COPR: Consistency-Oriented Pre-Ranking for Online Advertising](https://arxiv.org/abs/2306.03516) | CIKM | Pre-ranking, rank consistency, online ads | COPR 直接处理广告级联系统中粗排和精排排序结果不一致的问题：不用只对齐 raw score，而是显式优化 ECPM rank consistency；论文报告在 Taobao display advertising 上线带来 CTR 和 RPM 提升。 |
| 2023 | [Multi-Scenario Ranking with Adaptive Feature Learning](https://arxiv.org/abs/2306.16732) | SIGIR | CTR/ranking, multi-scenario, feature adaptation | Maria 针对多场景广告预估中“场景特征重要性不同”的问题，用 scenario-aware adaptive feature learning 自适应强化不同场景下的关键特征，并在 Alibaba search advertising 做了线上验证。 |
| 2023 | [Hybrid Contrastive Constraints for Multi-Scenario Ad Ranking](https://arxiv.org/abs/2302.02636) | CIKM | CTR/ranking, multi-scenario, contrastive learning | HC^2 用 hybrid contrastive constraints 同时约束 scenario 内和 scenario 间表征，使多场景广告排序既能共享共性，也能保留场景差异。 |
| 2023 | [Entire Space Cascade Delayed Feedback Modeling for Effective Conversion Rate Prediction](https://arxiv.org/abs/2308.04768) | CIKM | Effective CVR, refund-aware ranking, delayed feedback | ECAD 把 CVR 扩展到 ECVR：购买后可能退款，因此需要同时建模 conversion 和 refund rate，并处理 conversion/refund 两段级联延迟反馈。 |
| 2023 | [Multi-channel Integrated Recommendation with Exposure Constraints](https://arxiv.org/abs/2305.12319) | KDD | Feed ranking, exposure constraints | MIREC 把淘宝首页多频道内容混排建模成带曝光约束的在线分配和排序问题，从 user-item 扩展到 user-channel-item，并在全局曝光控制与单次请求布局之间做两层优化。 |
| 2023 | [Multi-factor Sequential Re-ranking with Perception-Aware Diversification](https://arxiv.org/abs/2305.12420) | KDD | List reranking, diversity | MPAD 是淘宝首页 feed 的序列重排工作：在用户连续浏览的上下文里同时考虑准确性和感知多样性，逐步选择下一件商品，而不是只按单 item 分数排序。 |
| 2024 | [Calibration-compatible Listwise Distillation of Privileged Features for CTR Prediction](https://arxiv.org/abs/2312.08727) | WSDM | CTR, listwise distillation, calibration | CLID 延续 JRC 的 ranking-calibration 问题，但放在 privileged feature distillation 场景：teacher 离线可见更多特征，student 在线不可见；它用 calibration-compatible listwise loss 蒸馏排序能力，同时保住 CTR 概率校准。 |
| 2024 | [Deep Evolutional Instant Interest Network for CTR Prediction in Trigger-Induced Recommendation](https://arxiv.org/abs/2401.07769) | WSDM | CTR, trigger-induced recommendation | DEI2N 面向 Alibaba.com 等 trigger-induced recommendation 场景，把 trigger item、target item、时间信息和用户滚动时即时兴趣强度变化一起建模。 |
| 2024 | [Enhancing Pre-Ranking Performance: Tackling Intermediary Challenges in Multi-Stage Cascading Recommendation Systems](https://doi.org/10.1145/3637528.3671580) | KDD | Pre-ranking, cascade systems | Ant Group 的 pre-ranking 工作，聚焦召回、粗排、精排级联系统中的中间层难题：训练样本来自曝光/精排反馈，但线上粗排要面对更大的 recall space，因此需要处理 sample selection bias 和跨阶段一致性。 |
| 2024 | [Text Matching Indexers in Taobao Search](https://dblp.org/rec/conf/kdd/LiL0OZR24.html) | KDD | Taobao search, retrieval-to-ranking | 这篇更靠近 retrieval/indexing，但和排序上界强相关：SMIND 结合用户搜索偏好的倒排索引剪枝与多粒度语义索引，为淘宝搜索后续 pre-rank/rank/rerank 提供更高质量候选。 |
| 2024 | [Mitigate Position Bias with Coupled Ranking Bias on CTR Prediction](https://arxiv.org/abs/2405.18971) | arXiv | CTR, position bias | Ant Group 论文，指出位置偏差估计会被 ranking bias 耦合污染：高分 item 本来就更容易被排在前面，因此 top position 的高 CTR 不全是 examination effect；提出 gradient interpolation 做偏差缓解。 |
| 2024 | [Enhancing Taobao Display Advertising with Multimodal Representations: Challenges, Approaches and Insights](https://arxiv.org/abs/2407.19467) | CIKM | CTR, multimodal representation | 这篇回答工业 CTR 里“多模态特征怎么真正接进线上 ID 模型”的问题：先预训练商品多模态表征，再和现有 ID-based CTR 模型集成，并说明 Taobao display ads 的实时特征生成与线上部署架构。 |
| 2024 | [UID-Net: Enhancing Click-Through Rate Prediction in Trigger-Induced Recommendation Through User Interest Decomposition](https://dblp.org/rec/conf/adma/LouLWLZLCW24.html) | ADMA | CTR, trigger-induced recommendation | UID-Net 延续 TIR 方向，把用户兴趣拆成 trigger-relevant 和 trigger-irrelevant 两部分，并用对比学习增强区分，再自适应融合做 CTR 预测。 |
| 2025 | [PRECTR: A Synergistic Framework for Integrating Personalized Search Relevance Matching and CTR Prediction](https://arxiv.org/abs/2503.18395) | WWW | Search ranking, CTR/relevance fusion | PRECTR 将搜索相关性匹配和 CTR 预测放到统一框架里，避免两个模型分开训练后靠规则融合导致的不一致；同时建模用户对“相关性”的个性化敏感度。 |
| 2025 | [A Generative Re-ranking Model for List-level Multi-objective Optimization at Taobao](https://arxiv.org/abs/2505.07197) | SIGIR / arXiv | Generative reranking, multi-objective | SORT-Gen 是非常贴近 slate/list optimization 的新工作：用 Transformer + ordered regression 估计变长子列表的点击、转化、GMV 等多目标价值，再用快速生成算法产出线上列表。 |
| 2025 | [AliBoost: Ecological Boosting Framework in Alibaba Platform](https://arxiv.org/abs/2506.00954) | KDD / arXiv | Ecosystem-aware ranking, cold items | AliBoost 从平台生态角度补足“只面向用户即时偏好”的自然推荐，用分层 boosting 和 item-oriented bidding boosting 给高潜冷启动商品合理曝光，同时控制对用户体验的扰动。 |
| 2025 | [User Long-Term Multi-Interest Retrieval Model for Recommendation](https://arxiv.org/abs/2507.10097) | arXiv | Long-behavior retrieval, multi-interest recommendation | ULIM 虽然偏 retrieval，但来自 Taobao/Tmall Group 且直接服务后续推荐排序：把千级用户行为按 category-aware 子序列拆成多兴趣，再用 category-to-item 级联检索提升 Taobaomiaosha 点击、订单和 GMV。 |
| 2025 | [See Beyond a Single View: Multi-Attribution Learning Leads to Better Conversion Rate Prediction](https://arxiv.org/abs/2508.15217) | CIKM / arXiv | CVR, multi-attribution learning | MAL 指出 CVR label 本身受 attribution mechanism 影响：只用 Last-Click 或单一归因会丢掉其他触点信号，因此用多归因视角联合学习更稳定的转化意图。 |
| 2025 | [Bid2X: Revealing Dynamics of Bidding Environment in Online Advertising from A Foundation Model Lens](https://arxiv.org/abs/2510.23410) | KDD | Online advertising, bidding foundation model | Bid2X 不直接做 CTR scorer，但和阿里广告排序/竞价生态相邻：用 foundation model 统一建模不同 bidding scenario 下 bid 到预算消耗、GMV、PV 等效果的映射，服务自动出价环境理解。 |
| 2025 | [Bursting Filter Bubble: Enhancing Serendipity Recommendations with Aligned Large Language Models](https://arxiv.org/abs/2502.13539) | KDD | Serendipity recommendation, LLM alignment | SERAL 面向 Taobao App 首页 “Guess What You Like” 的 filter bubble 问题：用用户认知画像压缩长行为，再对齐 LLM 的 serendipity 判断，并通过 nearline adaptation 接入工业推荐链路。 |
| 2025 | [MOON Embedding: Multimodal Representation Learning for E-commerce Search Advertising](https://arxiv.org/abs/2511.11305) | arXiv | CTR, multimodal representation | MOON 是阿里妈妈搜索广告团队的多模态表征学习工作，已全面部署在淘宝搜索广告系统的召回、相关性和排序链路；通过多模态表征直接驱动 CTR 预估，论文报告线上 CTR 提升约 20%。 |
| 2025 | [RAIR: A Rule-Aware Benchmark Uniting Challenging Long-Tail and Visual Salience Subset for E-commerce Relevance Assessment](https://arxiv.org/abs/2512.24943) | arXiv | Search relevance benchmark, multimodal, LLM/VLM | RAIR 是 Taobao & Tmall Group 发布的中文电商搜索相关性 benchmark，含通用、长尾难例和视觉显著性三个子集，用于评测 LLM/VLM（含 GPT-5）在 query-商品相关性判断上的能力，服务多模态相关性/排序研究。 |
| 2025 | [Equip Pre-ranking with Target Attention by Residual Quantization](https://arxiv.org/abs/2509.16931) | arXiv | Pre-ranking, target attention, cascade consistency | TARQ 用残差量化把 target attention 引入延迟敏感的粗排阶段，让粗排打分器也能用上精排式的目标感知交互，从而提升粗精排一致性；来自淘宝团队并已在服务数千万 DAU 的生产系统部署。 |
| 2025 | [Bidding-Aware Retrieval for Multi-Stage Consistency in Online Advertising](https://arxiv.org/abs/2508.05206) | arXiv | Retrieval-to-ranking, cascade consistency, online ads | BAR 针对召回与排序级联不一致问题，把出价信号通过单调性约束学习和多任务蒸馏注入检索阶段，让召回结果更贴近下游 ECPM 排序；来自阿里妈妈展示广告并已在阿里广告平台部署。 |
| 2025 | [ChoirRec: Semantic User Grouping via LLMs for Conversion Rate Prediction of Low-Activity Users](https://arxiv.org/abs/2510.09393) | arXiv | CVR, LLM-based user grouping, low-activity users | ChoirRec 用 LLM 做语义化用户分组，借助高活用户群体信息缓解低活用户行为稀疏导致的 CVR 预估困难；来自 Alibaba 并已在淘宝部署。 |
| 2025 | [TranSUN: A Preemptive Paradigm to Eradicate Retransformation Bias Intrinsically from Regression Models in Recommender Systems](https://arxiv.org/abs/2505.13881) | NeurIPS | Regression debiasing, ranking calibration | TranSUN 从根源上消除回归类排序模型（如 GMV/时长预估）训练时对数变换带来的 retransformation bias，是一种预防式范式；已在淘宝首页"猜你喜欢"的商品与短视频推荐排序中部署。 |
| 2025 | [MUSE: A Simple Yet Effective Multimodal Search-Based Framework for Lifelong User Interest Modeling](https://arxiv.org/abs/2512.07216) | arXiv | CTR, long sequence, multimodal search-based | MUSE 把 SIM 式 GSU/ESU 检索范式扩展到 10 万级多模态长行为序列，用 SimTier 和语义感知 target attention 从超长历史里检索相关兴趣证据；来自阿里妈妈展示广告并已在淘宝展示广告系统部署。 |
| 2025 | [MIM: Multi-modal Content Interest Modeling Paradigm for User Behavior Modeling](https://arxiv.org/abs/2502.00321) | arXiv | CTR, multimodal content interest, user behavior | MIM 提出多模态内容兴趣建模范式，把多模态内容信号接进用户行为序列做 CTR 预估；作者包含阿里妈妈/淘宝研究者并已在淘宝部署。 |
| 2025 | [AIF: Asynchronous Inference Framework for Cost-Effective Pre-Ranking](https://arxiv.org/abs/2511.12934) | arXiv | Pre-ranking, serving efficiency, ad CTR | AIF 是 Taobao & Tmall Group 的粗排异步推理框架，通过解耦计算降低粗排成本；自 2023 年 10 月起在淘宝展示广告粗排阶段部署，报告 CTR +8.72%、RPM +5.80%。 |
| 2025 | [RecGPT Technical Report](https://arxiv.org/abs/2507.22879) | arXiv | LLM-enhanced recommendation, intent mining, retrieval | RecGPT 是 Taobao 团队的 LLM 增强推荐系统技术报告，覆盖用户意图挖掘、物品检索和解释生成；已在淘宝 App 部署，是 RecGPT-Mobile/V2 的主干工作。 |
| 2025 | [RecGPT-V2 Technical Report](https://arxiv.org/abs/2512.14503) | arXiv | LLM-enhanced ranking/recommendation | RecGPT-V2 延续 RecGPT 的 LLM 增强推荐/排序路线，并在淘宝首页"猜你喜欢"feed 做了 A/B；报告 CTR +2.98%、IPV +3.71%、TV +2.19%、NER +11.46% 等线上排序收益。 |
| 2025 | [Scaling Transformers for Discriminative Recommendation via Generative Pretraining](https://arxiv.org/abs/2506.03699) | KDD | CTR/CVR, scaling law, generative pretraining | 这篇用生成式预训练来 scale 判别式推荐的 Transformer，面向工业推荐排序阶段的 CTR/CVR 预估；来自 Alibaba 并在大规模电商平台做了线上 A/B，属于 scaling-law 排序方向。 |
| 2025 | [Large Language Model as Universal Retriever in Industrial-Scale Recommender System](https://arxiv.org/abs/2502.03041) | arXiv | LLM universal retrieval, multi-objective, online ads | URM 用 LLM 做统一的多目标、多场景（含搜索）生成式检索，直接影响广告排序/CTR 目标；来自 Taobao & Tmall Group 并在阿里广告平台 A/B，报告广告收入提升约 3%。 |
| 2025 | [TaoSR-AGRL: Adaptive Guided Reinforcement Learning Framework for E-commerce Search Relevance](https://arxiv.org/abs/2510.08048) | WWW | Search relevance, RL, LLM-enhanced | TaoSR-AGRL 用自适应引导式强化学习框架做 LLM 增强的电商搜索相关性与排序；来自淘宝并已部署，属于阿里体系近期 LLM 化搜索/排序方向。 |
| 2025 | [LLM-Auction: Generative Auction towards LLM-Native Advertising](https://arxiv.org/abs/2512.10551) | arXiv | Generative auction, ad allocation, LLM-native ads | LLM-Auction 提出面向 LLM 原生广告的学习型生成式拍卖机制，用 Iterative Reward-Preference Optimization 在广告主价值与用户体验间做生成式广告分配；来自 Taobao & Tmall Group，使用真实淘宝广告。 |
| 2025 | [Reinforced Preference Optimization for Recommendation](https://arxiv.org/abs/2510.12211) | arXiv | Generative recommendation, RL preference optimization | 这篇用强化学习（RLVR/GRPO）优化 LLM 生成式推荐的排序偏好；来自 Taobao & Tmall Group 与 NUS，属于 LLM 化排序与偏好优化方向。 |
| 2026 | [Modeling Cascaded Delay Feedback for Online Net Conversion Rate Prediction: Benchmark, Insights and Solutions](https://arxiv.org/abs/2601.19965) | WWW | NetCVR, delayed feedback, refund-aware ranking | TESLA/CASCADE 把 CVR 扩展到 NetCVR：点击后购买有延迟，购买后退款也有延迟，而且两段延迟方向相反；论文给出 Taobao App 的 CASCADE 数据集、级联 CVR/refund-rate 建模、stage-wise debiasing 和 delay-time-aware ranking loss。 |
| 2026 | [Delayed Feedback Modeling for Post-Click Gross Merchandise Volume Prediction: Benchmark, Insights and Approaches](https://arxiv.org/abs/2601.20307) | WWW | Post-click GMV, delayed feedback | READER/TRACE 是 TESLA 的姊妹线：目标从概率型 CVR 变成连续型 post-click GMV，并处理一次点击后多次购买、label 未完全到达时的 under-estimation 和 repurchase 分布差异。 |
| 2026 | [MAC: A Conversion Rate Prediction Benchmark Featuring Labels Under Multiple Attribution Mechanisms](https://arxiv.org/abs/2603.02184) | arXiv | CVR, multi-attribution benchmark, PyMAL | MAC 是 MAL 方向的公开 benchmark：从 Taobao advertising 系统抽取多归因标签数据，并发布 PyMAL baseline library；论文还提出 MoAE，用 asymmetric experts 更充分地学习和迁移多归因知识。 |
| 2026 | [Unlocking Scaling Law in Industrial Recommendation Systems with a Three-step Paradigm based Large User Model](https://arxiv.org/abs/2502.08309) | WSDM | Industrial recommendation, large user model | LUM 不是传统 CTR 小模型，而是阿里体系把 scaling law 引入工业推荐的一条线：用三阶段范式保留 DLRM 的工业特征/架构优势，同时扩到 billion-parameter user model 并做线上 A/B。 |
| 2026 | [PRECTR-V2: Unified Relevance-CTR Framework with Cross-User Preference Mining, Exposure Bias Correction, and LLM-Distilled Encoder Optimization](https://arxiv.org/abs/2602.20676) | arXiv | Search ranking, LLM-distilled CTR/relevance | PRECTR-V2 继续强化 relevance-CTR 统一建模：补低活用户的跨用户相关性偏好、构造 hard negatives 修正曝光偏差，并用 LLM 蒸馏轻量文本 encoder 以适配 CTR fine-tuning。 |
| 2026 | [EST: Towards Efficient Scaling Laws in Click-Through Rate Prediction via Unified Modeling](https://arxiv.org/abs/2602.10811) | arXiv | CTR, efficient scaling laws, unified modeling | EST 是 Taobao display ads 的 Efficiently Scalable Transformer：不再先把行为早聚合掉，而是把非行为特征、用户行为、候选相关行为和内容信号组织成统一 token 序列；用 Lightweight Cross-Attention 和 Content Sparse Attention 降低长序列计算冗余，并展示 CTR/RPM 线上收益。 |
| 2026 | [LoopCTR: Unlocking the Loop Scaling Power for Click-Through Rate Prediction](https://arxiv.org/abs/2604.19550) | arXiv | CTR, loop scaling, efficient inference | LoopCTR 是另一条 CTR scaling 路线：不靠简单堆参数，而是在训练时循环复用共享层增加 compute，用 process supervision 把多 loop 收益压进共享参数，最后用 train-multi-loop / infer-zero-loop 保持线上推理成本。 |
| 2026 | [KARMA: Knowledge-Action Regularized Multimodal Alignment for Personalized Search at Taobao](https://arxiv.org/abs/2603.22779) | arXiv | Personalized search, LLM/multimodal alignment | KARMA 关注 Taobao 个性化搜索里的 Knowledge-Action Gap：直接用行为目标 fine-tune LLM 会损伤语义泛化，因此用语义重建作为 train-only regularizer，让 next-interest embedding 同时服务 recall/pre-rank/rank 并保持 semantic decodability。 |
| 2026 | [RecGPT-Mobile: On-Device Large Language Models for User Intent Understanding in Taobao Feed Recommendation](https://arxiv.org/abs/2605.04726) | arXiv | Feed recommendation, on-device LLM, intent understanding | RecGPT-Mobile 把轻量 LLM 部署到移动端做用户实时意图理解/next-query prediction，让 feed 推荐能更快响应用户近期行为变化；它更像下一代 ranking feature / intent layer，而不是传统 CTR scorer。 |
| 2026 | [DSIRM: Learning Query-Bridged Discrete Semantic Identifiers for E-commerce Relevance Modeling](https://arxiv.org/abs/2606.04374) | arXiv | Search relevance, semantic ID, LLM-enhanced | DSIRM 把 query 作为桥梁学习离散语义 ID，用 LLM 增强电商搜索相关性建模，直接服务于 Tmall 搜索的排序和 CTR/CVR 目标；来自 Taobao & Tmall Group 并已在天猫部署。 |
| 2026 | [LEAPS: An LLM-Empowered Adaptive Plugin in Taobao AI Search](https://arxiv.org/abs/2601.05513) | arXiv | Search query understanding, relevance, LLM-enhanced | LEAPS 是 Taobao & Tmall Group 的 LLM 自适应插件，用 Query Expander 做查询理解扩展、用 Relevance Verifier 做相关性排序/过滤；自 2025 年 8 月起全面部署在淘宝 AI 搜索。 |
| 2026 | [SIGMA: A Semantic-Grounded Instruction-Driven Generative Multi-Task Recommender at AliExpress](https://arxiv.org/abs/2602.22913) | SIGIR Industry | Generative multi-task recommendation, LLM-enhanced | SIGMA 是 AliExpress 部署的语义接地、指令驱动的生成式多任务推荐器，用 LLM 增强统一建模多个排序/推荐目标；属于阿里体系近期 LLM 化排序方向。 |
| 2026 | [RankGR: Rank-Enhanced Generative Retrieval with Listwise Direct Preference Optimization in Recommendation](https://arxiv.org/abs/2602.08575) | arXiv | Generative retrieval, listwise LTR, recommendation | RankGR 给生成式检索补上 listwise LTR 目标（LDPO）和精排打分阶段，让生成召回直接对齐排序质量；来自浙江大学与 Alibaba 并在淘宝部署。 |
| 2026 | [Efficient Generative Retrieval for E-commerce Search with Semantic Cluster IDs and Expert-Guided RL](https://arxiv.org/abs/2605.14434) | arXiv | Generative retrieval, ranking-aligned RL, search | 这篇用语义聚类 ID 和专家引导强化学习（EG-GRPO）做高效生成式检索，并加入排序对齐的精炼训练阶段，让召回直接服务下游排序目标；部署于天猫，生成式召回贡献超 50% 曝光，报告 GMV/CVR 线上提升。 |
| 2026 | [Query-Mixed Interest Extraction and Heterogeneous Interaction: A Scalable CTR Model for Industrial Recommender Systems](https://arxiv.org/abs/2602.09387) | arXiv | CTR, multi-interest, scaling law | HeMix 用 Query-Mixed Interest Extraction 在全局与实时行为序列上做自适应序列 token 化，再配 HeteroMixer 交互模块，并强调排序模型的 scaling-law 行为；部署于阿里全资子公司高德（AMAP），报告 GMV/CTR/CVR 线上提升。 |
| 2026 | [Generative Auto-Bidding with Unified Modeling and Exploration](https://arxiv.org/abs/2605.19457) | SIGIR | Auto-bidding, generative modeling, online ads | GUIDE 是 Taobao & Tmall Group 的生成式自动出价框架，统一建模并加入探索机制做广告投放优化；已在淘宝广告平台线上部署，属于阿里广告竞价/优化相邻方向。 |
| 2026 | [NEZHA: A Zero-sacrifice and Hyperspeed Decoding Architecture for Generative Recommendations](https://arxiv.org/abs/2511.18793) | WWW | Generative recommendation, decoding efficiency, ad CTR | NEZHA 用类似 speculative decoding 的架构在不损效果的前提下加速 LLM 生成式推荐的解码；自 2025 年 10 月起部署在淘宝搜索广告的候选生成阶段，直接服务广告排序/CTR 链路。 |
| 2026 | [Bridging Sequential and Contextual Features with a Dual-View of Fine-grained Core-Behaviors and Global Interest-Distribution](https://arxiv.org/abs/2603.12578) | arXiv | CTR, long sequence, sequential-contextual fusion | 这篇用细粒度核心行为和全局兴趣分布的双视角，把长用户行为序列与上下文特征桥接起来做 CTR 预估；来自 Alibaba 并在大规模电商平台经线上 A/B 验证。 |
| 2026 | [AIGQ: An End-to-End Hybrid Generative Architecture for E-commerce Query Recommendation](https://arxiv.org/abs/2603.19710) | arXiv | Generative query recommendation, search, LLM-enhanced | AIGQ 是端到端混合生成式架构，做电商搜索前的 query 推荐；部署于淘宝 HintQ 场景，来自 Taobao & Tmall Group，属于 LLM 化搜索/生成式推荐方向。 |
| 2026 | [A Long-term Value Prediction Framework In Video Ranking](https://arxiv.org/abs/2602.17058) | WWW | LTV, multi-objective ranking, post-click | 这篇做视频排序里的长期价值（LTV）建模，含多目标与点击后归因组件；来自淘宝并已部署在淘宝排序系统，直接对应排序阶段的 LTV / 多目标 LTR / 后链路目标。 |
| 2026 | [AliBoostV2: CTR-Growth Balanced Boosting Framework in Billion-Scale Recommendation Platform](https://dl.acm.org/doi/10.1145/3774904.3792800) | WWW | Multi-objective controllable ranking, cold items | AliBoostV2 延续 AliBoost 的生态加权排序，在十亿级推荐平台上做 CTR 与增长（冷启动商品后链路 GMV/growth）平衡的可控 boosting；来自淘宝并已部署。 |

## Main Threads

### 1. User Interest Modeling: DIN -> DIEN -> DSIN/BST -> MIMN -> SIM -> ETA-Net

Alibaba CTR 论文最清晰的一条主线是用户行为序列建模。DIN 解决“同一个用户对不同 target 的兴趣不同”，DIEN 解决“行为背后有 latent interest 且会演化”，DSIN/BST 分别引入 session 结构和 Transformer 序列建模。到 MIMN、SIM、ETA-Net，问题从“如何表达兴趣”变成了“如何在毫秒级线上系统里从几千到几万条行为中找到与当前 target 有关的兴趣证据”。

对 ranking/slate survey 来说，这条线的启发是：最终排序分数并不是 pointwise 地看用户和单个 item，而是在候选 target 的条件下，从用户历史、上下文、session 和长期记忆里动态构造证据。

### 2. Feature Interaction and Adaptation: CAN, STAR, AdaSparse/HC^2/Maria, APG

CAN、STAR、AdaSparse、HC^2、Maria、APG 都在回答一个工业 CTR 的现实问题：模型容量要放在哪里。CAN 说很多有价值的信息在显式 feature co-action 里；STAR/AdaSparse 处理多域共享和差异化稀疏结构；HC^2/Maria 进一步面向多场景广告排序，让场景内、场景间表征和特征重要性自适应；APG 说同一个网络的参数可以根据样本动态生成。它们都不是单纯追求更深的网络，而是在稀疏特征、场景分布和线上成本之间找更可控的表达方式。

### 3. CVR and Post-click Objectives: ESMM -> Delayed Feedback -> HDR/ECAD -> TESLA

电商排序不只看 CTR。ESMM 把 CVR 放回整个 impression space 里建模，避免只看点击样本导致的偏差；DEFER/DEFUSE 等 delayed feedback 工作处理“转化需要时间发生”的标签问题；HDR 关注大促期间 CVR 分布突变，ECAD 把退款后的有效转化也纳入目标；TESLA/CASCADE 进一步把购买和退款的级联延迟做成 NetCVR benchmark。它们提醒我们，排序目标如果包含购买、GMV、退款后有效转化等指标，就必须处理样本空间、时间延迟、级联反馈和多任务依赖。

### 4. Ranking and Whole-page Optimization

CLOES、RL to Rank、Dynamic Ad Allocation、DC-LTR、COPR 共同说明 Alibaba 的排序系统不只是在训练一个 CTR scorer。真实系统还要考虑级联召回/排序效率、粗排和精排一致性、session-level reward、页面广告位数量、业务约束、大促期间目标切换等问题。这些论文和 slate recommendation 的关系很近，因为它们的优化对象已经从单个 item 扩展到 page、session 或多目标排序策略。

### 5. Recent Ranking, Calibration, and Reranking: JRC -> MIREC/MPAD -> SORT-Gen/PRECTR

2023 年之后的 Alibaba/Ant 工作明显从“CTR 估准一点”继续往“排序目标本身怎么定义”推进。JRC 关注 ranking ability 和 calibration ability 的统一；COPR 关注粗排结果如何和精排 ECPM 排序保持一致；CLID 把 calibration-compatible listwise signal 推进到 privileged feature distillation；MIREC、MPAD 把淘宝首页 feed 里的频道曝光、连续浏览和多样性放进排序/重排目标；SORT-Gen 则直接做 list-level multi-objective generative reranking；PRECTR 系列把搜索相关性和 CTR 从后融合推进到统一建模。对 slate survey 来说，这些比早期 DIN/DIEN 更像真正的列表优化论文。

### 6. Multimodal, Scaling, and LLM Directions: Taobao Ads -> EST -> LUM -> KARMA/RecGPT-Mobile

2024 之后还有一条明显的新方向：ranking/CTR 模型开始把“ID 表征之外的信息”“统一 token 化建模”和“更大规模 user model”接进工业系统。Taobao 多模态广告 CTR 论文说明 multimodal representation 不是简单把图片/text embedding 拼进去，而是要配套预训练任务、在线特征生成、实时同步和 serving 架构；EST 则进一步追问 CTR 模型怎样像 LLM 一样可预测地 scale，同时又不能被长行为序列的计算量拖垮；LoopCTR 从参数复用和训练时计算扩展角度补上另一种高效 scaling；LUM 代表阿里体系尝试把 scaling law 迁移到工业推荐的大用户模型；KARMA 和 RecGPT-Mobile 则是 Taobao & Tmall Group 把 LLM 语义能力接到搜索/Feed 推荐中的近期例子。

## Alimama Tech Source Trail

`阿里妈妈技术` 公众号和年刊是追踪展示广告 Rank 团队论文的关键入口。后续更新建议先搜这些关键词，再回到 arXiv/ACM/DBLP 校正式题名、作者和 venue：

- `阿里妈妈展示RANK 团队`
- `阿里妈妈展示广告Rank团队`
- `阿里妈妈展示广告Ranking团队`
- `阿里妈妈技术 预估模型`
- `阿里妈妈技术 年刊 展示广告 预估`

已用到的公众号/年刊线索：

| Source | Useful clues | Papers / topics pulled back into this README |
| --- | --- | --- |
| [2023 阿里妈妈技术年刊目录](https://www.168i.cn/soft/show.asp?id=326165) | 预估模型章节集中列出展示 Rank 方向文章 | JRC, HDR, Maria, HC^2, AdaSparse, Bayesian live-score calibration |
| [2023 阿里妈妈技术年刊发布页](https://hub.baai.ac.cn/view/34904) | 官方说明这些内容来自 `阿里妈妈技术` 公众号年度沉淀 | 用作公众号来源确认，并反查 2023 展示广告预估模型线 |
| [2024 阿里妈妈技术年刊目录](https://www.fxbaogao.com/detail/4681173) | 召回/预估模型章节列出 CIKM'24 多模态预估、WSDM'24 优势特征实践 | Taobao multimodal display ads, 以及后续 multimodal CTR / ranking 线索 |
| [2024 阿里妈妈技术年刊发布页](https://hub.baai.ac.cn/view/42847) | 官方说明 2024 年刊由公众号文章汇编 | 用作 2024 展示广告预估模型来源确认 |
| [CIKM'25 MAL 公众号镜像](https://blog.csdn.net/alimama_Tech/article/details/151978865) | 阿里妈妈展示广告提出基于多归因学习的 CVR 预估范式 | MAL, attribution-aware CVR；顺着同一作者线可继续追到 MAC/PyMAL |
| [2025 阿里妈妈技术年刊发布页](https://hub.baai.ac.cn/view/52514) | 官方说明 2025 年刊已发布，需公众号回复 `2025年刊` 获取 | 后续继续补 2025 年展示广告 Rank / 预估模型文章时的入口 |

需要注意：公众号文章标题通常是中文技术解读，不一定直接暴露论文英文题名；实际收录到主表前，应再用高频作者、中文标题关键词和 paper acronym 反查英文论文。

## Author-expansion Notes

为了减少漏文，后续更新应优先从这些高频作者/团队反查，再按业务场景过滤：

- **Display ads / CTR / CVR**：Xiang-Rong Sheng, Zhangming Chan, Han Zhu, Jian Xu, Bo Zheng, Shuguang Han, Yuning Jiang, Hongbo Deng。
- **Taobao & Tmall feed/search/reranking**：Yue Meng, Cheng Guo, Yi Cao, Tong Liu, Qijie Shen, Dimin Wang, Hao Chen, Yuning Jiang, Bo Zheng。
- **广告竞价和生态**：Chuan Yu, Jian Xu, Bo Zheng, Qijie Shen。
- **公众号/年刊反查关键词**：`阿里妈妈展示RANK 团队`、`阿里妈妈展示广告Rank团队`、`预估模型`、`2023年刊`、`2024年刊`、`2025年刊`。

这条反查链能发现单纯搜 “Alibaba CTR” 容易漏掉的文章，例如 DEFER、DEFUSE、AdaSparse、HDR、COPR、Maria、HC^2、ECAD、KEEP、Rec4Ad、MAL/MAC、TRACE/READER、LoopCTR、ULIM 和 Bid2X。

## Suggested Reading Order

1. **CTR 入门主线**：DIN -> DIEN -> DSIN -> BST。
2. **长序列工业化主线**：MIMN/UIC -> SIM -> ETA-Net。
3. **特征/场景泛化主线**：CAN -> STAR -> AdaSparse -> HC^2 -> Maria -> APG。
4. **排序校准和粗精排一致性主线**：JRC -> COPR -> CLID -> CRB -> PRECTR -> PRECTR-V2。
5. **转化目标主线**：ESMM -> DEFER -> DEFUSE -> HDR -> ECAD -> MAL -> MAC/PyMAL -> TESLA/CASCADE -> READER/TRACE。
6. **排序和页面优化主线**：CLOES -> RL to Rank -> Dynamic Ad Allocation -> DC-LTR -> MIREC -> MPAD -> SERAL -> SORT-Gen。
7. **新模型能力主线**：KEEP -> Taobao multimodal display ads -> EST -> LoopCTR -> LUM -> KARMA -> RecGPT-Mobile。

## Notes for Slate Recommendation Survey

- Alibaba 的 CTR 工作大多仍是 pointwise prediction form，但它们越来越依赖 target-conditioned history retrieval、session structure、domain/scenario context 和 page/business constraints；这些都是 slate/list ranking 需要显式考虑的因素。
- 长序列兴趣建模可以和 slate reranking 结合：如果 reranker 知道整个候选列表，就可以从用户历史中为不同候选甚至候选组合检索不同证据。
- 多目标 LTR 和 CVR delayed feedback 对长期价值建模很重要；点击不是最终 reward，购买/GMV/留存/退款后有效转化都可能改变排序策略。
- 页面级广告/自然结果混排说明“展示多少个广告、放在哪些位置”本身就是 slate construction 问题，而不是 CTR scorer 之后的简单规则。
