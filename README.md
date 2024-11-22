# Medical Chatbot - End-to-End Generative AI Application

This project implements an end-to-end medical chatbot using Flask as the backend framework and a combination of LangChain, Pinecone, and Hugging Face embeddings for natural language processing and retrieval-augmented generation (RAG).

The chatbot is capable of answering user queries by leveraging a retriever-based mechanism for finding relevant context and generating responses using a large language model (LLM).

---

## Features

- **PDF Loading & Text Processing**: Extracts and processes text from medical PDFs for embedding and storage.
- **Pinecone Vector Store**: Stores and retrieves document embeddings for context-based responses.
- **Hugging Face Embeddings**: Utilizes Sentence Transformers for efficient text vectorization.
- **RAG Model**: Combines retrieval and generative capabilities to handle complex queries.
- **Flask Frontend**: Provides an interactive chat UI using HTML, Bootstrap, and AJAX.
- **Customizable LLM**: Supports models like OpenAI's GPT or Llama 2 via LangChain.

---

## Prerequisites

Ensure the following are installed and configured:

1. Python 3.9 or above.
2. Required Python libraries (install using `requirements.txt`):
   ```bash
   pip install -r requirements.txt
3. Pinecone API Key and Index setup.
4. Hugging Face model (sentence-transformers/all-MiniLM-L6-v2 for embeddings).
5. Flask framework.
6. Download the Llama 2 Model:
   llama-2-7b-chat.ggmlv3.q4_0.bin
   From the following link:
   https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML/tree/main

**Setup Instructions**:
1. Clone the Repository
   bash
   git clone <repository-url>
  cd project
2. Install Dependencies
  bash
  pip install -r requirements.txt
3. Configure Environment Variables
   Create a .env file in the project root:
   PINECONE_API_KEY=your_pinecone_api_key
   OPENAI_API_KEY=your_openai_api_key
4. Initialize Pinecone Index
   Use the provided helper.py functions to upload medical document embeddings into Pinecone.
5. Run the Flask App
   bash
   python app.py
6. Navigate to http://localhost:8080 in your browser to interact with the chatbot.

**How It Works**:

**Backend Flow**
1. PDF Loading: Reads and processes PDF documents into text chunks.
2. Embeddings: Generates vector representations of text using Hugging Face.
3. Storage: Stores embeddings in Pinecone for quick retrieval.
4. Query Processing:
  a. Retrieves relevant document chunks based on similarity.
  b. Generates responses using LLM and the retrieved context.

**Frontend Flow**
1. User inputs a message in the chat interface.
2. Flask processes the request, retrieves relevant context, and generates a response.
3. Response is displayed in the chat interface dynamically using AJAX.

**Technologies Used**:

1. Flask: For backend server and API routing.
2. LangChain: Orchestrates the retrieval and generation logic.
3. Hugging Face: Provides embeddings for document vectorization.
4. Pinecone: Vector database for embedding storage and retrieval.
5. Bootstrap: For responsive chat interface design.

**Deployment**:

This project can be deployed locally or on cloud platforms (e.g., AWS, Google Cloud, Heroku). Ensure your API keys are securely stored in environment variables.

**Future Improvements**:

Add user authentication for personalized experiences.
Expand to support multi-language queries.
Incorporate advanced LLMs for more nuanced responses.
