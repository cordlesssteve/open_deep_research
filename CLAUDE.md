# Project CLAUDE.md

## ═══════════════════════════════════════════════════════
## GLOBAL CONFIGURATION (Auto-Inherited - Do Not Edit Here)
## ═══════════════════════════════════════════════════════
## These are imported from ~/.claude/config/*
## To update global behavior, edit those files directly
## Changes will automatically apply to all projects using this template
##
## NOTE: Using tilde paths (~/.claude/...) works across all project locations
## Alternative formats: relative (@../../../.claude/...) or absolute (@/home/user/...)

@~/.claude/config/intellectual-honesty.md
@~/.claude/config/verification-protocols.md
@~/.claude/config/file-organization.md
@~/.claude/config/backup-systems.md
@~/.claude/config/mcp-discovery-protocol.md

## ═══════════════════════════════════════════════════════
## PROJECT-SPECIFIC CONFIGURATION
## ═══════════════════════════════════════════════════════
## Edit below this line for project-specific instructions

## Project Context
- **Name:** [Project Name]
- **Type:** [Web App / CLI Tool / Game / Library / MCP Server / etc.]
- **Status:** [Active / Archived / Prototype / Paused]
- **Tech Stack:** [Languages, frameworks, tools]
- **Repository:** [Git repo URL if applicable]

## 🚨 MANDATORY READING ORDER 🚨
Before starting ANY development work, Claude MUST read these files in order:

1. **CURRENT_STATUS.md** - Current reality and what's actually done
2. **ACTIVE_PLAN.md** - What we're currently executing (if exists)
3. Only then reference other documentation for context

## Project-Specific Guidelines

### Directory Structure
**Directory Tree:** Use `.directory_tree.txt` in project root for complete structure
**NEVER regenerate directory tree** - read existing file to save context tokens

### Development Workflow
[Add project-specific development workflow here]

### Testing Requirements
[Add project-specific testing requirements here]

### Deployment Process
[Add deployment instructions if applicable]

## Architecture Overview
[Add architecture notes, key components, design decisions]

## External Dependencies
[List critical external services, APIs, databases]

## Common Tasks
[Add frequently used commands, scripts, or procedures]

## Known Issues / Gotchas
[Document any quirks, workarounds, or things to watch out for]## Project Description
Open Deep Research is a configurable, fully open-source deep research agent that works across multiple model providers, search tools, and MCP (Model Context Protocol) servers. It enables automated research with parallel processing and comprehensive report generation.

## Repository Structure

### Root Directory
- `README.md` - Comprehensive project documentation with quickstart guide
- `pyproject.toml` - Python project configuration and dependencies
- `langgraph.json` - LangGraph configuration defining the main graph entry point
- `uv.lock` - UV package manager lock file
- `LICENSE` - MIT license
- `.env.example` - Environment variables template (not tracked)

### Core Implementation (`src/open_deep_research/`)
- `deep_researcher.py` - Main LangGraph implementation (entry point: `deep_researcher`)
- `configuration.py` - Configuration management and settings
- `state.py` - Graph state definitions and data structures  
- `prompts.py` - System prompts and prompt templates
- `utils.py` - Utility functions and helpers
- `files/` - Research output and example files

### Legacy Implementations (`src/legacy/`)
Contains two earlier research implementations:
- `graph.py` - Plan-and-execute workflow with human-in-the-loop
- `multi_agent.py` - Supervisor-researcher multi-agent architecture
- `legacy.md` - Documentation for legacy implementations
- `CLAUDE.md` - Legacy-specific Claude instructions
- `tests/` - Legacy-specific tests

### Security (`src/security/`)
- `auth.py` - Authentication handler for LangGraph deployment

### Testing (`tests/`)
- `run_evaluate.py` - Main evaluation script configured to run on deep research bench
- `evaluators.py` - Specialized evaluation functions  
- `prompts.py` - Evaluation prompts and criteria
- `pairwise_evaluation.py` - Comparative evaluation tools
- `supervisor_parallel_evaluation.py` - Multi-threaded evaluation

### Examples (`examples/`)
- `arxiv.md` - ArXiv research example
- `pubmed.md` - PubMed research example
- `inference-market.md` - Inference market analysis examples

## Key Technologies
- **LangGraph** - Workflow orchestration and graph execution
- **LangChain** - LLM integration and tool calling
- **Multiple LLM Providers** - OpenAI, Anthropic, Google, Groq, DeepSeek support
- **Search APIs** - Tavily, OpenAI/Anthropic native search, DuckDuckGo, Exa
- **MCP Servers** - Model Context Protocol for extended capabilities

## Development Commands
- `uvx langgraph dev` - Start development server with LangGraph Studio
- `python tests/run_evaluate.py` - Run comprehensive evaluations
- `ruff check` - Code linting
- `mypy` - Type checking

## Configuration
All settings configurable via:
- Environment variables (`.env` file)
- Web UI in LangGraph Studio
- Direct configuration modification

Key settings include model selection, search API choice, concurrency limits, and MCP server configurations.
