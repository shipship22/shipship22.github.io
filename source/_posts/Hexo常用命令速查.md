---
title: Hexo 常用命令速查
date: 2025-03-24 10:30:55
categories:
  - 技术
tags:
  - Hexo
  - 速查表
---

日常使用 Hexo 时最常用的命令合集，方便随时查阅。

<!-- more -->

## 文章管理

```bash
# 新建文章
hexo new "文章标题"

# 新建草稿
hexo new draft "草稿标题"

# 将草稿发布
hexo publish "草稿标题"
```

新建的文章保存在 `source/_posts/` 目录，Markdown 格式，支持 Front Matter：

```yaml
---
title: 文章标题
date: 2025-01-01 12:00:00
categories:
  - 分类名
tags:
  - 标签1
  - 标签2
---
```

## 本地预览

```bash
# 启动本地服务器（默认端口 4000）
hexo server
# 或简写
hexo s

# 指定端口
hexo server -p 5000
```

## 生成与部署

```bash
# 生成静态文件（输出到 public/ 目录）
hexo generate
# 或简写
hexo g

# 生成并部署
hexo deploy
# 或简写
hexo d

# 合并命令
hexo g -d
```

## 清理

```bash
# 清理缓存和生成文件
hexo clean

# 清理后重新生成（推荐出现奇怪问题时使用）
hexo clean && hexo g
```

## 页面管理

```bash
# 新建独立页面（如 About、Tags、Categories）
hexo new page "about"
hexo new page "tags"
hexo new page "categories"
```

创建后编辑 `source/about/index.md` 等文件即可。

## 常见问题

### 文章不显示？

```bash
hexo clean && hexo g && hexo s
```

### 中文文章链接乱码？

在 `_config.yml` 中设置固定 permalink：

```yaml
permalink: :year/:month/:day/:abbrlink/
```

安装插件：

```bash
npm install hexo-abbrlink --save
```

---

收藏这篇文章，下次忘记命令时直接来查！
