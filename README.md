# Prompt Optimizer Skill

专业的提示词优化技能（Skill），用于分析、改进和重构 AI 提示词。

## 功能

- **问题诊断** — 识别原始 prompt 中的模糊表述、结构缺失、输出格式不明确等问题
- **技巧应用** — 自动匹配并应用 Chain of Thought、Few-shot、Self-Consistency、ReAct 等高级技巧
- **任务适配** — 针对推理、写作、代码、提取、创意五大任务类型提供优化模板
- **完整输出** — 返回优化后的 prompt + 改动说明 + 测试建议

## 项目结构

```
prompt-optimizer/
├── README.md              # 项目说明
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

## 使用方式

1. **作为 System Prompt** — 将 `skill.md` 内容直接作为 AI 助手的 system prompt
2. **作为参考框架** — 按照 `templates/` 中的模板手动优化 prompt
3. **集成到工作流** — 在 IDE 或自动化工具中调用

## 快速开始

将 `skill.md` 的内容设置为你的 AI 助手的 system prompt，然后发送你需要优化的原始 prompt 即可。

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
