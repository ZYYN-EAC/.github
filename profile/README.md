<div align="center">

# 只因由你 EAC

**多平台电商聚合 AI 托管工作站**

抖店 · 微信小店 · 快手 · 淘宝

</div>

---

## 📦 项目矩阵

| 仓库 | 角色 | 技术栈 |
|------|------|--------|
| [eac-app](https://github.com/ZYYN-EAC/eac-app) | PC 客户端 | Electron 38 · React 19 · Ant Design 6 · Tailwind v4 · Zustand · React Router 7 |
| [eac-rtc](https://github.com/ZYYN-EAC/eac-rtc) | WebRTC 信令服 + 手机工作端 H5 | Node 20 · ws · Docker |
| [eac-download](https://github.com/ZYYN-EAC/eac-download) | 安装包分发 / 自动更新 | — |

---

## 🚀 能做什么

- **一台 PC 同时管理多个店铺**(抖店 / 微信小店 / 快手 / 淘宝),webview 隔离
- **客服在线状态统一管控** —— 值班 / 离线 / 自动切换
- **售后 / 财务 / 运营 / 仓库** 工单聚合 + 数据看板,板块级自动刷新
- **AI 员工** 基于 Claude Agent SDK,自动处理重复工作流 + 知识库 / 商品学习 / 自动回复
- **仓库 退货待收货处理** —— 手机扫码当远程摄像头 → 桌面端录制凭证 → 一键同步抖店售后页
- **微信 iLink 桥** —— 通过微信远程跟 AI Agent 对话 + 命令菜单
- **数据推送 / Webhook** —— 工单 / 违规 / 关键事件 push 到企微 / 飞书 / 钉钉

---

## 🏗 技术架构

- **进程模型**:Electron 五种进程边界(主 / 预加载 / 渲染 / 通知 / Webview-preload / Utility),IPC 走 `'agent:*'` / `'api:*'` 前缀分发
- **平台插件**:`@eac/platform-*` workspace 包,统一 `platformService` 抽象,credentials / autoLogin / batchLogin / AI 托管能力靠 meta flags 显式启停
- **MCP 工具集**:`@eac/mcp-*` 11 个子包,对齐一级路由(`shop` / `after-sales` / `finance` / `operations` / `warehouse` / `ai` / `account` / `ticket` / `bookmark` / `app-actions` / `doudian`),HTTP 31234 暴露 `actionRegistry`(242+ action),LLM 通过 `app_invoke_action` 兜底任意 action
- **AI 引擎**:双 engine —— `claude-sdk`(直连 Anthropic / 豆包 / 千问 等)+ `eac-aie`(后端 LLM 网关 + 配额 / 急停 / 草稿审批)
- **协议栈**:WebRTC DataChannel + RTP / WebSocket(iLink + 信令)/ Anthropic SSE / MCP HTTP

---

## 🔐 关于

本组织所有仓库均为 **私有**,仅授权成员可见。如需协作请联系 maintainer。

<sub>© ZYYN-EAC.</sub>
