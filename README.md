# Foundations-of-Artificial-Intelligence

Foundations of Artificial Intelligence Project CS23533



\# MEDIXAI: Explainable AI-Based Medical Expert System Prototype



\*\*Course:\*\* CS23533 – Foundations of Artificial Intelligence  

\*\*Core Concept:\*\* Unit IV – Knowledge-Based Reasoning  

\*\*Stack:\*\* Pure Client-Side JavaScript / HTML5 / CSS3  



\---



\## 📌 Project Overview

\*\*MEDIXAI\*\* is an educational, explainable classical AI playground that ports symbolic rule evaluation directly into the browser. Unlike black-box machine learning models, this system is \*\*explainable by construction\*\*—allowing users to see every step, fired rule, and missing premise behind a condition match.



All computations happen locally within the user's browser tab; no data is sent to a server or saved externally.



\*Note: This is a toy academic prototype built for learning knowledge representation. It is completely unvalidated and does not replace professional clinical diagnosis or triage.\*



\## ⚙️ How It Works (Inference Engine)



\### 1. Facts \& Rules Structure

\* \*\*Knowledge Base:\*\* Contains \*\*38 disease rules\*\* and \*\*104 symptom facts\*\* split across 8 distinct categories.

\* \*\*Premises:\*\* Each disease profile contains weighted symptom facts and strict required premises.



\### 2. Forward Rule Evaluation

\* Executes a single pass across every disease rule once facts are submitted.

\* Requires \*\*all\*\* mandatory premises to be selected before a rule's implication fires.

\* \*\*Heuristic Scoring:\*\* Calculates an overlap score based on matched weights. If a required fact is missing, a penalty multiplier is applied:

&#x20; \\\[\\text{Score} = 100 \\times \\frac{\\text{Matched Weight}}{\\text{Total Weight}} \\times 0.60 \\text{ (if required fact missing)}\\]



\### 3. Backward Premise Checks

\* Users can select a specific hypothesis (disease) to inspect its missing required facts.

\* Answering unknown premises interactively updates the inference engine to dynamically re-evaluate the target rule.



\### 4. Input Consistency Checks

\* Implements direct, explicit input consistency filtering rather than a heavy CNF resolution prover.

\* Automatically flags and blocks evaluation on absolute logical contradiction pairs (e.g., \*Fever vs. No Fever\*, \*High Fever vs. No Fever\*, and \*Diarrhea vs. Constipation\*).



\---



\## 📂 Repository Structure



```text

├── index.html          # Main application UI dashboard \& workspace

├── css/

│   └── styles.css      # Interface layout and styling

├── js/

│   ├── main.js         # Core application driver and state management

│   ├── knowledgebase.js# The 38-disease rule dictionary \& symptom mapping

│   └── engine.js       # Forward chaining evaluation \& consistency checks

└── README.md

```



\---



\## 🚀 Getting Started



Because this prototype has \*\*no backend server, databases, or external framework dependencies\*\*, running it is instant:



1\. Clone the repository:

&#x20;  ```bash

&#x20;  git clone https://github.com

&#x20;  cd MEDIXAI

&#x20;  ```

2\. Open `index.html` directly in any modern web browser (Chrome, Firefox, Safari, Edge).



