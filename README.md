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

> 所有安装方式均为**永久生效**，安装一次后跨窗口、跨项目自动可用。

### Windsurf（全局 Skill）

Windsurf 的 Skill 存储在 `~/.codeium/windsurf/skills/` 目录，安装后所有工作区自动识别。

```bash
# macOS / Linux
git clone https://github.com/QingnAioo/prompt-optimizer.git ~/.codeium/windsurf/skills/prompt-optimize

# Windows (PowerShell)
git clone https://github.com/QingnAioo/prompt-optimizer.git "$env:USERPROFILE\.codeium\windsurf\skills\prompt-optimize"
```

**验证安装**：打开 Windsurf → Customizations → Skills 页签，应看到 `prompt-optimize`。

### Cursor（全局 User Rule）

Cursor 的全局规则存储在 Settings 中，对所有项目永久生效。

1. 打开 Cursor → `Settings` → `Rules` → `User Rules`
2. 将 [`skill.md`](https://raw.githubusercontent.com/QingnAioo/prompt-optimizer/main/skill.md) 全文粘贴到 User Rules 中
3. 保存

**验证安装**：任意项目中输入"优化这个 prompt"，AI 应按 5 步流程返回结果。

### Claude Code（全局 Settings）

Claude Code 的全局配置存储在 `~/.claude/settings.json`，对所有项目永久生效。

```bash
# 创建全局 CLAUDE.md（所有项目共享）
mkdir -p ~/.claude && curl -sSL https://raw.githubusercontent.com/QingnAioo/prompt-optimizer/main/skill.md >> ~/.claude/CLAUDE.md
```

**验证安装**：新开终端运行 `claude`，输入"优化这个 prompt：写个爬虫"，应按 5 步流程返回。

### ChatGPT（永久自定义指令）

ChatGPT 的自定义指令对账号下所有新对话永久生效。

1. 打开 [ChatGPT](https://chat.openai.com) → 左下角头像 → `Customize ChatGPT`
2. 在「How would you like ChatGPT to respond?」中粘贴 [`skill.md`](https://raw.githubusercontent.com/QingnAioo/prompt-optimizer/main/skill.md) 全文
3. 保存

或创建专用 GPT：`New GPT` → 将 `skill.md` 粘贴为 Instructions → 发布。

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
