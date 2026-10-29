# 现有工具索引与收敛边界

Toolkit 当前没有可执行 CLI。本页是维护入口和能力差异说明，不能代替所选版本的 README、帮助和目标实例兼容检查。

| 入口 | 现有用途 | Toolkit 的处理 |
| --- | --- | --- |
| [旧单向导入器](https://github.com/eaopen/cloudfile-docker/tree/102eedd10a59c10af05e15f8dd8c5019eeb1e736/tools/migrate) | 本地 staging 或引用源经认证文件 API 导入；任务目录持久化、计划、状态、报告与 HEAD 冲突检查 | 保留原位，不简单改名包装成通用批量导入 |
| 原项目中经实测的批量迁移路径 | 场景化原生合批、任务状态与首轮恢复机制 | 先核对实际代码、许可、配置及目标绑定，再抽取通用部分；不发布客户脚本或参数 |
| [单库离线维护入口](https://github.com/eaopen/cloudfile-docker/blob/dev/tools/ops/README-seafile-library-offline.md) | 按 UUID 检查及显式授权的原生离线维护 | 继续由 Docker 仓库维护，不作为普通文件或迁移 CLI |
| [旧实例恢复实现](https://github.com/eaopen/cloudfile-docker/blob/102eedd10a59c10af05e15f8dd8c5019eeb1e736/tools/migrate/cf_recovery.py) | 历史全实例离线灾备路径 | 不作为当前 V2 正常迁移或自动备份入口 |

旧单向导入器在已核对版本中按文件上传并进行目标 SHA-256 核验；check/plan/apply/probe/report 与独占及 HEAD 检查有既定语义。它不等同于 [多轮迁移设计](migration-design.md) 中默认增量元数据核对、错误隔离和原生合批的新要求，不能直接改变原行为或抹去原有恢复证据。

抽取前只需形成一份可审阅对照：原入口及固定版本、实际可复用机制、客户依赖、目标兼容条件、待实现项、最小验证样本。通用实现验证前，运行任务继续用原版本和原账本；验证后再决定兼容委托或入口退役，避免永久维护两套引擎。

这里固定的源码版本仅用于说明核对依据，不是目标实例版本建议，也不是部署或生产验收证明。
