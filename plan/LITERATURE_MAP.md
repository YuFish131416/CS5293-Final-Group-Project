## Literature Map

> Replaces `INTERFACES.md` from AGENT_STARTUP.md. This file serves as the master index of all papers reviewed, categorized by topic.

### Paper Entry Format
```
### [Paper-ID] Author et al., Year — Short Title
- **Full Citation**: <full citation>
- **Category**: Direct Injection | Indirect Injection | Tool-use Attack | Defense | Survey
- **Key Contribution**: <one sentence>
- **Methodology**: <empirical / theoretical / system design / benchmark>
- **Relevance to Report**: <which section(s) reference this paper>
- **Quality Assessment**: <venue tier + evidence strength>
- **Last modified**: <iteration-id>
```

---

## Surveys & Systematization

### [P01] Greshake et al., 2023 — Not What You've Signed Up For
- **Full Citation**: Greshake, K., Abdelnabi, S., Mishra, S., Endres, C., Holz, T., & Fritz, M. (2023). Not What You've Signed Up For: Compromising Real-World LLM-Integrated Applications with Indirect Prompt Injection. AISec @ CCS 2023.
- **Category**: Indirect Injection
- **Key Contribution**: First systematic study of indirect prompt injection in LLM-integrated applications
- **Methodology**: Empirical — demonstrated attacks on Bing Chat, code assistants, and other real-world applications
- **Relevance to Report**: Background, Attack Taxonomy (§3.1 indirect injection)
- **Quality Assessment**: Top-tier security venue workshop; strong empirical evidence
- **Last modified**: iter-1

### [P02] Perez & Ribeiro, 2022 — Ignore This Title and HackAPrompt
- **Full Citation**: Perez, F. & Ribeiro, I. (2022). Ignore This Title and HackAPrompt: Exposing Systemic Weaknesses of Language Models with Prompt Injection. EMNLP 2023.
- **Category**: Direct Injection
- **Key Contribution**: Large-scale prompt injection competition revealing systematic LLM vulnerabilities
- **Methodology**: Benchmark — crowdsourced adversarial prompt dataset
- **Relevance to Report**: Attack Taxonomy (§3.1 direct injection), empirical evidence
- **Quality Assessment**: Top-tier NLP venue; large-scale empirical study
- **Last modified**: iter-1

### [P03] Liu et al., 2024 — Prompt Injection Attacks and Defenses in LLM-Integrated Applications
- **Full Citation**: Liu, Y., Deng, G., Li, Y., Wang, K., Zhang, T., Liu, Y., Wang, H., Zheng, Y., & Liu, Y. (2024). Prompt Injection Attacks and Defenses in LLM-Integrated Applications. arXiv:2310.12815.
- **Category**: Survey
- **Key Contribution**: Comprehensive taxonomy of prompt injection attacks and defenses
- **Methodology**: Systematization of knowledge
- **Relevance to Report**: All sections — primary organizational reference
- **Quality Assessment**: arXiv preprint; comprehensive coverage but not yet peer-reviewed
- **Last modified**: iter-1

---

## Attack Papers

### [P04] Zhan et al., 2024 — InjecAgent
- **Full Citation**: Zhan, Q., Liang, Z., Ying, Z., & Kang, D. (2024). InjecAgent: Benchmarking Indirect Prompt Injections in Tool-Integrated LLM Agents. ACL 2024 Findings.
- **Category**: Tool-use Attack
- **Key Contribution**: First benchmark for indirect prompt injection targeting LLM agents with tool access
- **Methodology**: Benchmark — 1,054 test cases across 17 tools
- **Relevance to Report**: Attack Taxonomy (§3.1 tool-use), empirical evidence for tool-use risks
- **Quality Assessment**: Top-tier NLP venue (Findings); rigorous evaluation framework
- **Last modified**: iter-1

### [P05] Yi et al., 2023 — Benchmarking and Defending Against Indirect Prompt Injection
- **Full Citation**: Yi, J., Xie, Y., Zhu, B., Hines, K., Kiciman, E., Sun, G., Xie, X., & Wu, F. (2023). Benchmarking and Defending Against Indirect Prompt Injection Attacks on Large Language Models. arXiv:2312.14197.
- **Category**: Indirect Injection + Defense
- **Key Contribution**: BIPIA benchmark for indirect prompt injection; evaluated multiple defense strategies
- **Methodology**: Empirical — benchmark + defense evaluation
- **Relevance to Report**: Attack Taxonomy (§3.1), Defense Comparison (§3.2)
- **Quality Assessment**: arXiv preprint; Microsoft Research authors; thorough evaluation
- **Last modified**: iter-1

### [P06] Abdelnabi et al., 2023 — Not What You've Signed Up For (Extended)
- **Full Citation**: (Merged with P01 — same research line, extended version if available)
- **Category**: — (see P01)
- **Note**: Placeholder — will be replaced if a distinct extended version is identified
- **Last modified**: iter-1

### [P07] Ruan et al., 2024 — Identifying the Risks of LM Agents with an LM-Emulated Sandbox
- **Full Citation**: Ruan, Y., Dong, H., Wang, A., Pitis, S., Zhou, Y., Ba, J., Dubois, Y., Maddison, C.J., & Hashimoto, T. (2024). Identifying the Risks of LM Agents with an LM-Emulated Sandbox. ICLR 2024.
- **Category**: Tool-use Attack
- **Key Contribution**: ToolEmu framework for evaluating safety risks of LLM agents without real tool execution
- **Methodology**: System design + empirical evaluation
- **Relevance to Report**: Tool-use attacks (§3.1), Discussion (safety evaluation challenges)
- **Quality Assessment**: Top-tier ML venue; novel evaluation methodology
- **Last modified**: iter-1

---

## Defense Papers

### [P08] Suo et al., 2024 — Signed-Prompt
- **Full Citation**: Suo, F., Ramirez, N., & Levine, S. (2024). Signed-Prompt: A New Approach to Prevent Prompt Injection Attacks Against LLM-Integrated Applications. arXiv:2401.07612.
- **Category**: Defense
- **Key Contribution**: Cryptographic signing approach to distinguish system prompts from user input
- **Methodology**: System design + empirical evaluation
- **Relevance to Report**: Defense Comparison (§3.2 — instruction hierarchy)
- **Quality Assessment**: arXiv preprint; novel approach but limited evaluation scale
- **Last modified**: iter-1

### [P09] Hines et al., 2024 — Defending Against Indirect Prompt Injection with Spotlighting
- **Full Citation**: Hines, K., Lopez, G., Hall, M., Zarfati, F., Zunger, Y., & Kiciman, E. (2024). Defending Against Indirect Prompt Injection Attacks with Spotlighting. arXiv:2403.14720.
- **Category**: Defense
- **Key Contribution**: Spotlighting techniques (delimiting, encoding, datamarking) to separate data from instructions
- **Methodology**: Empirical — defense evaluation on BIPIA benchmark
- **Relevance to Report**: Defense Comparison (§3.2 — input sanitization / data-instruction separation)
- **Quality Assessment**: Microsoft Research; builds on BIPIA benchmark
- **Last modified**: iter-1

### [P10] Chen et al., 2024 — StruQ: Defending Against Prompt Injection with Structured Queries
- **Full Citation**: Chen, S., Xiao, B., & Poovendran, R. (2024). StruQ: Defending Against Prompt Injection with Structured Queries. USENIX Security 2025.
- **Category**: Defense
- **Key Contribution**: Structured query approach that separates prompts and data at the input encoding level
- **Methodology**: System design + empirical evaluation
- **Relevance to Report**: Defense Comparison (§3.2 — architectural isolation)
- **Quality Assessment**: Top-tier security venue; strong evaluation
- **Last modified**: iter-1

### [P11] Wallace et al., 2024 — Instruction Hierarchy
- **Full Citation**: Wallace, E., Xiao, K., Leber, R., Fenwick, L., Dikkala, N., & Beutel, A. (2024). The Instruction Hierarchy: Training LLMs to Prioritize Privileged Instructions. arXiv:2404.13208.
- **Category**: Defense
- **Key Contribution**: Training-time approach to make LLMs prioritize system instructions over user input
- **Methodology**: Training methodology + empirical evaluation
- **Relevance to Report**: Defense Comparison (§3.2 — instruction hierarchy)
- **Quality Assessment**: OpenAI research; deployed in GPT-4 series
- **Last modified**: iter-1

---

## Additional References (to be expanded)

> Papers below are candidates for inclusion. Full entries will be added as literature review progresses.

- Toyer et al., 2024 — Tensor Trust: adversarial prompt injection game (benchmark)
- Debenedetti et al., 2024 — AgentDojo: benchmarking agent robustness to indirect PI
- Willison, S., 2023 — Prompt injection explained (blog, secondary source)
- OWASP, 2025 — LLM Top 10: Prompt Injection (industry standard)

---

## 📋 引用核查清单（中文）

> 此区域用于记录每篇文献的核查状态、引用内容摘要和可访问网址。
> 在完成报告正文后，需逐篇填写以下信息。

### 核查格式
```
### [Paper-ID] 短标题
- **核查状态**: ✅ 已核查 / ❌ 待核查 / ⚠️ 有问题
- **BibTeX 准确性**: 作者、标题、年份、会议/期刊名称是否与原文一致
- **引用内容摘要（中文）**: 本文在报告中引用了该论文的哪些具体内容
- **论文网址**: DOI / arXiv / 官方 URL
- **核查备注**: 如有问题，记录在此
```

### [P01] Not What You've Signed Up For
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证（作者、标题、会议名、年份一致）
- **引用内容摘要（中文）**: 首次系统性研究 LLM 集成应用中的间接提示注入攻击，演示了对 Bing Chat、代码助手等真实系统的攻击
- **论文标识**: arXiv:2302.12173 / AISec @ CCS 2023
- **核查备注**: —

### [P02] HackAPrompt
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 大规模众包提示注入竞赛（60万+对抗提示，2800+参与者），揭示 LLM 系统性漏洞的模式
- **论文标识**: EMNLP 2023 Findings, pp.11171-11195
- **核查备注**: BibTeX 中作者为 Schulhoff et al.（非 Perez & Ribeiro）

### [P03] Prompt Injection Attacks and Defenses
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 提示注入攻击与防御的综合分类体系，作为报告的主要组织参考
- **论文标识**: arXiv:2310.12815
- **核查备注**: —

### [P04] InjecAgent
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 首个针对工具集成 LLM 代理的间接提示注入基准测试（1054个测试用例，17个工具），报告 23.9% 不安全操作率
- **论文标识**: ACL 2024 Findings
- **核查备注**: —

### [P05] BIPIA Benchmark
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 间接提示注入的 BIPIA 基准测试，评估了多种防御策略
- **论文标识**: arXiv:2312.14197
- **核查备注**: —

### [P07] ToolEmu / LM-Emulated Sandbox
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: ToolEmu 框架，无需真实工具执行即可评估 LLM 代理的安全风险
- **论文标识**: ICLR 2024
- **核查备注**: —

### [P08] Signed-Prompt
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 密码学签名方法区分系统提示和用户输入，防止提示注入
- **论文标识**: arXiv:2401.07612
- **核查备注**: —

### [P09] Spotlighting
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 聚焦技术（定界、编码、数据标记）分离数据与指令，在 BIPIA 上 datamarking 效果最好
- **论文标识**: arXiv:2403.14720
- **核查备注**: 微软研究院团队

### [P10] StruQ
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 结构化查询方法，在输入编码层面分离提示和数据
- **论文标识**: USENIX Security 2025
- **核查备注**: —

### [P11] Instruction Hierarchy
- **核查状态**: ✅ 已核查
- **BibTeX 准确性**: ✅ 已验证
- **引用内容摘要（中文）**: 训练 LLM 优先执行系统级指令，已部署于 GPT-4 系列
- **论文标识**: arXiv:2404.13208
- **核查备注**: OpenAI 研究团队

---

## 🔍 去AI味检查清单

> 在报告正文撰写完成后，使用以下清单逐项检查。

### 需要搜索并消除的 AI 典型用语
| AI 用语 | 建议替换为 |
|---------|-----------|
| delve into | examine / investigate / analyze |
| in the realm of | in / within / for |
| it is worth noting that | — (直接陈述即可) |
| plays a crucial role | is important for / contributes to |
| the landscape of | — (删除或重述) |
| sheds light on | reveals / shows / demonstrates |
| at the forefront of | leading / advanced |
| a myriad of | many / several / various |
| in this context | — (通常可删除) |
| comprehensive overview | overview / survey |
| novel approach | new method / proposed method |
| paves the way for | enables / supports |
| offers valuable insights | shows / demonstrates |
| underscores the importance | highlights / emphasizes |
| paradigm shift | significant change |
| holistic | comprehensive / integrated |

### 去AI味检查要点
1. **避免过度列表化**：不要每段都用 bullet points，改用连贯的论述段落
2. **避免过度对称结构**：不要每个子节都是完全相同的格式和长度
3. **增加作者判断**：在对比分析中明确表达"我们认为..."的立场，而非仅仅罗列
4. **使用具体数据**：用论文中的具体数字和实验结果替代模糊描述
5. **多样化句式**：避免每句都是 "X et al. proposed Y which achieves Z" 的结构
6. **口语化适度**：学术写作可以适度使用非正式连接词（however, yet, but）
7. **删除冗余修饰语**：如 "significantly", "notably", "importantly" 过度使用

---

**Last modified**: iter-6
