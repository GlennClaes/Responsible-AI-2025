## Source Material 

2025-10-28 14:29

Status: Draft 
Tags: [[Source Material]] [[3 - Tags/Article|Article]] [[Fairness]] [[Bias]] [[Model Performance]] [[Azure Machine Learning]] [[Fairlearn]]

# Model performance and fairness

**Author(s):** Azure Machine Learning Documentation Team
**Publication:** Microsoft Learn
**Date Published:** September 30, 2024 (Last Updated)
**URL:** https://learn.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml?view=azureml-api-2

## Summary

This article describes methods available in Azure Machine Learning to understand model performance and fairness. It defines unfair AI behavior through the lens of harms (allocation and quality-of-service), introduces the concept of group fairness using sensitive features, and explains how the Responsible AI dashboard and the Fairlearn open-source package help assess fairness via disparity metrics and mitigate unfairness using parity constraints and specific algorithms.

## Key Points

- **AI-caused Harms:** Defines **Harm of allocation** (withholding opportunities/resources) and **Harm of quality-of-service** (system working poorly for certain groups).

- **Group Fairness:** Fairness is conceptualized as group fairness, focusing on risks for groups defined by **sensitive features**.

- **Fairness Assessment:** Done by quantifying fairness through **disparity metrics** (ratios or differences).
    - **Disparity in model performance:** Compares performance metrics (accuracy, error rate, precision, recall, MAE) across subgroups.
    - **Disparity in selection rate:** Compares the rate of favorable predictions (e.g., loan approval) across subgroups.

- **Fairlearn Package:** Azure ML's fairness capabilities come from the Fairlearn open-source package, providing assessment metrics and mitigation algorithms.

- **Fairness is Socio-technical:** Quantitative metrics alone don't capture all aspects (like justice); human judgment and qualitative analysis are essential. Multiple fairness metrics often cannot be satisfied simultaneously.

- **Mitigation via Parity Constraints:** Mitigation algorithms aim to make predictor behavior comparable across groups based on sensitive features, using **parity constraints**. Supported constraints include Demographic Parity, Equalized Odds, Equal Opportunity, and Bounded Group Loss.

- **Mitigation Algorithms (from Fairlearn):**
    - **Reduction:** Retrains models using reweighted datasets (e.g., ExponentiatedGradient, GridSearch).
    - **Post-processing:** Transforms predictions of an existing classifier without retraining (e.g., ThresholdOptimizer).

## Quotes

> "Fairness is a socio-technical challenge. Quantitative fairness metrics don't capture many aspects of fairness, such as justice and due process. Also, many quantitative fairness metrics can't all be satisfied simultaneously."

> "Ultimately, it's up to the humans who build AI and machine learning models to make trade-offs that are appropriate for their scenarios."

## References

- NeurIPS 2017 keynote by Kate Crawford (Mentioned for types of harm)
- Fairlearn open-source package (Used for assessment and mitigation)
- Azure Machine Learning Responsible AI dashboard (Tool for visualization and assessment)
- Paper: *A Reductions Approach to Fair Classification* (Basis for ExponentiatedGradient and GridSearch)
- Paper: *Fair Regression: Quantitative Definitions and Reduction-based Algorithms* (Basis for GridSearch in regression)
- Paper: *Equality of Opportunity in Supervised Learning* (Basis for ThresholdOptimizer)
