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

### Windsurf

在 Windsurf 聊天窗口中发送：

```
请从 https://github.com/QingnAioo/prompt-optimizer 安装 prompt-optimize skill 到 ~/.codeium/windsurf/skills/prompt-optimize/ 目录
```

或手动：将 `skill.md` 内容复制到 `~/.codeium/windsurf/skills/prompt-optimize/SKILL.md`

### Cursor

在项目根目录创建 `.cursor/rules/prompt-optimize.md`，粘贴 `skill.md` 内容。

或在聊天中发送：

```
请读取 https://github.com/QingnAioo/prompt-optimizer 的 skill.md，将其保存为 .cursor/rules/prompt-optimize.md
```

### Claude Code

```bash
# 方式1：添加为全局 CLAUDE.md
curl -sSL https://raw.githubusercontent.com/QingnAioo/prompt-optimizer/main/skill.md >> ~/.claude/CLAUDE.md

# 方式2：在对话中直接说
请从 https://github.com/QingnAioo/prompt-optimizer 读取 skill.md 作为 prompt 优化规则使用
```

### ChatGPT / 任意 AI

直接将以下内容粘贴为 System Prompt 或自定义指令：

```
请读取并遵循此 prompt 优化规则：https://github.com/QingnAioo/prompt-optimizer/blob/main/skill.md
```

或复制 `skill.md` 全文粘贴到「自定义指令」中。

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
