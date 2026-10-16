# Deep Agents Course

This repository is a hands-on project for learning how to build **Deep Agents** with the `deepagents` library and LangGraph. It includes Jupyter notebooks that explore the concepts step by step and a Streamlit chatbot that brings them together in an interactive demo.

## What we're exploring

The goal is to understand how agents can do more than answer a single prompt. The notebooks and app demonstrate how to:

- Plan and carry out multi-step tasks.
- Use tools, including Tavily web search.
- Manage context with files, `AGENTS.md`, memory, and skills.
- Choose where an agent's files and memory live with different backends.
- Keep conversation state with a checkpointer.
- Delegate focused work to subagents, including a subagent that returns structured results.

## Screenshot

![Deep Agents Chatbot running in Streamlit](<./Screenshot 2026-10-16 at 12.37.36 PM.png>)

## Run the Streamlit app

### Requirements

- Python **3.14 or newer**
- [`uv`](https://docs.astral.sh/uv/) for environment and dependency management
- API keys for the services you use:
  - `OPENAI_API_KEY` for the OpenAI models available in the app.
  - `TAVILY_API_KEY` for web search.

### Setup

From the repository root, sync the project dependencies:

```bash
uv sync
```

Create a `.env` file in the repository root and add your API keys:

```dotenv
OPENAI_API_KEY=your-openai-api-key
TAVILY_API_KEY=your-tavily-api-key
```

Keep `.env` private; do not commit API keys.

### Start the app

```bash
uv run streamlit run streamlit_app.py
```

Streamlit will print a local URL (usually `http://localhost:8501`) to open in your browser. In the sidebar, choose a model and backend, and toggle context loading, skills, or subagents. Enter a prompt in the chat box to try the agent.

Web search requires `TAVILY_API_KEY`. The selected OpenAI model requires `OPENAI_API_KEY`.

## Notebooks

The notebooks under [`src/deepagentcourse/`](./src/deepagentcourse/) provide a learning path through the project:

1. [`1-basicdeep.ipynb`](./src/deepagentcourse/1-basicdeep.ipynb) — Deep Agents basics, models, tools, prompts, and planning.
2. [`2-backend.ipynb`](./src/deepagentcourse/2-backend.ipynb) — State, filesystem, and store backends.
3. [`3-contextengineering.ipynb`](./src/deepagentcourse/3-contextengineering.ipynb) — Context, memory, skills, and related agent configuration.
4. [`4-subagents.ipynb`](./src/deepagentcourse/4-subagents.ipynb) — Delegating work to subagents and structured output.

Open a notebook in VS Code or your Jupyter environment and select the Python environment created by `uv sync`. Some notebook examples also call external model or search services, so set the relevant API keys before running those cells.

## Project layout

```text
.
├── streamlit_app.py                 # Interactive Deep Agents chatbot
├── src/deepagentcourse/              # Learning notebooks and agent resources
│   ├── 1-basicdeep.ipynb
│   ├── 2-backend.ipynb
│   ├── 3-contextengineering.ipynb
│   ├── 4-subagents.ipynb
│   ├── projects/AGENTS.md
│   └── skills/
├── pyproject.toml                    # Project metadata and dependencies
├── requirements.txt
└── uv.lock                           # Locked dependency versions
```