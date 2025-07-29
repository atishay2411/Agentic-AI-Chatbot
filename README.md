# Agentic AI Chatbots – End-to-End Application with LangGraph, Groq LLM, and Streamlit

This project is a production-ready implementation of multi-agent AI chatbots using LangGraph, LangChain, and Groq LLMs. It includes several intelligent workflows, including web-augmented chat, real-time AI news summarization, and basic conversational agents—all accessible through a user-friendly Streamlit interface.

## Features

- Basic Chatbot: A stateless language model-based conversational agent.
- Chatbot with Web Search: Integrates external web search results using Tavily API.
- AI News Summary Bot: Fetches and summarizes the latest AI news articles using a multi-node LangGraph workflow.

## Tech Stack

- LangGraph: Graph-based agent orchestration.
- LangChain: LLM framework integration.
- Groq LLM: High-speed inference using LLaMA-3 and Gemma models.
- Streamlit: Front-end interface for interaction.
- Tavily API: Live search tool for RAG and knowledge augmentation.
- FAISS: Local vector storage (prepared for extensibility).

## Architecture Overview

```
User Input (via Streamlit)
        |
        v
LangGraph Runtime Engine
        |
        |-- Basic Chatbot Node
        |-- Chatbot with Tool Node (Tavily Search)
        \-- AI News Pipeline:
            |-- Fetch News via Tavily
            |-- Summarize via Groq LLM
            \-- Save Markdown Report
```

## Project Structure

```
project/
|
├── app.py                           # Entry point to Streamlit app
├── requirements.txt
├── AINews/                          # Markdown summaries saved here
│   └── daily_summary.md
├── src/
│   └── langgraphagenticai/
│       ├── main.py                 # Initializes app
│       ├── graph/                  # LangGraph builders
│       ├── nodes/                  # Agent nodes (chatbot, news, etc.)
│       ├── LLMS/                   # Groq LLM integration
│       ├── tools/                  # Tavily integration
│       ├── state/                  # State definitions for LangGraph
│       └── ui/streamlitui/         # Streamlit interface logic
```

## Setup Instructions

### 1. Clone the repository

```bash
git clone https://github.com/yourusername/agentic-ai-chatbots.git
cd agentic-ai-chatbots
```

### 2. Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Set required environment variables

You must provide API keys for Groq and Tavily. Set them as environment variables or directly through the UI.

```bash
export GROQ_API_KEY=your_groq_api_key
export TAVILY_API_KEY=your_tavily_api_key
```

Alternatively, add them to `.streamlit/secrets.toml` if using Streamlit Secrets.

### 5. Run the application

```bash
streamlit run app.py
```

## Use Cases

- **Basic Chatbot**: Simple conversational flow using Groq LLM.
- **Chatbot With Web**: Answers enhanced with real-time web search from Tavily.
- **AI News**: Select a time frame (daily, weekly, monthly) and generate summarized reports saved in markdown format.

## API References

- Groq API: https://console.groq.com/
- Tavily API: https://app.tavily.com/home

## License

This project is released under the MIT License.
