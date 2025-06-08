## 🎯 Overview

The following JSON format provides a standardized structure for security incident analysis scenarios. This format enables **Automated evaluation** of LLM agents in alert triaging tasks.

## Structure Overview

```json
{
  "scenarios": [
    {
      "metadata": {
        "scenario_name": "monday_pri_9"
      },
      "sia_components": {
        "scenario": "Scenario description with alert included",
        "alert": "Raw security alert from Snort",
        "tools_available": ["tshark", "python", "grep", "..."],
        "files_available": "capture.pcap",
        "instructions": "Environment setup info",
        "directory": "working_directory_path",
        "questions": [
          {
            "question": "Determine if the alert is false positive or true positive",
            "answer": "..."
          }
        ]
      }
    }
  ]
}
```

## Field Descriptions

### Metadata
- **scenario_name**: Unique identifier for the scenario

### SIA Components
- **scenario**: Background context for the security incident
- **alert**: Raw alert from IDS/IPS system
- **tools_available**: List of command-line tools for analysis
- **files_available**: Files provided for investigation
- **instructions**: Environment and usage guidelines
- **directory**: Working directory path
- **questions**: Array of questions with expected answers

## Usage

**For LLM Input:** Use all fields except `questions[].answer and alert`

**For Evaluation:** Compare LLM responses against `questions[].answer`