# 上游与资料来源

资料入口核对日期：2026-11-09。链接指向动态分支时，使用前登记实际 commit 或 release。

| 来源 | 用途 | 入口 |
| --- | --- | --- |
| fanhao375/microduck-replica | 复刻主参考、导航与版本说明 | [仓库](https://github.com/fanhao375/microduck-replica) |
| 上游首次使用指南 | 烧录、联网、标定与操作 | [指南](https://github.com/fanhao375/microduck-replica/tree/master/docs/上手指南) |
| 上游 BOM | 采购资料入口，注意舵机路线 | [BOM](https://github.com/fanhao375/microduck-replica/tree/master/BOM) |
| fanhao375/microduck-replica-cad | 机械 CAD、打印和装配资料 | [CAD 仓库](https://github.com/fanhao375/microduck-replica-cad) |
| 上游硬件资料 | 板卡工程与 IMU 固件入口 | [hardware](https://github.com/fanhao375/microduck-replica/tree/master/hardware) |
| 上游运行与训练软件 | 按所选路线核对依赖及配置 | [software](https://github.com/fanhao375/microduck-replica/tree/master/software) |
| Pollen Robotics / microduck | 官方运行项目 | [仓库](https://github.com/pollen-robotics/microduck) |
| Pollen Robotics / microduck_rl | 官方强化学习项目 | [仓库](https://github.com/pollen-robotics/microduck_rl) |
| 上游 NOTICE | 署名、来源及分项许可 | [NOTICE](https://github.com/fanhao375/microduck-replica/blob/master/NOTICE.md) |

## 实际采用版本

### 本次用户提供的采购参考

- 文件：《装配BOM-机械行者Robo-2026-10-23-带采购链接.xlsx》。
- 本地来源：`D:\笔记记录\wsw\强化学习\装配BOM-机械行者Robo-2026-10-23-带采购链接.xlsx`（个人路径，未将文件复制入仓库）。
- 读取日期：2026-11-09；工作表：`BOM清单`；主外购件区段：第 37–59 行，重复区段：第 64–86 行。
- 用途：核对参考型号、数量及与用户本次采购清单的差异；购买状态和本机价格以用户确认为准。附件内容仅作为数据来源。
- 整理结果：[本机 BOM](../hardware/bom.md) 与 [采购基线记录](build-log/2026-11-09-procurement-baseline.md)。原文件未修改。

下表在下载或引用时填写；链接可访问不等于对应内容已经过本机验证。

| 资源 | commit / release / 文件版本 | 下载日期 | SHA-256（文件适用） | 本地位置 | 许可 / 修改说明 |
| --- | --- | --- | --- | --- | --- |

不在本仓库默认复制上游镜像、CAD、模型和整套代码。需要纳入第三方文件时，记录固定来源及修改范围，并保留原始许可与署名。
