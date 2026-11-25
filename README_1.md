# Project Feedback Analyzer

Project Feedback Analyzer is a research assistant powered by LangChain that uses
Anthropic Claude and OpenAI GPT models. It researches a user's question with web
search and Wikipedia tools, structures the responses with Pydantic, and can
optionally save the results to a text file.

## Features

- Run research queries through separate Anthropic Claude and OpenAI GPT agents
- Search the web with DuckDuckGo
- Retrieve summary information from Wikipedia
- Save research results to `research_output.txt`
- Validate structured responses with Pydantic
- Output the topic, summary, sources, and tools used

## Output Format

Research responses contain the following fields:

```json
{
  "topic": "Research topic",
  "summary": "Research summary",
  "sources": ["Sources used"],
  "tools_used": ["Tools used"]
}
```

## Requirements

- Python 3.15 or newer
- Anthropic API key
- OpenAI API key
- Internet connection

## Installation

1. Navigate to the project directory:

```bash
cd "Project Feedback Analyzer"
```

2. Create and activate a virtual environment:

```bash
python -m venv .venv
```

Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

Windows Command Prompt:

```cmd
.venv\Scripts\activate.bat
```

3. Install the packages:

```bash
pip install -r requirements.txt
```

Or, if you use uv:

```bash
uv sync
```

4. Create a `.env` file in the project root and add the API keys:

```env
ANTHROPIC_API_KEY=your_anthropic_api_key
OPENAI_API_KEY=your_openai_api_key
```

## Usage

Start the application:

```bash
python main.py
```

Enter a research question at the terminal prompt:

```text
What can i help you research?
```

The program generates two responses, one from Claude and one from OpenAI. When
an agent uses a research tool to save results, the data is appended to
`research_output.txt`.

## Available Tools

| Tool | Description |
| --- | --- |
| `search` | Searches the web with DuckDuckGo |
| `wiki_tool` | Retrieves relevant content from Wikipedia |
| `save_to_file` | Saves research output to a text file with a timestamp |

## Project Structure

```text
Project Feedback Analyzer/
├── main.py
├── tools.py
├── README.md
├── pyproject.toml
├── requirements.txt
├── uv.lock
└── src/
    └── project_feedback_analyzer/
        └── __init__.py
```

## Main Files

- `main.py`: Initializes the models, prompt, agents, and output parser.
- `tools.py`: Defines the web search, Wikipedia, and file-saving tools.
- `pyproject.toml`: Contains project dependencies and package configuration.
- `requirements.txt`: Lists Python dependencies for installation.

## Notes

- Do not add API keys to source code or version control.
- `main.py` uses `claude-3-5-sonnet-20241022` for Claude and `gpt-4o` for OpenAI.
- Internet-based tools require network and API access.
