# 部署指南

## GitHub Pages

1. Fork 仓库或复制到自己的仓库，修改个人资料及示例内容。
2. Settings → Pages → Source 选择 GitHub Actions。
3. Actions 中选择 Deploy Astro to GitHub Pages，点击 Run workflow。

工作流仅手动部署；需要推送自动发布时，在 deploy.yml 的 on 下添加 `push: { branches: [main] }`。

工作流自动适配用户名根站点和 `/仓库名/` 项目路径。自定义域名时，在 Actions Variables 设置 `SITE_URL=https://blog.example.com` 和 `BASE_PATH=/`，然后在 Pages 配置域名、DNS 和 HTTPS。

## 其他静态托管

构建命令 `npm ci && npm run build`，输出目录 `dist`。通过构建环境设置 SITE_URL 和 BASE_PATH；配置读取进程环境变量，不自动读取 .env，.env.example 仅供参考。

本地默认构建地址为 https://example.com，发布前请提供实际地址，保证 canonical、RSS 和 Sitemap 正确。

PowerShell 项目路径示例：

```powershell
$env:SITE_URL = 'https://your-name.github.io'
$env:BASE_PATH = '/your-repository'
npm run build
npm run verify
npm run preview
```
