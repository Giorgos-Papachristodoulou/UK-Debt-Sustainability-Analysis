# UK Debt Sustainability Analysis

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.11](https://img.shields.io/badge/python-3.11-blue.svg)](https://www.python.org/downloads/)

Replication code for **"Debt Sustainability in the United Kingdom: A Comprehensive Econometric Assessment Post UK Autumn Budget 2025"** by Papachristodoulou, Keshari, and Michaelides (2025).

## Paper Abstract

This paper presents a comprehensive debt sustainability analysis for the United Kingdom, incorporating data from the November 2025 Budget. We employ debt dynamics decomposition, Blanchard r−g analysis, Bohn fiscal reaction function tests, and Monte Carlo simulations with fat-tailed distributions. Key findings include a negative Bohn coefficient (β = −0.048) and identification of the 25% index-linked gilt share as a unique vulnerability.

## Quick Start
```bash
# Clone the repository
git clone [https://github.com/yourusername/uk-debt-sustainability-analysis.git](https://github.com/Giorgos-Papachristodoulou/UK-Debt-Sustainability-Analysis
)
cd uk-debt-sustainability-analysis

# Create environment
pip install -r requirements.txt

# Run main analysis
python src/main.py

# Generate all figures
python src/visualization.py
```

## Repository Structure

| Directory | Description |
|-----------|-------------|
| `src/` | Core Python modules for analysis |
| `data/` | Raw and processed datasets |
| `notebooks/` | Jupyter notebooks for exploration |
| `paper/` | PDF of the paper and figures |
| `results/` | Output tables and figures |

## Key Results

| Finding | Value | Source |
|---------|-------|--------|
| Bohn coefficient (β) | −0.048*** | Table 3 |
| P(debt > 100% GDP) baseline | 14% | Table 5 |
| P(debt > 100% GDP) historical | 100% | Table 5 |
| ILG sensitivity (Year 5) | £7.9bn per 1pp RPI | OBR ready reckoners |

## Data Sources

- **ONS**: Public Sector Finances (monthly, 1946–2024)
- **DMO**: Gilt market data, Debt Management Report 2025-26
- **OBR**: Economic and Fiscal Outlook (November 2025)
- **Bank of England**: Interest rates, yield curves

## Citation
```bibtex
@article{papachristodoulou2025ukdebt,
  title={Debt Sustainability in the United Kingdom: A Comprehensive Econometric Assessment Post UK Autumn Budget 2025},
  author={Papachristodoulou, Giorgos and Keshari, Aaisha and Michaelides, Alex},
  journal={Working Paper},
  institution={Imperial College Business School},
  year={2025}
}
```

## License

This project is licensed under the MIT License - see [LICENSE](LICENSE) for details.

## Contact
For questions about the code: [g.papachristodoulou@outlook.com or gp422@ic.ac.uk]

For questions about the code: [your.email@imperial.ac.uk]
