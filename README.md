# 技术博客

基于 GitHub Pages 原生 Jekyll 和 Minima 主题。当前仅包含仓库骨架，文章将在审核后加入。

## 目录

- `_posts/`：Markdown 文章。
- `assets/images/`：公开图片。
- `scripts/`：可公开的复现脚本，不输出到网站。
- `_includes/custom-head.html`：MathJax 公式渲染配置。

## 新增文章

创建 `_posts/YYYY-MM-DD-article-slug.md`，日期采用实际确认的发布日期：

```markdown
---
layout: post
title: "文章标题"
date: YYYY-MM-DD
---

正文。
```

图片放入 `assets/images/<article-slug>/`。当前固定链接为 `/posts/<article-slug>/`，可用标准 Markdown 引用 `../../assets/images/<article-slug>/figure.png`；发布前需同时检查网页和本地预览。调整固定链接时，需重新核对相对路径。

支持公式、表格和代码块。公式由浏览器加载 MathJax 渲染，首次发布需检查实际效果。

## 发布

目标仓库：`986882799-gif/986882799-gif.github.io`。

在 GitHub 设置 Pages：Deploy from a branch → `main` → `/ (root)`。推送前检查 `git diff --cached`，仅提交已确认可公开的内容。请勿提交原始工作目录、配置备份、凭据、废稿或 `_site/`。

```sh
git add <明确选定的文件>
git commit -m "Add article"
git push origin main
```

仓库创建、首次推送和 Pages 启用尚未执行。部署后检查 Pages 构建状态、首页列表、文章图片与公式。

## 本地预览（可选）

安装 Ruby 和 Bundler 后执行 `bundle install`、`bundle exec jekyll serve`。当前骨架仅进行静态检查，不代表已通过 Jekyll 构建。
