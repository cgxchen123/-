# 发布策略

每次正式版本必须建立可追溯记录。

## 必填

- version
- date
- summary
- fixed issues
- validation
- known limitations
- competition-material status

## 推荐提交节奏

`fix/*` → `test/*` → `release/vX.Y.Z` → merge main → tag `vX.Y.Z`

## 禁止

- 修改历史版本号掩盖真实变更
- 将测试夹具当成真实用户证据
- 提交真实 API Key
- 把未实现能力写进比赛材料
