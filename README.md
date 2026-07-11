# AI/ML Engineering Advanced Internship Tasks - DevelopersHub Corporation

This repository contains completed tasks from the Advanced Internship Task Set for the AI/ML Engineering Internship at DevelopersHub Corporation. The internship required completing at least 3 out of 5 advanced tasks covering transformer models, ML pipelines, multimodal learning, conversational AI, and LLM applications.

**Status: 3 of 5 tasks completed** (Task 2, Task 3, Task 5)

## Tasks Completed

### Task 2: End-to-End ML Pipeline with Scikit-learn Pipeline API
Folder: [`task2-churn-prediction-pipeline/`](./task2-churn-prediction-pipeline)

A reusable, production-ready machine learning pipeline for predicting customer churn on the Telco Churn Dataset. Built using scikit-learn's `Pipeline` API with preprocessing (scaling, encoding), Logistic Regression and Random Forest models, hyperparameter tuning via `GridSearchCV`, and the final pipeline exported with `joblib` for reuse.

See the folder's own README for full methodology and results.

### Task 3: Multimodal ML - Housing Price Prediction Using Images + Tabular Data
Folder: [`task3-multimodal-housing-price-prediction/`](./task3-multimodal-housing-price-prediction)

A multimodal regression model predicting housing prices from both structured data (bedrooms, bathrooms, area, zip code) and house images. A custom CNN extracts visual features from tiled room photos, fused with an MLP branch processing tabular features, evaluated with MAE and RMSE, and benchmarked against a tabular-only Random Forest baseline.

See the folder's own README for full methodology and results.

### Task 5: Auto-Tagging Support Tickets Using LLM
Folder: [`task5-auto-tagging-support-tickets/`](./task5-auto-tagging-support-tickets)

An LLM-based multi-label tagging system for free-text customer support tickets. Compares zero-shot classification (BART-MNLI), few-shot prompting (FLAN-T5), and a fine-tuned DistilBERT multi-label classifier, outputting the top 3 most probable tags per ticket.

See the folder's own README for full methodology and results.

## Tasks Not Attempted
- Task 1: News Topic Classifier Using BERT
- Task 4: Context-Aware Chatbot Using LangChain or RAG

## Repository Structure
```
.
├── task2-churn-prediction-pipeline/
│   ├── (notebook, files, README.md)
├── task3-multimodal-housing-price-prediction/
│   ├── task3-multimodal-housing-price-prediction.ipynb
│   └── README.md
├── Task-5-Support-Ticket-Auto-Tagging-Using-LLM/
│   ├── task5-auto-tagging-support-tickets-llm.ipynb
│   ├── ticket_tag_predictions.csv
│   └── README.md
├── .gitignore
└── README.md
```

## Technologies Used
Hugging Face Transformers, scikit-learn, TensorFlow/Keras, joblib, CNNs, LLMs (BART-MNLI, FLAN-T5, DistilBERT), Kaggle Notebooks

## Notes
Each task folder contains its own README with the specific objective, methodology, and results for that task, in line with the internship submission requirements. This top-level README serves as an index across all completed work.