# NLP-QUERY-ENGINE
# 🧠 NLP Query Engine

An AI-powered **NLP Query Engine** that bridges natural language queries with database and document insights. Built using **FastAPI**, **React**, and **Sentence Transformers**, it allows users to connect databases, ingest documents, and ask questions in plain English — retrieving structured results and contextual information.

---

## 🚀 Features

### 🔍 Schema-Aware Querying

* Automatically discovers database schema (tables, columns, relationships).
* Infers table purpose using heuristics (e.g., `employee`, `department`, etc.).
* Maps natural language queries to relevant SQL statements.

### 📄 Document Understanding

* Upload documents (TXT, DOCX, PDF) and process them in the background.
* Dynamic chunking and embedding generation using `sentence-transformers`.
* Semantic retrieval for hybrid database + document search.

### ⚡ Fast & Modular

* **FastAPI** backend with async I/O for efficiency.
* **React** frontend with intuitive query, upload, and results interfaces.
* Docker-ready setup for one-command deployment.

---

## 🏗️ Tech Stack

| Layer                        | Technology                                 |
| ---------------------------- | ------------------------------------------ |
| **Frontend**                 | React (Bootstrap, Axios)                   |
| **Backend**                  | FastAPI, SQLAlchemy, Pydantic              |
| **Embeddings**               | Sentence Transformers (`all-MiniLM-L6-v2`) |
| **Database**                 | PostgreSQL                                 |
| **Vector Search (optional)** | FAISS or in-memory similarity              |
| **Containerization**         | Docker, Docker Compose                     |

---

## 🧩 Project Structure

```
project/
├── backend/
│   ├── api/routes/                # FastAPI endpoints
│   ├── services/                  # Core business logic
│   ├── main.py                    # App entry point
│   ├── requirements.txt           # Backend dependencies
│   └── tests/                     # Optional unit tests
│
├── frontend/
│   ├── src/components/            # React components
│   ├── src/api.js                 # Axios setup
│   ├── src/styles.css             # UI styling
│   └── package.json               # Frontend dependencies
│
├── docker-compose.yml             # Combined setup for app + DB
└── README.md                      # You are here
```

---

## ⚙️ Setup & Installation

### 1️⃣ Clone the repository

```bash
git clone https://github.com/<your-username>/nlp-query-engine.git
cd nlp-query-engine
```

### 2️⃣ Backend setup

```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt

# Run the API server
uvicorn main:app --reload
```

The backend runs at [http://localhost:8000](http://localhost:8000)

### 3️⃣ Frontend setup

```bash
cd frontend
npm install
npm start
```

The frontend runs at [http://localhost:3000](http://localhost:3000)

### 4️⃣ Docker (optional, one-command deployment)

```bash
docker-compose up --build
```

---

## 🧠 Usage

### 🔗 Connect a Database

1. Enter a valid Postgres connection string.
2. The engine introspects your database tables, columns, and keys.

### 📂 Upload Documents

1. Upload `.txt`, `.pdf`, or `.docx` files.
2. Documents are chunked and embedded for semantic search.

### 💬 Query in Natural Language

Type questions like:

```text
List all employees with Python skills.
Show average salary per department.
Find resumes mentioning data analysis.
```

The engine will automatically generate SQL or search documents accordingly.

---

## 🧪 Example Queries

| Natural Query                       | Generated SQL                                            |
| ----------------------------------- | -------------------------------------------------------- |
| "How many employees are there?"     | `SELECT COUNT(*) FROM employees;`                        |
| "Show employees skilled in Python." | `SELECT * FROM employees WHERE skills ILIKE '%python%';` |
| "List all departments."             | `SELECT * FROM departments;`                             |

---

## 📈 Future Improvements

* ✅ Integrate FAISS vector store for semantic retrieval.
* ✅ Enhance NL→SQL translation using LLMs (T5 / LLaMA / GPT-based models).
* ✅ Role-based access and API key management.
* ✅ Caching layer for query optimization.
* ✅ Add CI/CD workflows and automated tests.

---

## 🧰 Developer Notes

* **Security:** SQL generation is heuristic-based. Always validate before production use.
* **Extensibility:** Plug in a local LLM for more advanced query understanding.
* **Performance:** Use connection pooling and async operations for scale.

---

## 🧑‍💻 Author

**Aryan Amaresh**
📧 [btech10005.23@bitmesra.ac.in](mailto:btech10005.23@bitmesra.ac.in)
🔗 [LinkedIn](https://www.linkedin.com/in/aryan-amaresh-678733340)
💻 [GitHub](https://github.com/<your-username>)

---

## 🪪 License

This project is licensed under the **MIT License** — feel free to use and modify with attribution.

---

## 🌟 Acknowledgements

* [FastAPI](https://fastapi.tiangolo.com/)
* [Sentence Transformers](https://www.sbert.net/)
* [React](https://react.dev/)
* [PostgreSQL](https://www.postgresql.org/)

> *“Turning natural language into actionable insights.”*
