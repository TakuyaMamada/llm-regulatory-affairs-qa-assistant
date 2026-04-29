# Regulatory Affairs RAG AI Assistant
A Retrieval-Augmented Generation (RAG)-based AI assistant designed to answer user questions related to pharmaceutical and medical device regulatory affairs in the United States, the European Union, and Japan.

## Overview
This AI assistant answers user questions by retrieving and referencing information from the following regulatory sources:

1. **Pharmaceuticals and Medical Devices Act (Japan)**  
https://laws.e-gov.go.jp/api/1/lawdata/335AC0000000145

2. **EudraLex (European Union)**  
https://health.ec.europa.eu/medicinal-products/eudralex_en

3. **21 CFR Subchapter D — Drugs for Human Use (United States)**  
https://www.govinfo.gov/content/pkg/CFR-2025-title21-vol5/xml/CFR-2025-title21-vol5-chapI-subchapD.xml

The assistant maintains chat history to support multi-turn interactions and is explicitly instructed to respond with *“I don’t know”* when sufficient supporting information cannot be found in the retrieved documents, helping reduce hallucinations.

## Motivation

This project was developed to support professionals working in Regulatory Affairs.

During my experience as an IT project manager in both medical device and pharmaceutical companies, I observed that Regulatory Affairs teams work under highly complex and demanding regulatory requirements. I also recognized that non-compliance can result in significant consequences, affecting both business continuity and patient safety.

Based on this experience, I believed an AI assistant for this domain could be valuable in supporting professionals navigating regulatory information.

## Features

- Chat interface with conversation memory  
- Retrieval-Augmented Generation (RAG) for document-grounded answers  
- Hallucination mitigation through “I don't know” fallback responses  
- Answers based on official regulatory documents from competent authorities  
- Source-grounded responses with retrieved context  
- Simple natural-language responses and structured JSON-formatted outputs  
- Streaming output for real-time responses  
- Follow-up question suggestions
- Multi-query retrieval and contextual compression for improved retrieval quality

## Tech Stack

- Python
- LangChain
- OpenAI API  
- ChromaDB
- beautifulsoup
- Jupyter Notebook

## Installation

1. Install dependencies:

```bash
pip install -r requirements.txt
```

(or use `uv` if preferred)

2. Configure required API keys and environment variables.

3. Run the notebook:

```bash
jupyter notebook
```

## Usage

Open the notebook and provide user questions as a Python list in the input cell.

Example:

```python
questions = [
    "Hello, I am Hippocrates of Kos from ancient Greece.",
    "Do you recall my name and location?",
    "Please summarize the structure of the Pharmaceuticals and Medical Devices Act (Japan), EudraLex (EU), and 21 CFR Subchapter D — Drugs for Human Use (United States), respectively.",
    "Based on the summary you created earlier, what are the key structural differences among these three regulations?"
]
```

The assistant processes the questions sequentially while retaining chat history across interactions.

## Disclaimer

This project was created for learning and research purposes.

It is intended for informational use only and does not constitute legal, regulatory, or professional advice. Users should always consult official regulatory sources and qualified professionals before making compliance-related decisions.
