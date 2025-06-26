# RAG Chatbot for Car Manual

This project implements a **Retrieval-Augmented Generation (RAG)** chatbot that answers questions about a car manual, such as dashboard warnings and driving recommendations. Built using **LangChain** and free tools in **Google Colab**, it combines document retrieval with a large language model (LLM) to provide context-aware responses.

## Features
- Extracts text from a car manual PDF using `PyPDF2`.
- Splits text into chunks and indexes them in a **FAISS** vector store with **Hugging Face** embeddings (`all-MiniLM-L6-v2`).
- Uses **Groq**'s free LLM (`mixtral-8x7b-32768`) to generate accurate responses.
- Includes an interactive interface in Colab for user-friendly querying.
- Answers questions like:
  - "What does the check engine light mean?"
  - "What should I do if the tire pressure warning light comes on?"

## Tech Stack
- **LangChain**: For the RAG pipeline and retrieval.
- **Hugging Face**: Free embeddings for text vectorization.
- **FAISS**: Lightweight vector store for efficient retrieval.
- **PyPDF2**: To process PDF manuals.
- **Groq**: Free LLM API for response generation.
- **Google Colab**: Free cloud environment for development.

## How It Works
1. Upload a car manual PDF to Colab.
2. Extract and chunk the text for indexing.
3. Convert chunks to embeddings and store them in FAISS.
4. Use LangChain's `RetrievalQA` chain to retrieve relevant chunks and generate answers with Groq's LLM.
5. Interact via a simple Colab interface or predefined queries.

## Setup Instructions
1. Open the notebook (`rag_chatbot.ipynb`) in Google Colab.
2. Obtain a free **Groq API key** from [console.groq.com](https://console.groq.com) and add it to Colab Secrets as `GROQ_API_KEY`.
3. Upload a car manual PDF (e.g., from [manualslib.com](https://www.manualslib.com)).
4. Run the notebook cells sequentially to set up and test the chatbot.

## Example Usage
```python
ask_question("What does the check engine light mean?")
# Output: The check engine light indicates a potential issue with the engine or emissions system...
