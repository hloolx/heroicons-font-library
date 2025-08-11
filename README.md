# Heroicons Font - Heroicons 字体图标库

<div align="center">

![Version](https://img.shields.io/badge/version-1.0.0-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Icons](https://img.shields.io/badge/icons-224-orange)
![Language](https://img.shields.io/badge/language-中文/English-red)

[在线预览 Demo](https://your-demo-url.com) | [English](#english) | [中文](#中文)

</div>

## 中文

### 📋 项目介绍

这是一个基于 [Heroicons](https://github.com/tailwindlabs/heroicons) 的字体图标库项目。通过技术转换，将原本使用 stroke（描边）方式绘制的 SVG 图标转换为可作为字体使用的填充路径，填补了 GitHub 上 Heroicons 字体版本的空白。

### ✨ 特性

- 🎨 **224 个精美图标** - 来自 Heroicons 的高质量设计
- 🔍 **中英文搜索** - 支持中文名称搜索（如"电话"、"下载"、"设置"）
- 📋 **一键复制** - 点击图标即可复制类名，无需手动选择
- 🌏 **双语支持** - 界面支持中英文切换
- 📱 **响应式设计** - 完美适配各种屏幕尺寸
- ⚡ **轻量高效** - 纯前端实现，无需后端服务

### 🎯 制作初衷

在开发个人博客 [www.alantx.cn](https://www.alantx.cn) 时，需要使用 Heroicons 图标，但发现：

1. Heroicons 的 outline 图标采用 stroke 方式绘制，无法直接作为字体图标使用
2. GitHub 上缺少将 Heroicons 转换为字体图标的完整解决方案
3. 现有的图标库不支持中文搜索，对国内开发者不够友好

因此决定自己动手，将这套优秀的图标集转换为更易用的字体格式，并分享给社区。

### 🛠 技术实现

#### 1. SVG 转换流程

```bash
# 安装依赖
npm install oslllo-svg-fixer

# 运行转换脚本
node convert-svg-proper.js
```

转换脚本核心代码：

```javascript
const SVGFixer = require('oslllo-svg-fixer');

const options = {
    showProgressBar: true,
    throwIfDestinationDoesNotExist: false,
    traceResolution: 600  // 高分辨率以获得更好的质量
};

await SVGFixer(inputDir, outputDir, options).fix();
```

#### 2. 字体生成

使用阿里巴巴 [iconfont.cn](https://www.iconfont.cn/) 平台将转换后的 SVG 文件生成字体文件：
- `.ttf` - TrueType Font
- `.woff` - Web Open Font Format
- `.woff2` - Web Open Font Format 2.0

#### 3. 前端实现

- **原生 JavaScript** - 无框架依赖，加载快速
- **CSS Variables** - 主题颜色管理
- **Async/Await** - 异步加载图标数据
- **模糊搜索算法** - 智能匹配图标名称

### 📦 使用方法

#### 在项目中引入

1. 下载字体文件和 CSS 文件
2. 在 HTML 中引入：

```html
<link rel="stylesheet" href="iconfont.css">
```

3. 使用图标：

```html
<i class="iconfont icon-home"></i>
<i class="iconfont icon-user"></i>
<i class="iconfont icon-heart"></i>
```

#### 自定义大小和颜色

```css
.iconfont {
    font-size: 24px;
    color: #2563eb;
}
```

### 🔍 搜索示例

- 搜索 **"电话"** → phone, phone-arrow-down-left, phone-arrow-up-right 等
- 搜索 **"下载"** → download, cloud-arrow-down, folder-arrow-down 等
- 搜索 **"文件"** → folder, document, clipboard 等
- 搜索 **"arrow"** → 所有箭头相关图标
- 搜索 **"设置"** → cog, cog-6-tooth, cog-8-tooth 等

### 📄 开源协议

本项目基于 MIT 协议开源：

- 原始图标版权归 [Tailwind Labs Inc.](https://github.com/tailwindlabs) 所有
- 图标遵循 [MIT License](https://opensource.org/licenses/MIT)
- 可免费用于商业和个人项目
- 使用时请保留原始版权声明

### 🙏 致谢

- [Heroicons](https://github.com/tailwindlabs/heroicons) - 精美的 SVG 图标集
- [Tailwind CSS](https://tailwindcss.com/) - 实用优先的 CSS 框架
- [Steve Schoger](https://twitter.com/steveschoger) - Heroicons 设计师
- [阿里巴巴 iconfont](https://www.iconfont.cn/) - 字体转换平台
- [oslllo-svg-fixer](https://github.com/oslllo/svg-fixer) - SVG 转换工具

---

## English

### 📋 Project Introduction

This is a font icon library based on [Heroicons](https://github.com/tailwindlabs/heroicons). Through technical conversion, the SVG icons originally drawn with stroke are converted into fill paths that can be used as fonts, filling the gap of Heroicons font version on GitHub.

### ✨ Features

- 🎨 **224 Beautiful Icons** - High-quality designs from Heroicons
- 🔍 **Bilingual Search** - Support Chinese and English search
- 📋 **One-click Copy** - Click to copy class name instantly
- 🌏 **Bilingual Interface** - Switch between Chinese and English
- 📱 **Responsive Design** - Perfect for all screen sizes
- ⚡ **Lightweight** - Pure frontend, no backend required

### 🎯 Motivation

When developing my personal blog [www.alantx.cn](https://www.alantx.cn), I needed to use Heroicons but found:

1. Heroicons outline icons use stroke rendering, cannot be used directly as font icons
2. No complete solution on GitHub for converting Heroicons to font icons
3. Existing icon libraries don't support Chinese search

So I decided to convert this excellent icon set into a more usable font format and share it with the community.

### 🛠 Technical Implementation

#### 1. SVG Conversion Process

```bash
# Install dependencies
npm install oslllo-svg-fixer

# Run conversion script
node convert-svg-proper.js
```

Core conversion code:

```javascript
const SVGFixer = require('oslllo-svg-fixer');

const options = {
    showProgressBar: true,
    throwIfDestinationDoesNotExist: false,
    traceResolution: 600  // High resolution for better quality
};

await SVGFixer(inputDir, outputDir, options).fix();
```

#### 2. Font Generation

Using Alibaba [iconfont.cn](https://www.iconfont.cn/) platform to generate font files:
- `.ttf` - TrueType Font
- `.woff` - Web Open Font Format
- `.woff2` - Web Open Font Format 2.0

#### 3. Frontend Implementation

- **Vanilla JavaScript** - No framework dependencies
- **CSS Variables** - Theme color management
- **Async/Await** - Asynchronous icon data loading
- **Fuzzy Search** - Smart icon name matching

### 📦 Usage

#### Include in Your Project

1. Download font files and CSS file
2. Include in HTML:

```html
<link rel="stylesheet" href="iconfont.css">
```

3. Use icons:

```html
<i class="iconfont icon-home"></i>
<i class="iconfont icon-user"></i>
<i class="iconfont icon-heart"></i>
```

#### Custom Size and Color

```css
.iconfont {
    font-size: 24px;
    color: #2563eb;
}
```

### 📄 License

This project is open source under the MIT License:

- Original icons copyright belongs to [Tailwind Labs Inc.](https://github.com/tailwindlabs)
- Icons follow [MIT License](https://opensource.org/licenses/MIT)
- Free for commercial and personal use
- Please retain original copyright notice when using

### 🙏 Acknowledgments

- [Heroicons](https://github.com/tailwindlabs/heroicons) - Beautiful SVG icon set
- [Tailwind CSS](https://tailwindcss.com/) - Utility-first CSS framework
- [Steve Schoger](https://twitter.com/steveschoger) - Heroicons designer
- [Alibaba iconfont](https://www.iconfont.cn/) - Font conversion platform
- [oslllo-svg-fixer](https://github.com/oslllo/svg-fixer) - SVG conversion tool

---

## 📁 项目结构 / Project Structure

```
heroicons-font/
├── index.html           # 图标预览页面 / Icon preview page
├── about.html          # 关于页面 / About page
├── iconfont.css        # 图标样式 / Icon styles
├── iconfont.ttf        # 字体文件 / Font file
├── iconfont.woff       # 字体文件 / Font file
├── iconfont.woff2      # 字体文件 / Font file
├── iconfont.json       # 图标数据 / Icon data
├── icon-names.js       # 中英文名称映射 / Name mapping
└── README.md          # 说明文档 / Documentation
```

## 🤝 贡献 / Contributing

欢迎提交 Issue 和 Pull Request！

Contributions are welcome! Please feel free to submit Issues and Pull Requests.

## 📮 联系方式 / Contact

- Blog: [www.alantx.cn](https://www.alantx.cn)
- GitHub: [@yourusername](https://github.com/yourusername)
- Email: your-email@example.com

## 📊 Star History

[![Star History Chart](https://api.star-history.com/svg?repos=yourusername/heroicons-font&type=Date)](https://star-history.com/#yourusername/heroicons-font&Date)

---

<div align="center">
Made with ❤️ by Alan in 2025
</div>