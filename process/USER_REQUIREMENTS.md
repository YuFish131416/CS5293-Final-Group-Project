# 用户需求记录

> 记录于: 2026-04-08

## 用户约定

### 0. 工作流程约定
- 首先阅读 `AGENT_STARTUP.md` 理解工作流程规范
- 所有过程文件记录在 `process/` 中，防止遗忘

### 1. 需求澄清阶段
- Agent 必须先不断向用户提问，明确需求、难度、工作量适配
- 直到完全没有问题为止，才能进入下一阶段

### 2. 规划阶段（需求确认后）
- 生成 `SPEC.md` 记录：项目目标、功能列表、非目标（明确不做什么）、技术约束、验收标准
- 参照 `AGENT_STARTUP.md` 生成 `process/`、`plan/`、`review/` 文件夹及其下属 markdown 文件

### 3. 实施阶段（规划完成后）
- 开始书写代码、README.md、操作步骤等一系列后续流程和交付文件

## 项目基本信息（来自 CS5293_Group_Project.pdf）

### 课程
- CS5293: Topics on Information Security
- 期末小组项目（Final Group Project）

### 团队
- 5 人小组

### 重要日期
| 日期 | 事项 |
|------|------|
| April 17, 2026 | 团队注册 + 主题提交 |
| May 7, 2026 | 幻灯片提交 (PDF) |
| May 8, 2026 | 课堂演示 (5分钟 + 2分钟Q&A) |
| May 10, 2026 | 最终报告提交 (PDF) |

### 项目性质
- **文献综述型项目**（Literature Survey），不是编码项目
- 阅读、组织文献，解释核心技术思想，比较假设和局限性，进行批判性综合分析
- 交付物：IEEE 格式报告（最多6页双栏，不含参考文献）+ 幻灯片

### 评估标准
- 报告 (5 分): 范围覆盖(1) + 技术准确性(1) + 批判分析(1) + 综合洞察(1) + 写作格式(1)
- 演示 (6 分): 主题动机(1) + 技术准确性(1) + 组织清晰(1) + 表达(1) + 协调时间管理(1) + 幻灯片+Q&A(1)

### 可选主题（附录 A）
- Module 1: 应用密码学 (Topics 1-4)
- Module 2: 系统安全与访问控制 (Topics 5-9)
- Module 3: 网络安全 (Topics 10-12)
- Module 4: Web 与应用安全 (Topics 13-16)
- Module 5: AI 安全与新兴话题 (Topics 17-30)

## Clarification Results (2026-04-08)

### Topic
- **Topic 17: Prompt Injection and Tool-use Attacks in LLM Applications**
- Reason: Low barrier for dev-background team, hot topic with abundant literature, demo-friendly

### Team Profile
- 5 members, mainly development background, basic security knowledge
- Difficulty expectation: B/C (medium to efficient)

### Deliverable Preferences
- Focus on literature survey (not coding project)
- Demo: prefer runnable script (A), fallback to screenshots (B), then pure literature (C)
- All English documentation
- Agent decides work division

### No Excluded Topics

## Current Status
- [x] Requirements clarification — COMPLETED
- [x] Project framework setup (SPEC.md + plan/ + process/) — COMPLETED
- [ ] Report skeleton — IN PROGRESS
- [ ] Report content writing — PENDING
- [ ] Demo implementation — PENDING
- [ ] Slides creation — PENDING
- [ ] Review & finalization — PENDING
