# API 规范文档

## API 端点设计

### 用户模块

```
GET  /api/profile              - 获取用户简介
POST /api/profile              - 更新用户简介
GET  /api/profile/skills       - 获取技能列表
GET  /api/profile/avatar       - 获取头像
POST /api/profile/avatar       - 上传头像
```

### 作品模块

```
GET    /api/projects           - 获取作品列表 (分页)
GET    /api/projects/:id       - 获取单个作品详情
POST   /api/projects           - 提交新作品
PUT    /api/projects/:id       - 更新作品
DELETE /api/projects/:id       - 删除作品
GET    /api/projects/search    - 搜索作品
GET    /api/projects/filter    - 筛选作品
GET    /api/projects/trending  - 热门作品
```

### 书籍模块

```
GET  /api/books                - 获取书籍列表
GET  /api/books/:id            - 获取书籍详情
POST /api/books                - 添加书籍
PUT  /api/books/:id            - 更新书籍
DELETE /api/books/:id          - 删除书籍
GET  /api/books/:id/notes      - 获取读书笔记
POST /api/books/:id/notes      - 添加读书笔记
```

### 音乐模块

```
GET  /api/music                - 获取音乐列表
GET  /api/music/:id            - 获取音乐详情
POST /api/music                - 添加音乐
PUT  /api/music/:id            - 更新音乐
DELETE /api/music/:id          - 删除音乐
GET  /api/music/:id/lyrics     - 获取歌词
GET  /api/music/playlists      - 获取播放列表
```

### 成长履历模块

```
GET  /api/timeline             - 获取完整时间线
GET  /api/timeline/:year       - 获取特定年份事件
GET  /api/achievements         - 获取成就列表
GET  /api/achievements/:id     - 获取成就详情
POST /api/timeline/events      - 添加事件
```

### 留言模块

```
GET    /api/messages           - 获取留言列表 (分页)
POST   /api/messages           - 发布新留言
GET    /api/messages/:id       - 获取留言详情
PUT    /api/messages/:id       - 更新留言
DELETE /api/messages/:id       - 删除留言
POST   /api/messages/:id/like  - 点赞留言
DELETE /api/messages/:id/like  - 取消点赞
GET    /api/messages/:id/replies - 获取回复
POST   /api/messages/:id/replies - 添加回复
```

### 联系模块

```
POST /api/contact              - 提交联系表单
GET  /api/contact/status/:id   - 获取提交状态
GET  /api/contact/list         - 获取所有提交 (管理员)
```

### 统计模块

```
GET  /api/stats                - 获取访问统计
POST /api/stats/visit          - 记录访问
GET  /api/stats/popular        - 获取热门内容
```

## 响应格式

### 成功响应

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    // 具体数据
  },
  "timestamp": "2026-05-23T10:00:00Z"
}
```

### 分页响应

```json
{
  "code": 200,
  "message": "Success",
  "data": {
    "items": [
      // 数据项
    ],
    "total": 100,
    "page": 1,
    "pageSize": 10,
    "totalPages": 10
  },
  "timestamp": "2026-05-23T10:00:00Z"
}
```

### 错误响应

```json
{
  "code": 400,
  "message": "Bad Request",
  "errors": [
    {
      "field": "email",
      "message": "Invalid email format"
    },
    {
      "field": "name",
      "message": "Name is required"
    }
  ],
  "timestamp": "2026-05-23T10:00:00Z"
}
```

## 状态码

| 状态码 | 含义 |
|-------|------|
| 200 | 成功 |
| 201 | 创建成功 |
| 204 | 无内容 |
| 400 | 请求错误 |
| 401 | 未认证 |
| 403 | 禁止访问 |
| 404 | 未找到 |
| 500 | 服务器错误 |
| 503 | 服务不可用 |

## 认证方式

使用 JWT (JSON Web Token)

```
Authorization: Bearer <token>
```

## 请求示例

### 获取作品列表

```bash
GET /api/projects?page=1&pageSize=10&sort=latest
```

### 提交留言

```bash
POST /api/messages
Content-Type: application/json

{
  "author": "访客名字",
  "email": "guest@example.com",
  "content": "很棒的作品！",
  "rating": 5
}
```

### 提交联系表单

```bash
POST /api/contact
Content-Type: application/json

{
  "name": "张三",
  "email": "zhangsan@example.com",
  "subject": "商务合作",
  "message": "我们想和你合作..."
}
```

## 错误代码

| 错误代码 | 说明 |
|---------|------|
| ERR_INVALID_INPUT | 无效的输入 |
| ERR_NOT_FOUND | 资源不存在 |
| ERR_UNAUTHORIZED | 未授权 |
| ERR_FORBIDDEN | 禁止访问 |
| ERR_DATABASE | 数据库错误 |
| ERR_SERVER | 服务器错误 |

