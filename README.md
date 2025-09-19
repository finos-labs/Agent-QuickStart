# Financial AI Agent Quickstart

## Table of Contents

- [Financial AI Agent Quickstart](#financial-ai-agent-quickstart)
  - [Table of Contents](#table-of-contents)
  - [About The Project](#about-the-project)
  - [Prerequisites](#prerequisites)
  - [Environment Setup](#environment-setup)
  - [Installation](#installation)
  - [Directory Structure](#directory-structure)
  - [Setup](#setup)
  - [Input Data](#input-data)
  - [Usage Example](#usage-example)
    - [SEC 10-K \& 10-Q Filings Analysis with LlamaIndex](#sec-10-k--10-q-filings-analysis-with-llamaindex)
    - [Stock Data and Sentiment Analysis with Agno](#stock-data-and-sentiment-analysis-with-agno)
  - [Roadmap](#roadmap)
    - [✅ Completed](#-completed)
    - [🚧 In Development](#-in-development)
    - [🎯 Future Enhancements](#-future-enhancements)
  - [Contributing](#contributing)
  - [License](#license)
  - [Acknowledgments](#acknowledgments)

## About The Project

This project provides a template and best practice for developing multi-agent AI workflows, leveraging various agentic frameworks, modern LLMs and AI evaluation strategies. It demonstrates:

- Multi-agent orchestration strategies 
- Integration with local and cloud LLMs, including SOTA (OpenAI / Google Gemini) and Open Weight models (Llama, Qwen, DeepSeek)
- RAG pipeline for document-based retrieval
- Evaluation metrics for agent orchestration, tool execution and RAG quality

## Prerequisites

Before starting, ensure you have:

- **Python 3.11.9**
- **uv**: High-performance Python package manager ([uv installation](https://github.com/astral-sh/uv))
- **Google Gemini API Key**: Provided by the FINOS Team and set as `GOOGLE_API_KEY` in your environment
- **Tavily Search API Key**: [Get from Tavily](https://tavily.com/) and set as `TAVILY_SEARCH_API_KEY`
- **Scaleway GenAI API Key**: Provided by the FINOS team and set as `SCW_SECRET_KEY`
- (Optional) **LM Studio** for local LLM serving ([Download LM Studio](https://lmstudio.ai/))

## Environment Setup

Rename tje `.env.new` file in your project root to `.env` and update with the API Keys provided by the FINOS team.

## Installation

Clone the repo and install dependencies:

```sh
git clone https://github.com/your_username/agent-quickstart.git
cd agent-quickstart
uv sync
```

## Directory Structure

```text
Agent-QuickStart/
├── .env
├── llama_index_agent_example.ipynb
├── main.py
├── data/
│   ├── input/          # Place PDF files here
│   └── output/         # Converted markdown files will be stored here
└── database/
    └── vector_store/   # ChromaDB database will be created here
```

## Setup

- **Local LLM (Optional)**:
  - Install LM Studio
  - Download a compatible model (e.g., qwen3-8b)
  - Start LM Studio server on `http://127.0.0.1:1234/v1`

## Input Data

- Place PDF documents (10K or 10Q reports) to be processed in `data/input/`
- Converted markdown files will be saved in `data/output/`

## Usage Example

We have two agent examples providing a full multi-agent execution workflow.

### SEC 10-K & 10-Q Filings Analysis with LlamaIndex

 The `llama_index_agent_example.ipynb` notebook demonstrates how to:

- Load environment variables
- Convert PDFs to markdown
- Generate vector database
- Query and evaluate RAG pipeline
- Define and run multi-agent workflow
- Leverage DeepEval across the flow execution, with a LLM-as-Judge approach

### Stock Data and Sentiment Analysis with Agno

The `agno_agent_example.ipynb` notebod demonstrates how to:

- Leverage Google Search for web search on recent information to produce sentiment analysis
- Leverage Yahoo Finance for financial data retrieval including historical stock prices and financial ratios
- Define and run multi-agent workflow to produce an analyst report

## Roadmap

### ✅ Completed

- [x] Multi-agent financial analysis workflow (Research → Write → Review)
- [x] RAG pipeline with financial document processing
- [x] Comprehensive AI evaluation metrics (DeepEval integration)
- [x] Real-time quality assessment during agent execution

### 🚧 In Development  

- [ ] **Additional Financial Use Cases**
  - [ ] ESG (Environmental, Social, Governance) analysis agents
  - [ ] Regulatory compliance assessment workflows
  - [ ] Financial risk analysis and stress testing
  - [ ] Market sentiment analysis from earnings calls

### 🎯 Future Enhancements

- [ ] **Advanced Evaluation Strategies**
  - [ ] Custom financial domain evaluation metrics
  - [ ] Bias detection in financial analysis
  - [ ] Hallucination detection for financial facts
  - [ ] Regulatory compliance validation

- [ ] **Multi-Modal Analysis**
  - [ ] Financial chart and graph analysis
  - [ ] Integration with financial data APIs (Bloomberg, Reuters)
  - [ ] Audio analysis of earnings calls

- [ ] **Production Features**
  - [ ] Model performance monitoring and alerts
  - [ ] A/B testing framework for agent improvements
  - [ ] Audit trail and explainability features
  - [ ] Integration with financial data platforms

## Contributing

All commits must be signed with a DCO signature. See [CONTRIBUTING.md](./CONTRIBUTING.md) for details.

```
Signed-off-by: Your Name <your.email@example.com>
```
Add the `-s` flag to your `git commit` to sign automatically.

## License

Distributed under the [Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0).
SPDX-License-Identifier: [Apache-2.0](https://spdx.org/licenses/Apache-2.0)

## Acknowledgments

- [LlamaIndex](https://docs.llamaindex.ai/) - Multi-agent workflow framework and RAG implementation
- [DeepEval](https://github.com/DeepEval/DeepEval) - AI evaluation metrics and testing framework
- [LM Studio](https://lmstudio.ai/) - Local LLM serving platform
- [Tavily](https://tavily.com/) - Web search API for real-time information retrieval
- [ChromaDB](https://www.trychroma.com/) - Vector database for document embedding and retrieval
