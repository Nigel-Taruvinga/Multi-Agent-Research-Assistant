# Multi-Agent Investment Research Assistant

An autonomous multi-agent AI system that produces structured investment research reports by coordinating three specialized AI agents using CrewAI, LangChain, and FAISS.

## Live Demo

https://huggingface.co/spaces/NigelTaruvinga/multi-agent-research

## Architecture

Three agents collaborate sequentially:

1. Web Research Agent -- retrieves real-time company data via Wikipedia REST API
2. Knowledge Base Agent -- queries a local FAISS vector store using semantic search
3. Senior Analyst Agent -- synthesises findings into a structured investment report

## Tech Stack

Python, CrewAI, LangChain, FAISS, sentence-transformers, Llama 3.1 via Cerebras, REST APIs, Gradio

## Frameworks Used

- CrewAI -- multi-agent orchestration and sequential task delegation
- LangChain -- document processing, text splitting, and embeddings
- FAISS -- vector store for semantic similarity search
- sentence-transformers -- all-MiniLM-L6-v2 embedding model (384-dim)
- Cerebras Llama 3.1 -- LLM for research synthesis (free API)
- Wikipedia REST API -- real-time web data retrieval
- Gradio -- interactive web interface

## How It Works

1. User enters a company name
2. Agent 1 fetches real-time data from Wikipedia REST API
3. Agent 2 retrieves relevant context from FAISS knowledge base using cosine similarity
4. Agent 3 synthesises both sources into a structured 200-word report

## Report Structure

Each generated report contains three sections:
1. Company Overview
2. Financial Highlights
3. Investment Considerations

## Setup

1. Install dependencies:
   pip install langchain langchain-openai langchain-community langchain-text-splitters crewai litellm faiss-cpu sentence-transformers requests python-dotenv gradio cerebras-cloud-sdk

2. Create a .env file with your Cerebras API key:
   CEREBRAS_API_KEY=your-key-here

3. Run all cells in Multi_Agent_Research_Assistant.ipynb

4. Launch the Gradio app from the final cell
