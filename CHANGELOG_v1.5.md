# CHANGELOG · life-coach (self-discovery-coach)

## v1.5 — 2026-08-14

### 本次改造：对话话术「去硬编码化」

**背景**
技能内大量具体台词被写成"照说 / 第 X 句要说 X / 固定文案 / 典型开场白：X"的强制逐字形式，导致对话机械重复、不自然。用户要求：所有对话示例、问句、话术改为"风格与方向参考"，让模型基于用户当下实际处境**自然化用、改写、替换**，避免逐字照搬。

**目标**
- 所有对话示例/问句/话术 → 示例话术（只给风格与方向）。
- 方法论护栏（三重门、理解六层次、AQAL、三态置信、非标签化、冰山 8 层定义）→ 保留原文，是必须遵循的原则，但具体实现话术可灵活发挥。
- 自研题库（题项）→ 不动，按模型计分。
- 不删除任何内容，只加标注 + 降级强制措辞。

### 改动范围

**主文件 SKILL.md**
- 新增"话术总则"全局声明（置于核心定位之后、模式路由之前）。
- 14 个话术区块全部降级为示例 + 加标注：
  - 3.1.6 原 5 步里的硬问句
  - 3.2 八维度路由表的"问题切入点/应对策略"列（含"你最近一周里…"从强制文案降级为示例）
  - 3.3.1 考官式→朋友式替代表
  - 3.3.2 七原则"问 X，不问 Y"
  - 3.3.3 逐级缩小示范表
  - 3.4 "不知道"预案策略台词
  - 3.5 人生盘点"告诉用户"台词 + 清单 + 提炼台词
  - 3.6 六大类型"典型开场白"列
  - 3.7 高认知防御者应对策略台词
  - 冰山各层"替代"问句（逐层加"示例素材库"标注）
  - 核心原则里的"问 X，不问 Y"
  - 示例 A / B / C / D 开场演示（保留为风格示例 + 标注）
  - 示例 G 全程 14 轮演示（保留为风格示例 + 标注）
  - 桥接 / 转介台词
- 版本段 `1.4` → `1.5`。

**references 文件**
- `assessments/deep_dialogue_guide.md`、`assessments/iceberg_layer_prompts.md`
- `integration/conflict_detection.md`、`integration/ai_insight_patterns.md`
- `assessments/adaptive_routing.md`、`assessments/real_assessment_bridge.md`
- `philosophy/strengths_philosophy.md`、`philosophy/ai_perspective.md`
- `analysis/six_levels_iceberg_integration.md`
- `models/extended/` 全部 13 个文件（enneagram、flow_state、perma、ikigai、scarf、immunity_to_change、logical_levels、narrative_identity、possible_selves、johari_window、self_determination、spiral_dynamics、hedgehog_concept）

### 排除（未改动）
- 自研题库：`references/assessments/integrated_item_bank.md` 及 `mbti_questions.md` / `disc_questions.md` / `holland_questions.md` / `via_questions.md` / `strengths_questions.md` —— 按模型计分，保持原样。
- 方法论护栏：三重门、理解六层次、AQAL 四象限、三态置信分级、非标签化原则、冰山 8 层定义 —— 保留原文。

### 验证
- Grep 复查：技能内不应再出现 `照说` / `第1句要说` / `固定文案` / `典型开场白：` 等强制措辞（"绝对禁止开放式抽象问题"等护栏原则保留）。
- 抽查区块确认示例标注到位、方法论与题库完整。
