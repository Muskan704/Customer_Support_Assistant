> A fully local AI chatbot using RAG + LLM with zero API cost.

# ShopMart AI Customer Support Chatbot

An AI-powered customer support chatbot built using 
RAG (Retrieval Augmented Generation) + Local LLM.
Runs 100% locally — no API cost, no cloud dependency.

## Tech Stack
- Python + Flask
- Ollama (Gemma3:4b — local LLM)
- ChromaDB (vector database)
- Sentence Transformers (all-MiniLM-L6-v2)
- HTML/CSS/JS (frontend)

## Project Structure
```
CHATBOT/
├── knowledge_base/     # Add your .txt files here
├── templates/
│   └── index.html      # Chat UI
├── app.py              # Flask server
├── chat_engine.py      # LLM + conversation logic
├── rag_engine.py       # RAG pipeline
├── ingest.py           # Knowledge base ingestion
└── requirements.txt    # Python dependencies
```

## Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/Muskan704/Customer_Support_Assistant.git
cd Customer_Support_Assistant
```

### 2. Create virtual environment
```bash
python -m venv myenv
myenv\Scripts\activate      # Windows
source myenv/bin/activate   # Mac/Linux
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Install Ollama
Download from https://ollama.com and pull the model:
```bash
ollama pull gemma3:4b
```

### 5. Add your knowledge base
Place your `.txt` files inside the `knowledge_base/` folder.

### 6. Ingest knowledge base
```bash
python ingest.py
```

### 7. Run the app
```bash
ollama serve          # Run in a separate terminal
python app.py         # Run in main terminal
```

### 8. Open browser
```
http://localhost:5000
```

## Notes
- Run `python ingest.py` again only if you change .txt files
- `chroma_db/` is auto-created on first ingest — do not upload
- `myenv/` is machine-specific — always create fresh on new device
