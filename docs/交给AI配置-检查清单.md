# 交给 AI 配置 · 检查清单（买家可转发）

请按顺序做，每步打勾：

## A. 账号与 Key（本机完成）

- [ ] 已购买 Kimi 订阅（99/199 以官网为准）
- [ ] 已申请 Kimi API Key → 只写入本机 `.env` 的 `KIMI_API_KEY=`
- [ ] 已申请 DeepSeek API Key 并充值 → `DEEPSEEK_API_KEY=`
- [ ] 已设置随机 `ROUTER_LOCAL_TOKEN=`（勿用 123456）
- [ ] 对话里对 AI **只发占位符**，真 Key 不进聊天记录

## B. 路由

- [ ] 按文档启动路由后，`http://127.0.0.1:8787/healthz` 正常
- [ ] 主脑模型名：`k3.1-pro`（或文档写明的 Kimi 主脑 id）
- [ ] 子代理：`deepseek-flash`（或文档写明的 DeepSeek id）

## C. Windows 启动器

- [ ] 双击 `KimiDeepSeekRouter.exe` → 绿灯
- [ ] 已自动备份并切换 Windows Claude settings
- [ ] 重启 `claude` 后 `/status` 指向 `http://127.0.0.1:8787`
- [ ] 「恢复原配置」或「停止路由」后能回到原样（再重启 claude 验证）

## D. 冒烟

- [ ] 让主脑拆一个小任务
- [ ] 让 ds-coder（或等价子代理）改一个小文件并跑通测试
