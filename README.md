# 香香腐宅 防走失页

`index.html`（内嵌 CSS／JS，无外部 CDN）+ 两张背景图 `bg-mobile.jpg`、`bg-desktop.jpg`，三个文件放同一目录上传即可使用。

## 修改网域
打开 `index.html`，找到 `<script>` 最上方的设置区：
- `PERMANENT`：永久网域，格式 `{ name: "香香腐宅永久网域", domain: "boylove.cc" }`；卡片只显示 name
- `MIRRORS`：大陆免翻墙线路，格式 `{ name: "线路1", domain: "网域" }`，一行一个；卡片只显示 name，不显示网域
- 联系方式区块默认隐藏，见 HTML 中“联系方式”注释说明

## 部署方式
> 建议：防走失页应放在**与主站不同的独立网域**上，主站网域被封时才不会一起失效。

### 1. Cloudflare Pages / Workers（推荐）
- 后台：Workers & Pages → 创建 → Pages → “直接上传”，拖入本文件夹即可。
- 或用命令：`npx wrangler pages deploy . --project-name boylove-fanglost`
- 部署后于“自定义域”绑定一个独立网域。

### 2. GitHub Pages
- 新建公开仓库，上传 `index.html` 及两张背景图。
- Settings → Pages → Source 选 `main` 分支根目录，保存。
- 可在同页设置自定义域名（Custom domain）。

### 3. 任意静态主机
- 将 `index.html` 及背景图上传到任何虚拟主机、对象存储（如 S3、R2）或 Nginx 网站根目录即可，无需后端。

## 注意
- 测速是在访客浏览器中请求各网域的 `/favicon.ico`，结果仅供参考；若某网域没有 favicon，可修改 `PROBE_PATH`。
- `preview-*.png` 为预览截图，部署时可不上传；`bg-mobile.jpg`、`bg-desktop.jpg` 为背景图，需与 `index.html` 放在同一目录。
