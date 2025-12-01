# SIABench 🚀

Welcome to the **SIABench** repository! This benchmark is designed for **Security Incident Analysis** tasks, encompassing various cybersecurity investigation domains such as **Memory Forensics, Malware Analysis, Network Forensics, and more.**

## Overview

SIABench consists of two main components:

- **Part I: SIA Tasks** - Simulates the in-depth investigation process of SIA tasks with **25 unique security scenarios** containing **229 investigative questions** in total
- **Part II: Alert Triage** - Includes true and false positives for evaluating classification tasks with **135 alert scenarios** and **135 questions** in total (for the time being, only the alerts generated from CIC-IDS2017 network traffic are included in this repo).

We evaluate different LLMs with our dataset using the [🤖 SIABench Agent].

---

## 📊 Performance Evaluation on SIA Dataset

### Summary Results

| Model | Fully Solved Scenarios (FS) | Overall Solving Percentage (%) |
|-------|-----------------------------|---------------------------------|
| Claude-4.5-Sonnet | 8/25 | 81.7% |
| GPT-5 | 5/25 | 80.7% |
| Claude-3.5-Sonnet | 4/25 | 71.03% |
| GPT-4.0 | 3/25 | 57.93% |
| DeepSeek-Reasoner | 1/25 | 49.33% |
| Gemini1.5-pro | 1/25 | 41.61% |
| OpenAI-o3-mini | 1/25 | 41.1% |
| GPT-4.0mini | 1/25 | 32.53% |
| Llama3.1-405B | 0/25 | 23.65% |
| Llama3.1-70B | 0/25 | 16.53% |
| Llama3.1-8B | 0/25 | 7.03% |

### Detailed Results by Category

<details>
<summary>📊 Click to view the detailed breakdown by category and difficulty</summary>

| Model | NF-E (3S) | NF-M (4S) | NF-H (1S) | MF-E (4S) | MF-M (2S) | MF-H (1S) | MA-E (2S) | MA-M (3S) | MA-H (1S) | MS-E (3S) | MS-M (1S) | MS-H | 🌟**Overall** |
|-------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|-----------|------|----------------|
| **Llama3.1-8B** | 0/3 (8.33%) | 0/4 (0%) | 0/1 (0%) | 0/4 (2.27%) | 0/2 (0%) | 0/1 (0%) | 0/2 (25%) | 0/3 (0%) | 0/1 (0%) | 0/3 (27.5%) | 0/1 (9.09%) | — | **0/25 (7.03%)** |
| **Llama3.1-70B** | 0/3 (17.5%) | 0/4 (15.08%) | 0/1 (0%) | 0/4 (14.09%) | 0/2 (5%) | 0/1 (0%) | 0/2 (26.67%) | 0/3 (6.67%) | 0/1 (8.33%) | 0/3 (47.78%) | 0/1 (9.09%) | — | **0/25 (16.53%)** |
| **Llama3.1-405B** | 0/3 (31.79%) | 0/4 (19.07%) | 0/1 (10%) | 0/4 (24.09%) | 0/2 (5%) | 0/1 (0%) | 0/2 (43.33%) | 0/3 (10.26%) | 0/1 (16.67%) | 0/3 (53.33%) | 0/1 (9.09%) | — | **0/25 (23.65%)** |
| **GPT-4.0** | 0/3 (64.05%) | 0/4 (43.17%) | 0/1 (40%) | 1/4 (61.47%) | 0/2 (60%) | 0/1 (33.33%) | 1/2 (80%) | 0/3 (58.97%) | 0/1 (16.67%) | 1/3 (84.72%) | 0/1 (36.36%) | — | **3/25 (57.93%)** |
| **GPT-4.0mini** | 0/3 (29.29%) | 0/4 (26.49%) | 0/1 (20%) | 0/4 (33.14%) | 0/2 (18.33%) | 0/1 (0%) | 0/2 (73.33%) | 0/3 (18.46%) | 0/1 (16.67%) | 1/3 (58.33%) | 0/1 (36.36%) | — | **1/25 (32.53%)** |
| **Gemini1.5-pro** | 0/3 (62.98%) | 0/4 (31.79%) | 0/1 (20%) | 0/4 (33.35%) | 0/2 (31.67%) | 0/1 (6.67%) | 0/2 (73.33%) | 0/3 (25.13%) | 0/1 (16.67%) | 1/3 (72.22%) | 0/1 (45.45%) | — | **1/25 (41.61%)** |
| **DeepSeek-Reasoner** | 0/3 (70.12%) | 0/4 (36.29%) | 0/1 (30%) | 0/4 (50.88%) | 0/2 (38.33%) | 0/1 (26.67%) | 1/2 (70%) | 0/3 (48.72%) | 0/1 (33.33%) | 0/3 (61.67%) | 0/1 (36.36%) | — | **1/25 (49.33%)** |
| **OpenAI-o3-mini** | 0/3 (72.14%) | 0/4 (41.91%) | 0/1 (40%) | 0/4 (31.24%) | 0/2 (15%) | 0/1 (13.33%) | 0/2 (53.33%) | 0/3 (25.13%) | 0/1 (25%) | 1/3 (63.89%) | 0/1 (36.36%) | — | **1/25 (41.1%)** |
| **Claude-4.5-Sonnet** | 0/3 (87.74%) | 1/4 (86.12%) | 1/1 (100%) | 2/4 (86.74%) | 1/2 (85%) | 0/1 (33.33%) | 0/2 (81.67%) | 1/3 (80.51%) | 0/1 (41.67%) | 2/3 (94.44%) | 0/1 (54.55%) | — | **8/25 (81.7%)** |
| **GPT-5** | 1/3 (92.5%) | 0/4 (84.92%) | 0/1 (90%) | 2/4 (86.04%) | 0/2 (81.67%) | 0/1 (26.67%) | 1/2 (91.67%) | 0/3 (76.41%) | 0/1 (41.67%) | 1/3 (86.11%) | 0/1 (63.64%) | — | **5/25 (80.7%)** |

</details>

### Legend

- **FS** = Fully Solved Scenario
- **PS** = Partially Solved Scenarios (Average Percentage)
- **S** = Scenarios, **Q** = Questions

**Category Abbreviations:**
- **MF** = Memory Forensics
- **MA** = Malware Analysis
- **NF** = Network Forensics
- **MS** = Miscellaneous

**Difficulty Levels:**
- **E** = Easy
- **M** = Medium
- **H** = Hard

---

## 🔬 Optimized Performance with Model Combinations

While individual models show varying performance across different scenarios, our analysis reveals that **strategic model combination** can significantly improve overall performance. Different models excel at different types of security investigation tasks, and leveraging their complementary strengths leads to better results.

### 🎯 Ensemble Analysis: DeepSeek-Reasoner & o3-mini

We conducted a comprehensive ensemble analysis combining **DeepSeek-Reasoner** and **o3-mini** to explore different optimization strategies:

#### Individual Baseline Performance
- **DeepSeek-Reasoner**: 48.03% (110/229 questions)
- **o3-mini**: 40.61% (93/229 questions)

#### Oracle Performance (Theoretical Upper Bound)
When at least one model answers correctly: **58.52% (134/229 questions)**

This represents a **+10.48% improvement** over the best individual model, demonstrating significant complementary capabilities:
- Both models correct: 69 questions (30.13%)
- Only o3-mini correct: 24 questions (10.48%)
- Only DeepSeek correct: 41 questions (17.90%)
- Both models incorrect: 95 questions (41.48%)

#### Practical Optimization Strategies

**1. Scenario-Based Routing (Best: 51.97%)**

Select the optimal model for each security scenario type:
- **o3-mini excels at**: PsExec (71.43%), HawkEye (66.67%), Network Forensics scenarios
- **DeepSeek-Reasoner excels at**: Malware Analysis (Ramnit 50%, XLM_Macro 46.15%), Obfuscated code (80%), Port scanning (80%), Tomcat exploitation (87.5%)

**2. Task Category-Based Routing (49.78%)**

Route questions based on investigation domain:
- **Network Forensics** → o3-mini (54.02% vs 49.43%)
- **Malware Analysis** → DeepSeek-Reasoner (50.00% vs 30.43%)
- **Memory Forensics** → DeepSeek-Reasoner (41.67% vs 25.00%)
- **Miscellaneous** → DeepSeek-Reasoner (52.78% vs 47.22%)

**3. Difficulty-Based Routing (48.03%)**

All difficulty levels favor DeepSeek-Reasoner:
- Easy questions: 61.11% vs 52.22%
- Medium questions: 43.14% vs 36.27%
- Hard questions: 29.73% vs 24.32%

### 📊 Performance Comparison Summary

| Strategy | Performance | Improvement |
|----------|-------------|-------------|
| **Oracle (Either correct)** | 58.52% | +10.48% |
| **Scenario-Based Ensemble** | 51.97% | +3.93% |
| **Task Category Ensemble** | 49.78% | +1.75% |
| **Difficulty-Based Ensemble** | 48.03% | +0.00% |
| DeepSeek-Reasoner (single) | 48.03% | baseline |
| o3-mini (single) | 40.61% | -7.42% |

### 💡 Key Insights

1. **Complementary Strengths**: The 10.48% oracle improvement shows significant non-overlapping capabilities between models
2. **Scenario-Specific Excellence**: Different models excel at different attack types and investigation scenarios
3. **Practical Gains**: Scenario-based routing achieves 75% of the theoretical oracle improvement with practical implementation
4. **Domain Specialization**: o3-mini shows strength in network analysis, while DeepSeek-Reasoner excels at malware and memory forensics

---

## 📊 Performance Evaluation on Alert Triaging Dataset

> **📢 Note:** The TII-SRC-23 dataset will be uploaded soon!

### TII-SRC-23 Dataset (50 TP and 50 FP)

| Model | True Positives (TP) | False Positives (FP) | Accuracy |
|-------|---------------------|----------------------|----------|
| GPT-5 | 48/50 (96.00%) | 50/50 (100.00%) | 98.00% |
| Claude-4.5-Sonnet | 50/50 (100.00%) | 46/50 (92.00%) | 96.00% |
| DeepSeek-Reasoner | 47/50 (94.00%) | 42/50 (84.00%) | 89.00% |
| GPT-4.0mini | 43/50 (86.00%) | 32/50 (64.00%) | 75.00% |

### CIC-IDS2017 Dataset (5 TP and 30 FP)

| Model | True Positives (TP) | False Positives (FP) | Accuracy |
|-------|---------------------|----------------------|----------|
| GPT-5 | 4/5 (80.00%) | 30/30 (100.00%) | 97.14% |
| Claude-4.5-Sonnet | 4/5 (80.00%) | 27/30 (90.00%) | 88.57% |
| DeepSeek-Reasoner | 4/5 (80.00%) | 26/30 (86.67%) | 85.71% |
| GPT-4.0mini | 4/5 (80.00%) | 14/30 (46.67%) | 51.43% |

---

## 🏆 Leaderboard

**📊 [View Interactive Leaderboard](https://llm-leaderboard-f4z.pages.dev/)**

Explore detailed performance metrics and comparisons across all models on our interactive leaderboard! 🚀

---

## 🧠 Model Integrations

### ✅ Evaluated Models

SIA Agent has been tested and integrated with **11 popular LLMs**:

| Model | Provider | API Documentation |
|-------|----------|-------------------|
| Claude-4.5-Sonnet | Anthropic | [Claude API](https://docs.anthropic.com/en/docs/about-claude/models/all-models) |
| GPT-5 | OpenAI | [OpenAI API](https://platform.openai.com/docs/overview) |
| Claude-3.5-Sonnet | Anthropic | [Claude API](https://docs.anthropic.com/en/docs/about-claude/models/all-models) |
| GPT-4.0 | OpenAI | [OpenAI API](https://platform.openai.com/docs/overview) |
| DeepSeek-Reasoner | DeepSeek | [DeepSeek API](https://www.deepseek.com/en) |
| Gemini1.5-pro | Google | [Google Gemini API](https://ai.google.dev/) |
| OpenAI-o3-mini | OpenAI | [OpenAI API](https://platform.openai.com/docs/overview) |
| GPT-4.0mini | OpenAI | [OpenAI API](https://platform.openai.com/docs/overview) |
| Llama3.1-8B | Meta | [Fireworks API](https://fireworks.ai/models) |
| Llama3.1-70B | Meta | [Fireworks API](https://fireworks.ai/models) |
| Llama3.1-405B | Meta | [Fireworks API](https://fireworks.ai/models) |

---

## 📂 Repository Structure

```plaintext
SIABench/
├── SIA_Dataset/                    # Contains JSON files with SIA scenarios
│   ├── SIA_Dataset.md             # Dataset structure and format documentation
│   └── [scenario files...]        # JSON files with security scenarios
├── Alert_Triaging_Dataset/         # Contains JSON files with Alert triaging scenarios
│   ├── Alert_Triaging_Dataset.md  # Dataset structure and format documentation
│   └── [scenario files...]        # JSON files with security scenarios
├── ETHICS.md                       # Ethics statement and responsible use guidelines
└── README.md                       # This file
```

### 📋 Dataset Documentation

For detailed information about the SIA and Alert Triaging dataset structure, format, and examples, please refer to:
- **[SIA_Dataset.md](./SIA_Dataset/SIA_Dataset.md)** - Complete documentation of the SIA dataset structure, question types, and data format
- **[Alert_Triaging_Dataset.md](./Alert_Triaging_Dataset/Alert_Triaging_Dataset.md)** - Complete documentation of the Alert Triaging dataset structure, question types, and data format

### 🛡️ Ethics and Responsible Use

Please review our **[Ethics Statement](./ETHICS.md)** which covers:
- Data compliance and curation practices
- Risk assessment and mitigation strategies
- Responsible use guidelines for researchers and practitioners

---

## 🌟 Acknowledgments

- The [LangChain](https://www.langchain.com/) community
- Security researchers who continue to push boundaries in automated incident analysis

---
