# Module 2: Eerlijkheid, Bias en Verklaarbaarheid (Ethische Kern)

## Responsible Artificial Intelligence (RAI)

**Versie:** 2.0 **Datum:** November 2025 **Status:** Volledig uitgewerkt

---

## Overzicht Module 2

**Doel van deze module:** Module 2 vormt de **ethische kern** van Responsible AI. Het gaat verder dan de principes (Module 1) door te focussen op de **praktische en theoretische mechanismen** om onwenselijk gedrag (bias) te corrigeren en de beslissingen van complexe modellen (**XAI**) transparant te maken, terwijl het een kader biedt voor de onvermijdelijke **ethische afwegingen**. Deze module definieert de **'Hoe' van ethische AI**:

- **Hoe:** Bias herkennen, meten, mitigeren en verklaren (2.1)
- **Hoe:** Modelbeslissingen transparant en verklaarbaar maken (2.2)
- **Hoe:** Ethische theorieën toepassen en menselijke factoren integreren in AI-besluitvorming (2.3)

---

## 2.1 Theorie van Bias en Fairness

### **Focus & Leerdoel**

Begrijp de aard en bronnen van **bias** en beheers de strategieën om **eerlijkheid** te herstellen.

---

### **De Drie Typen Bias**

Bias in AI-systemen kan op verschillende niveaus ontstaan en heeft impact op de fairness van uitkomsten. Gebaseerd op internationale frameworks (Microsoft, OECD) onderscheiden we **drie hoofdtypen bias**:

#### **1. Data Bias (Data-vooroordeel)**

**Definitie:** Vooroordelen die inherent zijn aan de data die gebruikt wordt voor training, validatie of testing van AI-modellen.

**Praktische betekenis:**

- **Bronnen:** Historische onevenwichtigheden (bijv. ondervertegenwoordiging van minderheidsgroepen in datasets), selectiebias (bijv. data verzameld uit specifieke regio's), of labeling bias (menselijke annotators met vooroordelen).
- **Impact:** Leidt tot modellen die discriminerende patronen versterken, zoals genderbias in gezichtsherkenningssystemen.

**Voorbeeld implementatie:**

- Dataset audits met tools zoals Facets (Google) om distributies te visualiseren.
- Data augmentation om ondervertegenwoordigde groepen te balanceren.

**Risico's bij afwezigheid:**

- Systematische discriminatie, zoals in COMPAS (Correctional Offender Management Profiling for Alternative Sanctions) waar Afro-Amerikaanse verdachten hoger risico scoorden.

---

#### **2. Algorithmic Bias (Algorithmisch vooroordeel)**

**Definitie:** Bias die ontstaat door de keuze van algoritmes, hyperparameters of optimalisatieprocessen.

**Praktische betekenis:**

- **Bronnen:** Algoritmes die gevoelig zijn voor bepaalde features (bijv. decision trees die overfit op correlaties in plaats van causaliteit), of verliesfuncties die fairness niet expliciet optimaliseren.
- **Impact:** Zelfs met gebalanceerde data kan het model oneerlijke beslissingen nemen, zoals in kredietscores waar inkomensproxies leiden tot indirecte discriminatie.

**Voorbeeld implementatie:**

- Fairness-aware machine learning met constrained optimization (bijv. in Fairlearn toolkit).
- Ensemble methods om bias van individuele modellen te verminderen.

**Risico's bij afwezigheid:**

- Versterking van bestaande ongelijkheden, zoals in Amazon's recruitment tool dat vrouwen benadeelde door mannelijke cv-patronen te prioriteren.

---

#### **3. Use Bias (Gebruiksvooroordeel)**

**Definitie:** Bias die optreedt tijdens de inzet of interpretatie van het AI-systeem in de real-world context.

**Praktische betekenis:**

- **Bronnen:** Misinterpretatie van modeloutputs door gebruikers, deployment in ongepaste contexten, of feedback loops waar bias zich versterkt (bijv. predictive policing dat meer patrouilles stuurt naar bias-gebieden).
- **Impact:** Leidt tot oneerlijke toepassingen, zelfs als het model technisch fair is.

**Voorbeeld implementatie:**

- User training en guidelines voor interpretatie.
- Post-deployment monitoring met drift detection tools.

**Risico's bij afwezigheid:**

- Maatschappelijke schade, zoals in social media algoritmes die polarisatie versterken door engagement-bias.

---

### **Vier Stappen van Bias-Analyse**

Om bias systematisch aan te pakken, volg deze **vier stappen** (gebaseerd op Microsoft's Responsible AI Standard):

1. **Identificatie:** Detecteer potentiële bias-bronnen door data audits, stakeholder consultaties en exploratory data analysis (EDA). Gebruik metrics zoals demographic parity difference.
2. **Meting:** Kwantificeer bias met fairness metrics (bijv. equalized odds, disparate impact ratio). Tools: AIF360 (IBM) voor statistische tests.
3. **Mitigatie:** Pas strategieën toe om bias te verminderen (zie onderstaande sectie).
4. **Evaluatie & Monitoring:** Valideer mitigaties en monitor continu in productie om drift te detecteren.

**Fairness Metrics Overzicht:**

|**Metric**|**Definitie**|**Toepassing**|**Voordeel**|
|---|---|---|---|
|**Demographic Parity**|Gelijke uitkomstkansen over groepen|Group fairness|Simpel te berekenen|
|**Equalized Odds**|Gelijke true/false positive rates|Individual fairness|Voorkomt discriminerende fouten|
|**Disparate Impact**|Ratio van uitkomsten tussen groepen|Legal compliance (80% rule)|Regulatorisch relevant|
|**Individual Fairness**|Gelijke behandeling voor gelijkaardige individuen|Personalized fairness|Voorkomt arbitraire verschillen|

---

### **Mitigatiestrategieën**

Bias mitigatie kan op drie momenten in de AI-levenscyclus plaatsvinden:

#### **1. Pre-processing (Voorafgaand aan training)**

- **Methoden:** Data resampling (oversampling minorities), reweighting samples, of feature removal (verwijder proxies voor protected attributes).
- **Voordelen:** Model-agnostisch; behoudt data integriteit.
- **Voorbeeld:** SMOTE (Synthetic Minority Over-sampling Technique) voor imbalanced datasets.

#### **2. In-processing (Tijdens training)**

- **Methoden:** Regularisatie termen in verliesfunctie (bijv. fairness constraints), adversarial debiasing (train discriminator om bias te detecteren).
- **Voordelen:** Directe optimalisatie voor fairness.
- **Voorbeeld:** Constrained optimization in TensorFlow Constrained Optimization library.

#### **3. Post-processing (Na training)**

- **Methoden:** Aanpassen van thresholds per groep, of calibration van probabilities.
- **Voordelen:** Geen hertraining nodig; snel deploybaar.
- **Voorbeeld:** ROC pivot method om equalized odds te bereiken.

**Trade-offs in Mitigatie:**

- Fairness vs. Accuracy: Mitigatie kan performance verminderen (bijv. 5-10% accuracy drop).
- Groep vs. Individueel: Groepsfairness kan individuele onrechtvaardigheden veroorzaken.

---

### **Koppeling met SDG 10 (Reduced Inequalities)**

**Waarom relevant:** Bias in AI kan ongelijkheden versterken; fairness strategieën dragen bij aan inclusieve samenleving.

**Praktische impact:**

- **Indicators:** 10.2.1 (sociale inclusie), 10.3.1 (anti-discriminatie).
- **Voorbeelden:** Fair AI in hiring (reduce gender gap), healthcare (equitable diagnostics).

**Strategische implementatie:**

- Integreer SDG 10 in bias audits.
- Report impact in sustainability verslagen.

---

### **Belangrijkste Bronnen - Submodule 2.1**

**Primaire bronnen:**

1. **Microsoft Responsible AI Principles**
    - Focus op fairness en bias mitigation.
    - Link: [https://www.microsoft.com/en-us/ai/principles-and-approach](https://www.microsoft.com/en-us/ai/principles-and-approach)
2. **OECD AI Principles (2024 update)**
    - Fairness en non-discriminatie.
    - Link: [https://oecd.ai/en/ai-principles](https://oecd.ai/en/ai-principles)
3. **Fairlearn Toolkit (Microsoft)**
    - Open-source voor bias meting en mitigatie.
    - Link: [https://fairlearn.org/](https://fairlearn.org/)
4. **AI Fairness 360 (IBM)**
    - Toolkit voor bias detectie.
    - Link: [https://aif360.res.ibm.com/](https://aif360.res.ibm.com/)

**Ondersteunende academische bronnen:**

- Barocas et al. (2019): "Fairness and Machine Learning" (MIT Press).
- Mehrabi et al. (2021): "A Survey on Bias and Fairness in Machine Learning" (ACM Computing Surveys).

---

## 2.2 Verklaarbaarheid en XAI

### **Focus & Leerdoel**

Krijg inzicht in de noodzaak van **transparantie** en de tools om modelbeslissingen uit te leggen.

---

### **Onderscheid tussen Interpreteerbaarheid en Verklaarbaarheid (XAI)**

**Interpreteerbaarheid:** De mate waarin een model inherent begrijpelijk is voor mensen, zonder extra tools (bijv. lineaire regressie).

**Verklaarbaarheid (XAI):** Methoden om complexe modellen (black-box) post-hoc uit te leggen, zelfs als ze niet inherent interpreteerbaar zijn (bijv. neural networks).

**Waarom onderscheid belangrijk?**

- Interpreteerbare modellen zijn eenvoudiger maar vaak minder accuraat.
- XAI maakt high-performance modellen toegankelijk voor uitleg, cruciaal voor trust en compliance.

**Niveaus van XAI:**

1. **Global:** Uitleg van het gehele model (bijv. feature importance).
2. **Local:** Uitleg van specifieke voorspellingen (bijv. waarom deze lening geweigerd?).

---

### **Theoretische Basis van LIME en SHAP**

#### **LIME (Local Interpretable Model-agnostic Explanations)**

**Definitie:** Creëert lokale surrogate modellen om individuele voorspellingen uit te leggen.

**Praktische betekenis:**

- **Hoe werkt het?** Perturbeert input data en traint een eenvoudig model (bijv. linear) rond de voorspelling.
- **Voordelen:** Model-agnostisch; werkt op images, text, tabular data.

**Voorbeeld implementatie:**

- In healthcare: Uitleg waarom een AI een diagnose stelt, door features te highlighten.
- Bibliotheek: lime (Python).

#### **SHAP (SHapley Additive exPlanations)**

**Definitie:** Gebaseerd op speltheorie (Shapley values) om feature contributions te berekenen.

**Praktische betekenis:**

- **Hoe werkt het?** Berekent marginale contributie van elke feature over alle permutaties.
- **Voordelen:** Consistent en additief; biedt global en local explanations.

**Voorbeeld implementatie:**

- In finance: SHAP plots voor kredietbeslissingen.
- Bibliotheek: shap (Python).

**Vergelijking LIME vs. SHAP:**

|**Aspect**|**LIME**|**SHAP**|
|---|---|---|
|**Scope**|Local only|Local + Global|
|**Basis**|Surrogate models|Game theory|
|**Computation**|Sneller voor locals|Meer accuraat maar computationeel intensief|
|**Gebruik**|Quick prototyping|Production explanations|

---

### **Documentatieconcepten: Model Cards en Data Sheets**

#### **Model Cards**

**Definitie:** Gestandaardiseerde documentatie voor modellen, inclusief intended use, performance, ethical considerations.

**Praktische betekenis:**

- **Inhoud:** Model details, benchmarks, bias evaluations, limitations.
- **Voordelen:** Verhoogt transparantie; helpt bij responsible deployment.

**Voorbeeld:** Google's Model Cards for vision models.

#### **Data Sheets**

**Definitie:** Datasheets voor datasets, beschrijvend compositie, collection process, biases.

**Praktische betekenis:**

- **Inhoud:** Motivation, composition, preprocessing, uses, distribution.
- **Voordelen:** Voorkomt misbruik; bevordert reproducibility.

**Voorbeeld:** Datasheets for Datasets (Gebru et al., 2021).

---

### **Risicogebaseerde Uitleg**

**Aanpak:** Pas XAI intensiteit aan op basis van risico (EU AI Act geïnspireerd).

- **High-risk:** Verplichte gedetailleerde explanations (bijv. SHAP voor medische AI).
- **Low-risk:** Basis transparantie voldoende.

**Implementatie:**

- Integreer in AI-levenscyclus: Design voor explainability.
- Tools: Responsible AI Toolbox (Microsoft) voor end-to-end XAI.

---

### **Belangrijkste Bronnen - Submodule 2.2**

**Primaire bronnen:**

1. **Microsoft Responsible AI Principles**
    - Transparency en explainability focus.
    - Link: [https://www.microsoft.com/en-us/ai/principles-and-approach](https://www.microsoft.com/en-us/ai/principles-and-approach)
2. **OECD AI Principles (2024 update)**
    - Transparency requirements.
    - Link: [https://oecd.ai/en/ai-principles](https://oecd.ai/en/ai-principles)
3. **SHAP Library**
    - Open-source tool.
    - Link: [https://shap.readthedocs.io/en/latest/](https://shap.readthedocs.io/en/latest/)
4. **LIME Library**
    - Open-source tool.
    - Link: [https://github.com/marcotcr/lime](https://github.com/marcotcr/lime)

**Ondersteunende academische bronnen:**

- Ribeiro et al. (2016): "Why Should I Trust You? Explaining the Predictions of Any Classifier" (LIME paper).
- Lundberg & Lee (2017): "A Unified Approach to Interpreting Model Predictions" (SHAP paper).
- Mitchell et al. (2019): "Model Cards for Model Reporting".

---

## 2.3 Ethische Theorie en Menselijke Factor

### **Focus & Leerdoel**

Pas klassieke **ethische modellen** toe op AI-besluitvorming en begrijp de rol van menselijke supervisie.

---

### **Ethische Modellen: Utilitarisme versus Deontologie**

#### **Utilitarisme**

**Definitie:** Ethiek gebaseerd op maximale nut voor de meerderheid (outcome-focused).

**Praktische betekenis in AI:**

- **Toepassing:** Optimaliseer voor overall performance (bijv. AI die meeste levens redt in autonomous vehicles).
- **Voordelen:** Kwantificeerbaar; align met data-driven decisions.

**Risico's:** Kan minderheden opofferen (bijv. trolley problem in AI).

#### **Deontologie**

**Definitie:** Ethiek gebaseerd op regels en plichten (rule-focused).

**Praktische betekenis in AI:**

- **Toepassing:** Volg absolute principes (bijv. nooit discrimineren, GDPR naleven).
- **Voordelen:** Beschermt individuele rechten.

**Risico's:** Kan inflexible zijn in complexe scenarios.

**Vergelijking:**

|**Model**|**Focus**|**AI Voorbeeld**|**Voordeel**|**Nadeel**|
|---|---|---|---|---|
|**Utilitarisme**|Outcomes|Maximaliseer accuracy|Efficient|Kan unfair zijn|
|**Deontologie**|Rules|Altijd fair behandelen|Rechtvaardig|Kan suboptimaal presteren|

---

### **De Rol van de Mens: Human-in/over-the-Loop**

**Human-in-the-Loop (HITL):** Menselijke interventie tijdens training/operatie (bijv. labeling data).

**Human-over-the-Loop (HOTL):** Menselijke oversight zonder directe interventie (bijv. approval van high-risk decisions).

**Praktische betekenis:**

- **Waarom nodig?** AI mist moreel oordeel; voorkomt catastrofale fouten.
- **Implementatie:** EU AI Act vereist human oversight voor high-risk.

**Voorbeelden:**

- HITL: Active learning in ML.
- HOTL: Escalation protocols in chatbots.

---

### **Het “Gap Problem” en Moral Dumbfounding**

**Gap Problem:** Kloof tussen AI's capaciteit om te voorspellen en moreel te redeneren.

**Moral Dumbfounding:** Mensen kunnen intuïtieve morele oordelen niet altijd uitleggen (Haidt, 2001).

**Praktische betekenis:**

- **Impact op AI:** Modellen kunnen "dumbfounded" decisions nemen zonder uitleg.
- **Oplossing:** Integreer XAI en ethische reviews.

---

### **Afweging tussen Performance, Fairness en Maatschappelijke Impact**

**Trade-offs:**

- **Performance vs. Fairness:** Hogere accuracy kan bias introduceren.
- **Fairness vs. Impact:** Short-term fairness kan long-term ongelijkheid verminderen (SDG link).

**Framework voor Afweging:**

1. **Assess Impact:** Gebruik AI Impact Assessments.
2. **Prioriteer:** Gebaseerd op stakeholders en risico.
3. **Documenteer:** Transparant over trade-offs.

---

### **Belangrijkste Bronnen - Submodule 2.3**

**Primaire bronnen:**

1. **Microsoft Responsible AI Principles**
    - Accountability en human oversight.
    - Link: [https://www.microsoft.com/en-us/ai/principles-and-approach](https://www.microsoft.com/en-us/ai/principles-and-approach)
2. **OECD AI Principles (2024 update)**
    - Human-centred values.
    - Link: [https://oecd.ai/en/ai-principles](https://oecd.ai/en/ai-principles)
3. **UNESCO Ethics of AI**
    - Ethische modellen.
    - Link: [https://unesdoc.unesco.org/ark:/48223/pf0000380455](https://unesdoc.unesco.org/ark:/48223/pf0000380455)

**Ondersteunende academische bronnen:**

- Floridi et al. (2021): "Ethics of AI" (Oxford University Press).
- Haidt (2001): "The Emotional Dog and Its Rational Tail" (moral dumbfounding).

---

## Samenvattende Conclusie Module 2

### **Wat hebben we geleerd?**

**Submodule 2.1** heeft ons de **theorie van bias** gegeven:

- Drie typen bias en vier stappen voor analyse.
- Mitigatiestrategieën en link met SDG 10.

**Submodule 2.2** heeft ons **XAI** geïntroduceerd:

- Interpreteerbaarheid vs. verklaarbaarheid.
- Tools zoals LIME, SHAP, Model Cards.

**Submodule 2.3** heeft ons **ethische besluitvorming** geleerd:

- Utilitarisme vs. Deontologie.
- Human-in/over-the-Loop, Gap Problem.
- Afwegingen in AI.

### **Waarom is dit belangrijk?**

**Voor organisaties:** Mitigeert risico's, voldoet aan EU AI Act.

**Voor AI professionals:** Bouwt ethische skills op.

**Voor de samenleving:** Bevordert fairness en trust.

### **Volgende stappen**

Module 3: Risk assessment, etc.

**Reflectievragen:**

1. Wat zijn de drie typen bias?
2. Verschil LIME en SHAP?
3. Utilitarisme vs. Deontologie in AI?
4. Wat is Human-in-the-Loop?

---

## Appendix: Aanvullende Resources

### **Online Courses en Certificeringen**

1. **Coursera: Responsible AI Practices**
2. **edX: Explainable AI**

### **Key Organizations en Networks**

1. **Partnership on AI**
2. **AI Ethics Guidelines Global Inventory**

### **Tools en Platforms**

1. **Responsible AI Toolbox**
2. **Aequitas (bias audit)**

### **Regelmatige Updates Volgen**

1. **OECD.AI**
2. **AI Index (Stanford)**

---

## Document Metadata

**Auteur:** [Naam] **Organisatie:** [Organisatie] **Versie:** 2.0 **Laatste update:** November 2025 **Review datum:** Februari 2026 (geplanned)

**Versiehistorie:**

- v1.0 (Oktober 2025): Initiële draft
- v2.0 (November 2025): Volledige uitwerking

**Feedback en verbeteringen:** Feedback welkom via [contact].

**Licentie:** Creative Commons CC BY-SA 4.0

---

**Einde Module 2: Eerlijkheid, Bias en Verklaarbaarheid (Ethische Kern)**