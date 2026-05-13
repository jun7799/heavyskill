# HeavySkill

多角度深度推理引擎 — Claude Code Skill

基于 [arXiv:2605.02396](https://arxiv.org/abs/2605.02396) 的多 agent 并行推理框架。核心发现：**审议是生成性的** — 综合器能产出所有独立推理链中都不存在的正确答案。

## 工作原理

1. **K 个独立子 agent 并行推理** — 每个子 agent 在隔离上下文中独立思考，不受其他推理链影响
2. **审议综合** — Claude Agent 作为审议主持，批判性评估所有推理链并综合结论
3. **报告输出** — 生成 Markdown + HTML + PDF 三种格式的深度分析报告

## 两种模式

| 模式 | 适用场景 | 子 agent 角色 | 示例 |
|------|----------|--------------|------|
| **验证模式** | 有正确答案的问题 | 不同推理方法 | 代码 bug、数学、逻辑、事实分析 |
| **审议模式** | 没有唯一答案的问题 | 不同利益相关方视角 | 技术选型、产品决策、战略讨论 |

## 安装

```bash
# 克隆到 Claude Code skills 目录
git clone git@github.com:jun7799/heavyskill.git ~/.claude/skills/heavyskill
```

## 使用

在 Claude Code 中触发关键词：

- `深度分析`
- `多角度推理`
- `heavyskill`
- `think harder`
- `让我们深入思考`
- `推敲一下`
- `讨论一下`
- `分析利弊`

## 目录结构

```
heavyskill/
├── SKILL.md              # 主文件（触发条件、工作流）
├── README.md             # 说明文档
├── agents/
│   └── interface.yaml    # Agent 接口配置
└── references/
    └── framework.md      # 完整框架文档（子 agent 提示词、审议模板、HTML 模板）
```

## 依赖

无外部依赖，纯 Claude Code Agent tool 实现。

## 鸣谢

感谢向阳乔木大哥的启发和指导。

## License

MIT
