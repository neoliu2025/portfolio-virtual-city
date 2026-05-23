# 部署指南

## 前端部署

### Vercel 部署

```bash
# 1. 安装 Vercel CLI
npm install -g vercel

# 2. 登录
vercel login

# 3. 部署
vercel

# 4. 生产部署
vercel --prod
```

### Netlify 部署

```bash
# 1. 安装 Netlify CLI
npm install -g netlify-cli

# 2. 构建
npm run build

# 3. 部署
netlify deploy --prod --dir=dist
```

## 后端部署

### Railway 部署

```bash
# 1. 安装 Railway CLI
npm install -g @railway/cli

# 2. 登录
railway login

# 3. 初始化项目
railway init

# 4. 部署
railway up
```

### Heroku 部署

```bash
# 1. 安装 Heroku CLI
brew tap heroku/brew && brew install heroku

# 2. 登录
heroku login

# 3. 创建应用
heroku create your-app-name

# 4. 部署
git push heroku main
```

## 环境配置

### 前端环境变量 (.env.production)

```
VITE_API_URL=https://api.yourdomain.com
VITE_APP_NAME=Portfolio Virtual City
VITE_ANALYTICS_ID=your-analytics-id
VITE_ENABLE_DEVTOOLS=false
```

### 后端环境变量 (.env)

```
NODE_ENV=production
PORT=3000
DATABASE_URL=your-database-url
JWT_SECRET=your-jwt-secret
JWT_EXPIRE=7d
CORS_ORIGIN=https://yourdomain.com
SMTP_HOST=your-smtp-host
SMTP_PORT=587
SMTP_USER=your-email
SMTP_PASS=your-password
```

## 数据库部署

### MongoDB Atlas

1. 访问 [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
2. 创建账户并登录
3. 创建集群
4. 获取连接字符串
5. 添加到 `.env` 的 `DATABASE_URL`

### PostgreSQL (Heroku)

```bash
# 添加 PostgreSQL 附加服务
heroku addons:create heroku-postgresql:hobby-dev

# 查看数据库 URL
heroku config | grep DATABASE_URL
```

## 性能优化

### 前端优化

```bash
# 1. 启用 Gzip 压缩
# Vercel/Netlify 自动启用

# 2. 图片优化
# 使用 WebP 格式 + 懒加载

# 3. 代码分割
# Vue Router 自动进行代码分割

# 4. CDN 缓存
# 设置长期缓存策略
```

### 后端优化

```bash
# 1. 数据库索引
db.projects.createIndex({ createdAt: -1 })

# 2. Redis 缓存
redis-cli
config set maxmemory 256mb
config set maxmemory-policy allkeys-lru

# 3. API 速率限制
# 已在中间件中配置

# 4. 日志级别
NODE_ENV=production # 自动禁用详细日志
```

## 监控和日志

### 前端监控

- Sentry: 错误跟踪
- Google Analytics: 用户分析
- Vercel Analytics: 性能监控

### 后端监控

- PM2: 进程管理
- New Relic: 性能监控
- CloudWatch: 日志聚合

## 自动化部署

### GitHub Actions

```yaml
name: Deploy

on:
  push:
    branches: [main]

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      
      - name: Install dependencies
        run: npm install
      
      - name: Build
        run: npm run build
      
      - name: Deploy to Vercel
        run: vercel --prod --token ${{ secrets.VERCEL_TOKEN }}
```

## 域名配置

1. 购买域名 (GoDaddy / Namecheap)
2. 配置 DNS 指向部署平台
3. 申请 SSL 证书 (Let's Encrypt / 平台提供)
4. 启用 HTTPS

## 备份策略

```bash
# MongoDB 备份
mongodump --uri="mongodb+srv://user:pass@cluster.mongodb.net/dbname"

# 恢复备份
mongorestore --uri="mongodb+srv://user:pass@cluster.mongodb.net/dbname" ./dump
```

