# ALPHA: Adaptive Learning via Penalty in Hierarchical Assessment

[![arXiv](https://img.shields.io/badge/arXiv-2601.01320-b31b1b.svg)](https://arxiv.org/abs/2601.01320)
[![PDF](https://img.shields.io/badge/PDF-Download-brightgreen)](https://arxiv.org/pdf/2601.01320)

The first function-level Python benchmark for evaluating LLMs and SAST tools using hierarchically aware, CWE-specific penalties.

## Overview

ALPHA introduces a taxonomy-aware evaluation framework for vulnerability detection that distinguishes between over-generalisation, over-specification, and lateral errors in CWE predictions. This provides more actionable feedback for iterative code correction systems compared to binary classification approaches.

## Key Features

- **Hierarchical Penalty System**: Direction-aware penalties reflecting practical differences in diagnostic utility
- **Function-level Analysis**: Python vulnerability detection at appropriate granularity for LLM context windows
- **Consistency Evaluation**: Multi-run analysis assessing reliability for iterative feedback systems
- **Comprehensive Comparison**: Benchmarks 7 LLMs and 2 SAST tools (CodeQL, Semgrep)

## Datasets

- **SecurityEval**: 121 vulnerable Python functions across multiple CWE abstraction levels
- **SVEN**: 342 Python samples with base-level CWE labels

## Results

### ALPHA Scores

Lower scores indicate better performance. LLM results show mean ± standard deviation across 3 runs.

| Model | SVEN | SecurityEval |
|-------|------|--------------|
| **LLMs** | | |
| Qwen2.5-Coder-32B | 574.7 ± 42.4 | 617.8 ± 18.5 |
| Devstral-24B | 695.1 ± 71.2 | 578.5 ± 27.4 |
| Phi4-14B | 646.4 ± 47.4 | 797.4 ± 13.0 |
| Qwen2.5-Coder-7B | 753.2 ± 39.5 | 921.5 ± 15.1 |
| Llama3.1-8B | 813.5 ± 51.0 | 856.5 ± 42.7 |
| Mistral-7B | 923.3 ± 77.0 | 1156.9 ± 32.0 |
| DeepSeek-Coder-6.7B | 2557.0 ± 194.3 | 1228.5 ± 60.9 |
| **SAST Tools** | | |
| CodeQL (Confidence) | 5981.9 | 1261.0 |
| CodeQL (Any Match) | 5981.9 | 1212.9 |
| Semgrep (Confidence) | 3663.5 | 1307.6 |
| Semgrep (Any Match) | 3562.7 | 1307.6 |

## Main Findings

- LLMs substantially outperform SAST tools on ALPHA scores
- SAST tools demonstrate higher precision when detections occur (coverage-precision trade-off)
- Prediction consistency varies dramatically across models (8.26%-81.87% agreement)
- Qwen2.5-Coder-32B and Devstral-24B achieve best performance and consistency

## Citation

If you use ALPHA in your research, please cite:

```bibtex
@article{alpha2026,
  title={Adaptive Hierarchical Evaluation of LLMs and SAST tools for CWE Prediction in Python},
  author={Adnan, Muntasir and Kuhn, Carlos C. N.},
  journal={arXiv preprint arXiv:2601.01320},
  year={2026}
}
```