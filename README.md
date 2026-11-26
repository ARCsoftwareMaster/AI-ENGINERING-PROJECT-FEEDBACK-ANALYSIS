# Project Feedback Analyzer

Project Feedback Analyzer is a Python research assistant that combines an Anthropic language model with web search, Wikipedia, and file-saving tools. It uses LangChain to turn a research query into structured output containing the topic, summary, sources, and tools used.

> This repository currently runs a demonstration research query and writes structured results to the console.

## Features

- AI-powered research through Anthropic Claude
- DuckDuckGo web search
- Wikipedia article retrieval
- Structured Pydantic response validation
- Research results saved to a text file
- Automatic loading of environment variables with `python-dotenv`

## Technology Stack

- Python 3.12+
- LangChain and LangChain Community
- Anthropic Claude
- Pydantic
- DuckDuckGo Search
- Wikipedia API

## Project Structure

```text
.
|-- main.py
|-- tool.py
|-- requirements.txt
|-- pyproject.toml
|-- src/
|   `-- project_feedback_analyzer/
|       `-- __init__.py
`-- README.md
```

- `main.py` creates the Claude model, research prompt, parser, agent, and agent executor.
- `tool.py` defines the web search, Wikipedia, and text file-saving tools.
- `pyproject.toml` contains package metadata and the Python 3.12+ requirement.
- `src/project_feedback_analyzer/__init__.py` contains the package entry point.

## Prerequisites

- Python 3.12 or newer
- An Anthropic API key
- Internet access for web search and Wikipedia

## Installation

Clone the repository and enter its directory:

```bash
git clone <repository-url>
cd "Project Feedback Analyzer"
```

Create and activate a virtual environment.

### Windows

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Configuration

Create a `.env` file in the project root:

```env
ANTHROPIC_API_KEY=your_anthropic_api_key
```

Keep API keys out of source control and do not commit the `.env` file.

## Usage

Run the demonstration application:

```bash
python main.py
```

The agent currently sends this question to the model:

```text
What is the capital of France?
```

The response is validated against the following Pydantic model:

```python
class ResearchResponse(BaseModel):
    topic: str
    summary: str
    sources: list[str]
    tools_used: list[str]
```

## Saving Results

The `save_text_to_file` tool appends formatted research output to `research_output.txt` by default:

```python
save_to_file(data, filename="research_output.txt")
```

Each saved entry includes a timestamp and the supplied research data.

## Development

Install the project dependencies and run Python directly:

```bash
pip install -r requirements.txt
python main.py
```

The project can also be used as a Python package, where `project-feedback-analyzer` currently prints a placeholder message.

## Security

- Never add API keys to `main.py`, `tool.py`, or commit history.
- Add `.env` and local virtual environments to `.gitignore`.
- Review output and external sources before using research in production or published work.

## License

Add a license file before publishing this project as open source.
