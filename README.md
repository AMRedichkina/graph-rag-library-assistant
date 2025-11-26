# Library ChatBot — Graph-RAG Conversational Agent for Book Discovery

**Library ChatBot** is an AI-powered librarian assistant that answers questions strictly based on data stored in a **Neo4j knowledge graph**.  
It combines **ReAct-style agent reasoning**, **semantic vector search**, **Cypher-based fact retrieval**, and a clean **Streamlit conversational UI** to help users explore books, authors, genres, and plots.

This project demonstrates a production-grade architecture for building **domain-restricted, hallucination-resistant** AI assistants.

---

## ✨ Key Features

### 🔹 Domain-Bound Conversational Agent
The chatbot answers **only** using information stored in Neo4j.  
It refuses out-of-domain questions and never relies on pre-trained model knowledge.

### 🔹 ReAct Agent with Multiple Tools
The system uses LangChain’s ReAct agent equipped with three specialized tools:

| Tool | Description |
|------|-------------|
| **General Chat** | Handles lightweight book conversations when no structured search is required. |
| **Books Plot Search** | Vector-based plot search using embeddings to identify books by description. |
| **Book Information (Cypher)** | Detailed fact lookup using Cypher queries (author, genre, year, ratings, recommendations). |

The agent chooses when to invoke a tool using the ReAct flow (`Thought → Action → Observation → Final Answer`).

## Technology Stack

- **Streamlit** 
- **Neo4j**
- **OpenAI API**
- **Langchain**
- **Docker**

## Setup

### Prerequisites

- Docker
- Docker Compose
- An OpenAI API key
- Neo4j database credentials

### Environment Variables

Create a `.env` file in the root directory and update it with your credentials:

```plaintext
NEO4J_URI=neo4j://<host>:<port>
NEO4J_USERNAME=<username>
NEO4J_PASSWORD=<password>
OPENAI_API_KEY=<your_openai_api_key>
EMBEDDING_MODEL=<your_preferred_openai_model>
DIMENSIONS=<embedding_dimensions>
SIMILARITY_FUNCTION=<similarity_function>
```

![Demo of Library ChatBot](./assets/demo.png)


[View Presentation PDF](./assets/Presentation_1.pdf)



