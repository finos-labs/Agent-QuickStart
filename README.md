# Financial AI Agent Quickstart

## Table of Contents

- [Financial AI Agent Quickstart](#financial-ai-agent-quickstart)
  - [Table of Contents](#table-of-contents)
  - [About The Project](#about-the-project)
  - [Prerequisites](#prerequisites)
  - [Environment Setup](#environment-setup)
  - [Installation](#installation)
  - [Directory Structure](#directory-structure)
  - [LLM Setup](#llm-setup)
  - [Input Data](#input-data)
  - [Usage Example](#usage-example)
  - [Development Setup](#development-setup)
  - [Roadmap](#roadmap)
  - [Contributing](#contributing)
  - [License](#license)
  - [Acknowledgments](#acknowledgments)

## About The Project

This project provides a robust template for developing multi-agent AI workflows, leveraging LlamaIndex and modern LLMs. It demonstrates:

- Multi-agent orchestration with `AgentWorkflow`
- Integration with local and cloud LLMs (Google Gemini, LM Studio, etc.)
- RAG pipeline for document-based retrieval
- Evaluation metrics for agent and RAG quality
- Modular directory structure for extensibility


## Prerequisites

Before starting, ensure you have:

- **Google Gemini API Key**: [Get from Google AI Studio](https://aistudio.google.com/app/apikey) and set as `GOOGLE_API_KEY` in your environment
- **Tavily Search API Key**: [Get from Tavily](https://tavily.com/) and set as `TAVILY_SEARCH_API_KEY`
- **Python 3.10+**
- **uv**: High-performance Python package manager ([uv installation](https://github.com/astral-sh/uv))
- (Optional) **LM Studio** for local LLM serving ([Download LM Studio](https://lmstudio.ai/))

## Environment Setup

Create a `.env` file in your project root:

```.env
GOOGLE_API_KEY=your_google_api_key_here
TAVILY_SEARCH_API_KEY=your_tavily_api_key_here
```

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

## LLM Setup

- **Google Gemini**: Set up API key as above
- **Local LLM (Optional)**:
  - Install LM Studio
  - Download a compatible model (e.g., qwen3-8b)
  - Start LM Studio server on `http://127.0.0.1:1234/v1`

## Input Data

- Place PDF documents to be processed in `data/input/`
- Converted markdown files will be saved in `data/output/`
- Example: `internet-history-09.pdf`

## Usage Example

See `llama_index_agent_example.ipynb` for a full workflow:

- Load environment variables
- Convert PDFs to markdown
- Generate vector database
- Query and evaluate RAG pipeline
- Define and run multi-agent workflow

## Development Setup

Install development dependencies and run tests:

```sh
uv sync
# (Add test instructions if available)
```

## Roadmap

- [x] Multi-agent workflow example
- [x] RAG pipeline integration
- [x] LLM evaluation metrics
- [ ] Add more agent templates
- [ ] Expand documentation and examples

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

- [LlamaIndex Documentation](https://docs.llamaindex.ai/en/stable/examples/llm/openai/)
- [LM Studio](https://lmstudio.ai/)
- [DeepEval](https://github.com/DeepEval/DeepEval)
