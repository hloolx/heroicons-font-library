# 🚀 EdgeOne Pages 一键部署指南

<div align="center">
  <img src="https://edgeone.ai/media/34fe3a45-492d-4ea4-ae5d-ea1087ca7b4b.png" alt="EdgeOne Logo" width="200">
  
  # Tencent EdgeOne Pages
  
  亚洲最佳CDN、边缘和安全解决方案
  
  [![使用 EdgeOne Pages 部署](https://cdnstatic.tencentcs.com/edgeone/pages/deploy.svg)](https://edgeone.ai/pages/new?repository-url=https://github.com/hloolx/heroicons-font-library&project-name=heroicons-font&output-directory=.)
</div>

## 📋 什么是 EdgeOne Pages？

[EdgeOne Pages](https://edgeone.ai/) 是腾讯云推出的边缘静态网站托管服务，具有以下特点：

- ⚡ **全球加速** - 基于腾讯云边缘节点，提供全球CDN加速
- 🔒 **安全防护** - 内置 DDoS 防护和 WAF 安全防护
- 🚀 **一键部署** - 支持 GitHub 仓库一键部署
- 💰 **免费额度** - 提供免费使用额度，适合个人项目
- 🌏 **亚洲优化** - 针对亚洲地区特别优化，国内访问速度快

## 🎯 为什么选择 EdgeOne？

### 对比 GitHub Pages

| 特性 | EdgeOne Pages | GitHub Pages |
|------|--------------|--------------|
| 国内访问速度 | ✅ 快速 | ❌ 较慢 |
| 自定义域名 | ✅ 支持 | ✅ 支持 |
| HTTPS | ✅ 自动配置 | ✅ 支持 |
| CDN 加速 | ✅ 全球节点 | ⚠️ 有限 |
| 构建配置 | ✅ 灵活 | ⚠️ 有限 |
| 免费额度 | ✅ 有 | ✅ 完全免费 |

## 🚀 一键部署步骤

### 方法一：使用部署按钮（最简单）

1. **点击下方按钮**：

   [![使用 EdgeOne Pages 部署](https://cdnstatic.tencentcs.com/edgeone/pages/deploy.svg)](https://edgeone.ai/pages/new?repository-url=https://github.com/hloolx/heroicons-font-library&project-name=heroicons-font&output-directory=.)

2. **登录账号**：
   - 使用腾讯云账号登录
   - 或使用微信扫码登录

3. **授权 GitHub**：
   - 首次使用需要授权 EdgeOne 访问你的 GitHub
   - 选择允许访问的仓库

4. **确认配置**：
   - 项目名称：`heroicons-font`
   - 输出目录：`.`（根目录）
   - 构建命令：留空（静态项目无需构建）

5. **点击部署**：
   - 等待 1-2 分钟
   - 部署成功后会分配一个默认域名

### 方法二：手动配置

1. **访问 EdgeOne 控制台**：
   - 打开 [EdgeOne Pages 控制台](https://edgeone.ai/pages)
   - 登录你的账号

2. **创建新项目**：
   - 点击 "新建项目"
   - 选择 "从 GitHub 导入"

3. **选择仓库**：
   - 搜索 `heroicons-font-library`
   - 选择你的仓库

4. **配置部署**：
   ```json
   {
     "项目名称": "heroicons-font",
     "分支": "main",
     "构建命令": "",
     "输出目录": ".",
     "安装命令": ""
   }
   ```

5. **环境变量**（可选）：
   - 本项目无需环境变量

6. **开始部署**：
   - 点击 "部署"
   - 等待部署完成

## 🔧 配置文件说明

项目根目录的 `edgeone.json` 文件用于配置部署：

```json
{
  "build": {
    "command": "",        // 构建命令，静态项目留空
    "output": "."         // 输出目录，使用根目录
  },
  "deploy": {
    "projectName": "heroicons-font-library",
    "installCommand": "", // 安装命令，静态项目留空
    "headers": [
      {
        "key": "Cache-Control",
        "value": "public, max-age=3600"  // CDN缓存1小时
      },
      {
        "key": "X-Content-Type-Options",
        "value": "nosniff"
      }
    ]
  }
}
```

## 🌐 访问你的网站

部署成功后，你将获得：

1. **默认域名**：
   ```
   https://[项目名].edgeone.page
   ```

2. **自定义域名**（可选）：
   - 在项目设置中添加自定义域名
   - 配置 DNS CNAME 记录
   - EdgeOne 自动配置 SSL 证书

## 📊 查看部署状态

### 控制台查看

1. 访问 [EdgeOne Pages 控制台](https://edgeone.ai/pages)
2. 选择你的项目
3. 查看部署历史和日志

### 部署状态

- 🟡 **部署中** - 正在构建和部署
- ✅ **成功** - 部署完成，网站已上线
- ❌ **失败** - 部署失败，查看日志排查

## 🔄 更新部署

### 自动部署

配置 GitHub 仓库后，每次推送到 main 分支都会自动触发部署：

```bash
git add .
git commit -m "Update icons"
git push origin main
# EdgeOne 自动检测并部署
```

### 手动重新部署

1. 进入项目控制台
2. 点击 "重新部署"
3. 选择要部署的分支或提交

## ⚙️ 高级配置

### 1. 配置重定向

在 `edgeone.json` 中添加：

```json
{
  "redirects": [
    {
      "from": "/old-path",
      "to": "/new-path",
      "status": 301
    }
  ]
}
```

### 2. 自定义响应头

```json
{
  "headers": [
    {
      "key": "X-Frame-Options",
      "value": "SAMEORIGIN"
    },
    {
      "key": "Content-Security-Policy",
      "value": "default-src 'self'"
    }
  ]
}
```

### 3. 配置缓存策略

```json
{
  "headers": [
    {
      "key": "Cache-Control",
      "value": "public, max-age=31536000",
      "path": "*.woff2"  // 字体文件长期缓存
    }
  ]
}
```

## 🚨 常见问题

### 1. 部署失败

**问题**：部署状态显示失败

**解决方案**：
- 检查 `edgeone.json` 格式是否正确
- 确认仓库权限已授权
- 查看部署日志了解具体错误

### 2. 字体文件不显示

**问题**：图标显示为方块

**解决方案**：
- 检查字体文件路径是否正确
- 确认 MIME 类型配置正确
- 清除浏览器缓存重试

### 3. 访问速度慢

**问题**：首次加载较慢

**解决方案**：
- EdgeOne CDN 需要预热
- 配置合适的缓存策略
- 使用 webp 等优化格式

### 4. 自定义域名配置

**问题**：自定义域名无法访问

**解决方案**：
1. 确认 DNS 记录已生效（使用 `nslookup` 检查）
2. 等待 SSL 证书配置完成（通常 10-30 分钟）
3. 检查域名是否已备案（中国大陆域名）

## 💡 优化建议

### 1. 启用 Gzip 压缩

EdgeOne 默认启用 Gzip，可进一步配置 Brotli 压缩。

### 2. 资源预加载

在 HTML 中添加：

```html
<link rel="preload" href="iconfont.woff2" as="font" type="font/woff2" crossorigin>
```

### 3. 使用 CDN 链接

部署后，可以直接使用 EdgeOne CDN 链接：

```html
<link rel="stylesheet" href="https://[你的域名]/iconfont.css">
```

## 📈 监控和分析

EdgeOne 提供详细的访问分析：

- **流量统计** - 查看访问量和带宽使用
- **访问分析** - 了解用户地域分布
- **性能监控** - 页面加载速度分析
- **错误日志** - 4xx/5xx 错误追踪

## 🆓 免费额度

EdgeOne Pages 提供免费套餐：

- ✅ 每月 100GB 流量
- ✅ 无限部署次数
- ✅ 自定义域名支持
- ✅ 自动 SSL 证书
- ✅ 全球 CDN 加速

对于个人项目和小型网站完全够用！

## 📚 相关链接

- [EdgeOne 官网](https://edgeone.ai/)
- [EdgeOne Pages 文档](https://edgeone.ai/zh/document/173005746548674560)
- [控制台登录](https://edgeone.ai/pages)
- [定价说明](https://edgeone.ai/pricing)

---

<div align="center">

### 🎉 立即体验极速部署！

[![使用 EdgeOne Pages 部署](https://cdnstatic.tencentcs.com/edgeone/pages/deploy.svg)](https://edgeone.ai/pages/new?repository-url=https://github.com/hloolx/heroicons-font-library&project-name=heroicons-font&output-directory=.)

让你的图标库在亚洲地区获得最佳访问体验！

</div>