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
./run.sh
```

This opens Jupyter Notebook in your browser. Then:

1. Click **`es_blueprint_poc.ipynb`** to open the notebook
2. Run all cells: `Run` > `Run All Cells` (or `Kernel` > `Restart Kernel and Run All Cells` for a clean run)
3. When prompted for operator intent, type your intent (e.g. `Optimize energy while maintaining throughput above 2 Mbps`).
4. The closed-loop simulation will run — progress is printed in the terminal output below each cell
5. Results are saved to `output/closed_loop_results.png` and `output/closed_loop_log.txt`

## Project Structure

```
es-blueprint-rsg/
├── data/                 # Dataset CSVs (CellReports, UEReports)
├── notebooks/            # Jupyter notebooks
├── output/               # Simulation results (charts, logs)
├── .env.example          # Environment variable template
├── requirements.txt      # Python dependencies
├── setup.sh              # One-time setup script
└── run.sh                # Launch Jupyter Notebook
```
