# Moments AI - 朋友圈分析助手

<p align="center">
  <strong>上传朋友圈截图，AI 帮你快速分析画像、兴趣和聊天建议</strong>
</p>

---

## 项目简介

Moments AI 是一个基于 AI 的朋友圈截图分析工具。通过上传对方的朋友圈截图，AI 会智能分析对方的性格特征、兴趣爱好、生活方式、价值观等，并给出个性化的交友建议和聊天话题推荐。

### 核心功能

- **人物画像分析** - 分析性格标签、核心特征
- **兴趣爱好识别** - 识别兴趣领域及参与程度
- **生活方式洞察** - 了解生活习惯、作息规律
- **价值观解读** - 推断事业观、感情观、家庭观
- **情绪状态评估** - 评估近期情绪状态
- **交友建议** - 聊天话题、开场白、约会建议、互动策略

---

## 技术栈

| 层级 | 技术 |
|------|------|
| 前端 | React 19 + TypeScript + Vite |
| UI 组件 | Ant Design Mobile |
| 后端 | Node.js + Express |
| AI 模型 | 豆包大模型 (Doubao-Seed-2.0-pro) |
| 部署 | Vercel (Serverless) |

---

## 项目结构

```
moments-analyzer/
├── frontend/           # 前端应用
│   ├── src/
│   │   ├── App.tsx    # 主应用组件
│   │   ├── App.css    # 样式文件
│   │   └── main.tsx   # 入口文件
│   ├── index.html
│   ├── vite.config.ts
│   └── package.json
├── backend/            # 后端 API
│   ├── index.js       # Express 服务入口
│   └── package.json
├── api/                # Vercel Serverless 函数
├── vercel.json         # Vercel 配置
└── PRD.md              # 产品需求文档
```

---

## 快速开始

### 环境要求

- Node.js >= 18
- npm 或 yarn

### 安装依赖

```bash
# 安装前端依赖
cd frontend && npm install

# 安装后端依赖
cd ../backend && npm install
```

### 配置环境变量

在 `backend/` 目录下创建 `.env` 文件：

```bash
ARK_API_KEY=your_api_key_here
```

> API Key 获取方式：登录 [火山引擎控制台](https://console.volcengine.com/ark) → Ark 平台 → API 密钥管理

### 本地开发

```bash
# 启动后端服务 (端口 3001)
cd backend && npm run dev

# 启动前端开发服务器 (新终端)
cd frontend && npm run dev
```

访问 `http://localhost:5173` 即可使用。

---

## 使用说明

1. **上传图片** - 拖拽或点击上传朋友圈截图（至少 3 张）
2. **开始分析** - 点击"开始分析"按钮，等待 AI 处理（约 1 分钟）
3. **查看报告** - 分析完成后自动展示结构化报告
4. **下载报告** - 可下载 Markdown 格式的分析报告

### 图片要求

- 支持格式：JPG / PNG / JPEG
- 最少上传：3 张
- 最多分析：8 张（超出部分自动忽略）
- 单张限制：原图最大 30MB，分析前自动压缩至 5MB 以内

---

## API 接口

### 分析接口

```
POST /api/analyze
```

**请求体：**

```json
{
  "images": ["data:image/jpeg;base64,...", "..."]
}
```

**响应：**

```json
{
  "success": true,
  "raw": "口语化长文分析...",
  "data": {
    "personality": {
      "tags": ["标签1", "标签2"],
      "description": "性格描述"
    },
    "interests": [...],
    "lifestyle": {...},
    "values": {...},
    "emotion": {...},
    "suggestions": {...}
  }
}
```

---

## 部署

### Vercel 部署

1. Fork 本仓库
2. 在 Vercel 中导入项目
3. 配置环境变量 `ARK_API_KEY`
4. 部署完成

---

## 开发计划

- [x] V1.0 - 基础分析功能
- [x] V1.1 - 优化分析准确性、报告下载
- [ ] V2.0 - 视频分析、历史记录、个性化推荐

---

## 注意事项

- **隐私保护** - 上传的图片仅用于分析，不会被保存
- **分析结果仅供参考** - AI 分析结果不能完全代表真实情况
- **合理使用** - 请在尊重他人隐私的前提下使用本工具

---

## 许可证

MIT License