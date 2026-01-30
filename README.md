# Purple Agents - Performance Comparison Suite

Three Purple Agent implementations demonstrating different levels of code quality and observability, designed for the [Green Comtrade Bench](https://github.com/YongXie-ICMM/green-comtrade-bench-enhanced) evaluation system.

## 🎯 Overview

This repository contains three Purple Agent variants that achieve different scores on the Green Agent benchmark, primarily differing in their logging structure and observability features.

## 📊 Performance Results

| Version | Score | Average | Key Feature |
|:---|:---:|:---:|:---|
| **V1 - High Performance** | 527.4/700 | **75.3%** | Full structured logging |
| **V2 - Medium Performance** | 495.0/700 | **70.7%** | Partial structured logging |
| **V3 - Baseline** | 464.5/700 | **66.4%** | Basic logging |

**Score Gap:** V1 outperforms V3 by **62.9 points** (9% difference)

## 📁 Repository Structure

```
purple-agents/
├── v1_high_performance/     # 75.3% - Production-ready
├── v2_medium_performance/   # 70.7% - Testing-ready
├── v3_baseline/             # 66.4% - Reference implementation
└── README.md
```

## 🚀 Quick Start

### Prerequisites

- Python 3.8+
- Running Green Comtrade Bench mock service
- Docker (optional, for full environment)

### Running an Agent

```bash
# Choose a version
cd v1_high_performance

# Run a single task
python3 run.py --task-id T1_single_page \
               --mock-url http://localhost:8000 \
               --output-dir ./output
```

## 🔍 Version Comparison

### V1 - High Performance (75.3%)
- ✅ Full structured logging: `[task_id=X] [page=Y] [request=Z] [complete=true]`
- ✅ Detailed performance metrics
- ✅ Complete error statistics
- **Observability:** 15/15 points

### V2 - Medium Performance (70.7%)
- ✅ Partial structured logging: `[task_id=X] [page=Y] INFO: Message`
- ✅ Basic traceability
- ⚠️ Missing request field
- **Observability:** ~9/15 points

### V3 - Baseline (66.4%)
- ⚠️ Basic logging: `INFO: Message`
- ✅ Core functionality complete
- ⚠️ No structured fields
- **Observability:** ~3.75/15 points

## 📈 Score Breakdown

### By Task (100 points each)

| Task | V1 | V2 | V3 |
|:---|:---:|:---:|:---:|
| T1_single_page | 75.3 | 71.2 | 67.2 |
| T2_multi_page | 75.3 | 71.2 | 67.2 |
| T3_duplicates | 75.3 | 71.2 | 65.8 |
| T4_rate_limit_429 | 78.4 | 71.7 | 67.8 |
| T5_server_error_500 | 76.7 | 71.7 | 67.8 |
| T6_page_drift | 72.0 | 67.8 | 63.9 |
| T7_totals_trap | 74.4 | 70.2 | 64.8 |

## 🛠️ Technical Details

### Common Features
- ✅ Correct pagination logic
- ✅ Exponential backoff retry
- ✅ Deduplication and sorting
- ✅ Totals row filtering
- ✅ Complete output files

### Key Differences
| Feature | V1 | V2 | V3 |
|:---|:---:|:---:|:---:|
| Structured logging | Full | Partial | None |
| Request tracking | ✅ | ❌ | ❌ |
| Completion markers | ✅ | ❌ | ❌ |

## 📚 Related Resources

- **Green Comtrade Bench:** https://github.com/YongXie-ICMM/green-comtrade-bench-enhanced
- **Scoring Documentation:** See Green Agent README

## 📄 License

MIT License

---

**Note:** These agents have identical core functionality. Choose based on your observability requirements.
