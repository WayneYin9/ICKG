# Expert Validation of Industrial Chain Knowledge Graph (ICKG)

This repository provides the **human expert validation dataset, annotation protocol, and evaluation reports** for assessing the quality of the Industrial Chain Knowledge Graph (ICKG) construction pipeline.

The validation focuses on the correctness of automatically extracted entity–relation–entity triples from news texts.

> **Important**:  
> This dataset is used **exclusively for evaluation and analysis purposes** and **was not used for model training**.

---

## 1. Dataset Overview

- **Task**: Verification of extracted industrial chain knowledge triples
- **Domain**: Financial and industrial news
- **Evaluation Unit**: (Head Entity, Relation, Tail Entity)
- **Total Samples**: **2,000**
- **Annotators**: **3 domain experts**
- **Annotation Type**: Binary correctness judgment with ambiguity guidelines

---

## 2. File Structure

| File | Description |
|---|---|
| `annotated_samples.jsonl` | Expert-annotated validation dataset (2,000 samples) |
| `annotation_guidelines.pdf` | Official annotation protocol provided to experts |
| `expert_profiles.md` | Background descriptions of annotators (anonymized) |
| `agreement_stats.md` | Inter-annotator agreement (IAA) analysis |
| `expert_validationbaseline_comparison.csv` | Performance comparison with baseline systems |

---

## 3. Validation Dataset (`annotated_samples.jsonl`)

The validation dataset consists of **2,000 randomly sampled triples** extracted from heterogeneous financial news sources across different time periods.

Each entry links the automatically extracted triple, and the final expert judgment.

### Data Format

```json
{
  "text_id": "news_1_0",
  "triple": ["Wind Power", "includes", "New Energy Generation"],
  "prediction": "correct",
  "expert_label": "correct"
}
````

### Field Description

* `text_id`: Unique identifier of the source document
* `triple`: Extracted knowledge triple
  *(Head Entity, Relation, Tail Entity)*
* `prediction`: Model prediction result
* `expert_label`: Final expert judgment (`correct` / `incorrect`)

---

## 4. Human Annotation Protocol

### 4.1 Annotation Guidelines (`annotation_guidelines.pdf`)

All experts followed a unified and predefined annotation protocol to ensure consistency and reproducibility.

The guidelines specify:

* **Entity Boundary Rules**
  (e.g., company names, industry concepts)
* **Relation Validity**
  Whether the relation is explicitly stated or strongly implied
* **Label Definitions**:

  * **Correct**: Factually accurate triple with clear entity boundaries
  * **Incorrect**: Wrong entities, relations, or unsupported claims
  * **Ambiguous**: Insufficient context for reliable verification

---

### 4.2 Annotator Profiles (`expert_profiles.md`)

Three domain experts participated in the validation process:

* **Expert A**: Industrial policy analysis (8+ years experience)
* **Expert B**: PhD researcher in supply chain systems
* **Expert C**: Senior enterprise knowledge management engineer

All annotators were independent and anonymized.

---

## 5. Inter-Annotator Agreement (`agreement_stats.md`)

To assess annotation reliability, inter-annotator agreement (IAA) was measured before consensus aggregation.

* **Fleiss’ Kappa**: **0.82**
* **Average Pairwise Agreement**: **89.5%**

According to standard interpretation, these values indicate **strong agreement**, supporting the reliability of the expert judgments.

---

## 6. Evaluation and Baseline Comparison

### 6.1 Baselines (`expert_validationbaseline_comparison.csv`)

The ICKG system is compared against commonly used extraction baselines and human upper bounds:

* `Baseline_BERT`
* `Baseline_OpenIE`
* `Our_Model_ICKG`
* `Human_Expert`

### 6.2 Results Summary

| Model              | Precision | Recall   | F1       |
| ------------------ | --------- | -------- | -------- |
| **Our_Model_ICKG** | **0.89**  | **0.86** | **0.87** |
| Baseline_BERT      | 0.72      | 0.68     | 0.70     |
| Baseline_OpenIE    | 0.65      | 0.55     | 0.60     |
| Human_Expert       | 0.96      | 0.94     | 0.95     |

The proposed ICKG approach substantially outperforms general-purpose baselines while remaining within a reasonable margin of human expert performance.

---

## 7. Reproducibility Notes

* All evaluation metrics are computed **solely on the expert-validated dataset**
* No additional preprocessing is required
* The dataset is self-contained and independent of model training code

This artifact is intended to support **transparent evaluation and reproducibility** of the human validation results reported in the paper.

