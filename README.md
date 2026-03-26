# LLM Human Evaluation Analysis

Two-stage analysis of human preference evaluation data comparing large language model outputs across a range of prompt types and evaluation settings. Completed as part of a professional AI evaluation and data annotation role.

## Overview

### Stage 1 — Bard vs ChatGPT (`RLHF Evaluation Data Analysis - Bard v GPT/`)

Analysis of a 1,003-record human preference evaluation dataset comparing Google Bard and ChatGPT across 13 prompt categories. Human evaluators rated each response pair on a 1–7 scale, where 1 = Bard much better and 7 = ChatGPT much better.

**Prompt categories:** Coding, Creative Writing, Mathematical Reasoning, Summarization, Extraction, Classification, Open QA, Closed QA, Brainstorming, Rewriting, Poetry, Adversarial Harmfulness, Adversarial Dishonesty

**Key findings:**
- ChatGPT was preferred overall across the majority of categories, with particularly strong performance in coding (71.7% preference), creative writing (73.7%), and poetry (83.5%)
- Bard performed most competitively in adversarial and open-ended categories, where ChatGPT's tendency toward over-elaboration was penalised
- Adversarial Harmfulness showed the most evenly distributed preferences (32.9% Bard, 41.4% ChatGPT, 32.9% neutral), suggesting different refusal strategies with different evaluator reactions
- Mathematical Reasoning showed the highest rate of neutral ratings, consistent with both models producing structurally similar step-by-step outputs

**Deliverable:** Written analysis report with visualisations and category-level recommendations, delivered within a 3-day deadline. The client commissioned a follow-up project (Stage 2) based on the quality of this work.

---

### Stage 2 — Multi-Model RLHF Evaluation (`RLHF Evaluation Data Analysis - RAG, Jailbreak, MT, LC/`)

Multi-axis evaluation of three LLMs across four specialised evaluation settings: Multi-Turn General conversation, Retrieval-Augmented Generation (RAG), Long Context comprehension, and Jailbreaking resistance. Model identities are anonymised per client requirements (referred to as Model A, Model B, and GPT-4o).

**Evaluation settings:**
- **Multi-Turn General:** multi-turn conversational coherence and helpfulness
- **RAG:** accuracy and groundedness of responses given retrieved context
- **Long Context:** performance on tasks requiring comprehension of extended input documents
- **Jailbreaking:** robustness of safety mechanisms against adversarial prompts

**Deliverable:** Slide deck with visualisations and model-level recommendations across all four settings.

---

## Repository Structure

```
.
├── README.md
├── requirements.txt
├── .gitignore
├── RLHF Evaluation Data Analysis - Bard v GPT/
│   ├── LLM_Human_Eval_bardgpt.ipynb       # Analysis notebook
│   └── human eval_ Bard_vs_ChatGPT.csv    # Human evaluation dataset (1,003 records)
└── RLHF Evaluation Data Analysis - RAG, Jailbreak, MT, LC/
    ├── LLM Human Eval Dataset Analysis.ipynb  # Analysis notebook
    ├── Multi-axis evaluation.xlsx             # Source data (4 evaluation sheets)
    ├── Jailbreak Averages.csv
    ├── Long Context csv.csv
    ├── MT General Averages.csv
    ├── RAG Averages.csv
    ├── jailbreak.csv
    ├── mt_b24.csv
    ├── mt_b31.csv
    ├── mt_gpt.csv
    ├── rag_b24.csv
    └── rag_gpt.csv
```

## Running the Notebooks

Both notebooks were developed in Google Colab. To run locally:

1. Install dependencies:
```bash
pip install -r requirements.txt
```

2. Update the file path in the first data-loading cell to point to the local CSV/xlsx file rather than a Colab `/content/` path.

## Technical Stack

- Python 3.10
- `pandas` — data loading, cleaning, grouping
- `matplotlib`, `seaborn` — visualisation (bar charts, pie charts, stacked proportion charts, heatmaps)
- `numpy` — numerical operations
