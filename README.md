# ⚖️ Samvidhan AI — Indian Constitution Assistant

A RAG (Retrieval-Augmented Generation) based chatbot that answers questions about the Indian Constitution using actual constitutional text.

---

## 🚀 Tech Stack

- **LangChain** — RAG pipeline
- **Qdrant** — Vector database for storing chunks
- **HuggingFace Embeddings** — `sentence-transformers/all-MiniLM-L6-v2`
-  (LLaMA 3.1)** — LLM for generating answers(any llama model for localy run on system)
- **FastAPI** — Backend API server
- **HTML/CSS/JS** — Static frontend
- ****Docker** - Running Qdrant

---

## 📁 Project Structure

```
├── index.html          # Frontend UI
├── server.py           # FastAPI backend
├── build_vector_db.py  # Script to build Qdrant vector DB
├── llm.py              # RAG chain (testing)
├── requirements.txt    # Python dependencies
└── .env                # API keys (not pushed to Git)
```

---

## ⚙️ Setup & Installation

### 1. Clone the repo
```bash
git clone https://github.com/Tarutiwari/bajaj_solve.git
cd bajaj_solve
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
```

### 3. Setup `.env` file
Create a `.env` file in the root directory:
```
define you model and if using any key for the incase using pine database and api key og nay chatbot model

### 4. Start Qdrant (Docker)
```bash
docker pull qdrant/qdrant
docker run -p 6333:6333 qdrant/qdrant
```

### 5. Build Vector Database
Add your Constitution PDF files in a `constitution/` folder, then run:
```bash
python build_vector_db.py
```

### 6. Start Backend Server
```bash
uvicorn server:app --reload
```

### 7. Open Frontend
Open `index.html` in your browser — done! 🎉

---

## 💡 How It Works

Constitution PDF
       ↓
Split into chunks
       ↓
Create embeddings
       ↓
Store in Qdrant
       ↓
User asks a question
       ↓
Search for relevant chunks
       ↓
Send retrieved context to LLM
       ↓
Generate the answer


---

## 🔑 Environment Variables

| Variable | Description |
|----------|-------------|
| `API_KEY` |  API Key |

---

## 📌 Notes

- Constitution PDFs are  included in this repo due to size
- Make sure Qdrant is running before starting the server
