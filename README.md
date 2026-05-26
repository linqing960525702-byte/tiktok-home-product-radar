# TikTok 欧区家居百货选品雷达

这是一个静态选品分析网站，适合部署到 Cloudflare Pages。

## 本地预览

直接用浏览器打开：

```text
index.html
```

## Cloudflare Pages 部署建议

推荐使用 GitHub 仓库连接 Cloudflare Pages：

1. 新建 GitHub 仓库，例如 `tiktok-home-product-radar`。
2. 上传本目录所有文件，至少包括：
   - `index.html`
   - `README.md`
   - `wrangler.toml`
3. 打开 Cloudflare Dashboard。
4. 进入 `Workers & Pages`。
5. 选择 `Create application` -> `Pages` -> `Connect to Git`。
6. 选择仓库。
7. 构建设置：
   - Framework preset: `None`
   - Build command: 留空
   - Build output directory: `/`
8. 部署后会得到 `*.pages.dev` 公开网址。

## GitHub 网页上传方式

如果本机没有安装 Git，可以用 GitHub 网页上传：

1. 打开 <https://github.com/new>。
2. Repository name 填 `tiktok-home-product-radar`。
3. 选择 `Public` 或 `Private`。
4. 创建仓库。
5. 点击 `uploading an existing file`。
6. 上传 `github-upload.zip` 解压后的文件，或直接上传本目录里的 `index.html`、`README.md`、`wrangler.toml`。
7. 点击 `Commit changes`。

## 后续自动更新方案

当前 Codex 自动任务可以每天更新本地文件。要让公网网站也自动更新，建议改成：

1. 每日任务更新产品和资讯数据。
2. 自动提交到 GitHub。
3. Cloudflare Pages 监听 GitHub commit 后自动重新部署。

## 文件说明

- `index.html`：网站入口，Cloudflare Pages 使用这个文件。
- `tiktok-home-product-dashboard.html`：本地备份版本。
- `wrangler.toml`：Cloudflare 项目配置参考。
