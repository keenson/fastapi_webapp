# FastAPI Blog

A modern, high-performance blog web application built with **FastAPI**. This  project scaffolded is with FastAPI 0.136.3 and Python 3.12+, designed to serve as a foundation for a full-featured blogging platform with RESTful APIs.


## Quick Start

### Prerequisites

- Python 3.12 or newer
- [uv](https://docs.astral.sh/uv/) (recommended) or pip

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd fastapi_blog

# Create and activate a virtual environment (if not using uv)
python -m venv .venv
source .venv/bin/activate  # Linux/macOS

# Install dependencies
uv sync                   # using uv
# OR
pip install -e .          # using pip
```

### Run the Development Server

```bash
uv run fastapi dev main.py
# OR
fastapi dev main.py
```

The server will start at `http://localhost:8000`.

Visit:
- **API Docs (Swagger):** `http://localhost:8000/docs`
- **Alternative Docs (ReDoc):** `http://localhost:8000/redoc`
- **OpenAPI Schema:** `http://localhost:8000/openapi.json`

### Run the Entry Point Directly

```bash
uv run python main.py
# Output: Hello from fastapi-blog!
```

## Project Structure

```
fastapi_blog/
├── .git/                  # Git repository data
├── .gitignore             # Git ignore rules
├── .python-version        # Python version specification (3.12)
├── .venv/                 # Virtual environment (local, not tracked)
├── main.py                # Application entry point
├── pyproject.toml         # Project metadata and dependencies
├── README.md              # This file
└── uv.lock                # Locked dependency versions (uv)
```

## Available Commands

| Command                          | Description                              |
|----------------------------------|------------------------------------------|
| `uv run python main.py`          | Run the entry point (prints greeting)    |
| `uv run fastapi dev main.py`     | Start the FastAPI dev server             |
| `uv run fastapi run main.py`     | Start the FastAPI production server      |
| `uv sync`                        | Install/update dependencies from lock    |
| `uv add <package>`               | Add a new dependency                     |
| `uv lock`                        | Update the lock file                     |




