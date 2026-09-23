# 📄 RAG Document with PDF

A **Retrieval-Augmented Generation (RAG)** application built with **LangChain** that allows users to upload PDF documents and ask questions about their content. The application uses **Hugging Face embeddings**, **Chroma vector storage**, and conversational retrieval to generate context-aware responses based on the uploaded document.

## ✨ Features

* 📤 **PDF Upload** — Upload a PDF document directly to the application.
* 📖 **PDF Processing** — Extract document content using `PyPDFLoader`.
* ✂️ **Text Chunking** — Split documents into manageable chunks using `RecursiveCharacterTextSplitter`.
* 🤗 **Hugging Face Embeddings** — Convert document chunks into vector embeddings.
* 🗄️ **Chroma Vector Database** — Store and retrieve relevant document chunks efficiently.
* 👤 **Session Management** — Maintain separate conversation histories for different sessions.

## 🛠️ Tech Stack

| Technology                         | Purpose                                          |
| ---------------------------------- | ------------------------------------------------ |
| **Python**                         | Core programming language                        |
| **LangChain**                      | RAG pipeline and LLM orchestration               |
| **PyPDFLoader**                    | Extract text from uploaded PDFs                  |
| **Hugging Face Embeddings**        | Generate vector embeddings                       |
| **Chroma**                         | Vector database for document retrieval           |
| **Session Management**             | Maintains independent user conversation sessions |

## 🔄 How It Works

```text
User Uploads PDF
       ↓
   PyPDFLoader
       ↓
Extract Document Text
       ↓
RecursiveCharacterTextSplitter
       ↓
Create Document Chunks
       ↓
Hugging Face Embeddings
       ↓
Chroma Vector Database
       ↓
User Asks a Question
       ↓
Session / Chat History
       ↓
History-Aware Retriever
       ↓
Retrieve Relevant Chunks
       ↓
Retrieval Chain
       ↓
      LLM
       ↓
Context-Aware Answer
```

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd RAG-Document-with-PDF
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

For macOS/Linux:

```bash
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure Environment Variables

Create a `.env` file and add the required API credentials for the LLM used by the application.

```env
OPENAI_API_KEY=your_api_key
```

### 5. Run the Application

If the application uses Streamlit:

```bash
streamlit run app.py
```

## 📖 How to Use

1) Launch the application.
2) Upload a PDF document.
3) The extracted content is divided into smaller chunks using `RecursiveCharacterTextSplitter`.
4) Hugging Face embeddings are generated for the document chunks.
5) The embeddings are stored in **Chroma**.
6) Enter a question related to the uploaded PDF.
7) The application retrieves relevant document chunks.
8) The retrieval chain passes the relevant context to the LLM.
9) The generated answer is displayed while maintaining the conversation history.

## 🧠 RAG Architecture

The application uses a conversational RAG architecture:

```text
                 ┌─────────────────┐
                 │   Upload PDF    │
                 └────────┬────────┘
                          ↓
                 ┌─────────────────┐
                 │  PyPDFLoader    │
                 └────────┬────────┘
                          ↓
              ┌───────────────────────┐
              │ RecursiveCharacter    │
              │ TextSplitter          │
              └───────────┬───────────┘
                          ↓
                 ┌─────────────────┐
                 │ Hugging Face    │
                 │   Embeddings    │
                 └────────┬────────┘
                          ↓
                 ┌─────────────────┐
                 │     Chroma      │
                 │  Vector Store   │
                 └────────┬────────┘
                          ↓
              ┌───────────────────────┐
              │ History-Aware         │
              │ Retriever             │
              └───────────┬───────────┘
                          ↓
                 ┌─────────────────┐
                 │ Retrieval Chain │
                 └────────┬────────┘
                          ↓
                 ┌─────────────────┐
                 │       LLM       │
                 └────────┬────────┘
                          ↓
                 ┌─────────────────┐
                 │     Answer      │
                 └─────────────────┘
```

## 🎯 Use Cases

* 📚 Ask questions about study material
* 📄 Interact with research papers
* 📖 Query technical documentation
* 📝 Extract information from reports
* 💬 Have contextual conversations with uploaded documents
