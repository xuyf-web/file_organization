# Default file organization

This file provides guidance to user when building a new project.

## Project Overview

This is a Python research project organized with experiment-driven development. The structure follows:
- `configs/` - Centralized project configuration files (such as naming conventions, directory paths, etc.)
- `experiments/` - Versioned experiment folders, named as "$n$.EYYYYMMDD_name" (e.g., `1.E20250822_alpha/`). Each experiment contains: `src/`, `tests/`, `logs/`, `figures/`, `cache/`, `tmp/`
- `utils/` - General-purpose tools and scripts shared across experiments
- `data/` - Directories for both raw and processed datasets
- `model/` - Model files and related resources (e.g., WRF-Chem, FLEXPART)
- `reports/` - Analytical reports and research findings
- `docs/` - Manuscript drafts, documentation, and publication materials
- `archive/` - Storage for deprecated or archived files

## Development Commands

Since this uses `pyproject.toml`, standard Python tools apply:

**Package Management:**
```bash
# Install package in development mode
conda install -e .

# Install with development dependencies
conda install -e ".[dev]"
```

**Testing:**
```bash
# Run tests with pytest (if configured)
pytest

# Run specific experiment tests
pytest experiments/1.E20250822_alpha/tests/
```

**Code Quality:**
```bash
# Format code with black
black .

# Sort imports with isort
isort .

# Type checking with mypy
mypy .

# Linting with ruff
ruff check .
```

## Experiment Structure

Each experiment directory follows this pattern:
- `src/` - Source code for the experiment
- `tests/` - Contains jupyter notebook files
- `logs/` - Experiment running logs
- `figures/` - Generated visualizations
- `cache/` - Cached computation results
- `tmp/` - Temporary files and data

## Common Tasks

1. **Create new experiment:** Copy an existing experiment directory and update the version number
2. **Run experiment:** Navigate to experiment directory and execute main scripts
3. **Analyze results:** Check logs/ and figures/ directories for outputs
4. **Document findings:** Update reports/ and manuscripts/ with results

## Data Organization

- `data/raw/` - Original, immutable data
- `data/processed/` - Cleaned and transformed data
- Always preserve raw data - processing should be reproducible

## Best Practices

- Keep experiments isolated and reproducible
- Document data processing steps in reports/
- Version models in model/ directory
- Use consistent naming conventions across experiments

## Default File structure
```bash
.
├── archive/
├── configs/
├── data
│   ├── processed
│   └── raw
├── docs
│   ├── manuscripts/
│   └── publications/
├── experiments
│   └── 1.E20250822_alpha
│       ├── cache/
│       ├── figures/
│       ├── logs/
│       ├── README.md
│       ├── src/
│       ├── tests/
│       └── tmp/
├── .git/
├── .gitignore
├── LICENSE
├── logs/
├── model/
├── pyproject.toml
├── .python-version
├── README.md
├── reports/
└── utils/

30 directories, 23 files
```