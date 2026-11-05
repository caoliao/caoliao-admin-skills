# 草料管理助手

`caoliao-admin` 是草料二维码管理端的 Agent Skill。它指导 AI 批量建码、选用官方模板、搭建表单与巡检计划，以及查询记录和扫码统计。[草料二维码官网](https://cli.im/)

## 安装与使用

在项目目录运行以下命令。需要 Node.js 22.20 或更高版本。[Skills CLI 安装文档](https://github.com/vercel-labs/skills/blob/main/docs/commands.md#skills-add)

```bash
npx skills add caoliao/caoliao-admin-skills --skill caoliao-admin
```

命令直接从 GitHub 默认分支安装。加 `-g` 可在多个项目中使用。手动安装时，导入 `skills/caoliao-admin/` 目录。

1. 在客户端添加草料管理端 MCP，地址为 `https://open.cli.im/mcp`，传输方式选 Streamable HTTP，然后完成 OAuth 授权并选择组织。可用工具和数据范围取决于当前授权。[草料管理端 MCP 文档](https://cli.im/open-api/agent/open-platform-mcp.html)
2. 在对话中调用技能，例如「查询当前连接的组织和剩余额度」或「按设备清单批量建码」。文件上传、批量数据准备和码图下载脚本所需的 Python 或 Node.js 版本见对应参考文档。

## 源码结构

```text
skills/caoliao-admin/
├── SKILL.md       # 技能入口，包含 YAML 元数据与 Markdown 指令
├── references/    # 按任务查阅的工具和流程说明
├── scripts/       # 上传、数据准备与码图下载脚本
└── examples/      # 使用占位数据的通讯录和设备巡检示例
```

技能目录名与 `SKILL.md` 的 `name` 一致。`description` 描述适用场景，`metadata.version` 记录技能版本。参考资料、脚本和示例随技能目录一起分发。[Agent Skills 规范](https://agentskills.io/specification)
