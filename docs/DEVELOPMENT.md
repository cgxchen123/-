# 开发说明

## 本地环境

建议使用 Python 3.11+；以当前 `01_程序/requirements.txt` 与运行脚本为准。

## 运行

Windows：
```text
一键启动芯造天工.bat
```

macOS/Linux：
```bash
./一键启动芯造天工.sh
```

## 验证

完整入口：

```bash
./04_开发与测试/02_验证脚本/run_full_validation.sh
```

## 修改纪律

修改前先确定问题属于：
- 解析层
- AI 规划层
- 确定性工程层
- Evidence / Gate
- UI
- 验证脚本
- 比赛材料

涉及工程安全的改动必须新增回归用例，而不是只改页面文字。
