
### **Core Problem:**

* **Bias in AI:** Systematic errors leading to unfair or skewed outcomes. Not just a technical anomaly, often reflects/amplifies societal inequalities. Arises from data, algorithm design, human biases.

* **Fairness in AI:** The attempt to correct algorithmic bias and ensure equitable treatment. It's a complex, subjective, context-dependent, and normative concept, not purely technical optimization. Multiple, sometimes conflicting definitions exist.

---
### **Why important?:**

* AI can cause **Harms**:
    * **Harm of Allocation:** Withholding opportunities/resources for certain groups (e.g., hiring, loans).
    * **Harm of Quality-of-Service:** System works poorly for certain groups (e.g., voice recognition).

* Reinforces existing inequalities and stereotypes.

* Crucial for **trust**, ethics, equality, and social justice.

* **Corporate Principles (e.g., Microsoft):** Fairness & Inclusiveness, Reliability & Safety, Privacy & Security, Transparency, Accountability.

---
### **Types of Bias:**

* **Data-related:**
    * **Historical Bias:** Data reflects past societal inequities.
    * **Reporting Bias:** Frequency in data ≠ real-world frequency.
    * **Selection Bias:** Data chosen isn't reflective of real-world distribution. Includes:
        * **Coverage Bias:** Not selecting data representatively.
        * **Non-Response Bias:** Participation gaps in data collection.
        * **Sampling Bias:** Improper randomization during collection.
    * **Measurement Bias:** Over/under-representation due to how data is measured.
    * **Labeling Bias:** Biases introduced by human annotators.

* **Algorithm/Model-related:**
    * **Algorithmic Bias:** Flaws in algorithm design/implementation.
    * **Generative Bias:** Unbalanced outputs in generative models.
    * **Proxy Bias:** Neutral features indirectly acting as proxies for sensitive attributes.

* **Human/Interaction-related:**
    * **Confirmation Bias:** Processing data in ways that affirm pre-existing beliefs.
    * **Automation Bias:** Over-reliance on automated systems.
    * **Group Attribution Bias:** Generalizing group characteristics to individuals (incl. In-group bias, Out-group homogeneity).
    * **Implicit Bias:** Assumptions based on one's own experiences.
    * **Experimenter's Bias:** Training a model until it confirms a hypothesis.

---
### **Types of Fairness:**

* **Mathematical/Quantitative:**
    * **Group Fairness:** Equal treatment/outcomes across groups. Metrics:
        * **Demographic Parity:** Equal proportion of positive outcomes.
        * **Equal Opportunity:** Equal True Positive Rates (for 'qualified' group).
        * **Equalized Odds:** Equal True Positive *and* False Positive Rates.
    * **Individual Fairness:** Similar individuals treated similarly.
    * **Counterfactual Fairness:** Outcome doesn't change if a sensitive attribute (hypothetically) changes for otherwise identical individuals.

* **Process/Contextual:**
    * **Procedural Fairness:** Fair and transparent decision-making *process*.
    * **Causal Fairness:** Decisions not based on historical bias; focus on causal relationships.

* **Socio-cultural:** Distributive justice, contextual fairness.

---
### **Identification & Evaluation of Bias:**

* Look for missing values, unexpected values, data skew (under/over-representation).

* Evaluate model performance **per subgroup**, not just aggregate.

* Use **Fairness Metrics** (Demographic Parity, Equal Opportunity, Equalized Odds, Disparate Impact Ratio, Counterfactual Fairness). Azure ML dashboard offers Disparity in model performance & selection rate.

* **Advanced Evaluation:** Intersectionality, qualitative analysis, stability (cross-validation), dynamic evaluation (A/B testing).

* **Tools:** Azure ML Responsible AI Dashboard (Fairness assessment, Error analysis).

---
### **Mitigation of Bias:**

* **Pre-processing:** Modify data *before* training (Resampling, Reweighting, Synthetic data generation, Data auditing).

* **In-processing:** Modify algorithm/training process (Adversarial debiasing, Fairness-aware regularization, Fairness constraints, Modifying loss functions - e.g., MinDiff, Counterfactual Logit Pairing). Fairlearn "Reduction" algorithms (ExponentiatedGradient, GridSearch) fall here.

* **Post-processing:** Modify model outputs *after* training (Threshold adjustment, Calibration). Fairlearn "Post-processing" algorithm (ThresholdOptimizer).

* **Other:** Ensemble methods, Causal inference.

* **Tools:** Fairlearn package, TensorFlow Model Remediation Library.

---
### **Broader Context & Frameworks:**

* **Sociotechnical Perspective:** Purely technical solutions are insufficient. Need integration of social context, stakeholder engagement, human oversight (human-in-the-loop), regulation.

* **Frameworks:** Sociotechnical framework (paper Emerald), Microsoft Responsible AI Standard.

* **Governance:** Ethical guidelines, accountability mechanisms, impact assessments, audits, transparency. Azure MLOps supports accountability.

* **Philosophical/Sustainability:** Connections to justice theories (Rawls, Utilitarianism), intergenerational equity.

---