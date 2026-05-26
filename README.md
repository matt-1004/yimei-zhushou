# 医美助手 · Prompt 生成器

医美咨询师的"面诊方案设计"海报 prompt 生成工具。

→ **生产环境**：https://yimei.matt.jiheniao.com/

## 流程

1. 销售/咨询师在网页填名字 + 勾改善方向 + 推荐项目 + 写专业判断
2. 提交 → 后端 spawn lark-cli 把 prompt 卡片消息发飞书给马特
3. 销售扫码加马特微信 → 发客户脸图
4. 马特用 ChatGPT (GPT-Image-2) 跑图 → 微信发回销售
5. 销售发给客户

## 架构

```
[手机/浏览器] HTTPS
    ↓
[腾讯云 nginx] 静态 + /api/ 反代
    ↓ SSH 反向隧道
[本机 Mac Node 服务]
    ↓ spawn lark-cli
[飞书私聊卡片 → 马特]
```

## 状态

V1 spike 阶段。
