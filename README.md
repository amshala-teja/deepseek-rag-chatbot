
# 🚀 **Sai Teja's RAG Chatbot 3.0 – Now with GraphRAG & Chat History Integration!**
**(100% Free, Private (No Internet), and Local PC Installation)**  


🔥 **DeepSeek + NOMIC + FAISS + Neural Reranking + HyDE + GraphRAG + Chat Memory = The Ultimate RAG Stack!**  

This chatbot enables **fast, accurate, and explainable retrieval of information** from PDFs, DOCX, and TXT files using **DeepSeek-7B**, **BM25**, **FAISS**, **Neural Reranking (Cross-Encoder)**, **GraphRAG**, and **Chat History Integration**.  

---

## 🔹 **New Features in This Version**

- **GraphRAG Integration**: Builds a **Knowledge Graph** from your documents for more **contextual** and **relational** understanding.  
- **Chat Memory History Awareness**: Maintains context by referencing **chat history**, enabling more **coherent** and **contextually relevant** responses.  
- **Improved Error Handling**: Enhanced support for smoother user experience and bug fixes.  

---

## 🔜 **Upcoming Features**

- **Model Selector UI**: Choose from models like `mistral`, `gemma`, or `llama3` directly in the interface.  
- **Smart Question Suggestions**: Automatically suggests relevant questions based on the document content.  
- **Multiple RAG Pipelines**: Switch between basic and advanced pipelines (e.g., FAISS vs ChromaDB with metadata filtering).  
- **Flexible Data Stores & Search Techniques**: Support for PostgreSQL, Pinecone, Weaviate, ChromaDB, using cosine, Euclidean, or Jaccard similarity.

---

## 🛠 **Installation & Setup**

You can install and run **Sai Teja's RAG Chatbot** in one of two ways:

### **1️⃣ Traditional (Python/venv) Installation**
```bash
git clone https://github.com/saitejaamshala/deepseek-rag-chatbot.git
cd deepseek-rag-chatbot

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # Or venv\Scripts\activate on Windows

# Upgrade pip and install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

### Step B: Download & Set Up Ollama
1. Download Ollama → [https://ollama.com/](https://ollama.com/)  
2. Pull required models:
   ```bash
   ollama pull deepseek-r1:7b
   ollama pull nomic-embed-text
   ```

Update `.env` if using custom models.

### Step C: Run the Chatbot
```bash
ollama serve
streamlit run app.py
```
Visit: [http://localhost:8501](http://localhost:8501)

---

### **2️⃣ Docker Installation**

#### A) Single-Container (Ollama on Host)
```bash
docker-compose build
docker-compose up
```
Runs at [http://localhost:8501](http://localhost:8501)

#### B) Two-Container (Ollama in Docker)
```yaml
version: "3.8"
services:
  ollama:
    image: ghcr.io/jmorganca/ollama:latest
    ports:
      - "11434:11434"

  deepgraph-rag-service:
    build: .
    ports:
      - "8501:8501"
    environment:
      - OLLAMA_API_URL=http://ollama:11434
      - MODEL=deepseek-r1:7b
      - EMBEDDINGS_MODEL=nomic-embed-text:latest
      - CROSS_ENCODER_MODEL=cross-encoder/ms-marco-MiniLM-L-6-v2
    depends_on:
      - ollama
```
Then run:
```bash
docker-compose build
docker-compose up
```

---

## 🧠 **How It Works**

1. **Upload Documents**: PDF, DOCX, or TXT via sidebar.  
2. **Hybrid Retrieval**: BM25 + FAISS fetches relevant chunks.  
3. **GraphRAG**: Builds knowledge graph to enhance context.  
4. **Neural Reranking**: Cross-encoder reorders chunks.  
5. **HyDE Expansion**: Adds hypothetical answers for recall.  
6. **Chat Memory**: Maintains long conversation history.  
7. **DeepSeek-7B**: Generates final response from ranked data.

---

## 🌟 **Why This Upgrade?**

| Feature                       | Previous Version        | This Version                      |
|------------------------------|-------------------------|-----------------------------------|
| Retrieval Method             | BM25 + FAISS            | + GraphRAG                        |
| Contextual Understanding     | Basic                   | Enhanced with Knowledge Graph     |
| UI                           | Standard                 | Custom + Sidebar Navigation       |
| Chat Memory                  | No                      | Full Context Retention            |
| Stability                    | Basic Error Handling     | Improved UX & Debug Handling      |

---

## 🤝 **Contributing**

- Fork and submit PRs or issues  
- Open to community feedback and contributions  
- Let's build better local AI tools together!

---


---

**Run your own private RAG-powered chatbot—fully offline, blazing fast, and intelligent.**  
_Local Knowledge, Personalized Chat. Powered by Open-Source._
