# Shiro for Astro

[Shiro](https://github.com/Innei/Shiro) 的社区静态迁移版，使用 Astro，专注首页视觉和阅读体验。无需 Mix Space 后端或生产 Node 服务器，可部署到 GitHub Pages。

这是独立迁移项目，并非官方主题。基于固定上游提交，不承诺与最新版或增强版完全一致。

## 功能

- 多行首页、社交链接、最近文稿与手记、年度时间线。
- 胶囊导航、亮暗主题、移动导航、原生切页效果。
- 文稿与手记布局、目录、阅读进度、沉浸阅读、图片放大、分享及手记字形设置。
- Pagefind 静态搜索，配套移动端毛玻璃搜索面板。
- Markdown、KaTeX、代码高亮、脚注、提示容器、图库和部分 Shiro 扩展语法。
- 独立季节 Canvas 背景、RSS、Sitemap、GitHub Actions。

账户、后台管理、实时互动及评论服务不在迁移范围，详见[迁移说明](docs/MIGRATION.md)。

## 快速开始

需要 Node.js 22.12+，推荐 Node.js 24。

```sh
git clone https://github.com/EthanZer0/Shiro-For-Astro.git
cd Shiro-For-Astro
npm ci
npm run dev
```

默认开发地址为 http://localhost:4321/ 。搜索索引在构建时生成，完整搜索请运行：

```sh
npm run check
npm run build
npm run verify
npm run preview
```

## 配置与写作

| 文件 | 用途 |
| --- | --- |
| src/site.config.ts | 站点、作者、首页模板、头像、社交、导航与背景 |
| src/content/posts/ | Markdown 文稿 |
| src/content/notes/ | Markdown 手记 |
| src/pages/about.astro | 关于页面 |
| public/ | 图片及静态资源 |

默认使用通用作者名和 SVG 头像，请替换为自己的资料。首页大字由 hero.title.template 依次组合，br 换行，code 支持角色介绍；hero.description 是小字介绍。

文章元数据示例：

```yaml
---
title: 我的第一篇文章
description: 文章摘要
published: 2026-10-09T10:00:00+08:00
slug: my-first-post
category: 随笔
categorySlug: essays
tags: [生活]
draft: false
pin: false
---
```

文稿地址为 `/posts/<categorySlug>/<slug>/`；手记可设置唯一正整数 nid，使用 `/notes/<nid>/`，否则使用 slug。公开源码仓库中的草稿文件仍然公开；示例草稿仅验证隔离行为。

background 支持 auto、spring、summer、autumn、winter 和 none。自动模式按访客本地月份选择：2–5 月春季、6–8 月夏季、9–11 月秋季、12–1 月冬季。手机、正文阅读页、打印以及减少动态偏好下隐藏背景。

## 部署

支持 GitHub Pages 项目子路径和自定义域名，见[部署指南](docs/DEPLOYMENT.md)。默认 CI 仅检查和构建，部署工作流手动触发。

## 来源与许可

原作者：[Innei](https://github.com/Innei)，上游：[Innei/Shiro](https://github.com/Innei/Shiro)，固定提交 `891bb24cd59aff7c9baaf4d9a3579ca4275da3b7`。

保留上游 [AGPLv3](LICENSE) 及[附加商业使用条款](ADDITIONAL_TERMS.md)。请一并阅读；商业使用须按上游附加条款取得授权，本项目不另行放宽上游授权。来源和第三方资源见[来源说明](docs/SOURCES.md)。

欢迎提交 Issues 和 Pull Requests，见[贡献指南](CONTRIBUTING.md)。
