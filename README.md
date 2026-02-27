# Enhanced Text Analysis with Apache Beam

A text analysis pipeline built with **Apache Beam** that performs word frequency analysis, bigram extraction, and word length distribution on Shakespeare's *Romeo and Juliet*. The project uses Beam's DirectRunner for local execution and includes data visualizations with Matplotlib.

## Features

- **Word Frequency Analysis** — Counts word occurrences with case normalization and stop word filtering (60+ English and Shakespearean stop words)
- **Bigram Analysis** — Extracts and ranks consecutive word pairs to reveal common phrases and collocations
- **Word Length Distribution** — Analyzes vocabulary complexity by computing word length frequencies
- **Visualizations** — Generates bar charts for top words, top bigrams, and word length distribution
- **Summary Statistics** — Reports unique word count, total occurrences, average word length, and most common terms

## Tech Stack

- Python 3.11
- Apache Beam (DirectRunner)
- Matplotlib
- urllib (for dataset download)

## Project Structure

```
.
├── enhanced_beam_text_analysis.ipynb   # Main notebook with all pipelines
├── data/                               # Downloaded text data (auto-created)
├── outputs/                            # Pipeline output files and plots (auto-created)
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.11 (recommended for best Beam compatibility)
- pip

### Setup

1. **Clone the repository**

   ```bash
   git clone https://github.com/Malav2002/MLOpsApacheBeamLab.git
   cd MLOpsApacheBeamLab
   ```

2. **Create and activate a virtual environment**

   ```bash
   python3.11 -m venv .venv
   source .venv/bin/activate        # macOS/Linux
   # .venv\Scripts\activate          # Windows
   ```

3. **Install dependencies**

   ```bash
   pip install --upgrade pip setuptools
   pip install "apache-beam==2.60.0" matplotlib ipykernel
   ```

4. **Register the Jupyter kernel**

   ```bash
   python -m ipykernel install --user --name mlops --display-name "MLOps"
   ```

### Running the Notebook

1. Open `enhanced_beam_text_analysis.ipynb` in Jupyter or VS Code
2. Select the **MLOps** (or `.venv`) kernel
3. Run all cells sequentially — the notebook will:
   - Download *Romeo and Juliet* from Project Gutenberg
   - Run three Apache Beam pipelines (word count, bigrams, word length)
   - Generate visualizations and summary statistics

### Output

After execution, the `outputs/` directory will contain:

- `word_counts-00000-of-*` — Word frequency results
- `bigram_counts-00000-of-*` — Bigram frequency results
- `word_length_dist-00000-of-*` — Word length distribution
- `analysis_plots.png` — Visualization charts

## Pipelines Overview

### Pipeline 1 — Word Count
Reads text → extracts words → lowercases → filters stop words → counts frequencies

### Pipeline 2 — Bigram Count
Reads text → extracts consecutive word pairs → counts pair frequencies

### Pipeline 3 — Word Length Distribution
Reads text → extracts words → maps to word length → counts per length category

## Author

**Malav Patel** — [GitHub](https://github.com/Malav2002)
