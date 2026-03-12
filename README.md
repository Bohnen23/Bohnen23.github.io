# 书简与散步 — Hugo 博客

## 快速开始

### 1. 安装 Hugo

**macOS：**
```bash
brew install hugo
```

**Windows：**
```bash
# 用 Chocolatey
choco install hugo-extended

# 或用 Scoop
scoop install hugo-extended
```

**Linux：**
```bash
sudo apt install hugo
# 或者从 https://github.com/gohugoio/hugo/releases 下载
```

### 2. 本地预览

```bash
cd hugo-blog
hugo server
```

打开浏览器访问 `http://localhost:1313`，就能看到博客了。
修改任何文件都会自动刷新。

### 3. 写新文章

```bash
hugo new posts/my-new-post.md
```

这会在 `content/posts/` 下创建一个新文件，打开它，改标题、选分类、写正文：

```markdown
---
title: "文章标题"
date: 2026-03-15
categories: ["随笔"]
slug: "my-new-post"
---

正文写在这里。支持 Markdown 语法。
```

**可用的分类：**
- `写给你的信` — 写给孩子的信
- `随笔` — 思考与杂文
- `生活` — 日常记录
- `她们的故事` — 女性主题

你也可以随时新增分类，只要在文章的 `categories` 里写新名字就行。

### 4. 生成静态网站

```bash
hugo
```

生成的文件在 `public/` 文件夹里，可以部署到任何地方。

### 5. 部署到 GitHub Pages

1. 在 GitHub 创建仓库，比如 `yourusername.github.io`
2. 把整个项目推上去
3. 在仓库 Settings → Pages 里选择 GitHub Actions
4. 创建 `.github/workflows/hugo.yml`（Hugo 官方文档有现成模板）
5. 每次推送代码，网站自动更新

也可以部署到 Netlify 或 Vercel，拖拽 `public/` 文件夹即可。

## 项目结构

```
hugo-blog/
├── hugo.toml              ← 全站配置（标题、作者、描述等）
├── content/
│   ├── about.md           ← "关于"页面
│   └── posts/             ← 所有文章放这里
│       ├── letter-01-courage.md
│       ├── lost-in-three-languages.md
│       └── ...
├── layouts/
│   ├── _default/
│   │   ├── baseof.html    ← 页面骨架
│   │   ├── list.html      ← 首页（文章列表）
│   │   ├── single.html    ← 文章详情页
│   │   └── about.html     ← 关于页面
│   └── partials/
│       ├── head.html      ← <head> 标签
│       ├── nav.html       ← 导航栏
│       └── footer.html    ← 页脚
├── static/
│   └── css/
│       └── style.css      ← 样式表
└── archetypes/
    └── default.md         ← 新文章模板
```

## 常用修改

**改博客名称或描述：** 编辑 `hugo.toml`

**改样式：** 编辑 `static/css/style.css`

**改导航栏：** 编辑 `layouts/partials/nav.html`

**改页脚：** 编辑 `layouts/partials/footer.html`

**改文章排版：** 编辑 `layouts/_default/single.html`

## 日常写作流程

```bash
# 1. 新建文章
hugo new posts/article-name.md

# 2. 写作（用任何编辑器打开 .md 文件）

# 3. 本地预览
hugo server

# 4. 满意后生成并部署
hugo
git add . && git commit -m "新文章" && git push
```

就这么简单。专心写字就好。
