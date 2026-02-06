# NebulaExtract

A Python CLI that transforms unstructured text (emails, tickets, messages) into structured JSON using Google Gemini.

## Core Features & Concepts

- **LLM Integration:** Direct communication with Gemini via HTTP API (urllib).
- **Smart Prompting:** Builds a strict JSON-only extraction prompt.
- **Resilient Parsing:** Defensive logic to handle LLM responses reliably.
- **JSON Sanitization:** Removes ```json wrappers when the model returns Markdown.
- **Validation:** Uses `json.loads` to verify the output is valid JSON.

## Prerequisites

- Python 3.x
- A Gemini API key available as an environment variable: `GEMINI_API_KEY`

## How to run (Windows PowerShell)

```powershell
# Navigate to the project directory
cd NebulaExtract

# Set your API key for the current terminal session
$env:GEMINI_API_KEY="YOUR_KEY_HERE"

# Run the CLI
python .\cli\main.py
