# Release 说明（草稿）

本文件说明「公开仓第一次可用」时 Release 应写什么。  
**创建 GitHub Release、上传附件、对外发帖均须政政确认后再做。**

## 建议 Tag

- 文档先行：`docs-v0.1.0`（仅文档，无二进制）
- 带启动器时再：`v0.1.0`（附 `KimiDeepSeekRouter.exe` 等，且 **禁止** 打包真 `.env`）

## Release 正文模板（可复制）

```markdown
## KimiDeepSeekRouter docs-v0.1.0

Windows 本地路由文档：Claude Code → Kimi 主脑 + DeepSeek 写码。

### 本包包含
- 仓库 README 与 docs/ 下买家说明、检查清单、免费 vs 1.99 说明
- （若有附件）预构建启动器 exe —— 仍须自备双 Key

### 不包含
- API Key、填好的 .env
- 代管账号或「保证省钱」承诺

### 快速开始
1. 读根目录 README
2. 自备 Kimi 订阅 + 双 Key，按 docs/02-买家README.md 填写本机 .env
3. 启动路由 → 重启 claude → /status 确认 127.0.0.1:8787

### 1.99 打包
打不开 GitHub 时可私信获取同款教程+启动器 zip（省事包装，非隐藏功能）。
```

## 附件自检（有 exe 时）

- [ ] 无 `.env`、无真 Key
- [ ] 有简短 `买家README` 或指向本仓 docs
- [ ] 校验和（可选）写在 Release 正文
