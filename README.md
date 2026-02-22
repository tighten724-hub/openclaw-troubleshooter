# OpenClaw Troubleshooter

OpenClaw 故障排除技能 - 适用于0代码基础用户

## 功能特点

- 🤖 **自动问题识别** - 触发10+种问题类型
- 📊 **决策树** - 可视化问题分类
- ✅ **7大问题解决方案** - Gateway、Dashboard、渠道、模型、会话、安装、节点
- 📝 **响应模板** - 标准化的解决方案输出格式
- 🚨 **紧急处理** - 强制重启、配置重置
- 📖 **文档链接** - 官方文档URL索引

## 快速开始

当您遇到OpenClaw相关问题时，直接告诉AI助手：

- "Gateway启动不了"
- "Dashboard打不开"
- "WhatsApp连不上"
- "模型切换失败"
- "安装报错"

AI会自动使用此技能帮您解决！

## 常见问题解决方案

### 问题1：Gateway无法启动
```bash
openclaw gateway status
openclaw gateway restart
openclaw doctor
```

### 问题2：Dashboard无法连接
```bash
openclaw gateway status
openclaw config get gateway.auth.token
openclaw doctor --generate-gateway-token
```

### 问题3：渠道消息不流动
```bash
openclaw channels status --probe
openclaw pairing list whatsapp
```

## 文件结构

```
openclaw-troubleshooter/
├── SKILL.md              # 技能主文件
└── references/
    └── URL_INDEX.md      # 官方文档URL索引
```

## 触发关键词

Gateway、启动、连接、报错、问题、故障、无法、失败、错误、Dashboard、UI、渠道、模型、会话、节点、浏览器、Cron、心跳、安装、更新

## 官方文档

- 官网：https://docs.openclaw.ai/
- 故障排除：https://docs.openclaw.ai/help/troubleshooting.md
- Discord社区：https://discord.gg/clawd

## License

MIT
