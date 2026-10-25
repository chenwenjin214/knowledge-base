# 我的知识库

> 用 GitHub Pages 搭的个人知识库。边玩边学,攒下来就是自己的东西。

## 这是什么

一个纯静态网站,托管在 GitHub Pages 上。改完只要 commit 一下,线上几十秒自动更新。

- **在线地址**: `https://<你的用户名>.github.io/<仓库名>/`
- **技术栈**: 原生 HTML + CSS,没有构建步骤,没有依赖,不要钱

## 目录结构

```
.
├── index.html            # 首页(文章导航)
├── pages/
│   └── github-101.html   # GitHub 生存指南
├── assets/
│   └── style.css         # 全站共享样式
├── README.md
└── .nojekyll             # 让 Pages 按纯静态托管,不走 Jekyll
```

## 怎么加一篇新文章

1. 在 `pages/` 里新建 `xxx.html`,复制现有的页面改内容
2. 回到 `index.html`,在 `<div class="kb-grid">` 里加一段 `<a class="kb-card">`
3. 在 GitHub 网页上点 **Commit changes**

三步,一分钟,连命令行都不用碰。

## 本地预览

```bash
# 任选其一
python3 -m http.server 8000
npx serve .
```

然后浏览器打开 `http://localhost:8000`。

## 一些约定

- 分类用 `kicker`(小标签),标题用 `h3`,简介一句话说清这页讲什么
- 页面路径用相对路径:`../assets/style.css`、链接回首页用 `../index.html`
- 每个页面的 `<head>` 里带上同样的 `<title>` 和 `<link>`,改标题那行

## 想继续折腾的话

- 加个深色模式:在 `style.css` 里加一组 `@media (prefers-color-scheme: dark)` 变量覆盖
- 加个搜索:把 `kb-card` 的标题渲染成 JSON,加一个简单的过滤框
- 换个框架:Pages 支持在仓库根目录放 `mkdocs.yml` 或 `docs/`,用 MkDocs / Docusaurus / VitePress 都能自动生成带侧边栏的站点
