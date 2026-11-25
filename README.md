# DaFeiYu QQ AI Assistant

基于 [DeepSeek Harness](https://github.com/deepseek-ai) 的 QQ 接入 AI 助手（个人开发项目，进行中）。

## 架构

```
QQ 客户端
   ⇅  QQ 协议
OneBot v11 协议端（无头模式，本地运行）
   ⇅  OneBot v11 / WebSocket (127.0.0.1:3001)
dsh-qq-onebot 插件 v1.4.0
   ⇅  插件 API
DeepSeek Harness Agent（LLM 应用端，本地）
```

## 功能规划

- QQ 私聊 / 群聊接入大模型对话（白名单模式，仅限本人账号）
- 日程与定时提醒（基于 Agent 的 scheduled tasks）
- 文件 / 图片收发助手
- 本地笔记与知识库问答
- 群聊词典与梗百科查询（娱乐功能）

## 已完成的工作

- 应用端：DeepSeek Harness + dsh-qq-onebot 1.4.0 已部署并启用，私聊白名单与 owner 权限已配置
- 协议端选型与验证：评估了 NapCat / LLOneBot / Lagrange.Milky / LLBot 等多套方案，完成网络连通性、TLS、镜像下载等基础设施验证
- 安全基线：GPG 密钥体系（RSA，用于签名服务注册验证）、本地文件权限加固
- 详见 `docs/notes.md`（开发过程记录）

## 环境

- Windows x64，本地化部署，不依赖云服务
- 协议端以无头（headless）模式运行，独立于 QQ 客户端进程

## 免责声明

本项目仅供个人学习与自动化测试使用，不用于任何商业用途或大规模消息发送。
