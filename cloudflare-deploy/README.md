# AurumFi Cloudflare Pages 部署包

## 📁 文件结构

```
cloudflare-deploy/
├── index.html              # 主页 (官网首页)
├── app.html                # 应用页面 (aUSD 铸造和管理)
├── liquidity-mining.html   # 流动性挖矿活动页面
├── dashboard.html          # KPI 监控仪表板
├── calculator.html         # 盈利计算器
├── 404.html               # 404 错误页面
├── robots.txt             # 搜索引擎爬虫配置
├── sitemap.xml            # 网站地图
├── _redirects             # Cloudflare Pages 重定向配置
├── _headers               # 安全头和缓存配置
└── README.md              # 部署说明文档
```

## 🚀 部署步骤

### 1. 准备 Cloudflare 账户
- 注册/登录 Cloudflare 账户
- 进入 Cloudflare Pages 控制台

### 2. 创建新项目
1. 点击 "Create a project"
2. 选择 "Upload assets" 或连接 Git 仓库
3. 项目名称: `aurumfi` 或 `aurumfi-app`

### 3. 上传文件
- 将 `cloudflare-deploy` 文件夹中的所有文件上传
- 确保 `index.html` 在根目录

### 4. 配置自定义域名 (可选)
- 在 Cloudflare Pages 项目设置中
- 添加自定义域名: `aurumfi.com`
- 配置 DNS 记录

### 5. 环境变量配置 (如需要)
```
NODE_ENV=production
API_URL=https://api.aurumfi.com
```

## 🔧 页面功能说明

### index.html - 主页
- **功能**: AurumFi 官网首页
- **特色**: 响应式设计，动画效果，数据展示
- **路由**: `/` 或 `/index.html`

### app.html - 应用页面
- **功能**: aUSD 铸造和 PAXG 赎回
- **特色**: 钱包连接，实时计算，交易历史
- **路由**: `/app.html`

### liquidity-mining.html - 流动性挖矿
- **功能**: 流动性挖矿活动页面
- **特色**: 收益计算器，钱包连接，活动介绍
- **路由**: `/liquidity-mining.html` 或 `/mining`

### dashboard.html - 数据仪表板
- **功能**: KPI 监控和数据分析
- **特色**: 实时图表，多维度数据，交互式界面
- **路由**: `/dashboard.html` 或 `/data`

### calculator.html - 盈利计算器
- **功能**: 盈利模式分析和计算
- **特色**: 动态参数调整，情景分析，可视化图表
- **路由**: `/calculator.html` 或 `/profit`

## 🛡️ 安全配置

### _headers 文件配置
- **CSP**: 内容安全策略
- **HSTS**: 强制 HTTPS
- **XSS 保护**: 跨站脚本攻击防护
- **缓存控制**: 静态资源缓存优化

### _redirects 文件配置
- **友好 URL**: 简化访问路径
- **API 代理**: 后端 API 路由
- **404 处理**: 错误页面重定向

## 📊 性能优化

### 缓存策略
- **HTML 文件**: 1小时缓存
- **CSS/JS 文件**: 1年缓存
- **图片文件**: 1年缓存

### 压缩优化
- **Gzip 压缩**: 自动启用
- **Brotli 压缩**: 自动启用
- **图片优化**: Cloudflare 自动优化

## 🔗 URL 路由映射

| 友好 URL | 实际文件 | 功能描述 |
|----------|----------|----------|
| `/` | `index.html` | 主页 |
| `/mining` | `liquidity-mining.html` | 流动性挖矿 |
| `/data` | `dashboard.html` | 数据仪表板 |
| `/profit` | `calculator.html` | 盈利计算器 |
| `/application` | `app.html` | 应用页面 |

## 📱 移动端适配

所有页面都已针对移动端进行优化：
- **响应式设计**: 适配各种屏幕尺寸
- **触摸友好**: 按钮和交互元素优化
- **加载速度**: 移动端性能优化

## 🔍 SEO 优化

### 已配置的 SEO 元素
- **Meta 标签**: 标题、描述、关键词
- **Open Graph**: 社交媒体分享优化
- **结构化数据**: 搜索引擎理解
- **网站地图**: `sitemap.xml`
- **Robots.txt**: 爬虫指引

## 📈 分析和监控

### 建议集成的工具
- **Google Analytics**: 网站访问分析
- **Cloudflare Analytics**: 性能和安全分析
- **Hotjar**: 用户行为分析
- **Sentry**: 错误监控

## 🚨 部署后检查清单

### 功能测试
- [ ] 主页加载正常
- [ ] 所有页面链接可访问
- [ ] 移动端显示正常
- [ ] 钱包连接功能正常 (如果有 MetaMask)
- [ ] 计算器功能正常
- [ ] 图表显示正常

### 性能测试
- [ ] 页面加载速度 < 3秒
- [ ] 移动端性能评分 > 90
- [ ] 所有资源正确缓存
- [ ] HTTPS 正确配置

### SEO 检查
- [ ] 所有页面有正确的 title 和 meta
- [ ] sitemap.xml 可访问
- [ ] robots.txt 配置正确
- [ ] 404 页面正常显示

## 🔄 更新和维护

### 内容更新
1. 修改对应的 HTML 文件
2. 重新上传到 Cloudflare Pages
3. 清除缓存 (如需要)

### 版本控制
- 建议使用 Git 管理代码
- 连接 GitHub 仓库实现自动部署
- 设置分支保护和审核流程

## 📞 技术支持

如遇到部署问题，请检查：
1. 文件路径是否正确
2. _redirects 和 _headers 配置是否有效
3. 自定义域名 DNS 配置是否正确
4. Cloudflare Pages 构建日志

---

**部署完成后，AurumFi 网站将在 Cloudflare 的全球 CDN 网络上运行，提供快速、安全、可靠的用户体验。**