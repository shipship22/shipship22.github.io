# Shipship's Blog

> 个人博客，基于 Hexo 7 + GitHub Pages，自动化部署。  
> 🌐 访问地址：**[https://shipship22.github.io](https://shipship22.github.io)**

---

## 项目结构

```
shipship22.github.io/
├── source/
│   ├── _posts/          # 博客文章（Markdown）
│   ├── about/           # 关于页面
│   ├── tags/            # 标签页面
│   └── categories/      # 分类页面
├── themes/              # 主题文件
├── scaffolds/           # 文章模板
├── _config.yml          # Hexo 主配置文件
├── _config.landscape.yml # 主题配置文件
└── .github/workflows/
    └── deploy.yml       # GitHub Actions 自动部署
```

---

## 本地开发

### 前置要求

- [Node.js](https://nodejs.org/) v18 或更高版本
- Git

### 安装与启动

```bash
# 克隆仓库
git clone https://github.com/shipship22/shipship22.github.io.git
cd shipship22.github.io

# 安装依赖
npm install

# 启动本地预览（访问 http://localhost:4000）
npx hexo server
```

### 新建文章

```bash
npx hexo new "文章标题"
# 文章创建在 source/_posts/ 目录
```

文章 Front Matter 模板：

```yaml
---
title: 文章标题
date: 2025-01-01 12:00:00
categories:
  - 分类
tags:
  - 标签1
  - 标签2
---

文章摘要内容...

<!-- more -->

正文内容...
```

> **提示**：`<!-- more -->` 之前的内容作为首页摘要展示。

---

## 自动部署

本项目使用 **GitHub Actions** 实现自动化部署：

1. 向 `main` 分支推送代码后，Actions 自动触发
2. 构建 Hexo 静态文件
3. 将生成的 `public/` 目录推送到 `gh-pages` 分支
4. GitHub Pages 从 `gh-pages` 分支提供网站服务

### ⚠️ 首次部署必读：修改 GitHub Pages 设置

默认 GitHub Pages 从 `main` 分支提供服务，需要改为 `gh-pages` 分支：

1. 打开仓库页面 → **Settings** → **Pages**
2. 在 **Branch** 下拉框中选择 `gh-pages`，目录选 `/ (root)`
3. 点击 **Save**

完成后，每次推送到 `main` 都会自动更新网站，通常 1~2 分钟内生效。

---

## 手动部署（备用）

如需手动部署：

```bash
# 安装 hexo-deployer-git
npm install hexo-deployer-git --save

# 生成并部署
npx hexo clean && npx hexo g -d
```

---

## 技术栈

| 工具 | 版本 | 说明 |
|------|------|------|
| [Hexo](https://hexo.io/) | 7.x | 静态博客框架 |
| Hexo Landscape | 默认 | 博客主题 |
| GitHub Pages | — | 免费静态托管 |
| GitHub Actions | — | CI/CD 自动部署 |

---

## License

[MIT](LICENSE)
