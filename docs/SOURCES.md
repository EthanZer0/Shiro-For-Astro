# 来源与适配

上游作者 Innei，仓库 https://github.com/Innei/Shiro，固定提交 `891bb24cd59aff7c9baaf4d9a3579ca4275da3b7`。

src/styles/upstream/、src/components/upstream/、部分图标、结构及动画参数来自公开 Shiro，保留 LICENSE 和 ADDITIONAL_TERMS.md。public/avatar.png 与 favicon.ico 是上游公开占位资源。未使用私有赞助版代码或上游作者个人文章。

Astro 路由、Markdown 静态适配、Pagefind 集成、季节背景和示例文章为本项目适配或编写。public/avatar.svg 为通用占位头像，发布包不含个人头像。

背景视觉及月份选择参考 https://www.xiaohanwu.com/，使用 Canvas 2D 自行绘制银杏、樱花、雪花和粒子，不包含参考站增强版组件或 shader。搜索卡片及夏冬部分粒子效果为本项目定制。

字体通过 @fontsource 或按需 CDN 加载；Manrope 与 Noto Serif SC 许可副本位于 public/licenses/，外部字体地址见手记字体组件。第三方依赖适用各自许可证。

## 可选上游对照

构建不依赖 .research。审计或重新生成图标时，在仓库根目录执行：

```sh
git clone https://github.com/Innei/Shiro.git .research/Shiro
git -C .research/Shiro checkout 891bb24cd59aff7c9baaf4d9a3579ca4275da3b7
npm run audit:source
```

scripts/sync-code-icons.mjs 同样依赖该固定源码；.research 被 gitignore 排除。
