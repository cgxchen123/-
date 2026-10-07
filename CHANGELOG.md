# CHANGELOG

## v5.4.0 — 2026-10-07

### Fixed
- 修复显式 5V/12V/24V 输入被默认模板电压覆盖的问题。
- Evidence 页面改为根据实际输入电压生成 PASS / REVIEW 与计算说明。
- 发布包验证改为稳定解析交付包根目录，降低对开发机目录结构的依赖。

### Added / Polished
- 比赛提交资料统一收口。
- 增强 24V → 5V → 3.3V 电源树回归。
- 保留 12V / 24V Evidence 差异化判断。
- 保留高风险继电器线圈直接接 MCU GPIO 的 BLOCKED 行为。
- 完成发布追溯、工程契约与完整验证入口。

### Validation
- 83/83 单元测试通过。
- 发布自检 ALL CHECKS PASSED。
- Fail-Closed Round-5 预演通过。
- 接线文档 64/64 PASS。
- MCU 专项 35/35 PASS。
- Datasheet、工程契约、发布追溯与 API Smoke 通过。

### Boundary
本版本不新增“全自动 PCB、全品类 SPICE、全品类参数级 Datasheet 自动核验、量产级认证”等未被证据支持的能力声明。

## v5.3.6 — 2026-09-29

正式交付基线，形成 AI Gateway、工程约束、Evidence、Wiring、硬件状态、比赛材料与验证脚本等核心结构。

其 Git 历史还包含 v5.0.0、v5.1.x、v5.2.x、v5.3.x 多个工程阶段，详见 `docs/HISTORY_INDEX.md`。

## 后续版本规则

- 版本号必须与实际交付内容对应，禁止“为了好看”跳版本。
- 修复类版本写明复现输入、错误行为、修复行为和回归测试。
- 比赛材料变化不能伪装成算法能力变化。
- 新增能力必须同时更新能力边界和验证证据。
