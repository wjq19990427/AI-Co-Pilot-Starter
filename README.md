# AI Co-Pilot Starter

一套可复用的 **AI 协同开发 SOP 模板**，基于「架构师（Claude）+ 实现工手（Codex）+ PM（用户）」三角色模型，配合分层文档体系，让 AI 参与软件开发的全流程有章可循。

## 核心理念

```
用户（PM）        →  提需求 / 测试 / 最终合并
Claude（架构师）  →  诊断 / 任务卡 / Review / 维护文档
Codex（实现工手） →  在独立 worktree 实现任务卡 / 不 push main
```

文档分四层，上层只读不写下层的实现细节：

```
L0  CLAUDE.md + AGENTS.md        自动注入的角色规则
L1  docs/STATUS.md + ARCHITECTURE.md   项目快照 + 模块索引
L2  docs/api/{layer}.md          模块公开 API 契约（唯一权威来源）
L3  源代码                        实现细节
```

## 快速开始

1. **Use this template** 或 clone 本仓库到新项目
2. 阅读 [`SETUP.md`](SETUP.md) — 引导文档，说明每个文件如何按项目定制
3. 将 `{占位符}` 替换为项目实际内容，提交基线
4. 开始按 SOP 工作

## 仓库结构

```
├── SETUP.md               ← 新项目引导（先读这里）
├── CLAUDE.md              ← 架构师角色规则（放项目根目录）
├── AGENTS.md              ← 实现工手规则（放项目根目录）
└── docs/
    ├── STATUS.md          ← ≤50 行项目快照模板
    ├── ARCHITECTURE.md    ← L1 模块索引模板
    ├── api/
    │   └── _HOWTO.md      ← 如何编写 L2 契约文档
    └── tasks/
        └── _template.md   ← 任务卡标准格式
```

## 适用场景

- 个人项目引入 AI 辅助开发，需要明确角色分工
- 多人协作时统一 AI 工具的使用规范
- 任何需要长期维护、上下文频繁切换的代码库

## 源项目

本模板从 [MyPresent](https://github.com/wjq19940427/MyPresent) 项目的实际开发流程中提炼，经过 15 个完整任务卡的实战验证。
