## [iter-1] Project Setup & Framework — 2026-04-08
- ADD: SPEC.md — Project specification document
- ADD: README.md — Project overview and build instructions
- ADD: .gitignore — Standard ignore rules
- ADD: plan/PROJECT_OVERVIEW.md — Goals, features, non-goals, acceptance criteria
- ADD: plan/ARCHITECTURE.md — Report logical architecture and literature framework
- ADD: plan/LITERATURE_MAP.md — Master paper index (replaces INTERFACES.md)
- ADD: plan/COMPARISON_FRAMEWORK.md — Paper comparison matrices (replaces SCHEMAS.md)
- ADD: plan/CONSTRAINTS.md — Tech stack and deadline constraints
- ADD: plan/DIR_MAP.md — Directory and file purpose map
- ADD: plan/ITERATION_LOG.md — This file
- ADD: plan/CHANGELOG.md — Human-readable changelog
- ADD: plan/API_CHANGELOG.md — Reserved (N/A for survey project)
- ADD: plan/TECH_DEBT.md — Known issues tracker
- ADD: process/PROGRESS.md — Milestone checkboxes
- ADD: process/CURRENT_TASK.md — Breakpoint-resume state

## [iter-2] Report Skeleton & Quality Assurance Tasks — 2026-04-08
- ADD: report/main.tex — Main LaTeX file with 5-author block, abstract, section imports
- ADD: report/sections/introduction.tex — Introduction chapter skeleton with writing guidelines
- ADD: report/sections/background.tex — Background chapter skeleton (LLM basics, tool-use, threat model)
- ADD: report/sections/analysis_attacks.tex — Attack taxonomy skeleton (direct/indirect/tool-use)
- ADD: report/sections/analysis_defenses.tex — Defense mechanisms skeleton (4 categories)
- ADD: report/sections/analysis_comparison.tex — Comparative analysis skeleton (3 dimensions)
- ADD: report/sections/discussion.tex — Discussion skeleton (key findings, limitations, open problems)
- ADD: report/sections/conclusion.tex — Conclusion skeleton
- ADD: report/sections/ai_statement.tex — AI Use Statement skeleton
- ADD: report/references.bib — Initial 16 BibTeX entries
- COPY: report/IEEEtran.cls — From Template/LaTex/
- UPDATE: plan/LITERATURE_MAP.md — Added 引用核查清单（中文）and 去AI味检查清单
- UPDATE: plan/TECH_DEBT.md — Added TD-004~TD-007 for reference audit and de-AI checks
- UPDATE: process/PROGRESS.md — Added M6 (引用核查) and M7 (去AI味) milestones; M2 marked complete
- UPDATE: process/CURRENT_TASK.md — S02-S04 marked complete; added Phase 6-8 and T07-T08

## [iter-3] Report Content Writing & Quality Review — 2026-04-08
- UPDATE: report/main.tex — Replaced placeholder author block with 5 real members (Yu Peihan, Hu Xuelin, Weng Ziyan, Deng Leying, Zhao Haichao) with IDs and emails
- WRITE: report/references.bib — 16 BibTeX entries (11 core papers + 5 supplementary)
- WRITE: report/sections/introduction.tex — Full Introduction (problem context, attack surface, scope, organization)
- WRITE: report/sections/background.tex — Full Background (LLM fundamentals, tool-augmented apps, threat model)
- WRITE: report/sections/analysis_attacks.tex — Full Attack Taxonomy (direct injection, indirect injection, tool-use exploitation)
- WRITE: report/sections/analysis_defenses.tex — Full Defense Mechanisms (input sanitization, instruction hierarchy, output monitoring, architectural isolation)
- WRITE: report/sections/analysis_comparison.tex — Full Comparative Analysis (threat models, evaluation methodology, deployment feasibility + table)
- WRITE: report/sections/discussion.tex — Full Discussion (key findings, literature limitations, open problems)
- WRITE: report/sections/conclusion.tex — Full Conclusion
- WRITE: report/sections/ai_statement.tex — Full AI Use Statement
- FIX: background.tex — Changed "underscores the practical risk" → "highlighting the practical risk" (de-AI)
- FIX: background.tex — Removed inaccurate "ReAct paradigm" attribution to ToolEmu paper
- FIX: conclusion.tex — Changed "threat landscape" → "threat space" (de-AI)
- ADD: review/REVIEW_iter-3.md — Full review covering citation consistency, logical coherence, de-AI check, format compliance
- UPDATE: process/PROGRESS.md — M3 complete, M6/M7/M8 partially complete

## [iter-4] Prompt Injection Demo — 2026-04-08
- CREATE: src/demo/prompt_injection_demo.py — 4-scenario demo (2 direct injection + 2 indirect/tool-use injection), dual-mode (simulated + live API), CLI with --live/--model/--scenario/--json flags
- CREATE: src/demo/requirements.txt — openai>=1.0.0 for live mode only
- CREATE: src/demo/README.md — Usage guide, scenario descriptions, report connection, setup instructions
- TEST: All 4 scenarios pass in simulated mode; --scenario and --json flags verified
- UPDATE: process/PROGRESS.md — M4 Demo milestone complete

## [iter-5] Presentation Slides — 2026-04-08
- CREATE: slides/build_slides.js — PptxGenJS script generating 12-slide presentation with Midnight Cyber color scheme
- CREATE: slides/slides.pptx — Final output, 12 slides covering all 7 agenda items
- Slide layout: Title(1), Agenda(2), Motivation(3), Background+Threat Model(4), Attack Taxonomy(5), Direct+Indirect Injection(6), Tool-use Attacks(7), Defense Mechanisms(8), Comparative Analysis Table(9), Live Demo(10), Open Problems(11), Conclusion+Q&A(12)
- Speaker assignment: Yu Peihan (1-3), Hu Xuelin (4), Weng Ziyan (5-7), Deng Leying (8-9), Zhao Haichao (10-12)
- QA: Content extraction verified via markitdown — all 12 slides text-complete, no placeholders
- QA: Code-explorer subagent reviewed for 23 visual/layout issues; fixed 12 critical/medium issues including:
  - Slide 4/7: 3-card layout right margin 0.3" → 0.55" (card width 2.8→2.65, spacing 3.05→2.9)
  - Slide 9: colW sum 7.7" ≠ w 8.8" → fixed to colW sum 8.4" = w; left margin 0.6→0.8"
  - Slide 10: command line bottom margin 0.225" → 0.475"; demo cards compressed
  - Slide 12: footer bottom margin 0.175" → 0.5"; Q&A section moved up
  - Slide 8: row spacing 0.2" → 0.3"
  - Slide 9: headerOpts shared object → factory function
- UPDATE: process/PROGRESS.md — M5 Slides milestone complete

## [iter-6] Final Review & Finalization (Phase 5) — 2026-04-08
- UPDATE: report/sections/ai_statement.tex — Revised AI Use Statement: literature search (AI), core outline (human), language polishing (AI), reference verification (AI); added 4 representative prompts and detailed breakdown
- REWRITE: README.md — Full Chinese rewrite targeting collaborators: project overview, file architecture with person assignments, paper list with arXiv/venue identifiers, Git workflow guide (branching, conflict resolution, common issues), per-person file responsibility table, AI usage summary
- CREATE: review/REVIEW_iter-6.md — Final Phase 5 review covering all deliverables, SPEC.md acceptance criteria verification, management file consistency check
- UPDATE: plan/ITERATION_LOG.md — Added iter-6 entry
- UPDATE: plan/CHANGELOG.md — Added iter-6 entry
- UPDATE: plan/TECH_DEBT.md — Resolved TD-004~TD-007; closed remaining items
- UPDATE: plan/DIR_MAP.md — Added slides/build_slides.js, review/REVIEW_iter-6.md, updated last-modified
- UPDATE: process/PROGRESS.md — M6/M7/M8 milestones fully complete; all checkboxes marked
- UPDATE: plan/LITERATURE_MAP.md — Updated citation audit checklist with arXiv/venue identifiers
