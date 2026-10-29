# 管理运维

解决问题：检查实例健康、容量、权限与维护准备。使用对应只读或管理权限，按任务限定范围。

## 日常流程

1. 确认环境与实际运行版本，检查服务可达性、容量与 inode、近期错误和任务摘要。
2. 对访问问题核对实际登录身份、授权来源、目录范围和同步状态；不因库可见就判断文件可读写。
3. 查看备份执行与恢复验证记录；升级、GC、FSCK 和离线恢复遵循 [cloudfile-docker](https://github.com/eaopen/cloudfile-docker) 的对应版本说明。
4. 对维护变更明确影响、备份、回退和验证步骤；执行后记录真实结果，不能用配置或测试代替上线验收。

正常结果：可说明当前状态、异常和下一项可验证动作。状态检查优先使用已有汇总，限制日志时间和数量，不无条件扫描全部文件。

通用管理说明参考 [Seafile 服务器手册](https://cloud.seafile.com/wiki/publish/seafile-manual/7Lj3/)，需核对当前 CloudFile 版本差异。

AI 入口：[cloudfile-diagnose](../../skills/cloudfile-diagnose/SKILL.md)；首版 Agent 范围见 [AI 边界](../ai.md)。
