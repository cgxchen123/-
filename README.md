# 芯造天工（XinZaoTianGong）

> 面向高校嵌入式原型开发的可信 AI 硬件方案生成与风险审查系统

**当前基线：v5.4.0｜2026-10-07**  
**参赛方向：2026 AIC 第八届全球校园人工智能算法精英大赛｜算法创新赛｜AI+场景创新**

## 项目定位

芯造天工把生成式 AI 放进一个需要工程约束、证据和拒绝机制的真实硬件开发场景。

核心链路：

`自然语言需求 → 工程需求契约 → AI Planning-only → 确定性工程校验 → Evidence → Engineering Gate → READY / REVIEW / BLOCKED`

AI 负责理解、规划和解释；确定性工程层负责器件、电源、引脚、BOM、约束、证据和最终 Gate。模型不能直接授权硬件设计结论。

## 当前能力

- 自然语言需求解析与结构化工程需求契约
- 场景、模块、主控、接口和电源识别
- 显式供电电压优先于模板默认值
- 器件、接口、引脚、电源树和部分高风险连接校验
- Evidence / provenance / Engineering Gate
- AI Gateway + Planning-only Schema
- Datasheet PDF 证据中心与人工复核边界
- Wiring / Schematic 确定性生成
- Hardware State / Fail-Closed 演示链路
- Web 工作台、响应式 UI、本地可重复验证

## 关键安全/可信案例

输入：

`24V供电，ESP32主控，蓝牙小车`

v5.4.0 的回归要求：

- `input_voltage = 24.0V`
- 模板默认 12V 不得覆盖明确输入
- 电源树进入 `24V → 5V → 3.3V`
- 24V Evidence 不能伪装为 12V PASS，而应按当前规则进入 REVIEW
- 明确危险的继电器线圈直连 GPIO 应进入 BLOCKED

这些是工程回归结论，不代表真实用户收益。

## 仓库结构

```text
├─ 01_程序/                  # 当前 v5.4.0 运行内核
├─ 02_使用与演示/             # 运行手册、AI 接入、硬件演示
├─ 03_比赛提交资料/            # 唯一最终提交集 + 可编辑材料
├─ 04_开发与测试/              # 历史源码、验证脚本、审计、截图证据
├─ 05_发布与完整追溯/           # manifests、Git bundle、运行记录、checksum
├─ docs/                     # 总览、架构、版本、证据台账、限制
├─ .github/workflows/        # 自动工程检查
├─ CHANGELOG.md
├─ CONTRIBUTING.md
├─ SECURITY.md
└─ 一键启动芯造天工.* / 验证芯造天工.*
```

## 运行

Windows：双击根目录 `一键启动芯造天工.bat`

macOS / Linux：

```bash
./一键启动芯造天工.sh
```

默认地址：`http://127.0.0.1:8765`

完整验证：

```bash
./04_开发与测试/02_验证脚本/run_full_validation.sh
```

Windows 也可直接双击 `验证芯造天工.bat`。

## 当前验证口径

整理后的 v5.4.0 仍通过 83/83 单元测试、Competition Release Smoke、Python compileall、JavaScript syntax check 以及完整专项验证；接线文档和 MCU 专项也保留原始回归记录。

这些全部属于工程实现验证。真实用户数量、用户节省时间、企业试点收益等必须有独立原始证据，见 `docs/EVIDENCE_LEDGER.md`。

## 能力边界

当前不宣称：

- 全自动 PCB Layout / 生产文件
- 全品类 SPICE 自动仿真
- 全知识库参数级 Datasheet 自动核验
- 量产级认证
- 已完成企业试点
- 已经取得固定比例的用户效率提升

## 历史版本

历史 tag 从 v5.0.0-fused 到 v5.3.6-final-release，完整信息见 `docs/VERSION_HISTORY_DETAILED.md`；原始 Git bundle 在 `05_发布与完整追溯/02_Git完整历史/`。

v5.4.0 是基于 v5.3.6 历史工程基线做的比赛收口版本，不改写历史 bundle。

## 真实性原则

每一条对外结论都要能够回答：

1. 事实是什么？
2. 证据在哪里？
3. 证据只支持到什么范围？

没有原始证据的数据统一写“待验证”，不拿测试夹具、演示状态或模型输出冒充真实应用成果。
