 
## rag_project/

            # RAG Project - Retrieval-Augmented Generation System

## Overview
This project implements a Retrieval-Augmented Generation (RAG) system that allows a language model to produce answers grounded in external documents. It combines a retriever (vector database) and a generator (large language model) to provide accurate responses to user queries.

The system can process documents (PDF, TXT) and create embeddings for semantic search. Users can ask questions via a web interface powered by Gradio. This project demonstrates a working RAG pipeline deployed live on Hugging Face Spaces.

---

## Project Structure

rag-project/
- app.py                # Main entry file for Hugging Face Gradio app
- requirements.txt      # Python dependencies
- README.md
- app/
  - utils.py            # Helper functions for preprocessing, embeddings
- data/
  - docs/               # Folder containing PDF/TXT documents

---

## Setup Architecture

1. User Query  
   The user enters a query in the web interface.

2. Preprocessing  
   The query is cleaned and tokenized for processing.

3. Embedding  
   The query is converted into a vector using a sentence embedding model.

4. Vector Database / Retriever  
   The query embedding is compared against document embeddings stored in FAISS to retrieve the most relevant documents.

5. Retrieved Documents  
   The top relevant document(s) are selected as context for the language model.

6. Generative Model  
   A language model (e.g., Flan-T5, GPT) generates an answer based on the retrieved documents.

7. Final Answer  
   The generated answer is displayed to the user in the web interface.

---

## Setup Instructions

1. Clone the Repository

2. Install Dependencies

3. Prepare Documents  
Add your PDF or TXT documents inside the `data/docs/` folder.

4. Run the App
The app will start in Gradio. Open the URL displayed in the terminal or visit the live Hugging Face link below.

---

## Live Demo
The project is hosted live on Hugging Face Spaces:
https://huggingface.co/spaces/manogna-27/rag-project

---

## Remarks / Trade-offs

- Currently, the system uses FAISS for retrieval and Sentence Transformers for embeddings. This ensures fast queries but requires memory proportional to the number of documents.  
- Precomputed embeddings can be saved to reduce load time for large datasets.  
- Using larger LLMs can improve answer quality but increases inference time and computational cost.  
- The system currently supports TXT and PDF documents; adding other formats requires preprocessing.  
- The Gradio interface is simple and lightweight, suitable for demo purposes; a full frontend could improve usability.  

---

## What to do next

1. Integrate more advanced LLMs such as Flan-T5-large or LLaMA for better answer quality.  
2. Add support for real-time PDF ingestion and automatic embedding updates.  
3. Implement caching or persistent storage for embeddings to handle large datasets efficiently.  
4. Enhance the UI with more interactive elements or a React frontend.  
5. Add authentication if deploying in a private or multi-user environment.  
6. Connect the Hugging Face Space to your GitHub repo for auto-deploy on updates.

---

## Technologies Used

- Python  
- Gradio  
- FAISS (vector search)  
- Sentence Transformers (embeddings)  
- Hugging Face Hub (LLMs)  
- PDF/TXT document processing  

resume link https://drive.google.com/file/d/1d1aF4DoQzvv_LJdq9Stolo5phEiWSPdV/view?usp=sharing ##
