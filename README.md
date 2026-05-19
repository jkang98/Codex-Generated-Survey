# Slate Recommendation Survey

A living reading list for recommendation settings where the system returns more
than one item at a time: a top-k slate, ranked list, bundle, playlist, grid,
carousel row, widget, shelf, module, or whole page.

This list intentionally excludes pure next-item sequential recommendation papers
unless the method explicitly optimizes or evaluates a whole list, slate, page, or
multi-list recommendation surface.

## Taxonomy

- **1D Lists & Rankings**: ordered top-k lists, listwise re-ranking, slate
  generation, set/list diversification, bandits, reinforcement learning, and
  off-policy evaluation over slates.
- **2D Grids or Carousel Interfaces & Multi-slate Pages**: recommendation
  surfaces with row/column position effects, multiple carousels, widgets,
  shelves, modules, or page-level layout optimization.
- **Adjacent but useful**: search, advertising, and learning-to-rank papers are
  included when their objective or feedback is about a multi-item or whole-page
  presentation rather than a single next item.

## Surveys and Background

| Year | Paper | Venue | Why it matters |
| --- | --- | --- | --- |
| 2023 | [Multi-list interfaces for recommender systems: survey and future directions](https://doi.org/10.3389/fdata.2023.1239705) | Frontiers in Big Data | The most directly relevant survey for carousel and multi-list recommender interfaces. |
| 2023 | [Deep Reinforcement Learning in Recommender Systems: A Survey and New Perspectives](https://doi.org/10.1016/j.knosys.2023.110335) | Knowledge-Based Systems | Broad RL-for-recommendation context, including long-term optimization beyond one-step prediction. |
| 2023 | [Impression-Aware Recommender Systems](https://arxiv.org/abs/2308.07857) | arXiv | Useful background for logged impressions/exposures, which are essential for slate and page-level evaluation. |

## 1D Lists & Rankings

### Direct Slate, List, and Set Optimization

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2018 | [Beyond Greedy Ranking: Slate Optimization via List-CVAE](https://arxiv.org/abs/1803.01682) | ICLR 2019 | Directly generates complete slates with a conditional VAE instead of greedily sorting item scores. |
| 2018 | [Seq2Slate: Re-ranking and Slate Optimization with RNNs](https://arxiv.org/abs/1810.02019) | arXiv / OpenReview | Uses a pointer-network style sequence model to choose a slate item by item while conditioning on previous choices. |
| 2021 | [Variation Control and Evaluation for Generative Slate Recommendations](https://arxiv.org/abs/2102.13302) | WWW | Shuchang Liu et al.; studies generative slate recommendation and adds variation metrics beyond accuracy for stochastic slate generators. |
| 2021 | [Conditional Sequential Slate Optimization](https://arxiv.org/abs/2108.05618) | SIGIR eCom | Re-ranks candidates into a slate while jointly optimizing ranking quality and composition constraints. |
| 2021 | [Combining Reward and Rank Signals for Slate Recommendation](https://arxiv.org/abs/2107.12455) | arXiv | Probabilistic slate model that uses both whether the slate received a reward and which rank was selected. |
| 2022 | [Dynamic Slate Recommendation with Gated Recurrent Units and Thompson Sampling](https://arxiv.org/abs/2104.15046) | Data Mining and Knowledge Discovery | Models slate exposure explicitly and introduces in-slate Thompson sampling for exploration. |
| 2023 | [Exploration and Regularization of the Latent Action Space in Recommendation](https://arxiv.org/abs/2302.03431) | WWW | Shuchang Liu et al.; decomposes list action generation into latent hyper-actions and item-list selection for RL-based recommendation. |
| 2023 | [Generative Slate Recommendation with Reinforcement Learning](https://arxiv.org/abs/2301.08632) | WSDM | Learns to generate slates with RL under the combinatorial action-space challenge. |
| 2023 | [Generative Flow Network for Listwise Recommendation](https://arxiv.org/abs/2306.02239) | KDD | Uses GFlowNets to generate diverse high-reward recommendation lists. |
| 2023 | [Slate-Aware Ranking for Recommendation](https://arxiv.org/abs/2302.12427) | WSDM | Brings slate-level relationships into the ranking stage before the final re-ranker. |
| 2024 | [Diffusion Model for Slate Recommendation](https://arxiv.org/abs/2408.06883) | arXiv | Models the joint distribution of items in a slate and supports multi-item user engagement. |
| 2024 | [Hierarchical Reinforcement Learning for Temporal Abstraction of Listwise Recommendation](https://arxiv.org/abs/2409.07416) | arXiv | Uses hierarchical RL to separate long-term perception from short-term list construction. |
| 2024 | [Learned Ranking Function: From Short-term Behavior Predictions to Long-term User Satisfaction](https://arxiv.org/abs/2408.06512) | RecSys | YouTube system that learns a ranking function for slate-level long-term satisfaction. |

### Re-ranking and Listwise Context Models

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2018 | [Learning a Deep Listwise Context Model for Ranking Refinement](https://arxiv.org/abs/1804.05936) | SIGIR | Uses local context among top-ranked results to refine the whole list. |
| 2019 | [Personalized Re-ranking for Recommendation](https://doi.org/10.1145/3298689.3347000) | RecSys | Transformer-style personalized re-ranking that models item interactions in the candidate list. |
| 2019 | [Learning Groupwise Multivariate Scoring Functions Using Deep Neural Networks](https://arxiv.org/abs/1811.04415) | ICTIR | Scores documents/items in groups to capture cross-item effects. |
| 2020 | [SetRank: Learning a Permutation-Invariant Ranking Model for Information Retrieval](https://arxiv.org/abs/1912.05891) | SIGIR | Set-based ranking model that captures cross-document interactions without depending on input order. |
| 2024 | [Utility-Oriented Reranking with Counterfactual Context](https://doi.org/10.1145/3671004) | ACM TKDD | Optimizes list utility by reasoning about the counterfactual context after re-ranking. |
| 2024 | [Beyond Positive History: Re-ranking with List-level Hybrid Feedback](https://arxiv.org/abs/2410.20778) | arXiv | Uses both positive and negative feedback from previously exposed lists for re-ranking. |

### Bandits, RL, and Off-policy Evaluation for Slates

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2014 | [Contextual Combinatorial Bandit and its Application on Diversified Online Recommendation](https://doi.org/10.1137/1.9781611973440.53) | SDM | Contextual bandit formulation for selecting a diversified set of recommendations. |
| 2017 | [Off-policy Evaluation for Slate Recommendation](https://papers.nips.cc/paper/6954-off-policy-evaluation-for-slate-recommendation) | NeurIPS | Practical counterfactual evaluation for ordered slates from logged data. |
| 2019 | [Top-K Off-Policy Correction for a REINFORCE Recommender System](https://arxiv.org/abs/1812.02353) | WSDM | Production YouTube top-k policy-gradient recommender with off-policy correction for multiple displayed items. |
| 2019 | [SlateQ: A Tractable Decomposition for Reinforcement Learning with Recommendation Sets](https://doi.org/10.24963/ijcai.2019/360) | IJCAI | Decomposes long-term value of a slate into item-level values under a user-choice model. |
| 2021 | [Top-K Contextual Bandits with Equity of Exposure](https://doi.org/10.1145/3460231.3474248) | RecSys | Top-k contextual bandits with exposure fairness constraints. |
| 2023 | [Combinatorial Categorized Bandits with Expert Rankings](https://www.microsoft.com/en-us/research/publication/combinatorial-categorized-bandits-with-expert-rankings/) | UAI | Aggregates expert/category rankings into a short top-k list under combinatorial bandit objectives. |
| 2024 | [Neural Combinatorial Clustered Bandits for Recommendation Systems](https://arxiv.org/abs/2410.14586) | arXiv | Neural contextual combinatorial bandit for recommending item subsets. |

### Kuaishou and Shuchang Liu: Request-level, Retention, and Long-term RL

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2023 | [Multi-Task Recommendations with Reinforcement Learning](https://arxiv.org/abs/2302.03328) | WWW | Kuaishou collaboration; uses an RL-enhanced multi-task framework to learn dynamic task-loss weights from session-wise interactions. |
| 2023 | [Reinforcing User Retention in a Billion Scale Short Video Recommender System](https://arxiv.org/abs/2302.01724) | WWW | Kuaishou system paper; formulates retention optimization as a request-based MDP and deploys RLUR in production. |
| 2023 | [State Regularized Policy Optimization on Data with Dynamics Shift](https://proceedings.neurips.cc/paper_files/paper/2023/hash/67dd6a41bf9539cffc0fc0165e4d0616-Abstract-Conference.html) | NeurIPS | Kuaishou/NTU RL paper for dynamics shift, motivated partly by time-varying recommender environments. |
| 2024 | [Sequential Recommendation for Optimizing Both Immediate Feedback and Long-term Retention](https://arxiv.org/abs/2404.03637) | SIGIR | Shuchang Liu et al.; decision-transformer approach for balancing immediate engagement with long-term retention. |
| 2024 | [Future Impact Decomposition in Request-level Recommendations](https://arxiv.org/abs/2401.16108) | KDD | Kuaishou system paper; decomposes request-level list rewards into item-wise future impact for long-term optimization. |
| 2024 | [Modeling User Retention through Generative Flow Networks](https://arxiv.org/abs/2406.06043) | KDD | Shuchang Liu et al.; propagates sparse retention rewards back to recommended items through a probabilistic flow. |
| 2025 | [Value Function Decomposition in Markov Recommendation Process](https://arxiv.org/abs/2501.17409) | WWW | Shuchang Liu et al.; decomposes temporal-difference learning to separate stochastic policy effects from user-environment randomness. |

### Diversity, Coverage, and Set Quality

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2005 | [Improving Recommendation Lists Through Topic Diversification](https://doi.org/10.1145/1060745.1060754) | WWW | Early work on diversifying the final recommendation list rather than optimizing items independently. |
| 2010 | [Understanding Choice Overload in Recommender Systems](https://doi.org/10.1145/1864708.1864724) | RecSys | Studies how list length and diversity affect satisfaction and decision difficulty. |
| 2012 | [Determinantal Point Processes for Machine Learning](https://arxiv.org/abs/1207.6083) | Foundations and Trends in ML | Core DPP reference used by many diverse slate/list recommenders. |
| 2018 | [Practical Diversified Recommendations on YouTube with Determinantal Point Processes](https://doi.org/10.1145/3269206.3272018) | CIKM | Production-scale DPP diversification for recommendation lists. |
| 2018 | [Fast Greedy MAP Inference for Determinantal Point Process to Improve Recommendation Diversity](https://arxiv.org/abs/1709.05135) | NeurIPS | Scalable DPP inference for diversified top-k recommendation. |
| 2019 | [Bandit Learning for Diversified Interactive Recommendation](https://arxiv.org/abs/1907.01647) | arXiv | Diversified contextual combinatorial bandit for interactive recommendation. |

## 2D Grids or Carousel Interfaces & Multi-slate Pages

### Whole-page and Page-level Optimization

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2014 | [Whole Page Optimization: How Page Elements Interact with the Position Auction](https://www.microsoft.com/en-us/research/publication/whole-page-optimization-how-page-elements-interact-with-the-position-auction/) | ACM EC | Search/ads paper showing that whole-page elements interact with ad clicks and revenue. |
| 2016 | [Beyond Ranking: Optimizing Whole-Page Presentation](https://doi.org/10.1145/2835776.2835824) | WSDM | Optimizes heterogeneous whole-page presentation rather than a single ranked list. |
| 2016 | [Whole-Page Optimization and Submodular Welfare Maximization with Online Bidders](https://doi.org/10.1145/2892563) | ACM TEAC | Whole-page ad allocation under slot and diversity constraints. |
| 2017 | [Efficient Ordered Combinatorial Semi-Bandits for Whole-Page Recommendation](https://doi.org/10.1609/aaai.v31i1.10939) | AAAI | Ordered combinatorial semi-bandit for selecting items and display positions on a page. |
| 2018 | [Deep Reinforcement Learning for Page-wise Recommendations](https://arxiv.org/abs/1805.02343) | RecSys | DeepPage jointly selects complementary items and a 2D page display strategy. |
| 2018 | [The Whole-Page Optimization via Dynamic Ad Allocation](https://doi.org/10.1145/3184558.3191584) | WWW Companion | Search/ads page optimization for deciding how many ads to show. |
| 2019 | [Whole Page Optimization with Global Constraints](https://doi.org/10.1145/3292500.3330675) | KDD | Amazon Video homepage widget ranking with relevance, diversity, and business constraints. |
| 2021 | [Toward User Engagement Optimization in 2D Presentation](https://doi.org/10.1145/3437963.3441749) | WSDM | Models position noticeability in grid-like 2D recommendation layouts. |
| 2021 | [Page-level Optimization of e-Commerce Item Recommendations](https://arxiv.org/abs/2108.05891) | RecSys | Optimizes item recommendation modules at page level in e-commerce. |
| 2022 | [Automate Page Layout Optimization: An Offline Deep Q-learning Approach](https://www.amazon.science/publications/automate-page-layout-optimization-an-offline-deep-q-learning-approach) | Amazon Science | Offline RL approach for page layout optimization. |
| 2023 | [A Bird's-eye View of Reranking: from List Level to Page Level](https://arxiv.org/abs/2211.09303) | WSDM | Page-level attentional re-ranking for multi-list recommendation pages. |
| 2024 | [Cooperative Multi-Agent Deep Reinforcement Learning in Content Ranking Optimization](https://arxiv.org/abs/2408.04251) | arXiv | Whole-page ranking with cooperative RL agents across positions. |
| 2025 | [Enhanced Whole Page Optimization via Mixed-Grained Reward Mechanism-Adapted Language Models](https://arxiv.org/abs/2506.09084) | arXiv | LLM-based whole-page optimization with mixed-grained rewards. |

### Carousel, Multi-list, Shelf, and Widget Interfaces

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2015 | [The Netflix Recommender System: Algorithms, Business Value, and Innovation](https://doi.org/10.1145/2843948) | ACM TMIS | Industrial system paper for a homepage composed of many personalized rows. |
| 2016 | [Using Navigation to Improve Recommendations in Real-Time](https://doi.org/10.1145/2959100.2959174) | RecSys | Uses navigation behavior to update recommendations in carousel-like production surfaces. |
| 2018 | [Explore, Exploit, and Explain: Personalizing Explainable Recommendations with Bandits](https://doi.org/10.1145/3240323.3240354) | RecSys | Spotify system for selecting explainable recommendation shelves with bandits. |
| 2020 | [Carousel Personalization in Music Streaming Apps with Contextual Bandits](https://doi.org/10.1145/3383313.3412217) | RecSys | Contextual bandits for ordering and personalizing carousels in music apps. |
| 2021 | [Automatic Collection Creation and Recommendation](https://doi.org/10.1145/3460231.3478865) | RecSys | Creates and recommends collections/carousels from user-item representations. |
| 2021 | [Optimizing the Selection of Recommendation Carousels with Quantum Computing](https://doi.org/10.1145/3460231.3478853) | RecSys | Formulates carousel selection as a combinatorial optimization problem. |
| 2021 | [Measuring the User Satisfaction in a Recommendation Interface with Multiple Carousels](https://doi.org/10.1145/3452918.3465493) | IMX | Studies satisfaction and evaluation for interfaces with multiple carousels. |
| 2022 | [Offline Evaluation of Recommender Systems in a User Interface With Multiple Carousels](https://doi.org/10.3389/fdata.2022.910030) | Frontiers in Big Data | Proposes 2D/carousel-aware offline evaluation such as N2DCG. |
| 2022 | [The Magic of Carousels: Single vs. Multi-List Recommender Systems](https://doi.org/10.1145/3511095.3531278) | HT | Formal and empirical analysis of why multi-list carousel interfaces can outperform single lists. |
| 2022 | [From Ranked Lists to Carousels: A Carousel Click Model](https://arxiv.org/abs/2209.13426) | arXiv | Click model for browsing behavior in carousel recommenders. |
| 2024 | [Towards Simulation-Based Evaluation of Recommender Systems with Carousel Interfaces](https://doi.org/10.1145/3643709) | ACM TORS | Simulates user interaction with carousel interfaces for evaluation. |
| 2025 | [Effective Diversification of Multi-Carousel Book Recommendation](https://arxiv.org/abs/2511.14461) | arXiv | Diversification methods and metrics across multiple book recommendation carousels. |

### Interface, User Study, and Grid/Carousel Behavior Papers

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2010 | [Eye-tracking Study of User Behavior in Recommender Interfaces](https://doi.org/10.1007/978-3-642-13470-8_35) | UMAP | Eye-tracking study of how users inspect recommendation interfaces. |
| 2010 | [The Effects of Recommendations' Presentation on Persuasion and Satisfaction in a Movie Recommender System](https://doi.org/10.1007/s00530-010-0190-0) | Multimedia Systems | Compares presentation choices for movie recommendation interfaces. |
| 2016 | [Personalizing User Interfaces for Improving Quality of Experience in VoD Recommender Systems](https://doi.org/10.1109/QoMEX.2016.7498940) | QoMEX | Personalizes VoD recommender UI presentation. |
| 2021 | [Controlling Personalized Recommendations in Two Dimensions with a Carousel-Based Interface](https://ceur-ws.org/Vol-2948/short3.pdf) | IntRS | Lets users control recommendation topics in a two-dimensional carousel interface. |
| 2021 | [Exploring Multi-List User Interfaces for Similar-Item Recommendations](https://doi.org/10.1145/3450613.3456809) | UMAP | User study comparing multi-list interfaces for similar-item recommendation. |
| 2021 | [Serving Each User: Supporting Different Eating Goals Through a Multi-List Recommender Interface](https://doi.org/10.1145/3460231.3474232) | RecSys | Multi-list food recommendation interface for different user goals. |
| 2022 | [Examining Choice Overload Across Single-List and Multi-List User Interfaces](https://ceur-ws.org/Vol-3177/paper10.pdf) | IntRS | Compares choice overload across list, grid, and carousel-style interfaces. |
| 2023 | [How Users Ride the Carousel: Exploring the Design of Multi-List Recommender Interfaces From a User Perspective](https://doi.org/10.1145/3604915.3610638) | RecSys | User study on carousel type, length, and design in multi-list interfaces. |
| 2023 | [Examining the User Evaluation of Multi-List Recommender Interfaces in the Context of Healthy Recipe Choices](https://doi.org/10.1145/3581930) | ACM TORS | User evaluation of multi-list recipe recommendation with personalized labels. |
| 2025 | [RecGaze: The First Eye Tracking and User Interaction Dataset for Carousel Interfaces](https://arxiv.org/abs/2504.20792) | arXiv | Eye-tracking and interaction dataset for carousel recommender interfaces. |
| 2025 | [Riding the Carousel: The First Extensive Eye Tracking Analysis of Browsing Behavior in Carousel Recommenders](https://arxiv.org/abs/2507.10135) | arXiv | Eye-tracking analysis of browsing behavior in carousel recommendation pages. |

## Explicitly Out of Scope

The following families are important for recommender systems, but are not the
focus of this survey unless they are extended to slate, list, page, or multi-list
outputs:

- Pure next-item sequential recommendation: GRU4Rec, Caser, SASRec, BERT4Rec,
  NextItNet, TiSASRec, etc.
- Pointwise CTR/CVR/rating prediction papers that only score one item at a time.
- Retrieval/candidate-generation papers where the final output is not optimized
  as a list, slate, grid, carousel, or page.

## Contribution Notes

Good additions usually include:

- The exact presentation unit: list, slate, set, grid, carousel, widget, shelf,
  page, bundle, playlist, etc.
- Whether the method is online, offline, logged-bandit, supervised, generative,
  reinforcement learning, or user-study based.
- Whether the paper models item-item, position, row-column, carousel-carousel,
  or page-level interactions.
- Links to paper, code, dataset, and BibTeX when available.
