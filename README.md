# Data Science & LLM Technical Assessment

Joseph Farrington, June 2025

This repository contains my solution to the Data Science & LLM Technical Assessment. The code for both parts of the exercise is included in the Jupyter Notebook `solution.ipynb`. I provide instructions below for re-running the analysis on Google Colab or locally. The short report is included in this repository as `report.pdf`.

## Run on Google Colab

<a target="_blank" href="https://colab.research.google.com/github/joefarrington/hospital_stay_exercise/blob/main/solution.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

1. Use the button above the open the notebook in Colab.

2. Check that the notebook is running on a GPU instance (Runtime -> Change runtime type, then check that one of the GPU options is selected)

3. Run the cells to repeat the analysis. The first cell in the notebook will identify that it is being run on Colab and automatically install the Python dependencies, install Ollama, download the LLM model weights and start serving the LLM.

## Run locally

The terminal commands below assume that uv is used to manage Python dependencies. See the [uv installation guide](https://docs.astral.sh/uv/getting-started/installation/).

Running the named entitiy recognition pipeline locally requires [Ollama](https://ollama.com/) and it is recommended that a Nividia GPU is available for LLM inference.

1.  Clone the repository, create a new Python environment and install Python dependencies

```bash
# Clone the repository
git clone https://github.com/joefarrington/hospital_stay_exercise
# Move into the newly created directory
cd hospital_stay_exercise
# Create a new Python virtual environment
uv venv
# Activate the virtual environment
source .venv/bin/activate
# Install the Python dependencies
uv sync
```

2. Install Ollama, start Ollama, and download the required LLM weights

```bash
# Install ollama
curl -fsSL https://ollama.com/install.sh | sh
# Start ollama in a background process
ollama serve &
# Download open source model weights (2GB)
ollama pull llama3.2:3b
```

3. Start a Jupyter Notebook server and open the UI in a brower window

```bash
# Start Jupyter Notebook
jupyter notebook
```

4. Open `solution.ipynb` in the Jupyter Notebook UI and run the cells to repeat the analysis.
