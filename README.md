# Conversational RAG Chatbot with PDF Upload and Chat History

This repository implements a Conversational Retrieval-Augmented Generation (RAG) chatbot using [LangChain](https://github.com/langchain-ai/langchain), [Streamlit](https://streamlit.io/), and PDF document ingestion. Users can upload PDF files, ask questions about their content, and maintain chat history across sessions.

## Features

- **PDF Upload:** Ingest and process PDF documents for context-aware Q&A.
- **Conversational RAG:** Uses chat history to contextualize user queries.
- **Session Management:** Supports multiple chat sessions with persistent history.
- **Embeddings:** Utilizes HuggingFace embeddings for document chunking and retrieval.
- **Vector Store:** Stores document chunks in a Chroma vector database for efficient retrieval.
- **LLM Integration:** Supports GROQ API for LLM-powered responses.
- **Streamlit UI:** Simple web interface for interaction.

## Architecture

- **Document Loader:** Loads PDFs using `PyPDFLoader`.
- **Text Splitter:** Splits documents into chunks with `RecursiveCharacterTextSplitter`.
- **Embeddings:** Generates vector representations using `HuggingFaceEmbeddings`.
- **Vector Store:** Stores and retrieves document chunks via `Chroma`.
- **Retriever:** Retrieves relevant chunks based on user queries.
- **History-Aware Retriever:** Reformulates queries using chat history.
- **QA Chain:** Answers questions using retrieved context and LLM.
- **Session Store:** Maintains chat history per session in Streamlit's `st.session_state`.

## Setup

### Prerequisites

- Python 3.8+
- GROQ API key (for LLM responses)
- HuggingFace token (for embeddings)

### Installation

1. **Clone the repository:**
   ```sh
   git clone https://github.com/<your-username>/<your-repo>.git
   cd <your-repo>
   ```

2. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

3. **Configure environment variables:**
   - Create a `.env` file in the root directory:
     ```
     HF_TOKEN=<your-huggingface-token>
     ```
   - The `.env` file is ignored by git ([.gitignore](.gitignore)).

### Running the App

```sh
streamlit run app.py
```

## Usage

1. **Enter your GROQ API key** in the input field.
2. **Upload a PDF file** using the file uploader.
3. **Start a chat session** by entering a session ID (default is `default_session`).
4. **Ask questions** about the PDF content. The assistant will use both the document and chat history for context.

## File Structure

- [`app.py`](app.py): Main Streamlit application.
- [`requirements.txt`](requirements.txt): Python dependencies.
- [`.env`](.env): Environment variables (not tracked by git).
- [`.gitignore`](.gitignore): Git ignore rules.
- [`.gitattributes`](.gitattributes): Git attributes for text normalization.

## Key Dependencies

- [`langchain`](https://github.com/langchain-ai/langchain)
- [`langchain-community`](https://github.com/langchain-ai/langchain)
- [`langchain-openai`](https://github.com/langchain-ai/langchain)
- [`langchain_core`](https://github.com/langchain-ai/langchain)
- [`streamlit`](https://streamlit.io/)
- [`python-dotenv`](https://github.com/theskumar/python-dotenv)
- [`langchain_chroma`](https://github.com/langchain-ai/langchain)
- [`langchain_groq`](https://github.com/langchain-ai/langchain)
- [`langchain_huggingface`](https://github.com/langchain-ai/langchain)
- [`langchain_text_splitters`](https://github.com/langchain-ai/langchain)

## Security

- **API Keys:** Never commit your `.env` file or API keys to version control.
- **PDFs:** Uploaded PDFs are stored temporarily as `temp.pdf` and processed locally.

## License

Specify your license here (e.g., MIT, Apache 2.0).

## Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you would like to change.

## Contact

For questions, open an issue or contact
