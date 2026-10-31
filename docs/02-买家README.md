<!-- 对外编号 02；与买家README.md 同步维护，发 zip 用本文件或改名拷贝 -->

# 买家 README（1.99 打包版大纲 · 可直接塞进 zip）

> 价格：¥1.99  
> 定位：GitHub 有免费文档；打不开 / 懒得找文件 → 付小钱拿同款教程 + 预打好的启动器。  
> **不承诺**具体省多少钱——以你自己的订阅与用量为准。

## 1. 你得到什么

- `KimiDeepSeekRouter.exe`（Windows 启动器）
- 本文使用说明 + 「交给 AI 配置」检查清单
- 能力：主脑 **Kimi k3.1 Pro**（`k3.1-pro`）+ 编码子代理 **DeepSeek**（如 `deepseek-flash`）走本地 `127.0.0.1:8787`

## 2. 你需要自备（Key 只用占位符写文档）

| 步骤 | 做什么 | 文档里怎么写 |
|------|--------|--------------|
| A | 在 Kimi 官网买订阅（常见 **99 / 199** 档，以当时页面为准） | — |
| B | 官网申请 Kimi API Key | 填入 `.env`：`KIMI_API_KEY=YOUR_KIMI_API_KEY` |
| C | DeepSeek 开放平台申请 Key，按需充值 | `DEEPSEEK_API_KEY=YOUR_DEEPSEEK_API_KEY` |
| D | 本地路由令牌（随机串即可） | `ROUTER_LOCAL_TOKEN=YOUR_RANDOM_LOCAL_TOKEN` |

**绝对不要**：把真 Key 发群、入镜、提交 Git、贴进飞书公开文档。

把 Key「丢给 AI 帮你配」时，对话里也用占位符；真值只粘进本机 `.env`。

## 3. Windows：双击即用（卖点按当前启动器）

1. 双击 `KimiDeepSeekRouter.exe`，等到状态绿色「运行中」。
2. 健康检查通过后，启动器会自动：
   - 备份当前 Windows Claude 配置到 `%USERPROFILE%\.claude\backups\kimi-router-launcher\<时间戳>\`
   - 把 `%USERPROFILE%\.claude\settings.json` 切到 `http://127.0.0.1:8787`（主模型 `k3.1-pro`，子代理 `deepseek-flash`）
   - 同步 `ds-coder` / `ds-reviewer` 到 `%USERPROFILE%\.claude\agents\`
3. **关掉已开的 claude**，再开 Windows 终端：

```bat
claude
```

输入 `/status`，确认 Base URL 为 `http://127.0.0.1:8787`、模型为 `k3.1-pro`。

4. （可选）`curl http://127.0.0.1:8787/healthz` 应返回健康。

## 4. 恢复原配置

- 点「**停止路由**」：停 WSL 路由进程，并**自动恢复**切换前的 Windows Claude 配置  
- 或点「**恢复原配置**」：不依赖是否正在跑，把备份写回  
- 恢复后再**重启 claude** 才生效  

备份指针：`%USERPROFILE%\.claude\backups\kimi-router-launcher\ACTIVE`

## 5. 交给 AI 配置时的检查清单（防配错）

请 AI 按顺序确认：

1. [ ] `.env` 仅在本机，含三个占位已替换的真值（Kimi / DeepSeek / ROUTER_LOCAL_TOKEN）  
2. [ ] 路由监听 `127.0.0.1:8787`，`/healthz` = 200  
3. [ ] `kimi-*` / `k3.1-pro` → Kimi；`deepseek-*` → DeepSeek；其它模型本地 400  
4. [ ] 双击 exe 变绿后，Windows `settings.json` 已指向本地路由  
5. [ ] `claude` 重启后 `/status` 正确  
6. [ ] 「恢复原配置」能回到切换前  

## 6. 常见坑

- 已开着的 `claude` **不会**热加载配置 → 必须重启  
- 项目目录若有自己的 `.claude/settings.json`，可能盖掉用户级设置  
- 关闭启动器窗口 ≠ 停止路由；要用按钮停  

## 7. 支持边界

本包提供启动器 + 文档。Kimi/DeepSeek 账号、订阅、额度、网络与第三方平台规则由买家自行负责。
