# 🔍 RAG Architecture with LangChain & DeepSeek R1 Integration

A Retrieval-Augmented Generation (RAG) pipeline built with LangChain and powered by DeepSeek R1 — enabling accurate, context-aware responses grounded in custom document knowledge bases.

## Overview

This project implements a full RAG (Retrieval-Augmented Generation) architecture that combines the reasoning power of DeepSeek R1 with LangChain's orchestration framework. Instead of relying solely on a model's pre-trained knowledge, the pipeline retrieves relevant context from a document store at query time, dramatically improving accuracy and reducing hallucinations.

## How RAG Works

```
User Query
    │
    ▼
Query Embedding
    │
    ▼
Vector Store Retrieval (find relevant document chunks)
    │
    ▼
Context + Query → Prompt Construction
    │
    ▼
DeepSeek R1 LLM (generates grounded response)
    │
    ▼
Final Answer
```

## Features

- **Document Ingestion** – Load and parse PDF, TXT, or other document formats
- **Text Chunking** – Splits documents into semantically meaningful chunks
- **Vector Embeddings** – Converts chunks into dense vector representations
- **Semantic Search** – Retrieves the most relevant chunks for any given query
- **DeepSeek R1 Integration** – Uses DeepSeek R1 as the reasoning LLM backbone
- **LangChain Orchestration** – Manages the full retrieval and generation pipeline
- **Conversational Memory** – Maintains context across multi-turn conversations (if enabled)

## Project Files

```
RAG-Architecture-with-LangChain-and-DeepSeek--R1-Integration/
│
├── DeepSeek RAG.ipynb    # Main notebook with full RAG pipeline implementation
└── README.md             # Project documentation
```

## Tech Stack

| Component | Tool |
|---|---|
| **LLM** | DeepSeek R1 |
| **Orchestration** | LangChain |
| **Embeddings** | HuggingFace / OpenAI Embeddings |
| **Vector Store** | FAISS / Chroma |
| **Document Loader** | LangChain Document Loaders |
| **Text Splitter** | RecursiveCharacterTextSplitter |
| **Environment** | Jupyter Notebook |

## Getting Started

### Prerequisites

```bash
pip install langchain langchain-community langchain-core faiss-cpu chromadb \
            sentence-transformers openai pypdf python-dotenv
```

### API Setup

Create a `.env` file in the project root with your DeepSeek API key:

```env
DEEPSEEK_API_KEY=your_api_key_here
```

### Running the Notebook

1. Clone the repository:
   ```bash
   git clone https://github.com/GayathriChilukala/RAG-Architecture-with-LangChain-and-DeepSeek--R1-Integration.git
   cd RAG-Architecture-with-LangChain-and-DeepSeek--R1-Integration
   ```

2. Launch the notebook:
   ```bash
   jupyter notebook "DeepSeek RAG.ipynb"
   ```

3. Follow the cells in order to:
   - Load and chunk your documents
   - Generate and store embeddings in the vector store
   - Run semantic retrieval on user queries
   - Generate grounded answers via DeepSeek R1

## Why DeepSeek R1?

DeepSeek R1 is a high-performance open-weight reasoning model known for its strong performance on complex reasoning, coding, and analytical tasks — making it an excellent backbone for a RAG system where logical synthesis of retrieved context is critical.

## RAG vs. Standard LLM

| Feature | Standard LLM | RAG + DeepSeek R1 |
|---|---|---|
| Knowledge Source | Pre-trained weights only | External documents + weights |
| Hallucination Risk | Higher | Significantly reduced |
| Custom Knowledge | Not supported | Fully supported |
| Up-to-date Info | Limited by cutoff | Real-time via document store |
| Explainability | Low | High (citable sources) |

## Use Cases

- **Enterprise Q&A** – Query internal documents, reports, or knowledge bases
- **Research Assistant** – Retrieve and synthesize information from academic papers
- **Customer Support** – Answer questions grounded in product documentation
- **Legal & Compliance** – Search and reason over contracts and policy documents
- **Personalized Chatbots** – Build domain-specific conversational agents

## Author

**Gayathri Chilukala**  
[GitHub Profile](https://github.com/GayathriChilukala)

## License

This project is open-source and available for educational and research purposes.
