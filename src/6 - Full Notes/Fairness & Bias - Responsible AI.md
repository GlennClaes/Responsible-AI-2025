
2025-10-28 15:22

Status: Draft 
Tags: [[Full note]] [[Fairness]] [[Bias]] [[Responsible AI]]

# Topic - Fairness and Bias in AI

## Summary

This note provides an overview of fairness and bias in Artificial Intelligence (AI). Bias refers to systematic errors leading to unfair outcomes, often reflecting societal inequalities, while fairness is the complex, context-dependent effort to correct these biases and ensure equitable treatment. Addressing bias is crucial for trust and preventing harm, requiring a sociotechnical approach that combines technical methods with human oversight, governance, and ethical considerations.

---
## Key Points

- **Bias in AI** stems from data, algorithms, and human factors, leading to systematic errors and potentially harmful outcomes.

- **Fairness in AI** is a multi-faceted concept aiming to achieve equitable treatment, with various mathematical and socio-cultural definitions that can conflict.

- **AI-caused harms** include **Harm of Allocation** (unequal opportunities/resources) and **Harm of Quality-of-Service** (poorer performance for certain groups).

- **Identifying bias** requires examining data (skew, missing values) and evaluating model performance per subgroup using specific **fairness metrics**.

- **Mitigating bias** involves techniques at different stages: **pre-processing** (data modification), **in-processing** (algorithm modification), and **post-processing** (output modification).

- A purely technical approach is insufficient; a **sociotechnical framework** integrating social context, stakeholder engagement, human oversight, and regulation is necessary.

---
## Details / Explanation

### Defining Bias and Fairness

* **Bias:** Systematic errors leading to unwarranted differential treatment. Includes **statistical bias** (selection, measurement, algorithmic) and **social bias** (reflecting historical inequalities, stereotypes). Bias often amplifies existing societal inequities.

* **Fairness:** The attempt to correct algorithmic bias. It encompasses multiple, often conflicting, dimensions:
    * **Mathematical:** Demographic Parity, Equal Opportunity, Equalized Odds, Individual Fairness.
    * **Socio-cultural:** Distributive Justice, Procedural Justice, Contextual Fairness.
    * Fairness is a normative concept requiring value judgments, not just optimization.

### Types of Bias

* **Data-related:** Historical, Reporting, Selection (Coverage, Non-Response, Sampling), Measurement, Labeling Bias.

* **Algorithm/Model-related:** Algorithmic, Generative, Proxy Bias.

* **Human/Interaction-related:** Confirmation, Automation, Group Attribution (In-group, Out-group homogeneity), Implicit, Experimenter's Bias.

### Types of Fairness

* **Group Fairness:** Equal treatment/outcomes across defined groups (Metrics: Demographic Parity, Equal Opportunity, Equalized Odds).

* **Individual Fairness:** Similar individuals treated similarly.

* **Procedural Fairness:** Fair and transparent decision-making *process*.

* **Counterfactual Fairness:** Outcome consistency when changing only a sensitive attribute.

* **Causal Fairness:** Avoiding decisions based on historical biases by focusing on causal links.

### Identification and Mitigation

* **Identification:** Audit data for missing values, unexpected values, skew. Evaluate performance per subgroup using Fairness Metrics (e.g., disparity metrics in Azure). Tools like Azure ML Responsible AI Dashboard can help.

* **Mitigation:** Apply techniques across the ML lifecycle:
    * **Pre-processing:** Modify data (e.g., Reweighting, Resampling, Augmenting).
    * **In-processing:** Modify algorithm/training (e.g., Adversarial Debiasing, Regularization, Constraints, Adjusting loss function like MinDiff/CLP).
    * **Post-processing:** Adjust model outputs (e.g., Threshold Adjustment, Calibration).
    * Tools like Fairlearn and TensorFlow Model Remediation Library offer implementations.

### Sociotechnical Importance

* Purely technical fairness metrics have limitations (trade-offs, context-insensitivity, inability to satisfy multiple simultaneously).

* A broader **sociotechnical framework** is needed, integrating technical methods with social science insights, stakeholder engagement, robust human oversight, regulatory compliance, and continuous evaluation.

* Ethical frameworks, governance structures, and accountability are key components of Responsible AI.

---
## Actions / Follow-up

- When developing AI systems, proactively audit data for potential biases listed above.

- Evaluate model performance not just overall, but across relevant demographic or sensitive subgroups using appropriate fairness metrics.

- Select and apply bias mitigation techniques (pre-, in-, or post-processing) based on the specific context and feasibility.

- Adopt a sociotechnical perspective: involve diverse stakeholders, consider the broader impact, and establish clear governance and accountability.

---
## Sources / References

- [[JICES – Fairness & Bias in AI]]
- [[GeeksforGeeks – Fairness & Bias in AI]]
- [[Google – Fairness in ML]]
- [[Fiveable – Fairness in ML]]
- [[Microsoft – Fairness in ML]]
- [[Microsoft – Responsible AI]]
- [[Sustainability Directory – Mitigating Bias]]

---
## Notes / Reflections

- The choice of fairness metric(s) is crucial and depends heavily on the application's context and ethical considerations. There's often no single "right" answer.

- Mitigation is not a one-off fix; continuous monitoring and auditing are essential as data and societal contexts evolve.