# 硬件工作区

本机已选择飞特舵机路线，采购信息见 [BOM](bom.md)，具体型号与板卡版本见 [设备档案](../docs/device-profile.md)。

## Mechanical｜机械模型与改进

机械模型来自 [fanhao375/microduck-replica-cad Releases](https://github.com/fanhao375/microduck-replica-cad/releases)。实际采用的 release 标签及压缩包文件名待补充。

**电源支架挖孔避让：** 用户反馈 IMU 舵机后方的针脚顶到板件，已对电源支架进行挖孔，为针脚预留避让空间。该改动**尚未打印验证**，实际间隙、装配效果及支架强度待检查。

详细记录见 [mechanical/README.md](mechanical/README.md)。

## 目录导航

| 目录 / 文件 | 应保存的内容 |
| --- | --- |
| [bom.md](bom.md) | 采购需求、实际型号、到货状态与费用 |
| [mechanical/](mechanical/README.md) | 打印、尺寸配合、装配与返工记录 |
| [electrical/](electrical/README.md) | 实际供电、端口定义、线束与检查结果 |
| [calibration/](calibration/README.md) | 舵机 ID、关节映射、零位、方向与 IMU 标定 |

上游工程保存在独立位置时，在文档中登记路径、版本和校验值；自行修改的图纸记录修改原因、适用设备及验证情况。装配与接线照片放入 `images/assembly/` 和 `images/wiring/`。
