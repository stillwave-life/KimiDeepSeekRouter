# KimiDeepSeekRouter

真·Windows 零配置：让本机 Claude Code 走 **Kimi 主脑 + DeepSeek 写码** 本地路由。

- 主模型：Kimi（如 `k3.1-pro`）
- 编码子代理：DeepSeek（如 `deepseek-flash`）
- 本地地址：`http://127.0.0.1:8787`
- 不用了可一键「恢复原配置」

> **不承诺**具体省多少钱——以你自己的订阅与用量为准。  
> **不要**把真 API Key、填好的 `.env` 提交进本仓库或发到公开群。

## 你需要自备

1. Windows 10/11（常见还需 WSL2 + Linux 发行版，以启动器/安装说明为准）
2. 已能运行的 Windows `claude`（Claude Code）
3. Kimi 订阅 → 申请 Kimi API Key
4. DeepSeek 开放平台 Key（按需充值）
5. 本机随机串作 `ROUTER_LOCAL_TOKEN`

文档里一律用占位符：`YOUR_KIMI_API_KEY` / `YOUR_DEEPSEEK_API_KEY` / `YOUR_RANDOM_LOCAL_TOKEN`。真值只写进本机 `.env`。

## 推荐用法（零配置方向）

1. 按仓库文档装好路由与启动器（或从 Release 取预构建，若已发布）
2. 本机填好 `.env`（可参考「交给 AI 配置」检查清单，对话里也用占位符）
3. 双击 `KimiDeepSeekRouter.exe`，等到状态绿色「运行中」
4. **关掉已开的** `claude`，再开 Windows 终端运行 `claude`
5. `/status` 确认 Base URL 为 `http://127.0.0.1:8787`、主模型为 `k3.1-pro`
6. 可选：`curl http://127.0.0.1:8787/healthz`

停止路由或点「恢复原配置」可回到切换前的 Windows Claude 设置。备份一般在：

`%USERPROFILE%\.claude\backups\kimi-router-launcher\`

## 教程顺序（写给买家 / 代配）

Kimi 订阅 → 双 API Key → 交给 AI 配置（用检查清单）→ 启动路由 → 重启 `claude` 验收。

详细检查清单见 [`docs/交给AI配置-检查清单.md`](docs/交给AI配置-检查清单.md)。  
更完整的买家说明见 [`docs/02-买家README.md`](docs/02-买家README.md)。

## GitHub 免费 vs ¥1.99 打包

| | GitHub 免费（本仓） | ¥1.99 打包 |
|---|---|---|
| 教程 / README | 公开可看 | 同款（可排版更好看） |
| 启动器 | 自行按文档获取 / 编译，或等 Release | 预打好的 exe + 清单 |
| 适合 | 会用 Git、能上 GitHub | 打不开 GitHub，或只想双击开干 |
| 功能 | — | **省事包装**，不是多一套未说明的神秘能力 |

一句话：文档免费；1.99 只收打包与投递成本。差异表：[`docs/免费版与1.99差异.md`](docs/免费版与1.99差异.md)。

## 短视频 / 口播素材（可选）

对比短视频口播草稿：[`docs/01-口播稿.md`](docs/01-口播稿.md)  
置顶与私信话术（收款方式需自行填写）：[`docs/03-置顶与私信.md`](docs/03-置顶与私信.md)

## 常见坑

- 已开着的 `claude` 不会热加载配置 → 必须重启
- 项目目录若有自己的 `.claude/settings.json`，可能盖掉用户级设置
- 关闭启动器窗口 ≠ 停止路由；要用按钮停
- 仓库、视频、zip 里禁止出现真 Key

## 支持边界

本仓提供文档（及后续 Release 中的构建物说明）。Kimi / DeepSeek 账号、订阅、额度、网络与第三方平台规则由使用者自行负责。不代申请 Key、不远程桌面、不承诺具体省钱金额。

## Release

见 [`docs/RELEASE_NOTES.md`](docs/RELEASE_NOTES.md)。正式打 Tag / 上传附件前须仓库维护者确认。
