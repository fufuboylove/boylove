# 香香腐宅 防走失頁

單一檔案 `index.html`（內嵌 CSS／JS，無外部資源），直接上傳即可使用。

## 修改網域
打開 `index.html`，找到 `<script>` 最上方的設定區：
- `PERMANENT`：永久網域，格式 `{ name: "香香腐宅永久網域", domain: "boylove.cc" }`；卡片只顯示 name
- `MIRRORS`：大陸免翻牆線路，格式 `{ name: "線路1", domain: "網域" }`，一行一個；卡片只顯示 name，不顯示網域
- 聯絡方式區塊預設隱藏，見 HTML 中「聯絡方式」註解說明

## 部署方式
> 建議：防走失頁應放在**與主站不同的獨立網域**上，主站網域被封時才不會一起失效。

### 1. Cloudflare Pages / Workers（推薦）
- 後台：Workers & Pages → 建立 → Pages → 「直接上傳」，拖入本資料夾即可。
- 或用指令：`npx wrangler pages deploy . --project-name boylove-fanglost`
- 部署後於「自訂網域」綁定一個獨立網域。

### 2. GitHub Pages
- 新建公開倉庫，上傳 `index.html`。
- Settings → Pages → Source 選 `main` 分支根目錄，儲存。
- 可在同頁設定自訂網域（Custom domain）。

### 3. 任意靜態主機
- 將 `index.html` 上傳到任何虛擬主機、物件儲存（如 S3、R2）或 Nginx 網站根目錄即可，無需後端。

## 注意
- 測速是在訪客瀏覽器中請求各網域的 `/favicon.ico`，結果僅供參考；若某網域沒有 favicon，可修改 `PROBE_PATH`。
- `preview-*.png` 為預覽截圖，部署時可不上傳。
