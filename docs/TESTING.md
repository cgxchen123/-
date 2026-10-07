# 测试与证据

## 已知 v5.4.0 本地结果

- 83/83 单元测试通过
- 发布自检通过
- Fail-Closed Round-5 预演通过
- 接线文档 64/64 PASS
- MCU 专项 35/35 PASS
- Datasheet 专项通过
- Engineering Contract / Provenance 通过
- API Smoke 通过

## 关键回归

### 明确电压
输入：24V供电，ESP32主控，蓝牙小车

预期：
- input_voltage = 24.0V
- 电源树 = 24→5→3.3
- 12V evidence 不应覆盖真实输入
- 24V evidence 应进入 REVIEW

### 高风险连接

输入包含“继电器线圈直连 GPIO”等高风险连接时：

预期：BLOCKED，而不是生成“看起来完整”的可执行连接方案。

## 证据纪律

工程测试证明的是“当前代码对当前测试集的行为”。它不能自动证明真实用户收益。真实效果需要独立的用户测试、对照实验或现场应用记录。
