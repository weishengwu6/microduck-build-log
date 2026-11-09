# Microduck Build Log

Microduck 机器人复现、硬件实验与具身智能开发记录。

本项目基于 [fanhao375/microduck-replica](https://github.com/fanhao375/microduck-replica)，记录自己的选型、采购、打印、装配、部署、标定和实验过程，并逐步探索仿真训练与具身智能应用。目标是形成一套能追溯版本、问题和验证结果的个人复现档案。

## 当前状态

**已确定飞特舵机路线，主要外购硬件已购买，当前推进齐套核对与到货验收。** 用户确认主控为 Radxa Zero 3W 1GB，配 64GB TF 卡，舵机已购 16 颗（清单写作 HD1901M，实物型号待核对），另已购 HAT、imu_to_dxl、URT2、NP-F550 电池、HUB 及所列轴承和紧固件。已购买不代表已到货或验收通过；打印、装配、部署与实机进展尚未确认。

IMX219 摄像头、VL53L8CX ToF、扬声器及乐泰 243 **未购买**。已购 17 项按用户列示小计合计 **2123.54 元**，未购 4 项参考金额 **109.10 元**；金额差异和未列附件见 [采购清单](hardware/bom.md)。

| 阶段 | 工作内容 | 完成依据 | 状态 |
| --- | --- | --- | --- |
| P0 方案确认 | 已选飞特路线，继续核对实际型号及 CAD、电控和软件兼容性 | 选型表、上游版本和采购清单齐全 | 进行中 |
| P1 采购与打印 | 主要外购件已购；继续齐套核对、到货验收与打印状态确认 | BOM 到货状态、打印参数和检查照片 | 进行中 |
| P2 机械与电气 | 分模块装配、线束整理、供电与总线检查 | 装配记录、接线图、检查结果 | 待确认 |
| P3 部署与标定 | 烧录、联网、单舵机检查、关节与 IMU 标定 | 镜像版本、配置备份和标定记录 | 待确认 |
| P4 基础运动 | 急停检查、承托下站立测试、逐步验证行走 | 实验条件、日志、视频和结果 | 待确认 |
| P5 仿真与训练 | 跑通仿真、评估与模型导出，核对部署接口 | 环境版本、训练配置和评估记录 | 后续规划 |
| P6 应用探索 | 按实际硬件开展感知、交互或策略实验 | 独立实验设计与可复查结果 | 后续规划 |

详细任务见 [复现路线](docs/roadmap.md)，本机配置见 [设备档案](docs/device-profile.md)。

## 上游与复现路线

上游资料核对日期：**2026-11-09**。以下描述来自[上游 README](https://github.com/fanhao375/microduck-replica/blob/master/README.md)，仅用于路线选择，不代表本机已有相同结果；动态分支内容可能继续更新。

| 路线 | 上游提供的资料与适用范围 | 本项目选择 |
| --- | --- | --- |
| 飞特 HD-1910 + Radxa ZERO 3W | 上游主线为 15 颗舵机，提供复刻镜像和 Studio 网页中控；报告了整机运动验证 | 已选飞特路线；已购清单型号为 HD1901M，需核对实物与适配关系 |
| Dynamixel XL330 | 提供对应 CAD 与装配资料，运行软件需另行匹配 | 本次未选用 |

已选飞特路线，仍需核对舵机实物型号；不同舵机的配合结构件不能混用。上游某些新镜像、更新功能及训练策略仍有待实机验收项，应阅读所选发布版本的说明。机器人上的 Studio 与电脑上的 Training Studio 是两个独立服务。

上游代码与大型资源建议单独获取，本仓库记录使用的版本与个人改动。不要把上游仿真网格直接当作最新版实物打印件，打印资料以对应 CAD 发布为准。

## 目录导航

```text
microduck-build-log/
├── README.md                      # 项目入口、状态与资料导航
├── docs/
│   ├── README.md                  # 文档索引与记录约定
│   ├── roadmap.md                 # 分阶段任务与验收依据
│   ├── device-profile.md          # 本机硬件、软件和模型版本
│   ├── references.md              # 上游入口、版本与来源记录
│   ├── build-log/                 # 按日期保存构建日志
│   ├── troubleshooting/           # 问题、证据、处理与复测
│   └── templates/                 # 构建、问题与实验模板
├── hardware/
│   ├── README.md                  # 硬件资料与填写说明
│   ├── bom.md                     # 采购、到货与替代件清单
│   ├── mechanical/               # 打印参数、配合检查与装配记录
│   ├── electrical/               # 接线、供电、板卡与通电检查
│   └── calibration/              # 舵机映射、零位、方向与 IMU 记录
├── software/
│   ├── README.md                  # 软件工作流与文件归档约定
│   ├── deployment/               # 镜像、联网、服务与回退记录
│   ├── configs/                  # 脱敏配置与版本说明
│   ├── scripts/                  # 后续自行编写的辅助脚本
│   ├── simulation/               # 仿真环境与运行记录
│   └── training/                 # 训练配置、评估与模型来源
├── experiments/
│   ├── README.md                  # 实验索引与结果记录规则
│   ├── records/                  # 每次实验的条件、步骤和结论
│   └── results/                  # 小型结果文件及大文件索引
└── images/
    ├── README.md                  # 图片命名与来源约定
    ├── assembly/                 # 打印与装配照片
    ├── wiring/                   # 接线图和板卡照片
    └── demos/                    # 实验截图与演示封面
```

各业务目录内的 README 提供填写清单；空的素材与结果目录使用 `.gitkeep` 保留。

## 从这里开始

1. 根据 [采购清单](hardware/bom.md) 核对到货、舵机实物型号、线束和供电附件，登记验收结果。
2. 补齐 [设备档案](docs/device-profile.md) 中的板卡版本和器件规格，未知项保留“待确认”。
3. 阅读 [资料导航](docs/references.md)，固定匹配实际舵机的 CAD 和软件发布，确认打印件状态。
4. 按 [复现路线](docs/roadmap.md) 推进，每次操作复制一份[构建日志模板](docs/templates/build-log.md)到 `docs/build-log/`。
5. 部署前填写 [部署记录](software/deployment/README.md)，标定后保存 [关节与 IMU 记录](hardware/calibration/README.md)。
6. 实机测试使用 [实验模板](docs/templates/experiment.md)，遇到问题使用 [问题模板](docs/templates/issue.md)，结论附上日志、照片或视频位置。

## 记录约定

- **事实来源**：用“上游说明 / 本机实测 / 假设 / 待核实”区分结论；上游成功案例不计入自己的完成项。
- **命名**：文档使用 `YYYY-MM-DD-topic.md`；同一天同主题可追加 `-01`。实验使用 `EXP-001` 等唯一编号，并在结果和素材文件名中沿用。
- **版本**：记录上游 commit 或 release、CAD 版本、镜像文件名及 SHA-256、软件与模型版本；更改配置时写明原因和复测结果。
- **证据**：日志记录关键原始输出；视频、大模型、镜像和 CAD 等大文件在文档中保存位置、来源与校验值。
- **隐私**：提交前移除 Wi-Fi 密码、令牌、私钥、个人收货信息和配置中的敏感字段。
- **操作顺序**：先核对供电极性与电压、单舵机通信、关节方向和限位，再逐步进行整机测试；首次运动做好承托，先验证所选软件的急停行为。

## 资料与署名

- 主要参考：[Microduck 第三方复刻项目](https://github.com/fanhao375/microduck-replica)。
- 机械资料：[配套 CAD 仓库](https://github.com/fanhao375/microduck-replica-cad)，按舵机路线选择对应发布。
- 官方项目：[Pollen Robotics / microduck](https://github.com/pollen-robotics/microduck) 与 [microduck_rl](https://github.com/pollen-robotics/microduck_rl)。
- 来源、版本登记和更多入口见 [references.md](docs/references.md)。

本仓库为个人复现记录，与上游作者及 Pollen Robotics 无隶属关系。引用或修改第三方代码、模型、图纸及文档时，保留对应来源、署名和许可；不同资源的许可不能用单一代码许可证覆盖，具体以[上游 NOTICE](https://github.com/fanhao375/microduck-replica/blob/master/NOTICE.md)及所选资源发布说明为准。本仓库尚未为原创内容指定统一许可证。
