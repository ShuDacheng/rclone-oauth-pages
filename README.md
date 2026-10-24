# Personal Drive Backup

用于个人 rclone / restic Google Drive 备份流程的公开应用介绍、隐私政策和服务条款。维护者：[Dacheng Shu / ShuDacheng](https://github.com/ShuDacheng)。

## 发布目标与 Google Branding

部署到 GitHub Pages 并确认网址可访问后，将下面的值填写到 Google 控制台。

| Google OAuth Branding 字段 | 值 |
| --- | --- |
| App name（如采用本页名称） | `Personal Drive Backup` |
| Application home page | https://shudacheng.github.io/rclone-oauth-pages/ |
| Application privacy policy link | https://shudacheng.github.io/rclone-oauth-pages/privacy.html |
| Application terms of service link | https://shudacheng.github.io/rclone-oauth-pages/terms.html |
| Authorized domains | `shudacheng.github.io`（以 Google 控制台校验结果为准） |

User support email 和 Developer contact information 填写由账号所有者管理的邮箱。本仓库不公开或生成邮箱地址。Google 控制台的应用名称及数据用途应与实际配置和这些页面一致；如使用其他名称，先同步修改三页及本文件。

公开网页发布成功不代表 Google 审核或域名所有权验证已通过。若 Google 要求验证域名所有权，应按控制台提示在自己控制的站点添加验证材料；不要将其他人的域名填入授权域名。

## 发布方式

GitHub Pages 使用 `main` 分支根目录 `/`。`.nojekyll` 让静态 HTML/CSS/SVG 原样发布。修改文件后提交到 `main`，由 GitHub Pages 重新发布。站点没有构建依赖、JavaScript、登录表单、分析脚本或 Cookie。

## 文件

- `index.html`：应用用途、权限范围、维护者及政策入口。
- `privacy.html`：数据访问、用途、存储、保留、第三方、撤销授权及 Limited Use 声明。
- `terms.html`：使用范围、操作者责任、可用性和停止使用。
- `styles.css` / `favicon.svg`：本站本地样式与图标。

本仓库只保存公开网站内容。OAuth 客户端 JSON、rclone 配置、token、restic 密码、备份、任务数据库和私有项目文件保存在仓库之外。

## Google OAuth 后续配置

1. 在 Google Cloud 为自有项目启用 Google Drive API，并创建 Desktop app 类型的 OAuth 客户端。
2. 在 Branding 填写上述真实网址、支持邮箱和授权域名，保存；在 Audience 按个人用途配置发布状态。
3. 在私有配置中安装自有客户端，执行 rclone 重新授权，再验证能读取原有 Drive 目录和备份仓库。

Testing 可用于先行验证。请求 Drive 等非基本身份权限时，Testing 授权及 refresh token 通常于 7 天后过期；个人自用免正式验证与发布资料要求是两项不同的规则。

参考：[rclone 自有客户端指南](https://rclone.org/drive/#making-your-own-client-id)、[Google Audience](https://support.google.com/cloud/answer/15549945?hl=en)、[Google 个人用途豁免](https://support.google.com/cloud/answer/13464323?hl=en)。
