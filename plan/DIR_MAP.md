| Path | Purpose |
|------|---------|
| `SPEC.md` | Project specification: goals, features, non-goals, constraints, acceptance criteria |
| `README.md` | Project overview, build instructions, demo usage guide |
| `.gitignore` | Standard ignore rules for tmp/, secrets, build artifacts |
| `plan/` | Compressed knowledge base — project's long-term memory |
| `plan/AGENT_STARTUP.md` | Workflow guide — read first every session |
| `plan/PROJECT_OVERVIEW.md` | Goals, feature list, non-goals, acceptance criteria |
| `plan/ARCHITECTURE.md` | Report logical architecture, literature organization framework |
| `plan/LITERATURE_MAP.md` | Master paper index with taxonomy (replaces INTERFACES.md) |
| `plan/COMPARISON_FRAMEWORK.md` | Structured comparison matrices for papers (replaces SCHEMAS.md) |
| `plan/CONSTRAINTS.md` | Tech stack, format rules, deadline constraints |
| `plan/DIR_MAP.md` | This file — one-line purpose for every folder and key file |
| `plan/ITERATION_LOG.md` | Structured log for Agent — file paths + change type |
| `plan/CHANGELOG.md` | Narrative log for humans — why + impact |
| `plan/API_CHANGELOG.md` | N/A for literature survey; reserved for report structure changes |
| `plan/TECH_DEBT.md` | Known issues, incomplete sections, weak arguments to revisit |
| `process/` | Progress tracking |
| `process/USER_REQUIREMENTS.md` | Original user requirements and clarification record |
| `process/PROGRESS.md` | Milestone-level checkboxes (coarse) |
| `process/CURRENT_TASK.md` | Breakpoint-resume state (fine) — updated after every step |
| `report/` | LaTeX report source files |
| `report/main.tex` | Main report file (IEEE format, 5 authors) |
| `report/references.bib` | BibTeX bibliography entries |
| `report/IEEEtran.cls` | IEEE class file (copied from Template/) |
| `report/sections/` | Individual chapter .tex files for modular editing |
| `report/figures/` | Figures used in the report |
| `slides/` | Presentation materials |
| `slides/slides.pptx` | 5-minute presentation slide deck (12 slides, Midnight Cyber theme) |
| `slides/build_slides.js` | PptxGenJS script to generate slides.pptx |
| `src/demo/` | Prompt injection demonstration scripts |
| `src/demo/prompt_injection_demo.py` | Python demo: 4 scenarios (2 direct + 2 indirect injection) |
| `src/demo/requirements.txt` | Python dependencies (simulated mode: none; live mode: openai) |
| `src/demo/README.md` | Demo setup and usage instructions (Chinese + English) |
| `review/` | Per-iteration self code/content review outputs |
| `review/REVIEW_iter-3.md` | iter-3 review: citation consistency, logical coherence, de-AI check |
| `review/REVIEW_iter-6.md` | iter-6 review: final Phase 5 deliverable completeness & acceptance criteria |
| `docs/` | Final compiled deliverable PDFs |
| `Template/` | IEEE templates — reference only, do not modify |
| `tmp/` | Scratch files — gitignored |

**Last modified**: iter-6
