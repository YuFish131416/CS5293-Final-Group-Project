## Task: iter-1 — Project Setup & Full Delivery
**Status**: IN PROGRESS
**Last completed step**: S04
**Next step**: S05
**Blocked by**: none
**Started**: 2026-04-08

## Steps

### Phase 1 — Project Framework Setup
- [x] S01 — Create SPEC.md and all plan/ knowledge base files (PROJECT_OVERVIEW, ARCHITECTURE, LITERATURE_MAP, COMPARISON_FRAMEWORK, CONSTRAINTS, DIR_MAP, ITERATION_LOG, CHANGELOG, API_CHANGELOG, TECH_DEBT)
- [x] S01b — Create process/PROGRESS.md, process/CURRENT_TASK.md (this file), .gitignore, README.md skeleton

### Phase 2 — Report Skeleton
- [x] S02 — Set up report/ directory: copy IEEEtran.cls, create main.tex with 5-author block
- [x] S03 — Create all section .tex files in report/sections/ (introduction, background, analysis_attacks, analysis_defenses, analysis_comparison, discussion, conclusion, ai_statement)
- [x] S04 — Initialize references.bib with core paper BibTeX entries

### Phase 3 — Report Content
- [ ] S05 — Write Introduction section [HARD GATE: update LITERATURE_MAP.md if new papers added]
- [ ] S06 — Write Background section (LLM architecture + threat model)
- [ ] S07 — Write Main Analysis: Attack Taxonomy (direct / indirect / tool-use)
- [ ] S08 — Write Main Analysis: Defense Mechanisms [HARD GATE: update COMPARISON_FRAMEWORK.md]
- [ ] S09 — Write Main Analysis: Cross-cutting Comparison
- [ ] S10 — Write Discussion section
- [ ] S11 — Write Conclusion section
- [ ] S12 — Write AI Use Statement
- [ ] S13 — Finalize references.bib (ensure 10–20 complete entries)

### Phase 4 — Demo
- [ ] S14 — Implement prompt_injection_demo.py (direct + indirect injection scenarios)
- [ ] S15 — Create src/demo/requirements.txt and src/demo/README.md
- [ ] S16 — Test demo functionality

### Phase 5 — Slides
- [ ] S17 — Create slides.pptx with full presentation content
- [ ] S18 — Assign speaking parts to 5 members

### Phase 6 — Quality Assurance: Reference Audit （引用核查）
- [ ] S19 — 验证所有 references.bib 条目的准确性（作者、标题、年份、会议/期刊名称）
- [ ] S20 — 检查每篇引用文献的实际可访问网址，记录 DOI / arXiv / URL
- [ ] S21 — 将文献引用内容摘要和网址更新到 plan/LITERATURE_MAP.md（中文描述）
- [ ] S22 — 将文献引用列表摘要更新到 README.md（中文说明）
- [ ] S23 — 确认报告正文中每个 \cite{} 都引用了正确的论文内容（非张冠李戴）

### Phase 7 — Quality Assurance: De-AI Writing Check （去AI味检查）
- [ ] S24 — 逐章检查 AI 写作痕迹：过度结构化、空泛修饰语、重复句式模式
- [ ] S25 — 搜索并替换 AI 典型用语（delve into, landscape, in the realm of, it is worth noting, plays a crucial role 等）
- [ ] S26 — 确保每段论述有具体的论据/数据支撑，删除泛泛而谈的句子
- [ ] S27 — 在 Discussion 和 Comparison 章节增加作者自身的批判性判断
- [ ] S28 — 通读全文至少两遍，反复修改至像人类研究者撰写的风格

### Phase 8 — Final Review & Submission
- [ ] S29 — Self-review all deliverables → review/REVIEW_iter-1.md
- [ ] S30 — Update all plan/ files for final consistency
- [ ] S31 — Verify all acceptance criteria in SPEC.md
- [ ] S32 — Final compilation and export (report PDF + slides PDF)

## Test Steps
- [ ] T01 — Verify report compiles without errors (LaTeX)
- [ ] T02 — Verify report ≤ 6 pages (excluding references)
- [ ] T03 — Verify all citations in report resolve to references.bib entries
- [ ] T04 — Verify demo runs successfully (or screenshot fallback prepared)
- [ ] T05 — Verify slides PDF is readable and ≤ 5 min content
- [ ] T06 — Verify all acceptance criteria in SPEC.md are met
- [ ] T07 — 引用核查：所有文献网址可访问且内容匹配
- [ ] T08 — 去AI味检查：全文不包含典型 AI 用语列表中的任何词汇
