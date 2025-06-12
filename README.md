# NBA Basketball News Hub

一个现代化的NBA篮球新闻、比分和赛程聚合网站，提供实时的NBA资讯和数据展示。

## 🏀 项目特色

- **自动抓取**: 每30分钟自动从官方源抓取最新NBA新闻
- **多源整合**: 集成NBA官网、ESPN等权威新闻源
- **实时更新**: 支持手动刷新和自动后台更新
- **响应式设计**: 完美适配桌面和移动设备
- **现代UI**: 采用现代化设计风格，提供流畅的用户体验
- **智能跳转**: 点击新闻卡片直接跳转到原文

## 🛠 技术架构

### 后端技术栈
- **Node.js**: 服务器运行环境
- **Express**: Web应用框架
- **Axios**: HTTP请求库
- **Cheerio**: 服务器端HTML解析
- **Node-Cron**: 定时任务调度
- **CORS**: 跨域资源共享支持

### 前端技术栈
- **HTML5**: 现代化标记语言
- **CSS3**: 响应式样式设计
- **JavaScript ES6+**: 现代JavaScript特性
- **Font Awesome**: 图标库
- **Google Fonts**: 网页字体

## 📁 项目结构

```
nba-news-scraper/
├── package.json          # 项目配置和依赖
├── server.js            # Express服务器主文件
├── scraper.js           # 新闻抓取模块
├── README.md            # 项目文档
└── public/              # 静态资源目录
    ├── index.html       # 主页面
    ├── styles.css       # 样式文件
    └── script.js        # 前端JavaScript
```

## 📋 核心功能

### 1. 新闻抓取系统
- **多源抓取**: 同时从NBA官网和ESPN抓取新闻
- **智能去重**: 自动过滤重复内容
- **容错机制**: 抓取失败时提供模拟数据
- **数据清洗**: 处理链接、标题和日期格式

### 2. 定时更新机制
- **服务器端**: 每30分钟自动抓取新闻
- **客户端**: 每5分钟静默更新页面数据
- **手动刷新**: 用户可随时点击刷新按钮

### 3. 优雅的用户界面
- **卡片式布局**: 新闻以卡片形式展示
- **动画效果**: 流畅的加载和悬停动画
- **状态指示**: 显示加载状态和更新时间
- **空状态处理**: 优雅处理无数据情况

## 🚀 快速开始

### 环境要求
- Node.js 14.0 或更高版本
- npm 6.0 或更高版本

### 安装步骤

1. **安装依赖**
```powershell
cd nba-news-scraper
npm install
```

2. **启动服务器**
```powershell
npm start
```

3. **访问网站**
打开浏览器访问: `http://localhost:3000`

### 开发模式
```powershell
npm run dev
```
使用nodemon实现代码修改自动重启

## 🔧 API接口

### GET /api/news
获取新闻列表
```json
{
  "success": true,
  "data": [
    {
      "title": "Lakers vs Warriors: Epic Showdown Tonight",
      "link": "https://www.nba.com/news/lakers-warriors-preview",
      "date": "2 hours ago",
      "source": "NBA Official",
      "timestamp": "2024-01-01T12:00:00.000Z"
    }
  ],
  "timestamp": "2024-01-01T12:00:00.000Z"
}
```

### POST /api/refresh
手动刷新新闻数据
```json
{
  "success": true,
  "message": "News data refreshed successfully",
  "count": 15
}
```

## 🎨 设计特色

### 颜色方案
- **主色调**: NBA蓝 (#1d428a)
- **辅助色**: NBA红 (#c8102e)
- **强调色**: 金黄色 (#fdb927)
- **文本色**: 深灰色 (#2c3e50)

### 响应式设计
- **桌面**: 多列网格布局
- **平板**: 双列布局
- **手机**: 单列布局

### 动画效果
- **加载动画**: 旋转图标
- **卡片动画**: 悬停上升效果
- **渐入动画**: 页面元素逐个显示

## 🔍 抓取策略

### 数据源配置
```javascript
sources: [
  {
    name: 'NBA Official',
    url: 'https://www.nba.com/news',
    selector: '.ContentList_list__item'
  },
  {
    name: 'ESPN NBA',
    url: 'https://www.espn.com/nba/',
    selector: '.contentItem'
  }
]
```

### 抓取流程
1. **并发请求**: 同时访问多个新闻源
2. **内容解析**: 使用CSS选择器提取信息
3. **数据验证**: 检查标题和链接有效性
4. **去重处理**: 基于标题进行去重
5. **排序输出**: 按时间戳降序排列

## 🛡 安全特性

- **XSS防护**: HTML内容转义处理
- **请求头伪装**: 模拟真实浏览器请求
- **跨域支持**: 配置CORS中间件
- **错误处理**: 完善的异常捕获机制

## 📱 兼容性

### 浏览器支持
- Chrome 70+
- Firefox 65+
- Safari 12+
- Edge 79+

### 设备支持
- 桌面电脑 (1200px+)
- 平板设备 (768px - 1199px)
- 手机设备 (320px - 767px)

## 🔄 更新日志

### v1.2.0 (2024-12-06)
- 🏀 **重大功能更新**: 增加比分和赛程展示
- 📰 **数据源优化**: 更新为NBA官方Top Stories页面 
- 🎯 **新功能**: 添加"Recent Scores"和"Upcoming Games"标签页
- 🎨 **UI增强**: 设计专属的比分卡片和赛程卡片样式
- 📱 **交互改进**: 实现标签页切换功能
- 🔧 **数据分类**: 智能分离新闻、比分、赛程三类内容
- 🎮 **真实数据**: 集成当前NBA总决赛实况（步行者vs雷霆）
- 🚀 **性能优化**: 改进数据渲染和页面加载速度

### 详细改动内容：

#### 后端更新 (scraper.js)
- 更新抓取源为 `https://www.nba.com/news/category/top-stories`
- 增加比分数据源 `https://www.nba.com/games`
- 优化CSS选择器适配NBA官网结构
- 更新模拟数据包含真实NBA新闻内容
- 增加数据类型分类：news, score, schedule

#### 前端更新 (HTML/CSS/JS)
- 新增比分和赛程展示区域
- 实现标签页切换功能 (Recent Scores / Upcoming Games)
- 设计NBA主题色彩的比分卡片
- 增加游戏状态显示 (FINAL / UPCOMING)
- 响应式网格布局适配新内容
- 智能解析比分和赛程信息

#### 数据结构优化
- 新增 `type` 字段区分内容类型
- 优化数据渲染逻辑支持多类型内容
- 改进错误处理和空状态显示

### v1.1.0 (2024-01-01)
- ✨ 初始版本发布
- 🚀 实现多源新闻抓取
- 💫 添加自动更新机制
- 🎨 完成响应式UI设计
- 🔧 配置定时任务系统

## 🤝 贡献指南

1. Fork 本项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开 Pull Request

## 📞 技术支持

如遇到问题或需要帮助，请通过以下方式联系：

- 📧 技术支持: support@nbanews.com
- 🐛 问题反馈: 请在GitHub Issues中提交
- 💡 功能建议: 欢迎提出改进意见

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件

---

**© 2024 NBA News Hub. All rights reserved.**

*Latest basketball news from official sources* 