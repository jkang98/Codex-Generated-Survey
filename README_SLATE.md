# Slate Recommendation Survey

A living reading list for recommendation settings where the system returns more
than one item at a time: a top-k slate, ranked list, bundle, playlist, grid,
carousel row, widget, shelf, module, or whole page.

This list intentionally excludes pure next-item sequential recommendation papers
unless the method explicitly optimizes or evaluates a whole list, slate, page, or
multi-list recommendation surface.

## Taxonomy

This survey is organized around two main research questions:

- **Slate Construction: what to recommend**: methods that construct the exposed
  multi-item object, including slates, ranked lists, diversified sets, bundles,
  carousels, widgets, shelves, grids, and whole pages.
- **Slate Feedback, Learning, and Evaluation: how to deal with user feedback**:
  methods that interpret what happened after exposure, including clicks, skips,
  position bias, browsing behavior, logged bandit feedback, counterfactual
  evaluation, simulators, and user studies.
- **Adjacent but useful**: search, advertising, and learning-to-rank papers are
  included when their objective or feedback is about a multi-item or whole-page
  presentation rather than a single next item.

## Layout Perspective Tree

This tree is a secondary index over the papers below. "Layout agnostic" does
not mean pointwise: these papers still optimize or evaluate the whole list,
set, or slate as a joint object, but they do not explicitly model visual UI
geometry. "Layout aware" means the paper explicitly reasons about presentation
structure such as grid position, carousel browsing, shelves, widgets, modules,
or whole-page layout. Some papers could fit more than one leaf; the tree places
each paper by its dominant layout assumption.

```text
Slate recommendation
|-- Layout agnostic
|   |-- Broad background and simulators
|   |   |-- Deep Reinforcement Learning in Recommender Systems: A Survey and New Perspectives
|   |   |-- KuaiSim: A Comprehensive Simulator for Recommender Systems
|   |   |-- LLM-as-a-Judge: Toward World Models for Slate Recommendation Systems
|   |   |-- The Diversity Paradox revisited: Systemic Effects of Feedback Loops in Recommender Systems
|   |   |-- Through Their Eyes: Fixation-aligned Tuning for Personalized User Emulation
|   |   |-- Exploring Recommender System Evaluation: A Multi-Modal User Agent Framework for A/B Testing
|   |   |-- Towards Faithful Simulation of Human Shopping Behavior
|   |   |-- Click Models for Web Search
|   |   |-- RecSim: A Configurable Simulation Platform for Recommender Systems
|   |   |-- RL4RS: A Real-World Dataset for Reinforcement Learning based Recommender System
|   |   |-- Neural Re-ranking in Multi-stage Recommender Systems: A Review
|   |-- Whole-list, slate, and set construction
|   |   |-- Beyond Greedy Ranking: Slate Optimization via List-CVAE
|   |   |-- Exact-K Recommendation via Maximal Clique Optimization
|   |   |-- Variation Control and Evaluation for Generative Slate Recommendations
|   |   |-- Conditional Sequential Slate Optimization
|   |   |-- Dynamic Slate Recommendation with Gated Recurrent Units and Thompson Sampling
|   |   |-- Exploration and Regularization of the Latent Action Space in Recommendation
|   |   |-- Generative Slate Recommendation with Reinforcement Learning
|   |   |-- Generative Flow Network for Listwise Recommendation
|   |   |-- Slate-Aware Ranking for Recommendation
|   |   |-- Multi-Task Recommendations with Reinforcement Learning
|   |   |-- Reinforcing User Retention in a Billion Scale Short Video Recommender System
|   |   |-- State Regularized Policy Optimization on Data with Dynamics Shift
|   |   |-- Learned Ranking Function: From Short-term Behavior Predictions to Long-term User Satisfaction
|   |   |-- Sequential Recommendation for Optimizing Both Immediate Feedback and Long-term Retention
|   |   |-- Future Impact Decomposition in Request-level Recommendations
|   |   |-- Modeling User Retention through Generative Flow Networks
|   |   |-- Value Function Decomposition in Markov Recommendation Process
|   |   |-- Seq2Slate: Re-ranking and Slate Optimization with RNNs
|   |   |-- Diffusion Model for Slate Recommendation
|   |   |-- Hierarchical Reinforcement Learning for Temporal Abstraction of Listwise Recommendation
|   |   |-- From Generation to Consumption: Personalized List Value Estimation for Re-ranking
|   |   |-- FlashEvaluator: Expanding Search Space with Parallel Evaluation
|   |   |-- Dual-Rerank: Fusing Causality and Utility for Industrial Generative Reranking
|   |   |-- From Local Indices to Global Identifiers: Generative Reranking for Recommender Systems via Global Action Space
|   |   |-- UniRank: Unified List-wise Reranking via Confidence-Ordered Denoising
|   |   |-- HiGR: Industrial-Scale Hierarchical Generative Slate Recommendation Framework in Tencent
|   |   |-- Next-Scale Generative Reranking: A Tree-based Generative Rerank Method at Meituan
|   |   |-- SCASRec: A Self-Correcting and Auto-Stopping Model for Generative Route List Recommendation
|   |   |-- Breaking the Likelihood Trap: Consistent Generative Recommendation with Graph-structured Model
|   |   |-- Don't Get Bored: Enhancing Scalability and Diversity in Session-Based Slate Recommendation
|   |   |-- Once Generated, Ranked: End-to-End Generative Slate Recommendation with Unified Semantic-Collaborative IDs
|   |   |-- Stochastic Primal-Dual Decoding for Multiobjective Generative Recommender Systems
|   |   |-- Large-Scale Online Learning for Generative List Recommendation in E-commerce: An Environment Policy Optimization Approach
|   |   |-- Fast Slate Policy Optimization: Going Beyond Plackett-Luce
|   |   |-- SlateFree: a Model-Free Decomposition for Reinforcement Learning with Slate Actions
|   |   |-- Sequential Multimodal Evidence Optimization for Product Media Ranking in E-Commerce
|   |   |-- A Reproducibility Study of Bundle Editing and Bundle Recommendation
|   |   |-- SAGE: Sequence-level Adaptive Gradient Evolution for Generative Recommendation
|   |   |-- LLMs as Orchestrators: Constraint-Compliant Multi-Agent Optimization for Recommendation Systems
|   |   |-- Rank-GRPO: Training LLM-based Conversational Recommender Systems with Reinforcement Learning
|   |   |-- Dual-Enhancement Product Bundling: Bridging Interactive Graph and Large Language Model
|   |   |-- A Language Model-Based Playlist Generation Recommender System
|   |   |-- Adaptive In-Context Learning with Large Language Models for Bundle Generation
|   |   |-- Routing Distilled Knowledge via Mixture of LoRA Experts for Large Language Model based Bundle Generation
|   |   |-- Decoupled Learning and Selection in Slate Recommendation for Privacy and Stability Under Noisy Scores
|   |   |-- Computationally Efficient Optimization of Plackett-Luce Ranking Models for Relevance and Fairness
|   |   |-- Personalized Bundle List Recommendation
|   |   |-- Generative Adversarial User Model for Reinforcement Learning Based Recommendation System
|   |   |-- Deep Reinforcement Learning for List-wise Recommendations
|   |   |-- Time-Constrained Recommendations: Reinforcement Learning Strategies for E-Commerce
|   |   |-- Melo: A Production LLM-Powered Music Recommendation Agent
|   |   |-- Automatic Music Playlist Generation via Simulation-based Reinforcement Learning
|   |   |-- Top-Personalized-K Recommendation
|   |-- Listwise reranking and large rankers
|   |   |-- Learning a Deep Listwise Context Model for Ranking Refinement
|   |   |-- Personalized Re-ranking for Recommendation
|   |   |-- Revisit Recommender System in the Permutation Prospective (PRS)
|   |   |-- GRN: Generative Rerank Network for Context-wise Recommendation
|   |   |-- PIER: Permutation-Level Interest-Based End-to-End Re-ranking
|   |   |-- Learning Groupwise Multivariate Scoring Functions Using Deep Neural Networks
|   |   |-- SetRank: Learning a Permutation-Invariant Ranking Model for Information Retrieval
|   |   |-- Utility-Oriented Reranking with Counterfactual Context
|   |   |-- Discrete Conditional Diffusion for Reranking in Recommendation
|   |   |-- Non-autoregressive Generative Models for Reranking Recommendation
|   |   |-- Comprehensive List Generation for Multi-Generator Reranking
|   |   |-- GoalRank: Group-Relative Optimization for a Large Ranking Model
|   |   |-- Denoising Neural Reranker for Recommender Systems
|   |   |-- Beyond Positive History: Re-ranking with List-level Hybrid Feedback
|   |   |-- One Pass, Any Order: Position-Invariant Listwise Reranking for LLM-Based Recommendation
|   |   |-- Beyond Static Best-of-N: Bayesian List-wise Alignment for LLM-based Recommendation
|   |   |-- Rich-Media Re-Ranker: A User Satisfaction-Driven LLM Re-ranking Framework for Rich-Media Search
|   |   |-- Whole-Pool Setwise Reranking with Long-Context Language Models
|   |   |-- A Generative Re-ranking Model for List-level Multi-objective Optimization at Taobao
|   |   |-- RIA: A Ranking-Infused Approach for Optimized Listwise CTR Prediction
|   |   |-- You Only Evaluate Once: A Tree-based Rerank Method at Meituan
|   |   |-- DeGRe: Dense-supervised Generative Reranking for Recommendation
|   |   |-- DEGR: Dual Exploration-Driven Generative Re-Ranking for Adaptive Cross-Request Context Bridging
|   |   |-- PSG: Pair-Space Generation for Efficient Generative Reranking
|   |   |-- SWIM: Step-Wise Integrated Measure for Session-supervised List Evaluation in Generative Re-ranking
|   |   |-- DIRECTOR: Dynamic Index-based Recommendation with Transport-Optimized Retrieval
|   |   |-- MetaStrategy: Generative Ranking with Executable LLM Strategies
|   |   |-- Fast and Feasible: Permutation-based Constrained Reranking for Revenue Maximization
|   |   |-- Position Bias Undermines Preference Consistency in Listwise LLM-Based Reranking
|   |   |-- Ranked by Position: Order Sensitivity as an Exploitable Attack Surface in LLM Listwise Recommenders
|   |   |-- Reasoning While Recommending: Entropy-Guided Latent Reasoning in Generative Re-ranking Models
|   |   |-- Efficient Personalized Reranking with Semi-Autoregressive Generation and Online Knowledge Distillation
|   |   |-- NLGR: Utilizing Neighbor Lists for Generative Rerank in Personalized Recommendation Systems
|   |   |-- GR2 Technical Report
|   |   |-- Diffusion-GR2: Diffusion Generative Reasoning Re-ranker
|   |   |-- hLLM: Single Pass Decoding for Generative Reranking
|   |   |-- PIANO: Personalized Reranking via Information Aggregation Node for Music Search Optimization
|   |   |-- Structure-aware Relative Policy Optimization for Ranking
|   |   |-- GReF: A Unified Generative Framework for Efficient Reranking via Ordered Multi-token Prediction
|   |   |-- LLM4Rerank: LLM-based Auto-Reranking Framework for Recommendations
|   |   |-- LLM-Enhanced Reranking for Complementary Product Recommendation
|   |   |-- A Multi-Objective Scoring Approach to Contract and Exposure-Aware Re-Ranking in Real-Estate Recommendation
|   |   |-- Learning from Emptiness: De-biasing Listwise Rerankers with Content-Agnostic Probability Calibration
|   |   |-- SR-Agent: An Experience-Driven Agentic Framework for Post-Ranking Strategy Refinement in E-Commerce Recommendation
|   |   |-- NGA: Non-autoregressive Generative Auction with Global Externalities for Advertising Systems
|   |   |-- Is ChatGPT Good at Search? Investigating Large Language Models as Re-Ranking Agents
|   |   |-- Large Language Models are Zero-Shot Rankers for Recommender Systems
|   |   |-- Found in the Middle: Permutation Self-Consistency Improves Listwise Ranking in Large Language Models
|   |   |-- Multi-Level Interaction Reranking with User Behavior History
|   |   |-- RankFormer: Listwise Learning-to-Rank Using Listwide Labels
|   |   |-- F-GRPO: Factorized Group-Relative Policy Optimization for Unified Candidate Generation and Ranking
|   |   |-- Towards Position-Robust Talent Recommendation via Large Language Models
|   |   |-- Controllable Multi-Objective Re-ranking with Policy Hypernetworks
|   |   |-- Evaluating Position Bias in Large Language Model Recommendations
|   |-- Diversity, coverage, and set quality
|   |   |-- Practical Diversified Recommendations on YouTube with Determinantal Point Processes
|   |   |-- Fast Greedy MAP Inference for Determinantal Point Process to Improve Recommendation Diversity
|   |   |-- Trading Engagement for Sustainability: Carbon-Aware Re-ranking for E-commerce Recommendations
|   |   |-- Adaptive Quality-Diversity Trade-offs for Large-Scale Batch Recommendation
|   |   |-- Diversity Recommendation via Causal Deconfounding of Co-purchase Relations and Counterfactual Exposure
|   |   |-- Diversified recommendations of cultural activities with personalized determinantal point processes
|   |   |-- Diversification as Risk Minimization
|   |   |-- ClawRec: A Claw-Native Recommender System
|   |   |-- ReList: A Multi-objective Reasoning Framework for Diversified Listwise Query Recommendation
|   |   |-- PreferRec: Learning and Transferring Pareto Preferences for Multi-objective Re-ranking
|   |   |-- Unifying Diversity and Fairness in Re-ranking via Economic Growth Theory
|   |   |-- RecoAtlas: From Semantic Plausibility to Set-Level Utility in LLM Recommendation Agents
|   |   |-- Optimizing Novelty of Top-k Recommendations using Large Language Models and Reinforcement Learning
|   |   |-- Enhancing Recommendation Diversity by Re-ranking with Large Language Models
|   |   |-- Scoring Is Not Enough: Addressing Gaps in Utility-fairness Trade-offs for Ranking
|   |   |-- Robustness and User-Perceived Value of Popularity Calibration in Music Recommendation: A User Study
|   |   |-- No Stakeholder Left Behind: Regret-Aware Re-Ranking for Two-Sided Fair Recommendation
|   |   |-- The Attention Market: Interpreting Online Fair Re-ranking as Manifold Optimization under Walrasian Equilibrium
|   |   |-- Streaming Stochastic Submodular Maximization with On-Demand User Requests
|   |   |-- Learning to Rank with Top-K Fairness
|   |   |-- Enhancing Diversity in News Recommendations Increases Click-Through Rates: Insights from an Online Experiment and User Study
|   |   |-- Fairness of Exposure in Rankings
|   |   |-- Sliding Spectrum Decomposition for Diversified Recommendation
|   |   |-- Feature-aware Diversified Re-ranking with Disentangled Representations for Relevant Recommendation
|   |   |-- PCN-Rec: Agentic Proof-Carrying Negotiation for Reliable Governance-Constrained Recommendation
|   |   |-- Producer-Fairness in Sequential Bundle Recommendation
|   |-- Ranked-list feedback, click models, bandits, and OPE
|   |   |-- Bandit Learning for Diversified Interactive Recommendation
|   |   |-- Cascading Bandits: Learning to Rank in the Cascade Model
|   |   |-- Combinatorial Cascading Bandits
|   |   |-- Cascading Bandits for Large-Scale Recommendation Problems
|   |   |-- Contextual Combinatorial Cascading Bandits
|   |   |-- DCM Bandits: Learning to Rank with Multiple Clicks
|   |   |-- Multiple-Play Bandits in the Position-Based Model
|   |   |-- Off-policy Evaluation for Slate Recommendation
|   |   |-- Doubly Robust Estimator for Ranking Metrics with Post-Click Conversions
|   |   |-- Open Bandit Dataset and Pipeline: Towards Realistic and Reproducible Off-Policy Evaluation
|   |   |-- Online Learning to Rank in Stochastic Click Models
|   |   |-- Offline Evaluation of Ranking Policies with Click Models
|   |   |-- TopRank: A Practical Algorithm for Online Stochastic Ranking
|   |   |-- Offline Evaluation to Make Decisions About Playlist Recommendation Algorithms
|   |   |-- Top-K Off-Policy Correction for a REINFORCE Recommender System
|   |   |-- SlateQ: A Tractable Decomposition for Reinforcement Learning with Recommendation Sets
|   |   |-- Cascading Non-Stationary Bandits: Online Learning to Rank in the Non-Stationary Cascade Model
|   |   |-- Cascading Linear Submodular Bandits: Accounting for Position Bias and Diversity in Online Learning to Rank
|   |   |-- Cascading Hybrid Bandits: Online Learning to Rank for Relevance and Diversity
|   |   |-- Counterfactual Evaluation of Slate Recommendations with Sequential Reward Interactions
|   |   |-- Learning to Rank in the Position Based Model with Bandit Feedback
|   |   |-- Top-K Contextual Bandits with Equity of Exposure
|   |   |-- Doubly Robust Off-Policy Evaluation for Ranking Policies under the Cascade Behavior Model
|   |   |-- Combinatorial Categorized Bandits with Expert Rankings
|   |   |-- Off-Policy Evaluation of Ranking Policies under Diverse User Behavior
|   |   |-- Off-Policy Evaluation of Slate Bandit Policies via Optimizing Abstraction
|   |   |-- Effective Off-Policy Evaluation and Learning in Contextual Combinatorial Bandits
|   |   |-- Long-term Off-Policy Evaluation and Learning
|   |   |-- Combining Reward and Rank Signals for Slate Recommendation
|   |   |-- Towards Adaptive Off-Policy Evaluation of Ranking Policies under Agnostic and Stochastic Behavior Models
|   |   |-- Impression-Aware Recommender Systems
|   |   |-- Neural Combinatorial Clustered Bandits for Recommendation Systems
|   |   |-- Off-Policy Evaluation for Ranking Policies under Deterministic Logging Policies
|   |   |-- Additive Control Variates Dominate Self-Normalisation in Off-Policy Evaluation
|   |   |-- Off-Policy Evaluation of Ranking Policies via Embedding-Space User Behavior Modeling
|   |   |-- Online Learning to Rank under Corruption: A Robust Cascading Bandits Approach
|   |   |-- Cascading Bandits Robust to Adversarial Corruptions
|   |   |-- Correcting for Position Bias in Learning to Rank: A Control Function Approach
|   |   |-- Addressing Personalized Bias for Unbiased Learning to Rank
|   |   |-- Unidentified and Confounded? Understanding Two-Tower Models for Unbiased Learning to Rank
|   |   |-- An Epistemic Position-Based Click Model: From Interactions to Epistemic Distributions of Relevance and Bias
|   |   |-- CLAX: Fast and Flexible Neural Click Models in JAX
|   |   |-- Diagnosing Identifiability in Two-Tower Models for Unbiased Learning to Rank
|   |   |-- Adaptive Doubly Robust Off-Policy Evaluation for Ranking Policies under Diverse User Behavior
|   |   |-- Quotient DAGs for Off-Policy Evaluation: Forward-Flow Importance Sampling and Exact Slate Propensities
|   |   |-- Contextual Slate GLM Bandits with Limited Adaptivity
|   |   |-- DCM Bandits: Multiplayer Information Asymmetric Cascading Bandits for Multiple Clicks
|   |   |-- Exposure-Based Reinforcement Learning to Rank
|   |   |-- Distributional Off-Policy Evaluation for Slate Recommendations
|   |   |-- Control Variates for Slate Off-Policy Evaluation
|   |   |-- FINN.no Slates Dataset: A new Sequential Dataset Logging Interactions, all Viewed Items and Click Responses/No-Click for Recommender Systems Research
|   |   |-- Neural Click Models for Recommender Systems
|   |   |-- Does Rank Still Matter? Position Bias When AI Agents Shop on Our Behalf
|   |   |-- Diversified Multinomial Logit Contextual Bandits
|   |   |-- Efficient and Robust Online Learning to Rank in Decentralized Systems
|   |   |-- Doubly-Robust Estimation for Correcting Position-Bias in Click Feedback for Unbiased Learning to Rank
|   |   |-- Unified Off-Policy Learning to Rank: a Reinforcement Learning Perspective
|   |   |-- Pessimistic Off-Policy Optimization for Learning to Rank
|   |   |-- On (Normalised) Discounted Cumulative Gain as an Off-Policy Evaluation Metric for Top-n Recommendation
|   |   |-- Efficient Algorithms for Logistic Contextual Slate Bandits with Bandit Feedback
|   |   |-- Towards Two-Stage Counterfactual Learning to Rank
|   |   |-- An Offline Metric for the Debiasedness of Click Models
|   |   |-- Offline Evaluation of Ranked Lists using Parametric Estimation of Propensities
|   |   |-- Practical and Robust Safety Guarantees for Advanced Counterfactual Learning to Rank
|   |   |-- Mitigating Exposure Bias in Online Learning to Rank Recommendation: A Novel Reward Model for Cascading Bandits
|   |   |-- Unbiased Learning to Rank with Query-Level Click Propensity Estimation: Beyond Pointwise Observation and Relevance
|   |   |-- Multi-User Contextual Cascading Bandits for Personalized Recommendation
|   |   |-- Cross-Positional Attention for Debiasing Clicks
|   |   |-- LLMs for estimating positional bias in logged interaction data
|   |   |-- Generalized Position-Based Model: Rethinking Position Weights in Ranking Off-Policy Evaluation
|   |   |-- A Causal Information-Flow Framework for Unbiased Learning-to-Rank
|   |   |-- RewardRank: Optimizing True Learning-to-Rank Utility
|   |   |-- A Reward-Informed Semi-Personalized Bandit Approach for Enhancing Accuracy and Serendipity in Online Slate Recommendations
|   |   |-- Unbiased Learning-to-Rank with Biased Feedback
|   |   |-- Unbiased Learning to Rank with Unbiased Propensity Estimation
|   |   |-- Position Bias Estimation for Unbiased Learning to Rank in Personal Search
|   |   |-- Policy-Aware Unbiased Learning to Rank for Top-k Rankings
|   |   |-- Unbiased Learning to Rank Meets Reality: Lessons from Baidu's Large-Scale Search Dataset
|   |   |-- A Neural Click Model for Web Search
|   |   |-- ContentWise Impressions: An Industrial Dataset with Impressions Included
|   |   |-- Offline A/B testing for Recommender Systems
|   |   |-- Probabilistic Rank and Reward: A Scalable Model for Slate Recommendation
|   |   |-- Evaluating Stochastic Rankings with Expected Exposure
|   |   |-- Thompson Sampling Algorithms for Cascading Bandits
|   |   |-- BubbleRank: Safe Online Learning to Re-Rank via Implicit Click Feedback
|   |   |-- Model-based Unbiased Learning to Rank
|   |   |-- Off-policy evaluation for learning-to-rank via interpolating the item-position model and the position-based model
|   |   |-- Unbiased Offline Evaluation for Learning to Rank with Business Rules
|-- Layout aware
|   |-- Grid and 2D presentation
|   |   |-- Personalizing User Interfaces for Improving Quality of Experience in VoD Recommender Systems
|   |   |-- Toward User Engagement Optimization in 2D Presentation
|   |   |-- Controlling Personalized Recommendations in Two Dimensions with a Carousel-Based Interface
|   |   |-- Examining Choice Overload Across Single-List and Multi-List User Interfaces
|   |   |-- Tile Networks: Learning Optimal Geometric Layout for Whole-page Recommendation
|   |   |-- Reinforcement Re-ranking with 2D Grid-based Recommendation Panels
|   |   |-- Towards Measuring Fairness in Grid Layout in Recommender Systems
|   |   |-- Debiasing Grid-based Product Search in E-commerce
|   |-- Carousel, multi-list, shelf, and widget interfaces
|   |   |-- Multi-list interfaces for recommender systems: survey and future directions
|   |   |-- The Netflix Recommender System: Algorithms, Business Value, and Innovation
|   |   |-- Using Navigation to Improve Recommendations in Real-Time
|   |   |-- Explore, Exploit, and Explain: Personalizing Explainable Recommendations with Bandits
|   |   |-- Carousel Personalization in Music Streaming Apps with Contextual Bandits
|   |   |-- Automatic Collection Creation and Recommendation
|   |   |-- Optimizing the Selection of Recommendation Carousels with Quantum Computing
|   |   |-- Measuring the User Satisfaction in a Recommendation Interface with Multiple Carousels
|   |   |-- Offline Evaluation of Recommender Systems in a User Interface With Multiple Carousels
|   |   |-- The Magic of Carousels: Single vs. Multi-List Recommender Systems
|   |   |-- Exploring Multi-List User Interfaces for Similar-Item Recommendations
|   |   |-- Serving Each User: Supporting Different Eating Goals Through a Multi-List Recommender Interface
|   |   |-- How Users Ride the Carousel: Exploring the Design of Multi-List Recommender Interfaces From a User Perspective
|   |   |-- Examining the User Evaluation of Multi-List Recommender Interfaces in the Context of Healthy Recipe Choices
|   |   |-- Towards Simulation-Based Evaluation of Recommender Systems with Carousel Interfaces
|   |   |-- From Ranked Lists to Carousels: A Carousel Click Model
|   |   |-- RecGaze: The First Eye Tracking and User Interaction Dataset for Carousel Interfaces
|   |   |-- Riding the Carousel: The First Extensive Eye Tracking Analysis of Browsing Behavior in Carousel Recommenders
|   |   |-- Effective Diversification of Multi-Carousel Book Recommendation
|   |   |-- LLM-Assisted Reranking to Operationalize Nuanced Objectives in Recommender Systems
|   |   |-- Full-Page Recommender: A Modular Framework for Multi-Carousel Recommendations
|   |   |-- Rethinking Click Models in Light of Carousel Interfaces: Theory-Based Categorization and Design of Click Models
|   |   |-- From Latent to Observable Position-Based Click Models in Carousel Interfaces
|   |   |-- UniPinRec: Unifying Generative Retrieval and Ranking at Pinterest Scale
|   |   |-- TubiFM: Unified Item, Carousel, and Search Ranking for Streaming Discovery
|   |   |-- From Click Modeling to Offline and Off-Policy Evaluation in Carousel Recommendation
|   |   |-- Revisiting N2DCG: An Empirically Grounded Reformulation of Carousel Recommendation Evaluation
|   |   |-- Following the Eye-Tracking Evidence: Established Web-Search Assumptions Fail in Carousel Interfaces
|   |   |-- Hypothesis-Driven Shelf Generation for Personalised Recommendation
|   |   |-- Under the Hood of Carousels: Investigating User Engagement and Navigation Effort in Multi-list Recommender Systems
|   |   |-- CARE: An Infrastructure for Evaluation of Carousel-Based Recommender Interfaces
|   |   |-- Understanding User Behavior in Carousel Recommendation Systems for Click Modeling and Learning to Rank
|   |   |-- Event-based Product Carousel Recommendation with Query-Click Graph
|   |   |-- An LLM-powered Agentic Recommendation System for Connected TV Content Discovery
|   |   |-- Foraging in multi-list recommender interfaces: the effects of digital nudges and aging
|   |   |-- Where to Explore: A Reach and Cost-Aware Approach for Unbiased Data Collection in Recommender Systems
|   |-- Whole page, page modules, and landing pages
|   |   |-- Beyond Ranking: Optimizing Whole-Page Presentation
|   |   |-- Whole-Page Optimization and Submodular Welfare Maximization with Online Bidders
|   |   |-- Efficient Ordered Combinatorial Semi-Bandits for Whole-Page Recommendation
|   |   |-- Deep Reinforcement Learning for Page-wise Recommendations
|   |   |-- The Whole-Page Optimization via Dynamic Ad Allocation
|   |   |-- Whole Page Optimization with Global Constraints
|   |   |-- Page-level Optimization of e-Commerce Item Recommendations
|   |   |-- Automate Page Layout Optimization: An Offline Deep Q-learning Approach
|   |   |-- A Bird's-eye View of Reranking: from List Level to Page Level
|   |   |-- Cooperative Multi-Agent Deep Reinforcement Learning in Content Ranking Optimization
|   |   |-- KLAN: Kuaishou Landing-page Adaptive Navigator
|   |   |-- Enhanced Whole Page Optimization via Mixed-Grained Reward Mechanism-Adapted Language Models
|   |   |-- STCRank: Spatio-temporal Collaborative Ranking for Interactive Recommender System at Kuaishou E-shop
|   |   |-- An Efficient Framework for Whole-Page Reranking via Single-Modal Supervision
|   |   |-- Design and Evaluation of Whole-Page Experience Optimization for E-commerce Search
|   |   |-- Constraint-Aware Generative Re-ranking for Multi-Objective Optimization in Advertising Feeds
|   |   |-- A Cascaded Generative Approach for e-Commerce Recommendations
|   |   |-- Designing for the Next Click: Bandits for Real-Time Page Layout
|   |   |-- Whole Page Unbiased Learning to Rank
|   |   |-- GenPage: Towards End-to-End Generative Homepage Construction at Netflix
|   |   |-- Multi-channel Integrated Recommendation with Exposure Constraints
|   |   |-- DEAR: Deep Reinforcement Learning for Online Advertising Impression in Recommender Systems
|   |   |-- Jointly Learning to Recommend and Advertise
|   |   |-- Hierarchical Reinforcement Learning for Integrated Recommendation
|   |   |-- Cross DQN: Cross Deep Q Network for Ads Allocation in Feed
|   |   |-- Online Advertising with Spatial Interactions
|   |   |-- Learning List-wise Representation in Reinforcement Learning for Ads Allocation with Multiple Auxiliary Tasks
```

## Coverage Statistics

These counts summarize the current README coverage, not citation impact or a
complete bibliographic census. Counts are approximate because several papers
have multiple authors and affiliations; a paper can contribute to more than one
author or institution cluster when the connection is visible from the paper
metadata, source page, or row notes.

### Author Coverage

| Author or cluster | Approx. README entries | Main coverage in this README |
| --- | ---: | --- |
| Shuchang Liu | 13+ | Generative slate/list recommendation, industrial reranking, request-level recommendation, retention optimization, and Kuaishou page navigation. |
| Yuta Saito | 8+ | Off-policy evaluation and learning for ranking and slate bandits, ranking-metric debiasing, the Open Bandit OPE benchmark, deterministic logging, and long-term policy value. |
| Haruka Kiyohara | 5+ | Ranking-policy OPE under cascade, agnostic, stochastic, and diverse user behavior models. |
| Branislav Kveton | 6+ | Cascade-bandit, ranked-bandit, and user-click-model learning for top-k recommendation. |
| Zheng Wen | 4+ | Cascading and dependent-click-model bandits for ranked recommendations. |
| Csaba Szepesvari | 4+ | Cascading bandits, stochastic ranking, and partial-feedback learning to rank. |
| James McInerney | 3+ | Playlist, shelf, and slate counterfactual evaluation in music recommendation. |
| Shuai Li | 2+ | Contextual combinatorial bandits and click-model offline evaluation for rankings. |

### Institution Coverage

| Institution or lab | Approx. README entries | Main coverage in this README |
| --- | ---: | --- |
| Kuaishou | 18+ | Industrial generative reranking, large rankers, request-level RL, retention optimization, simulation, and landing-page navigation. |
| Google / YouTube | 5+ | Slate generation, top-k off-policy correction, long-term satisfaction ranking, and production-scale diversification. |
| Spotify | 3+ | Playlist recommendation, explainable shelves, carousel bandits, and slate counterfactual evaluation. |
| Microsoft / Microsoft Research | 2+ | Whole-page ad allocation (submodular welfare) and combinatorial categorized bandits. |
| Amazon / Amazon Science | 2+ | Homepage/widget optimization and offline RL for page layout. |
| Yale / Tokyo Institute of Technology / Hanjuku-kaso / ZOZO | 5+ | Ranking and slate OPE with cascade, diverse, deterministic, and combinatorial behavior assumptions. |
| Netflix | 1+ | Multi-row homepage recommender systems. |

## Surveys and Background

| Year | Paper | Venue | Why it matters |
| --- | --- | --- | --- |
| 2015 | [Click Models for Web Search](https://doi.org/10.2200/S00654ED1V01Y201507ICR043) | Morgan & Claypool (Synthesis Lectures on Information Concepts, Retrieval, and Services) | Chuklin, Markov and de Rijke's monograph that systematizes probabilistic click models over ranked result lists (cascade, position-based, UBM, DBN, DCM and their extensions), their parameter estimation and evaluation, and their applications to ranking and simulation. |
| 2022 | [Neural Re-ranking in Multi-stage Recommender Systems: A Review](https://arxiv.org/abs/2202.06602) | IJCAI | Huawei Noah's Ark Lab / SJTU survey of neural reranking as the final multi-stage recommender stage, with a taxonomy of listwise context models and personalization plus the LibRerank benchmark library. |
| 2023 | [Multi-list interfaces for recommender systems: survey and future directions](https://doi.org/10.3389/fdata.2023.1239705) | Frontiers in Big Data | The most directly relevant survey for carousel and multi-list recommender interfaces. |
| 2023 | [Deep Reinforcement Learning in Recommender Systems: A Survey and New Perspectives](https://doi.org/10.1016/j.knosys.2023.110335) | Knowledge-Based Systems | Broad RL-for-recommendation context, including long-term optimization beyond one-step prediction. |

## Main Threads

The taxonomy and tree above are indexes; this section is the synthesis. Seven
arcs run through the collection, and reading the survey along them is often more
informative than reading it table by table.

### 1. From greedy pointwise ranking to whole-slate generation

The oldest and strongest arc treats the exposed list as a single object to be
generated rather than a set of independently scored items. List-CVAE (2018) first
generated complete slates with a conditional VAE; Seq2Slate (2018) made the
construction sequential with a pointer network. An intermediate *permutation-wise*
line — Exact-K (2019), PRS (2021), GRN (2021), and PIER (2023) — reframed
reranking as selecting or generating a whole permutation that is then scored by a
list-aware evaluator, bridging early slate generation and today's generative
rerankers. The generative line then branches into RL (Generative Slate
Recommendation with RL, 2023; Exploration and Regularization of the Latent Action
Space, 2023), GFlowNets (Generative Flow Network for Listwise Recommendation,
2023), and diffusion (Discrete Conditional Diffusion, 2024; Diffusion Model for
Slate Recommendation, 2024). By 2024-2026 the dominant industrial form is
autoregressive / non-autoregressive generative reranking (NAR4Rec, 2024, and the
Taobao / Meituan / Tencent / Kuaishou generative rerankers), and most recently
LLM-as-reranker (One Pass, Any Order, 2026; Rich-Media Re-Ranker, 2026).

### 2. A slate's value is not the sum of its items: long-term, list-level RL

A second arc insists that the reward of a slate is more than the sum of per-item
scores. SlateQ (2019) decomposed the long-term value of a slate into item-level
values under an explicit user-choice model; Top-K Off-Policy Correction (2019)
brought policy-gradient learning to a production top-k recommender. The Kuaishou
line then pushes toward long horizons: request-level MDPs for retention
(Reinforcing User Retention, 2023), future-impact decomposition (2024), retention
through generative flow networks (2024), and value-function decomposition (2025).
The recurring lesson is that clicks are a proxy, and the real objective is
long-term user value over the whole list and session.

### 3. Learning and evaluating from logged slate feedback

Because users reveal only partial, position-biased feedback, a large body of work
models the browsing process explicitly — cascade, position-based, and
dependent-click models — and builds bandit or off-policy estimators on top. The
bandit side runs from Cascading Bandits (2015) through combinatorial, contextual,
non-stationary, and corruption-robust variants. The off-policy-evaluation side
(most visibly the Saito / Kiyohara line) progresses from slate IPS (Off-policy
Evaluation for Slate Recommendation, 2017) to doubly robust cascade estimators,
learned slate abstractions, embedding-space behavior models, and
deterministic-logging and long-term-value estimators (2024-2026). This is the
deepest single thread in the collection and the one most tightly coupled to
explicit user-behavior assumptions.

### 4. Diversity and set quality

A slate's worth depends on coverage, not just per-item relevance. Production DPP on
YouTube (2018) and fast greedy MAP inference (2018) anchor the line; recent work
adds adaptive quality-diversity trade-offs from post-exposure feedback (B-DivRec,
2026), causal deconfounding of co-purchase relations (Cadence, 2025), personalized
DPP for the homepage (2025), and even carbon-aware re-ranking (2026). Intra-list
diversity (ILD) recurs as the evaluation currency across these papers.

### 5. Layout-aware presentation: carousels, multi-list, and whole pages

Once the surface is two-dimensional, geometry matters. From the Netflix multi-row
homepage (2015) and whole-page presentation optimization (2016), the carousel
sub-line develops contextual-bandit personalization (2020), carousel-specific click
models, and — most distinctively in 2024-2026 — eye-tracking datasets and analyses
(RecGaze, 2025; Riding the Carousel, 2025) plus simulation-based carousel
evaluation. The whole-page sub-line runs in parallel through page-wise RL
(DeepPage, 2018), constrained widget ranking (Whole Page Optimization with Global
Constraints, 2019), and recent LLM- and causal-driven whole-page optimization
(2025-2026).

### 6. The 2024-2026 inflection

Three currents converge in the most recent work: (i) generative and LLM-based
rerankers, world models, and judges (LLM-as-a-Judge world models, 2025, and the
2026 LLM-reranking cluster); (ii) the scientific study of carousel browsing through
eye tracking and principled click-model design; and (iii) industrial-scale
generative reranking deployed across Kuaishou, Meituan, Taobao, Tencent, Pinterest,
Bilibili, and Baidu. Taken together, the field is shifting from "score, then sort"
toward "generate, evaluate, and present the whole surface."

### 7. The evaluation gap: whole-slate generation on exposure-blind metrics

A methodological fault line runs between this survey's two halves. The
construction papers generate ever-more-expressive slates, yet almost none
evaluate them with the unbiased machinery built in the feedback-and-evaluation
branch. Because a freshly generated permutation was never logged, three offline
workarounds dominate, and each treats exposure bias differently. Simulator
rollouts (List-CVAE, 2018; Seq2Slate, 2018; Generative Slate Recommendation with
RL, 2023; GFN4Rec, 2023) bake position and examination bias into a hand-built or
learned response model and score generated slates inside it — bias is modeled as
environment, not corrected, and the simulator is often trained on the same logs
as the policy it judges. Learned list-wise evaluators (PRS, 2021; GRN, 2021;
PIER, 2023; GoalRank, 2025) are position- and context-aware but inherit the
logging policy's exposure bias wholesale, and frequently define their own "best
permutation" as ground truth, making the offline judge circular. The
now-dominant recover-the-logged-list metrics — Recall@k and leave-N-out NDCG/HR
(NAR4Rec, 2024; HiGR, 2025; Breaking the Likelihood Trap, 2025; Denoising Neural
Reranker, 2026) — are the most exposed of all: they reward reproducing what the
previous system chose to show, inheriting the exposure-blind, sampled-metric
convention of pure sequential recommenders (SASRec, GRU4Rec, BERT4Rec). The real
arbiter is therefore the online A/B test, where exposure happens for real —
SORT-Gen (2025) drops offline metrics altogether. Yet the antidote already lives
in this survey: ranking-metric debiasing (Doubly Robust Estimator for Ranking
Metrics, 2020), slate and cascade OPE (Off-policy Evaluation for Slate
Recommendation, 2017; the Kiyohara line), and large-action-space ranking OPE
(embedding-space user-behavior modeling, 2025) are exactly the tools for scoring
counterfactual permutations; they are simply rarely adopted on the construction
side. Benchmarking generative rerankers against a debiased offline estimator —
instead of against the slate the previous policy happened to log — is among the
clearest open problems the collection exposes.

## Slate Construction: What to Recommend

This branch asks how the system should build the final recommendation surface.
Hybrid papers are placed here when their main contribution is constructing,
ranking, reranking, diversifying, or laying out the slate/page that users see.

### Direct Slate, List, and Set Optimization

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2018 | [Beyond Greedy Ranking: Slate Optimization via List-CVAE](https://arxiv.org/abs/1803.01682) | ICLR 2019 | Directly generates complete slates with a conditional VAE instead of greedily sorting item scores. |
| 2019 | [Exact-K Recommendation via Maximal Clique Optimization](https://arxiv.org/abs/1905.07089) | KDD | Constructs a whole card of K items as constrained combinatorial optimization (reduced to maximal clique), learning the joint distribution of the set end-to-end rather than ranking items individually. |
| 2019 | [Personalized Bundle List Recommendation](https://arxiv.org/abs/1904.01933) | WWW | Alibaba/Peking University Bundle Generation Network that builds a personalized bundle list as structured prediction with an encoder-decoder, feature-aware softmax, masked beam search, and DPP-based selection to trade off quality and diversity. |
| 2019 | [Generative Adversarial User Model for Reinforcement Learning Based Recommendation System](https://arxiv.org/abs/1812.10613) | ICML | Ant Financial/Georgia Tech model-based RL recommender that learns a GAN user choice model over the displayed item set and uses cascading DQN to pick a k-item set from a combinatorial action space. |
| 2021 | [Variation Control and Evaluation for Generative Slate Recommendations](https://arxiv.org/abs/2102.13302) | WWW | Shuchang Liu et al.; studies generative slate recommendation and adds variation metrics beyond accuracy for stochastic slate generators. |
| 2021 | [Conditional Sequential Slate Optimization](https://arxiv.org/abs/2108.05618) | SIGIR eCom | Re-ranks candidates into a slate while jointly optimizing ranking quality and composition constraints. |
| 2021 | [Computationally Efficient Optimization of Plackett-Luce Ranking Models for Relevance and Fairness](https://arxiv.org/abs/2105.00855) | SIGIR | PL-Rank: sample-efficient gradient estimation for Plackett-Luce stochastic ranking policies that optimizes top-k ranked lists for relevance and exposure fairness. |
| 2022 | [Dynamic Slate Recommendation with Gated Recurrent Units and Thompson Sampling](https://arxiv.org/abs/2104.15046) | Data Mining and Knowledge Discovery | Models slate exposure explicitly and introduces in-slate Thompson sampling for exploration. |
| 2023 | [Exploration and Regularization of the Latent Action Space in Recommendation](https://arxiv.org/abs/2302.03431) | WWW | Shuchang Liu et al.; decomposes list action generation into latent hyper-actions and item-list selection for RL-based recommendation. |
| 2023 | [Generative Slate Recommendation with Reinforcement Learning](https://arxiv.org/abs/2301.08632) | WSDM | Learns to generate slates with RL under the combinatorial action-space challenge. |
| 2023 | [Generative Flow Network for Listwise Recommendation](https://arxiv.org/abs/2306.02239) | KDD | Uses GFlowNets to generate diverse high-reward recommendation lists. |
| 2023 | [Slate-Aware Ranking for Recommendation](https://arxiv.org/abs/2302.12427) | WSDM | Brings slate-level relationships into the ranking stage before the final re-ranker. |
| 2023 | [Multi-Task Recommendations with Reinforcement Learning](https://arxiv.org/abs/2302.03328) | WWW | Kuaishou collaboration; uses an RL-enhanced multi-task framework to learn dynamic task-loss weights from session-wise interactions. |
| 2023 | [Reinforcing User Retention in a Billion Scale Short Video Recommender System](https://arxiv.org/abs/2302.01724) | WWW | Kuaishou system paper; formulates retention optimization as a request-based MDP and deploys RLUR in production. |
| 2023 | [State Regularized Policy Optimization on Data with Dynamics Shift](https://proceedings.neurips.cc/paper_files/paper/2023/hash/67dd6a41bf9539cffc0fc0165e4d0616-Abstract-Conference.html) | NeurIPS | Kuaishou/NTU RL paper for dynamics shift, motivated partly by time-varying recommender environments. |
| 2023 | [Fast Slate Policy Optimization: Going Beyond Plackett-Luce](https://arxiv.org/abs/2308.01566) | TMLR | Criteo relaxation-based slate policy class with an efficient learning algorithm that scales slate policy optimization beyond Plackett-Luce to millions of actions. |
| 2023 | [Automatic Music Playlist Generation via Simulation-based Reinforcement Learning](https://arxiv.org/abs/2310.09123) | KDD | Spotify playlist generation with a modified DQN trained in a user-simulator environment to directly optimize whole-playlist satisfaction, validated offline and in online A/B tests. |
| 2024 | [Learned Ranking Function: From Short-term Behavior Predictions to Long-term User Satisfaction](https://arxiv.org/abs/2408.06512) | RecSys | YouTube system that learns a ranking function for slate-level long-term satisfaction. |
| 2024 | [Sequential Recommendation for Optimizing Both Immediate Feedback and Long-term Retention](https://arxiv.org/abs/2404.03637) | SIGIR | Shuchang Liu et al.; decision-transformer approach for balancing immediate engagement with long-term retention. |
| 2024 | [Future Impact Decomposition in Request-level Recommendations](https://arxiv.org/abs/2401.16108) | KDD | Kuaishou system paper; decomposes request-level list rewards into item-wise future impact for long-term optimization. |
| 2024 | [Modeling User Retention through Generative Flow Networks](https://arxiv.org/abs/2406.06043) | KDD | Shuchang Liu et al.; propagates sparse retention rewards back to recommended items through a probabilistic flow. |
| 2024 | [Adaptive In-Context Learning with Large Language Models for Bundle Generation](https://arxiv.org/abs/2312.16262) | SIGIR | Adaptive in-context learning framework that retrieves related sessions as demonstrations and uses self-correction and feedback prompting so an LLM jointly generates personalized bundles and infers their intents. |
| 2024 | [Top-Personalized-K Recommendation](https://arxiv.org/abs/2402.16304) | WWW | PerK framework (POSTECH) that picks a personalized recommendation list size K per user by maximizing expected list utility estimated from calibrated interaction probabilities. |
| 2025 | [Value Function Decomposition in Markov Recommendation Process](https://arxiv.org/abs/2501.17409) | WWW | Shuchang Liu et al.; decomposes temporal-difference learning to separate stochastic policy effects from user-environment randomness. |
| 2025 | [Don't Get Bored: Enhancing Scalability and Diversity in Session-Based Slate Recommendation](https://dl.acm.org/doi/10.1145/3733241) | ACM TORS | Composes diverse slates with RL using item- and slate-level representations, evaluated with a boredom/engagement user simulator. |
| 2025 | [A Language Model-Based Playlist Generation Recommender System](https://doi.org/10.1145/3705328.3748053) | RecSys | EURECOM playlist generator that builds semantic clusters from title embeddings, fine-tunes a transformer on the thematic clusters, and generates whole playlists for known or unseen titles via similarity voting, beating RecSys Challenge 2018 baselines in cold start. |
| 2026 | [Breaking the Likelihood Trap: Consistent Generative Recommendation with Graph-structured Model](https://arxiv.org/abs/2510.10127) | KDD | CONGRATS frames reranking as whole-sequence generation, decoding the entire exposed list with a graph-structured model for item dependencies and diversity. |
| 2026 | [Stochastic Primal-Dual Decoding for Multiobjective Generative Recommender Systems](https://arxiv.org/abs/2607.19357) | KDD | Spotify inference-time stochastic primal-dual decoding layer that generates slates from a generative recommender while dynamically trading relevance against attribute and fairness constraints on the remaining list, with regret guarantees and a 1M-user playlist A/B test. |
| 2026 | [Large-Scale Online Learning for Generative List Recommendation in E-commerce: An Environment Policy Optimization Approach](https://doi.org/10.1145/3805712.3809577) | SIGIR | Environment Policy Optimization (EPO) for online learning of an e-commerce generative list recommender that backpropagates the listwise reward through a differentiable evaluator, using NeuralSort and Gumbel-noise relaxation of discrete item selection for end-to-end list generation. |
| 2026 | [Sequential Multimodal Evidence Optimization for Product Media Ranking in E-Commerce](https://arxiv.org/abs/2608.15662) | CIKM | SMEO learns a position-bias-aware utility of consumed media sequences from logged e-commerce behavior and trains a policy to order a product's media list so decision-relevant evidence appears early. |
| 2026 | [A Reproducibility Study of Bundle Editing and Bundle Recommendation](https://doi.org/10.1145/3805712.3808559) | SIGIR | Reproducibility study re-implementing eight bundle-level and nine item-level bundle editing methods plus seven bundle recommendation models across six datasets, finding replacement to be the universal bottleneck of bundle construction. |
| 2026 | [Rank-GRPO: Training LLM-based Conversational Recommender Systems with Reinforcement Learning](https://arxiv.org/abs/2510.20150) | ICLR | Netflix ConvRec-R1 framework whose Rank-GRPO treats each rank of the generated recommendation list as the credit-assignment unit with rank-level importance ratios, training an LLM conversational recommender to directly improve whole-list Recall and NDCG. |
| 2026 | [Routing Distilled Knowledge via Mixture of LoRA Experts for Large Language Model based Bundle Generation](https://arxiv.org/abs/2508.17250) | Neural Networks | RouteDK distills generalized rules and session-specific reasoning from teacher LLMs into separate LoRA experts with an input-aware router, giving small student LLMs teacher-level bundle generation at lower cost. |
| 2026 | [Decoupled Learning and Selection in Slate Recommendation for Privacy and Stability Under Noisy Scores](https://github.com/mlgorithm/decoupled-slate-recommendation-recsys-2026) | RecSys | University of Bergen RecSys 2026 paper that decouples score learning from slate selection so multi-item slates stay stable and privacy-preserving under noisy item scores, evaluated on OULAD, EdNet, MovieLens-25M, and Amazon. |
| 2026 | [Melo: A Production LLM-Powered Music Recommendation Agent](https://arxiv.org/abs/2607.23718) | RecSys | NetEase Cloud Music production LLM agent (Melo) with a five-node state graph, search-index entity grounding, and reflective retry that generates whole playlists, yielding over 2pp lift in playlist retention. |

### Re-ranking and Listwise Context Models

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2018 | [Learning a Deep Listwise Context Model for Ranking Refinement](https://arxiv.org/abs/1804.05936) | SIGIR | Uses local context among top-ranked results to refine the whole list. |
| 2019 | [Personalized Re-ranking for Recommendation](https://doi.org/10.1145/3298689.3347000) | RecSys | Transformer-style personalized re-ranking that models item interactions in the candidate list. |
| 2019 | [Learning Groupwise Multivariate Scoring Functions Using Deep Neural Networks](https://arxiv.org/abs/1811.04415) | ICTIR | Scores documents/items in groups to capture cross-item effects. |
| 2020 | [SetRank: Learning a Permutation-Invariant Ranking Model for Information Retrieval](https://arxiv.org/abs/1912.05891) | SIGIR | Set-based ranking model that captures cross-document interactions without depending on input order. |
| 2022 | [Multi-Level Interaction Reranking with User Behavior History](https://arxiv.org/abs/2204.09370) | SIGIR | MIR (SJTU/Huawei Noah's Ark) reranks a candidate list with set-to-list SLAttention between the candidate set and user behavior history at item and feature levels while remaining permutation-invariant. |
| 2023 | [PIER: Permutation-Level Interest-Based End-to-End Re-ranking Framework in E-commerce](https://arxiv.org/abs/2302.03487) | KDD | Selects top permutations with a fine-grained permutation-selection module and scores them with an omnidirectional context-aware model, deployed at Meituan. |
| 2023 | [Reinforcement Re-ranking with 2D Grid-based Recommendation Panels](https://arxiv.org/abs/2204.04954) | SIGIR-AP | Panel-MDP (Renmin University with Huawei) casts filling a 2D grid recommendation panel as a sequential MDP solved with PPO so the reranker learns grid-specific browsing patterns. |
| 2023 | [Is ChatGPT Good at Search? Investigating Large Language Models as Re-Ranking Agents](https://arxiv.org/abs/2304.09542) | EMNLP | RankGPT casts reranking as listwise permutation generation by an LLM over a sliding window of candidates and distills the ranking ability into a small specialized reranker. |
| 2023 | [RankFormer: Listwise Learning-to-Rank Using Listwide Labels](https://arxiv.org/abs/2306.05808) | KDD | Amazon Search Transformer ranker that jointly optimizes a listwise ranking loss and a listwide objective capturing users' absolute feedback on the whole list's quality, distilled for online deployment. |
| 2023 | [Controllable Multi-Objective Re-ranking with Policy Hypernetworks](https://arxiv.org/abs/2306.05118) | KDD | CMR (Renmin University with Taobao) uses a policy hypernetwork to generate listwise re-ranker parameters for arbitrary accuracy/diversity/novelty preference weights without retraining, validated on Taobao data and online A/B tests. |
| 2024 | [Utility-Oriented Reranking with Counterfactual Context](https://doi.org/10.1145/3671004) | ACM TKDD | Optimizes list utility by reasoning about the counterfactual context after re-ranking. |
| 2024 | [Discrete Conditional Diffusion for Reranking in Recommendation](https://arxiv.org/abs/2308.06982) | WWW Companion | Kuaishou diffusion reranker that generates item permutations under user-response conditions. |
| 2024 | [Non-autoregressive Generative Models for Reranking Recommendation](https://arxiv.org/abs/2402.06871) | KDD | Kuaishou NAR4Rec system that generates whole reranked sequences in parallel for industrial latency. |
| 2024 | [Large Language Models are Zero-Shot Rankers for Recommender Systems](https://arxiv.org/abs/2305.08845) | ECIR | Formalizes recommendation as conditional listwise ranking of a candidate list by a zero-shot LLM, exposes candidate-position bias in the list prompt, and proposes prompting strategies (bootstrapping, recency emphasis) to mitigate it. |
| 2024 | [Found in the Middle: Permutation Self-Consistency Improves Listwise Ranking in Large Language Models](https://arxiv.org/abs/2310.07712) | NAACL | Permutation self-consistency removes input-order positional bias in LLM listwise rankers by shuffling the candidate list across prompts and aggregating the resulting rankings into an order-independent list. |
| 2025 | [Comprehensive List Generation for Multi-Generator Reranking](https://arxiv.org/abs/2504.15625) | SIGIR | Shuchang Liu et al.; learns complementary generators and optimizes list comprehensiveness for multi-generator reranking. |
| 2025 | [GoalRank: Group-Relative Optimization for a Large Ranking Model](https://arxiv.org/abs/2509.22046) | ICLR 2026 | Shuchang Liu et al.; trains a generator-only large ranker with group-relative optimization over recommendation lists. |
| 2025 | [A Generative Re-ranking Model for List-level Multi-objective Optimization at Taobao](https://arxiv.org/abs/2505.07197) | SIGIR | SORT-Gen; end-to-end generative reranker that builds ordered lists under list-level multi-objective targets (clicks, conversions, GMV) at Taobao. |
| 2025 | [You Only Evaluate Once: A Tree-based Rerank Method at Meituan](https://arxiv.org/abs/2508.14420) | CIKM | YOLOR; one-stage list-level reranker that evaluates candidate permutations with a tree-based context module and permutation cache at Meituan scale. |
| 2025 | [NLGR: Utilizing Neighbor Lists for Generative Rerank in Personalized Recommendation Systems](https://arxiv.org/abs/2502.06097) | WWW Companion | Meituan NLGR generative reranker that trains the generator with neighbor lists in combination space and decodes the reranked list with sampling-based non-autoregressive generation for online serving. |
| 2025 | [GReF: A Unified Generative Framework for Efficient Reranking via Ordered Multi-token Prediction](https://arxiv.org/abs/2510.25220) | CIKM | Kuaishou GReF generative reranker that unifies generator and evaluator with a bidirectional encoder, exposure-order pre-training, Rerank-DPO, and ordered multi-token prediction to emit reranked lists at non-autoregressive latency. |
| 2025 | [LLM4Rerank: LLM-based Auto-Reranking Framework for Recommendations](https://arxiv.org/abs/2406.12433) | WWW | Huawei Noah's Ark and CityU LLM4Rerank framework that reranks candidate lists by traversing a fully connected graph of aspect nodes (accuracy, diversity, fairness) with chain-of-thought, letting one LLM reranker balance multiple list-level criteria. |
| 2025 | [NGA: Non-autoregressive Generative Auction with Global Externalities for Advertising Systems](https://arxiv.org/abs/2506.05685) | CIKM | Meituan NGA generative auction that non-autoregressively decodes a complete ad slate under constraints and scores it with a parallel multi-tower list-wise reward and payment evaluator modelling externalities among ads and adjacent organic items. |
| 2026 | [Denoising Neural Reranker for Recommender Systems](https://arxiv.org/abs/2509.18736) | ICLR 2026 | Shuchang Liu et al.; treats reranking as denoising retriever scores before refining the exposed item list. |
| 2026 | [One Pass, Any Order: Position-Invariant Listwise Reranking for LLM-Based Recommendation](https://arxiv.org/abs/2604.27599) | SIGIR | InvariRank scores an entire candidate set in one pass to produce a list while removing position/permutation bias on LLM rankings. |
| 2026 | [STCRank: Spatio-temporal Collaborative Ranking for Interactive Recommender System at Kuaishou E-shop](https://arxiv.org/abs/2601.10027) | WWW Companion | Kuaishou E-shop; spatio-temporal collaborative ranking for an interactive multi-item recommendation surface. |
| 2026 | [Beyond Static Best-of-N: Bayesian List-wise Alignment for LLM-based Recommendation](https://arxiv.org/abs/2605.04559) | SIGIR | Frames recommendation as conditional list generation and directly optimizes non-differentiable list metrics (NDCG@k, ILD, group unfairness). |
| 2026 | [Rich-Media Re-Ranker: A User Satisfaction-Driven LLM Re-ranking Framework for Rich-Media Search](https://arxiv.org/abs/2602.05408) | CIKM | LLM reranks the whole rich-media search list with list-level principles, optimized via post-exposure user satisfaction in production. |
| 2026 | [DeGRe: Dense-supervised Generative Reranking for Recommendation](https://arxiv.org/abs/2605.25749) | KDD | Taobao Flash Shopping generative reranker that trains a lookahead cumulative-regression evaluator offline to label high-value whole sequences and distills it into a lightweight online generator, addressing heuristic label bias and credit assignment. |
| 2026 | [DEGR: Dual Exploration-Driven Generative Re-Ranking for Adaptive Cross-Request Context Bridging](https://arxiv.org/abs/2608.04809) | KDD | JD.com generative list reranker that combines supervised and reinforcement optimization with an adaptive reward model to trade off immediate list value against exploratory exposure across successive requests. |
| 2026 | [Position Bias Undermines Preference Consistency in Listwise LLM-Based Reranking](https://arxiv.org/abs/2608.03091) | RecSys | Evaluation framework showing that LLM listwise rerankers for recommendation give unstable pairwise, global, and listwise preferences across candidate permutations, so fixing marginal position bias alone does not yield a consistent ranking function. |
| 2026 | [PIANO: Personalized Reranking via Information Aggregation Node for Music Search Optimization](https://arxiv.org/abs/2606.16641) | ECML PKDD | NetEase Cloud Music PIANO reranker whose Information Aggregation Node token attends over the whole candidate list to jointly optimize list-level CTR and CVR in music search. |
| 2026 | [A Multi-Objective Scoring Approach to Contract and Exposure-Aware Re-Ranking in Real-Estate Recommendation](https://doi.org/10.3390/info17070674) | Information (MDPI) | PMOR multi-objective re-ranker for a real-estate marketplace that combines calibrated relevance with contract-specific business weights, contractual exposure-cap penalties, and within-slate similarity penalties under position discounting. |
| 2026 | [Learning from Emptiness: De-biasing Listwise Rerankers with Content-Agnostic Probability Calibration](https://arxiv.org/abs/2604.10150) | ACL | CapCal, a training-free calibration that probes generative listwise LLM rerankers with content-free placeholders to estimate position-bias priors and contrastively adjusts output logits, giving single-pass de-biased list reranking with large NDCG gains for small models. |

### Diversity, Coverage, and Set Quality

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2018 | [Practical Diversified Recommendations on YouTube with Determinantal Point Processes](https://doi.org/10.1145/3269206.3272018) | CIKM | Production-scale DPP diversification for recommendation lists. |
| 2018 | [Fast Greedy MAP Inference for Determinantal Point Process to Improve Recommendation Diversity](https://arxiv.org/abs/1709.05135) | NeurIPS | Scalable DPP inference for diversified top-k recommendation. |
| 2018 | [Fairness of Exposure in Rankings](https://arxiv.org/abs/1802.07281) | KDD | Cornell framework that allocates exposure over a ranked list under a position-based examination model and computes utility-maximizing stochastic rankings subject to demographic-parity, disparate-treatment, and disparate-impact exposure constraints. |
| 2021 | [Sliding Spectrum Decomposition for Diversified Recommendation](https://arxiv.org/abs/2107.05204) | KDD | Xiaohongshu production diversified reranking that models users' perceived diversity over a long browsed feed sequence via sliding spectrum decomposition, with an embedding fix for long-tail similarity. |
| 2022 | [Feature-aware Diversified Re-ranking with Disentangled Representations for Relevant Recommendation](https://arxiv.org/abs/2206.05020) | KDD | Kuaishou FDSB diversified reranker that disentangles feature-level aspects with multi-head attention and self-balances relevance versus diversity per aspect for relevant-recommendation lists, validated by online A/B tests. |
| 2024 | [Optimizing Novelty of Top-k Recommendations using Large Language Models and Reinforcement Learning](https://arxiv.org/abs/2406.14169) | KDD | Microsoft (Bing Ads) RL approach that optimizes the novelty of top-k recommendation lists using LLM feedback as reward, decomposing the list-level reward into item-wise <query, item> rewards to scale to millions of items on query-ad recommendation with minimal recall loss. |
| 2025 | [Diversified recommendations of cultural activities with personalized determinantal point processes](https://arxiv.org/abs/2509.10392) | RecSys Workshop | Personalized DPP selects a diverse subset of up to 60 items for the homepage, evaluated with offline diversity metrics and an online A/B/C CTR test. |
| 2025 | [Streaming Stochastic Submodular Maximization with On-Demand User Requests](https://arxiv.org/abs/2601.10901) | NeurIPS | Single-pass streaming algorithm (1/(8δ) competitive ratio, stream-length-independent memory) that selects up to k items for each arriving user to maximize expected topic coverage under stochastic consumption, motivated by news recommendation. |
| 2025 | [Learning to Rank with Top-K Fairness](https://arxiv.org/abs/2509.18067) | TMLR | Listwise learning-to-rank framework with a top-K exposure-disparity measure and a differentiable surrogate for the non-differentiable top-K selection, trading off relevance against group fairness within the top-K ranked list. |
| 2026 | [Diversification as Risk Minimization](https://arxiv.org/abs/2510.22681) | WSDM | Recasts ranked-list diversification as minimizing the risk faced by the least-served intents (VRisk) and gives a greedy re-ranker (VRisker) with approximation guarantees that cuts worst-case intent failures by up to 33% on TREC/NTCIR and MovieLens. |
| 2026 | [ReList: A Multi-objective Reasoning Framework for Diversified Listwise Query Recommendation](https://aclanthology.org/2026.acl-industry.97/) | ACL Industry | Reasoning-enhanced listwise generation of related-query recommendation lists, trained by back-translating diverse query lists into chain-of-thought rationales and then RL with multi-objective list rewards for diversity and engagement, validated in online A/B tests. |
| 2026 | [Unifying Diversity and Fairness in Re-ranking via Economic Growth Theory](https://doi.org/10.1145/3774904.3792644) | WWW | DivFair re-ranking algorithm that frames list diversity as a Sufficientarian and item fairness as a Rawlsian redistribution objective and optimizes their joint online re-ranking via mirror descent with sub-linear regret. |
| 2026 | [Enhancing Recommendation Diversity by Re-ranking with Large Language Models](https://arxiv.org/abs/2401.11506) | TORS | Zero-shot LLM (GPT/Llama) diversity re-ranking of recommendation lists with several prompting strategies, benchmarked against traditional diversity re-rankers on accuracy, diversity and cost. |
| 2026 | [No Stakeholder Left Behind: Regret-Aware Re-Ranking for Two-Sided Fair Recommendation](https://doi.org/10.1145/3820899) | TOIS | Renmin University and Huawei re-ranking method that casts fair list re-ranking as a regret-aware fuzzy programming problem so that provider exposure fairness, overall accuracy, and individual-user accuracy are guaranteed jointly. |
| 2026 | [The Attention Market: Interpreting Online Fair Re-ranking as Manifold Optimization under Walrasian Equilibrium](https://arxiv.org/abs/2604.25577) | SIGIR | ManifoldRank reformulates online fair re-ranking of ranked lists as a Walrasian-equilibrium market where item-exposure fairness acts as a taxation cost, adjusting gradients to trade accuracy against long-tail and within-group exposure. |
| 2026 | [Enhancing Diversity in News Recommendations Increases Click-Through Rates: Insights from an Online Experiment and User Study](https://doi.org/10.1145/3774935.3806153) | UMAP | Verachtert, Falk and Bauer compare interleaving with TF-IDF- and BERT-based intra-list diversification of news recommendation lists in a production A/B test on NU.nl plus a user survey, finding BERT-based ILD raises both topic diversity and click-through rate along with perceived relevance. |

### Whole-page and Page-level Optimization

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2016 | [Beyond Ranking: Optimizing Whole-Page Presentation](https://doi.org/10.1145/2835776.2835824) | WSDM | Optimizes heterogeneous whole-page presentation rather than a single ranked list. |
| 2016 | [Whole-Page Optimization and Submodular Welfare Maximization with Online Bidders](https://doi.org/10.1145/2892563) | ACM TEAC | Whole-page ad allocation under slot and diversity constraints. |
| 2018 | [Deep Reinforcement Learning for Page-wise Recommendations](https://arxiv.org/abs/1805.02343) | RecSys | DeepPage jointly selects complementary items and a 2D page display strategy. |
| 2018 | [The Whole-Page Optimization via Dynamic Ad Allocation](https://doi.org/10.1145/3184558.3191584) | WWW Companion | Search/ads page optimization for deciding how many ads to show. |
| 2019 | [Whole Page Optimization with Global Constraints](https://doi.org/10.1145/3292500.3330675) | KDD | Amazon Video homepage widget ranking with relevance, diversity, and business constraints. |
| 2020 | [Jointly Learning to Recommend and Advertise](https://arxiv.org/abs/2003.00097) | KDD | Two-level reinforcement learning framework (Zhao et al., KDD 2020) that first generates the recommended list and then decides whether, which, and where to insert ads into it, jointly optimizing long-term user experience and advertising revenue of the mixed page. |
| 2021 | [Toward User Engagement Optimization in 2D Presentation](https://doi.org/10.1145/3437963.3441749) | WSDM | Models position noticeability in grid-like 2D recommendation layouts. |
| 2021 | [Page-level Optimization of e-Commerce Item Recommendations](https://arxiv.org/abs/2108.05891) | RecSys | Optimizes item recommendation modules at page level in e-commerce. |
| 2021 | [DEAR: Deep Reinforcement Learning for Online Advertising Impression in Recommender Systems](https://arxiv.org/abs/1909.03602) | AAAI | DEAR (MSU/ByteDance) DQN that jointly decides whether to insert an ad, which ad, and at which position within a recommendation list to balance long-run revenue and user experience. |
| 2021 | [Hierarchical Reinforcement Learning for Integrated Recommendation](https://ojs.aaai.org/index.php/AAAI/article/view/16580) | AAAI | Tencent WeChat Top Stories HRL-Rec that composes a heterogeneous mixed feed with a low-level channel selector and a high-level item recommender, using rewards that balance accuracy and diversity of the integrated list. |
| 2022 | [Automate Page Layout Optimization: An Offline Deep Q-learning Approach](https://www.amazon.science/publications/automate-page-layout-optimization-an-offline-deep-q-learning-approach) | Amazon Science | Offline RL approach for page layout optimization. |
| 2022 | [Tile Networks: Learning Optimal Geometric Layout for Whole-page Recommendation](https://arxiv.org/abs/2303.01671) | AISTATS | Tile Networks, a reinforcement-learning neural architecture that learns the optimal 2D geometric placement of items on a whole page, outperforming ranking-based and deep-learning layout baselines on real-world data. |
| 2022 | [Cross DQN: Cross Deep Q Network for Ads Allocation in Feed](https://arxiv.org/abs/2109.04353) | WWW | Meituan Cross DQN that allocates ads among organic items in a feed by crossing item embeddings with attention to model arrangement effects, with auxiliary losses to constrain ad exposure ratio, deployed to 300M+ users. |
| 2022 | [Learning List-wise Representation in Reinforcement Learning for Ads Allocation with Multiple Auxiliary Tasks](https://arxiv.org/abs/2204.00888) | CIKM | Meituan RL-based ads allocation in feeds that learns list-wise state representations through reconstruction, prediction, and contrastive auxiliary tasks to improve revenue and sample efficiency. |
| 2023 | [A Bird's-eye View of Reranking: from List Level to Page Level](https://arxiv.org/abs/2211.09303) | WSDM | Page-level attentional re-ranking for multi-list recommendation pages. |
| 2023 | [Multi-channel Integrated Recommendation with Exposure Constraints](https://arxiv.org/abs/2305.12319) | KDD | Taobao homepage MIREC framework that casts multi-channel integrated feed ranking as binary online linear programming, allocating per-channel exposure with an O(sqrt(T))-regret online algorithm while collaborative models rank heterogeneous items into each page. |
| 2026 | [Design and Evaluation of Whole-Page Experience Optimization for E-commerce Search](https://arxiv.org/abs/2602.02514) | WSDM | Optimizes the whole e-commerce search page (relevance, 2D layout, visual elements) with a causal framework (DV-WPX) for page-level quality. |
| 2026 | [KLAN: Kuaishou Landing-page Adaptive Navigator](https://arxiv.org/abs/2507.23459) | KDD | Shuchang Liu et al.; selects personalized landing pages, tabs, channels, or aggregation pages before in-page recommendation. |
| 2026 | [Designing for the Next Click: Bandits for Real-Time Page Layout](https://arxiv.org/abs/2608.29850) | RecSys Workshop | LinUCB contextual bandit that picks e-commerce product-page layouts per session from live user interactions, beating heuristic layouts on a large retail platform (RecSys 2026 OARS workshop; WWW 2026 short accepted then withdrawn). |
| 2026 | [GenPage: Towards End-to-End Generative Homepage Construction at Netflix](https://arxiv.org/abs/2606.31031) | RecSys | Netflix GenPage replaces the multi-stage homepage pipeline with a single transformer that autoregressively generates the entire homepage (rows and items) from user context, pretrained on production logs and tuned with weighted classification or RL, yielding engagement lift and 20% lower serving latency in A/B tests. |

### Carousel, Multi-list, Shelf, and Widget Construction

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2015 | [The Netflix Recommender System: Algorithms, Business Value, and Innovation](https://doi.org/10.1145/2843948) | ACM TMIS | Industrial system paper for a homepage composed of many personalized rows. |
| 2021 | [Automatic Collection Creation and Recommendation](https://doi.org/10.1145/3460231.3478865) | RecSys | Creates and recommends collections/carousels from user-item representations. |
| 2021 | [Optimizing the Selection of Recommendation Carousels with Quantum Computing](https://doi.org/10.1145/3460231.3478853) | RecSys | Formulates carousel selection as a combinatorial optimization problem. |
| 2021 | [Event-based Product Carousel Recommendation with Query-Click Graph](https://arxiv.org/abs/2402.03277) | IEEE BigData | Walmart system that mines event-themed product carousels by iteratively clustering a query-click bipartite graph into event aspects and ranking products within each carousel by click-through rate. |
| 2022 | [The Magic of Carousels: Single vs. Multi-List Recommender Systems](https://doi.org/10.1145/3511095.3531278) | HT | Formal and empirical analysis of why multi-list carousel interfaces can outperform single lists. |
| 2025 | [Full-Page Recommender: A Modular Framework for Multi-Carousel Recommendations](https://dl.acm.org/doi/10.1145/3705328.3748753) | RecSys | Builds a full page of attribute-grouped carousels with soft de-duplication across rows, evaluated on Peacock streaming data. |
| 2025 | [Effective Diversification of Multi-Carousel Book Recommendation](https://arxiv.org/abs/2511.14461) | BNAIC/BeNeLearn | Diversification methods and metrics across multiple book recommendation carousels. |
| 2025 | [Where to Explore: A Reach and Cost-Aware Approach for Unbiased Data Collection in Recommender Systems](https://arxiv.org/abs/2512.14733) | IEEE CogMI | Chooses the scroll-depth region of a multi-row streaming homepage (100M+ MAU service) in which to place a randomized "Something Completely Different" exploration row, trading reach against opportunity cost to collect unbiased interaction data without hurting business metrics. |
| 2026 | [Hypothesis-Driven Shelf Generation for Personalised Recommendation](https://arxiv.org/abs/2607.25823) | RecSys | Spotify system that generates Home shelves from natural-language hypotheses of what a personalised shelf should contain, via hypothesis generation, catalogue fulfilment with generative retrieval, shelf alignment, and offline serving, decoupling shelf planning from retrieval and matching production shelf engagement. |

## Slate Feedback, Learning, and Evaluation: How to Deal with User Feedback

This branch asks what can be inferred after a slate or page has been shown. It
covers biased and partial observations, click and browsing assumptions, online
learning from feedback, counterfactual evaluation, simulators, and user-facing
studies of multi-item recommendation surfaces.

### Logged Feedback, Click Models, Bandits, and Off-policy Learning

These papers focus on the feedback loop after a slate is shown: what the user
examines, clicks, ignores, or selects, and how those observations can be used to
learn or evaluate a better slate policy under user-behavior assumptions.

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2015 | [Cascading Bandits: Learning to Rank in the Cascade Model](https://proceedings.mlr.press/v37/kveton15.html) | ICML | Assumes users scan a ranked list top-down and click the first attractive item, yielding partial feedback for slate learning. |
| 2015 | [Combinatorial Cascading Bandits](https://proceedings.neurips.cc/paper_files/paper/2015/hash/1f50893f80d6830d62765ffad7721742-Abstract.html) | NeurIPS | Generalizes cascading feedback to constrained tuple/slate selection with nonlinear rewards and partial observability. |
| 2016 | [Cascading Bandits for Large-Scale Recommendation Problems](https://auai.org/uai2016/proceedings/papers/96.pdf) | UAI | Adds feature-based generalization to cascade bandits so top-k recommendation can scale to large item sets. |
| 2016 | [Contextual Combinatorial Cascading Bandits](https://proceedings.mlr.press/v48/lif16.html) | ICML | Selects contextual item lists and observes only a prefix determined by a stopping criterion, with position discounts. |
| 2016 | [DCM Bandits: Learning to Rank with Multiple Clicks](https://proceedings.mlr.press/v48/katariya16.html) | ICML | Uses the dependent click model to learn rankings from multiple clicks and latent user satisfaction. |
| 2016 | [Multiple-Play Bandits in the Position-Based Model](https://papers.nips.cc/paper/6546-multiple-play-bandits-in-the-position-based-model) | NeurIPS | Models position bias and ambiguous non-clicks in multi-position recommendation displays. |
| 2016 | [A Neural Click Model for Web Search](https://doi.org/10.1145/2872427.2883033) | WWW | Yandex/University of Amsterdam neural click model (NCM) that replaces hand-crafted PGM click models with a recurrent network whose vector state of user need and result list is updated through the ranked result list to predict clicks and infer relevance. |
| 2017 | [Efficient Ordered Combinatorial Semi-Bandits for Whole-Page Recommendation](https://doi.org/10.1609/aaai.v31i1.10939) | AAAI | Ordered combinatorial semi-bandit for selecting items and display positions on a page. |
| 2017 | [Off-policy Evaluation for Slate Recommendation](https://papers.nips.cc/paper/6954-off-policy-evaluation-for-slate-recommendation) | NeurIPS | Practical counterfactual evaluation for ordered slates from logged data. |
| 2017 | [Online Learning to Rank in Stochastic Click Models](https://proceedings.mlr.press/v70/zoghi17a.html) | ICML | Learns ranked lists under a broad class of click models, including cascade and position-based models. |
| 2017 | [Unbiased Learning-to-Rank with Biased Feedback](https://arxiv.org/abs/1608.04468) | WSDM | Foundational counterfactual learning-to-rank framework (Joachims, Swaminathan, Schnabel) that uses inverse-propensity weighting of position-biased clicks on ranked lists to train an unbiased Propensity-Weighted Ranking SVM. |
| 2018 | [Explore, Exploit, and Explain: Personalizing Explainable Recommendations with Bandits](https://doi.org/10.1145/3240323.3240354) | RecSys | Spotify system for selecting explainable recommendation shelves with bandits. |
| 2018 | [Offline Evaluation of Ranking Policies with Click Models](https://www.kdd.org/kdd2018/accepted-papers/view/offline-evaluation-of-ranking-policies-with-click-models) | KDD | Shuai Li et al.; uses click-model assumptions to build statistically efficient offline estimators for ranked-list policies. |
| 2018 | [TopRank: A Practical Algorithm for Online Stochastic Ranking](https://proceedings.neurips.cc/paper/by-source-2018-1947) | NeurIPS | Uses a generalized click model covering cascade and PBM-style feedback to learn rankings from clicks. |
| 2018 | [Unbiased Learning to Rank with Unbiased Propensity Estimation](https://arxiv.org/abs/1804.05938) | SIGIR | Dual Learning Algorithm (DLA) that jointly learns an unbiased ranker and a position-bias propensity model from ranked-list clicks, treating propensity estimation as the dual problem of unbiased learning to rank without result randomization. |
| 2018 | [Position Bias Estimation for Unbiased Learning to Rank in Personal Search](https://research.google/pubs/position-bias-estimation-for-unbiased-learning-to-rank-in-personal-search/) | WSDM | Google regression-EM method that estimates position-bias propensities for unbiased learning to rank from regular personal-search click logs without result randomization. |
| 2018 | [Offline A/B testing for Recommender Systems](https://arxiv.org/abs/1801.07030) | WSDM | Criteo counterfactual estimators (variants of capped and normalised importance sampling) for predicting the uplift of new product-recommendation slate policies, validated against business metrics from live A/B tests. |
| 2019 | [Offline Evaluation to Make Decisions About Playlist Recommendation Algorithms](https://doi.org/10.1145/3289600.3291027) | WSDM | Spotify offline evaluation paper for playlist recommendation, comparing debiased offline estimates with online A/B outcomes. |
| 2019 | [Top-K Off-Policy Correction for a REINFORCE Recommender System](https://arxiv.org/abs/1812.02353) | WSDM | Production YouTube top-k policy-gradient recommender with off-policy correction for multiple displayed items. |
| 2019 | [SlateQ: A Tractable Decomposition for Reinforcement Learning with Recommendation Sets](https://doi.org/10.24963/ijcai.2019/360) | IJCAI | Decomposes long-term value of a slate into item-level values under a user-choice model. |
| 2019 | [Cascading Non-Stationary Bandits: Online Learning to Rank in the Non-Stationary Cascade Model](https://www.ijcai.org/proceedings/2019/396) | IJCAI | Extends cascading bandits to changing user preferences with sliding-window and discounted UCB methods. |
| 2019 | [BubbleRank: Safe Online Learning to Re-Rank via Implicit Click Feedback](https://arxiv.org/abs/1806.05819) | UAI | Safe online learning-to-rerank bandit that starts from a base ranked list and gradually swaps adjacent items based on click feedback under click models, with regret bounds that improve with the quality of the initial list (Li, Kveton, Lattimore, Markov, de Rijke, Szepesvari, Zoghi). |
| 2020 | [Carousel Personalization in Music Streaming Apps with Contextual Bandits](https://doi.org/10.1145/3383313.3412217) | RecSys | Contextual bandits for ordering and personalizing carousels in music apps. |
| 2020 | [Cascading Linear Submodular Bandits: Accounting for Position Bias and Diversity in Online Learning to Rank](https://proceedings.mlr.press/v115/hiranandani20a.html) | UAI | Combines cascade-style click feedback, position bias, and diversity through a submodular ranking model. |
| 2020 | [Cascading Hybrid Bandits: Online Learning to Rank for Relevance and Diversity](https://doi.org/10.1145/3383313.3412245) | RecSys | Hybrid cascade bandit that optimizes both relevance features and subtopic diversity from click feedback. |
| 2020 | [Counterfactual Evaluation of Slate Recommendations with Sequential Reward Interactions](https://doi.org/10.1145/3394486.3403229) | KDD | James McInerney et al.; evaluates slate policies when rewards interact sequentially across positions. |
| 2020 | [Learning to Rank in the Position Based Model with Bandit Feedback](https://doi.org/10.1145/3340531.3412723) | CIKM | Extends contextual bandits to ranked recommendation under PBM-style position bias. |
| 2020 | [Doubly Robust Estimator for Ranking Metrics with Post-Click Conversions](https://doi.org/10.1145/3383313.3412262) | RecSys | Yuta Saito; debiases ranking-quality metrics (e.g., DCG) estimated from post-click conversions, correcting the selection bias between clicked and unclicked items with an IPS / doubly-robust estimator. |
| 2020 | [Debiasing Grid-based Product Search in E-commerce](https://doi.org/10.1145/3394486.3403336) | KDD | Etsy click models for grid-based product search that capture row skipping and slower position decay in 2D result pages and are used for unbiased learning to rank on grids. |
| 2020 | [Policy-Aware Unbiased Learning to Rank for Top-k Rankings](https://arxiv.org/abs/2005.09035) | SIGIR | Policy-aware counterfactual estimator that stays unbiased for learning to rank when only a top-k slate is exposed by a stochastic logging policy, correcting both position bias and item-selection bias. |
| 2020 | [ContentWise Impressions: An Industrial Dataset with Impressions Included](https://arxiv.org/abs/2008.01212) | CIKM | Politecnico di Milano and ContentWise open industrial OTT dataset that logs the full impressions (recommendation rows shown to each user) alongside interactions, enabling exposure-aware training and evaluation. |
| 2020 | [Evaluating Stochastic Rankings with Expected Exposure](https://arxiv.org/abs/2004.13157) | CIKM | Expected-exposure metric that evaluates distributions over rankings under user browsing models, giving a list-level evaluation target for stochastic ranking and slate policies. |
| 2021 | [Top-K Contextual Bandits with Equity of Exposure](https://doi.org/10.1145/3460231.3474248) | RecSys | Top-k contextual bandits with exposure fairness constraints. |
| 2021 | [Open Bandit Dataset and Pipeline: Towards Realistic and Reproducible Off-Policy Evaluation](https://arxiv.org/abs/2008.07146) | NeurIPS | Yuta Saito et al.; large-scale logged-bandit benchmark from a three-position fashion recommender (ZOZOTOWN) with multiple logging policies, plus the Open Bandit Pipeline — a widely used testbed for recommendation and ranking OPE. |
| 2021 | [Control Variates for Slate Off-Policy Evaluation](https://arxiv.org/abs/2106.07914) | NeurIPS | Netflix and Cornell control-variate estimators for slate off-policy evaluation that improve on the pseudoinverse and self-normalized estimators with theoretical guarantees. |
| 2021 | [FINN.no Slates Dataset: A new Sequential Dataset Logging Interactions, all Viewed Items and Click Responses/No-Click for Recommender Systems Research](https://arxiv.org/abs/2111.03340) | RecSys | FINN.no marketplace dataset logging every exposed slate together with click and no-click responses to support exposure-aware slate recommendation research. |
| 2021 | [Cross-Positional Attention for Debiasing Clicks](https://doi.org/10.1145/3442381.3450098) | WWW | Google XPA model that learns examination bias with attention across all displayed items so click debiasing works for arbitrary grid and multi-position UIs rather than a single ranked list. |
| 2021 | [Thompson Sampling Algorithms for Cascading Bandits](https://arxiv.org/abs/1810.01187) | JMLR | Thompson-sampling algorithms (Beta-Bernoulli, Gaussian TS-Cascade, and a linear generalization) for cascading bandits over ranked lists with regret upper bounds, nearly matching lower bounds, and empirical gains over UCB-based cascading bandits. |
| 2022 | [Doubly Robust Off-Policy Evaluation for Ranking Policies under the Cascade Behavior Model](https://doi.org/10.1145/3488560.3498380) | WSDM | Haruka Kiyohara, Yuta Saito, et al.; combines cascade user behavior with a doubly robust ranking-policy estimator. |
| 2022 | [Offline Evaluation of Ranked Lists using Parametric Estimation of Propensities](https://arxiv.org/abs/2206.02470) | SIGIR | Fits parametric propensity models with learning-to-rank methods so that inverse-propensity offline evaluation of new rankers from historical clickthrough on ranked lists stays accurate when the new ranking diverges from the logged one. |
| 2022 | [Off-policy evaluation for learning-to-rank via interpolating the item-position model and the position-based model](https://arxiv.org/abs/2210.09512) | RecSys Workshop | INTERPOL estimator (Amazon/Cornell, CONSEQUENCES@RecSys 2022) that interpolates between the item-position model and the position-based model to trade off bias and variance in off-policy evaluation of ranking policies. |
| 2023 | [Combinatorial Categorized Bandits with Expert Rankings](https://www.microsoft.com/en-us/research/publication/combinatorial-categorized-bandits-with-expert-rankings/) | UAI | Aggregates expert/category rankings into a short top-k list under combinatorial bandit objectives. |
| 2023 | [Off-Policy Evaluation of Ranking Policies under Diverse User Behavior](https://doi.org/10.1145/3580305.3599447) | KDD | Haruka Kiyohara, Yuta Saito, et al.; adapts ranking OPE to context-dependent user behavior assumptions. |
| 2023 | [Doubly-Robust Estimation for Correcting Position-Bias in Click Feedback for Unbiased Learning to Rank](https://arxiv.org/abs/2203.17118) | TOIS | Harrie Oosterhuis; introduces the first doubly-robust estimator for position-biased click feedback in unbiased learning to rank, using expected treatment per rank instead of actual treatment, with stronger guarantees and orders-of-magnitude better sample efficiency than IPS-based counterfactual LTR. |
| 2023 | [Unified Off-Policy Learning to Rank: a Reinforcement Learning Perspective](https://arxiv.org/abs/2306.07528) | NeurIPS | CUOLR casts ranking under general click models as a Markov decision process and uses offline reinforcement learning to learn rankings from logged clicks in a click-model-agnostic way, avoiding per-model debiasing and outperforming existing off-policy LTR methods across click models. |
| 2023 | [An Offline Metric for the Debiasedness of Click Models](https://arxiv.org/abs/2304.09560) | SIGIR | Naver Labs and University of Amsterdam conditional-independence test of whether a click model's relevance estimates are debiased from the logging ranking policy, used for offline click-model selection under ranking-distribution shift. |
| 2023 | [Model-based Unbiased Learning to Rank](https://arxiv.org/abs/2207.11785) | WSDM | Model-based unbiased learning to rank (Baidu/Lehigh/Tsinghua) that trains a context-aware click simulator to generate pseudo-clicks for unobserved ranked lists and combines it with doubly robust IPW to stay robust on tail queries. |
| 2024 | [Off-Policy Evaluation of Slate Bandit Policies via Optimizing Abstraction](https://doi.org/10.1145/3589334.3645343) | WWW | Haruka Kiyohara, Yuta Saito; learns low-dimensional slate abstractions for lower-variance slate-bandit OPE. |
| 2024 | [Effective Off-Policy Evaluation and Learning in Contextual Combinatorial Bandits](https://doi.org/10.1145/3640457.3688099) | RecSys | Haruka Kiyohara, Yuta Saito, et al.; evaluates and learns policies that choose combinatorial action subsets. |
| 2024 | [Long-term Off-Policy Evaluation and Learning](https://doi.org/10.1145/3589334.3645446) | WWW | Yuta Saito et al.; estimates long-term policy value from historical logs and short-term experimental outcomes. |
| 2024 | [Whole Page Unbiased Learning to Rank](https://arxiv.org/abs/2210.10718) | WWW | Whole-page unbiased learning to rank (BAL) that uses causal discovery to recover the user behavior model and jointly correct biases induced by multiple SERP presentation features beyond position. |
| 2024 | [Distributional Off-Policy Evaluation for Slate Recommendations](https://arxiv.org/abs/2308.14165) | AAAI | Unbiased and consistent estimator of the full off-policy return distribution (not just the mean) for slate policies, with reduced variance and better sample efficiency on synthetic and MovieLens-20M slates. |
| 2024 | [Neural Click Models for Recommender Systems](https://arxiv.org/abs/2409.20055) | SIGIR | Recurrent, Transformer, adversarial, and hierarchical neural click models of user responses over recommendation lists on ContentWise and RL4RS, usable as simulators for evaluation and pretraining. |
| 2024 | [Pessimistic Off-Policy Optimization for Learning to Rank](https://arxiv.org/abs/2206.02593) | ECAI | Pessimistic off-policy learning of ranked lists from logged clicks that selects lists with the highest lower-confidence-bound value under click-model parameters, with Bayesian and frequentist variants and empirical-Bayes priors. |
| 2024 | [On (Normalised) Discounted Cumulative Gain as an Off-Policy Evaluation Metric for Top-n Recommendation](https://arxiv.org/abs/2307.15053) | KDD | ShareChat analysis deriving when DCG on logged top-n lists is an unbiased off-policy estimate of online performance, showing normalisation (nDCG) can invert method rankings while unbiased DCG correlates with online results at scale. |
| 2024 | [Practical and Robust Safety Guarantees for Advanced Counterfactual Learning to Rank](https://arxiv.org/abs/2407.19943) | CIKM | Generalizes safe counterfactual learning to rank to doubly-robust estimators and trust bias and introduces PRPO, a proximal ranking policy optimization that bounds how far a ranking policy learned from logged clicks can degrade from the deployed logging policy without behavioral assumptions. |
| 2024 | [Mitigating Exposure Bias in Online Learning to Rank Recommendation: A Novel Reward Model for Cascading Bandits](https://arxiv.org/abs/2408.04332) | CIKM | Exposure-aware reward model for linear cascading bandits that discounts item utility by its position and exposure in the recommended list, improving long-run exposure fairness of online learning to rank while keeping accuracy and a high-probability regret bound. |
| 2024 | [Unbiased Learning to Rank Meets Reality: Lessons from Baidu's Large-Scale Search Dataset](https://arxiv.org/abs/2404.02543) | SIGIR | Reproducibility study of unbiased learning-to-rank methods on Baidu's large-scale real search click logs, finding that ULTR robustly improves click prediction but does not consistently improve expert-judged ranking quality. |
| 2025 | [Addressing Personalized Bias for Unbiased Learning to Rank](https://arxiv.org/abs/2508.20798) | CIKM | Corrects personalized position/examination bias in ranked-list click feedback with a user-aware IPS estimator. |
| 2025 | [Unidentified and Confounded? Understanding Two-Tower Models for Unbiased Learning to Rank](https://arxiv.org/abs/2506.20501) | ICTIR | Analyzes identifiability and logging-policy confounding when two-tower models interpret ranked-list click feedback. |
| 2025 | [Efficient Algorithms for Logistic Contextual Slate Bandits with Bandit Feedback](https://arxiv.org/abs/2506.13163) | UAI | Slate-GLM-OFU and Slate-GLM-TS algorithms for logistic contextual slate bandits with a single binary slate-level reward, combining per-slot local planning with global learning to reach polynomial per-round cost and O(sqrt T) regret. |
| 2025 | [Towards Two-Stage Counterfactual Learning to Rank](https://arxiv.org/abs/2506.20854) | ICTIR | Two-stage counterfactual learning-to-rank estimator that models the interaction between candidate generator and ranker and jointly optimizes both from position-biased logged clicks, validated on semi-synthetic benchmarks. |
| 2025 | [Unbiased Learning to Rank with Query-Level Click Propensity Estimation: Beyond Pointwise Observation and Relevance](https://arxiv.org/abs/2502.11414) | WWW | Query-level click propensity model with dual inverse propensity weighting that corrects both position bias and relevance-saturation bias (users stop clicking once satisfied) in ranked-list click logs, validated on Baidu-ULTR. |
| 2025 | [LLMs for estimating positional bias in logged interaction data](https://arxiv.org/abs/2509.03696) | RecSys Workshop | Viator (Tripadvisor) study that uses an LLM as a judge to estimate per-position examination propensities from logged interactions, capturing row-column effects of the grid layout and feeding IPS-weighted reranking for about 2% weighted NDCG@10 gains. |
| 2026 | [Correcting for Position Bias in Learning to Rank: A Control Function Approach](https://arxiv.org/abs/2506.06989) | RecSys | Counterfactual learning-to-rank that corrects position bias in ranked-list click feedback via a control function. |
| 2026 | [Off-Policy Evaluation for Ranking Policies under Deterministic Logging Policies](https://arxiv.org/abs/2603.21485) | ICLR | Yuta Saito et al.; uses click stochasticity for ranking-policy OPE when the logging policy itself is deterministic. |
| 2026 | [Additive Control Variates Dominate Self-Normalisation in Off-Policy Evaluation](https://arxiv.org/abs/2602.14914) | SIGIR | Jeunen and Gupta; shows additive control variates outperform self-normalisation (SNIPS) for ranking and recommendation OPE. |
| 2026 | [From Latent to Observable Position-Based Click Models in Carousel Interfaces](https://arxiv.org/abs/2602.16541) | KDD | Position-based click models for carousels, including an Observed Examination PBM informed by eye-tracking browsing patterns. |
| 2026 | [An Epistemic Position-Based Click Model: From Interactions to Epistemic Distributions of Relevance and Bias](https://arxiv.org/abs/2607.18712) | SIGIR | Radboud evidential-deep-learning extension of the position-based click model that outputs beta distributions over item relevance and position bias, capturing epistemic uncertainty on unseen items and positions where point-estimate PBMs fail. |
| 2026 | [CLAX: Fast and Flexible Neural Click Models in JAX](https://arxiv.org/abs/2511.03620) | SIGIR | University of Amsterdam JAX library that reimplements ten classical click models for ranked lists with gradient-based training and neural extensions, scaling to the billion-session Baidu-ULTR data on one GPU. |
| 2026 | [Diagnosing Identifiability in Two-Tower Models for Unbiased Learning to Rank](https://doi.org/10.1145/3805712.3809640) | SIGIR | Practical diagnostic that perturbs and retrains individual position-bias parameters of two-tower ULTR models to test whether relevance and bias are identifiable from ranked-list click logs. |
| 2026 | [Adaptive Doubly Robust Off-Policy Evaluation for Ranking Policies under Diverse User Behavior](https://arxiv.org/abs/2608.29600) | RecSys Workshop | Adaptive Doubly Robust (ADR) estimator that combines adaptive importance weighting with reward regression to keep ranking-policy OPE unbiased yet low-variance under heterogeneous user browsing behavior. |
| 2026 | [Contextual Slate GLM Bandits with Limited Adaptivity](https://arxiv.org/abs/2606.31449) | ICML | B-SlateGLinCB and RS-SlateGLinCB algorithms for contextual slate bandits with generalized-linear rewards under batched and rarely-switching adaptivity limits, achieving kappa-independent regret bounds. |
| 2026 | [DCM Bandits: Multiplayer Information Asymmetric Cascading Bandits for Multiple Clicks](https://arxiv.org/abs/2608.11873) | ACMLC | Extends dependent-click-model cascading bandits over ranked lists to multiplayer settings with action and reward information asymmetry, giving sublinear regret and relaxing the need for a known termination ranking. |
| 2026 | [Exposure-Based Reinforcement Learning to Rank](https://arxiv.org/abs/2607.18689) | ICTIR | Radboud and Google RL-to-rank method that abstracts stochastic ranking policies through a document-exposure distribution so list-level objectives become differentiable functions of exposure with variance reduction and GPU-efficient autodiff training. |
| 2026 | [Generalized Position-Based Model: Rethinking Position Weights in Ranking Off-Policy Evaluation](https://github.com/amazon-science/gpbm) | RecSys | Amazon RecSys 2026 GPBM estimator that generalizes position-based-model weights into a learned F-matrix for off-policy evaluation of ranking policies that is robust to uncertain position bias, compared against IPS, PBM, and INTERPOL. |
| 2026 | [A Reward-Informed Semi-Personalized Bandit Approach for Enhancing Accuracy and Serendipity in Online Slate Recommendations](https://doi.org/10.1145/3771931) | TORS | Semi-personalized bandit (De Kerpel and Benoit) that learns per-item decision trees to segment users and runs segment-level Thompson sampling to build online recommendation slates that trade off regret and serendipity. |

### Simulators, User Behavior, and Interface Evaluation

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2016 | [Using Navigation to Improve Recommendations in Real-Time](https://doi.org/10.1145/2959100.2959174) | RecSys | Uses navigation behavior to update recommendations in carousel-like production surfaces. |
| 2016 | [Personalizing User Interfaces for Improving Quality of Experience in VoD Recommender Systems](https://doi.org/10.1109/QoMEX.2016.7498940) | QoMEX | Personalizes VoD recommender UI presentation. |
| 2021 | [Controlling Personalized Recommendations in Two Dimensions with a Carousel-Based Interface](https://ceur-ws.org/Vol-2948/short3.pdf) | IntRS | Lets users control recommendation topics in a two-dimensional carousel interface. |
| 2021 | [Exploring Multi-List User Interfaces for Similar-Item Recommendations](https://doi.org/10.1145/3450613.3456809) | UMAP | User study comparing multi-list interfaces for similar-item recommendation. |
| 2021 | [Measuring the User Satisfaction in a Recommendation Interface with Multiple Carousels](https://doi.org/10.1145/3452918.3465493) | IMX | Studies satisfaction and evaluation for interfaces with multiple carousels. |
| 2021 | [Serving Each User: Supporting Different Eating Goals Through a Multi-List Recommender Interface](https://doi.org/10.1145/3460231.3474232) | RecSys | Multi-list food recommendation interface for different user goals. |
| 2022 | [Offline Evaluation of Recommender Systems in a User Interface With Multiple Carousels](https://doi.org/10.3389/fdata.2022.910030) | Frontiers in Big Data | Proposes 2D/carousel-aware offline evaluation such as N2DCG. |
| 2022 | [Examining Choice Overload Across Single-List and Multi-List User Interfaces](https://ceur-ws.org/Vol-3177/paper10.pdf) | IntRS | Compares choice overload across list, grid, and carousel-style interfaces. |
| 2023 | [KuaiSim: A Comprehensive Simulator for Recommender Systems](https://arxiv.org/abs/2309.12645) | NeurIPS | Shuchang Liu et al.; simulator covering request-level listwise recommendation, whole-session sequential recommendation, and cross-session retention. |
| 2023 | [How Users Ride the Carousel: Exploring the Design of Multi-List Recommender Interfaces From a User Perspective](https://doi.org/10.1145/3604915.3610638) | RecSys | User study on carousel type, length, and design in multi-list interfaces. |
| 2023 | [Examining the User Evaluation of Multi-List Recommender Interfaces in the Context of Healthy Recipe Choices](https://doi.org/10.1145/3581930) | ACM TORS | User evaluation of multi-list recipe recommendation with personalized labels. |
| 2023 | [Towards Measuring Fairness in Grid Layout in Recommender Systems](https://arxiv.org/abs/2309.10271) | RecSys Workshop | Raj and Ekstrand extend provider-exposure fairness metrics from ranked lists to grid layouts and show that fairness of a ranking can change with column count and layout-specific attention models. |
| 2023 | [Understanding User Behavior in Carousel Recommendation Systems for Click Modeling and Learning to Rank](https://arxiv.org/abs/2307.01866) | RecSys | RecSys 2023 Doctoral Symposium plan for carousel click models and learning to rank from carousel clicks, grounded in an eye-tracking study of movie carousel browsing to be released as a public dataset. |
| 2023 | [RL4RS: A Real-World Dataset for Reinforcement Learning based Recommender System](https://arxiv.org/abs/2110.11073) | SIGIR | NetEase (Fuxi AI Lab) RL4RS open dataset and benchmark in which items are exposed as slates with slate-level feedback, bundled with tuned simulation environments, RL and batch RL baselines, and counterfactual policy evaluation for slate RL. |
| 2024 | [Towards Simulation-Based Evaluation of Recommender Systems with Carousel Interfaces](https://doi.org/10.1145/3643709) | ACM TORS | Simulates user interaction with carousel interfaces for evaluation. |
| 2024 | [CARE: An Infrastructure for Evaluation of Carousel-Based Recommender Interfaces](https://doi.org/10.1145/3640544.3645223) | IUI Companion | Rahdari and Brusilovsky (Pitt) CARE infrastructure for configuring and running user-study and simulation-based evaluations of carousel-based recommender interfaces. |
| 2025 | [Rethinking Click Models in Light of Carousel Interfaces: Theory-Based Categorization and Design of Click Models](https://arxiv.org/abs/2506.18548) | ICTIR | Categorizes click models across single-list, grid, and carousel surfaces and designs a new carousel click model. |
| 2025 | [RecGaze: The First Eye Tracking and User Interaction Dataset for Carousel Interfaces](https://arxiv.org/abs/2504.20792) | SIGIR | Eye-tracking and interaction dataset for carousel recommender interfaces. |
| 2025 | [Under the Hood of Carousels: Investigating User Engagement and Navigation Effort in Multi-list Recommender Systems](https://doi.org/10.1145/3708359.3712130) | IUI | Rahdari and Brusilovsky (Pittsburgh) IUI 2025 study of carousel versus ranked-list interfaces showing that thematically organized carousels reduce navigation effort and speed up adaptive profile updates. |
| 2025 | [Foraging in multi-list recommender interfaces: the effects of digital nudges and aging](https://doi.org/10.1016/j.ijhcs.2025.103588) | IJHCS | User study (N=441) framing browsing of multi-list carousel interfaces as information foraging, showing older users under-explore across carousels and that a digital nudge to switch carousels improves performance for all ages. |
| 2026 | [Riding the Carousel: The First Extensive Eye Tracking Analysis of Browsing Behavior in Carousel Recommenders](https://arxiv.org/abs/2507.10135) | IUI | Eye-tracking analysis of browsing behavior in carousel recommendation pages. |
| 2026 | [Following the Eye-Tracking Evidence: Established Web-Search Assumptions Fail in Carousel Interfaces](https://arxiv.org/abs/2604.21019) | SIGIR | Eye-tracking analysis showing that the F-pattern, examination hypothesis, and heading-reading assumptions from web search fail in carousel interfaces, where clicked items follow a carousel-specific L-pattern. |

## arXiv Preprints and Non-peer-reviewed Papers

These papers are relevant to slate, list, page, or multi-list recommendation,
but are kept separate from the peer-reviewed conference, workshop, and journal
papers above.

| Year | Area | Paper | Main idea |
| --- | --- | --- | --- |
| 2018 | Slate Construction | [Seq2Slate: Re-ranking and Slate Optimization with RNNs](https://arxiv.org/abs/1810.02019) | Uses a pointer-network style sequence model to choose a slate item by item while conditioning on previous choices. |
| 2018 | Slate Construction | [Deep Reinforcement Learning for List-wise Recommendations](https://arxiv.org/abs/1801.00209) | LIRD (JD.com/MSU) actor-critic recommender that generates a whole list of items per step and introduces a user-agent environment simulator for offline pre-training and evaluation on e-commerce data. |
| 2019 | Slate Feedback, Learning, and Evaluation | [Bandit Learning for Diversified Interactive Recommendation](https://arxiv.org/abs/1907.01647) | Diversified contextual combinatorial bandit for interactive recommendation. |
| 2019 | Slate Feedback, Learning, and Evaluation | [RecSim: A Configurable Simulation Platform for Recommender Systems](https://arxiv.org/abs/1909.04847) | Google Research configurable simulation platform (companion to SlateQ) whose environments model user state dynamics and user choice/response models over recommended slates for training and evaluating RL recommendation agents. |
| 2021 | Slate Construction | [Revisit Recommender System in the Permutation Prospective (PRS)](https://arxiv.org/abs/2102.12057) | Permutation-wise reranking framework: PMatch generates candidate lists via goal-oriented beam search and PRank scores whole permutations, deployed at Taobao. |
| 2021 | Slate Construction | [GRN: Generative Rerank Network for Context-wise Recommendation](https://arxiv.org/abs/2104.00860) | Generator-evaluator reranker; a pointer-network generator builds the list step by step while a context-aware evaluator scores the whole ranked list. |
| 2021 | Slate Feedback, Learning, and Evaluation | [Combining Reward and Rank Signals for Slate Recommendation](https://arxiv.org/abs/2107.12455) | Probabilistic slate model that uses both whether the slate received a reward and which rank was selected. |
| 2022 | Slate Feedback, Learning, and Evaluation | [From Ranked Lists to Carousels: A Carousel Click Model](https://arxiv.org/abs/2209.13426) | Click model for browsing behavior in carousel recommenders. |
| 2022 | Slate Feedback, Learning, and Evaluation | [Towards Adaptive Off-Policy Evaluation of Ranking Policies under Agnostic and Stochastic Behavior Models](https://www.kdd.org/kdd2022/papers/01_Haruka%20Kiyohara.pdf) | Haruka Kiyohara; adaptive IPS for ranking-policy OPE when the user behavior model is unknown or stochastic. |
| 2022 | Slate Construction | [SlateFree: a Model-Free Decomposition for Reinforcement Learning with Slate Actions](https://arxiv.org/abs/2209.01876) | Proves slate-MDPs decompose into K item-level Q-functions and proposes SlateFree, a model-free RL algorithm for N-item slate actions that converges without a user model. |
| 2022 | Slate Feedback, Learning, and Evaluation | [Probabilistic Rank and Reward: A Scalable Model for Slate Recommendation](https://arxiv.org/abs/2208.06263) | Criteo PRR probabilistic slate model that combines reward and rank signals to estimate off-policy the reward of K-item slates with at most one click, while serving at scale via maximum inner product search. |
| 2023 | Slate Feedback, Learning, and Evaluation | [Impression-Aware Recommender Systems](https://arxiv.org/abs/2308.07857) | Useful background for logged impressions/exposures, which are essential for slate and page-level evaluation. |
| 2023 | Slate Feedback, Learning, and Evaluation | [Unbiased Offline Evaluation for Learning to Rank with Business Rules](https://arxiv.org/abs/2311.01828) | Shows that post-processing business rules applied to ranked lists break standard off-policy evaluation assumptions and proposes a Birkhoff-von Neumann decomposition correction to recover unbiased ranking OPE estimates. |
| 2024 | Slate Construction | [Diffusion Model for Slate Recommendation](https://arxiv.org/abs/2408.06883) | Models the joint distribution of items in a slate and supports multi-item user engagement. |
| 2024 | Slate Construction | [Hierarchical Reinforcement Learning for Temporal Abstraction of Listwise Recommendation](https://arxiv.org/abs/2409.07416) | Uses hierarchical RL to separate long-term perception from short-term list construction. |
| 2024 | Slate Feedback, Learning, and Evaluation | [Beyond Positive History: Re-ranking with List-level Hybrid Feedback](https://arxiv.org/abs/2410.20778) | Uses both positive and negative feedback from previously exposed lists for re-ranking. |
| 2024 | Slate Feedback, Learning, and Evaluation | [Neural Combinatorial Clustered Bandits for Recommendation Systems](https://arxiv.org/abs/2410.14586) | Neural contextual combinatorial bandit for recommending item subsets. |
| 2024 | Slate Construction | [Cooperative Multi-Agent Deep Reinforcement Learning in Content Ranking Optimization](https://arxiv.org/abs/2408.04251) | Whole-page ranking with cooperative RL agents across positions. |
| 2025 | Slate Construction | [From Generation to Consumption: Personalized List Value Estimation for Re-ranking](https://arxiv.org/abs/2508.02242) | Shuchang Liu et al.; estimates consumed list value by modeling user exit probabilities and sub-list rewards. |
| 2025 | Slate Construction | [Enhanced Whole Page Optimization via Mixed-Grained Reward Mechanism-Adapted Language Models](https://arxiv.org/abs/2506.09084) | LLM-based whole-page optimization with mixed-grained rewards. |
| 2025 | Slate Construction | [HiGR: Industrial-Scale Hierarchical Generative Slate Recommendation Framework in Tencent](https://arxiv.org/abs/2512.24787) | Tencent; decouples generative slate construction into list-level planning and item-level decoding with multi-objective preference alignment. |
| 2025 | Slate Construction | [An Efficient Framework for Whole-Page Reranking via Single-Modal Supervision](https://arxiv.org/abs/2510.16803) | Baidu; SMAR reranks multi-modal whole-page search results with page-level NDCG and online CTR on Baidu Apps. |
| 2025 | Slate Construction | [RIA: A Ranking-Infused Approach for Optimized Listwise CTR Prediction](https://arxiv.org/abs/2511.21394) | Meituan ads; listwise CTR reranker with hierarchical item dependencies and position-sensitive preference learning over the whole list. |
| 2025 | Slate Construction | [Diversity Recommendation via Causal Deconfounding of Co-purchase Relations and Counterfactual Exposure](https://arxiv.org/abs/2512.17733) | Cadence; LightGCN-based diversity-aware recommender that optimizes list-level diversity alongside accuracy via causal deconfounding. |
| 2025 | Slate Feedback, Learning, and Evaluation | [Off-Policy Evaluation of Ranking Policies via Embedding-Space User Behavior Modeling](https://arxiv.org/abs/2506.00446) | Proposes GMIPS/MRIPS estimators — generalizing Saito & Joachims' MIPS (ICML 2022) from single large-action-space choices to rankings — with cascade behavior over ranking embeddings for large ranking action spaces. |
| 2025 | Slate Feedback, Learning, and Evaluation | [Online Learning to Rank under Corruption: A Robust Cascading Bandits Approach](https://arxiv.org/abs/2511.03074) | Cascading-bandit OLTR that presents a ranked list and learns from click feedback robustly under adversarial corruption (click fraud). |
| 2025 | Slate Feedback, Learning, and Evaluation | [Cascading Bandits Robust to Adversarial Corruptions](https://arxiv.org/abs/2502.08077) | Recommends a ranked list of K items and learns from cascade click feedback that is robust to adversarial corruptions. |
| 2025 | Slate Feedback, Learning, and Evaluation | [LLM-as-a-Judge: Toward World Models for Slate Recommendation Systems](https://arxiv.org/abs/2511.04541) | Uses LLMs as world models of user preference over whole slates, covering set selection, ordering, and joint selection-and-ordering. |
| 2025 | Slate Feedback, Learning, and Evaluation | [Multi-User Contextual Cascading Bandits for Personalized Recommendation](https://arxiv.org/abs/2508.13981) | Multi-user contextual cascading bandit with parallel context sessions and heterogeneous rewards, giving UCBBP and AUCBBP algorithms with regret bounds for sequentially exposed item lists. |
| 2025 | Slate Construction | [LLM-Enhanced Reranking for Complementary Product Recommendation](https://arxiv.org/abs/2507.16237) | Model-agnostic LLM prompting that reorders the candidate list of an existing complementary-product recommender to improve the accuracy-diversity trade-off of the top slots without retraining. |
| 2025 | Slate Feedback, Learning, and Evaluation | [RewardRank: Optimizing True Learning-to-Rank Utility](https://arxiv.org/abs/2508.14180) | UBC/Amazon RewardRank learns a reward model predicting the utility of an entire ranking from logged interactions and trains the ranker through a differentiable soft-permutation operator to maximize counterfactual list utility, evaluated with click-model and LLM-as-user oracles on Baidu-ULTR and Amazon KDD Cup data. |
| 2025 | Slate Construction | [Time-Constrained Recommendations: Reinforcement Learning Strategies for E-Commerce](https://arxiv.org/abs/2512.13726) | Budget-aware MDP formulation of slate recommendation under a finite user time budget where each item costs evaluation time, with on/off-policy RL beating contextual-bandit baselines in a simulator built on the Alibaba personalized re-ranking dataset. |
| 2025 | Slate Construction | [Producer-Fairness in Sequential Bundle Recommendation](https://arxiv.org/abs/2506.20329) | Formalizes producer-fairness for sequential bundle recommendation and gives an exact solver plus quality-first, fairness-first, and adaptive heuristics that trade bundle quality against group exposure across a session. |
| 2025 | Slate Construction | [Evaluating Position Bias in Large Language Model Recommendations](https://arxiv.org/abs/2508.02020) | Shows that candidate ordering in the prompt shifts LLM-generated recommendation lists and proposes RISE, an iterative-selection prompting strategy that stabilizes list outputs without fine-tuning. |
| 2026 | Slate Construction | [FlashEvaluator: Expanding Search Space with Parallel Evaluation](https://arxiv.org/abs/2603.02565) | Kuaishou evaluator that compares multiple generated sequences in one forward pass and selects better ranked lists. |
| 2026 | Slate Construction | [Dual-Rerank: Fusing Causality and Utility for Industrial Generative Reranking](https://arxiv.org/abs/2604.07420) | Kuaishou industrial reranker for whole-page utility, combining AR-to-NAR distillation with list-wise RL optimization. |
| 2026 | Slate Construction | [From Local Indices to Global Identifiers: Generative Reranking for Recommender Systems via Global Action Space](https://arxiv.org/abs/2604.25291) | Shuchang Liu et al.; reformulates listwise reranking as generation over global item identifiers and optimizes listwise utility. |
| 2026 | Slate Construction | [UniRank: Unified List-wise Reranking via Confidence-Ordered Denoising](https://arxiv.org/abs/2605.10527) | Shuchang Liu et al.; unifies autoregressive and non-autoregressive reranking with bidirectional ordered-slate denoising. |
| 2026 | Slate Construction | [Next-Scale Generative Reranking: A Tree-based Generative Rerank Method at Meituan](https://arxiv.org/abs/2604.05314) | Meituan; NSGR builds the recommendation list coarse-to-fine with a multi-scale evaluator guiding list construction. |
| 2026 | Slate Construction | [LLM-Assisted Reranking to Operationalize Nuanced Objectives in Recommender Systems](https://arxiv.org/abs/2606.02883) | Reranks YouTube's multi-item sidebar list via instruction-based LLM prompting and analyzes how exposure is distributed across positions. |
| 2026 | Slate Construction | [Trading Engagement for Sustainability: Carbon-Aware Re-ranking for E-commerce Recommendations](https://arxiv.org/abs/2606.04550) | Post-hoc re-ranking that reorders BPR/NeuMF/LightGCN lists to trade engagement against carbon footprint along a Pareto frontier. |
| 2026 | Slate Construction | [SCASRec: A Self-Correcting and Auto-Stopping Model for Generative Route List Recommendation](https://arxiv.org/abs/2602.03324) | Generates an ordered route list step-by-step with list-level coverage feedback and a learnable end-of-recommendation token for adaptive length. |
| 2026 | Slate Construction | [Whole-Pool Setwise Reranking with Long-Context Language Models](https://arxiv.org/abs/2606.01782) | Whole-Pool Setwise / DualEnd builds a full ranked list over the entire candidate pool, picking most- and least-relevant items per call. |
| 2026 | Slate Construction | [UniPinRec: Unifying Generative Retrieval and Ranking at Pinterest Scale](https://arxiv.org/abs/2606.00422) | Pinterest; joint generative retrieval and ranking trained on impression slates for Home Feed and Search grid surfaces. |
| 2026 | Slate Construction | [Constraint-Aware Generative Re-ranking for Multi-Objective Optimization in Advertising Feeds](https://arxiv.org/abs/2603.04227) | Bilibili; autoregressive generative reranker that builds the whole ad feed under constraints, balancing revenue and user experience. |
| 2026 | Slate Construction | [A Cascaded Generative Approach for e-Commerce Recommendations](https://arxiv.org/abs/2605.11118) | Builds whole storefront pages by generating placement-level themes plus per-placement keywords for retrieval, fused with ranking models. |
| 2026 | Slate Construction | [Adaptive Quality-Diversity Trade-offs for Large-Scale Batch Recommendation](https://arxiv.org/abs/2602.02024) | B-DivRec; DPP-based set selection that adapts the relevance-diversity balance using post-exposure user feedback. |
| 2026 | Slate Feedback, Learning, and Evaluation | [The Diversity Paradox revisited: Systemic Effects of Feedback Loops in Recommender Systems](https://arxiv.org/abs/2602.16315) | Feedback-loop simulation where recommenders return top-k lists and learn from implicit consumption to study long-term diversity dynamics. |
| 2026 | Slate Construction | [PSG: Pair-Space Generation for Efficient Generative Reranking](https://arxiv.org/abs/2607.26427) | Kuaishou generator-evaluator reranker that autoregressively generates ordered item pairs instead of single items, cutting list generation cost 1.8-4x without losing expressiveness and deployed to 400M DAU. |
| 2026 | Slate Construction | [SWIM: Step-Wise Integrated Measure for Session-supervised List Evaluation in Generative Re-ranking](https://arxiv.org/abs/2608.25104) | List-level evaluator for generator-evaluator reranking on short-video feeds that models consumption of the exposed list as a finite-horizon prefix session survival process, capturing context dependence and diminishing returns instead of scoring items independently. |
| 2026 | Slate Construction | [Once Generated, Ranked: End-to-End Generative Slate Recommendation with Unified Semantic-Collaborative IDs](https://arxiv.org/abs/2608.17613) | Kuaishou OGR framework that generates an ordered slate end to end with unified semantic-collaborative item IDs, listwise preference planning with pipelined position-wise decoding, and slate-level policy optimization, validated in online A/B tests. |
| 2026 | Slate Construction | [DIRECTOR: Dynamic Index-based Recommendation with Transport-Optimized Retrieval](https://arxiv.org/abs/2607.26418) | Kuaishou/USTC DIRECTOR reranker that generates request-conditioned retrieval indices for all slate positions in parallel and resolves conflicts with entropy-regularized optimal transport, avoiding autoregressive latency while aligning to a listwise evaluator. |
| 2026 | Slate Construction | [MetaStrategy: Generative Ranking with Executable LLM Strategies](https://arxiv.org/abs/2608.09440) | Taobao homepage MetaStrategy where a distilled 0.8B LLM policy emits executable JSON ranking strategies (objective weights, content preferences, positioning rules) that are compiled into generators competing inside a generator-evaluator list reranking framework trained on production-path replay. |
| 2026 | Slate Construction | [Fast and Feasible: Permutation-based Constrained Reranking for Revenue Maximization](https://arxiv.org/abs/2606.28059) | Avito PermR, a lightweight permutation-based reranker that swaps neighbouring items in e-commerce search result lists to approximate an integer linear program maximizing revenue under per-query list-level relevance constraints, recovering ~63% of exact-solution gains and +2% revenue in a 56M-query A/B test. |
| 2026 | Slate Construction | [Ranked by Position: Order Sensitivity as an Exploitable Attack Surface in LLM Listwise Recommenders](https://arxiv.org/abs/2607.24869) | Shows that reordering the candidate list alone can push low-quality items into the top-k of LLM listwise recommenders, introducing a promo@k vulnerability metric on MovieLens and Amazon data and proposing regularization and architectural mitigations. |
| 2026 | Slate Construction | [Reasoning While Recommending: Entropy-Guided Latent Reasoning in Generative Re-ranking Models](https://arxiv.org/abs/2601.13533) | EGLR interleaves entropy-guided variable-length latent reasoning steps with list generation in generative re-ranking models, using dynamic temperature to trade off exploration and exploitation while staying lightweight. |
| 2026 | Slate Construction | [Efficient Personalized Reranking with Semi-Autoregressive Generation and Online Knowledge Distillation](https://arxiv.org/abs/2603.07107) | PSAD trains a semi-autoregressive generative reranking teacher and distills it online into a lightweight scoring network with a user-profile network, improving list quality and inference efficiency on three datasets. |
| 2026 | Slate Construction | [TubiFM: Unified Item, Carousel, and Search Ranking for Streaming Discovery](https://arxiv.org/abs/2605.23702) | Tubi foundation model (Llama-3.2-1B) that serializes cross-surface viewer history into token sequences and ranks items, home-page carousels, and search results as prompted next-token prediction, lifting carousel and search viewing time online. |
| 2026 | Slate Feedback, Learning, and Evaluation | [From Click Modeling to Offline and Off-Policy Evaluation in Carousel Recommendation](https://arxiv.org/abs/2608.22022) | Doctoral research proposal that connects carousel interaction analysis, observable-variable click models, discrete-choice click interpretation, carousel-specific offline metrics, and off-policy evaluation for multi-carousel pages. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Revisiting N2DCG: An Empirically Grounded Reformulation of Carousel Recommendation Evaluation](https://arxiv.org/abs/2608.21877) | Reformulates the N2DCG carousel metric with a layout-feasible ideal ranking and eye-tracking-grounded discount functions, improving agreement with observed browsing and layout-comparison predictions. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Quotient DAGs for Off-Policy Evaluation: Forward-Flow Importance Sampling and Exact Slate Propensities](https://arxiv.org/abs/2605.29500) | Quotient-DAG view of autoregressive slate generation with Forward-DP dynamic programming that computes exact unordered-slate propensities for lower-variance importance-sampling OPE without factorial enumeration. |
| 2026 | Slate Construction | [GR2 Technical Report](https://arxiv.org/abs/2606.31984) | Meta AI GR2 industrial generative reasoning re-ranker that combines semantic-ID mid-training, reasoning distillation, on-policy distillation and RL with verifiable rewards to re-rank candidate lists for carousel and grid layouts at scale. |
| 2026 | Slate Construction | [Diffusion-GR2: Diffusion Generative Reasoning Re-ranker](https://arxiv.org/abs/2607.01170) | Meta follow-up to GR2 that converts an autoregressive reasoning re-ranker into a block-diffusion parallel-decoding re-ranker via conversion fine-tuning, on-policy distillation and RL, giving 2.4-3.5x faster list re-ranking at matched accuracy. |
| 2026 | Slate Construction | [hLLM: Single Pass Decoding for Generative Reranking](https://arxiv.org/abs/2609.01807) | Meta hLLM generative reranker that reads an item-position score matrix from a single forward pass and solves a Hungarian assignment to emit a guaranteed-valid full permutation of the candidate list, a 64x speed-up over autoregressive decoding. |
| 2026 | Slate Construction | [ClawRec: A Claw-Native Recommender System](https://arxiv.org/abs/2607.23779) | ClawRec agentic recommender with persistent cross-platform user state that selects candidates by marginal utility to produce non-redundant unified slates, plus a ClawRec-SimBench evaluation suite. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Does Rank Still Matter? Position Bias When AI Agents Shop on Our Behalf](https://arxiv.org/abs/2608.22697) | Randomized experiment over 5,000 hotel result-page sessions with four LLM shopping agents showing that rank affects which listings agents inspect only weakly and non-monotonically, and that product attributes dominate placement in agentic purchase choices. |
| 2026 | Slate Construction | [PreferRec: Learning and Transferring Pareto Preferences for Multi-objective Re-ranking](https://arxiv.org/abs/2603.22073) | Multi-objective re-ranking that learns each user's Pareto-optimal trade-off among accuracy, diversity, and fairness at the intent level and transfers shared optimization patterns across similar users to cut re-ranking cost. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Diversified Multinomial Logit Contextual Bandits](https://arxiv.org/abs/2607.11684) | Contextual MNL assortment bandit (DMNL) that adds a submodular within-assortment diversity term and builds assortments greedily via optimistic marginal gains (OFU-DMNL) with a (1-1/(e+1))-approximate regret bound. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Efficient and Robust Online Learning to Rank in Decentralized Systems](https://arxiv.org/abs/2606.12246) | RankGuard, a decentralized online learning-to-rank framework in which peers accept exchanged ranking models only if they better explain their own position-bias-corrected click histories, with the first convergence analysis for decentralized OLTR. |
| 2026 | Slate Construction | [Structure-aware Relative Policy Optimization for Ranking](https://arxiv.org/abs/2607.25268) | Tsinghua SRPO applies GRPO-style RL to listwise ranking, normalizing reward differences between sampled permutations by a top-weighted Kendall-tau distance so credit is assigned to structurally local, top-position refinements of whole lists under sparse list-level feedback. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Through Their Eyes: Fixation-aligned Tuning for Personalized User Emulation](https://arxiv.org/abs/2604.09368) | FixATE learns personalized prompts that align a vision-language user simulator's slot-level attention with each user's eye-tracking fixations on 3x5 carousel-grid movie recommendation pages (RecGaze), improving both attention alignment and click prediction. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Exploring Recommender System Evaluation: A Multi-Modal User Agent Framework for A/B Testing](https://arxiv.org/abs/2601.04554) | LLM-based user-agent sandbox with multimodal perception, preference modeling, and fatigue that browses multi-page recommendation lists to substitute for online A/B tests and generate synthetic training data. |
| 2026 | Slate Construction | [SAGE: Sequence-level Adaptive Gradient Evolution for Generative Recommendation](https://arxiv.org/abs/2601.21452) | SAGE RL preference optimizer for list-wise generative recommenders that uses a geometric-mean sequence-level importance ratio, a decoupled multi-objective advantage, and asymmetric adaptive bounds to avoid diversity collapse and improve top-K accuracy and diversity. |
| 2026 | Slate Construction | [LLMs as Orchestrators: Constraint-Compliant Multi-Agent Optimization for Recommendation Systems](https://arxiv.org/abs/2601.19121) | DualAgent-Rec uses an LLM to coordinate a constrained exploitation agent and a Pareto-search exploration agent with adaptive epsilon-relaxation so recommended lists satisfy hard business constraints while trading off accuracy and diversity. |
| 2026 | Slate Feedback, Learning, and Evaluation | [RecoAtlas: From Semantic Plausibility to Set-Level Utility in LLM Recommendation Agents](https://arxiv.org/abs/2605.18805) | Criteo benchmark (Aouali, Vasile, Sakhi et al.) that scores the recommendation set produced by LLM shopping agents with behavior-grounded set-level utility proxies for relevance, complementarity, and diversity instead of per-item semantic plausibility. |
| 2026 | Slate Construction | [An LLM-powered Agentic Recommendation System for Connected TV Content Discovery](https://arxiv.org/abs/2607.09988) | Meta agentic LLM system for the Connected TV home screen that generates topic carousels, ranks media within each carousel, and orders the carousels into a personalized channel-and-media page layout. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Towards Faithful Simulation of Human Shopping Behavior](https://arxiv.org/abs/2608.20707) | RecVerse (Renmin University with Alibaba/Taobao) GUI-grounded shopping simulator that perceives multi-item pages via screenshots, keeps hierarchical working/episodic/preference memory, and is aligned to real multi-turn browsing trajectories with trajectory-level RL, plus the USB e-commerce trajectory dataset. |
| 2026 | Slate Construction | [Dual-Enhancement Product Bundling: Bridging Interactive Graph and Large Language Model](https://arxiv.org/abs/2604.14030) | Product-bundle construction that binds interaction-graph structure into LLM prompts via a Dynamic Concept Binding mechanism, combining graph learning for cold-start bundles with LLM semantics on POG and Steam bundle benchmarks. |
| 2026 | Slate Construction | [Scoring Is Not Enough: Addressing Gaps in Utility-fairness Trade-offs for Ranking](https://arxiv.org/abs/2606.26369) | Proves that pointwise scoring functions (deterministic or randomized, single- or multi-query) cannot reach all optimal utility-fairness trade-offs for ranked lists and proposes semi-greedy list post-processing that approaches exhaustive post-processing. |
| 2026 | Slate Feedback, Learning, and Evaluation | [Robustness and User-Perceived Value of Popularity Calibration in Music Recommendation: A User Study](https://arxiv.org/abs/2608.05402) | User study (JKU Linz and collaborators) showing that listeners perceive popularity-composition differences between personalized playlists but do not clearly prefer popularity-calibrated lists, and that list-level calibration metrics only weakly align with user judgments. |
| 2026 | Slate Feedback, Learning, and Evaluation | [A Causal Information-Flow Framework for Unbiased Learning-to-Rank](https://arxiv.org/abs/2601.05590) | Gong, Ai, Tao and Zhang (Rutgers/Tsinghua) combine a structural causal model of click generation over ranked lists with conditional-mutual-information bias-leakage measurement and a doubly robust estimator to learn relevance unbiased by position, selection and trust bias. |
| 2026 | Slate Construction | [SR-Agent: An Experience-Driven Agentic Framework for Post-Ranking Strategy Refinement in E-Commerce Recommendation](https://arxiv.org/abs/2607.17719) | Kuaishou e-commerce SR-Agent uses a three-agent experience-driven loop to diagnose and automatically refine post-ranking strategies that govern the exposed ranked list, deployed with one-month A/B gains in orders, browsing depth and category diversity. |
| 2026 | Slate Construction | [F-GRPO: Factorized Group-Relative Policy Optimization for Unified Candidate Generation and Ranking](https://arxiv.org/abs/2605.12995) | UCSD/UIUC/Adobe generative ranker that has one LLM emit candidates and then a ranked list in a single autoregressive pass, trained with an order-invariant coverage reward plus a position-aware list utility reward and factorized group-relative advantages. |
| 2026 | Slate Construction | [PCN-Rec: Agentic Proof-Carrying Negotiation for Reliable Governance-Constrained Recommendation](https://arxiv.org/abs/2601.09771) | Two LLM agents (User Advocate and Policy Agent) negotiate and an LLM mediator emits a top-N slate with a constraint certificate, which a deterministic validator checks and repairs to guarantee diversity and long-tail exposure constraints on MovieLens-100K. |
| 2026 | Slate Construction | [Online Advertising with Spatial Interactions](https://arxiv.org/abs/2602.12481) | Allocates a whole screen of ad slots modelled as points in a metric space where each ad's value is discounted by neighbouring ads, giving a constant-factor truthful mechanism for the nearest-neighbour model and hardness results for the product-distance model. |
| 2026 | Slate Construction | [Towards Position-Robust Talent Recommendation via Large Language Models](https://arxiv.org/abs/2604.02200) | L3TR listwise LLM talent recommender that uses block attention, local positional encoding, and ID sampling to remove position bias and lost-in-the-middle effects when ranking a whole candidate list in one pass. |

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
