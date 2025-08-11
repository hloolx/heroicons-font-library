# 📡 CDN 使用指南

## 🌐 跨域使用说明

本图标库支持 CDN 引用，已配置 CORS 允许跨域访问。

### ✅ 直接引用（推荐）

在你的 HTML 中直接添加：

```html
<!-- 引入图标样式 -->
<link rel="stylesheet" href="https://heroicons.15o.cc/iconfont.css">

<!-- 使用图标 -->
<i class="iconfont icon-home"></i>
<i class="iconfont icon-user"></i>
<i class="iconfont icon-heart"></i>
```

### 📦 完整示例

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>使用 Heroicons 字体图标</title>
  
  <!-- 引入 Heroicons 字体图标 -->
  <link rel="stylesheet" href="https://heroicons.15o.cc/iconfont.css">
  
  <style>
    /* 自定义图标样式 */
    .my-icon {
      font-size: 24px;
      color: #2563eb;
      margin: 0 8px;
    }
    
    /* 大图标 */
    .icon-large {
      font-size: 48px;
    }
    
    /* 带动画的图标 */
    .icon-spin {
      animation: spin 2s linear infinite;
    }
    
    @keyframes spin {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }
  </style>
</head>
<body>
  <!-- 基础使用 -->
  <i class="iconfont icon-home"></i>
  
  <!-- 自定义大小和颜色 -->
  <i class="iconfont icon-heart my-icon"></i>
  
  <!-- 大图标 -->
  <i class="iconfont icon-star icon-large"></i>
  
  <!-- 旋转动画 -->
  <i class="iconfont icon-cog icon-spin"></i>
  
  <!-- 在按钮中使用 -->
  <button>
    <i class="iconfont icon-download"></i> 下载
  </button>
</body>
</html>
```

## 🔧 CORS 配置说明

本站已配置以下 CORS 头：

```http
Access-Control-Allow-Origin: *
Access-Control-Allow-Methods: GET, OPTIONS
```

这意味着：
- ✅ 任何网站都可以引用我们的资源
- ✅ 支持 GET 和 OPTIONS 请求
- ✅ 字体文件、CSS、JS 都已开启跨域

## ⚠️ 可能的问题

### 1. 仍然出现 CORS 错误

**原因**：CDN 缓存可能还未更新

**解决方案**：
- 等待几分钟让 CDN 更新
- 尝试清除浏览器缓存
- 使用无痕模式测试

### 2. 字体文件 404

**原因**：路径问题

**解决方案**：
确保使用完整的 URL：
```html
<!-- 正确 -->
<link rel="stylesheet" href="https://heroicons.15o.cc/iconfont.css">

<!-- 错误 -->
<link rel="stylesheet" href="//heroicons.15o.cc/iconfont.css">
<link rel="stylesheet" href="heroicons.15o.cc/iconfont.css">
```

### 3. 图标显示为方块

**原因**：字体文件未加载

**解决方案**：
- 检查网络是否正常
- 确认 CSS 文件已加载
- 检查类名是否正确（如 `icon-home` 不是 `icon-Home`）

## 🚀 高级用法

### 使用 CSS @import

```css
@import url('https://heroicons.15o.cc/iconfont.css');

/* 你的其他样式 */
.my-app {
  /* ... */
}
```

### 使用 JavaScript 动态加载

```javascript
// 动态加载图标样式
function loadIconFont() {
  const link = document.createElement('link');
  link.rel = 'stylesheet';
  link.href = 'https://heroicons.15o.cc/iconfont.css';
  document.head.appendChild(link);
}

// 页面加载完成后加载
window.addEventListener('load', loadIconFont);
```

### 在 React 中使用

```jsx
// 在 App.jsx 或 index.jsx 中
import { useEffect } from 'react';

function App() {
  useEffect(() => {
    // 动态加载图标字体
    const link = document.createElement('link');
    link.rel = 'stylesheet';
    link.href = 'https://heroicons.15o.cc/iconfont.css';
    document.head.appendChild(link);
  }, []);

  return (
    <div>
      <i className="iconfont icon-home"></i>
      <i className="iconfont icon-user"></i>
    </div>
  );
}
```

### 在 Vue 中使用

```vue
<!-- 在 main.js 或 App.vue 中 -->
<template>
  <div>
    <i class="iconfont icon-home"></i>
    <i class="iconfont icon-user"></i>
  </div>
</template>

<style>
@import url('https://heroicons.15o.cc/iconfont.css');
</style>
```

## 📊 性能优化建议

### 1. 预连接

在 HTML `<head>` 中添加：

```html
<link rel="preconnect" href="https://heroicons.15o.cc">
<link rel="dns-prefetch" href="https://heroicons.15o.cc">
```

### 2. 预加载关键字体

```html
<link rel="preload" 
      href="https://heroicons.15o.cc/iconfont.woff2" 
      as="font" 
      type="font/woff2" 
      crossorigin>
```

### 3. 使用字体显示策略

```css
@font-face {
  font-family: 'iconfont';
  font-display: swap; /* 提高感知性能 */
  /* ... */
}
```

## 🎯 CDN 特性

由 Tencent EdgeOne 提供的 CDN 服务具有以下特点：

- ⚡ **全球加速** - 多节点分发
- 🔒 **HTTPS** - 自动 SSL
- 🗜️ **Gzip 压缩** - 自动压缩
- 📊 **智能缓存** - 优化加载速度
- 🛡️ **DDoS 防护** - 安全可靠

## 📱 浏览器兼容性

| 浏览器 | 版本 | 支持情况 |
|--------|------|----------|
| Chrome | 4+ | ✅ |
| Firefox | 3.5+ | ✅ |
| Safari | 3.1+ | ✅ |
| Edge | 12+ | ✅ |
| IE | 9+ | ✅ |
| iOS Safari | 3.2+ | ✅ |
| Android Browser | 2.2+ | ✅ |

## 💡 最佳实践

1. **使用 HTTPS** - 始终使用 `https://` 协议
2. **版本控制** - 考虑在 URL 中添加版本号以便更新
3. **本地备份** - 对于关键项目，建议下载一份本地备份
4. **监控加载** - 使用浏览器开发工具监控资源加载情况

## 🤝 反馈与支持

如果遇到 CDN 使用问题：

1. 检查本文档的问题解决部分
2. 在 [GitHub Issues](https://github.com/hloolx/heroicons-font-library/issues) 提交问题
3. 访问 [在线演示](https://heroicons.15o.cc) 测试

---

<div align="center">

**享受极速的图标加载体验！** 🚀

Powered by [Tencent EdgeOne](https://edgeone.ai/zh?from=github)

</div>