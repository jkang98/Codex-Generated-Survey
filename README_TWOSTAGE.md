# Off-Policy Learning and Evaluation in Multi-Stage Recommender Systems

A living reading list for the off-policy, counterfactual view of multi-stage
recommender pipelines: candidate generation or matching narrows a catalogue of
millions to a few thousand, an optional pre-ranking stage trims further, and a
ranking stage (often followed by re-ranking) chooses what is served. The item a
user sees is produced jointly by every stage, and logged feedback exists only for
items that survived all of them.

This list collects work that treats that composition as an off-policy problem:
training one stage from feedback logged under a different pipeline, evaluating a
new pipeline whose first stage changes the action set the later stages choose
from, and correcting the exposure and selection bias that stages impose on one
another. The anchor is Off-policy Learning in Two-stage Recommender Systems (Ma
et al., WWW 2020), which folds the downstream ranker into the candidate
generator's importance weight; the list runs from its direct foundation, Top-K
Off-Policy Correction (WSDM 2019), to the 2025-2026 wave of two-stage off-policy
evaluation, offline policy selection, and two-stage counterfactual learning to
rank.

Scope is deliberately narrow. A core paper must both model the recommender as an
explicit multi-stage pipeline and use off-policy or counterfactual machinery
(importance weighting, doubly robust estimation, propensity modelling of
candidate generation) across stages. A small adjacent set is kept for two
reasons: large-action-space off-policy evaluation and learning that targets
retrieval-scale action spaces is the estimator toolkit the core papers draw on,
and industrial entire-space and propensity work corrects the same cross-stage
sample-selection bias without an off-policy framing. Reading the two lines side
by side is the point of the collection. Single-stage slate and ranking OPE lives
in `README_SLATE.md`; generic retrieval and pre-ranking consistency work lives
in `README_ALIBABA.md`.

## Taxonomy

This list is organized around two research questions:

- **Off-policy learning across stages: how to train one stage under another**:
  methods that optimize the candidate-generation or retrieval stage from logged
  feedback while accounting for the ranker that sits downstream, or that train
  both stages jointly from logs.
- **Off-policy evaluation and selection of the pipeline: how to judge a new
  stage from logs**: estimators for the value of a pipeline whose first stage
  changes the action set the ranker chooses from, and offline selection among
  (generator, ranker) pairs.
- **Adjacent but useful**: large-action-space off-policy estimators and learners
  at retrieval scale, and industrial corrections of cross-stage sample-selection
  bias that use entire-space labels or stage propensities instead of importance
  weighting.

## Pipeline Perspective Tree

This tree is a secondary index over the papers below, grouped by which part of
the pipeline a paper reasons about and how. Core papers satisfy both the
multi-stage and the off-policy condition; adjacent papers satisfy one of them
and are kept because the core papers depend on them or because they solve the
same cross-stage bias by other means.

```text
Off-policy learning and evaluation in multi-stage recommender systems
|-- Foundations: top-K off-policy correction for the candidate-generation stage
|   |-- Top-K Off-Policy Correction for a REINFORCE Recommender System
|   |-- Off-Policy Actor-critic for Recommender Systems
|   |-- Session-Level Optimization for Large-Scale Retrieval using REINFORCE with Multi-Step Off-Policy Correction
|-- Off-policy learning of the two-stage pipeline
|   |-- Ranker-aware candidate-generator training
|   |   |-- Off-policy Learning in Two-stage Recommender Systems
|   |   |-- Towards Two-Stage Counterfactual Learning to Rank
|   |   |-- Off-Policy Learning for Diversity-aware Candidate Retrieval in Two-stage Decisions
|   |   |-- Credit-assigned Policy Gradient for Early Stage Retrieval in Two-stage Ranking
|   |-- Counterfactual control of the retrieval stage
|   |   |-- Deep-learning Causal Retrieval Optimization for Efficient e-commerce Distribution in Pinterest
|-- Off-policy evaluation and selection of the multi-stage pipeline
|   |-- Evaluating a changed candidate generator
|   |   |-- Off-Policy Evaluation of Candidate Generators in Two-Stage Recommender Systems
|   |   |-- Off-Policy Evaluation in Two-Stage Recommender Systems via Latent Distribution Alignment
|   |-- Offline policy selection over (generator, ranker) pairs
|   |   |-- CASP: Support-Aware Offline Policy Selection for Two-Stage Recommender Systems
|   |-- OPE as a certificate for the first stage
|   |   |-- Uncertainty Quantification for Fairness in Two-Stage Recommender Systems
|-- Large-action-space off-policy methods at retrieval scale
|   |-- Estimators: marginalization, clustering, convolution
|   |   |-- Off-Policy Evaluation for Large Action Spaces via Embeddings
|   |   |-- Off-Policy Evaluation for Large Action Spaces via Conjunct Effect Modeling
|   |   |-- Off-Policy Evaluation for Large Action Spaces via Policy Convolution
|   |   |-- Off-Policy Evaluation for Semantic ID Recommenders: Does the Model's Own Code Hierarchy Help?
|   |-- Learners: decomposed and scalable policy optimization
|   |   |-- POTEC: Off-Policy Contextual Bandits for Large Action Spaces via Policy Decomposition
|   |   |-- Practical Counterfactual Policy Learning for Top-K Recommendations
|   |   |-- Fast Offline Policy Optimization for Large Scale Recommendation
|   |   |-- Off-Policy Learning in Large Action Spaces: Optimization Matters More Than Estimation
|-- Cross-stage selection bias without off-policy weighting
|   |-- Theory of stage interaction
|   |   |-- On component interactions in two-stage recommender systems
|   |   |-- Generalization Error Bounds for Two-stage Recommender Systems with Tree Structure
|   |-- Propensity-flavored debiasing of the retrieval / matching stage
|   |   |-- Contrastive Learning for Debiased Candidate Generation in Large-Scale Recommender Systems
|   |   |-- Re-weighting Negative Samples for Model-Agnostic Matching
|   |-- Entire-space / entire-chain correction of the pre-ranking stage
|   |   |-- Rethinking Large-scale Pre-ranking System: Entire-chain Cross-domain Models
|   |   |-- An Unbiased Entire-Space Causal Framework for Click-Through Rate Estimation in Pre-Ranking
|   |   |-- Both Supply and Precision: Sample Debias and Ranking Consistency Joint Learning for Large Scale Pre-Ranking System
|   |   |-- Generative Pseudo-Labeling for Pre-Ranking with LLMs
|   |-- Cascade-aware ranking principle
|   |   |-- Full Stage Learning to Rank: A Unified Framework for Multi-Stage Systems
```

## Coverage Statistics

These counts summarize the current README coverage, not citation impact or a
complete bibliographic census. Counts are approximate because several papers
have multiple authors and affiliations.

### Author Coverage

| Author or cluster | Approx. README entries | Main coverage in this README |
| --- | ---: | --- |
| Thorsten Joachims | 6+ | Large-action-space OPE and OPL (MIPS, OffCEM, POTEC), two-stage diversity-aware and credit-assigned retrieval policies, and OPE-certified fairness of the candidate set. |
| Yuta Saito | 3+ | Marginalized and cluster-based OPE estimators, and policy decomposition for large action spaces. |
| Haruka Kiyohara | 2+ | Off-policy and policy-gradient learning of the retrieval stage in two-stage pipelines. |
| Minmin Chen / Ed H. Chi | 3+ | Top-K off-policy correction, two-stage off-policy learning, and off-policy actor-critic for YouTube candidate generation. |
| Otmane Sakhi | 2+ | Scalable offline policy optimization and the estimation-versus-optimization study for large catalogues. |

### Institution Coverage

| Institution or lab | Approx. README entries | Main coverage in this README |
| --- | ---: | --- |
| Cornell University | 6+ | The academic two-stage off-policy line and its large-action-space estimator toolkit. |
| Google / YouTube | 3+ | The production origin of top-K and two-stage off-policy correction. |
| Criteo AI Lab | 3+ | Scalable offline policy optimization, semantic-ID OPE, and optimization-landscape analysis. |
| Alibaba | 3+ | Propensity-flavored retrieval debiasing (CLRec, UMA2) and LLM pseudo-labeling for pre-ranking. |
| JD.com | 2+ | Entire-chain and entire-space causal correction of pre-ranking selection bias. |
| Meta | 2+ | Two-stage counterfactual LTR and credit-assigned early-stage retrieval. |
| Amazon / Kyushu University / Texas A&M | 3 | Two-stage OPE with a changed candidate generator and offline policy selection. |
| Kuaishou / Pinterest / Weibo / Netflix / USTC | 1 each | Full-stage LTR, causal retrieval triggering, entire-chain pre-ranking negatives, policy convolution, and generalization bounds for tree-retriever pipelines. |

## Main Threads

The taxonomy and tree above are indexes; this section is the synthesis. Five
arcs run through the collection.

### 1. From top-K off-policy correction to ranker-aware candidate generation

The spine of the collection is a single lineage. Top-K Off-Policy Correction
(2019) brought importance-weighted REINFORCE to YouTube's candidate generator,
adding a top-K multiplier so the gradient targets a set rather than one item,
but treated the downstream ranker as an external black box. Off-policy Learning
in Two-stage Recommender Systems (2020) is the pivot: it folds the ranking model
into the candidate generator's importance weight and shows that ignoring the
generator-ranker interaction yields a sub-optimal first stage. The single-stage
foundation kept evolving in parallel — Off-Policy Actor-critic (2022) swaps the
Monte-Carlo return for an importance-sampled critic, and Session-Level
Optimization (2026) replaces the one-step ratio with a capped multi-step product
— yet neither models the ranker. The two-stage extensions come from academia:
Two-Stage Counterfactual LTR (2025) generalizes the correction from top-1 to
top-K rankings and alternates updates across both stages; Diversity-aware
Candidate Retrieval (2025) replaces vanilla IS with kernel IS for Plackett-Luce
candidate sets; and Credit-assigned Policy Gradient (2026) marginalizes over set
compositions to collapse the set-level action space to item level, though still
on-policy. Joint off-policy training of both stages at production scale remains
open.

### 2. Evaluating a pipeline whose action set moves: two-stage OPE and selection

Learning is half the problem; the other half is deciding from logs whether a new
first stage is better. Off-Policy Evaluation of Candidate Generators (2025) poses
this cleanly: a new generator leaves the ranker untouched but changes the action
set the ranker chooses from, so the pipeline must be evaluated as a contextual
bandit with a moving action set, and it derives importance-weighting estimators
with asymptotic bias/variance analysis. Latent Distribution Alignment (2026)
attacks the resulting support deficiency — the logged candidate set and the
target set may barely overlap — by marginalizing weights over a discrete latent
space and aligning the logging marginal so overlap and bounded variance are
guaranteed. CASP (2026) turns evaluation into selection: given a library of
(generator, ranker) pairs, it scores each by a doubly-robust value minus a
support-burden penalty on the coupled generator x ranker ratio. Two adjacent
papers show the same machinery in other roles: Uncertainty Quantification for
Fairness (2023) uses clipped-IPS confidence bounds to certify that a candidate
set is not irrecoverably unfair, and Pinterest's Causal Retrieval Optimization
(2026) validates a generator-triggering policy with an offline replay that
tracks online A/B results.

### 3. Retrieval-scale action spaces: making importance weights survive millions of items

A candidate generator ranges over millions of items, so importance-weighted
methods for the first stage inherit the large-action-space problem, and the
estimator toolkit is mostly single-stage. MIPS (2022) marginalizes per-action
weights over action embeddings; OffCEM (2023) splits reward into a cluster effect
estimated by importance weighting and a per-item residual fitted by regression;
Policy Convolution (2024) smooths logging and target policies over an embedding
space and, tellingly, tests on a shortlist-then-select logging policy modelled on
Ma et al. POTEC (2025) lifts the cluster-then-item factorization from evaluation
to learning — a low-variance cluster policy followed by a within-cluster argmax —
a retrieve-then-select decomposition over predefined clusters rather than a
learned generator. Semantic-ID OPE (2026) applies the same marginalization to a
generative retriever's own code hierarchy, deferring the changed-generator case
to the RecSys 2025 estimators. On the learning side, Fast Offline Policy
Optimization (2023) uses the serving ANN index as an IS proposal to scale
REINFORCE logarithmically in catalogue size, Practical Counterfactual Policy
Learning for Top-K (2022) prunes per-position weights rather than pre-selecting
candidates, and Optimization Matters More Than Estimation (2026) warns that
IPS-family objectives degrade in optimization landscape as the action space
grows.

### 4. Stage interaction as sample-selection bias: the entire-space industrial line

Industry reached the same stage interaction from the labeling side. On component
interactions (2021) proved that nominators trained independently of the ranker
can incur linear regret because they only observe feedback on what the ranker
served, and proposed joint mixture-of-experts training as a lower-variance
alternative to Ma et al.'s importance weights; Generalization Error Bounds
(2024) formalized the ranker's excess error under the retriever-induced
distribution as a density-ratio term. Rather than weighting, the deployed
corrections relabel. For retrieval, CLRec (2021) shows the sampled-softmax loss
is already an inverse-propensity loss under the exposure distribution and
debiases it with a FIFO negative queue; UMA2 (2022) partitions negatives by how
far they travelled through matching, ranking and re-ranking and reweights by
stage propensities from auxiliary selection tasks. For pre-ranking, Entire-chain
Cross-domain Models (2022) decompose pETCTR into pETR x pCTR over nested stage
domains; the Unbiased Entire-Space Causal Framework (2025) generates and
propensity-models labels for unexposed candidates; SDCL (2025) draws
entire-chain negatives from each stage's rejects; and Generative Pseudo-Labeling
(2026) has an LLM label the recall set. Full Stage LTR (2024) states the
unifying principle: a non-final stage should rank by user interest times
downstream selection probability.

### 5. Two vocabularies for one quantity: downstream survival probability

Read together, the off-policy line and the entire-space line are two
vocabularies for one quantity: the probability that an item survives the stages
downstream of the one being trained. In Ma et al. (2020) and Two-Stage
Counterfactual LTR (2025) it sits in the numerator of an importance weight (the
generator surfaces the item and the ranker places it in the top-K); in Full
Stage LTR (2024) it is the downstream-selection factor of the Generalized
Probability Ranking Principle; in UMA2 (2022) and Entire-chain Cross-domain
Models (2022) it is the product of stage propensities; in Generalization Error
Bounds (2024) it is the density ratio between the retriever-induced and the
logged distribution. What differs is the estimation strategy. The off-policy
papers estimate it through a logged behavior policy and pay in variance and
support — Latent Distribution Alignment (2026), CASP (2026) and Policy
Convolution (2024) are all responses to that cost — while the industrial papers
estimate it with auxiliary selection tasks or relabeled stage logs and pay in
bias. The 2025-2026 core papers make this trade explicit for the first time; a
method that combines stage-level exposure labels with doubly-robust pipeline
estimators does not yet appear in this list.

## Off-Policy Learning Across Stages: Training One Stage Under Another

This branch asks how to optimize the candidate-generation or retrieval stage from
logged feedback while accounting for the ranker that consumes its output, or how
to train both stages jointly from logs.

### Core: Two-Stage Off-Policy Learning and Its Foundation

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2019 | [Top-K Off-Policy Correction for a REINFORCE Recommender System](https://arxiv.org/abs/1812.02353) | WSDM | Google / YouTube; importance-weighted REINFORCE for a production candidate generator over millions of items, with a jointly learned behavior-policy head, a top-K multiplier so the gradient targets a K-item set, and weight capping and normalized IS for variance; the direct foundation the two-stage line extends. |
| 2020 | [Off-policy Learning in Two-stage Recommender Systems](https://doi.org/10.1145/3366423.3380130) | WWW | Google; the anchor paper: trains the candidate-generation stage with importance weights that fold in the downstream ranking model, showing that ignoring the generator-ranker interaction yields a sub-optimal first-stage policy. |
| 2025 | [Towards Two-Stage Counterfactual Learning to Rank](https://arxiv.org/abs/2506.20854) | ICTIR | University of Amsterdam / Meta AI; first counterfactual LTR estimator for a generator-then-ranker pipeline, with IPS over the joint exposure probability that the generator surfaces a document and the ranker places it in the top-K, extending Ma et al. from top-1 to top-K and alternating updates across both stages. |
| 2025 | [Off-Policy Learning for Diversity-aware Candidate Retrieval in Two-stage Decisions](https://openreview.net/forum?id=5yAoEzbeWt) | ICML SIM Workshop / RecSys CONSEQUENCES Workshop | Cornell (Kiyohara, Khanna, Joachims); generalizes the two-stage off-policy gradient to a diversity-aware Plackett-Luce retrieval policy trained against a fixed second stage, replacing vanilla IS with kernel IS to tame variance and deficient support at retrieval scale (theory; experiments deferred). |

### Adjacent: Single-Stage Off-Policy Retrieval Training and Counterfactual Retrieval Control

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2022 | [Off-Policy Actor-critic for Recommender Systems](https://dl.acm.org/doi/10.1145/3523227.3546758) | RecSys | Google / YouTube; swaps the Monte-Carlo return in off-policy-corrected REINFORCE for an importance-sampled TD critic on the candidate-generation policy, keeping the one-step weight and never modelling the downstream ranker. |
| 2026 | [Credit-assigned Policy Gradient for Early Stage Retrieval in Two-stage Ranking](https://arxiv.org/abs/2605.26385) | ICML | Cornell / Meta; trains the early-stage retriever through a fixed late-stage ranker via the gradient of an item's marginal probability of entering any candidate set, reducing the action space from set level to item level; on-policy, with off-policy learning from logs left as future work. |
| 2026 | [Deep-learning Causal Retrieval Optimization for Efficient e-commerce Distribution in Pinterest](https://arxiv.org/abs/2607.14161) | KDD | Pinterest; treats firing shopping candidate generators in early retrieval as a causal policy decision, learning triggering policies from doubly-robust pseudo-outcomes on randomized logs and choosing thresholds with an offline replay that tracks online A/B results. |
| 2026 | [Session-Level Optimization for Large-Scale Retrieval using REINFORCE with Multi-Step Off-Policy Correction](https://arxiv.org/abs/2607.02818) | KDD Workshop | AI VK / HSE; extends top-K off-policy correction to session-level credit assignment for a two-tower retrieval stage, replacing the one-step ratio with a capped multi-step product of per-step ratios plus step-IS and DR evaluation of cumulative session reward. |

## Off-Policy Evaluation and Selection of the Pipeline: Judging a New Stage From Logs

This branch asks how to estimate, from logged data, the value of a pipeline whose
first stage has changed and therefore changes the action set downstream, and how
to choose among candidate pipelines offline.

### Core: Two-Stage Off-Policy Evaluation

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2025 | [Off-Policy Evaluation of Candidate Generators in Two-Stage Recommender Systems](https://doi.org/10.1145/3705328.3748057) | RecSys | Amazon; frames evaluating a new first-stage generator as contextual-bandit OPE in which the generator changes the action set the downstream ranker chooses from, with two importance-weighting estimators, asymptotic bias/variance analysis, and a bias-reduction procedure. |
| 2026 | [Off-Policy Evaluation in Two-Stage Recommender Systems via Latent Distribution Alignment](https://doi.org/10.5281/zenodo.20690139) | ECML PKDD | Kyushu University; LPAIPS marginalizes importance weights over a discrete latent space and aligns the logging latent marginal so that a target candidate set differing from the logged one still has guaranteed overlap and bounded variance. |

### Adjacent: OPE as a Certificate for the First Stage

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2023 | [Uncertainty Quantification for Fairness in Two-Stage Recommender Systems](https://arxiv.org/abs/2205.15436) | WSDM | Cornell (Wang, Joachims); shows a first stage can surface an irrecoverably unfair candidate set that no ranker can repair, and certifies first-stage threshold rules with confidence bounds around a clipped-IPS off-policy estimate from logged, presentation-biased feedback. |

## Adjacent: Large-Action-Space Off-Policy Methods at Retrieval Scale

These papers treat a single policy over a catalogue-scale action space; they are
kept because the importance-weighted methods above inherit exactly this
large-action-space problem at the candidate-generation stage. This section is a
toolkit, not a complete survey of large-action-space OPE.

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2022 | [Off-Policy Evaluation for Large Action Spaces via Embeddings](https://arxiv.org/abs/2202.06317) | ICML | Cornell (Saito, Joachims); MIPS marginalizes importance weights over action embeddings so OPE stays unbiased and low-variance at thousands-to-millions of items; the standard foundation that retrieval-scale OPE builds on. |
| 2022 | [Practical Counterfactual Policy Learning for Top-K Recommendations](https://dl.acm.org/doi/10.1145/3534678.3539295) | KDD | NTU / Meituan; single-stage IPS policy gradient for a top-K policy over the full catalogue with factorized, pruned per-position weights and KL-regularized per-item IPS, positioned against pre-selection approaches rather than as a multi-stage method. |
| 2023 | [Off-Policy Evaluation for Large Action Spaces via Conjunct Effect Modeling](https://arxiv.org/abs/2305.08062) | ICML | Cornell; OffCEM splits reward into an importance-weighted cluster effect and a regressed per-item residual, the coarse-to-fine factorization that POTEC later lifts from evaluation to learning. |
| 2023 | [Fast Offline Policy Optimization for Large Scale Recommendation](https://arxiv.org/abs/2208.05327) | AAAI | Criteo AI Lab; scales offline REINFORCE to million-item catalogues by using the serving ANN index as a self-normalized importance-sampling proposal, logarithmic in catalogue size. |
| 2024 | [Off-Policy Evaluation for Large Action Spaces via Policy Convolution](https://arxiv.org/abs/2310.15433) | WWW | Netflix / UCSD / Cornell; convolves logging and target policies over an action-embedding space to relax IPS common support, and evaluates on a shortlist-then-select logging policy explicitly modelled on the two-stage setup of Ma et al. |
| 2025 | [POTEC: Off-Policy Contextual Bandits for Large Action Spaces via Policy Decomposition](https://arxiv.org/abs/2402.06151) | ICLR | Cornell / UW; decomposes a large-action off-policy policy into an importance-weighted cluster-selection stage and a regression-based within-cluster stage — a retrieve-then-select decomposition over predefined clusters rather than a learned candidate generator. |
| 2026 | [Off-Policy Learning in Large Action Spaces: Optimization Matters More Than Estimation](https://arxiv.org/abs/2509.03456) | ICML | Criteo AI Lab; shows IPS-family objectives (IPS, DR, MIPS, OffCEM, POTEC, Policy Convolution) degrade in optimization landscape as the action space grows, while pessimistic weighted log-likelihood objectives optimize better at competitive policy value. |

## Adjacent: Cross-Stage Selection Bias Without Off-Policy Weighting

These papers reason explicitly about the stage pipeline and correct the
sample-selection bias one stage imposes on another, but do so with entire-space
labels, stage propensities, or joint training rather than importance-weighted
off-policy learning.

| Year | Paper | Venue | Main idea |
| --- | --- | --- | --- |
| 2021 | [On component interactions in two-stage recommender systems](https://arxiv.org/abs/2106.14979) | NeurIPS | Cambridge / Berkeley / TUM; proves nominators trained independently of the ranker can incur linear regret because they only observe feedback on what the ranker served, and proposes joint mixture-of-experts pool allocation as a lower-variance alternative to two-stage importance weighting. |
| 2021 | [Contrastive Learning for Debiased Candidate Generation in Large-Scale Recommender Systems](https://arxiv.org/abs/2005.12964) | KDD | Alibaba DAMO; shows the sampled-softmax loss of a deep retrieval stage is an inverse-propensity loss under the deployed exposure distribution, and debiases it with a FIFO negative queue (CLRec) without a separate propensity model. |
| 2022 | [Re-weighting Negative Samples for Model-Agnostic Matching](https://arxiv.org/abs/2207.02468) | SIGIR | Alibaba; UMA2 partitions matching negatives by how far they travelled through matching, ranking and re-ranking and reweights them with stage propensities learned by auxiliary selection tasks. |
| 2022 | [Rethinking Large-scale Pre-ranking System: Entire-chain Cross-domain Models](https://arxiv.org/abs/2310.08039) | CIKM | JD.com; recasts pre-ranking sample-selection bias as an entire-chain problem, decomposing pETCTR into pETR x pCTR over nested stage domains and training on labels drawn from every cascade stage. |
| 2024 | [Full Stage Learning to Rank: A Unified Framework for Multi-Stage Systems](https://arxiv.org/abs/2405.04844) | WWW | Kuaishou; Generalized Probability Ranking Principle: a non-final stage should rank by user interest times the downstream stages' selection probability, realized by relabeling stage-wise exposure logs into ordinal LTR targets. |
| 2024 | [Generalization Error Bounds for Two-stage Recommender Systems with Tree Structure](https://papers.nips.cc/paper_files/paper/2024/hash/4140fe26102db5fea1f40118afc7137b-Abstract-Conference.html) | NeurIPS | USTC; decomposes the generalization error of a tree retriever plus ranker and shows the ranker's excess error under the retriever-induced distribution is a density-ratio term — the cross-stage shift the off-policy line corrects with importance weights. |
| 2025 | [An Unbiased Entire-Space Causal Framework for Click-Through Rate Estimation in Pre-Ranking](https://doi.org/10.1145/3701716.3715210) | WWW Companion | JD.com; treats pre-ranking's selection bias as a counterfactual problem, generating unbiased labels for unexposed candidates, modelling their propensity, and proving entire-space unbiasedness; deployed with online CTR gains. |
| 2025 | [Both Supply and Precision: Sample Debias and Ranking Consistency Joint Learning for Large Scale Pre-Ranking System](https://doi.org/10.1609/aaai.v39i11.33270) | AAAI | Weibo; SDCL corrects exposure-conditioned pre-ranking training with entire-chain negatives drawn from each stage's rejects, jointly with logit distillation from the ranker, without propensity or IPS. |

## arXiv Preprints and Non-peer-reviewed Papers

These papers are relevant to off-policy or counterfactual reasoning across
stages, but are kept separate from the peer-reviewed conference, workshop, and
journal papers above.

| Year | Area | Paper | Main idea |
| --- | --- | --- | --- |
| 2026 | Off-policy evaluation and selection | [CASP: Support-Aware Offline Policy Selection for Two-Stage Recommender Systems](https://arxiv.org/abs/2604.23022) | Texas A&M; selects among a library of (generator, ranker) pairs by a doubly-robust pipeline value minus a support-burden penalty on the coupled generator x ranker importance ratio, with finite-class guarantees and MovieLens-1M experiments. |
| 2026 | Large-action-space toolkit | [Off-Policy Evaluation for Semantic ID Recommenders: Does the Model's Own Code Hierarchy Help?](https://arxiv.org/abs/2608.28905) | Criteo AI Lab; OPE for generative semantic-ID retrievers by marginalizing propensities up to code-prefix clusters of the model's own RQ tree, restoring effective sample size under near-argmax logging; defers the changed-generator case to the RecSys 2025 estimators. |
| 2026 | Cross-stage selection bias | [Generative Pseudo-Labeling for Pre-Ranking with LLMs](https://arxiv.org/abs/2602.20995) | Alibaba; has a fine-tuned LLM generate confidence-weighted pseudo-labels for unexposed recalled candidates so the pre-ranker's training distribution matches the recall space it serves, without propensities. |

## Explicitly Out of Scope

The following families are deliberately excluded here, even when they use
off-policy or counterfactual machinery, because another list in this repository
owns them or because they fail the two-condition scope test:

- Single-stage slate / ranking OPE (slate IPS and pseudoinverse estimators,
  doubly robust cascade estimators, learned slate abstractions, embedding-space
  behavior models, deterministic-logging and long-term-value estimators):
  `README_SLATE.md`, section "Logged Feedback, Click Models, Bandits, and
  Off-policy Learning". A paper belongs here only when the logged action set
  itself is produced by an upstream stage.
- Cascade, position-based, dependent-click and combinatorial bandits:
  `README_SLATE.md`. "Cascade" there means the user's browsing model over a
  list, not the system's stage pipeline.
- Top-K Off-Policy Correction (WSDM 2019) appears in both lists on purpose:
  `README_SLATE.md` files it under list-level RL, this list files it as the
  direct foundation of the two-stage off-policy line.
- On-policy or long-horizon RL for recommendation (retention, request-level
  MDPs, GFlowNets, generative slate RL, multi-stage RL with replay buffers but
  no importance weighting) that does not correct for the logging pipeline:
  `README_SLATE.md`.
- Generic retrieval methods (two-tower / dual-encoder models, ANN / MIPS
  indexing, tree-based retrieval, generative and semantic-ID retrieval) without
  a counterfactual or propensity correction: `README_ALIBABA.md`, where
  retrieval is background to ranking.
- Pre-ranking consistency, distillation and calibration work with no propensity
  or counterfactual element (pre-rank / rank score alignment, lightweight
  pre-ranker architectures, knowledge distillation from the ranker):
  `README_ALIBABA.md`.
- Generic CTR / CVR debiasing that is not about the stage pipeline (position
  bias, popularity bias, exposure bias inside a single ranking stage,
  ESMM-style click-to-conversion entire-space modelling): `README_ALIBABA.md`.
- Multi-stage datasets and empirical bias studies that propose no estimator
  (e.g. full-flow datasets, selection-bias measurements in ads retrieval).

## Contribution Notes

Good additions usually include:

- Which stage is being trained or evaluated (candidate generation / matching,
  pre-ranking, ranking, re-ranking) and which stages are held fixed.
- What is logged: behavior-policy propensities, stage-wise exposure or
  survival labels, randomized traffic, or only final impressions.
- The estimator family: IPS / SNIPS / clipped IS, doubly robust, marginalized or
  clustered weights, entire-space relabeling, or auxiliary selection propensities.
- Whether stages are optimized jointly or separately, and whether the downstream
  ranker is modelled explicitly in the weight.
- Links to paper, code, dataset, and BibTeX when available.
