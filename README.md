# LLM 应用中的 Prompt Injection 与 Tool-use 攻击：文献综述

> **CS5293 信息安全专题 — 期末小组项目**
> **Topic 17**: Prompt Injection and Tool-use Attacks in LLM Applications
> **团队成员**: 余沛翰、胡薛林、翁梓严、邓乐盈、赵海超

---

## 📌 项目概述

本项目是一篇关于 **LLM（大语言模型）应用中的提示注入攻击与工具利用攻击** 的文献综述。我们系统性地分析了三类攻击家族（直接注入、间接注入、工具利用攻击）和四类防御机制（输入过滤、指令层级、输出监测、架构隔离），并对现有文献进行了批判性的交叉比较。

---

## 📅 截止日期

| 日期 | 交付物 | 提交方式 |
|------|--------|---------|
| 2026年4月17日 | 团队注册 + 选题确认 | 邮件发送至 TA |
| 2026年5月7日 | 幻灯片 PDF | CANVAS 提交 |
| 2026年5月8日 | 课堂演示（5分钟 + 2分钟 Q&A） | 到场演讲 |
| 2026年5月10日 | 报告 PDF | CANVAS 提交 |

---

## 👥 分工方案

| 成员 | 文献负责领域 | 报告章节 | 幻灯片 |
|------|-------------|---------|--------|
| **余沛翰**（协调人） | 综述概述 + 分类体系 | Introduction + Conclusion | Slides 1-3（开场） |
| **胡薛林** | 直接 Prompt Injection | Background（攻击类型） | Slide 4（背景+威胁模型） |
| **翁梓严** | 间接 Prompt Injection | Main Analysis: 攻击分类 | Slides 5-7（攻击深入分析） |
| **邓乐盈** | 防御机制 | Main Analysis: 防御对比 | Slides 8-9（防御对比） |
| **赵海超** | Tool-use 攻击 + Demo | Discussion + Demo | Slides 10-12（Demo + Q&A） |

---

## 📂 文件架构说明

> 💡 **给协作者的提示**：你只需要关注自己负责的文件。编辑前请先 `git pull` 获取最新版本，编辑完成后及时 `git add + commit + push`。

```
project-root/
│
├── README.md                            ← 【本文件】项目说明，协作指引
├── SPEC.md                              ← 项目规格书：目标、功能列表、验收标准
├── .gitignore                           ← Git 忽略规则
│
├── report/                              ← 📝 【核心】LaTeX 报告源文件
│   ├── main.tex                         ← 报告主文件（导入各章节，不需要直接编辑内容）
│   ├── IEEEtran.cls                     ← IEEE 模板类文件（⚠️ 不要修改）
│   ├── references.bib                   ← 参考文献 BibTeX 条目（所有引用都在这里）
│   ├── figures/                         ← 报告用图片
│   └── sections/                        ← 各章节独立文件 ⭐ 编辑报告内容在这里
│       ├── introduction.tex             ← 引言：问题定义、动机、研究范围 【余沛翰】
│       ├── background.tex               ← 背景：LLM 架构、工具调用、威胁模型 【胡薛林】
│       ├── analysis_attacks.tex         ← 攻击分类：直接/间接/工具利用 【翁梓严】
│       ├── analysis_defenses.tex        ← 防御机制：过滤/层级/监测/隔离 【邓乐盈】
│       ├── analysis_comparison.tex      ← 交叉比较：威胁模型/评估方法/部署可行性 【邓乐盈】
│       ├── discussion.tex               ← 讨论：核心发现、文献局限、开放问题 【赵海超】
│       ├── conclusion.tex               ← 结论 【余沛翰】
│       └── ai_statement.tex             ← AI 使用声明 【余沛翰】
│
├── slides/                              ← 🎬 幻灯片
│   ├── slides.pptx                      ← 最终幻灯片（12张，5分钟演示）
│   └── build_slides.js                  ← 幻灯片生成脚本（PptxGenJS）
│
├── src/demo/                            ← 🔧 Prompt Injection 演示脚本
│   ├── prompt_injection_demo.py         ← Python 演示：4个场景（2直接 + 2间接注入）
│   ├── requirements.txt                 ← Python 依赖
│   └── README.md                        ← Demo 使用说明
│
├── plan/                                ← 📋 项目知识库（管理文档）
│   ├── PROJECT_OVERVIEW.md              ← 项目目标和功能列表
│   ├── ARCHITECTURE.md                  ← 报告逻辑架构和文献组织框架
│   ├── LITERATURE_MAP.md                ← 文献索引和分类（含引用核查清单）
│   ├── COMPARISON_FRAMEWORK.md          ← 论文比较矩阵
│   ├── CONSTRAINTS.md                   ← 技术约束和格式要求
│   ├── DIR_MAP.md                       ← 目录结构说明
│   ├── ITERATION_LOG.md                 ← 迭代日志（每次变更记录）
│   ├── CHANGELOG.md                     ← 变更日志（面向人类阅读）
│   ├── TECH_DEBT.md                     ← 已知问题和待办事项
│   └── API_CHANGELOG.md                 ← 保留字段（本项目不适用）
│
├── process/                             ← 📊 进度跟踪
│   ├── PROGRESS.md                      ← 里程碑检查清单
│   ├── CURRENT_TASK.md                  ← 当前任务状态
│   └── USER_REQUIREMENTS.md             ← 原始需求记录
│
├── review/                              ← 🔍 自审文档
│   └── REVIEW_iter-*.md                 ← 每次迭代的审查报告
│
├── docs/                                ← 📦 最终交付物（编译后的 PDF）
│
├── Template/                            ← 📄 IEEE 模板参考（⚠️ 不要修改）
│
└── tmp/                                 ← 临时文件（已 gitignore）
```

---

## 🔨 如何编译报告

### 环境要求
- LaTeX 发行版（TeX Live 或 MiKTeX）
- `latexmk`（推荐）或手动 `pdflatex` + `bibtex`

### 编译命令
```bash
cd report/
latexmk -pdf main.tex
```

或手动编译：
```bash
cd report/
pdflatex main
bibtex main
pdflatex main
pdflatex main
```

编译后的 PDF 位于 `report/main.pdf`，最终提交时复制到 `docs/report.pdf`。

---

## 🔧 如何运行 Demo

### 模拟模式（默认，无需任何依赖）
```bash
cd src/demo/
python prompt_injection_demo.py
```

### 实际 API 模式（需要 OpenAI API Key）
```bash
cd src/demo/
pip install -r requirements.txt
export OPENAI_API_KEY="你的密钥"
python prompt_injection_demo.py --live
```

### 运行指定场景
```bash
python prompt_injection_demo.py --scenario 1    # 只运行场景1
python prompt_injection_demo.py --json           # JSON 格式输出
```

详细说明见 `src/demo/README.md`。

---

## 📚 核心引用文献列表

> 以下为本项目引用的 16 篇文献。BibTeX 条目见 `report/references.bib`，详细分析见 `plan/LITERATURE_MAP.md`。

### 攻击类论文

| 编号 | 论文 | 类别 | 简要说明 | 标识信息 |
|------|------|------|---------|---------|
| P01 | Greshake et al., 2023 | 间接注入 | 首次系统性研究 LLM 集成应用中的间接提示注入攻击，在 Bing Chat 等真实系统上演示 | arXiv:2302.12173 |
| P02 | Schulhoff et al., 2023 | 直接注入 | HackAPrompt 大规模众包提示注入竞赛，揭示 LLM 系统性漏洞模式 | EMNLP 2023, pp.11171-11195 |
| P03 | Liu et al., 2024 | 综述 | 提示注入攻击与防御的综合分类体系 | arXiv:2310.12815 |
| P04 | Zhan et al., 2024 | 工具使用攻击 | InjecAgent: 首个针对工具集成 LLM 代理的间接注入基准（1054 测试用例） | ACL 2024 Findings |
| P05 | Yi et al., 2023 | 间接注入+防御 | BIPIA 间接提示注入基准测试与防御评估 | arXiv:2312.14197 |
| P07 | Ruan et al., 2024 | 工具使用攻击 | ToolEmu: 无需真实工具的 LLM 代理安全评估框架 | ICLR 2024 |
| P12 | Toyer et al., 2024 | 直接注入 | Tensor Trust: 可解释的提示注入攻击在线游戏基准 | ICLR 2024 |
| P13 | Debenedetti et al., 2024 | 工具使用攻击 | AgentDojo: 评估 LLM 代理提示注入攻防的动态环境 | arXiv:2406.13352 |
| P14 | Pedro et al., 2023 | 间接注入 | 从 Prompt Injection 到 SQL Injection: LLM 集成 Web 应用的安全性 | arXiv:2308.01990 |

### 防御类论文

| 编号 | 论文 | 类别 | 简要说明 | 标识信息 |
|------|------|------|---------|---------|
| P08 | Suo et al., 2024 | 防御 | Signed-Prompt: 密码学签名区分系统提示和用户输入 | arXiv:2401.07612 |
| P09 | Hines et al., 2024 | 防御 | Spotlighting: 聚焦技术（定界/编码/数据标记）分离数据与指令 | arXiv:2403.14720 |
| P10 | Chen et al., 2025 | 防御 | StruQ: 结构化查询在编码层面分离提示和数据 | USENIX Security 2025 |
| P11 | Wallace et al., 2024 | 防御 | Instruction Hierarchy: 训练 LLM 优先执行系统级指令，已部署于 GPT-4 | arXiv:2404.13208 |

### 补充文献

| 编号 | 论文 | 类别 | 简要说明 | 标识信息 |
|------|------|------|---------|---------|
| — | Willison, 2023 | 科普 | Prompt Injection 概念解释（博客文章） | simonwillison.net/2023/prompt-injection/ |
| — | OWASP, 2025 | 标准 | OWASP Top 10 for LLM Applications: Prompt Injection 排名第一 | genai.owasp.org/llm-top-10/ |
| — | Achiam et al., 2023 | 技术报告 | GPT-4 Technical Report | arXiv:2303.08774 |

---

## 🤝 协作者指引（Git 工作流程）

### 基本流程

1. **拉取最新代码**
   ```bash
   git pull origin main
   ```

2. **创建你的工作分支**（推荐）
   ```bash
   git checkout -b feature/你的名字-你的任务
   # 例如: git checkout -b feature/ziyan-attack-section
   ```

3. **编辑你负责的文件**（见下方分工表）

4. **提交并推送**
   ```bash
   git add .
   git commit -m "描述你的修改内容"
   git push origin feature/你的分支名
   ```

5. **提交 Pull Request 或直接合并到 main**

### 每人需要关注的文件

| 成员 | 主要编辑文件 | 说明 |
|------|-------------|------|
| **余沛翰** | `report/sections/introduction.tex` | 引言章节 |
|  | `report/sections/conclusion.tex` | 结论章节 |
|  | `report/sections/ai_statement.tex` | AI 使用声明 |
|  | `report/main.tex` | 报告主文件（通常不需要改） |
|  | `README.md` | 项目说明 |
| **胡薛林** | `report/sections/background.tex` | 背景章节（LLM 基础、威胁模型） |
| **翁梓严** | `report/sections/analysis_attacks.tex` | 攻击分类章节 |
| **邓乐盈** | `report/sections/analysis_defenses.tex` | 防御机制章节 |
|  | `report/sections/analysis_comparison.tex` | 交叉比较章节 |
| **赵海超** | `report/sections/discussion.tex` | 讨论章节（核心发现、开放问题） |
|  | `src/demo/prompt_injection_demo.py` | Demo 脚本 |
|  | `slides/slides.pptx` | 幻灯片 |

### 常见 Git Issue 处理

#### ❓ 合并冲突
如果 `git pull` 时遇到冲突：
```bash
# 查看冲突文件
git status

# 手动编辑冲突文件，搜索 <<<<<<< 标记并解决
# 然后：
git add 冲突文件
git commit -m "resolve merge conflict in 文件名"
```

#### ❓ 不小心修改了别人的文件
```bash
# 撤销对某个文件的修改
git checkout -- report/sections/别人的文件.tex
```

#### ❓ 想查看某个文件的修改历史
```bash
git log --oneline report/sections/你的文件.tex
```

#### ❓ LaTeX 编译报错
- 先确保 `references.bib` 中的引用 key 和正文中的 `\cite{key}` 一致
- 检查是否有未闭合的 `{}` 或 `\begin{}`/`\end{}` 配对
- 尝试清理编译缓存后重新编译：
  ```bash
  cd report/
  latexmk -C
  latexmk -pdf main.tex
  ```

---

## ✅ AI 使用说明

本项目在以下环节使用了 AI 工具辅助：

| 环节 | AI 参与程度 | 说明 |
|------|-----------|------|
| **文献检索** | ✅ AI 辅助 | 生成搜索关键词，筛选候选论文 |
| **报告核心大纲** | ❌ 人工完成 | 分析框架、攻击/防御分类、论证逻辑由团队独立设计 |
| **报告撰写** | ❌ 人工完成 | 各章节初稿由负责人独立撰写 |
| **语言润色** | ✅ AI 辅助 | 初稿完成后使用 AI 改善语法和表达 |
| **引用核查** | ✅ AI 辅助 | 验证 BibTeX 条目准确性、引用内容与原文一致性 |

详细的 AI 使用声明见报告中的 AI Use Statement 章节。

---

## 📜 学术诚信

- 所有借用的观点、图表和文本均已正确引用
- AI 工具仅用于辅助角色（检索、润色、核查），核心学术内容为人工完成
- 详细规则见 `SPEC.md`
- 本项目仅用于学术用途，不得转载或重新分发
