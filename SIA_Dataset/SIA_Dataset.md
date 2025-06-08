

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
| `source`        | String | Original challenge URL or reference  | `"https://blueteamlabs.online/home/challenge/..."` |
| `scenario_name` | String | Unique identifier for the scenario   | `"BTLO_Ransomware_Script"`                         |
| `last_accessed` | String | Date when scenario was last accessed | `"June 04, 2025"`                                  |
| `writeup`       | String | Link to solution documentation       | `"https://medium.com/@author/solution"`            |

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
  "answer": "...",
  "task_category": "...",
  "complexity": "...",
  "adversarial_tactic": "..."
}
```

---

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
| `questions`       | Array  | Questions to be answered by the LLM    |

#### Example:

```json
{
  "scenario": "A recent ransomware attack compromised one of our web servers...",
  "tools_available": ["tshark", "python", "grep", "strings", "..."],
  "files_available": ["network.pcap"],
  "instructions": "You are working in a Kali Linux environment. Use the provided tools to analyze the files.",
  "directory": "/home/analyst/investigation",
  "questions": ["..."]
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