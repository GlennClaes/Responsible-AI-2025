## Source Material 
2025-10-28 14:50

Status: Draft 
Tags: [[Source Material]] [[3 - Tags/Other|Other]] [[Fairness]] [[Bias]] [[Machine Learning]]

# 13.1 Fairness in Machine Learning

**Type:** Online Course Material / Study Guide
**Creator / Author:** The Fiveable Content Team
**Date / Year:** September 2025 (Last Updated)
**URL / Location:** https://fiveable.me/machine-learning-engineering/unit-13/fairness-machine-learning/study-guide/Gw1jdTs0Gu6UMN4t

## Description

This study guide explains that fairness in machine learning is crucial to prevent bias and discrimination in AI systems. It discusses the need to address biases in data and algorithms using techniques like pre-processing, in-processing, and post-processing. Evaluating fairness involves various metrics and requires considering ethical implications in domains like hiring and lending.

## Key Points

- **Fairness Definition:** Prevents bias based on protected attributes (race, gender, etc.), encompassing individual and group fairness. It involves trade-offs with model performance and has legal/ethical dimensions.

- **Bias Types:** Data collection bias (non-representative data), historical bias (past prejudices), measurement bias (inaccurate capture), sampling bias (non-random selection), labeling bias (human annotator bias). Algorithmic bias (design choices) and proxy bias (neutral features acting as proxies for protected ones).

- **Mitigation Techniques:**
    - **Pre-processing:** Modify data (resampling, reweighting, synthetic data).
    - **In-processing:** Modify algorithms (adversarial debiasing, fairness-aware regularization, constrained optimization, etc.).
    - **Post-processing:** Adjust model outputs (threshold adjustment, calibrated equalized odds).
    - **Ensemble Methods:** Combine multiple models.
    - **Causal Inference:** Identify and mitigate unfair causal relationships.

- **Fairness Evaluation Metrics:**
    - **Demographic Parity:** Equal probability of positive outcomes across groups.
    - **Equal Opportunity:** Equal true positive rates across groups.
    - **Equalized Odds:** Equal true positive *and* false positive rates across groups.
    - **Disparate Impact Ratio:** Compares proportion of positive outcomes between groups.

- **Advanced Evaluation Techniques:** Intersectional fairness (multiple attributes), qualitative analysis (expert review, user studies), stability assessment (cross-validation, bootstrapping), dynamic evaluation (time-series analysis, A/B testing).

## Notes

- The text emphasizes that the list of biases is not exhaustive.
- It positions fairness evaluation as a critical step before model deployment.
- The original text included examples which have been removed for brevity.

## References

(No external references explicitly listed)