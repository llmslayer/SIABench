# SIABench 🚀

Welcome to the **SIABench** repository! This benchmark is designed for **Security Incident Analysis** tasks, encompassing various cybersecurity investigation domains such as **Memory Forensics, Malware Analysis, Network Forensics, and more.**

## Overview

SIABench consists of two main components:

- **Part I: SIA Tasks** - Simulates the in-depth investigation process of SIA tasks with **25 unique security scenarios** containing **229 investigative questions** in total
- **Part II: Alert Triage** - Includes true and false positives for evaluating classification tasks with **35 alert scenarios** and **35 questions** in total

We evaluate different LLMs with our dataset using the [🤖 SIABench Agent].

---

## 📊 Performance Evaluation on SIA Dataset

### Summary Results

| Model | Fully Solved Scenarios (FS) | Overall Solving Percentage (%) |
|-------|-----------------------------|---------------------------------|
| Claude-3.5-Sonnet | 4/25 | 68.29% |
| GPT-4o | 3/25 | 55.69% |
| DeepSeek-Reasoner | 1/25 | 47.43% |
| o3-mini | 1/25 | 40.08% |
| Gemini-1.5-pro | 1/25 | 39.51% |
| GPT-4o-mini | 1/25 | 31.27% |
| LLaMA-3.1-405B | 0/25 | 22.45% |
| LLaMA-3.1-70B | 0/25 | 15.59% |
| LLaMA-3.1-8B | 0/25 | 6.75% |

### Detailed Results by Category

<details>
<summary>📊 Click to view the detailed breakdown by category and difficulty</summary>

| Model | MF-E (4S, 29Q) | MF-M (2S, 16Q) | MF-H (1S, 15Q) | MA-E (2S, 11Q) | MA-M (3S, 23Q) | MA-H (1S, 12Q) | NF-E (3S, 25Q) | NF-M (4S, 52Q) | NF-H (1S, 10Q) | MS-E (3S, 25Q) | MS-M (1S, 11Q) | 🌟**Overall** |
|-------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|----------------|
| **Claude-3.5-Sonnet** | **1/4** (76.73%) | **0/2** (65.00%) | **0/1** (53.33%) | **1/2** (80.00%) | **1/3** (78.97%) | **0/1** (16.67%) | **0/3** (82.98%) | **0/4** (60.05%) | **0/1** (60.00%) | **1/3** (83.33%) | **0/1** (72.72%) | **4/25 (68.29%)** |
| **GPT-4o** | **1/4** (61.47%) | **0/2** (60.00%) | **0/1** (33.33%) | **1/2** (80.00%) | **0/3** (58.97%) | **0/1** (16.67%) | **0/3** (64.05%) | **0/4** (43.17%) | **0/1** (40.00%) | **1/3** (84.72%) | **0/1** (36.36%) | **3/25 (55.69%)** |
| **DeepSeek-Reasoner** | **0/4** (50.88%) | **0/2** (38.33%) | **0/1** (26.67%) | **1/2** (70.00%) | **0/3** (48.71%) | **0/1** (33.33%) | **0/3** (70.12%) | **0/4** (36.29%) | **0/1** (30.00%) | **0/3** (61.67%) | **0/1** (36.36%) | **1/25 (47.43%)** |
| **o3-mini** | **0/4** (31.24%) | **0/2** (15.00%) | **0/1** (13.33%) | **0/2** (53.33%) | **0/3** (25.13%) | **0/1** (25.00%) | **0/3** (72.14%) | **0/4** (41.90%) | **0/1** (40.00%) | **1/3** (63.89%) | **0/1** (36.36%) | **1/25 (40.08%)** |
| **Gemini-1.5-pro** | **0/4** (33.81%) | **0/2** (31.67%) | **0/1** (6.67%) | **0/2** (73.33%) | **0/3** (25.13%) | **0/1** (16.67%) | **0/3** (62.98%) | **0/4** (31.79%) | **0/1** (20.00%) | **1/3** (72.22%) | **0/1** (45.45%) | **1/25 (39.51%)** |
| **GPT-4o-mini** | **0/4** (33.14%) | **0/2** (18.33%) | **0/1** (0.00%) | **0/2** (73.33%) | **0/3** (18.46%) | **0/1** (16.67%) | **0/3** (29.29%) | **0/4** (26.50%) | **0/1** (20.00%) | **1/3** (58.33%) | **0/1** (36.36%) | **1/25 (31.27%)** |
| **LLaMA-3.1-405B** | **0/4** (24.09%) | **0/2** (5.00%) | **0/1** (0.00%) | **0/2** (43.33%) | **0/3** (10.26%) | **0/1** (16.67%) | **0/3** (32.38%) | **0/4** (19.07%) | **0/1** (10.00%) | **0/3** (53.33%) | **0/1** (0.00%) | **0/25 (22.45%)** |
| **LLaMA-3.1-70B** | **0/4** (14.09%) | **0/2** (0.00%) | **0/1** (0.00%) | **0/2** (26.67%) | **0/3** (6.67%) | **0/1** (8.33%) | **0/3** (17.50%) | **0/4** (15.60%) | **0/1** (0.00%) | **0/3** (47.78%) | **0/1** (9.09%) | **0/25 (15.59%)** |
| **LLaMA-3.1-8B** | **0/4** (2.20%) | **0/2** (0.00%) | **0/1** (0.00%) | **0/2** (25.00%) | **0/3** (0.00%) | **0/1** (0.00%) | **0/3** (8.33%) | **0/4** (0.00%) | **0/1** (0.00%) | **0/3** (27.50%) | **0/1** (9.09%) | **0/25 (6.75%)** |

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

## 📊 Performance Evaluation on Alert Triaging Dataset

| Model | True Positives (TP) | False Positives (FP) | Accuracy |
|-------|---------------------|----------------------|----------|
| Claude-3.5-Sonnet | 4/5 (80%) | 28/30 (93.3%) | 91.4% |
| GPT-4o | 3/5 (60%) | 22/30 (73.3%) | 71.4% |
| DeepSeek-Reasoner | 4/5 (80%) | 26/30 (86.7%) | 85.7% |
| o3-mini | 4/5 (80%) | 27/30 (90%) | 88.6% |

---

## 🏆 Leaderboard

**📊 Interactive Leaderboard Coming Soon!**

Stay tuned for updates! 🚀

---

## 🧠 Model Integrations

### ✅ Evaluated Models

SIA Agent has been tested and integrated with **9 popular LLMs**:

| Model | Provider | API Documentation |
|-------|----------|-------------------|
| Claude-3.5-Sonnet | Anthropic | [Claude API](https://docs.anthropic.com/en/docs/about-claude/models/all-models) |
| GPT-4o | OpenAI | [OpenAI API](https://platform.openai.com/docs/overview) |
| DeepSeek-Reasoner | DeepSeek | [Fireworks API](https://fireworks.ai/models) |
| o3-mini | OpenAI | [OpenAI API](https://platform.openai.com/docs/overview) |
| GPT-4o-mini | OpenAI | [OpenAI API](https://platform.openai.com/docs/overview) |
| Gemini-1.5-pro | Google | [Google Gemini API](https://ai.google.dev/) |
| LLaMA-3.1-8B | Meta | [Fireworks API](https://fireworks.ai/models) |
| LLaMA-3.1-70B | Meta | [Fireworks API](https://fireworks.ai/models) |
| LLaMA-3.1-405B | Meta | [Fireworks API](https://fireworks.ai/models) |

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

Please review our **[Ethics Statement](./Ethics.md)** which covers:
- Data compliance and curation practices
- Risk assessment and mitigation strategies
- Responsible use guidelines for researchers and practitioners

---

## 🌟 Acknowledgments

- The [LangChain](https://www.langchain.com/) community
- Security researchers who continue to push boundaries in automated incident analysis

---
