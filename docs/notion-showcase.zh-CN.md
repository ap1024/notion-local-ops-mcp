# Notion 工作流展示

English version: [notion-showcase.md](./notion-showcase.md)

这是一个建立在 `notion-local-ops-mcp` 之上的**可选示范工作流**。

## 1. Coordination Hub

- `Agent Start Here` + `Projects` + `Tasks`
- 右侧 Notion AI 面板提供项目上下文
- Notion 负责协调，真正实现仍在本地 repo

![Coordination Hub](../assets/notion/notion-coordination-hub.png)

## 2. 任务执行

- 从 task 卡片开始
- 查看 task 属性和实际工作目录
- 让 **MCP Agent** 执行，并回写简短状态 / 验证摘要

![任务执行](../assets/notion/notion-task-execution.png)

## 3. 交接 / 进度页

- 单独的任务交接页面
- 给下一次执行提供紧凑上下文
- 适合跨 session 或多 agent 协作

![交接页](../assets/notion/notion-handoff-chat.png)

## 边界

- **Notion AI**：页面级指令层
- **MCP Agent**：执行层
- **Projects / Tasks**：协调层
- **本地 repo + 本地文档**：source of truth
