# life-coach · 人生教练

> AI 人生教练技能（WorkBuddy Skill）：通过冰山深度对话 + 多心理学模型交叉验证 + 原创整合题库，帮用户**看见天赋、理清自我、找到匹配的职业/事业/创业方向，并给出可落地的执行路径**。
>
> An AI life-coach skill that helps people *see their talents, clarify themselves, and find a fitting career / business direction* — through iceberg deep-dialogue, multi-model cross-validation, and an original integrated item bank.

**formerly known as `self-discovery-coach`** · current version **1.4**

---

## 目录 · Table of Contents

- [这是什么 · What is this](#这是什么--what-is-this)
- [核心理念 · Core Philosophy](#核心理念--core-philosophy)
- [核心能力 · Key Features](#核心能力--key-features)
- [11 种模式 · 11 Modes](#11-种模式--11-modes)
- [快速开始 · Quick Start](#快速开始--quick-start)
- [安装 · Installation](#安装--installation)
- [目录结构 · Directory Structure](#目录结构--directory-structure)
- [原创题库与版权 · Item Bank & License](#原创题库与版权--item-bank--license)
- [版本历史 · Changelog](#版本历史--changelog)

---

## 这是什么 · What is this

`life-coach` 不是一份冷冰冰的测评报告生成器，而是一个**持续陪伴的 AI 人生教练**。它整合了 MBTI、VIA、克利夫顿（盖洛普）优势、DISC、霍兰德、AQAL 等 20+ 心理学模型，通过有引导的深度对话，陪伴用户潜入自己的"冰山底层"——从水面上的行为，一路挖到天赋、价值观、信念、身份、恐惧与潜能。

`life-coach` is not a cold assessment generator. It is a *companion AI life coach* that blends 20+ psychology models (MBTI, VIA, CliftonStrengths, DISC, Holland, AQAL…) and uses guided dialogue to help users dive into their personal "iceberg" — from surface behaviors down to talents, values, beliefs, identity, fears and potential.

它和"做题测人格"最大的不同：**对话中就能识别天赋**，且在聊天过程里会自动插入轻量题验证、排序你的天赋（盖洛普式前 N），最后把天赋映射到具体行业/角色，并给出差距分析与落地 Playbook。

Unlike "answer quizzes to get a type", it *recognizes talent from conversation*, and can insert lightweight questions mid-chat to validate and rank your talents (Gallup-style Top-N), then map them to concrete industries/roles with gap analysis and an actionable Playbook.

---

## 核心理念 · Core Philosophy

1. **优势导向 · Strengths-Based**
   不是帮用户"修补短板"，而是发现并放大已经存在的天赋。天赋 × 投入 = 优势。
   Discover and amplify existing talents rather than fixing weaknesses. *Talent × Investment = Strength.*

2. **超越模型 · Beyond Models**
   任何单一模型都有盲区（MBTI 看不到价值观，DISC 看不到天赋）。AI 同时持有多模型，看到模型之间、模型之外、以及模型缝隙中流动的真相。
   Every single model is blind somewhere. The AI holds multiple models at once and sees what lies *between and beyond* them.

3. **冰山深度对话 · Iceberg Deep Dialogue**
   不做选择题，而是通过对话逐层深入：行为 → 应对 → 感受/天赋 → 价值观 → 身份 → 渴望/恐惧 → 潜能 → 盲区。
   No multiple-choice. Dialogue dives layer by layer: Behavior → Coping → Feeling/Talent → Values → Identity → Desire/Fear → Potential → Blind spot.

---

## 核心能力 · Key Features

- **对话式天赋识别 · Talent recognition from talk**
  无需做题，从用户的自然叙述中捕捉"天赋早期信号"（"我最享受…""我能看透别人看不到的…"），并持有多模型同时识别多种天赋倾向。

- **原创整合题库 · Original integrated item bank**（v1.4 新增）
  五大模型全部题项化：MBTI 12 题 / VIA 10 组配对 / 克利夫顿 16 场景 / DISC 8 题 / 霍兰德 12 题。统一计分输出**前 N 排序**（VIA/克利夫顿 Top5、霍兰德三位码、MBTI 类型、DISC 主+次型）。

- **对话中自动路由插题 · Adaptive question routing**（v1.4 新增）
  聊天中检测到某模型维度信号，自动插入对应轻量题验证/排序（单题 / 模块 / 全量三档），不打断对话流；用户说"先不测"立刻回聊。

- **三模型协同 · Three-model synergy**
  冰山（看见） + 理解六层次（定位） + AQAL 四象限（安放）同步运行。AI 提问层 = 用户表达层 + 1 个理解层次，逐层深入但不跳层。

- **职业落地闭环 · Career landing loop**
  职业映射 → 差距分析（量化能力/时间/资金三类缺口 + 相邻替代方向） → 行业落地 Playbook（Top 8 高频方向，含 3 个月周计划、信息访谈、作品集方案、验证里程碑） → 真实市场数据校验（门槛/薪资/趋势/雇主/切入路径）。

- **中文职场语境 · Chinese workplace context**
  内置考公、大厂、35 岁危机、AI 转行、副业转主业、一线 vs 家乡、家庭责任、创业、自由职业等 9 类场景与教练话术，不硬套西方个人主义叙事。

- **安全护栏 · Safety guardrails**
  - 不主动写文件、不输出结构化 JSON、不识别 user_id（数据隔离由部署平台负责）。
  - 识别到心理创伤信号时**只陪伴、不给方向、建议转介**，不冒充咨询师。
  - 任何"类型 → 职业"结论都附"概率性参考，不是鉴定"，并走反伪精确与反幻觉校验。
  - 三态置信分级：对话推断(低) / 题型库结果(中) / 官方真测评(高)，冲突时优先级 真测评 > 题型库 > 对话推断。

---

## 11 种模式 · 11 Modes

| # | 模式 Mode | 触发词 Triggers | 技能会做什么 What it does |
|---|-----------|----------------|---------------------------|
| 1 | 完整测评 Full Assessment | 了解自己 / 完整测评 | 冰山 8 层对话 + 多模型画像，逐层深入 |
| 2 | 快速画像 Quick Profile | 快速看 / 简单了解 | 轻量盘点，给方向性感觉 |
| 3 | 单模型测评 Single Model | 测 MBTI / 测霍兰德 | 只跑一个模型，给维度倾向 |
| 4 | 交叉分析 Cross Analysis | 帮我串起来 / 整合 | 多模型交叉验证 + 张力点 + AQAL + 反幻觉 |
| 5 | 对比分析 Comparison | 对比 / 我们合适吗 | 双人/团队维度对比，给互补与冲突预警 |
| 6 | 发展追踪 Progress Tracking | 重新测 / 我变了 | 读历史档案，画变化时间线 |
| 7 | 场景模拟 Scenario Simulation | 如果转行 / 假设 | 用"可能自我"模拟场景，给 1–10 匹配度 + 风险预案 |
| 8 | 资源推荐 Resource Reco | 推荐书 / 学什么 | 按画像推书/课/练习，说明基于哪个证据 |
| 9 | 人生教练 Life Coaching | 我该不该换工作 / 迷茫 | 教练对话（提问>陈述），自己找答案 |
| 10 | 报告生成 Report | 出报告 / 总结 | 结构化 Markdown 报告（默认不写文件） |
| 11 | 整合测评 Integrated Assessment（v1.4） | 做个测评 / 系统结果 | 五模型原创轻量题 → 前 N 排序 + 跨模型交叉 |

用户**无需手动选择模式**——技能根据触发词 + 用户状态自动路由。

You do **not** pick a mode manually — the skill auto-routes from your trigger words and current state.

---

## 快速开始 · Quick Start

把它作为 WorkBuddy 技能加载后，直接开口即可，例如：

Once loaded as a WorkBuddy skill, just talk to it:

```
用户：我最近很迷茫，不知道自己适合做什么。
用户：帮我做个测评。
用户：如果我去转行做内容策略，会怎么样？
```

技能会自动判断你的状态（共 10 类用户画像），选择匹配模式，并以"陪伴式 ↔ 指导式"动态切换——浅层只陪伴不给方向，捕捉到天赋信号且你主动问"具体怎么做"时才给行动。

The skill detects your user-type (10 profiles), picks a mode, and dynamically switches between *companion* and *coach* — companion-only at shallow layers, actionable coaching once a talent signal appears and you ask "what should I do".

---

## 安装 · Installation

**方式 A · 作为 WorkBuddy 用户技能（推荐）**
Copy or clone this folder into your WorkBuddy skills directory:

```bash
# 放到用户级技能目录（跨项目可用）
cp -r life-coach ~/.workbuddy/skills/life-coach
```

**方式 B · 从 GitHub 克隆**
Clone and place under your skills directory, then restart / re-index WorkBuddy:

```bash
git clone https://github.com/<your-username>/life-coach.git ~/.workbuddy/skills/life-coach
```

> 技能为纯提示词 + Markdown 参考文件，无外部依赖、无需联网即可运行（市场数据校验为可选增强，无联网时自动降级为"仅画像推断"）。
> Pure prompt + Markdown references. No runtime dependencies. Works offline; the market-data check is an optional enhancement that gracefully degrades.

---

## 目录结构 · Directory Structure

```
life-coach/
├── SKILL.md                      # 主技能文件（11 模式路由 + 三模型协同 + 护栏）
├── README.md                     # 本文件
├── CHANGELOG_v1.3.md            # 1.3 增强说明（市场现实层 + 落地执行层）
├── CHANGELOG_v1.4.md            # 1.4 说明（原创整合题库 + 对话路由插题）
├── _user_meta.json              # 技能元数据
└── references/
    ├── assessments/             # 测评与题库
    │   ├── integrated_item_bank.md      # 原创整合题库（五大模型 · 统一计分 · 前 N 排序）
    │   ├── adaptive_routing.md          # 对话自动路由插题机制
    │   ├── real_assessment_bridge.md    # 三态置信分级桥接
    │   ├── mbti_questions.md / via_questions.md / strengths_questions.md / disc_questions.md / holland_questions.md
    │   ├── deep_dialogue_guide.md / iceberg_layer_prompts.md
    │   └── aqal_diagnosis.md
    ├── integration/             # 整合与映射
    │   ├── career_mapping.md           # 职业映射 + 差距分析
    │   ├── cross_model_mapping.md      # 跨模型映射 + 反幻觉校验
    │   ├── market_data_protocol.md     # 真实市场数据接入协议（含联网降级）
    │   ├── conflict_detection.md / synergy_patterns.md / ai_insight_patterns.md
    ├── resources/               # 资源库
    │   ├── career_database.md          # 职业方向库 + 时效登记表
    │   ├── career_playbook_template.md # 行业落地 Playbook（Top 8）
    │   ├── chinese_workplace_context.md# 中文职场语境
    │   ├── books.md / courses.md
    ├── models/                  # 模型第一性原理
    ├── philosophy/              # 哲学与方法论（冰山 / 优势 / AI 视角）
    ├── analysis/                # 分析指南（含 six_levels_iceberg_integration 冰山-六层次整合）
    ├── templates/               # 报告模板（Markdown / HTML）
    └── workflows/               # 各模式工作流
```

---

## 原创题库与版权 · Item Bank & License

本技能的整合题库（`integrated_item_bank.md` 及 `references/assessments/*_questions.md`）为**基于公开心理学理论的自研轻量题**，用于方向性识别与排序：

- **不复制** MBTI / 克利夫顿（盖洛普） / VIA / DISC / 霍兰德 等任何官方完整量表或题目；
- 不声称替代官方测评，仅作为对话式推断之外的中置信验证通道；
- 官方完整测评请走各机构正规渠道，其结果与本技能三态体系中的"真测评（高置信）"对接。

The item bank is **original, self-developed lightweight items based on public theory** — it does *not* reproduce any official MBTI / CliftonStrengths / VIA / DISC / Holland instruments, and is not a substitute for them.

技能整体以 **MIT License** 开源（详见仓库 `LICENSE` 文件），欢迎 Fork、改进与提交 PR。

Released under the **MIT License** (see `LICENSE`).

---

## 版本历史 · Changelog

版本号采用单一 **1.x** 体系（历史代号 v3.x 仅作溯源）。

- **1.2**（原 v3.1）：冰山-六层次-AQAL 三模型协同总览、10 类用户画像、陪伴/指导动态切换、数据职责边界重写。
- **1.3**：新增市场现实层（真实市场数据接入协议）、落地执行层（差距分析 + 行业 Playbook）、反伪精确护栏（反幻觉校验 + 三态分级雏形）、职业库时效登记表、中文职场语境。
- **1.4**：原创整合题库（五大模型题项化 + 统一计分前 N 排序）、对话自动路由插题、题型库第三置信态、题库→职业映射衔接、Top 8 Playbook 全补齐、联网降级处理。

详见 `CHANGELOG_v1.3.md` 与 `CHANGELOG_v1.4.md`。

Full history in `CHANGELOG_v1.3.md` / `CHANGELOG_v1.4.md`.

---

*Made with care by the life-coach project. 它不是告诉你"你是谁"，而是陪你发现自己本就是谁。*
