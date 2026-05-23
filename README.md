# 虚拟城市作品集 Portfolio Virtual City

一个基于 **2.5D 等距视角** 的虚拟城市作品展示平台，用户通过探索城市的不同区域来了解设计师的信息、作品、成长经历等。

## 🎮 项目特色

- ✨ **沉浸式体验**: 打破传统作品集展示方式，进入虚拟城市探索
- 🎯 **交互高粘性**: WASD 移动 + 点击探索，增加用户停留时间
- 🏗️ **多维度展示**: 同一空间中展示多种内容维度
- 🎨 **记忆点强**: 城市环境比列表更容易记住

## 📋 城市区域

| 区域 | 功能 | 说明 |
|------|------|------|
| 🏢 **办公楼** | 个人简介 | 了解设计师的背景、技能、服务 |
| 🎮 **游戏厅** | 作品库 | 所有人的作品展示、筛选、搜索 |
| 📚 **书吧** | 书籍展示 | 书籍收藏、笔记、评分、3D翻转 |
| 🎵 **音乐���** | 音乐播放 | 喜欢的音乐、播放器、音乐可视化 |
| 🏛️ **成长馆** | 成长履历 | 时间线、里程碑、成就、证书 |
| 💬 **留言广场** | 用户留言 | 访客签名、互动评论、高分榜 |
| 📧 **信箱** | 联系方式 | 联系表单、邮件发送 |
| 🌆 **中央广场** | 核心简介 | 品牌展示、导航中心 |

## 🛠️ 技术栈

### 前端
- **框架**: Vue 3 (Composition API)
- **3D 引擎**: Three.js / Babylon.js
- **动画**: GSAP / Framer Motion
- **样式**: Tailwind CSS + SCSS
- **打包**: Vite
- **类型**: TypeScript

### 后端
- **运行时**: Node.js
- **框架**: Express.js / Fastify
- **数据库**: MongoDB / PostgreSQL
- **缓存**: Redis

### 部署
- **前端**: Vercel / Netlify
- **后端**: Railway / Heroku
- **存储**: AWS S3 / Cloudinary

## 📁 项目结构

```
portfolio-virtual-city/
├── docs/                          # 文档
│   ├── UI_UX_DESIGN.md           # UI/UX 设计文档
│   ├── ARCHITECTURE.md            # 技术架构
│   ├── API_SPEC.md               # API 规范
│   └── DEPLOYMENT.md             # 部署指南
├── frontend/                      # 前端项目
│   ├── src/
│   │   ├── components/
│   │   │   ├── CityMap.vue       # 主城市地图
│   │   │   ├── buildings/        # 建筑组件
│   │   │   ├── ui/               # UI 组件
│   │   │   └── common/           # 通用组件
│   │   ├── composables/          # 逻辑复用
│   │   ├── services/             # API 服务
│   │   ├── store/                # Pinia 状态
│   │   ├── views/                # 页面
│   │   ├── assets/               # 资源文件
│   │   ├── utils/                # 工具函数
│   │   ├── config/               # 配置文件
│   │   ├── App.vue               # 根组件
│   │   └── main.ts               # 入口
│   └── package.json
├── backend/                       # 后端项目
│   ├── src/
│   │   ├── controllers/          # 业务逻辑
│   │   ├── models/               # 数据模型
│   │   ├── routes/               # 路由定义
│   │   ├── middleware/           # 中间件
│   │   ├── config/               # 配置
│   │   └── server.ts             # 服务器
│   └── package.json
├── .gitignore
├── package.json                   # Monorepo 根配置
└── LICENSE
```

## 🚀 快速开始

### 前置要求
- Node.js >= 16
- npm >= 8 或 yarn >= 3
- Git

### 安装和运行

```bash
# 克隆项目
git clone https://github.com/neoliu2025/portfolio-virtual-city.git
cd portfolio-virtual-city

# 安装依赖
npm install

# 运行前端开发服务器
cd frontend
npm run dev

# 在新终端运行后端
cd backend
npm run dev

# 打开浏览器
open http://localhost:5173
```

## 📚 文档

- [UI/UX 设计文档](./docs/UI_UX_DESIGN.md) - 完整的设计规范
- [技术架构](./docs/ARCHITECTURE.md) - 系统设计和架构
- [API 规范](./docs/API_SPEC.md) - 后端接口文档
- [部署指南](./docs/DEPLOYMENT.md) - 生产环境部署

## 🎮 使用指南

### 键盘控制
| 按键 | 功能 |
|------|------|
| W/A/S/D | 移动视角 |
| 鼠标移动 | 旋转摄像机 |
| 左键点击 | 选择/进入 |
| 滚轮 | 缩放视图 |
| Q | 快速菜单 |
| M | 小地图显示/隐藏 |
| ESC | 返回/关闭 |
| Space | 跳跃/确认 |
| T | 时间切换 (日/夜) |
| R | 彩蛋触发 |

## 🎯 开发路线图

### Phase 1: 基础框架 (第1-2周)
- [ ] Vue 3 + Vite 项目搭建
- [ ] Three.js 3D 场景初始化
- [ ] 基础城市地图渲染
- [ ] 摄像机控制系统
- [ ] 键盘/鼠标交互

### Phase 2: 建筑系统 (第3-4周)
- [ ] 办公楼 (个人简介)
- [ ] 游戏厅 (作品库)
- [ ] 书吧 (书籍展示)
- [ ] 音乐厅 (音乐播放)

### Phase 3: 交互功能 (第5-6周)
- [ ] 成长馆 (时间线)
- [ ] 留言广场 (用户留言)
- [ ] 信箱 (联系表单)
- [ ] 中央广场 (导航)

### Phase 4: 动效和优化 (第7-8周)
- [ ] 全局动画系统
- [ ] 音效集成
- [ ] 性能优化
- [ ] 响应式设计

### Phase 5: 后端和部署 (第9-10周)
- [ ] 后端 API 开发
- [ ] 数据库设计
- [ ] 用户认证
- [ ] 部署和上线

## 🤝 贡献指南

欢迎提交 Issue 和 Pull Request！

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开 Pull Request

## 📝 许可证

MIT License - 详见 [LICENSE](./LICENSE) 文件

## 👤 作者

**Neo Liu**
- GitHub: [@neoliu2025](https://github.com/neoliu2025)
- 网站: [coming soon]

## 🙏 致谢

感谢所有贡献者和使用者的支持！

---

**最后更新**: 2026-05-23

⭐ 如果这个项目对你有帮助，请给个 Star 支持一下！
