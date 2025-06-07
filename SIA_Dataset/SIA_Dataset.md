# Cybersecurity Scenarios JSON Data Structure

This document outlines the standardized JSON data structure used in the **SIABench.** 

---

## 📘 Overview

The SIABench JSON format is designed to encapsulate detailed information about cybersecurity incident analysis (SIA) tasks. It includes:

- Scenario metadata  
- Task instructions  
- Investigation questions  
- Ground truth answers and evaluation parameters  

This structure supports automated evaluation workflows within an LLM agentic framework.

---

## 🗂️ Root Structure

```json
{
  "scenarios": [
    // Array of scenario objects
  ]
}
```

The root-level `scenarios` array contains one or more scenario objects, each representing a complete incident scenario.

---

## 🧩 Scenario Object Structure

Each scenario object contains two main sections:

### 1. 🔖 Metadata

```json
"metadata": {
  "source": "string",
  "scenario_name": "string",
  "last_accessed": "string",
  "writeup": "string"
}
```

**Fields:**
- `source`: Link or reference to the original challenge source  
- `scenario_name`: Unique identifier for the scenario  
- `last_accessed`: Last accessed date (e.g., "June 04, 2026")  
- `writeup`: Link to the solution or investigation write-up  

---

### 2. 🧪 SIA Components

The `sia_components` section contains the core information for scenario-based analysis:

#### 📝 Basic Information

- `scenario`: Description of the cybersecurity incident  
- `task_category`: Classification (e.g., *Network Forensics*, *Malware Analysis*, *Memory Forensics*, *Miscellaneous*)  
- `complexity`: Difficulty level (e.g., *Easy*, *Medium*, *Hard*)  

#### 🛠️ Technical Environment

- `tools_available`: List of suggested tools  
- `files_available`: Filename(s) provided for analysis  
- `instructions`: Tool and environment instructions  
- `directory`: Working directory path for files  

#### ❓ Questions Array

Each question object has the following structure:

```json
{
  "question": "string",
  "answer": "string",
  "adversarial_tactic": "string"
}
```

**Fields:**
- `question`: A question the LLM must answer based on scenario data  
- `answer`: Ground truth response used for evaluation  
- `adversarial_tactic`: Mapped MITRE ATT&CK tactic for evaluation  

---

## 💡 Example Scenario

```json
{
  "metadata": {
    "source": "https://blueteamlabs.online/home/challenge/network-analysis-web-shell-d4d3a2821b",
    "scenario_name": "Btlo_port_scanning",
    "last_accessed": "June 04, 2026",
    "writeup": "https://medium.com/btlo-investigation-solutions/btlo-network-analysis-web-shell-9fa8d3135b6"
  },
  "sia_components": {
    "scenario": "An analyst detects unusual network activity...",
    "task_category": "Network Forensics",
    "complexity": "Easy",
    "tools_available": ["tshark", "python", "grep", "strings"],
    "files_available": "capture.pcap",
    "instructions": "Use tshark and grep to identify suspicious activity.",
    "directory": "/home/analyst/btlo/portscan",
    "questions": [
      {
        "question": "Based on the network traffic, is there any indication of port scanning activity?",
        "answer": "Yes, the network traffic shows clear indications of port scanning activity.",
        "adversarial_tactic": "Reconnaissance: Port scanning is commonly used for identifying open ports..."
      }
    ]
  }
}
```

---

## 🧠 LLM Input vs. Evaluation Components

To enable structured and efficient processing, `sia_components` are split into two categories:

### 🔵 LLM Input Components

Provided to the LLM agent to reason about and answer questions:

```json
{
  "scenario": "...",
  "tools_available": [...],
  "files_available": "...",
  "instructions": "...",
  "directory": "...",
  "questions": ["..."]
}
```

### 🔴 Evaluation Components

Used solely for automated scoring and benchmarking:

```json
{
  "task_category": "...",
  "complexity": "...",
  "answer": "...",
  "adversarial_tactic": "..."
}
```



---

## 📌 Summary

This JSON specification is foundational to building reproducible, evaluable, and scalable cybersecurity training and assessment scenarios using LLMs. By adhering to this structure, contributors can create scenarios that are both informative and compatible with automated evaluation pipelines.

---