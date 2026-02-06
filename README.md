# NebulaExtract

CLI em Python que transforma texto não estruturado (emails, tickets, mensagens) em JSON estruturado usando a Gemini API.

## Core Features & Concepts:

LLM Integration: Direct communication with Gemini via HTTP API.
Smart Prompting: Dynamically builds JSON payloads for the model.
Resilient Parsing: Defensive logic to handle LLM responses reliably.
JSON Sanitization: Post-processing to ensure you get JSON output.
Validation: Built-in verification using json.loads to catch formatting errors.

## Prerequisites
Python 3.x and a Gemini API Key: Needs to be configured as an environment variable.

## So... how do i run?

# Navigate to the project directory:
cd NebulaExtract

# Set your API Key for the session:
paste "$env:GEMINI_API_KEY="YOUR_KEY_HERE""

# Launch the tool:
python cli\main.py

# output example:
{
  "summary": "...",
  "intent": "...",
  "priority": "low|medium|high",
  "entities": {
    "name": null,
    "email": null,
    "phone": null
  }
}
