

## 🎯 Overview

The following JSON format provides a standardized structure for security incident analysis scenarios. This format enables **Automated evaluation** of LLM agents in SIA tasks.

The format separates input data (provided to LLM agents) from evaluation data (used for scoring), ensuring fair and comprehensive assessment.

---

## 🏗️ Root Structure

```json
{
  "scenarios": [
    {
      "metadata": { "..." },
      "sia_components": { "..." }
    }
  ]
}
```

**Key Points:**

- Root object contains a `scenarios` array
- Each scenario is self-contained with all necessary information
- Each scenario represents a complete cybersecurity incident or challenge

---

## 🧩 Scenario Object Components

Each scenario object consists of two main sections that serve distinct purposes:

### 🔖 Metadata Section

Contains reference information about the scenario source.

```json
"metadata": {
  "source": "https://example.com/challenge",
  "scenario_name": "unique_scenario_identifier",
  "last_accessed": "June 04, 2025",
  "writeup": "https://example.com/solution"
}
```

| Field           | Type   | Purpose                              | Example                                            |
| --------------- | ------ | ------------------------------------ | -------------------------------------------------- |
| `source`        | String | Original challenge URL or reference  | `"https://cyberdefenders.org/blueteam-ctf-challenges/bluesky-ransomware/"` |
| `scenario_name` | String | Unique identifier for the scenario   | `"BlueSky"`                         |
| `last_accessed` | String | Date when scenario was last accessed | `"June 04, 2025"`                                  |
| `writeup`       | String | Link to solution documentation       | `"https://h05am10.gitbook.io/h05am10/write-ups/cyberdefenders/network-forensics/bluesky-ransomware"`            |

### 🧪 SIA Components Section

Contains the core scenario data, questions, and evaluation fields.

```json
"sia_components": {
  "scenario": "...",
  "tools_available": ["..."],
  "files_available": ["..."],
  "instructions": "...",
  "directory": "...",
  "questions": ["..."],
  "task_category": "...",
  "complexity": "...",
}
```

The `questions` array contains three components:

```json
{
 "question": "",
 "answer": "",
 "adversarial_tactic": ""
}
```
## 📊 Component Categories

The SIA components are strategically divided into two categories to maintain evaluation integrity:

### 🔵 LLM Input Components

**Purpose:** Information provided to the LLM agent for solving the task.

#### Core Fields:

| Field             | Type   | Description                            |
| ----------------- | ------ | -------------------------------------- |
| `scenario`        | String | An incident scenario description  |
| `tools_available` | Array  | List of available suggested command-line tools   |
| `files_available` | Array  | Files provided for analysis            |
| `instructions`    | String | Environment setup and usage guidelines |
| `directory`       | String | Working directory path                 |
| `question`       | String  | List of questions to be answered by the LLM    |

#### Example:

```json
{
  "scenario": "A major corporation responsible for vital data...",
  "tools_available": ["tshark", "python", "grep", "strings", "..."],
  "files_available": ["capture.pcap"],
  "instructions": "You are working in a Kali Linux environment. Use the provided tools to analyze the files.",
  "directory": "/home/analyst/investigation",
  "question": ["Is there any evidence of port scanning in the network traffic? If so, what is the IP address responsible for the scanning activity?, ..."]
}
```

### 🔴 Evaluation Components

**Purpose:** Ground truth data used exclusively for automated scoring

#### Core Fields:

| Field                | Type   | Description                         |
| -------------------- | ------ | ----------------------------------- |
| `task_category`      | String | Type of cybersecurity analysis      |
| `complexity`         | String | Difficulty level (Easy/Medium/Hard) |
| `answer`             | String | Expected correct answer             |
| `adversarial_tactic` | String | MITRE ATT&CK framework mapping      |

#### Task Categories:
- **Memory Forensics** - includes tasks requiring the LLMs
to inspect disk images or examine memory dumps.
- **Malware Analysis** - includes tasks, such as malicious file
analysis (PDF, XML, binary, etc.), static code review, and
inspecting ransomware scripts.
- **Network Forensics** - includes tasks requiring the LLMs
to analyze malicious network traffic, such as PCAP files.
- **Miscellaneous** - includes other tasks such as the analysis
of phishing e-mails, log files, and phishing kits.

### 🗂️ Artifacts Availability

There are primarily two ways of downloading the files/artifacts:

1. **GitHub Repository**  
   Some artifacts are available in this repository:  
   [Cyber-Defenders Repository](https://github.com/Panagiotis-INS/Cyber-Defenders/tree/main)  
   Licensed under **AGPL-3.0**.

2. **Blue Team Training Platforms**  
   - [Blue Team Labs Online (BTLO)](https://blueteamlabs.online/)  
   - [CyberDefenders](https://cyberdefenders.org/)  
   - [TryHackMe](https://tryhackme.com/)  

   Following their **Terms & Conditions**, we do not host their artifacts.  
   Instead, we reference the **source challenge links (URLs)** in our JSON files for each scenario.  
   - Artifacts can be downloaded freely by signing up (no payment or subscription required).  
   - These are **free, retired challenges**.  
   - Each free scenario has a **public writeup** available.
