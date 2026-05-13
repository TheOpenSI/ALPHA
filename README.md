# ALPHA: Adaptive Learning via Penalty in Hierarchical Assessment

[![IEEE](https://img.shields.io/badge/DOI-0085CA?style=for-the-badge&logo=doi&logoColor=white)](https://ieeexplore.ieee.org/document/11498216)
[![arXiv](https://img.shields.io/badge/arXiv-B31B1B?style=for-the-badge&logo=arxiv&logoColor=white)](https://arxiv.org/abs/2601.01320)

The first function-level Python benchmark for evaluating LLMs and SAST tools using hierarchically aware, CWE-specific penalties. 
<b>The paper had been published at the IEEE conference proceedings of 2026 International Conference on Advances in Artificial Intelligence and Machine Learning (AAIML).</b>

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
@INPROCEEDINGS{11498216,
  author={Adnan, Muntasir and Kuhn, Carlos C. N.},
  booktitle={2026 International Conference on Advances in Artificial Intelligence and Machine Learning (AAIML)}, 
  title={Adaptive Hierarchical Evaluation of LLMs and SAST tools for CWE Prediction in Python}, 
  year={2026},
  volume={},
  number={},
  pages={193-200},
  keywords={Feedback;Circuits;Filtering;Filters;Integrated circuits;Feedback loop;Radio access networks;Regional area networks;Protocols;Communication systems;Vulnerability Detection;Large Language Models;Static Analysis;CWE Classification;Hierarchical Evaluation},
  doi={10.1109/AAIML67890.2026.11498216}}
```