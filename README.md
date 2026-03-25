# Google ADK sample agents

Small examples built with the [Google Agent Development Kit (ADK)](https://google.github.io/adk-docs/) and Gemini (`gemini-2.5-flash`).

## Layout

| Directory          | Description |
|--------------------|-------------|
| `basic_agent/`     | Single-tool agent with a stub `get_current_time` function. |
| `multi_tool_agent/` | Weather and time tools (demo data for New York; time uses real timezone data). |

Each agent folder contains `__init__.py` and `agent.py` with a `root_agent` object, which is what the ADK CLI expects.

## Prerequisites

- Python 3.10+ (this repo was set up with 3.13)
- A [Google AI API key](https://aistudio.google.com/apikey) for the Gemini API (when not using Vertex AI)

## Setup

```bash
cd /path/to/google-adk
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install google-adk
```

## Configuration

Copy or edit the `.env` file inside the agent you want to run (`basic_agent/.env` or `multi_tool_agent/.env`):

- `GOOGLE_GENAI_USE_VERTEXAI=0` — use the Gemini API (not Vertex AI).
- `GOOGLE_API_KEY=` — set your API key.

Alternatively, export these variables in your shell before running `adk`.

## Run the Web UI

From this repository root, start the dev server so you can pick an agent in the browser:

```bash
adk web .
```

Then open the URL shown in the terminal (default host `127.0.0.1`).

## Run the terminal UI

Interactive CLI for one agent at a time:

```bash
adk run basic_agent
# or
adk run multi_tool_agent
```

Run these commands from the repository root (parent of `basic_agent` and `multi_tool_agent`).

## More ADK commands

- `adk --help` — list commands (`api_server`, `deploy`, `eval`, etc.)

## License

Sample code is for learning; refer to [Google ADK licensing](https://github.com/google/adk-python) for the SDK terms.
