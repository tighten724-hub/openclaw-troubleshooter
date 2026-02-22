# 🛠️ OpenClaw Troubleshooter

> OpenClaw 故障排除技能 - 让0代码基础用户也能轻松解决OpenClaw问题

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)
[![OpenClaw Version](https://img.shields.io/badge/OpenClaw-2026.2.x-blue.svg)](https://github.com/openclaw/openclaw)

---

## 📖 介绍

**OpenClaw Troubleshooter** 是一个专门为 OpenClaw 用户设计的故障排除技能。无论您是初次使用还是高级用户，当遇到 OpenClaw 相关问题时，这个技能都能帮助您快速定位并解决问题。

只需描述您遇到的问题，AI会自动识别问题类型，并提供一步步的解决方案，让0代码基础的用户也能跟着操作解决问题。

---

## ✨ 功能特点

| 功能 | 说明 |
|------|------|
| 🤖 **自动问题识别** | 自动识别10+种常见问题类型 |
| 📊 **决策树** | 可视化问题分类，快速定位问题 |
| ✅ **7大问题解决方案** | Gateway、Dashboard、渠道、模型、会话、安装、节点 |
| 📝 **响应模板** | 标准化的解决方案输出格式 |
| 🚨 **紧急处理** | 强制重启、配置重置等紧急方案 |
| 📖 **文档链接** | 内置官方文档URL索引，按需查阅 |

---

## 🎯 触发条件

当您遇到以下关键词时，技能会自动触发：

```
Gateway、启动、连接、报错、问题、故障、无法、失败、错误、
Dashboard、UI、渠道、模型、会话、节点、浏览器、Cron、
心跳、安装、更新
```

**示例问题**：
- ❌ "Gateway启动不了"
- ❌ "Dashboard打不开"
- ❌ "WhatsApp连不上"
- ❌ "模型切换失败"
- ❌ "安装报错"

---

## 🚀 快速开始

### 1. 安装技能

将技能文件复制到您的 OpenClaw skills 目录：

```bash
# 克隆仓库
git clone https://github.com/tighten724-hub/openclaw-troubleshooter.git

# 移动到skills目录
cp -r openclaw-troubleshooter ~/.openclaw/workspace/skills/
```

### 2. 使用技能

当您遇到 OpenClaw 相关问题时，直接告诉 AI 助手：

```
我的Gateway无法连接了
```

AI会自动：
1. 识别问题类型（Gateway连接问题）
2. 提供诊断命令
3. 给出解决方案
4. 验证问题是否解决

---

## 📋 常见问题解决方案

### 问题1：Gateway无法启动

**症状**：运行 `openclaw gateway` 报错、闪退、无响应

**解决步骤**：

```bash
# 1. 检查Gateway状态
openclaw gateway status

# 2. 停止并重启
openclaw gateway stop
openclaw gateway restart

# 3. 运行诊断修复
openclaw doctor
openclaw doctor --fix
```

**常见错误**：

| 错误信息 | 解决方法 |
|----------|----------|
| `EADDRINUSE` 端口被占用 | 运行 `openclaw gateway stop` 然后重启 |
| `gateway.mode=local` 被阻止 | 修改配置 `gateway.mode="local"` |
| 缺少认证 | 运行 `openclaw configure` 重新配置 |

---

### 问题2：Dashboard无法连接

**症状**：浏览器打开 http://127.0.0.1:18789 失败

**解决步骤**：

```bash
# 1. 检查Gateway是否运行
openclaw gateway status

# 2. 如果没运行，启动它
openclaw gateway start

# 3. 检查认证
openclaw config get gateway.auth.token

# 4. 如果没有token，生成一个
openclaw doctor --generate-gateway-token
```

---

### 问题3：渠道消息不流动

**症状**：渠道显示已连接，但发消息没有回复

**解决步骤**：

```bash
# 1. 检查渠道状态
openclaw channels status --probe

# 2. 检查配对列表
openclaw pairing list whatsapp

# 3. 检查日志
openclaw logs --follow
```

---

### 问题4：模型问题

**症状**：模型无法切换、API报错

**解决步骤**：

```bash
# 1. 查看模型状态
openclaw models status

# 2. 查看配置的模型
openclaw config get agents.defaults.model.primary

# 3. 切换模型
openclaw models set anthropic/claude-sonnet-4-5
```

---

### 问题5：安装/更新问题

**症状**：安装失败、无法更新

**解决步骤**：

```bash
# 方式1：重新运行安装脚本（推荐）
curl -fsSL https://openclaw.ai/install.sh | bash

# 方式2：npm更新
npm install -g openclaw@latest

# 方式3：pnpm更新
pnpm add -g openclaw@latest

# 更新后运行诊断
openclaw doctor
openclaw gateway restart
```

---

## 🔬 决策树

```
我的问题是：
├─ 1️⃣ Gateway无法启动/无响应
│  └─ → 运行 openclaw gateway status
│
├─ 2️⃣ Dashboard/Control UI打不开
│  └─ → 检查认证 token
│
├─ 3️⃣ 渠道消息发不出去/收不到
│  └─ → 运行 openclaw channels status --probe
│
├─ 4️⃣ 模型相关问题
│  └─ → 运行 openclaw models status
│
├─ 5️⃣ 会话相关问题
│  └─ → 运行 openclaw sessions list
│
├─ 6️⃣ 安装/更新问题
│  └─ → 重新运行安装脚本
│
└─ 7️⃣ 节点/配对问题
   └─ → 运行 openclaw nodes status
```

---

## 📖 官方文档

当以上解决方案无法解决问题时，可以查阅官方文档：

| 文档 | 链接 |
|------|------|
| 官方文档 | https://docs.openclaw.ai/ |
| 故障排除 | https://docs.openclaw.ai/help/troubleshooting.md |
| Gateway问题 | https://docs.openclaw.ai/gateway/troubleshooting.md |
| 渠道问题 | https://docs.openclaw.ai/channels/troubleshooting.md |
| 配置问题 | https://docs.openclaw.ai/gateway/configuration.md |
| 模型配置 | https://docs.openclaw.ai/providers/models.md |
| 安装更新 | https://docs.openclaw.ai/install/updating.md |
| Discord社区 | https://discord.gg/clawd |

---

## 📁 文件结构

```
openclaw-troubleshooter/
├── SKILL.md                    # 技能主文件
│   ├── 触发条件                # 自动识别问题
│   ├── 快速诊断流程            # 60秒诊断
│   ├── 决策树                 # 问题分类
│   ├── 7大问题解决方案       # 详细解决步骤
│   ├── 响应模板              # 标准化输出
│   └── 紧急处理              # 紧急情况处理
│
└── references/
    └── URL_INDEX.md           # 官方文档URL索引
```

---

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建分支 (`git checkout -b feature/xxx`)
3. 提交更改 (`git commit -m 'Add xxx'`)
4. 推送分支 (`git push origin feature/xxx`)
5. 创建 Pull Request

---

## 📄 License

MIT License - 详见 [LICENSE](LICENSE) 文件

---

## 🙏 致谢

- [OpenClaw](https://github.com/openclaw/openclaw) - 项目官方
- [OpenClaw 文档](https://docs.openclaw.ai/) - 故障排除指南
- [Discord 社区](https://discord.gg/clawd) - 社区支持

---

## 📞 支持

- 📧 问题反馈：提交 GitHub Issue
- 💬 社区支持：加入 [Discord](https://discord.gg/clawd)
- 📖 官方文档：https://docs.openclaw.ai/

---

**让 OpenClaw 问题不再困扰您！** 🎉
