# Named Entity Recognition using Large Language Models

## Overview
This project implements a **Named Entity Recognition (NER)** system using a **Large Language Model (LLM)** to extract structured information from unstructured real-estate chat conversations.

The goal is to extract entities such as:
- First Name
- Last Name
- Phone Number
- Email
- Budget
- Current Location
- Preferred Location  

The extracted entities are evaluated against gold labels using standard NLP metrics.

---

## Project Structure

```text
ner_assignment/
├── data/
│   ├── chats.json
│   └── gold_labels.json
│
├── prompts/
│   ├── prompt_v1.txt
│   └── prompt_v2.txt
│
├── outputs/
│   └── model_outputs/
│       ├── predictions.json
│       ├── evaluation.json
│       ├── errors.json
│       └── error_summary.json
│
├── main.ipynb
├── requirements.txt
├── .gitignore
└── README.md
```



---

## Dataset Description
- **chats.json**  
  Contains unstructured chat conversations between users and a real-estate assistant.

- **gold_labels.json**  
  Contains ground-truth entity annotations used for evaluation.

---

## Methodology
1. Load chat conversations from `chats.json`
2. Construct a structured prompt to guide the LLM
3. Call the LLM (Groq – LLaMA-3) for entity extraction
4. Parse and validate JSON output
5. Save predictions
6. Compare predictions with gold labels
7. Compute evaluation metrics
8. Perform error analysis

---

## Model Details
- **Model Provider:** Groq
- **Model Used:** LLaMA-3
- **Temperature:** 0 (for deterministic output)
- **Output Format:** Strict JSON

Environment variables are used to securely load API keys.

---

## Evaluation Metrics
The following metrics are computed:
- **Accuracy**
- **Precision**
- **Recall**
- **F1-Score**

These metrics are saved in:

---

## Error Analysis
An error analysis is performed to identify:
- Missing entities
- Incorrect predictions
- Model limitations due to ambiguous or incomplete input

Detailed error logs are available in:

---

## Results Summary
- The model demonstrates strong precision but lower recall in some cases.
- Missed entities are primarily due to ambiguous phrasing or missing information in the chat.
- Strict JSON enforcement reduces hallucinations but can increase null predictions.

---

## How to Run
1. Create and activate a virtual environment
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
