# NebulaExtract

A Python CLI that transforms unstructured text (emails, tickets, messages) into structured JSON using Google Gemini.



##  What it does

NebulaExtract takes free-form text and extracts structured information such as **summary, intent, priority, and entities**, returning a clean and validated JSON output ready for automation or downstream processing.

Typical use cases include:
- Support tickets
- Emails
- User messages
- Any unstructured text input **(through interactive or automation mode)**



## Example

### Input
```text
Hi, my name is John Doe.  
I need urgent help because my account was charged twice.  
You can contact me at john.doe@email.com.
```

### Output
```JSON
{
  "summary": "User reports being charged twice and requests urgent help.",
  "intent": "billing_issue",
  "priority": "high",
  "entities": {
    "name": "John Doe",
    "email": "john.doe@email.com",
    "phone": null
  }
}
``` 
## Output Schema
```JSON
{
  "summary": "string",
  "intent": "string",
  "priority": "low | medium | high",
  "entities": {
    "name": "string | null",
    "email": "string | null",
    "phone": "string | null"
  }
}
```

## Core Features & Concepts
LLM Integration: Direct communication with Gemini via HTTP API.

Smart Prompting: Enforces strict JSON-only responses.

Resilient Parsing: Defensive logic to handle malformed or wrapped outputs.

JSON Sanitization: Removes ```json Markdown wrappers when present.

Validation: Uses json.loads to ensure valid JSON output.

# Prerequisites

Python 3.x

A Gemini API key available as an environment variable: GEMINI_API_KEY

# Usage

NebulaExtract can be used in two ways: **interactive mode** (human-friendly) or **CLI mode** (automation-friendly).

### Interactive mode (default)

Run the program without arguments and paste your text directly into the terminal.  
Finish the input by pressing **Enter on an empty line**.

```powershell
python .\cli\main.py
```

### CLI Mode (using --text)
You can also provide the input text directly as a command-line argument.
```PowerShell
python .\cli\main.py --text "Hi, I need help with my subscription"
```
This mode is designed for automation, scripting, and integration with other systems.

# How to run (Windows PowerShell)
### Navigate to the project directory
```PowerShell
cd NebulaExtract
```
### Set your API key for the current terminal session

```PowerShell
$env:GEMINI_API_KEY="YOUR_KEY_HERE"
``` 
### Run the CLI (interactive mode)
```PowerShell
python .\cli\main.py
```
### or Run the CLI with direct input (--text)
```PowerShell
python .\cli\main.py --text "Your text here"
```
