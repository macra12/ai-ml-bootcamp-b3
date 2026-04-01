# Week 1 Day 1 - Homework Assignment

## Mapping the ML Universe

---

## Part 1: Conceptual Exercises

Complete these three exercises before moving on to the coding section. They do not require any code — write your answers as comments or in a separate markdown/text file called `w1d1-concepts.md`.

---

### Exercise A: Classify Real-World ML Problems

For each scenario below, determine:
- Problem type (`classification`, `regression`, `clustering`, or `generative`)
- At least 2 likely input features
- What the model output would be

| Scenario | Problem Type | Input Features | Output |
|----------|-------------|----------------|--------|
| Predict whether a loan applicant will default | Classification | credit score, income, loan amount | yes/no |
| Forecast next month's energy consumption for a city | Regression | temperature, historical energy usage, population | numeric value(kWh) |
| Group customers by purchasing behavior | Clustering | purchase frequency, average spend, product categories bought | customer groups/segments |
| Detect fraudulent credit card transactions | Clustering | transaction amount, location, time of transaction | fraud / not fraud |
| Generate product descriptions from an image | Generative | image pixels/features, object type, detected attribute | text description of product |
| Predict the severity (1–5) of a patient's condition | Reression | heart rate, blood pressure, age | severity score from 1 to 5 |

**How to think about it**:

- Start by asking: *"What does the model output?"* — is it a category, a number, a group, or new content?
- For input features, ask: *"What information would a human expert look at to make this decision?"*
- Watch out for tricky cases: an output that looks like a number (e.g., a severity score 1–5) might still be treated as classification — think about whether the *distance* between values matters.
- If no labeled examples exist in the scenario, clustering is likely the right framing.
- If the model is asked to *produce* something new rather than predict a pre-existing value, lean toward generative.

---

### Exercise B: Map the ML Lifecycle

**Scenario**: A hospital wants to predict which patients admitted to the ER are at high risk of readmission within 30 days.

For each lifecycle step, write 2–3 sentences describing what would happen in this specific scenario.

```
1. Problem Definition:   The hospital wants to predict whether a patient will be readmitted within 30 days after discharge. The output will be a risk score or a yes/no risk label used by doctors and case managers. Success means identifying high-risk patients early enough to intervene and reduce readmissions.
2. Data Collection:      The hospital would use existing electronic health records (EHR), including past admissions, lab results, diagnoses, prescriptions, and demographic data. Data from multiple years (e.g., 3–5 years) would be ideal to capture patterns over time. A large dataset is needed to ensure enough examples of readmitted patients.
3. EDA & Preprocessing:  Medical records may contain missing values, inconsistent entries, and rare diagnosis codes. There is likely class imbalance because most patients are not readmitted. Categorical data like diagnosis codes and medication types need to be encoded into numerical features.
4. Model Training:       A baseline model like logistic regression or decision trees would be a good starting point for interpretability. More advanced models like random forests or gradient boosting could improve performance later. Interpretability matters because clinicians need to understand why a patient is considered high risk.
5. Evaluation:           Accuracy alone is not enough because false negatives (missing a high-risk patient) are more serious than false positives. Metrics like recall, precision, and especially ROC-AUC or F1-score are more meaningful. The goal is to correctly identify as many high-risk patients as possible.
6. Deployment:           The model output would appear in the hospital dashboard or patient management system as a risk score. Doctors and nurses would use it to decide follow-ups, extra tests, or early interventions. It should also include explanations like key contributing factors (e.g., previous admissions, high blood pressure).
7. Monitoring:           Over time, patient populations, treatment methods, or hospital policies may change, causing model drift. Monitoring would track prediction performance and changes in input data distributions. Alerts would trigger if accuracy or recall drops significantly or if feature patterns shift.
```

**How to think about each step**:

- **Problem Definition**: Pin down *what exactly* is being predicted, who will act on the prediction, and what "good enough" looks like in business terms.
- **Data Collection**: What records does the hospital already store? How far back should you go? What's a realistic minimum dataset size?
- **EDA & Preprocessing**: What could be messy or missing in medical records? Are there obvious class imbalances? How do you turn diagnosis codes into model-friendly features?
- **Model Training**: Should you start simple or complex? Why might interpretability matter here more than in other industries?
- **Evaluation**: Why might raw accuracy be misleading? What metric would better capture real usefulness?
- **Deployment**: Who sees the output? What context would a nurse or case manager need alongside a risk score?
- **Monitoring**: What real-world changes could make the model go stale? How would you detect this before users notice?

---

### Exercise C: AI vs ML vs Deep Learning Sorting

Label each system as **Rule-based AI**, **Classical ML**, or **Deep Learning**. Write one sentence justifying your choice.

1. A chess engine that evaluates positions using a hand-crafted evaluation function: Rule-based AI
2. A spam filter trained on 10 million labeled emails using random forest: Classical ML
3. GPT-4 generating text responses: Deep Learning
4. Netflix's collaborative filtering recommendation engine: Classical ML
5. A thermostat that adjusts temperature based on time-of-day rules: Rule-based AI
6. A CNN that detects tumors in medical images: Deep Learning
7. A decision tree that approves/rejects credit card applications based on features: Classical ML

**How to think about it**:

- Ask: *"Does this system learn from data, or does a human write all the rules?"* — if a human encodes the logic explicitly, it's rule-based AI.
- Ask: *"Is this working with raw unstructured data (images, text, audio) at scale?"* — if yes, Deep Learning is likely involved.
- A decision tree *algorithm* trained on data is Classical ML even though the output looks like a set of rules.
- For ambiguous cases (e.g., collaborative filtering): think about whether the underlying method is a neural network or a mathematical decomposition.

---

## 📤 Submission

1. Save your answers in a file named `w1d1-concepts.md`
2. Add it to your repository at `modules/1-foundations/codes/w1d1/w1d1-concepts.md`
3. Submit the GitHub link via the class submission form

---