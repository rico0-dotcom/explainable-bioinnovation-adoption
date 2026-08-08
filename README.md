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
Behavioural_Bias_Detection_Framework.ipynb

data/
│
├── unified_bio_discussion_data.csv
├── clustered_bio_innovations.csv
├── bias_analysis_results.csv
└── bias_summary.csv
```

---

# Dataset

The pilot dataset contains multilingual consumer discussions collected from online platforms relating to bio-based innovations including:

- Bio-based construction materials
- Mass timber
- Wood fibre insulation
- Bioplastics
- Sustainable packaging
- Engineered wood products

Dataset characteristics

- 100 consumer discussions
- English and Finnish
- Multiple online discussion platforms
- Preprocessed and translated into English for NLP analysis

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

# Example Findings

Pilot study (n = 100)

Most prevalent behavioural barriers:

| Behavioural Bias | Mean Probability |
|------------------|----------------:|
| Loss Aversion | 72.7% |
| Trust | 53.1% |
| Ambiguity Aversion | 43.0% |
| Social Norms | 36.6% |
| Status Quo Bias | 29.6% |
| Familiarity Bias | 17.9% |

These findings should be interpreted as exploratory observations from a proof-of-concept dataset rather than population estimates.

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

# Practical Applications

The proposed framework can support:

- Sustainable product marketing
- Forest bioeconomy research
- Behavioural economics
- Innovation adoption studies
- Explainable AI research
- Sustainability communication
- Consumer behaviour analysis
- Policy design

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
