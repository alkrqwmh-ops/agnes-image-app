# Agnes AI 文生图 App

一个精美的单文件 HTML 应用，输入提示词即可调用 **Agnes AI** 图像生成模型。

---

## 特性

- 🎨 **纯前端** — 单个 `index.html`，无需服务器，双击即可运行
- ⚡ **OpenAI 兼容接口** — 支持 `/images/generations` 端点
- 🔒 **API Key 本地存储** — 配置保存在浏览器 `localStorage`，不出本机
- 📐 **多种尺寸** — 1:1、16:9、9:16 一键切换
- 🖼️ **批量生成** — 单次最多生成 4 张图
- ⌨️ **Ctrl+Enter 快捷提交**

---

## 快速开始

```bash
# 1. 下载 index.html
# 2. 双击打开（Chrome / Edge / Firefox 均可）
# 3. 点击 ⚙ API 配置，填入：
#      Base URL : https://apihub.agnes-ai.com/v1
#      Model    : agnes-image-2.0-flash
#      API Key  : 你的密钥
# 4. 输入提示词，点「生成图片」
```

---

## API 参考

| 参数 | 类型 | 说明 |
|------|------|------|
| `model` | string | `agnes-image-2.0-flash` |
| `prompt` | string | 英文提示词效果更佳 |
| `size` | string | `1024x1024` / `1024x576` / `576x1024` |
| `n` | integer | 生成数量，1–4 |

请求示例：
```bash
curl https://apihub.agnes-ai.com/v1/images/generations \
  -H "Authorization: Bearer $API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "agnes-image-2.0-flash",
    "prompt": "A cyberpunk cat sitting on neon rain",
    "size": "1024x1024",
    "n": 1
  }'
```

---

## 文件结构

```
agnes-image-app/
├── index.html   # 主应用（单文件，可直接打开）
└── README.md
```

---

## 注意事项

- API Key 仅保存在本地浏览器，不会上传至任何第三方
- 建议先通过 curl 验证 Key 是否有效：`curl .../models -H "Authorization: Bearer xxx"`
- 如遇 CORS 问题，可在 Chrome 启动时加 `--disable-web-security` 参数，或使用代理转发

---

Built for **Agnes AI** · Model: `agnes-image-2.0-flash`
