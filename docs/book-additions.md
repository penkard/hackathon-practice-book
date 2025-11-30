## Rag-architecture-appendix title: Appendix: RAG Architecture & Tooling sidebar_label: RAG Architecture

### Appendix: The Technical Architecture

This section documents the specific technical implementation used to build this book and its integrated intelligence systems. It serves as a reference for the Hackathon judges and a testing ground for the embedded RAG Chatbot.

:::tip Testing the Chatbot
Use the definitions and steps below to test the accuracy of the Retrieval-Augmented Generation system. Ask questions like "What is the 5-phase RAG flow?" or "How does Spec-Kit Plus work?"
:::

1. The Retrieval-Augmented Generation (RAG) Architecture

The core intelligence of this project is powered by a custom RAG pipeline connecting Docusaurus, FastAPI, and Qdrant.

## The 5-Phase Retrieval Flow

### The RAG loop involves five distinct stages to ensure accurate, context-aware responses.

Ingestion (Preprocessing): When the book is built, Markdown content is chunked into digestible segments (paragraphs/headings). These chunks are converted into numerical embeddings using a pre-trained model.

Storage (Qdrant Cloud): These vectors are stored in the Qdrant Cloud Free Tier vector database alongside metadata (chapter titles, file paths). This creates the "knowledge index."

User Query & Vectorization: When a user asks a question, the FastAPI backend receives it and converts it into a vector using the same embedding model.

Retrieval: The backend queries Qdrant for the top $k$ text chunks mathematically closest to the query vector. This ensures the LLM receives context only from this book.

Generation: The retrieved chunks + user query are sent to the LLM (via OpenAI Agents/ChatKit). The LLM generates the final response based strictly on the provided context.