# Chapter 7: RAG Chatbot Inside the Book

This book includes a smart chatbot that understands everything written here.

How it works:
- Your chapters get embedded  
- Embeddings go into Qdrant  
- FastAPI handles requests  
- ChatKit generates answers  
- Users can select text and ask specific questions about it  

---

## Practice: Test the Chatbot  
Try asking:
- "What is the main idea of Chapter 2?"  
- "Explain the full flow in Chapter 3."  
- "How does the hands-on project work?"  

:::tip Accuracy Test  
Ask detailed questions like:  
"What are the 5 steps in the pipeline?"  
"Which component handles failure conditions?"  

The goal is to check if the RAG system retrieves the right sections.
:::

---

## Mini Challenge  
Select a paragraph from this book and ask the chatbot  
"What does this mean?"  

See if it explains correctly.
