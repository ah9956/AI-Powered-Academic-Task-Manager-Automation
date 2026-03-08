# 🎓 AI-Powered Academic Task Manager

An **automation system for students** that converts complex assignment PDFs into **structured, summarized tasks with realistic time estimates**.

The system connects **Google Classroom with task planning** by automatically transforming large assignment documents into **actionable study tasks stored in Google Sheets**.

---

# 🚀 Key Features

### 🔄 Automated Assignment Sync

Assignments are automatically pulled from **Google Classroom** using OAuth2 authentication.

### 🧠 Local AI Processing

Uses a **self-hosted Llama 3.2:1b model via Ollama** to summarize assignment PDFs locally.
This ensures **100% data privacy** since no external APIs are used.

### ⏱ Smart Time Estimation

Predicts **realistic completion time** for assignments based on **undergraduate-level complexity**, rather than professional benchmarks.

### 📊 Structured Data Export

Transforms raw AI output into **clean structured rows in Google Sheets** for easy task tracking and planning.

---

# 🛠 Tech Stack

| Component         | Technology                             |
| ----------------- | -------------------------------------- |
| Automation Engine | n8n (Self-hosted via Docker on Ubuntu) |
| AI Model          | Llama 3.2:1b (via Ollama)              |
| Data Processing   | JavaScript (n8n expressions)           |
| Parsing Layer     | Regex-based text processing            |
| Data Storage      | Google Sheets                          |

---

# 🧠 System Architecture

The automation is optimized for **mid-range hardware**:

* **8GB RAM**
* **Intel i5 Processor**
* **CPU-only AI inference**

---

## Sequential Processing Chain

To prevent memory overload when processing large PDFs, the workflow uses a **Daisy-Chain Architecture**:

### Node A – Assignment Summarization

Performs **high-compression summarization** of long assignment PDFs to extract key tasks and instructions.

### Node B – Time Estimation

Analyzes the summarized content separately to estimate **realistic effort and completion time**.

### Data Processing Layer

Uses **regex-based parsing** to convert unstructured AI output into **clean structured spreadsheet columns**.

---

# ⚙️ Installation (Backend Setup)

### 1. Install Docker

Install Docker on an **Ubuntu server or VPS**.

### 2. Deploy n8n

Run **n8n using Docker containers**.

### 3. Install the Local AI Model

```bash
ollama run llama3.2:1b
```

### 4. Import the Workflow

Import the provided **n8n workflow JSON file** into your n8n instance.

### 5. Configure Google APIs

Create credentials in **Google Cloud Console** for:

* Google Classroom API
* Google Drive API

Add the OAuth credentials to **n8n**.

---

# 📦 Automation Workflow

1. Retrieve assignments from **Google Classroom**
2. Download assignment **PDF files**
3. Process the PDF using the **Llama 3.2 model**
4. Extract key tasks and summaries
5. Estimate completion time
6. Parse and structure the AI output
7. Store the final results in **Google Sheets**

---

# 👥 Contributors

**Abdul Hannan**

---

# 📜 License

This project is licensed under the **MIT License**.
