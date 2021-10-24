# Machine Learning for Computational Biology

## Representing sequences

Introduction to machine learning, and why we need to find a numerical representation.

Sequences
- DNA and RNA sequences are a 4 letter alphabet
- Protein sequences are a 20 letter alphabet
- one hot encoding
- kmers and spectrum kernels
- counting and hashing
- language models

Opportunities and challenges
- graphs, geometric deep learning
- Hard and soft constraints
- Really need causal graphs, and dynamical systems

## High dimension low sample size

Introduction to linear regression and the fundamental theorem of linear algebra

Why high dimensions will never be solved
- Cheap sequencing.
  Wetterstrand KA.
    DNA Sequencing Costs: Data from the NHGRI Genome Sequencing Program (GSP)
    Available at: www.genome.gov/sequencingcostsdata. Accessed [date of access].
- Mobile sequencing. Minion. Laura Boykin
- Medical data. Rare disease so few patients. E.g. prostate cancer PeterMac
- [PCAWG](https://dcc.icgc.org/pcawg/#!) is 285GB per person.

Genome wide association studies (see [slides](https://raw.githubusercontent.com/goepp/ml-in-genomics-2021/master/slides/main.pdf) from Chloe and Vivien)
- Statistical hypothesis testing
- Multiple testing correction
- Use linear regression for feature selection
- Need predictions. GBLUP and ABLUP
- Epistasis
- Stability

Opportunities and challenges
- Predicting with uncertainty
- Finite domain (we want predictions genome wide)
- Measurement Noise and Data Normalisation
- Evaluation and Interpretability


## Designing Genomic Sequences

What do we do after we have a predictor?
- Active learning
- Bandits and Bayesian Optimization
- Choice Theory
- Design of Experiments

Discuss RBS experiment

Opportunities and challenges [WCB workshop paper](https://icml-compbio.github.io/2021/papers/WCBICML2021_paper_8.pdf)
- Generalization from Ribosome Binding Site to other regulatory sequences
- Exploration-Exploitation tradeoff in bandits
- Interdisciplinary Collaboration


## (no time) Predicting sequences

Motivating examples
- Difficult to satisfy i.i.d. assumption
- gene finding
- sequence alignment

Structured prediction
- Markov models
- hidden Markov models
- conditional random fields

Opportunities and challenges
- Recurrent neural networks, Attention models
- (trees) phylogenetic prediction
- (graphs) Alphafold2
