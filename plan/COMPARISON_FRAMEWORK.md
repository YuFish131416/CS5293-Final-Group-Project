## Comparison Framework

> Replaces `SCHEMAS.md` from AGENT_STARTUP.md. This file defines the structured comparison matrices used to analyze and contrast the surveyed literature.

---

## Attack Comparison Matrix

| Paper | Attack Type | Target | Threat Model Assumptions | Evaluation Method | Success Metric | Key Limitation |
|-------|------------|--------|--------------------------|-------------------|----------------|----------------|
| P01 Greshake et al. | Indirect PI | Real-world LLM apps (Bing Chat, etc.) | Attacker controls external data source | Empirical demo on live systems | Successful instruction override | Limited to specific apps tested |
| P02 Perez & Ribeiro | Direct PI | General LLMs | Attacker has direct prompt access | Crowdsourced benchmark (HackAPrompt) | % of successful injections | Competition setting may not reflect real use |
| P04 Zhan et al. | Indirect PI (tool-use) | LLM agents with tools | Attacker injects via tool-retrieved data | Benchmark (InjecAgent, 1054 cases) | Attack success rate across tools | Simulated environment, not production |
| P05 Yi et al. | Indirect PI | LLMs processing external text | Attacker controls retrieved content | Benchmark (BIPIA) | Attack success + defense bypass rate | Synthetic injection scenarios |
| P07 Ruan et al. | Tool-use exploitation | LLM agents | Attacker manipulates agent actions | LM-emulated sandbox (ToolEmu) | Risk score across safety dimensions | Emulation fidelity vs. real tools |

---

## Defense Comparison Matrix

| Paper | Defense Category | Mechanism | Training Required? | LLM-Agnostic? | Evaluation Benchmark | Effectiveness | Usability Impact | Deployment Practicality |
|-------|-----------------|-----------|-------------------|----------------|---------------------|---------------|-----------------|------------------------|
| P08 Suo et al. | Instruction Hierarchy | Cryptographic prompt signing | No | Yes | Custom test set | Moderate | Low overhead | Requires infrastructure changes |
| P09 Hines et al. | Input Sanitization | Spotlighting (delimiting, encoding, datamarking) | No | Yes | BIPIA | High (datamarking best) | Increased token usage | Easy to deploy |
| P10 Chen et al. | Architectural Isolation | Structured queries — separate prompt/data encoding | Yes (fine-tuning) | No (model-specific) | Custom + BIPIA | High | Minimal | Requires model retraining |
| P11 Wallace et al. | Instruction Hierarchy | Training LLMs to prioritize system instructions | Yes (training-time) | No (model-specific) | Custom benchmark | High | Minimal | Deployed in GPT-4 |

---

## Cross-Cutting Comparison Dimensions

### 1. Threat Model Realism
| Level | Description | Papers |
|-------|-------------|--------|
| High | Tested on real deployed systems | P01 |
| Medium | Realistic simulated environment with real LLM | P04, P05, P07 |
| Low | Synthetic / contrived scenarios | P02 (competition) |

### 2. Evidence Strength
| Level | Description | Papers |
|-------|-------------|--------|
| Strong | Large-scale benchmark, reproducible | P02, P04, P05 |
| Moderate | Meaningful evaluation but limited scale | P01, P07, P09, P10 |
| Preliminary | Proof-of-concept or small-scale | P08 |

### 3. Deployment Feasibility
| Level | Description | Papers |
|-------|-------------|--------|
| Deployed | Already in production systems | P11 (GPT-4) |
| Ready | No model changes, drop-in | P09 |
| Requires changes | Model retraining or infra modification | P08, P10 |

---

## Template for Adding New Entries

### Attack Paper
```
| Paper ID | Attack Type | Target | Threat Model Assumptions | Evaluation Method | Success Metric | Key Limitation |
```

### Defense Paper
```
| Paper ID | Defense Category | Mechanism | Training Required? | LLM-Agnostic? | Evaluation Benchmark | Effectiveness | Usability Impact | Deployment Practicality |
```

---

**Last modified**: iter-1
