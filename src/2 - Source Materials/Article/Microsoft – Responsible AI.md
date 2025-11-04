## Source Material 

2025-10-28 14:03

Status: Draft 
Tags: [[Source Material]] [[3 - Tags/Article|Article]] [[Responsible AI]] [[Microsoft Azure]] [[Fairness]] [[Bias]] [[Transparency]] [[Accountability]]

# What is Responsible AI?

**Author(s):** Azure Machine Learning Documentation Team
**Publication:** Microsoft Learn
**Date Published:** October 9, 2025 (Last Updated)
**URL:** https://learn.microsoft.com/en-us/azure/machine-learning/concept-responsible-ai?view=azureml-api-2

## Summary

This document defines Responsible Artificial Intelligence (Responsible AI) as an approach to developing, assessing, and deploying AI systems safely, ethically, and trustworthily. It outlines Microsoft's **Responsible AI Standard**, based on six core principles: fairness, reliability and safety, privacy and security, inclusiveness, transparency, and accountability. The article details how specific tools within **Azure Machine Learning** help developers implement and operationalize these principles.

## Key Points

- **Definition:** Responsible AI guides AI development decisions towards beneficial and equitable outcomes, centering on people and values like fairness, reliability, and transparency.

- **Microsoft's Six Principles:**
    - **Fairness & Inclusiveness:** AI systems should treat everyone fairly and avoid affecting similar groups differently. Azure ML Tool: **Fairness assessment** component in the Responsible AI dashboard.
    - **Reliability & Safety:** Systems must operate reliably, safely, consistently, handle unexpected conditions, and resist manipulation. Azure ML Tool: **Error analysis** component in the Responsible AI dashboard.
    - **Transparency:** People should understand how AI decisions impacting them are made. Involves **interpretability**. Azure ML Tools: **Model interpretability** and **counterfactual what-if** components in the Responsible AI dashboard; **Responsible AI scorecard** (PDF report).
    - **Privacy & Security:** Protecting privacy and securing data is crucial, especially given AI's data dependency. Compliance with privacy laws is necessary. Azure ML Features: Secure configurations (access control, network restrictions, encryption, vulnerability scanning, policy audits). Open-source tools: **SmartNoise** (Differential Privacy) and **Counterfit** (adversarial attack simulation).
    - **Accountability:** Designers and deployers are accountable for system operations. Humans should maintain meaningful control. Azure ML Features: **MLOps** capabilities (model registration/tracking, governance data capture, notifications/alerts, monitoring); **Responsible AI scorecard**; Decision-support tools (**causal inference** and **counterfactual what-if** components).

## Quotes

> "Responsible Artificial Intelligence (Responsible AI) is an approach to developing, assessing, and deploying AI systems safely, ethically, and with trust."

> "It keeps people and their goals at the center of design and respects values like fairness, reliability, and transparency."

## References

- Microsoft Responsible AI Standard
- Azure ML Responsible AI dashboard Components (Fairness assessment, Error analysis, Model interpretability, Counterfactual what-if, Causal inference)
- Azure ML Responsible AI scorecard
- Azure ML Secure configurations
- SmartNoise (Open Source Differential Privacy)
- Counterfit (Open Source Adversarial Simulation)
- Azure ML MLOps capabilities
