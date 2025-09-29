# Zero-Cost Deep Research Setup

## Configuration Summary

This fork is configured for completely free operation using:

- **LLM**: Ollama with Llama 3.1 (local, no API costs)
- **Search**: DuckDuckGo (free, no API key required)
- **Platform**: LangGraph Studio (free local development)

## Environment Variables

Create a `.env` file with:

```bash
# Zero-cost configuration using local LLM and free search
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
GOOGLE_API_KEY=
TAVILY_API_KEY=
LANGSMITH_API_KEY=
LANGSMITH_PROJECT=
LANGSMITH_TRACING=false

# Local LLM configuration (Ollama)
OLLAMA_BASE_URL=http://localhost:11434
LOCAL_LLM=llama3.1

# DuckDuckGo is used by default (no API key required)
# Search will fall back to DuckDuckGo when Tavily is not configured

# Only necessary for Open Agent Platform
SUPABASE_KEY=
SUPABASE_URL=
GET_API_KEYS_FROM_CONFIG=false
```

## Prerequisites

1. **Ollama installed and running**: `ollama serve`
2. **Llama 3.1 model downloaded**: `ollama pull llama3.1`
3. **Python 3.11+** with dependencies: `uv sync`

## Usage

```bash
# Start development environment
cd ~/projects/open_deep_research
source .venv/bin/activate
langgraph dev --allow-blocking

# Direct model testing
ollama run llama3.1 "Your research query here"
```

## Git Configuration

- **Origin**: Your fork (cordlesssteve/open_deep_research)
- **Upstream**: Original repo (langchain-ai/open_deep_research) - PUSH DISABLED
- **Safety**: Cannot accidentally push to main repository

## Cost Analysis

- **Setup cost**: $0
- **Operating cost**: $0 per research session
- **Rate limits**: DuckDuckGo free tier (generous)
- **Privacy**: Complete (all processing local)

## Installation Date

Installed: 2025-09-28