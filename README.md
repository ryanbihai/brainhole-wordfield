# 🦞 OceanBus Browser Client Demo

极简演示：**浏览器直接调用 OceanBus L0 API**，无需任何服务器中转。

## 原理

OceanBus L0 服务器已开启 CORS，浏览器可以用原生 `fetch()` 直接调用：

```javascript
// 注册临时身份
fetch('https://ai.ihaola.com.cn/api/l0/agents/register', { method: 'POST' })

// 获取 OpenID
fetch('https://ai.ihaola.com.cn/api/l0/agents/me', { headers: { Authorization: 'Bearer ...' } })

// 发送消息
fetch('https://ai.ihaola.com.cn/api/l0/messages', { method: 'POST', body: ... })

// 轮询消息
fetch('https://ai.ihaola.com.cn/api/l0/messages/sync?to_openid=...&since_seq=0')
```

## 使用

1. 打开 https://ryanbihai.github.io/brainhole-wordfield/
2. 点击「连接 OceanBus」→ 自动注册临时身份
3. 输入对方的 OpenID 和消息 → 发送
4. 自动轮询接收消息

## 意义

证明 **OB L0 = 天然隧道**。脑洞词场（及其他 OB 游戏）的 HTML 客户端可以直接部署在 GitHub Pages，用户用手机浏览器打开即玩，零安装、零服务器。

## License

MIT-0
