# PDF RAG System using LangChain, ChromaDB and Groq

A Retrieval-Augmented Generation (RAG) application that allows users to query PDF documents using Large Language Models (LLMs).

The system extracts text from PDF files, splits documents into semantic chunks, generates vector embeddings, stores them in ChromaDB, retrieves relevant content using semantic search, and generates context-aware answers using a Groq-hosted LLM.

---

## Project Overview

This project demonstrates the complete RAG workflow:

1. Load PDF documents
2. Convert documents into LangChain Document objects
3. Split documents into smaller chunks
4. Generate embeddings for each chunk
5. Store embeddings in ChromaDB
6. Perform semantic retrieval for user queries
7. Generate answers using a Large Language Model

---

## Project Architecture

```text
PDF Documents
      │
      ▼
Document Loaders
(PyMuPDFLoader)
      │
      ▼
Document Objects
      │
      ▼
Text Chunking
(RecursiveCharacterTextSplitter)
      │
      ▼
Embeddings
(Sentence Transformers)
      │
      ▼
Vector Store
(ChromaDB)
      │
      ▼
Semantic Retrieval
(RAGRetriever)
      │
      ▼
Context Creation
      │
      ▼
Groq LLM
      │
      ▼
Generated Answer
```

---

## Features

- PDF document ingestion
- Automatic document chunking
- Embedding generation using Sentence Transformers
- ChromaDB vector database integration
- Semantic similarity search
- Retrieval-Augmented Generation pipeline
- Source tracking and confidence scoring
- Context inspection for debugging

---

## Technologies Used

### Frameworks

- LangChain
- ChromaDB

### Document Processing

- PyMuPDF
- LangChain Document Loaders

### Embedding Model

- all-MiniLM-L6-v2

### LLM

- Groq API
- Llama 3.1

### Environment

- Python 3.12
- Jupyter Notebook

---

## Project Structure

```text
Project_RAG/
│
├── data/
│   ├── pdf/
│   ├── vector_db/
│
├── notebooks/
│   └── rag_pipeline.ipynb
│
├── .env
├── requirements.txt
└── README.md
```

---

## Pipeline Stages

### 1. Data Ingestion

Load PDF documents using:

```python
DirectoryLoader
PyMuPDFLoader
```

Output:

```python
List[Document]
```

---

### 2. Data Chunking

Documents are split into smaller chunks using:

```python
RecursiveCharacterTextSplitter
```

Benefits:

- Better semantic retrieval
- Improved LLM context utilization
- Reduced token usage

---

### 3. Data Embedding

Each chunk is converted into a dense vector representation using:

```python
SentenceTransformer
```

Model:

```text
all-MiniLM-L6-v2
```

---

### 4. Vector Store

Embeddings and metadata are stored in ChromaDB.

Stored Information:

- Chunk ID
- Document Content
- Metadata
- Embedding Vector

---

### 5. Retrieval Pipeline

User queries are converted into embeddings.

The system performs semantic similarity search to retrieve the most relevant document chunks.

---

### 6. Answer Generation

Retrieved chunks are combined into a context.

The context and user query are passed to a Groq-hosted LLM for answer generation.

---

## Example Query

### Question

```text
What are the main steps in a RAG pipeline?
```

### Generated Answer

```text
The main steps in a RAG pipeline are:

1. Document Loading
2. Text Chunking
3. Embedding Generation
4. Vector Database Storage
5. Semantic Retrieval
6. Context Augmentation
7. LLM Response Generation
```

---

## Setup Instructions

### Clone Repository

```bash
git clone https://github.com/your-username/Project_RAG.git
cd Project_RAG
```

### Create Virtual Environment

```bash
python -m venv .venv
```

Activate the environment:

#### Linux / macOS

```bash
source .venv/bin/activate
```

#### Windows

```bash
.venv\Scripts\activate
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

---

## Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_api_key_here
```

---

## How to Run

1. Add PDF files inside the `data/pdf/` directory.
2. Run the notebook cells sequentially:
   - Data Ingestion
   - Data Chunking
   - Data Embedding
   - Vector Store Creation
   - Retrieval Pipeline
   - RAG Pipeline
3. Enter a query.
4. Receive context-aware answers from the LLM.

---

## Future Improvements

- Conversational memory
- Hybrid search (Keyword + Semantic Search)
- Re-ranking
- Metadata filtering
- FastAPI backend
- Streamlit frontend
- Multi-document support
- Production deployment

---

## Learning Outcomes

Through this project, the following concepts were implemented and explored:

- LangChain Document Loaders
- Document Standardization
- Recursive Text Chunking
- Sentence Transformer Embeddings
- Vector Databases
- ChromaDB Collections
- Semantic Search
- Retrieval-Augmented Generation (RAG)
- Prompt Engineering
- LLM Integration with Groq

---

## Author

**Sri Nithya**

Built as a hands-on project to understand the complete Retrieval-Augmented Generation (RAG) workflow using LangChain, ChromaDB, Sentence Transformers, and Groq-hosted LLMs.