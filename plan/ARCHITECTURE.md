## Report Logical Architecture

This project is a literature survey, not a software system. "Architecture" here refers to the logical structure of the report, the literature organization framework, and the relationships between deliverables.

### Report Chapter Dependencies

```
Introduction (scope + motivation)
    ↓
Background (LLM basics + threat model)
    ↓
Main Analysis
    ├── 3.1 Attack Taxonomy (direct / indirect / tool-use)
    ├── 3.2 Defense Mechanisms (filtering / isolation / monitoring / sandboxing)
    └── 3.3 Cross-cutting Comparison (assumptions / evidence / practicality)
    ↓
Discussion (limitations + open problems + trends)
    ↓
Conclusion (key takeaways)
    ↓
AI Use Statement (if applicable)
```

### Literature Organization Framework

Papers are organized along two primary dimensions:

**Dimension 1 — Attack Type:**
| Category | Description | Example Techniques |
|----------|-------------|--------------------|
| Direct Prompt Injection | User-supplied input overrides system instructions | Instruction override, role-playing, jailbreaks |
| Indirect Prompt Injection | Malicious content injected via external data sources | Poisoned web pages, email content, retrieved documents |
| Tool-use / Agent Exploitation | Attacks that abuse LLM tool-calling capabilities | Malicious function calls, parameter manipulation, chain-of-tool attacks |

**Dimension 2 — Defense Approach:**
| Category | Description | Key Techniques |
|----------|-------------|----------------|
| Input Sanitization & Filtering | Pre-process prompts to remove/neutralize injections | Keyword filtering, prompt rewriting, perplexity-based detection |
| Instruction Hierarchy & Privilege Separation | Enforce priority levels between system and user instructions | System-prompt hardening, dual-LLM architectures, role separation |
| Output Monitoring & Guardrails | Post-process LLM outputs to detect policy violations | Classifier-based filtering, rule-based output checks |
| Architectural Isolation (Sandboxing) | Limit what the LLM can access or do | Tool permission scoping, execution sandboxes, least-privilege design |

### Deliverable Relationships

```
Literature Research (8–12 core papers)
    ↓                   ↓
LITERATURE_MAP.md    COMPARISON_FRAMEWORK.md
    ↓                   ↓
    └───── Report (LaTeX) ─────┘
              ↓
         Slides (PPTX)
              ↓
         Demo (Python, optional)
```

### Modules Affected (iter-1)
- All modules — this is the initial setup and full delivery iteration
