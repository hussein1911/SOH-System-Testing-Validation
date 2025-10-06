# QA: SOH-System-Testing-Validation
This repository implements a Python-based validation framework which is a signal validation pipeline used for Electric Vehicle (EV) battery State-of-Health (SoH) verification to test through it the system testing functionality:

It performs automatic alignment between real and emulated battery signals using optimal lag estimation, resampling, and interpolation, then detects discrepancies through amplitude and sample-rate checks.

Includes visual comparison plots and structured test reports for regression validation and HiL analysis.


## ✨ Features
- **Numeric + datetime alignment** of original vs emulated signals
- **Resampling & interpolation** to common index
- **Optimal lag estimation** (scalar optimization + xcorr baseline)
- **Failure modes**:
  - signal existence
  - **time-delta / sample-rate** differences
  - amplitude offset/factor/cutoff (configurable thresholds)
- **Publication-quality plots** for reviews and reports
- Minimal **CLI** and example notebook

## 🧩 Signals (typical)
`VOLTAGE, CURRENT, MILEAGE, SPEED, IGNITION, SOC_DISPLAY, SOC_REAL`

The original project was tested and managed using **YouTrack** for agile tracking and **TestRail** for test case management.


## 📁 Project Structure
ev-soh-signal-validation/
├─ src/
│  └─ sohval/
│     ├─ __init__.py
│     ├─ alignment.py
│     ├─ lag.py
│     ├─ checks.py
│     ├─ plots.py
│     ├─ types.py
│     └─ pipeline.py
├─ examples/
│  ├─ demo_notebook.ipynb
│  ├─ sample_original.csv
│  └─ sample_emulated.csv
├─ tests/
│  ├─ test_alignment.py
│  ├─ test_lag.py
│  └─ test_checks.py
├─ .github/workflows/
│  └─ ci.yml
├─ README.md
├─ pyproject.toml
├─ requirements.txt
├─ .gitignore
├─ LICENSE
└─ CONTRIBUTING.md
