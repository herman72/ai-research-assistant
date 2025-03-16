# 📚 AI-Powered Research Assistant

## 🔍 Overview
The **AI-Powered Research Assistant** is a web-based tool that helps users **search, summarize, and analyze** research papers. It integrates with sources like **arXiv, PubMed, and Semantic Scholar**, uses **GPT-4 for summarization**, and supports **semantic search with FAISS** for finding similar research papers. Users can also **upload PDFs** to extract **figures and tables**.

## 🚀 Features
- **🔎 Fetch Research Papers** from **arXiv, PubMed, and Semantic Scholar**.
- **🧠 AI-Powered Summarization** using **GPT-4**.
- **🔬 Extract Figures & Tables** from uploaded PDFs.
- **📖 Semantic Search** using **FAISS & OpenAI Embeddings**.
- **🖥️ Web UI** for easy interaction via **React & FastAPI**.

---

## 🛠️ Tech Stack
### Backend:
- **FastAPI** - Handles API requests.
- **PostgreSQL** - Stores research papers and summaries.
- **FAISS** - Enables vector-based semantic search.
- **OpenAI GPT-4** - Provides research paper summaries.
- **PyMuPDF** - Extracts figures and tables from PDFs.

### Frontend:
- **React (Vite)** - Provides an intuitive web UI.
- **Axios** - Handles API requests.
- **Tailwind CSS** - Provides clean UI styling.

---

## 🏗️ Installation & Setup
### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/research-assistant.git
cd research-assistant
```

### 2️⃣ Backend Setup (FastAPI & PostgreSQL)
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Create a **.env** file with your API keys:
```env
OPENAI_API_KEY=your-openai-api-key
DB_CONNECTION=postgresql://user:password@localhost:5432/research_assistant
```

Run the backend:
```bash
uvicorn main:app --host 0.0.0.0 --port 8000 --reload
```

### 3️⃣ Frontend Setup (React)
```bash
cd frontend
npm install
npm run dev
```

Your frontend should now be running at **http://localhost:5173** 🚀

---

## 🎯 Usage
### 🔍 Search & Fetch Papers
1. Enter a research topic.
2. Choose a source (**arXiv, PubMed, Semantic Scholar**).
3. Click **Fetch Paper** to retrieve relevant results.

### 🧠 Summarize Research Papers
1. Click **Summarize** after fetching a paper.
2. GPT-4 will generate a short summary.

### 🔬 Extract Figures & Tables
1. Upload a **PDF** of a research paper.
2. Click **Extract Figures & Tables** to analyze its contents.

### 📖 Semantic Search (Find Similar Papers)
1. Enter a research topic and click **Search Similar Papers**.
2. The system finds **similar papers** using **FAISS embeddings**.

---

## 📡 API Documentation
The backend provides RESTful API endpoints for fetching papers, summarizing them, performing semantic searches, and extracting figures/tables.

### **1️⃣ Fetch Research Papers**
**Endpoint:** `GET /fetch_paper`

**Request:**
```bash
curl -X GET "http://localhost:8000/fetch_paper?query=machine learning&source=arxiv"
```

**Response:**
```json
{
  "title": "Deep Learning for AI",
  "authors": ["John Doe"],
  "abstract": "This paper discusses deep learning applications..."
}
```

### **2️⃣ Summarize a Research Paper**
**Endpoint:** `POST /summarize_paper`

**Request:**
```bash
curl -X POST "http://localhost:8000/summarize_paper" -H "Content-Type: application/json" -d '{"content": "Deep learning is a subset of AI..."}'
```

**Response:**
```json
{
  "summary": "Deep learning is a key AI technique that..."
}
```

### **3️⃣ Search for Similar Papers (Semantic Search)**
**Endpoint:** `GET /search_paper`

**Request:**
```bash
curl -X GET "http://localhost:8000/search_paper?query=deep learning applications"
```

**Response:**
```json
{
  "matched_papers": ["paper_1", "paper_2", "paper_3"]
}
```

### **4️⃣ Extract Figures & Tables from a PDF**
**Endpoint:** `POST /extract_figures_tables`

**Request:**
```bash
curl -X POST "http://localhost:8000/extract_figures_tables" -F "pdf_file=@sample.pdf"
```

**Response:**
```json
{
  "extracted": {
    "tables": 3,
    "figures": 5
  }
}
```

---

## 📜 License
This project is licensed under the **Apache 2.0 License**.

---

## 🤝 Contributing
Feel free to submit **issues, feature requests, or pull requests**! 🙌

1. Fork the repo.
2. Create a new branch: `git checkout -b feature-branch`
3. Commit changes: `git commit -m 'Added new feature'`
4. Push to GitHub: `git push origin feature-branch`
5. Submit a Pull Request 🎉

---

## 📩 Contact
For questions or feedback, reach out via GitHub Issues or email **m.sherafati7@gmail.com**. 🚀

