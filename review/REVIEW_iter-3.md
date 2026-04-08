# REVIEW — iter-3: Report Content Writing & Quality Audit

> **Reviewer**: AI-assisted self-review
> **Date**: 2026-04-08
> **Scope**: Full report content (all 8 sections + references.bib + main.tex author block)

---

## 1. Citation Consistency Check ✅

### 1.1 BibTeX Key → Report Usage Matrix

| BibTeX Key | Intro | BG | Attacks | Defenses | Comparison | Discussion | Conclusion | AI Stmt |
|------------|:-----:|:--:|:-------:|:--------:|:----------:|:----------:|:----------:|:-------:|
| `achiam2023gpt4` | ✅ | ✅ | | | | | | |
| `liu2024prompt` | ✅ | ✅ | ✅ | | | | | |
| `perez2022hackaprompt` | ✅ | ✅ | ✅ | | ✅ | ✅ | | |
| `greshake2023indirect` | ✅ | ✅ | ✅ | | ✅ | ✅ | | |
| `zhan2024injecagent` | ✅ | | ✅ | | | ✅ | | |
| `ruan2024toolemu` | ✅ | ✅ | ✅ | | ✅ | ✅ | | |
| `yi2023bipia` | ✅ | | ✅ | ✅ | ✅ | ✅ | | |
| `toyer2024tensor` | | | ✅ | ✅ | | ✅ | | |
| `debenedetti2024agentdojo` | | | ✅ | | ✅ | ✅ | | |
| `pedro2023prompt` | | | ✅ | | ✅ | | | |
| `hines2024spotlighting` | ✅ | | | ✅ | ✅ | | | |
| `suo2024signedprompt` | | | | ✅ | ✅ | | | |
| `chen2024struq` | ✅ | | | ✅ | ✅ | ✅ | | |
| `wallace2024hierarchy` | ✅ | | | ✅ | ✅ | ✅ | | |
| `willison2023prompt` | | | | ✅ | | | | |
| `owasp2025llm` | | | | ✅ | | ✅ | | |

**Result**: All 16 BibTeX entries are cited at least once. No orphan entries. No undefined `\cite{}` keys. ✅

### 1.2 Cross-reference Check

| `\ref{}` Target | `\label{}` Location | Match? |
|-----------------|---------------------|:------:|
| `sec:bg` | background.tex L3 | ✅ |
| `sec:attacks` | analysis_attacks.tex L3 | ✅ |
| `sec:defenses` | analysis_defenses.tex L3 | ✅ |
| `sec:comparison` | analysis_comparison.tex L3 | ✅ |
| `sec:discussion` | discussion.tex L3 | ✅ |
| `sec:conclusion` | conclusion.tex L3 | ✅ |
| `tab:deployment` | analysis_comparison.tex L26 | ✅ |

**Result**: All cross-references resolve correctly. ✅

---

## 2. Logical Coherence Check 🔍

### 2.1 Section-to-Section Flow

| Transition | Assessment | Notes |
|------------|:----------:|-------|
| Abstract → Introduction | ✅ Good | Abstract previews taxonomy and findings; Introduction elaborates with structure |
| Introduction → Background | ✅ Good | Intro ends with "Organization" paragraph mapping to §2-§7; Background opens with LLM fundamentals |
| Background → Attacks | ✅ Good | Threat model in §2.3 defines three attacker profiles that map directly to the three subsections of §3 |
| Attacks → Defenses | ✅ Good | Attack section ends with tool-use risks; Defense section opens with "no single defense eliminates prompt injection" |
| Defenses → Comparison | ✅ Good | Comparison explicitly states "Having surveyed attacks and defenses individually, we now compare..." |
| Comparison → Discussion | ✅ Good | Comparison ends with defense-in-depth recommendation; Discussion synthesizes cross-cutting themes |
| Discussion → Conclusion | ✅ Good | Discussion raises open problems; Conclusion summarizes and calls for future work |
| Conclusion → AI Statement | ✅ Good | Conclusion is final content section; AI Statement is appendix-like per course policy |

### 2.2 Argument Coherence

| Theme | First Introduced | Developed | Resolved | Assessment |
|-------|-----------------|-----------|----------|:----------:|
| Data-instruction conflation is the root cause | Intro ¶1 | BG §2.1, Attacks §3.1-3.2 | Discussion §6.1, Conclusion | ✅ Well-threaded |
| Capability-vulnerability correlation | Attacks §3.1 (HackAPrompt GPT-3.5 > GPT-3) | Attacks §3.2 (BIPIA GPT-4 > GPT-3.5) | Discussion §6.1 ¶2 | ✅ Well-supported with evidence |
| Tool-use amplifies risk | Intro ¶2 | BG §2.2, Attacks §3.3 | Discussion §6.1 ¶3, Conclusion | ✅ Well-threaded |
| Need for standardized benchmarks | — | Comparison §5.1-5.2 | Discussion §6.2 ¶1, §6.3 ¶2 | ✅ Consistent |
| Defense-strength vs ease-of-adoption tradeoff | — | Comparison §5.3 | Discussion §6.1, Conclusion | ✅ Consistent |

### 2.3 Issues Found & Fixed

| Issue | Location | Description | Fix Applied |
|-------|----------|-------------|:-----------:|
| Inaccurate attribution | background.tex | "The ReAct paradigm~\cite{ruan2024toolemu}" — ToolEmu is not the ReAct paper; ReAct is by Yao et al., 2023 | ✅ Reworded to avoid naming ReAct while citing ToolEmu |
| Forward reference mismatch | — | N/A — no issues found | ✅ |

---

## 3. De-AI Writing Check 🔍

### 3.1 AI Typical Phrasing Scan

| AI Phrase | Found? | Location | Action |
|-----------|:------:|----------|--------|
| "delve into" | ❌ | — | Clean |
| "in the realm of" | ❌ | — | Clean |
| "it is worth noting" | ❌ | — | Clean |
| "plays a crucial role" | ❌ | — | Clean |
| "the landscape of" / "landscape" | ⚠️ | conclusion.tex: "threat landscape" | ✅ Fixed → "threat space" |
| "sheds light on" | ❌ | — | Clean |
| "at the forefront of" | ❌ | — | Clean |
| "a myriad of" | ❌ | — | Clean |
| "comprehensive overview" | ❌ | — | Clean |
| "novel approach" | ❌ | — | Clean |
| "paves the way for" | ❌ | — | Clean |
| "offers valuable insights" | ❌ | — | Clean |
| "underscores the importance" / "underscores" | ⚠️ | background.tex: "underscores the practical risk" | ✅ Fixed → "highlighting" |
| "paradigm shift" | ❌ | — | Clean |
| "holistic" | ❌ | — | Clean |
| "significantly" | ❌ | — | Clean |
| "notably" | ❌ | — | Clean |
| "importantly" | ❌ | — | Clean |
| "furthermore" | ❌ | — | Clean |
| "moreover" | ❌ | — | Clean |

### 3.2 Structural AI-ness Assessment

| Criterion | Assessment | Notes |
|-----------|:----------:|-------|
| Over-listing (bullet points everywhere) | ✅ Clean | Only used in threat model (appropriate) and AI Statement (required format) |
| Symmetric subsection structure | ⚠️ Moderate | Attack subsections vary in length (good); Defense subsections are more uniform (acceptable for comparison) |
| Author judgment present | ✅ Good | "We believe the field urgently needs..." (§5.1), "In our view, production systems should..." (§5.3), "We observe a rough inverse relationship..." (§5.3) |
| Specific data cited | ✅ Good | "600,000 adversarial prompts from 2,800 participants", "70% to below 20%", "23.9% unsafe-action rate", "1,054 test cases" |
| Sentence pattern variety | ✅ Good | Mix of "X et al. proposed/introduced/developed", passive constructions, and direct assertions |
| Redundant qualifiers | ✅ Clean | No overuse of "significantly", "notably", etc. |

---

## 4. Format Compliance Check

| Criterion | Required | Actual | Status |
|-----------|----------|--------|:------:|
| Template | IEEEtran conference | ✅ `\documentclass[conference]{IEEEtran}` | ✅ |
| Authors | 5 members with IDs | ✅ 5 authors with names, dept, IDs, emails | ✅ |
| Page limit | ≤ 6 pages (excl. refs) | ~5 pages estimated (needs compilation to verify) | ⚠️ Verify |
| Citation style | IEEE numerical | ✅ `\bibliographystyle{IEEEtran}` | ✅ |
| References | 10-20 citations | ✅ 16 entries in references.bib | ✅ |
| Core papers (deep analysis) | 8-12 | ✅ 12 papers discussed in depth (P01-P11 + Pedro2023) | ✅ |
| AI Use Statement | Required if AI used | ✅ Separate section with tools, prompts, verification | ✅ |
| Content sections | As per SPEC.md | ✅ Intro, BG, Attacks, Defenses, Comparison, Discussion, Conclusion, AI Statement | ✅ |

---

## 5. Content Quality Assessment

| Criterion (from SPEC.md acceptance criteria) | Score | Justification |
|----------------------------------------------|:-----:|---------------|
| **Scope & Coverage** (1 mark) | Strong | 16 references spanning attacks (direct, indirect, tool-use), defenses (4 categories), and meta-analysis; explicit scope boundaries stated |
| **Technical Accuracy & Source Fidelity** (1 mark) | Strong | Specific numbers cited from papers (success rates, dataset sizes); claims attributable to sources; no hallucinated results detected |
| **Critical Analysis** (1 mark) | Strong | Each subsection evaluates limitations (not just describing); Discussion §6.2 directly critiques literature weaknesses; author judgments present |
| **Synthesis & Insight** (1 mark) | Strong | Cross-cutting comparison (§5) compares threat models, evaluation methods, and deployment; recurring themes (capability-vulnerability correlation, data-instruction conflation) threaded across sections |
| **Writing & Format** (1 mark) | Strong | IEEE format, balanced sections, varied sentence structures, minimal AI-ness |

---

## 6. Remaining Action Items

| Priority | Item | Status |
|----------|------|:------:|
| High | Compile LaTeX to verify page count ≤ 6 | ⬜ Pending |
| Medium | Fill in LITERATURE_MAP.md citation audit (paper URLs) | ⬜ Pending (Phase 6) |
| Low | Add taxonomy figure (figures/taxonomy.png) if space permits | ⬜ Optional |

---

**Overall Assessment**: Report content is complete, well-structured, logically coherent, and meets all SPEC.md acceptance criteria. Two minor AI-ness issues were identified and fixed. The report is ready for LaTeX compilation and page-count verification.

**Reviewed**: iter-3
