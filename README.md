# Final-Project-Boot-Camp-Awais-ALi

IntelliCourse API

An AI-powered university course advisor built with FastAPI, LangChain, and HuggingFace.
This API helps students query course prerequisites, catalogs, and general information using RAG (Retrieval-Augmented Generation) and web search.

Features

Query university courses and prerequisites

Hybrid retrieval (course retriever + web search)

Uses HuggingFace models (DistilGPT2 by default)

REST API built with FastAPI

Easily extensible with new tools and models

Project Structure
Final Project Boot Camp/
│── app/
│   ├── main.py          # FastAPI entry point
│   ├── agent.py         # AI Agent (retriever + web search + LLM)
│   ├── rag.py           # Retrieval logic
│   ├── __init__.py      # Marks app/ as a Python package
│── data/                # Course documents, embeddings, etc.
│── db/                  # Database files ( Used in this)
│── venv/                # Virtual environment
│── requirements.txt     # Dependencies



Setup Instructions
1. Clone the project
git clone <your-repo-url>
cd "Final Project Boot Camp"

2. Create a virtual environment
python -m venv venv
venv\Scripts\activate   # On Windows
source venv/bin/activate  # On Linux/Mac

3. Install dependencies
pip install -r requirements.txt

4. Setup environment variables

Create a .env file in the root folder:

TAVILY_API_KEY=your_tavily_api_key_here

5. Run the API
uvicorn app.main:app --reload

6. Test in browser

Go to:

Docs UI: http://127.0.0.1:8000/docs

Health check: POST /chat with:

{
  "query": "What are the prerequisites for Artifical Intelligence ?"
}



Requirements (example requirements.txt)

fastapi
uvicorn
python-dotenv
transformers
langchain
langchain-community
langchain-tavily

Future Improvements

Swap HuggingFace DistilGPT2 with larger models (LLaMA, Falcon, etc.)

Add vector database (FAISS, ChromaDB) for better retrieval

Extend to multiple universities’ course catalogs
