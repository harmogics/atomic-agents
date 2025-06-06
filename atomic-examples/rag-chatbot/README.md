# RAG Chatbot

This directory contains the RAG (Retrieval-Augmented Generation) Chatbot example for the Atomic Agents project. This example demonstrates how to build an intelligent chatbot that uses document retrieval to provide context-aware responses using the Atomic Agents framework.

## Features

1. Document Chunking: Automatically splits documents into manageable chunks with configurable overlap
2. Vector Storage: Uses ChromaDB for efficient storage and retrieval of document chunks
3. Semantic Search: Generates and executes semantic search queries to find relevant context
4. Context-Aware Responses: Provides detailed answers based on retrieved document chunks
5. Interactive UI: Rich console interface with progress indicators and formatted output

## Getting Started

To get started with the RAG Chatbot:

1. **Clone the main Atomic Agents repository:**
   ```bash
   git clone https://github.com/BrainBlend-AI/atomic-agents
   ```

2. **Navigate to the RAG Chatbot directory:**
   ```bash
   cd atomic-agents/atomic-examples/rag-chatbot
   ```

3. **Install the dependencies using Poetry:**
   ```bash
   poetry install
   ```

4. **Set up environment variables:**
   Create a `.env` file in the `rag-chatbot` directory with the following content:
   ```env
   OPENAI_API_KEY=your_openai_api_key
   ```
   Replace `your_openai_api_key` with your actual OpenAI API key.

5. **Run the RAG Chatbot:**
   ```bash
   poetry run python rag_chatbot/main.py
   ```

## Components

### 1. Query Agent (`agents/query_agent.py`)
Generates semantic search queries based on user questions to find relevant document chunks.

### 2. QA Agent (`agents/qa_agent.py`)
Analyzes retrieved chunks and generates comprehensive answers to user questions.

### 3. ChromaDB Service (`services/chroma_db.py`)
Manages the vector database for storing and retrieving document chunks.

### 4. Context Provider (`context_providers.py`)
Provides retrieved document chunks as context to the agents.

### 5. Main Script (`main.py`)
Orchestrates the entire process, from document processing to user interaction.

## How It Works

1. The system initializes by:
   - Downloading a sample document (State of the Union address)
   - Splitting it into chunks with configurable overlap
   - Storing chunks in ChromaDB with vector embeddings

2. For each user question:
   - The Query Agent generates an optimized semantic search query
   - Relevant chunks are retrieved from ChromaDB
   - The QA Agent analyzes the chunks and generates a detailed answer
   - The system displays the thought process and final answer

## Customization

You can customize the RAG Chatbot by:
- Modifying chunk size and overlap in `config.py`
- Adjusting the number of chunks to retrieve for each query
- Using different documents as the knowledge base
- Customizing the system prompts for both agents

## Example Usage

The chatbot can answer questions about the loaded document, such as:
- "What were the main points about the economy?"
- "What did the president say about healthcare?"
- "How did he address foreign policy?"

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your enhancements or bug fixes.

## License

This project is licensed under the MIT License. See the [LICENSE](../../LICENSE) file for details.
