# rule/mrs — mihomo 规则集 MRS 产物

由 `.github/workflows/build-rules.yml` 每天 UTC 18:30（北京时间次日 02:30）自动从 blackmatrix7/ios_rule_script release 分支拉源、转换、提交；也可 `workflow_dispatch` 手动触发。

- `*.mrs`：4 个 domain/ipcidr 文件（zstd 格式，mihomo convert-ruleset 生成）
- `*.yaml`：3 个 classical 文件（Global / AdvertisingLite / Lan，mrs 不支持 classical）

服务器 fair-light-1 只从本目录 raw 拉这 7 个成品到 `/opt/1panel/www/rules/`，经 `https://api.chattalk.win/rules/` 提供给客户端；客户端不访问 GitHub。转换逻辑与踩坑见 fair-light-1 工作区报告。
