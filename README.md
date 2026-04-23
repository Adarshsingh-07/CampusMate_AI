# 📘 CampusMate – AI-Powered RAG System

CampusMate is an **AI assistant** that helps students interact with study materials (notes, textbooks, manuals) more effectively.  
It applies **Retrieval-Augmented Generation (RAG)** to let users upload PDFs and query them directly, avoiding the hassle of manually searching through 100+ pages.

---

## 🚀 Features
- 📂 **Upload PDFs** (up to 200 MB) – notes, textbooks, or manuals  
- ✂️ **Text parsing & semantic chunking** for efficient retrieval  
- 🔍 **Vector embeddings** with **Google/BGE**  
- ⚡ **Semantic search** using **Pinecone**  
- 🤖 **Groq’s LLaMA3-70B** (via LangChain) for fast, grounded responses  
- 🌐 **Full-stack deployment** – Streamlit (frontend) + FastAPI (backend) on Render  

---

## 📂 Project Structure

    User Input
    ↓
    Query Embedding → Pinecone Vector DB ← Embedded Chunks ← Chunking ← PDF Loader
    ↓
    Retrieved Docs
    ↓
        RAG Chain (Groq + LangChain)
    ↓
    LLM-generated Answer

## 🛠️ Tech Stack

| Component   | Tech Used                          |
|-------------|------------------------------------|
| **LLM**     | Groq API (LLaMA3-70B)             |
| **Embeddings** | Google Generative AI / BGE      |
| **Vector DB**  | Pinecone                        |
| **Framework**  | LangChain                       |
| **Backend**    | FastAPI                         |
| **Frontend**   | Streamlit                       |
| **Deployment** | Render                          |

---
## 📚 Api Endpoints

    POST /upload_pdfs/ --- Upload one or more PDF files

    POST /ask/ --- Ask a question --- Form field: `question`


## 📁 Folder Structure

    └── 📁client
    └── 📁__pycache__
        ├── config.cpython-311.pyc
    └── 📁components
        └── 📁__pycache__
            ├── chatUI.cpython-311.pyc
            ├── history_download.cpython-311.pyc
            ├── upload.cpython-311.pyc
        ├── chatUI.py
        ├── history_download.py
        ├── upload.py
    └── 📁utils
        └── 📁__pycache__
            ├── api.cpython-311.pyc
        ├── api.py
    ├── app.py
    ├── config.py
    └── requirements.txt

####

    └── 📁server
    └── 📁__pycache__
        ├── logger.cpython-311.pyc
        ├── main.cpython-311.pyc
        ├── test.cpython-311.pyc
    └── 📁middlewares
        └── 📁__pycache__
            ├── exception_handlers.cpython-311.pyc
        ├── exception_handlers.py
    └── 📁modules
        └── 📁__pycache__
            ├── llm.cpython-311.pyc
            ├── load_vectorstore.cpython-311.pyc
            ├── query_handlers.cpython-311.pyc
        ├── llm.py
        ├── load_vectorstore.py
        ├── pdf_handlers.py
        ├── query_handlers.py
    └── 📁routes
        └── 📁__pycache__
            ├── ask_question.cpython-311.pyc
            ├── upload_pdfs.cpython-311.pyc
        ├── ask_question.py
        ├── upload_pdfs.py
    └── 📁uploaded_docs
        ├── resume.pdf
    ├── .env
    ├── logger.py
    ├── main.py
    ├── requirements.txt
    └── test.py

---

## ⚙️ Installation & Setup

### . Clone the Repository
    ```bash
    git clone https://github.com/Adarshsingh-07/CampusMate.git
    cd CampusMate

## Create Virtual Environment & Install Dependencies

    python -m venv venv

    source venv/bin/activate   # for Linux/Mac
    venv\Scripts\activate      # for Windows
    pip install -r requirements.txt

## Setup Environment Variables

### Create a .env file inside the root folder with:
    GROQ_API_KEY=your_groq_api_key
    PINECONE_API_KEY=your_pinecone_api_key
    GOOGLE_API_KEY=your_google_api_key

## Run Backend (FastAPI)

    cd backend
    uvicorn main:app --reload

## Run Frontend (Streamlit)

    cd frontend
    streamlit run app.py

## 📸 Demo

🔗 Live Project: https://campusmate.streamlit.app/

    Upload your study PDFs → Ask questions → Get instant answers 🎓⚡


## 🤝Contribution

    Contributions are welcome!
    Fork the repo
    Create a feature branch
    Submit a PR 🚀

## 📜 License

  This project is licensed under the MIT License.

## 👨‍💻 Author

Adarsh Kumar
