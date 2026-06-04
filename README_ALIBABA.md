# Alibaba Ranking and CTR Papers

这是一份围绕 Alibaba 体系公开论文整理的 ranking / CTR 读书笔记。范围以
阿里妈妈、淘宝、天猫、AliExpress、Lazada 等生产系统中的排序、广告 CTR、
CVR、多目标 LTR、长序列兴趣建模和页面级优化为主；召回、匹配、图嵌入等
论文只有在它们直接影响排序或 CTR 建模时才作为背景提到。

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
|-- Feature, domain, and parameter adaptation
|   |-- CAN: explicit feature co-action
|   |-- STAR: one multi-domain CTR model for many ad domains
|   |-- APG: instance-wise adaptive parameter generation
|-- CVR, delayed feedback, and post-click objectives
|   |-- ESMM: entire-space multitask CVR estimation
|   |-- ESDF / delayed-feedback papers: false negatives and delayed conversion
|-- Ranking, LTR, and page optimization
|   |-- CLOES: cascade ranking for e-commerce search efficiency
|   |-- RL to Rank: search-session MDP for Taobao ranking
|   |-- Dynamic Ad Allocation: whole-page sponsored/organic allocation
|   |-- DC-LTR: online controllable multi-objective learning to rank
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
| 2022 | [APG: Adaptive Parameter Generation Network for Click-Through Rate Prediction](https://arxiv.org/abs/2203.16218) | NeurIPS | CTR, adaptive parameters | APG 让深度 CTR 模型的参数随 instance 动态生成，缓解静态参数难以覆盖不同用户/场景分布的问题，同时通过低秩化控制线上成本。 |
| 2022 | [Efficient Long Sequential User Data Modeling for Click-Through Rate Prediction](https://arxiv.org/abs/2209.12212) | DLP-KDD / arXiv | CTR, long-sequence retrieval | ETA-Net 把长行为检索和 CTR 模型端到端训练，用 hashing-based efficient target attention 降低标准 target attention 对长序列的线性成本。 |

## Main Threads

### 1. User Interest Modeling: DIN -> DIEN -> DSIN/BST -> MIMN -> SIM -> ETA-Net

Alibaba CTR 论文最清晰的一条主线是用户行为序列建模。DIN 解决“同一个用户对不同 target 的兴趣不同”，DIEN 解决“行为背后有 latent interest 且会演化”，DSIN/BST 分别引入 session 结构和 Transformer 序列建模。到 MIMN、SIM、ETA-Net，问题从“如何表达兴趣”变成了“如何在毫秒级线上系统里从几千到几万条行为中找到与当前 target 有关的兴趣证据”。

对 ranking/slate survey 来说，这条线的启发是：最终排序分数并不是 pointwise 地看用户和单个 item，而是在候选 target 的条件下，从用户历史、上下文、session 和长期记忆里动态构造证据。

### 2. Feature Interaction and Adaptation: CAN, STAR, APG

CAN、STAR、APG 都在回答一个工业 CTR 的现实问题：模型容量要放在哪里。CAN 说很多有价值的信息在显式 feature co-action 里；STAR 说多业务域不能简单混在一起也不能完全拆开训练；APG 说同一个网络的参数可以根据样本动态生成。它们都不是单纯追求更深的网络，而是在稀疏特征、场景分布和线上成本之间找更可控的表达方式。

### 3. CVR and Post-click Objectives: ESMM and Delayed Feedback

电商排序不只看 CTR。ESMM 把 CVR 放回整个 impression space 里建模，避免只看点击样本导致的偏差；Delayed Feedback 系列处理“转化需要时间发生”的标签问题。这些论文提醒我们，排序目标如果包含购买、GMV、退款后有效转化等指标，就必须处理样本空间、时间延迟和多任务依赖。

### 4. Ranking and Whole-page Optimization

CLOES、RL to Rank、Dynamic Ad Allocation、DC-LTR 共同说明 Alibaba 的排序系统不只是在训练一个 CTR scorer。真实系统还要考虑级联召回/排序效率、session-level reward、页面广告位数量、业务约束、大促期间目标切换等问题。这些论文和 slate recommendation 的关系很近，因为它们的优化对象已经从单个 item 扩展到 page、session 或多目标排序策略。

## Suggested Reading Order

1. **CTR 入门主线**：DIN -> DIEN -> DSIN -> BST。
2. **长序列工业化主线**：MIMN/UIC -> SIM -> ETA-Net。
3. **特征/场景泛化主线**：CAN -> STAR -> APG。
4. **转化目标主线**：ESMM -> delayed-feedback CVR papers。
5. **排序和页面优化主线**：CLOES -> RL to Rank -> Dynamic Ad Allocation -> DC-LTR。

## Notes for Slate Recommendation Survey

- Alibaba 的 CTR 工作大多仍是 pointwise prediction form，但它们越来越依赖 target-conditioned history retrieval、session structure、domain/scenario context 和 page/business constraints；这些都是 slate/list ranking 需要显式考虑的因素。
- 长序列兴趣建模可以和 slate reranking 结合：如果 reranker 知道整个候选列表，就可以从用户历史中为不同候选甚至候选组合检索不同证据。
- 多目标 LTR 和 CVR delayed feedback 对长期价值建模很重要；点击不是最终 reward，购买/GMV/留存/退款后有效转化都可能改变排序策略。
- 页面级广告/自然结果混排说明“展示多少个广告、放在哪些位置”本身就是 slate construction 问题，而不是 CTR scorer 之后的简单规则。

