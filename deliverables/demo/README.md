# Prompt Injection Demo

Interactive command-line demonstration of prompt injection attacks against LLM applications, supporting the analysis in our CS5293 group report on **Topic 17: Prompt Injection and Tool-use Attacks in LLM Applications**.

## Scenarios

| # | Title | Category | Attack Technique | Reference |
|---|-------|----------|-----------------|-----------|
| 1 | Instruction Override | Direct Injection | Classic "Ignore previous instructions" to leak system prompt | Schulhoff et al. (HackAPrompt, 2023) |
| 2 | Context Switching | Direct Injection | Fake `System:` header via formatting tricks | HackAPrompt dataset patterns |
| 3 | Poisoned Web Content | Indirect Injection | Hidden HTML instructions in fetched web page | Greshake et al. (2023) |
| 4 | Email Data Exfiltration | Indirect + Tool-use | Injected tool call in email body exfiltrates inbox | Zhan et al. (InjecAgent, 2024) |

## Quick Start

### Simulated Mode (no API key needed)

```bash
cd src/demo
python prompt_injection_demo.py
```

The demo uses pre-written responses to illustrate each attack scenario. This is the recommended mode for classroom presentation.

### Live Mode (real LLM API)

```bash
pip install -r requirements.txt
export OPENAI_API_KEY="sk-..."          # or set via environment
python prompt_injection_demo.py --live
```

For non-OpenAI endpoints (e.g., local Ollama, Azure, etc.):

```bash
export OPENAI_API_KEY="ollama"
export OPENAI_BASE_URL="http://localhost:11434/v1"
python prompt_injection_demo.py --live --model llama3
```

### Command-Line Options

| Flag | Description |
|------|-------------|
| `--live` | Use real API calls instead of simulated responses |
| `--model NAME` | LLM model for live mode (default: `gpt-3.5-turbo`) |
| `--scenario N` | Run only scenario N (1–4) |
| `--json` | Output results as JSON |

### Examples

```bash
# Run all scenarios in simulated mode
python prompt_injection_demo.py

# Run only the indirect injection web scenario
python prompt_injection_demo.py --scenario 3

# Run with a local Ollama model
python prompt_injection_demo.py --live --model mistral

# Export results as JSON
python prompt_injection_demo.py --json > results.json
```

## How It Works

Each scenario follows the same structure:

1. **System Prompt** — The developer's instructions to the LLM (defines the app's behaviour)
2. **External Data** (indirect only) — Content fetched from an external source (web page, email)
3. **User Input** — Contains the injection payload (direct) or a benign query (indirect)
4. **Model Response** — Shows how the LLM follows the injected instructions
5. **Expected Safe Response** — What a defended system should produce instead
6. **Analysis** — Explains why the attack works, citing relevant papers from our report

## Connection to the Report

The demo directly supports **Section 3 (Attack Taxonomy)** of our report:

- **Scenarios 1–2** illustrate Section 3.1 (Direct Prompt Injection), demonstrating the instruction override and context switching patterns documented in the HackAPrompt dataset.
- **Scenario 3** illustrates Section 3.2 (Indirect Prompt Injection), reproducing the hidden-instruction web attack from Greshake et al.
- **Scenario 4** bridges Sections 3.2 and 3.3 (Tool-use Exploitation), showing how indirect injection gains leverage through tool access, as benchmarked by InjecAgent.

The closing summary connects all scenarios to the defence mechanisms discussed in Section 4 and the open problems raised in Section 5.

## Requirements

- Python 3.8+
- No additional packages needed for simulated mode
- `openai>=1.0.0` for live mode only (see `requirements.txt`)

## File Structure

```
src/demo/
├── prompt_injection_demo.py   # Main demo script
├── requirements.txt           # Python dependencies
└── README.md                  # This file
```
