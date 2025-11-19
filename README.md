# Ollama Coder

A powerful CLI coding assistant powered by Ollama, designed to be a local alternative to Claude Code.

## Features

- **Local Inference**: Runs entirely on your machine using Ollama.
- **Plan-Execute Workflow**: Creates detailed plans for complex tasks and asks for approval before execution.
- **File Operations**: Read, write, edit, delete, copy, and move files.
- **Code Search**: Search for patterns within files or across directories.
- **Git Integration**: Manage version control directly from the assistant.
- **Package Management**: Install and list Python packages.
- **Command Execution**: Run shell commands safely.

## Prerequisites

1. **Ollama**: Install Ollama from [ollama.com](https://ollama.com).
2. **Models**: Pull the required models (default is `qwen3:4b`).
   ```bash
   ollama pull qwen3:4b
   ```

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd ollama-coder
   ```

2. Create a virtual environment:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   # OR manually
   pip install ollama typer rich prompt_toolkit
   ```

## Usage

## Usage

Using the virtual environment:
```bash
.venv/bin/python -m ollama_coder.main start
```

Specify a different model:
```bash
.venv/bin/python -m ollama_coder.main start --model llama3
```

## Workflow

### Planning Mode
For complex requests (e.g., "Build a Flask app"), the assistant will:
1. **Analyze** your request.
2. **Propose a Plan** with step-by-step actions.
3. **Wait for Approval** (type "yes" or "proceed").
4. **Execute** the plan autonomously.

### Direct Mode
For simple requests (e.g., "List files", "Read main.py"), the assistant executes immediately.

## Available Tools

| Category | Tools |
|----------|-------|
| **File Ops** | `list_files`, `read_file`, `write_file`, `edit_file`, `delete_file`, `copy_file`, `move_file` |
| **Search** | `search_file`, `grep_search`, `find_files` |
| **Git** | `git_status`, `git_diff`, `git_log`, `git_add`, `git_commit` |
| **System** | `run_command`, `install_package`, `list_installed_packages` |

## Examples

**Create a new project:**
> "Create a directory called 'my-app' and add a main.py that prints hello world"

**Refactor code:**
> "Search for all print statements in src/ and replace them with logging"

**Git workflow:**
> "Check git status, add all changes, and commit with message 'Initial commit'"
