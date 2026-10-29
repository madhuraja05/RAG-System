 Document Q&A Using RAG

 About the Project

This project uses Retrieval-Augmented Generation (RAG) to answer questions based on information extracted from a PDF document. In this project, an SQL document is used as the source of information.

The system extracts text from the PDF, splits it into chunks, generates embeddings, and stores them in ChromaDB. When a user asks a question, the system retrieves relevant document chunks and uses a Groq-hosted language model to generate an answer based on the retrieved context.

 Features

- Extracts text from PDF documents using `pypdf`.
- Splits text into overlapping chunks using LangChain text splitters.
- Generates text embeddings using Sentence Transformers (`all-MiniLM-L6-v2`).
- Stores and retrieves document chunks using ChromaDB.
- Uses the Groq API to generate context-based answers.
- Provides an `ask_rag(question)` function to answer multiple questions.

  Tech Stack

- Python
- Google Colab / Jupyter Notebook
- pypdf
- Sentence Transformers
- ChromaDB
- LangChain Text Splitters
- Groq API

How It Works

1. Load an SQL PDF document from Google Drive.
2. Extract text from the PDF.
3. Split the extracted text into chunks of 1,000 characters with an overlap of 200 characters.
4. Generate embeddings for each chunk.
5. Store the chunks and embeddings in a ChromaDB collection.
6. Convert the user's question into an embedding and retrieve the three most relevant chunks.
7. Send the retrieved context and question to a Groq-hosted language model.
8. Generate an answer based on the retrieved context. If the answer is not available in the document, the model is instructed to say that it cannot find the answer.

Use Case

This project helps users ask questions about an SQL document and receive answers based on the information available in that document, without manually searching through the entire PDF.

