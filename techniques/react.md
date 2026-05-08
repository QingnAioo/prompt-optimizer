# ReAct (Reasoning + Acting)

## 概述

ReAct 将推理（Reasoning）和行动（Acting）交织进行，适用于需要外部信息或工具调用的复杂任务。

## 核心循环

```
Thought: 分析当前状态，决定下一步
Action: 执行具体操作（搜索、计算、API调用等）
Observation: 获取操作结果
... (重复直到得出最终答案)
Answer: 最终结论
```

## 模板

### 标准 ReAct
```
你是一个可以使用工具的智能助手。

可用工具：
- search(query): 搜索信息
- calculate(expression): 数学计算
- lookup(term): 查询术语定义

请按照 Thought → Action → Observation 的循环模式工作：

问题：[用户问题]

Thought 1: 我需要先了解...
Action 1: search("...")
Observation 1: [搜索结果]

Thought 2: 基于搜索结果，我还需要...
Action 2: ...
Observation 2: ...

...

Thought N: 我现在有足够信息来回答了。
Answer: [最终答案]
```

### 简化 ReAct（无工具）
```
[任务描述]

请按照"思考-行动-观察"的模式逐步解决：

第一步 - 思考：当前掌握哪些信息？还需要什么？
第一步 - 行动：[分析/分解/假设]
第一步 - 观察：从行动中得到了什么新认知？

第二步 - 思考：基于新认知，下一步该怎么做？
...

最终答案：[综合所有观察得出结论]
```

### Agent 场景
```
# 角色
你是一个研究助手 Agent。

# 目标
[用户目标]

# 可用工具
1. web_search(query) - 网络搜索
2. read_page(url) - 读取网页内容
3. summarize(text) - 文本摘要
4. compare(item_a, item_b) - 对比分析

# 工作规则
- 每次只执行一个 Action
- 在 Thought 中明确说明为什么选择这个 Action
- 如果 Observation 不符合预期，调整策略
- 最多执行 10 轮循环
- 信息足够时立即给出最终答案

# 开始
Thought 1:
```

## 适用场景

- 需要多步信息收集的问题
- Agent/工具调用场景
- 研究和调查类任务
- 需要动态调整策略的复杂任务

## 注意事项

- 定义清晰的工具列表和使用规范
- 设置最大循环次数防止无限循环
- Observation 应该基于实际结果，而非模型臆测
- 适合与 function calling 结合使用
