# 🩺 Diagnostic Workflow Explainer

An LLM-powered RAG chatbot that helps medical students explore diagnostic workflows using LangChain, FAISS, Groq API, and Streamlit.

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![LangChain](https://img.shields.io/badge/LangChain-RAG-green.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-App-red.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## ✨ Features

- **Medical Queries** — Ask questions about diagnostic workflows, symptoms, and conditions
- **RAG Pipeline** — Retrieval-Augmented Generation grounds responses in clinical evidence
- **Chat History** — Maintains context across multiple questions
- **Source Transparency** — View retrieved documents that inform each response

## 📊 Knowledge Base
- **24 Diagnostic Workflows** — Covering conditions from Heart Failure to Diabetes to Stroke
- **511 Clinical Notes** — Real annotated cases from MIMIC-IV

## 🛠️ Tech Stack

| Component | Technology |
|-----------|------------|
| **LLM** | Llama 3.3 70B (via Groq API) |
| **Embeddings** | HuggingFace BGE-small-en-v1.5 |
| **Vector Store** | FAISS |
| **Framework** | LangChain |
| **Frontend** | Streamlit |
| **Dataset** | MIMIC-IV-Ext-DiReCT |

## 📦 Installation

### 1. Clone the repository

```bash
git clone https://github.com/ReddyKhajaValluru/diagnostic-workflow-explainer.git
cd diagnostic-workflow-explainer
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set up environment variables

Create a `.env` file in the project root:

```bash
GROQ_API_KEY=your_groq_api_key_here
```

Get your free API key from [Groq Console](https://console.groq.com/).

## 📥 Data Setup

> ⚠️ **Important:** The dataset cannot be redistributed. You must obtain it directly from PhysioNet.

### Steps to get the data:

1. **Create a PhysioNet account** at [physionet.org](https://physionet.org/)

2. **Request access** to [MIMIC-IV-Ext-DiReCT](https://physionet.org/content/mimic-iv-ext-direct/)

3. **Download the dataset files:**
   - `samples.rar` — Clinical notes (511 annotated cases)
   - `diagnostic_kg.rar` — Diagnostic knowledge graphs (24 workflows)

4. **Extract into the `data/` folder:**

```
data/
├── samples/
│   └── Finished/
│       ├── Acute Coronary Syndrome/
│       ├── Diabetes/
│       ├── Heart Failure/
│       └── ... (other conditions)
├── diagnostic_kg/
│   └── Diagnosis_flowchart/
│       ├── Acute Coronary Syndrome.json
│       ├── Diabetes.json
│       └── ... (other workflows)
├── LICENSE.txt
└── README.md
```

## 🚀 Usage

### Run the Streamlit app

```bash
streamlit run TutorBot_app.py
```

The app will open in your browser at `http://localhost:8501`.

### Example queries

- "What are the symptoms of diabetes?"
- "How is heart failure diagnosed?"
- "What distinguishes STEMI from NSTEMI?"
- "Explain the diagnostic criteria for hypertension"

## 📁 Project Structure

```
├── TutorBot_app.py      # Main Streamlit application
├── requirements.txt     # Python dependencies
├── .env                 # Environment variables (create this)
├── data/                # Dataset folder (not included - see Data Setup)
│   ├── samples/         # Clinical notes
│   └── diagnostic_kg/   # Diagnostic workflows
└── README.md            # Project overview, setup, and usage instructions            

```

## 📚 Citations

If you use this project or the underlying dataset, please cite:

### MIMIC-IV-Ext-DiReCT Dataset

> Wang, B., Chang, J., & Qian, Y. (2025). MIMIC-IV-Ext-DiReCT (version 1.0.0). PhysioNet. https://doi.org/10.13026/yf96-kc87

### MIMIC-IV

> Johnson, A., Bulgarelli, L., Pollard, T., Gow, B., Moody, B., Horng, S., Celi, L. A., & Mark, R. (2024). MIMIC-IV (version 3.1). PhysioNet. https://doi.org/10.13026/kpb9-mt58

## ⚖️ License & Data Usage

- **Code:** This project's code is available under the MIT License.
- **Data:** The MIMIC-IV-Ext-DiReCT dataset is governed by the [PhysioNet Restricted Health Data License 1.5.0](https://physionet.org/content/mimic-iv-ext-direct/).

### Data usage restrictions:

- ✅ Research and educational use only
- ❌ No commercial use
- ❌ No redistribution of the data
- ❌ No attempting to re-identify patients
- ✅ Must open-source code from any publications

## ⚠️ Disclaimer

This application is for **educational purposes only**. It is not intended for clinical use or medical diagnosis. Always consult qualified healthcare professionals for medical advice.

