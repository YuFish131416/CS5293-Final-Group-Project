# SPEC.md — Project Specification

> **Topic 17: Prompt Injection and Tool-use Attacks in LLM Applications**
> CS5293 Topics on Information Security — Final Group Project
> Team size: 5 members

---

## Goal

Produce a focused, critical literature survey on prompt injection and tool-use attacks in LLM-based applications, accompanied by a short in-class presentation and an optional live demo, meeting all CS5293 final-project requirements.

---

## Feature List

### Deliverables
- [ ] **IEEE Report** — Up to 6-page double-column PDF using IEEEtran template, with 10–20 cited references (8–12 discussed in depth)
- [ ] **Slide Deck** — PDF slides for a 5-minute presentation + 2-minute Q&A
- [ ] **Demo (stretch goal)** — Lightweight Python script demonstrating direct and indirect prompt injection attacks against an LLM; degrades gracefully to screenshots if API access is unavailable

### Report Content
- [ ] Clear problem definition, motivation, and scope
- [ ] Background: LLM architecture basics, prompt processing pipeline, tool-use paradigm, threat model
- [ ] Attack taxonomy: direct prompt injection, indirect prompt injection, tool-use / agent exploitation
- [ ] Defense survey: input sanitization & filtering, instruction hierarchy & privilege separation, output monitoring & guardrails, architectural isolation (sandboxing)
- [ ] Cross-cutting comparison: threat-model assumptions, evaluation methodology, empirical evidence strength, deployment practicality
- [ ] Discussion of limitations, disagreements, open problems, and future directions
- [ ] AI Use Statement (if AI tools were used)

### Project Management
- [ ] SPEC.md (this file)
- [ ] Full plan/ knowledge base per AGENT_STARTUP.md (adapted for literature survey)
- [ ] process/ progress tracking (PROGRESS.md + CURRENT_TASK.md)
- [ ] review/ self-review per iteration
- [ ] README.md with build instructions and project overview
- [ ] 5-person work division plan

---

## Non-Goals

- **Not a software engineering project** — No production code, no web application, no database
- **Not an original research contribution** — No novel attacks or defenses; the project is a survey
- **Not exhaustive** — We do not aim to cover every paper on LLM security; scope is limited to prompt injection and tool-use attacks
- **No deep mathematical proofs** — Formal cryptographic or ML-theoretic analysis is out of scope
- **No real-world attack deployment** — Demo is purely illustrative and educational; no testing against live production systems
- **No video recording** — Presentation is live in-class only; no video deliverable required

---

## Technical Constraints

### Format & Submission
- Report: IEEE conference template (`IEEEtran.cls`), double-column, ≤ 6 pages excluding references
- Citations: IEEE numerical style (`\cite{}` with BibTeX)
- Slide deck: One PDF per group, submitted on CANVAS by May 7, 2026
- Report: One PDF per group, submitted on CANVAS by May 10, 2026

### Source Requirements
- Peer-reviewed papers form the core of the report
- arXiv preprints, standards, and industry reports may supplement but not replace research literature
- All borrowed figures/tables must be cited in captions
- Every nontrivial claim must be traceable to a cited source

### AI Usage Policy
- AI tools may only be used in a limited supporting role (wording improvement, search terms, planning)
- If used: include AI Use Statement after conclusion + prompts in appendix + verification description
- Hallucinated/fabricated content will be penalized

### Demo (optional)
- Language: Python 3.10+
- LLM backend: OpenAI API or local ollama — fallback to pre-recorded screenshots
- No API keys committed to repository

### Deadlines
| Date | Deliverable |
|------|-------------|
| April 17, 2026 | Team registration + topic submission |
| May 7, 2026 | Slide deck PDF submission |
| May 8, 2026 | In-class presentation (5 min + 2 min Q&A) |
| May 10, 2026 | Final report PDF submission |

---

## Acceptance Criteria

### Report (5 marks)
- [ ] **Scope & Coverage (1 mark)**: Topic is well-scoped; key literature on prompt injection and tool-use attacks is represented with 10–20 references
- [ ] **Technical Accuracy & Source Fidelity (1 mark)**: All claims are accurate, citations are real and relevant, prior work is represented fairly
- [ ] **Critical Analysis (1 mark)**: Report evaluates strengths, weaknesses, assumptions, and limitations rather than only describing papers
- [ ] **Synthesis & Insight (1 mark)**: Literature is connected into themes, comparisons, trends, or gaps — not paper-by-paper summaries
- [ ] **Writing & Format (1 mark)**: Report is clear, well-organized, follows IEEE format, ≤ 6 pages

### Presentation (6 marks)
- [ ] **Topic Motivation & Scope (1 mark)**: Talk explains the problem area and chosen scope clearly
- [ ] **Technical Accuracy (1 mark)**: Speakers show accurate understanding of the literature
- [ ] **Organization & Clarity (1 mark)**: Talk is easy to follow and structured effectively
- [ ] **Delivery (1 mark)**: Presentation is clear, well-paced, and professional
- [ ] **Coordination & Time Management (1 mark)**: Group uses the short time effectively and presents as a team
- [ ] **Slides & Q&A (1 mark)**: Slides support the talk well and Q&A responses show understanding

### Demo (bonus, not graded separately)
- [ ] At least one prompt injection scenario is demonstrable (live or via screenshot)
- [ ] Demo clearly illustrates the attack concept discussed in the report
