# CFnew 精简内核（core-only）

本仓库部署的是 [byJoey/cfnew](https://github.com/byJoey/cfnew) **core-only 分支**的精简代理内核，
通过 GitHub Actions 每 6 小时自动跟踪上游更新。

- 内核：[`_worker.js`](./_worker.js)（仅代理转发 + KV 配置 + 优选地址接口）
- 面板（页面 / 订阅生成 / 优选测试）：**<https://cfnew.xy.kg/>**
- 当前内核版本见 [`VERSION.txt`](./VERSION.txt)（上游 core-only 提交 SHA + 日期）
- 原完整版本仍在上游 `main` 分支，本仓库不再跟踪

## 部署要点

- Cloudflare Pages 项目：`cfnew-auto`（Git 关联本仓库 `main`）
- 环境变量：`u` = UUID
- KV 绑定：`c` → `cfnew-auto-kv`
- 兼容性日期：`2026-01-20`
- Worker 首页返回 `hello`；`/sub` 路径已移除，**订阅改由面板生成**

详见 `docs/CFnew-部署手册.md` / `docs/CFnew-使用指南.md`。
