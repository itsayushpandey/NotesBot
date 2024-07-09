# NotesBot: Question answering using RAG on class notes

## Overview
The Q-A Bot project aims to create an advanced Question-Answering (QA) system using Retrieval-Augmented Generation (RAG) techniques. This system is designed to answer user queries accurately by leveraging external knowledge bases.

## Key Components and Workflow

1. Document Loading and Preprocessing
Document Loading: Utilized PyPDFDirectoryLoader from LangChain to load PDF documents from a specified directory.
Text Splitting: Implemented text splitting using CharacterTextSplitter to manage large documents effectively by breaking them into manageable chunks.

2. Embeddings and Vector Storage
Document Embeddings: Employed HuggingFaceEmbeddings with the sentence-transformers/all-mpnet-base-v2 model for generating document embeddings.
Vector Database: Created a vector database using Chroma to store these embeddings, enabling efficient similarity search and retrieval.

3. Query Embedding and Context Retrieval
Query Embedding: Embedded user queries using the same HuggingFace embeddings model.
Context Retrieval: Performed similarity searches in the vector database to retrieve the most relevant document chunks as context for answering the query.

4. Model and Pipeline Integration
Text Generation: Integrated HuggingFace pipelines using models like TinyLlama/TinyLlama-1.1B-Chat-v1.0 for text generation.

5. Prompt Engineering
Chat Templates: Developed custom chat templates for HuggingFace models to structure the input for the LLMs.
Prompt Formatting: Ensured the models receive properly formatted prompts by using PromptTemplate from LangChain.

6. Inference and Response Generation
QA Process Management: Leveraged the LLMChain class from LangChain to manage the end-to-end QA process.
Contextual Answers: Retrieved context from the document database and fed it along with the user query to the LLM, generating accurate and contextually relevant answers.


# Technical Challenges and Solutions
Handling Large Documents: Used text splitting and chunking to process large documents efficiently.
Contextual Accuracy: Enhanced answer accuracy by embedding both documents and queries with the same model, ensuring high-quality similarity searches.
Model Integration: Overcame challenges with integrating different models and pipelines by employing specific tokenizers and chat templates.

# How to Run the Project
1) Clone the Repository
2) Install Dependencies
3) Place your PDF documents in the documents directory.
4) Run the Q-A Bot
