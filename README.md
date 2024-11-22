
# ⚕️🩺🥼💉 Medical Chatbot - End-to-End Generative AI Application

This project implements an end-to-end medical chatbot using Flask as the backend framework and a combination of LangChain, Pinecone, and Hugging Face embeddings for natural language processing and retrieval-augmented generation (RAG).

The chatbot is capable of answering user queries by leveraging a retriever-based mechanism for finding relevant context and generating responses using a large language model (LLM).

---

## ✅Features

- **PDF Loading & Text Processing**: Extracts and processes text from medical PDFs for embedding and storage.
- **Pinecone Vector Store**: Stores and retrieves document embeddings for context-based responses.
- **Hugging Face Embeddings**: Utilizes Sentence Transformers for efficient text vectorization.
- **RAG Model**: Combines retrieval and generative capabilities to handle complex queries.
- **Flask Frontend**: Provides an interactive chat UI using HTML, Bootstrap, and AJAX.
- **Customizable LLM**: Supports models like OpenAI's GPT or Llama 2 via LangChain.

---

## 📜Prerequisites

Ensure the following are installed and configured:

1. **Python 3.9 or above.**
   - Create a new virtual environment: `python -m venv newvenv`
   - Activate the virtual environment: 
     - On Windows: `newvenv\Scripts\activate`
     - On macOS/Linux: `source newvenv/bin/activate`
2. **Required Python Libraries**: Install dependencies using `requirements.txt`:
   ```bash
   pip install -r requirements.txt
   ```
3. **Pinecone API Key** and Index setup.
4. **Hugging Face Model**: Use `sentence-transformers/all-MiniLM-L6-v2` for embeddings.
5. **Flask Framework**.
6. **Download the Llama 2 Model**:
   - Model: `llama-2-7b-chat.ggmlv3.q4_0.bin`
   - Link: [Hugging Face - Llama 2](https://huggingface.co/TheBloke/Llama-2-7B-Chat-GGML/tree/main)

---

## 🛠Setup Instructions

### 1. Clone the Repository

```bash
git clone <repository-url>
cd project
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables

Create a `.env` file in the project root:

```plaintext
PINECONE_API_KEY=your_pinecone_api_key
OPENAI_API_KEY=your_openai_api_key
```

### 4. Initialize Pinecone Index

Use the provided `helper.py` functions to upload medical document embeddings into Pinecone.

### 5. Run the Flask App

```bash
python store_index.py
```

### 6. Run the Flask App

```bash
python app.py
```

Navigate to `http://localhost:8080` in your browser to interact with the chatbot.

---

## 🗃️File Structure

```
project/
│
├── app.py                 # Flask application entry point
├── src/
│   ├── helper.py          # PDF processing and embedding functions
│   ├── prompt.py          # Chat prompt templates
│
├── model/
│   ├── llama-2-7b-chat.ggmlv3.q4_0.bin
│
├── static/
│   ├── style.css          # Chat UI styles
│
├── templates/
│   ├── chat.html          # Chat UI template
│
├── requirements.txt       # Required Python libraries
├── .env                   # Environment variables (Pinecone, OpenAI keys)
```

---

## 🤷How It Works

### Backend Flow

1. **PDF Loading**: Reads and processes PDF documents into text chunks.
2. **Embeddings**: Generates vector representations of text using Hugging Face.
3. **Storage**: Stores embeddings in Pinecone for quick retrieval.
4. **Query Processing**:
   - Retrieves relevant document chunks based on similarity.
   - Generates responses using LLM and the retrieved context.

### Frontend Flow

- User inputs a message in the chat interface.
- Flask processes the request, retrieves relevant context, and generates a response.
- Response is displayed in the chat interface dynamically using AJAX.

---

## 🤖Technologies Used

- **Flask**: For backend server and API routing.
- **LangChain**: Orchestrates the retrieval and generation logic.
- **Hugging Face**: Provides embeddings for document vectorization.
- **Pinecone**: Vector database for embedding storage and retrieval.
- **Bootstrap**: For responsive chat interface design.

---

## 🚚Deployment

This project can be deployed locally or on cloud platforms (e.g., AWS, Google Cloud, Heroku). Ensure your API keys are securely stored in environment variables.

---

## 🔜Future Improvements

1. Add user authentication for personalized experiences.
2. Expand to support multi-language queries.
3. Incorporate advanced LLMs for more nuanced responses.

---

## 🤝Acknowledgments

- [LangChain](https://langchain.com/)
- [Pinecone](https://www.pinecone.io/)
- [Hugging Face](https://huggingface.co/)
- [Bootstrap](https://getbootstrap.com/)

---

## ✍️ Author  
Ronak Bansal

---

## 🙌 Contributing  
Feel free to fork this repository, make improvements, and submit a pull request.  

---

## 🐛 Troubleshooting  
If you encounter issues, please create an issue in this repository.  

---

## 📧 Contact  
For inquiries or support, contact [ronakbansal12345@gmail.com].  

