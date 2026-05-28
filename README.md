# 校園性別事件處理實務｜HTML 簡報包

這個資料夾是一份可離線開啟、也可部署到 GitHub Pages 的靜態 HTML 簡報包。內容包含講者投影用主簡報與聽眾手機互動頁，所有程式與圖片都放在本資料夾內，不需要外部 CDN。

## 檔案用途

- `index.html`：講者投影主簡報。這是正式簡報入口，建議投影或分享 GitHub Pages 首頁時使用。
- `audience.html`：聽眾手機互動頁。可讓聽眾在手機上顯示 A/B/C/D、三色卡、是／否卡與一句話備忘，不會送出或蒐集資料。
- `assets/slides/`：主簡報使用的圖片素材資料夾。部署時必須保留這個相對路徑。
- `speaker_flow_outline.md`：講者流程備忘。

## 離線開啟

直接用瀏覽器開啟 `index.html` 或 `audience.html` 即可。請保留整個資料夾結構，不要只移動單一 HTML 檔，否則圖片相對路徑可能失效。

## 主簡報操作

開啟 `index.html` 後可使用鍵盤操作：

- `→` / `Space`：下一頁
- `←`：上一頁
- `N`：顯示／隱藏講者備忘
- `F`：全螢幕
- `G`：總覽模式
- `P`：列印或另存 PDF

## 聽眾互動頁操作

在手機瀏覽器開啟 `audience.html`。簡報進行到互動橋段時，聽眾可依現場指示切換或顯示：

- A/B/C/D 選項卡
- 三色卡
- 是／否卡
- 一句話備忘

`audience.html` 是純前端靜態頁，不需要登入，也不會傳送資料。

## GitHub Pages 部署方式

1. 將整個資料夾內容放到 GitHub repository。
2. 確認 repository 根目錄包含 `index.html`、`audience.html`、`assets/slides/`、`.nojekyll`。
3. 在 GitHub repository 的 Settings → Pages 中選擇部署來源。
4. 部署完成後，以 GitHub Pages 網址開啟：
   - 主簡報：repository 的 GitHub Pages 根網址。
   - 聽眾互動頁：在 GitHub Pages 根網址後加上 `audience.html`。

正式推送前請參考 `deploy_checklist.md`。
