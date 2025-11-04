## Source Material 
2025-10-28 13:46

Status: Draft 
Tags: [[Source Material]] [[3 - Tags/Other|Other]] [[Fairness]] [[Bias]] [[Machine Learning]]

# Fairness (Google Machine Learning Crash Course)

**Type:** Online Course Material / Module
**Creator / Author:** Google for Developers 
**Date / Year:** August 25, 2025 (Last Updated)
**URL / Location:** https://developers.google.com/machine-learning/crash-course/fairness

## Description

This online module explains the importance of evaluating machine learning models for fairness beyond standard loss metrics. It introduces different types of human bias that can appear in training data and provides strategies to identify, mitigate, and evaluate bias in model predictions. The learning objectives are to become aware of common biases, learn to explore data for bias sources, and evaluate model predictions for bias.

## Key Points

- **Human Bias in Data:** ML models learn from data curated by humans, making them susceptible to human biases.

- **Types of Bias Discussed:**
    - **Reporting Bias:** Frequency in data doesn't match real-world frequency.
    - **Historical Bias:** Data reflects past societal inequities.
    - **Automation Bias:** Tendency to favor automated system results over human ones, regardless of error rates.
    - **Selection Bias:** Data chosen isn't reflective of real-world distribution. Includes:
        - **Coverage Bias:** Not selecting data representatively.
        - **Non-Response Bias:** Participation gaps lead to unrepresentative data.
        - **Sampling Bias:** Lack of proper randomization during data collection.
    - **Group Attribution Bias:** Generalizing individual traits to a whole group. Includes:
        - **In-group Bias:** Preferring members of one's own group.
        - **Out-group Homogeneity Bias:** Stereotyping members of groups one doesn't belong to.
    - **Implicit Bias:** Assumptions based on personal experiences that don't generalize.
    - **Confirmation Bias:** Processing data in ways that affirm pre-existing beliefs.
    - **Experimenter's Bias:** Training a model until it confirms the builder's hypothesis.

- **Identifying Bias:** Look for missing feature values, unexpected feature values, and data skew (under/over-representation). Evaluate performance not just overall, but per subgroup.

- **Mitigating Bias:**
    - **Augmenting Training Data:** Collect more representative data (can be infeasible).
    - **Adjusting Model's Loss Function:** Use fairness-aware optimization functions.

- **Evaluating for Bias (Fairness Metrics):** Aggregate metrics can hide subgroup issues.
    - **Demographic Parity:** Compares overall acceptance/positive outcome rates across groups. Ensures proportional representation but ignores qualification distribution differences.
    - **Equality of Opportunity:** Compares acceptance/positive outcome rates *only for qualified individuals* across groups. Allows overall rates to differ if success rate for qualified individuals is equal. Requires a clear preferred label.
    - **Counterfactual Fairness:** Checks if changing a sensitive attribute for otherwise identical individuals changes the model's prediction. Useful when full demographic data is missing but doesn't give a holistic group view.

- **Choosing a Metric:** Depends on context and goals. Fairness definitions can be mutually incompatible.

## Notes

- The text emphasizes that the list of biases is not exhaustive.
- It positions fairness evaluation as a critical step before model deployment.
- The original text included examples which have been removed for brevity.

## References

- Wikipedia's catalog of cognitive biases.
- TensorFlow Model Remediation Library.
- Book: *Fairness and Machine Learning: Limitations and Opportunities* by Solon Barocas, Moritz Hardt, and Arvind Narayanan.