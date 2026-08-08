# Explainable AI for Detecting Behavioural Biases in Consumer Discussions on Bio-Based Innovations

> An Explainable NLP Framework for Understanding Behavioural Barriers to Bio-Based Innovation Adoption

---

## Overview

This repository presents a proof-of-concept Natural Language Processing (NLP) framework for automatically identifying behavioural barriers influencing the adoption of bio-based innovations within the forest bioeconomy.

The project was developed as an independent research prototype inspired by behavioural economics, sustainability communication, explainable artificial intelligence (XAI), and computational social science.

Instead of simply classifying consumer opinions as positive or negative, the framework identifies **behavioural biases** that influence adoption decisions and translates them into actionable communication strategies for firms and policymakers.

The study demonstrates how modern transformer models can be combined with topic modelling and interpretable keyword extraction to analyse consumer discussions surrounding bio-based products.

---

# Research Motivation

The transition towards a sustainable bioeconomy depends not only on technological innovation but also on consumer acceptance.

Although bio-based materials often provide environmental benefits, consumers frequently hesitate to adopt unfamiliar products because of behavioural biases such as:

- Status Quo Bias
- Loss Aversion
- Ambiguity Aversion
- Familiarity Bias
- Trust
- Social Norms

Understanding these behavioural barriers is essential for designing effective communication strategies capable of accelerating sustainable innovation adoption.

---

# Research Objective

This project develops an explainable NLP framework capable of:

- Discovering major discussion themes related to bio-based innovations.
- Detecting behavioural biases using zero-shot transformer models.
- Providing interpretable evidence supporting behavioural classifications.
- Translating behavioural insights into communication recommendations.
- Demonstrating a scalable methodology for analysing consumer adoption barriers.

---

# Methodology

The framework integrates multiple NLP techniques into a single behavioural analysis pipeline.

```
Consumer Discussions
        │
        ▼
Data Cleaning & Translation
        │
        ▼
Sentence Embeddings
(all-MiniLM-L6-v2)
        │
        ▼
BERTopic Topic Discovery
        │
        ▼
Zero-Shot Behavioural Bias Detection
(BART-Large-MNLI)
        │
        ▼
KeyBERT Explainability
        │
        ▼
Behavioural Analysis
        │
        ▼
Communication Recommendations
```

---

# Behavioural Biases Analysed

The framework identifies six behavioural constructs derived from behavioural economics literature.

| Behavioural Bias | Description |
|------------------|-------------|
| Status Quo Bias | Preference for existing products over new alternatives |
| Loss Aversion | Fear of potential losses associated with adopting unfamiliar products |
| Ambiguity Aversion | Avoidance caused by uncertainty regarding product performance |
| Familiarity Bias | Preference for products already known or previously experienced |
| Trust | Lack of confidence in manufacturer claims or product performance |
| Social Norms | Influence of perceived behaviour within the surrounding community |

---

# Technologies Used

- Python
- BERTopic
- Sentence Transformers
- BART Large MNLI
- KeyBERT
- Scikit-Learn
- Pandas
- NumPy
- SciPy
- Jupyter Notebook

---

# Repository Structure

```
explainable-bioinnovation-adoption/
│
├── README.md
├── requirements.txt
│
├── notebook/
│   └── Explainable_Behavioural_Bias_Detection.ipynb
│
├── data/
│   └── unified_bio_discussion_data.csv
│
├── outputs/
    ├── clustered_bio_innovations.csv
    ├── bias_analysis_results.csv
    └── bias_summary.csv
```

---

# Dataset

The dataset includes discussions gathered from:

- Reddit (r/Construction, r/HomeImprovement, r/woodworking, r/environment, r/sustainability)
- Public Finnish discussion forums
- Online discussions relating to:
  - Mass timber
  - Cross-laminated timber (CLT)
  - Engineered wood products
  - Wood fibre insulation
  - Bio-based packaging
  - Bioplastics
  - Hempcrete
  - Sustainable construction materials

Dataset characteristics

| Attribute | Value |
|-----------|------:|
| Documents | 100 |
| Languages | English, Finnish |
| Translation | Finnish translated into English before NLP processing |
| Topic Modelling | BERTopic |
| Behavioural Classification | Zero-shot Natural Language Inference |
| Explainability | KeyBERT |

The dataset should be viewed as a pilot corpus intended to demonstrate the proposed methodology rather than provide population-level behavioural estimates.

---

# Behavioural Analysis Pipeline

The notebook performs the following analyses.

## 1. Data Preparation

- Language standardisation
- Text preprocessing
- Translation validation

---

## 2. Topic Modelling

BERTopic is used to discover major discussion themes.

Example topics include:

- Uncertainty About Novel Bio-Materials
- Risk Aversion in Material Decisions

---

## 3. Behavioural Bias Detection

A zero-shot Natural Language Inference (NLI) model (facebook/bart-large-mnli) estimates the probability of each behavioural bias using natural language hypotheses.

Example hypothesis:

> "The consumer fears potential losses from adopting this product."

---

## 4. Explainability

Instead of treating predictions as black boxes, KeyBERT extracts representative keyphrases providing qualitative evidence supporting each behavioural classification.

Example:

```
Loss Aversion

Evidence

• concrete blocks
• drainage risk
• timber buildings
• fibre boards
```

---

## 5. Aggregate Behavioural Analysis

The framework reports:

- Overall behavioural bias prevalence
- Dominant behavioural barriers
- Topic-level behavioural profiles
- Language comparisons
- Statistical significance testing
- Communication recommendations

---

# Key Findings

The proposed framework successfully identified behavioural barriers within multilingual discussions on bio-based innovations.

## Aggregate Behavioural Bias Prevalence

| Behavioural Construct | Mean Probability |
|-----------------------|----------------:|
| Loss Aversion | 72.7% |
| Trust | 53.1% |
| Ambiguity Aversion | 43.0% |
| Social Norms | 36.6% |
| Status Quo Bias | 29.6% |
| Familiarity Bias | 17.9% |

Loss aversion emerged as the dominant behavioural barrier across the pilot dataset, indicating that consumers frequently emphasised perceived risks and potential losses associated with adopting unfamiliar bio-based products. Trust and ambiguity aversion were also prominent, suggesting that uncertainty regarding product performance and confidence in manufacturer claims remain important adoption barriers.

These findings should be interpreted as exploratory observations from a proof-of-concept dataset rather than population estimates.

---

# Topic Discovery

BERTopic identified two dominant discussion themes:

| Topic | Interpretation |
|--------|----------------|
| Topic 0 | Uncertainty About Novel Bio-Materials |
| Topic 1 | Risk Aversion in Material Decisions |

These themes indicate that consumer discussions were primarily centred around uncertainty, perceived performance risk, and comparisons between established construction materials and emerging bio-based alternatives. :contentReference[oaicite:1]{index=1}

---

# Statistical Validation

Behavioural bias probabilities were compared between English and Finnish discussions using the Mann–Whitney U test.

| Behavioural Construct | p-value | Interpretation |
|-----------------------|--------:|----------------|
| Status Quo Bias | 0.0162 | Significant |
| Ambiguity Aversion | 0.0139 | Significant |
| Loss Aversion | 0.1387 | Not Significant |
| Familiarity Bias | 0.0978 | Not Significant |
| Trust | 0.0034 | Significant |
| Social Norms | 0.0193 | Significant |

The analysis indicates statistically significant cross-language differences in four behavioural constructs, suggesting that behavioural responses to bio-based innovations may vary across linguistic and cultural contexts. Loss aversion remained consistently high across both language groups and did not differ significantly.

---

# Outputs Generated

Running the notebook produces:

- Behavioural bias probabilities
- BERTopic topic assignments
- Aggregate bias statistics
- Topic-level bias analysis
- Language comparison
- Mann–Whitney statistical tests
- Behavioural evidence extraction
- Communication recommendations

Generated CSV files

```
bias_analysis_results.csv

bias_summary.csv

clustered_bio_innovations.csv
```

---

# Research Implications

The findings suggest that promoting bio-based innovations requires more than communicating environmental benefits.

Instead, communication strategies should address the behavioural mechanisms underlying consumer resistance.

The pilot study indicates that:

- Loss aversion should be mitigated through warranties, guarantees, and economic case studies.
- Trust should be strengthened through independent certification and transparent performance reporting.
- Ambiguity aversion should be reduced by providing long-term durability evidence and accessible technical documentation.

The proposed framework demonstrates how explainable NLP can convert large collections of consumer discussions into actionable behavioural insights for firms and policymakers. 

---

# Limitations

This project is intended as a proof-of-concept.

Current limitations include:

- Pilot dataset (n = 100)
- Zero-shot inference instead of supervised fine-tuning
- Limited number of discussion platforms
- Exploratory behavioural inference
- BERTopic results depend on corpus size

Future work will include larger multilingual datasets, manually annotated behavioural labels, supervised transformer fine-tuning, and broader validation.

---

# Future Work

Planned extensions include:

- 1,000+ multilingual consumer discussions
- Fine-tuned transformer classifiers
- Human-annotated behavioural datasets
- Interactive Streamlit dashboard
- Publication-quality visualisations
- Cross-country behavioural comparisons
- Explainability benchmarking
- Research paper submission

---

# Research Contribution

This project proposes an explainable NLP methodology for analysing behavioural barriers to sustainable innovation adoption.

The framework combines:

- Behavioural Economics
- Explainable AI
- Computational Social Science
- Sustainability Communication
- Transformer-based NLP

to generate interpretable behavioural insights from unstructured consumer discussions.

---

# Citation

If you use this repository in academic work, please cite:

```
Pal, A.
Explainable AI for Detecting Behavioural Biases in Consumer Discussions on Bio-Based Innovations.
GitHub Repository.
```

---

# License

This repository is released under the MIT License.

---

# Author

**Anuj Pal**

MBA (Finance)

Research interests

- Behavioural Economics
- Sustainable Finance
- Explainable AI
- Computational Social Science
- Natural Language Processing
- Innovation Adoption
