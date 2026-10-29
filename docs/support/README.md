# 开发与支持

解决问题：定位连接、版本、访问或文件操作异常。需要对应实例的只读诊断权限；访问日志也受原有权限约束。

## 排查流程

1. 记录实例环境、组件版本、故障时间、操作和脱敏错误。区分 DEV、PROD 与本地。
2. 确定失败阶段：连接、认证、授权、元数据、传输、提交或结果确认。
3. 只读取相关时间窗口和有限条数的日志；先做单个对象的最小复现，避免全库扫描。
4. 将观察事实、推断、待验证项分开记录；修复后重做原场景，并核实部署版本。

正常结果：能指出失败环节及证据，或明确缺少什么证据。权限解释需复用服务端真实有效权限机制；没有该能力就报告不支持，不在客户端重算。

API 与实现问题回到 [Hub](https://github.com/eaopen/cloudfile-hub) 或 [Server](https://github.com/eaopen/cloudfile-server)；构建部署问题回到 [Docker](https://github.com/eaopen/cloudfile-docker)。

AI 入口：[cloudfile-diagnose](../../skills/cloudfile-diagnose/SKILL.md)。
