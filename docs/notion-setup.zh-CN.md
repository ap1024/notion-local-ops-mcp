# Notion 配置指南

English version: [notion-setup.md](./notion-setup.md)

只有在你要使用**可选的 Notion 工作流示范**时，才需要这份文档。

## 角色分工

| 层 | 作用 |
| --- | --- |
| Notion AI | 读取 `Notion AI > 指令` 里的页面级指令页 |
| MCP Agent | 通过 `notion-local-ops-mcp` 执行本地工作 |
| Projects / Tasks | Notion 里的可选协调层 |
| 本地 repo | 实现层 source of truth |

![Notion AI 指令设置](../assets/notion/notion-ai-instruction-settings.png)

## 配置步骤

1. **启动 MCP 服务**

   ```bash
   cp .env.example .env
   ./scripts/dev-tunnel.sh
   ```

2. **在 Notion 中配置 MCP Agent**

   - URL：`https://<your-domain-or-tunnel>/mcp`
   - Auth type：`Bearer`
   - Token：`NOTION_LOCAL_OPS_AUTH_TOKEN`

3. **给 MCP Agent 粘贴 prompt**

   直接使用 [README](../README.zh-CN.md) 里的 prompt。

4. **duplicate 公开指令页**

   - [公开 Notion 指令页示例](https://ncp.notion.site/Agent-Start-Here-Template-10eb4da3979d8396861281ca608bc34e)

5. **绑定到 Notion AI**

   去 `Notion AI > 指令`，选择 duplicate 出来的页面。

## duplicate 后先改这些

- 替换示例 project 行
- 替换或删除示例 task 行
- 设置 `Workspace Root`
- 设置 `Default CWD`
- 设置 `Local Docs Root`

## 最小验证

- 读取一个本地文件
- 运行 `pwd`
- 从 task 开始，确认目录路由正确

示例：

```text
Open the task "Design Notion project and task system", read its linked project, and tell me which local directory you would use.
```

## 完成标准

- Notion AI 已绑定 duplicate 后的指令页
- MCP Agent 可以读本地文件、执行 shell
- task -> project 路由能得到正确工作目录
