# Prompt Optimizer Skill

> 一个跨平台的 AI Prompt 优化技能，支持 Windsurf / Cursor / Claude Code / ChatGPT 等主流 AI 工具。

[![GitHub](https://img.shields.io/badge/GitHub-QingnAioo%2Fprompt--optimizer-blue)](https://github.com/QingnAioo/prompt-optimizer)
[![Version](https://img.shields.io/badge/version-1.0.0-green)]()
[![License](https://img.shields.io/badge/license-MIT-yellow)]()

## 功能

- **问题诊断** — 识别原始 prompt 中的模糊表述、结构缺失、输出格式不明确等问题
- **技巧应用** — 自动匹配并应用 Chain of Thought、Few-shot、Self-Consistency、ReAct 等高级技巧
- **任务适配** — 针对推理、写作、代码、提取、创意五大任务类型提供优化模板
- **完整输出** — 返回优化后的 prompt + 改动说明 + 测试建议

---

## 一键安装

### Windsurf（全局 Skill）

```bash
# 克隆到 Windsurf 全局 Skills 目录
git clone https://github.com/QingnAioo/prompt-optimizer.git ~/.codeium/windsurf/skills/prompt-optimize
```

安装后在任何工作区中自动可用，无需额外配置。

### Cursor（全局 Rule）

```bash
# macOS / Linux
git clone https://github.com/QingnAioo/prompt-optimizer.git /tmp/po && cp /tmp/po/skill.md ~/.cursor/rules/prompt-optimize.md

# Windows
git clone https://github.com/QingnAioo/prompt-optimizer.git %TEMP%\po && copy %TEMP%\po\skill.md %USERPROFILE%\.cursor\rules\prompt-optimize.md
```

### Claude Code（全局 CLAUDE.md）

```bash
# 追加到全局配置
curl -sSL https://raw.githubusercontent.com/QingnAioo/prompt-optimizer/main/skill.md >> ~/.claude/CLAUDE.md
```

或使用 Claude Code 的 slash command 安装：

```
/install-skill https://github.com/QingnAioo/prompt-optimizer
```

### ChatGPT（自定义 GPT / 自定义指令）

1. 打开 ChatGPT → 设置 → 自定义指令（或创建自定义 GPT）
2. 将 [`skill.md`](https://github.com/QingnAioo/prompt-optimizer/blob/main/skill.md) 全文粘贴到 System Instructions 中
3. 保存，永久生效

---

## 使用方式

安装后，在任何对话中说：

- `优化这个 prompt：[你的原始prompt]`
- `帮我改进这个提示词：[你的原始prompt]`
- `/prompt-optimize [你的原始prompt]`

AI 会自动执行 5 步优化流程并返回完整结果。

---

## 项目结构

```
prompt-optimizer/
├── README.md              # 项目说明 + 安装指南
├── skill.md               # 核心 Skill 定义（System Prompt）
├── techniques/            # 高级提示技巧说明
│   ├── chain-of-thought.md
│   ├── few-shot.md
│   ├── self-consistency.md
│   ├── react.md
│   └── structured-output.md
├── templates/             # 任务类型优化模板
│   ├── reasoning.md
│   ├── writing.md
│   ├── coding.md
│   ├── extraction.md
│   └── creative.md
└── examples/              # 优化示例
    ├── example-reasoning.md
    ├── example-coding.md
    └── example-writing.md
```

## 支持的优化技巧

| 技巧 | 适用场景 | 效果 |
|------|---------|------|
| Chain of Thought | 推理、数学、逻辑 | 提升推理准确率 |
| Few-shot | 格式要求高、分类任务 | 稳定输出格式 |
| Self-Consistency | 复杂推理 | 减少随机错误 |
| ReAct | 需要外部工具/搜索 | 增强行动能力 |
| Structured Output | 数据提取、API 调用 | 确保输出可解析 |
| Role Prompting | 专业领域 | 提升领域质量 |
| Constraint Setting | 所有任务 | 缩小输出范围 |
