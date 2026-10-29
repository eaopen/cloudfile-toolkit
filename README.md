# CloudFile Toolkit

面向人和 AI Agent 的 CloudFile 操作入口：角色手册、实用 Skills，以及逐步交付的通用 CLI。

当前状态：**文档与 Skills 初始版本；尚未发布或实现 `cloudfile` CLI**。Skills 是工作流指导，不代表相应命令已可执行，尚未完成真实场景验收。

## 按角色开始

| 角色 | 入口 | 常见任务 |
| --- | --- | --- |
| 开发 / 支持 | [开发与支持手册](docs/support/README.md) | 企业系统集成、扩展开发、版本兼容、故障定位 |
| 部署实施 | [实施手册](docs/implementation/README.md) | 部署准备、历史导入、增量修复 |
| 管理运维 | [运维手册](docs/operations/README.md) | 健康、容量、权限、备份与升级 |
| 使用用户 | [用户手册](docs/user/README.md) | 查找、查看、下载、上传和编辑 |

## AI 与工具

企业应用接入从 [企业文件管理集成范例](docs/support/enterprise-integration.md) 开始，覆盖身份、组织、权限、业务页面与文件操作的协作边界。

- [Agent 使用边界](docs/ai.md)：使用当前身份，按任务授权，不额外授予管理员权限。
- [CLI 范围与交付计划](docs/cli.md)：优先通用批量导入，再增加最小查询与诊断。
- [cloudfile-files](skills/cloudfile-files/SKILL.md)：权限内查找和读取文件。
- [cloudfile-import](skills/cloudfile-import/SKILL.md)：导入规划、执行状态、恢复与报告。
- [cloudfile-diagnose](skills/cloudfile-diagnose/SKILL.md)：实例与访问异常诊断。

阅读 Skill 时保留仓库目录结构，其相对链接指向同仓库手册。当前不提供仅复制单个 Skill 文件的独立安装包。

## 仓库职责

| 仓库 | 职责 |
| --- | --- |
| [cloudfile](https://github.com/eaopen/cloudfile) | 产品门户、选型与下载入口 |
| 本仓库 | 角色手册、通用 CLI、Skills、经验证的通用脚本 |
| [cloudfile-docker](https://github.com/eaopen/cloudfile-docker) | 镜像、Compose、安装升级、离线维护与物理存储工具 |
| [cloudfile-hub](https://github.com/eaopen/cloudfile-hub) / [cloudfile-server](https://github.com/eaopen/cloudfile-server) | API 契约与功能实现 |

现有迁移工具继续保留原入口；待通用实现可用并验证后再收敛。客户参数、业务映射、凭据和私有文件不进入本仓库。

## 交付顺序

[近期交付计划](docs/delivery-plan.md) · [多轮迁移与优化设计](docs/implementation/migration-design.md) · [现有工具索引](docs/implementation/tools.md)

1. 整理四类角色手册与现有工具索引（当前阶段）。
2. 从真实迁移中抽取通用合批执行、持久状态与恢复能力。
3. 增加最小文件查询与诊断 CLI，按服务端能力接入搜索与权限解释。
4. 以找资料、增量导入、访问异常三个场景验收 Skills。

中文优先；按真实任务增加能力，不建设完整 API 镜像或独立 MCP 平台。一项能力只维护一个执行实现。

[Apache License 2.0](LICENSE)。现有上游工具仍遵循各自许可证；后续抽取代码前核对来源和兼容性。
