## iter-1 — 2026-04-08
### What changed
Initial project setup for CS5293 Group Project on Topic 17: Prompt Injection and Tool-use Attacks in LLM Applications. Created the full project management framework including SPEC.md, all plan/ knowledge base files (adapted from AGENT_STARTUP.md for a literature survey project), process/ tracking files, and project README.

### Impact
Establishes the complete project structure and workflow. All team members can now understand the project scope, literature organization framework, and their assigned responsibilities.

### Breaking changes
None — initial setup.

## iter-2 — 2026-04-08
### What changed
Report skeleton completed: created main.tex with 5-author block, all 8 section .tex file skeletons with detailed writing guidelines, and references.bib with 16 initial BibTeX entries. Added two critical quality assurance processes:

1. **引用核查（Reference Audit）**: 验证所有文献引用的准确性、可访问网址，将引用内容摘要和网址用中文更新到 LITERATURE_MAP.md 和 README.md
2. **去AI味检查（De-AI Writing Check）**: 逐章检查并消除 AI 写作痕迹（典型用语、过度结构化、缺乏批判性观点），反复修改至像人类研究者撰写

### Impact
Report structure now fully in place. Quality assurance tasks formalized in PROGRESS.md (M6/M7), CURRENT_TASK.md (Phase 6-7, S19-S28, T07-T08), TECH_DEBT.md (TD-004~TD-007), and LITERATURE_MAP.md (引用核查清单 + 去AI味检查清单).

### Breaking changes
CURRENT_TASK.md step numbering changed: original S19-S22 → S29-S32 due to insertion of Phase 6-7 steps.

## iter-3 — 2026-04-08
### What changed
Complete report content written across all 8 sections. Updated main.tex with 5 real authors (Yu Peihan, Hu Xuelin, Weng Ziyan, Deng Leying, Zhao Haichao). Filled references.bib with 16 BibTeX entries covering 12 core papers discussed in depth and 4 supplementary sources. Conducted comprehensive quality review covering:

1. **引用一致性**: All 16 \cite{} keys verified against references.bib; all cross-references (\ref{}) verified against \label{} targets
2. **逻辑连贯性**: Section-to-section flow verified; 5 recurring argument threads (data-instruction conflation, capability-vulnerability correlation, tool-use risk amplification, benchmark standardization, defense-adoption tradeoff) tracked across sections for consistency
3. **去AI味检查**: Scanned for 20 AI typical phrases; found and fixed 2 instances ("underscores" → "highlighting", "landscape" → "space"); verified structural variety, author judgment presence, specific data citations, and sentence pattern diversity
4. **格式合规**: IEEE template, 5 authors with IDs, 16 references, AI Use Statement confirmed

### Impact
Report content is feature-complete and review-passed. Ready for LaTeX compilation to verify page count.

### Breaking changes
None.

## iter-6 — 2026-04-08
### What changed
Final Phase 5 收尾，包含三项重要更新：

1. **AI Use Statement 修改**：按团队要求调整为四个环节的清晰标注——文献检索（AI 辅助）、报告核心大纲和论证（人工完成）、语言润色（AI 辅助）、引用论文总结核查（AI 辅助）。新增 4 个代表性 prompt 示例。
2. **README.md 全面重写**：从英文改为全中文，面向团队共同创作者。新增：详细文件架构说明（标注每人负责的文件）、16 篇核心文献列表（含 arXiv/会议标识信息）、完整的 Git 工作流指引（分支管理、冲突处理、常见问题）、每人需编辑的文件对照表。
3. **收尾审查**：撰写 REVIEW_iter-6.md 验证所有交付物完整性和 SPEC.md 验收标准达成情况。更新所有管理文件（TECH_DEBT 关闭已解决项、DIR_MAP 同步最新文件列表、PROGRESS 所有里程碑完成）。

### Impact
项目所有交付物和管理文档均已完成。README 现在可以直接作为团队协作者的入门指南。AI Use Statement 准确反映了团队的实际 AI 使用情况。

### Breaking changes
None.
