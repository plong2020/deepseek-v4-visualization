# DeepSeek-V4 作者可视化 - 部署指南

## 方案一：GitHub Pages（推荐，免费稳定）

1. 登录 GitHub，创建新仓库，例如 `deepseek-v4-visualization`
2. 将本目录下所有文件上传到仓库根目录
3. 进入仓库 Settings → Pages → Source 选择 Deploy from a branch
4. Branch 选择 `main`，folder 选择 `/(root)`，点击 Save
5. 等待 1-2 分钟，访问 `https://你的用户名.github.io/deepseek-v4-visualization/`

## 方案二：Cloudflare Pages（国内访问友好）

1. 登录 [Cloudflare Dashboard](https://dash.cloudflare.com)
2. 进入 Pages → Create a project → Upload assets
3. 将本目录压缩为 zip 上传
4. 等待部署完成，获得 `*.pages.dev` 域名

## 方案三：Vercel（部署最简单）

1. 登录 [Vercel](https://vercel.com)
2. 点击 Add New Project → Import Git Repository
3. 选择本仓库导入，Framework Preset 选 `Other`
4. 点击 Deploy，即刻获得访问链接

## 文件说明

| 文件 | 说明 |
|------|------|
| `index.html` | 主页面（可视化文章） |

## 临时访问

如需临时预览，可使用 Cloudflare Tunnel：

```bash
cd deploy
python3 -m http.server 8080 &
npx cloudflared tunnel --url http://localhost:8080
```
