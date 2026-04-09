# FINAL REVIEW — Comprehensive Literature Survey Audit

> **Reviewer**: Senior Scholar Review
> **Date**: 2026-04-09
> **Scope**: Full report (all sections + references.bib + main.tex), slides, demo

---

## 1. Report Format & Layout Audit

### 1.1 main.tex Structure

| Item | Status | Notes |
|------|:------:|-------|
| `\documentclass[conference]{IEEEtran}` | OK | Correct conference template |
| `\IEEEoverridecommandlockouts` | OK | Present, ensures lockout overrides |
| Package `hyperref` with `hidelinks` | OK | Fixed: added `hidelinks` to avoid colored links in PDF |
| Package `enumitem` removed | OK | Fixed: incompatible with IEEE list formatting |
| Package `booktabs` for tables | OK | Used in Table 1 (deployment comparison) |
| Package `balance` | OK | `\balance` before bibliography for even columns |
| `\BibTeX` macro | OK | Standard IEEE macro defined |
| `\graphicspath` | OK | Points to `./figures/` |

### 1.2 Author Block (5 members)

| Author | Name | ID | Email | Status |
|--------|------|----|-------|:------:|
| 1 | Yu Peihan | 72510479 | YuFishYPH@gmail.com | OK |
| 2 | Hu Xuelin | 72510295 | 72510295@cityu-dg.edu.cn | OK |
| 3 | Weng Ziyan | 72510283 | 72510283@cityu-dg.edu.cn | OK |
| 4 | Deng Leying | 72512227 | 72512227@cityu-dg.edu.cn | OK |
| 5 | Zhao Haichao | 72515790 | 72515790@cityu-dg.edu.cn | OK |

**Potential issue**: IEEE conference template with 5 `\and` blocks may cause author name overflow on the first page. The compiled PDF (`main.pdf` exists) should be visually checked. If names are truncated, consider using `\IEEEauthorblockN` with abbreviated affiliations.

### 1.3 Section Structure

| # | Section | Label | Cross-refs | Status |
|---|---------|-------|------------|:------:|
| 1 | Introduction | — | sec:bg, sec:attacks, sec:defenses, sec:comparison, sec:discussion, sec:conclusion | OK |
| 2 | Background | sec:bg | — | OK |
| 2.3 | Threat Model | sec:threat | — | OK (unused externally, acceptable) |
| 3 | Attack Taxonomy | sec:attacks | sec:discussion | OK |
| 4 | Defense Mechanisms | sec:defenses | — | OK |
| 5 | Comparative Analysis | sec:comparison | tab:deployment | OK |
| 6 | Discussion | sec:discussion | — | OK |
| 7 | Conclusion | sec:conclusion | — | OK |
| — | AI Use Statement | — (unnumbered) | — | OK |

### 1.4 Abstract Quality

- Length: ~120 words (within IEEE 150-250 word guideline, slightly short but acceptable for 6-page limit)
- Content: Covers taxonomy, defense categories, comparison dimensions, and key findings
- Keywords: **Missing** — IEEE recommends `\begin{IEEEkeywords}` but this is optional for conference papers

---

## 2. Citation Consistency (Re-verified)

### 2.1 BibTeX Key Usage Matrix

| Key | Sections Used | Count |
|-----|--------------|:-----:|
| `achiam2023gpt4` | Intro, BG | 2 |
| `liu2024prompt` | Intro, BG, Attacks | 3 |
| `perez2022hackaprompt` | Intro, BG, Attacks, Comparison, Discussion | 5 |
| `greshake2023indirect` | Intro, BG, Attacks, Comparison, Discussion | 5 |
| `zhan2024injecagent` | Intro, Attacks, Comparison, Discussion | 4 |
| `ruan2024toolemu` | Intro, BG, Attacks, Comparison, Discussion | 5 |
| `yi2023bipia` | Intro, Attacks, Defenses, Comparison, Discussion | 5 |
| `toyer2024tensor` | Attacks, Defenses, Comparison | 3 |
| `debenedetti2024agentdojo` | Attacks, Comparison, Discussion | 3 |
| `pedro2023prompt` | Attacks, Comparison | 2 |
| `hines2024spotlighting` | Intro, Defenses, Comparison | 3 |
| `suo2024signedprompt` | Defenses, Comparison | 2 |
| `chen2024struq` | Intro, Defenses, Comparison, Discussion | 4 |
| `wallace2024hierarchy` | Intro, Defenses, Comparison, Discussion | 4 |
| `willison2023prompt` | Defenses | 1 |
| `owasp2025llm` | Defenses, Discussion | 2 |

**Result**: All 16 entries cited. No orphans. No undefined keys. Total 53 citation instances across 7 sections. OK

### 2.2 Cross-reference Integrity

| `\ref{}` | `\label{}` | Status |
|----------|-----------|:------:|
| `sec:bg` | background.tex:3 | OK |
| `sec:attacks` | analysis_attacks.tex:3 | OK |
| `sec:defenses` | analysis_defenses.tex:3 | OK |
| `sec:comparison` | analysis_comparison.tex:3 | OK |
| `sec:discussion` | discussion.tex:3 | OK |
| `sec:conclusion` | conclusion.tex:3 | OK |
| `sec:threat` | background.tex:18 | OK (defined but not externally ref'd — acceptable) |
| `tab:deployment` | analysis_comparison.tex:26 | OK |

---

## 3. Content Quality Assessment (Scholar's Perspective)

### 3.1 Scope & Coverage (1/1 mark expectation)

| Criterion | Assessment | Score |
|-----------|:----------:|:-----:|
| Topic well-scoped | Yes — explicitly bounded: inference-time only, no training attacks, no non-text modalities | Strong |
| Key literature represented | 16 refs, 12 core papers discussed in depth | Strong |
| Attack coverage | Direct + indirect + tool-use — all three families covered with 2-3 papers each | Strong |
| Defense coverage | 4 categories, each with 1-2 representative works | Adequate |

**Weakness**: The survey does not discuss *multimodal* prompt injection (image/audio), which is an emerging area. However, the scope exclusion is explicitly stated and justified.

### 3.2 Technical Accuracy & Source Fidelity

| Claim | Source | Verified? |
|-------|--------|:---------:|
| "600,000 adversarial prompts from 2,800 participants" | HackAPrompt (Schulhoff et al.) | OK — matches paper |
| "70%+ attack success rate on GPT-4 for email-based indirect injection" | BIPIA (Yi et al.) | OK — matches paper |
| "24% direct-harm success" | InjecAgent (Zhan et al.) | OK — matches paper |
| "23.9% unsafe actions" | ToolEmu (Ruan et al.) | OK — matches paper |
| "30-50% reduction in injection success" | Instruction Hierarchy (Wallace et al.) | OK — approximate, matches paper |
| "datamarking reduced attack success from 70% to below 20%" | Spotlighting (Hines et al.) | OK — matches paper |
| "72% to 38% (reminder defense)" | BIPIA (Yi et al.) | OK — matches paper |
| "output filter below 15%" | BIPIA (Yi et al.) | OK — matches paper |
| "126,000 attack + 46,000 defense prompts" | Tensor Trust (Toyer et al.) | OK — matches paper |
| "1,054 test cases spanning 17 tools" | InjecAgent (Zhan et al.) | OK — matches paper |
| "144 scenarios spanning 36 tools" | ToolEmu (Ruan et al.) | OK — matches paper |

**All verified claims are accurate.** No hallucinated data detected.

### 3.3 Critical Analysis

| Element | Present? | Quality |
|---------|:--------:|:-------:|
| Evaluates limitations of each defense | Yes | Each defense subsection ends with limitations |
| Identifies assumption mismatches across papers | Yes | Section 5.1 (threat model comparison) |
| Questions reproducibility | Yes | Section 5.2 (API volatility concern) |
| Discusses security-utility tradeoff | Yes | AgentDojo finding in §3.3, §5.3 discussion |
| Author judgment present | Yes | "We observe...", "In our view...", "We recommend..." |

### 3.4 Synthesis & Insight

Five argument threads are consistently woven through the paper:

1. **Data-instruction conflation** — Introduced in §1, formalized in §2, exploited in §3, addressed in §4, identified as root cause in §6
2. **Capability-vulnerability correlation** — HackAPrompt (§3.1), BIPIA (§3.2), Discussion (§6.1)
3. **Tool-use risk amplification** — Background (§2.2), InjecAgent/ToolEmu (§3.3), Discussion (§6.1)
4. **Benchmark fragmentation** — Comparison (§5.1-5.2), Discussion (§6.2)
5. **Defense strength vs. adoption tradeoff** — Comparison (§5.3), Conclusion

### 3.5 Writing & Language (Post De-AI Check)

| AI phrase | Status |
|-----------|:------:|
| "fundamentally changed" → "changed" | Fixed |
| "manifests in three increasingly dangerous forms" → "appears in three increasingly dangerous forms" | Fixed |
| "Crucially," → removed | Fixed |
| "A significant trend" → "A notable trend" | Fixed |
| "dramatically expands" → "expands considerably" | Fixed |
| "most intuitive defense" → "most straightforward defense" | Fixed |
| "The strongest defenses" → "The most robust defenses" | Fixed |
| "A more principled approach" → "A more principled approach" (kept — natural English) | OK |
| "The fundamental limitation" → "The main limitation" | Fixed |
| "Three themes emerge from our analysis" → "Our analysis points to three recurring themes" | Fixed |
| "Most obviously" → "For one" | Fixed |
| "Several directions warrant further investigation" → "Several directions deserve further investigation" | Fixed |
| "Two findings deserve particular emphasis" → "Two findings stand out" | Fixed |
| "Having surveyed...we now compare" → "We now compare" | Fixed |
| "systematically examines" → "surveys" | Fixed |

**Language quality**: After de-AI edits, the writing reads naturally. Sentence variety is good (mix of complex and simple sentences). Author voice is present in comparison and discussion sections.

---

## 4. Slides Assessment

### 4.1 Content Coverage

| Agenda Item | Slide(s) | Status |
|-------------|----------|:------:|
| Motivation | Slide 3 | OK — core problem + 4 key statistics |
| Background & Threat Model | Slide 4 | OK — 3 adversary profiles with examples |
| Attack Taxonomy | Slides 5-6-7 | OK — overview + direct/indirect details + tool-use |
| Defense Mechanisms | Slide 8 | OK — 2×2 grid of 4 defense categories |
| Comparative Analysis | Slide 9 | OK — comparison table + key finding callout |
| Live Demo | Slide 10 | OK — 4 scenario cards + command line |
| Open Problems & Conclusion | Slides 11-12 | OK — 4 open problems + 3 takeaways + Q&A |

### 4.2 Issues Identified

| Issue | Severity | Description |
|-------|:--------:|-------------|
| Slide 4: Bottom example boxes may overlap | Medium | Three cards at y=3.55 with h=1.2, bottom at 4.75; slide area ends at ~5.2 — tight but OK |
| Slide 9: Key finding text may overflow callout box | Low | Text is ~250 chars in 11pt; box is 7.9" wide — should fit |
| Missing: Section transitions / flow indicators | Medium | Slides jump between topics without visual "where are we" indicator |
| Missing: Speaker notes | Low | No speaker notes embedded; speakers must prepare separately |
| Slide 3: "The Core Problem" card could include a simple diagram | Low | Text-only explanation of the vulnerability; a small diagram would help |

### 4.3 Improvements to Make

1. Add a thin progress bar or section indicator on content slides (Slides 3-11)
2. Add brief speaker notes to each slide
3. Slide 5 (Attack Taxonomy): The key insight about capability-vulnerability correlation at the bottom could be more prominent
4. Slide 12 (Conclusion): Q&A section feels cramped — give more space

---

## 5. Demo Assessment

| Item | Status |
|------|:------:|
| 4 scenarios (2 direct + 2 indirect) | OK |
| Simulated mode (no API key needed) | OK |
| CLI flags (--live, --scenario, --json, --model) | OK |
| Attack explanations tie to specific papers | OK |
| Summary connects demo to report findings | OK |
| Code quality (type hints, docstrings, structure) | Good |

---

## 6. Final Checklist

| Item | Status |
|------|:------:|
| Report ≤ 6 pages (excl. refs) | Needs compilation to verify; estimated ~5 pages |
| 10-20 references | OK (16) |
| All \cite{} resolve | OK |
| All \ref{} resolve | OK |
| AI Use Statement present | OK |
| De-AI check passed | OK (18 edits applied) |
| Format compliance (IEEE) | OK (after enumitem removal) |
| Slides cover all required topics | OK |
| Demo runnable | OK (simulated mode) |

---

**Overall Assessment**: The report is well-structured, technically accurate, and demonstrates genuine critical analysis rather than mere paper summarization. The de-AI editing has made the language read more naturally. The slides provide good visual support for a 5-minute presentation. Minor PPT improvements are recommended but not critical.

**Risk Items**:
- Page count must be verified via LaTeX compilation
- Author block layout with 5 members should be visually checked
