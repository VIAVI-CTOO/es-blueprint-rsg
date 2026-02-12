# ES Blueprint RSG

Prototyping notebooks for ES Blueprint RSG.

> **Note:** This project is only tested with Python 3.9.

## Setup

```bash
./setup.sh
```

This will:
1. Find or install Python 3.9 (via [pyenv](https://github.com/pyenv/pyenv) if needed)
2. Create a `.venv` virtual environment
3. Install all dependencies
4. Register a Jupyter kernel (`es-blueprint-rsg`)
5. Create `.env` from template

After setup, install the internal `viavi` package (authorized access required):

```bash
source .venv/bin/activate
pip install https://<server_ip>/package/adk
```

Then fill in your API keys in `.env`:

| Variable | Description |
|---|---|
| `NVIDIA_API_KEY` | API key for NVIDIA AI endpoints |

## Usage

```bash
source .venv/bin/activate
jupyter notebook notebooks/
```

In the notebook, select kernel **"ES Blueprint RSG"** to use the correct environment.

## Project Structure

```
es-blueprint-rsg/
├── data/                 # Dataset CSVs (CellReports, UEReports)
├── notebooks/            # Jupyter notebooks for prototyping
├── src/                  # Reusable Python modules
├── .env.example          # Environment variable template
├── requirements.txt      # Python dependencies
└── setup.sh              # One-command setup script
```
