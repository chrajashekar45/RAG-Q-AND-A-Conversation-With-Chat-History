# RAG Q&A Conversation With PDF and Chat History

**Conversational Retrieval-Augmented Generation (RAG) using PDFs and Persistent Chat History**  
_Empower your users to upload PDFs and converse with their content in real-time — with seamless history-aware context and advanced retrieval capabilities._

---

## 🚀 Overview

This project is an advanced, interactive web application built with **Streamlit** and **LangChain**. It enables users to:
- Upload one or multiple PDF files.
- Engage in rich, conversational Q&A with their documents.
- Leverage robust chat history to enable context retention.
- Utilize state-of-the-art embedding models and vector retrieval (FAISS).
- Support for HuggingFace and Groq APIs for deep NLP features.

Perfect for research, enterprise search, educational use-cases, and anywhere document Q&A with persistent, contextual conversations adds value.

---

## 🛠️ Features

- **PDF Upload & Parsing:** Effortlessly upload PDFs, which are chunked and indexed.
- **Conversational Chat Interface:** Ask questions about your documents in natural language. History-aware, so context is never lost.
- **Retrieval-Augmented Generation:** Combines RAG techniques with leading language models for precise, context-rich responses.
- **Session Management:** Each chat session is uniquely identifiable and maintains its own conversation history.
- **Custom Embeddings:** Integrates **HuggingFaceEndpointEmbeddings** for customizable, production-grade retrieval.
- **Pluggable LLM Backends:** Uses Groq and HuggingFace APIs — quickly switch or expand models as needed.
- **Vector Database:** FAISS-based storage for fast, scalable similarity search.
- **Accessible UI:** Powered by Streamlit for rapid prototyping and deployment.

---

## 🏗️ How It Works

1. **User Uploads PDFs:**  
   Files are parsed using [`PyPDFLoader`](https://python.langchain.com/docs/modules/data_connection/document_loaders/pdf).
2. **Document Chunking & Embeddings:**  
   Documents are split into manageable chunks and transformed into embeddings (default: `BAAI/bge-small-en-v1.5`).
3. **Vectorstore Creation:**  
   Data is indexed with FAISS for high-performance retrieval.
4. **Conversational Retrieval with History:**  
   - Users converse with the system.
   - Each message is interpreted in the context of prior exchanges using session IDs.
   - Retrieval and answer chains are managed by LangChain, ensuring up-to-date document context.

---

## 📦 Project Structure

```
.
├── app.py              # Main Streamlit application logic
├── requirements.txt    # Python dependencies
├── .devcontainer/      # (If used) VSCode/Dev Container setup
```

---

## 🔧 Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/chrajashekar45/RAG-Q-AND-A-Conversation-With-Chat-History.git
   cd RAG-Q-AND-A-Conversation-With-Chat-History
   ```

2. **Set Up a Virtual Environment (optional but recommended)**

   ```bash
   python -m venv venv
   source venv/bin/activate      # On Windows: venv\Scripts\activate
   ```

3. **Install Requirements**

   ```bash
   pip install -r requirements.txt
   ```

4. **Create a `.env` File with Your API Keys**

   ```
   LANGCHAIN_API_KEY=sk-...
   HF_TOKEN=hf_...
   ```

---

## 🚦 Usage

1. **Run the Streamlit App**

   ```bash
   streamlit run app.py
   ```

2. **Navigate & Interact**
   - Open the link provided by Streamlit.
   - Enter your **Groq API key** when prompted.
   - Upload PDFs, select or provide a chat session ID, and start conversing!

---

## ⚙️ Configuration

- **APIs:**  
  - Requires API keys for HuggingFace and Groq (enter at runtime or set via `.env`).
- **Session IDs:**  
  - Use custom session IDs to maintain separate chat histories for different conversations or users.

---

## 🧰 Key Dependencies

- **Streamlit:** Interactive UI
- **LangChain (Core, Community, HuggingFace, Groq, Text Splitters)**
- **FAISS:** Fast similarity search
- **PyPDF:** PDF parsing
- **dotenv:** Environment variable management

(See `requirements.txt` for the full list.)

---

## 🧑‍💻 Code Walk-Through Highlights

- **app.py** orchestrates:
  - Secure credential management via `dotenv` and Streamlit Secrets
  - PDF upload, chunking, embedding, and indexing
  - Custom prompts for question contextualization and answering
  - Modular, reusable session chat history using `ChatMessageHistory`
  - Clean, warning-guarded user experience if keys are missing

---

## 📚 Example Use-Cases

- Law firms querying case document archives
- Research assistants navigating scientific papers
- Corporate internal knowledge bases for onboarding or support
- Students and teachers for textbook Q&A

---

