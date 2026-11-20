# PDF RAG Pipeline

A notebook-based retrieval-augmented generation (RAG) example. It loads PDF files, splits them into text chunks, creates sentence embeddings, stores them in Chroma, retrieves relevant passages, and uses an LLM to draft an answer.

## Features

- Loads every PDF in `data/` with LangChain's PDF loader.
- Builds embeddings with `all-MiniLM-L6-v2` and persists the Chroma index locally.
- Retrieves relevant passages and supports OpenAI and Groq chat models.

## Tech Stack

Python, Jupyter, LangChain, Sentence Transformers, ChromaDB, OpenAI API, and Groq API.

## Installation

Use Python 3.10 or newer. From the project directory, create and activate a virtual environment, then install dependencies:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Copy `.env.example` to `.env` and add the API key or keys you intend to use. Never commit `.env`; it is ignored by Git. The notebook loads it with `python-dotenv`.

## Usage

Open `RAG_And_working _with apis.ipynb` in VS Code or Jupyter and run the cells in order. Put your own PDF inputs in `data/`. The first run downloads the embedding model and creates `vector_store/`, which is local generated data and is excluded from Git.

The notebook contains separate OpenAI and Groq examples. Configure the matching key before running each provider section; running the full notebook requires both keys.

## Results

The notebook produces retrieved passages and an LLM-generated response at runtime. No benchmark or fixed result is claimed; responses depend on the input PDFs, retrieval settings, model, and provider.

## Before Uploading

- Confirm you have permission to redistribute both PDFs in `data/` and the text in `RAG_text_data.txt`. Their licenses could not be established from the project files.
- PDFs under `data/` are ignored by Git by default because their licensing and privacy status are unknown, and an automated scan found email- and phone-like strings. Review the documents locally before deciding whether to remove that ignore rule.
- Review all source documents for private or personal information before making them public.
- Add a project license only after choosing terms you are authorized to grant.