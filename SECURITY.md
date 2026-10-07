# 安全说明

## 敏感信息

严禁提交 API Key、Access Token、Cookie、密码和真实个人敏感信息。

现有脱敏测试中的姓名、手机号、邮箱、证件号均为测试夹具，不代表真实用户数据。

## AI 安全边界

AI Gateway 应执行最小上下文、脱敏、Planning-only 和本地 Schema/白名单约束。模型输出不能直接授权器件型号、BOM、Pin、电源树或 Engineering Gate。

## 工程状态

LOCAL_DEMO 与 REAL_SERIAL 必须严格区分。故障状态优先 STOP / FAIL_SAFE；恢复必须经过人工确认。

发现密钥泄漏时，应先撤销/轮换密钥，再处理历史提交记录。