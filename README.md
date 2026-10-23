
# RAG Mini App

Speak with the PDF is a Retrieval-Augmented Generation (RAG) application built with Google Colab, OpenRouter, and Pinecone. The project allows users to upload a PDF or DOCX document, extract and chunk its content, convert the text into vector embeddings, store those embeddings in Pinecone, and ask natural-language questions about the document.

For this project, the application was tested using “The Lost Crystal of Eldoria,” an AI-generated text-based adventure game. The system retrieves relevant sections from the document and provides context-grounded answers using an LLM through OpenRouter. The implementation also compares Vanilla LLM responses with RAG-based responses to demonstrate how retrieval can improve factual accuracy and reduce unsupported answers. The notebook successfully converts the DOCX document to PDF, creates 24 text chunks, generates 1536-dimensional embeddings, and indexes them in Pinecone.

🔧 Technologies Used
Python
Google Colab
OpenRouter API
OpenAI GPT-4o-mini
OpenAI text-embedding-3-small
Pinecone Vector Database
PyPDF
LibreOffice for DOCX → PDF conversion
NumPy
⚙️ How It Works
Upload a PDF or DOCX document.
Convert DOCX files to PDF when required.
Extract and normalize the document text.
Split the text into overlapping chunks.
Generate vector embeddings using text-embedding-3-small.
Store the embeddings and document metadata in Pinecone.
Convert the user's question into an embedding.
Retrieve the most relevant document chunks using cosine similarity.
Send the retrieved context to GPT-4o-mini through OpenRouter.
Generate an answer using only the retrieved document context.
Compare the RAG answer with a Vanilla LLM answer.

The implementation uses a context-restricted system prompt instructing the model to answer only from the retrieved document and respond that it does not know when the information cannot be found in the document.

🧪 Example Questions

The application was tested with questions such as:

What is the main objective of The Lost Crystal of Eldoria?
What are the three main branching paths in the game and what is the outcome of each path?
What were the main strengths and weaknesses identified during the playtests?

The RAG system was able to retrieve specific information about the game's branching paths, including the Hero's Path, Risky Path, and Power Path, and their corresponding outcomes.

🎯 Project Goal

The main goal of this project is to demonstrate how Retrieval-Augmented Generation can connect an LLM to a specific document, allowing users to interact with their own content through natural-language questions while reducing hallucinations and improving document-grounded responses.

