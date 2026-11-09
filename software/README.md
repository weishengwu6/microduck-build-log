# 软件工作区

本仓库尚无控制程序或训练实现。以下目录用于组织后续个人代码、配置和复现记录。

| 目录 | 用途 |
| --- | --- |
| [deployment/](deployment/README.md) | 烧录、启动、联网、服务检查与回退 |
| [configs/](configs/README.md) | 经过脱敏的配置示例与变更说明 |
| [scripts/](scripts/README.md) | 自行编写的诊断、采集和整理脚本 |
| [simulation/](simulation/README.md) | 仿真安装、模型与任务验证 |
| [training/](training/README.md) | 训练环境、配置、评估及模型导出 |

建议将上游代码放在本仓库之外，记录 commit 与个人修改；当前不自动引入子模块或复制上游代码。具体安装和启动命令待硬件路线、版本确定后，依据对应文档实测补充。

机器人 Studio 和电脑 Training Studio 分别记录环境与访问方式。每次升级前记录当前基线和备份位置，升级后复测受影响的功能。
