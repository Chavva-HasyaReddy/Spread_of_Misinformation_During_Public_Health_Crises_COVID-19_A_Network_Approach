# 📚 Spread of Misinformation During Public Health Crises COVID-19 : A Network Approach

COVID-19 Misinformation Detection System is an AI-powered verification framework designed to detect misleading or false health claims using **semantic similarity, network-based risk analysis, and explainable AI techniques**.

The system can analyze **text**, **URLs**, and **image-based claims**, and classify them as:

- ✅ **CORRECT**
- ❌ **MISINFORMATION**
- ⚠️ **UNVERIFIED**

The system compares user claims with verified information from trusted health organizations such as **WHO, CDC, and NHS**, enabling reliable misinformation detection during public health crises.

Unlike many fact-checking tools that rely on cloud APIs, this system focuses on **offline operation, privacy preservation, and explainable decision-making** using a **locally curated knowledge base and local AI models**.

---

## 🔧 How It Works

### 🔹 Text Claim Verification
- Users enter a COVID-19 related claim in the interface.
- The system preprocesses the text (cleaning, normalization, translation if required).
- Sentence-BERT converts the claim into a semantic embedding.
- Cosine similarity compares the claim against verified facts and misinformation patterns.
- The decision engine classifies the claim and provides supporting evidence.

### 🔹 URL Claim Verification
- Users submit a webpage URL containing a claim.
- The system extracts textual content from the webpage.
- Extracted text is processed through the same semantic verification pipeline used for text inputs.

### 🔹 Image Claim Verification
- Users upload an image containing text (such as screenshots of posts or messages).
- **EasyOCR** extracts text from the image.
- Extracted text is analyzed through the same misinformation detection pipeline.

### 🔹 Network Risk Analysis
- Similar claims are grouped using **MinHash and Locality Sensitive Hashing (LSH)**.
- The system identifies neighboring claims that were previously labeled as misinformation.
- A **network risk score** adjusts the classification confidence.

### 🔹 Explainable AI Verification
- The system optionally uses a **local LLM via Ollama** to generate explanations.
- The LLM explains the classification result but **does not override rule-based decision logic**.

---

## 🗂️ Project Structure

```
misinformation-detection-system/
│
├── app.py                      # Main Streamlit application
├── classifier.py               # Semantic similarity computation pipeline
├── decision_engine.py          # Final classification logic
├── preprocessing.py            # Text cleaning and normalization
├── knowledge_base.py           # Loading verified facts and misinformation patterns
├── intent_detector.py          # Medical claim intent detection
├── entity_validator.py         # Entity validation using spaCy
├── network_analysis.py         # Claim similarity network (MinHash + LSH)
├── llm_verifier.py             # Local LLM explanation module
├── input_handler.py            # Handles text, URL, and image inputs
│
├── evaluation.py               # Experimental evaluation framework
├── fact_gatherer.py            # Fact collection from trusted sources
├── knowledge_ingestion.py      # Knowledge base expansion
├── tester_feedback.py          # Tester feedback logging
├── config.py                   # System configuration settings
│
├── requirements.txt            # Python dependencies
├── README.md                   # Project overview
│
├── data/
│   ├── verified_facts.json
│   ├── known_misinformation.json
│   ├── wikidata_entities.json
│   ├── staged_claims.json
│   ├── test_cases.json
│   └── feedback_log.json
│
├── cache/
│   ├── embeddings_cache.pkl
│   ├── verified_embeddings.pkl
│   ├── misinformation_embeddings.pkl
│   └── wikidata_cache.pkl
│
├── network_storage/
│   ├── lsh_index.pkl
│   ├── minhash_signatures.pkl
│   └── claim_graph.pkl
│
├── logs/
│   ├── system_logs.txt
│   ├── evaluation_results.json
│   └── error_logs.txt
│
└── static/
    ├── uploaded_images/
    └── temporary_files/
```

---

## 💻 Tech Stack

| Component | Technology |
|-----------|------------|
| Backend | Python |
| Web Interface | Streamlit |
| Semantic Embeddings | Sentence-BERT (all-MiniLM-L6-v2) |
| Local LLM | Ollama (Gemma 2B) |
| OCR | EasyOCR |
| NLP | spaCy |
| Language Detection | langdetect |
| Translation | deep-translator |
| Similarity Network | MinHash + LSH (datasketch) |
| Data Storage | JSON |

---

## 🚀 Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/yourusername/covid-misinformation-detection.git
cd covid-misinformation-detection
```

### 2. Install Python dependencies
```bash
pip install -r requirements.txt
```

### 3. Install spaCy language model
```bash
python -m spacy download en_core_web_sm
```

### 4. Install Ollama and load the LLM
Download Ollama:

```
https://ollama.ai/download
```

Pull the required model:

```bash
ollama pull gemma2:2b
```

### 5. Run the application
```bash
streamlit run app.py
```

Visit the application in your browser:

```
http://localhost:8501
```

---

## 🧪 Features Summary

- ✅ Multi-modal claim verification (Text, URL, Image)
- ✅ Semantic similarity based misinformation detection
- ✅ Network-based misinformation pattern detection
- ✅ Intent-aware validation of medical claims
- ✅ Entity validation using structured health data
- ✅ Explainable classification with evidence
- ✅ Offline and privacy-preserving architecture

---

## 🧠 Example Use Cases

- Verify claims like **“Garlic cures COVID-19”**
- Analyze misinformation from **social media posts or articles**
- Upload **screenshots of viral health messages** for verification
- Detect **repeated misinformation patterns** using similarity networks

---

## 🔗 GitHub Repository

Project Source Code:  
https://github.com/Chavva-HasyaReddy/Spread_of_Misinformation_During_Public_Health_Crises_COVID-19_A_Network_Approach

---

## 📄 Project Report

Project Title:  
**Spread of Misinformation During Public Health Crises COVID-19 : A Network Approach**

---

## 🤝 Contributors

- **Chavva Hasya Reddy**
- **Rahman Nayeem Abrar**
- **Gurramkonda Sharun Prakash**
- **Chaitanya Bala**
- **Jangamreddy Bhavitha Reddy**

---

## 📄 License

This project is developed for **academic and research purposes** as part of a **B.Tech Capstone Project**.
