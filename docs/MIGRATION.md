# 迁移范围与边界

固定公开 Shiro 的主要布局、原样式、图标、Spring 参数和阅读交互已适配到 Astro 静态内容及 React islands。包括首页、文稿列表、手记纸张布局、时间线、目录、字体、分享、图片查看、移动抽屉、标签云及主题切换。

支持 GFM、脚注、KaTeX、代码高亮、提示容器、gallery、Tabs、spoiler、tag、grid、masonry、carousel、静态 LinkCard 和视频。扩展字段见 src/content.config.ts。

Astro 切页前同步清理 Portal 和滚动锁，抽屉样式打包到全局 CSS，导航采用滚动条补偿。

## 明确差异

- Mix Space API 数据改为本地 Markdown 和构建时数据。
- 搜索采用 Pagefind，卡片为本项目定制的毛玻璃设计。
- 季节背景为独立 Canvas 2D 实现，无增强版代码。
- 部分文字色采用参考站 neutral-8 适配。
- 原切页效果适配 Astro，时长 500ms。
- 窄屏、键盘、安全区域和路由生命周期作必要适配。

没有迁移账户、后台、评论服务、在线统计、即时消息、任意 React 内容执行、Lexical 数据或增强版专有功能。不是最新上游的完整镜像，也未做全站逐像素一致性认证。

check 检查类型；build 生成页面和索引；verify 检查扩展渲染、资源、链接、草稿隔离和部署地址。真实手机交互及最终视觉效果仍需人工验收。
