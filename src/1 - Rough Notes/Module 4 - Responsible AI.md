# Module 4: Privacy, Robuustheid en Operationele Implementatie

## Responsible Artificial Intelligence (RAI)

## **Versie:** 2.0 **Datum:** November 2025 **Status:** Volledig uitgewerkt


The BUC model forms the foundation for managing the model throughout its lifecycle:

- **4.3 Operational Implementation and Model Management:** The BUC becomes the source of truth for the scope and functional requirements within **MLOps** and **Model Risk Management**. If the operational model (drift rate, fairness) no longer meets the original BUC requirements, action must be taken (Incident Response Plan, Decommissioning).
    

## Overzicht Module 4

**Doel van deze module:** Module 4 vormt de **operationele en technische verdediging** van Responsible AI. Het richt zich op de bescherming van data en modellen, en het beheren van de AI-levenscyclus. Deze module definieert de **'Hoe' van veilige en robuuste implementatie**:

- **Hoe:** Data beschermen met privacy-technieken (4.1)
- **Hoe:** Modellen beveiligen tegen bedreigingen (4.2)
- **Hoe:** De AI-pijplijn operationeel beheren (4.3)

## Het BUC-model (Business Use Case) speelt een centrale rol als bron van waarheid voor scope en eisen, en verbindt de submodules door bedrijfsdoelen te alignen met privacy-assessments, robuustheidschecks en levenscyclusbeheer.

## 4.1 Concepten van Privacy en Veiligheid

### **Focus & Leerdoel**

## Begrijp de bescherming van gevoelige data door ontwerp en geavanceerde technieken, inclusief koppeling aan duurzame doelen.

### **Belangrijkste Privacy Concepten**

Privacy in AI zorgt voor de bescherming van persoonlijke data doorheen de levenscyclus. Gebaseerd op frameworks (Microsoft, OECD) onderscheiden we **kernprincipes en technieken**:

#### **Privacy by Design**

**Definitie:** Privacy integreren vanaf het ontwerp van AI-systemen, in plaats van achteraf. **Praktische betekenis:**

- **Bronnen:** Embed privacy in architectuur, processen en cultuur.
- **Impact:** Voorkomt datalekken en bouwt vertrouwen op. **Voorbeeld implementatie:**
- Bij Microsoft: Systemen ontwerpen met privacy en security in gedachten.
- Integratie met BUC: Definieer data-eisen in BUC om privacy-risico's vroeg te identificeren. **Risico's bij afwezigheid:**
- Datalekken en non-compliance met GDPR.

---

#### **Privacy-Enhancing Technologies (PETs)**

**Definitie:** Tools die data-analyse mogelijk maken zonder privacy te schenden. **Praktische betekenis:**

- **Bronnen:** Omvatten technieken voor veilige data-deling en -analyse.
- **Impact:** Maakt samenwerking mogelijk in gevoelige domeinen zoals biomedisch onderzoek. **Voorbeeld implementatie:**
- Gebruik in AI: Bolster privacy met combinaties van technieken.

---

#### **Differential Privacy**

**Definitie:** Voegt ruis toe aan data om individuele privacy te beschermen terwijl statistische inzichten behouden blijven. **Praktische betekenis:**

- **Hoe werkt het?** Kwantificeert privacy-verlies met epsilon-waarde.
- **Voordelen:** Beschermt tegen re-identificatie. **Voorbeeld implementatie:**
- In AI-training: Gebruik libraries zoals Opacus in PyTorch.

---

#### **Federated Learning**

**Definitie:** Train modellen decentraal op apparaten, zonder data te centraliseren. **Praktische betekenis:**

- **Hoe werkt het?** Aggregatie van model-updates in plaats van ruwe data.
- **Voordelen:** Reduceert data-overdracht risico's. **Voorbeeld implementatie:**
- In healthcare: Train op gedistribueerde patient data.

---

#### **Homomorphic Encryption**

**Definitie:** Berekeningen uitvoeren op versleutelde data zonder decryptie. **Praktische betekenis:**

- **Hoe werkt het?** Ondersteunt operaties op ciphertext.
- **Voordelen:** Houdt data veilig tijdens verwerking. **Voorbeeld implementatie:**
- In AI-modellen: Bouw modellen op encrypted data. **Vergelijking PETs:** |**Techniek****Focus****Voordeel****Uitdaging**| |---|---|---|---| |**Differential Privacy**|Statistische privacy|Simpel te implementeren|Trade-off accuracy| |**Federated Learning**|Decentrale training|Geen data-centralisatie|Communicatie overhead| |**Homomorphic Encryption**|Encrypted computing|Volledige beveiliging|Computationeel intensief|

---

### **Koppeling aan SDG 16 (Veiligheid, Rechtvaardigheid)**

**Waarom relevant:** Privacy beschermt rechten en bevordert veilige instituties. **Praktische impact:**

- **Indicators:** 16.10.1 (privacy bescherming), 16.6.1 (transparante instituties).
- **Strategische implementatie:** Integreer PETs in BUC voor SDG-aligned AI.

---

### **Belangrijkste Bronnen - Submodule 4.1**

**Primaire bronnen:**

1. **Microsoft Responsible AI Principles**
    - Privacy focus.
    - Link: [https://www.microsoft.com/en-us/ai/principles-and-approach](https://www.microsoft.com/en-us/ai/principles-and-approach)
2. **OECD AI Principles (2024 update)**
    - Privacy requirements.
    - Link: [https://oecd.ai/en/ai-principles](https://oecd.ai/en/ai-principles) **Ondersteunende academische bronnen:**

- CIPL PETs and PPTs in AI (2025).
- ITIF Technology Explainer on PETs (2025).

---

## 4.2 Theorie van Robuustheid en Veiligheid

### **Focus & Leerdoel**

## Identificeer en mitigeer bedreigingen voor de integriteit en stabiliteit van AI-modellen.

### **Belangrijkste Bedreigingen**

Robuustheid zorgt voor betrouwbare AI onder adversariale condities. Gebaseerd op frameworks onderscheiden we **drie hoofdtypen bedreigingen**:

#### **1. Adversarial Attacks**

**Definitie:** Manipulatie van inputs om modellen te misleiden. **Praktische betekenis:**

- **Bronnen:** Perturbaties in data (bijv. pixels in images).
- **Impact:** Leidt tot verkeerde outputs. **Voorbeeld implementatie:**
- In computer vision: Kleine veranderingen veroorzaken misclassificatie. **Risico's bij afwezigheid:**
- Veiligheidsissues in autonome systemen.

---

#### **2. Data Poisoning**

**Definitie:** Injectie van malafide data in training sets. **Praktische betekenis:**

- **Bronnen:** Gericht op training fase.
- **Impact:** Compromitteert model gedrag. **Voorbeeld implementatie:**
- In federated learning: Malicious updates. **Risico's bij afwezigheid:**
- Langdurige model corruptie.

---

#### **3. Model Inversion**

**Definitie:** Reconstrueren van training data uit model outputs. **Praktische betekenis:**

- **Bronnen:** Exploit van model queries.
- **Impact:** Onthult gevoelige info. **Voorbeeld implementatie:**
- In generative AI: Herstel confidential data. **Risico's bij afwezigheid:**
- Privacy schendingen.

---

### **Beveiligingsstrategieën**

#### **Red Teaming**

**Definitie:** Simuleren van attacks om kwetsbaarheden te testen. **Praktische betekenis:**

- **Hoe:** Interactieve testing.
- **Voordelen:** Verhoogt veiligheid. **Voorbeeld:** In generative AI: Test op vulnerabilities.

---

#### **Safety Case**

**Definitie:** Documentatie van veiligheid en mitigations. **Praktische betekenis:**

- **Hoe:** Systematische risk assessment.
- **Voordelen:** Bewijst compliance. **Voorbeeld:** Voor high-risk AI onder EU AI Act. **Vergelijking Strategieën:** |**Strategie****Focus****Voordeel****Toepassing**| |---|---|---|---| |**Red Teaming**|Adversariale simulatie|Proactieve detectie|Pre-deployment| |**Safety Case**|Documentatie|Compliance|Doorlopend|

---

### **Belangrijkste Bronnen - Submodule 4.2**

**Primaire bronnen:**

1. **Microsoft Responsible AI Principles**
    - Safety and reliability.
    - Link: [https://www.microsoft.com/en-us/ai/principles-and-approach](https://www.microsoft.com/en-us/ai/principles-and-approach)
2. **OECD AI Principles (2024 update)**
    - Robustness and safety.
    - Link: [https://oecd.ai/en/ai-principles](https://oecd.ai/en/ai-principles) **Ondersteunende academische bronnen:**

- NIST Adversarial ML (2025).
- Securing AI Systems (arXiv 2025).

---

## 4.3 Conceptueel Modelbeheer

### **Focus & Leerdoel**

## Implementeer operationele processen voor de verantwoorde AI-levenscyclus.

### **Belangrijkste Concepten**

Modelbeheer omvat tools en processen voor duurzame AI. Gebaseerd op frameworks:

#### **MLOps met Ethische Checks**

**Definitie:** Automatisering van ML-pijplijnen met RAI integratie. **Praktische betekenis:**

- **Bronnen:** Inclusief monitoring en retraining.
- **Impact:** Handhaaft performance. **Voorbeeld implementatie:**
- Drift detection en adaptive models.
- Integratie met BUC: Monitor afwijkingen van BUC-eisen.

---

#### **Drift Monitoring en Fairness Dashboards**

**Definitie:** Detecteer veranderingen in data/model performance. **Praktische betekenis:**

- **Hoe:** Gebruik metrics en tools.
- **Voordelen:** Voorkomt degradatie. **Voorbeeld:** Responsible AI dashboard in Azure ML.

---

#### **Model Risk Management (MRM)**

**Definitie:** Risico's beheren doorheen levenscyclus. **Praktische betekenis:**

- **Hoe:** Assessments en governance.
- **Voordelen:** Reduceert enterprise risks. **Voorbeeld:** Bias en fairness monitoring.

---

#### **Synthetische Data (GANs)**

**Definitie:** Genereer fake data met GANs voor training. **Praktische betekenis:**

- **Hoe:** Privacy-vriendelijk alternatief voor real data.
- **Voordelen:** Mitigeert privacy risico's. **Voorbeeld:** In RAI voor bias testing.

---

#### **Decommissioning en Incident Response Plan**

**Definitie:** Veilig uitschakelen van modellen en reageren op incidents. **Praktische betekenis:**

- **Hoe:** Protocollen voor retirement en crisismanagement.
- **Voordelen:** Minimaliseert schade. **Voorbeeld:** Bij drift of bias escalatie.

---

### **Koppeling aan TRL en Strategische Risicoanalyse**

**TRL Levels:** Assess maturity van AI-technologieën. **Praktische impact:**

- **Integratie:** Gebruik TRL in MRM voor readiness checks. **Overzicht TRL in AI:** |**TRL****Beschrijving****AI Voorbeeld**| |---|---|---| |**1**|Basic principles|Theoretische AI concepten| |**9**|Proven in operations|Volledig gedeployde AI systemen|

---

### **Belangrijkste Bronnen - Submodule 4.3**

**Primaire bronnen:**

1. **Technology Readiness Levels (NASA)**
    - Maturity assessment.
    - Link: [https://www.nasa.gov/directorates/somd/space-communications-navigation-program/technology-readiness-levels/](https://www.nasa.gov/directorates/somd/space-communications-navigation-program/technology-readiness-levels/)
2. **OECD AI Principles (2024 update)**
    - Lifecycle management.
    - Link: [https://oecd.ai/en/ai-principles](https://oecd.ai/en/ai-principles) **Ondersteunende academische bronnen:**

- Data Drift Detection (2024).
- MLOps Guide (2025).

---

## Samenvattende Conclusie Module 4

### **Wat hebben we geleerd?**

**Submodule 4.1** heeft ons **privacy concepten** gegeven:

- Privacy by Design, PETs (Differential Privacy, Federated Learning, Homomorphic Encryption).
- Koppeling aan SDG 16. **Submodule 4.2** heeft ons **robuustheid threats** geïntroduceerd:
- Adversarial Attacks, Data Poisoning, Model Inversion.
- Strategieën zoals Red Teaming en Safety Case. **Submodule 4.3** heeft ons **modelbeheer** geleerd:
- MLOps, Drift Monitoring, MRM, Synthetic Data, Decommissioning.
- Koppeling aan TRL.

### **Waarom is dit belangrijk?**

**Voor organisaties:** Mitigeert risico's, voldoet aan regelgeving. **Voor AI professionals:** Bouwt veilige skills op. **Voor de samenleving:** Beschermt privacy en veiligheid.

### **Volgende stappen**

Module 5: Governance, etc. **Reflectievragen:**

1. Wat zijn de drie PETs?
2. Verschil adversarial attacks en data poisoning?
3. Rol van MLOps in RAI?
4. Belang van BUC in modelbeheer?

---

## Appendix: Aanvullende Resources

### **Online Courses en Certificeringen**

1. **Coursera: Privacy in AI**
2. **edX: AI Security**

### **Key Organizations en Networks**

1. **IAPP (International Association of Privacy Professionals)**
2. **NIST AI**

### **Tools en Platforms**

1. **Fiddler AI for Monitoring**
2. **Fairlearn for Fairness**

### **Regelmatige Updates Volgen**

1. **OECD.AI**
2. **NIST Publications**

---

## Document Metadata

**Auteur:** [Naam] **Organisatie:** [Organisatie] **Versie:** 2.0 **Laatste update:** November 2025 **Review datum:** Februari 2026 (geplanned) **Versiehistorie:**

- v1.0 (Oktober 2025): Initiële draft
- v2.0 (November 2025): Volledige uitwerking **Feedback en verbeteringen:** Feedback welkom via [contact]. **Licentie:** Creative Commons CC BY-SA 4.0

---

**Einde Module 4: Privacy, Robuustheid en Operationele Implementatie**

Zoekresultaten

[

[PDF] Privacy-Enhancing and Privacy- Preserving Technologies in AI:

Using other PETs, such as differential privacy or homomorphic encryption, in conjunction with federated learning, can bolster privacy and security. e ...

informationpolicycentre.com



](https://www.informationpolicycentre.com/uploads/5/7/1/0/57104281/cipl_pets_and_ppts_in_ai_mar25.pdf)

[

ITIF Technology Explainer: What Are Privacy Enhancing ...

Privacy-enhancing technologies (PETs) are tools that enable entities to access, share, and analyze sensitive data without exposing personal ...

itif.org



](https://itif.org/publications/2025/09/02/itif-technology-explainer-privacy-enhancing-technologies/)

[

PETs: Beyond privacy-enhancing - IAPP

Homomorphic encryption, however, allows users to perform operations and build models on encrypted data without needing to decrypt it first, ...

iapp.org



](https://iapp.org/news/a/pets-beyond-privacy-enhancing)

[

[PDF] Privacy enhancing technologies - Mastercard

Privacy enhancing technologies (PETs) are introduced to share financial crime data without revealing underlying data or who is querying it.

b2b.mastercard.com



](https://b2b.mastercard.com/media/z0pnu32l/privacy-enhancing-technologies-white-paper-final.pdf)

[

Privacy-Enhancing Technologies in Biomedical Data Science - PMC

Privacy-enhancing technologies (PETs) safeguard biomedical data, enabling sharing and analysis of sensitive data while protecting privacy. Examples include ...

pmc.ncbi.nlm.nih.gov



](https://pmc.ncbi.nlm.nih.gov/articles/PMC11346580/)

[

Pivot to PETs: What You Need to Know About Privacy Enhancing ...

PETs enable companies to embed privacy-by-design principles, minimizing personal data collection, use, and sharing while maximizing data security.

loeb.com



](https://www.loeb.com/en/insights/publications/2022/03/pets-what-you-need-to-know-about-privacy-enhancing-technologies)

[

Privacy-Enhancing Technologies for Artificial Intelligence-Enabled ...

In this paper, we investigate potential threats and propose the use of several privacy-enhancing technologies (PETs) to defend AI-enabled systems.

arxiv.org



](https://arxiv.org/html/2404.03509v1)

[

Privacy Enhancing Technologies

Privacy Enhancing Technologies (PETs) safeguard individual privacy while enabling research and data sharing. Examples include differential privacy and ...

fpf.org



](https://fpf.org/issue/privacy-enhancing-technologies/)

[

Evaluation and utilisation of privacy enhancing technologies—A ...

In this work, we review existing PETs and assess their relevance, technological maturity, and applicability in the context of common European data spaces.

sciencedirect.com



](https://www.sciencedirect.com/science/article/pii/S2352340924005274)

[

All About Privacy-Enhancing Technologies (PETS) - Sify

Homomorphic encryption: One of the most well-known of all PETs, this allows third parties to manipulate and process data in its encrypted form.

sify.com



](https://www.sify.com/security/all-about-privacy-enhancing-technologies-pets/)

[

6 Key Adversarial Attacks and Their Consequences - Mindgard

Poisoning attacks target the training phase of AI models, injecting malicious data into the training set to compromise the model's behavior. How ...

mindgard.ai



](https://mindgard.ai/blog/ai-under-attack-six-key-adversarial-attacks-and-their-consequences)

[

AI Red Teaming: How Enterprises Test and Harden Their AI Systems

Training data can be compromised through poisoning attacks. Model architectures may contain backdoors or exhibit biased behaviors.

obsidiansecurity.com



](https://www.obsidiansecurity.com/blog/ai-red-teaming)

[

AI Safety in Practice

Red teaming is a safety testing practice in which evaluators simulate adversarial attacks to interactively test AI models with the purpose of deliberately ...

aiethics.turing.ac.uk



](https://aiethics.turing.ac.uk/module-pages/risks-posed-to-security-and-robustness/)

[

Testing the limits of generative AI: How red teaming exposes ... - IBM

Model inversion attacks can, therefore, allow malicious actors to reconstruct training data, potentially revealing confidential information in the process.

ibm.com



](https://www.ibm.com/think/insights/testing-the-limits-of-generative-ai-red-teaming-exposes-vulnerabilities-in-ai-models)

[

Securing AI Systems: A Guide to Known Attacks and Impacts - arXiv

Data poisoning attacks involve intentionally inserting malicious data into an AI model's training dataset, aiming either to compromise the ...

arxiv.org



](https://arxiv.org/html/2506.23296v1)

[

[PDF] Adversarial Machine Learning - NIST Technical Series Publications

Data poisoning attacks are applicable to all learning paradigms, while model poisoning attacks are most prevalent in federated learning [190], ...

nvlpubs.nist.gov



](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2025.pdf)

[

What Are Adversarial AI Attacks on Machine Learning? - Palo Alto ...

An adversarial AI attack is a malicious technique that manipulates machine learning models by deliberately feeding them deceptive data to cause incorrect or ...

paloaltonetworks.com



](https://www.paloaltonetworks.com/cyberpedia/what-are-adversarial-attacks-on-AI-Machine-Learning)

[

Adversarial AI & Model Hardening: Defense Against Attacks - Medium

This article delves into adversarial AI threats, real-world case studies, advanced defensive strategies, and best practices for securing AI models against ...

medium.com



](https://medium.com/%2540dave-patten/adversarial-ai-model-hardening-defense-against-attacks-299dc80439f6)

[

AI Data Poisoning: How Corrupted Data Undermines Trust in Agents

Without regular red team exercises and adversarial validation, poisoned models can reach production environments undetected. Mitigation ...

obsidiansecurity.com



](https://www.obsidiansecurity.com/blog/ai-data-poisoning)

[

[PDF] Risks and Mitigation Strategies for Adversarial Artificial Intelligence ...

Some effective strategies to help mitigate the risk of data poisoning attacks include regular data sanitization and cleaning, data diversity, ...

dhs.gov



](https://www.dhs.gov/sites/default/files/2023-12/23_1222_st_risks_mitigation_strategies.pdf)

[

[PDF] Data drift detection and mitigation: A comprehensive MLOps ...

Therein, we propose an end-to-end MLOps solution for handling the drift and using automated drift detection, retraining techniques and adaptive models for ...

ijsra.net



](https://ijsra.net/sites/default/files/IJSRA-2024-0724.pdf)

[

The Ultimate Guide to MLOps in 2025: Scalable AI in Action

MLOps (Machine Learning Operations) unifies ML development, IT operations, and automation to deploy, monitor, and scale models with confidence.

superwise.ai



](https://superwise.ai/blog/the-ultimate-guide-to-mlops-best-practices-and-scalable-tools-for-2025/)

[

MLOps: Monitoring and Managing Drift - Open Data Science

Your machine learning model is always going to change over time, so how do you monitor and manage drift when it occurs?

opendatascience.com



](https://opendatascience.com/mlops-monitoring-and-managing-drift/)

[

MLOps Resources - Fiddler AI

Learn how to effectively manage the machine learning model lifecycle and discover how Fiddler streamlines model monitoring for enterprise success.

fiddler.ai



](https://www.fiddler.ai/topic/mlops)

[

(PDF) Data drift detection and mitigation: A comprehensive MLOps ...

Therein, we propose an end-to-end MLOps solution for handling the drift and using automated drift detection, retraining techniques and adaptive ...

researchgate.net



](https://www.researchgate.net/publication/388187259_Data_drift_detection_and_mitigation_A_comprehensive_MLOps_approach_for_real-time_systems)

[

Assess AI systems by using the Responsible AI dashboard

The Responsible AI dashboard provides a single interface to help you implement Responsible AI in practice effectively and efficiently.

learn.microsoft.com



](https://learn.microsoft.com/en-us/azure/machine-learning/concept-responsible-ai-dashboard?view=azureml-api-2)

[

Yields' Post - LinkedIn

(Source: PwC, 2024) Responsible AI isn't just an IT decision; it's enterprise risk management. With hallucinations, bias, and data leaks on ...

linkedin.com



](https://www.linkedin.com/posts/yields_ai-datascience-modelriskmanagement-activity-7338552860923609089-qhLT)

[

When machine learning models retire, decay, or become obsolete

The rapid adoption of artificial intelligence (AI) has introduced new layers of complexity to technology governance and environmental resource management [1].

sciencedirect.com



](https://www.sciencedirect.com/science/article/pii/S1364032125009049)

[

MLOps & AI Governance – Model Management & Responsible AI

Automated data and model drift detection. Statistical performance tracking and feedback loops. Bias and fairness monitoring using SHAP, LIME, and Fairlearn.

trigyn.com



](https://www.trigyn.com/services/data-and-ai/mlops-and-ai-governance)

[

Model drift, data leaks and deepfakes: Rethinking AI governance in ...

Today, AI governance teams find themselves confronted with real-time incidents that resemble those of cybersecurity or crisis management, ...

iapp.org



](https://iapp.org/news/a/model-drift-data-leaks-and-deepfakes-rethinking-ai-governance-in-the-age-of-autonomous-risk)

[

Responsible AI Principles and Approach | Microsoft AI

Responsible AI Principles and Approach | Microsoft AI This is the Trace Id: eee9a51c773faefb098bf21ada9037ef Microsoft Responsible AI # Principles and approach We're committed to developing AI systems in a way that is transparent, reliable, and worthy of trust. A couple of women sitting at a table with a laptop. ## The Microsoft Responsible AI Standard Explore guidance from Microsoft on how to design, build, and test AI systems. Principles ## Defining what’s important We've identified six principles that we believe should guide AI development and use. ### Fairness AI systems should treat all people fairly. How might an AI system allocate opportunities, resources, and information in ways that are fair to the humans who use it? ### Reliability and safety AI systems should perform reliably and safely. How might a system function well for people across different use conditions and contexts, including ones that it wasn’t originally intended for? ### Privacy and security AI systems shou

microsoft.com



](https://www.microsoft.com/en-us/ai/principles-and-approach)

[

AI Principles Overview - OECD.AI

# OECD AI Principles overview The OECD AI Principles promote use of AI that is innovative and trustworthy and that respects human rights and democratic values. Adopted in May 2019, they set standards for AI that are practical and flexible enough to stand the test of time. ## Principles for trustworthy AI The OECD AI Principles were [initially adopted in 2019](https://www.oecd.org/science/forty-two-countries-adopt-new-oecd-principles-on-artificial-intelligence.htm) and [updated in May 2024](https://legalinstruments.oecd.org/en/instruments/OECD-LEGAL-0449). Adherents updated them to consider new technological and policy developments, ensuring they remain robust and fit for purpose. The Principles guide AI actors in their efforts to develop trustworthy AI and provide policymakers with recommendations for effective AI policies. Countries use the OECD AI Principles and related tools to shape policies and create AI risk frameworks, building a foundation for global interoperability between jurisdictions. Today, th

oecd.ai



](https://oecd.ai/en/ai-principles)

[

Technology Readiness Levels - NASA

Due to the lapse in federal government funding, NASA is not updating this website. 2 min read # Technology Readiness Levels Technology Readiness Levels (TRL) are a type of measurement system used to assess the maturity level of a particular technology. Each technology project is evaluated against the parameters for each technology level and is then assigned a TRL rating based on the projects progress. There are nine technology readiness levels. TRL 1 is the lowest and TRL 9 is the highest. [](https://www.nasa.gov/wp-content/uploads/2023/09/trl.png) Technology Readiness Levels When a technology is at TRL 1, scientific research is beginning and those results are being translated into future research and development. TRL 2 occurs once the basic principles have been studied and practical applications can be applied to those initial findings. TRL 2 technology is very speculative, as there is little to no experimental proof of concept for the technology. When active research and design begin, a technology i

nasa.gov



](https://www.nasa.gov/directorates/somd/space-communications-navigation-program/technology-readiness-levels/) 