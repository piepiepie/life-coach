# HTML 报告模板说明

## 设计原则

生成一份美观、专业的自我探索评估报告 HTML 文件。报告应满足以下要求：

1. **自包含**：所有 CSS 内联，无需外部依赖
2. **响应式设计**：适配桌面端和平板/手机端
3. **可打印**：打印时自动优化排版
4. **中文优化**：使用适合中文排版的字体和行距

## 色彩方案

使用温暖、专业的色彩调色板：

```css
:root {
  --primary: #2C3E50;        /* 深蓝灰 - 主色 */
  --secondary: #3498DB;      /* 蓝色 - 强调 */
  --accent: #E67E22;         /* 暖橙 - 高亮 */
  --bg: #FAFAFA;             /* 浅灰 - 背景 */
  --card-bg: #FFFFFF;        /* 白色 - 卡片背景 */
  --text: #333333;           /* 深灰 - 正文 */
  --text-light: #7F8C8D;     /* 浅灰 - 辅助文字 */
  --border: #E0E0E0;         /* 边框 */
  --success: #27AE60;        /* 绿色 - 优势 */
  --warning: #F39C12;        /* 黄色 - 注意 */
  --info: #2980B9;           /* 蓝色 - 信息 */
  --mbti: #8E44AD;           /* 紫色 - MBTI */
  --via: #E74C3C;            /* 红色 - VIA */
  --strengths: #2ECC71;      /* 绿色 - 优势 */
  --disc: #3498DB;           /* 蓝色 - DISC */
  --holland: #F39C12;        /* 橙色 - Holland */
  --aqal: #1ABC9C;           /* 青色 - AQAL */
}
```

## 页面结构

### 1. 顶部横幅（Hero Banner）
- 背景使用渐变色（primary → secondary）
- 显示用户姓名和报告标题
- 生成日期和版本号
- 设计一个简洁的装饰性图案

### 2. 个人画像卡片
- 一句话描述（大号字体，突出显示）
- 核心特质标签（彩色圆角标签）
- 测评结果一览表（小卡片布局）

### 3. 各模型详情区（Tab 式或折叠式）
每个模型一个独立区块，包含：
- **MBTI 区块**：类型代码大号展示 + 功能栈可视化（四个叠放的卡片表示功能层级）
- **VIA 区块**：Top 5 优势以排名列表展示，每条一个横条，带进度条样式
- **CliftonStrengths 区块**：Top 5 天赋主题卡片网格
- **DISC 区块**：四维度雷达图描述 + 四个条形进度条
- **Holland 区块**：RIASEC 六边形描述 + 适配职业方向列表
- **AQAL 区块**：四象限网格布局 + 发展阶段时间线

### 4. 交叉分析区
- 共振发现（绿色高亮卡片）
- 张力发现（黄色高亮卡片）
- 整合洞察（蓝色高亮卡片）

### 5. 方向推荐区
- 三个方向卡片，每个包含图标、标题和描述
- 优先级以序号和颜色深度区分

### 6. 发展路径区
- 三个阶段的时间线布局
- 每个阶段包含目标、关键行动、推荐资源
- 使用横向时间线或竖向步骤条

### 7. 页脚
- 报告声明
- AI 自我探索教练标识

## 视觉元素

### 进度条实现
```css
.progress-bar {
  height: 12px;
  background: var(--border);
  border-radius: 6px;
  overflow: hidden;
}
.progress-fill {
  height: 100%;
  border-radius: 6px;
  transition: width 1s ease;
}
```

### 雷达图描述
使用 CSS 实现的简化雷达图效果，或使用 SVG 多边形。每个顶点对应一个维度，填充区域表示得分。

### 标签系统
```css
.tag {
  display: inline-block;
  padding: 4px 12px;
  border-radius: 20px;
  font-size: 14px;
  margin: 4px;
}
```

## 响应式断点

- 桌面端（≥1024px）：双栏布局，侧边导航
- 平板端（768px-1023px）：单栏布局，折叠式导航
- 手机端（<768px）：全宽卡片，堆叠布局

## 打印样式

```css
@media print {
  .no-print { display: none; }
  body { font-size: 12pt; }
  .card { break-inside: avoid; }
  @page { margin: 2cm; }
}
```

## 生成提示

在生成 HTML 报告时，请遵循以下提示：

1. 使用语义化 HTML5 标签（header, main, section, article, footer）
2. 所有颜色使用 CSS 变量，便于统一调整
3. 为每个模型区块添加独特的标识色，增强视觉区分度
4. 数据可视化优先使用 CSS 实现，避免依赖 JavaScript 图表库
5. 确保所有占位符 `{placeholder}` 被实际数据替换
6. 添加适当的动画效果（如卡片淡入、进度条动画），但不要过度
7. 在 `<head>` 中设置正确的 viewport meta 标签和字符编码
8. 字体回退方案：`"PingFang SC", "Microsoft YaHei", "Hiragino Sans GB", "Noto Sans SC", sans-serif`

## 数据占位符映射

| 占位符 | 数据来源 |
|--------|----------|
| `{name}` | 用户姓名 |
| `{date}` | 报告生成日期 |
| `{version}` | 报告版本号 |
| `{mbti_type}` | MBTI 类型代码 |
| `{mbti_stack}` | MBTI 功能栈 |
| `{via_top5}` | VIA Top 5 列表 |
| `{strengths_top5}` | CliftonStrengths Top 5 列表 |
| `{disc_scores}` | DISC 四维度得分 |
| `{holland_code}` | Holland 代码 |
| `{aqal_quadrant}` | AQAL 主导象限 |
| `{cross_insights}` | 交叉分析发现 |
| `{directions}` | 方向推荐 |
| `{development_plan}` | 发展路径 |