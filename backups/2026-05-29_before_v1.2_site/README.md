# 校園性別事件處理與防制：90 分鐘研習簡報

這個專案是可部署到 GitHub Pages 的 HTML 簡報，主題為「校園性別事件處理與防制」。目前版本先完成前 12 頁樣張，用來確認整體風格、版型與主視覺使用方式；確認後再展開完整 42 頁研習版。

## 目前輸出

- `index.html`：講者投影主簡報，可部署到 GitHub Pages，也可本機離線開啟。
- `audience.html`：聽眾手機互動頁，保留作為手機填答入口。
- `dashboard.html`：結果頁，供講者或工作人員查看互動結果。
- `dist/deck.pptx`：可編輯的 PowerPoint 簡報。
- `dist/preview.pdf`：12 頁樣張預覽 PDF。
- `dist/png_preview/`：每頁 PNG 預覽圖。

## 視覺素材

主視覺圖片放在 `assets/visuals/`，檔名已對應簡報用途：

- `01_cover_phone_corridor.png`：封面
- `02_opening_quote_wall.png`：開場金句
- `03_interaction_desktop.png`：手機互動頁背景
- `04_section_event_map.png`：事件辨識章節轉場
- `05_section_first_response.png`：第一時間章節轉場
- `06_quote_reporting_not_judgment.png`：通報金句
- `07_section_recording_risk.png`：通報與紀錄章節轉場
- `08_section_people_pressure.png`：人際壓力章節轉場
- `09_case_digital_spread.png`：數位擴散案例
- `10_closing_system_support.png`：收束頁

請不要直接修改這些原圖，也不要把中文文字合成到圖片裡。簡報標題、頁碼、流程圖、QR Code 與所有中文內容都應維持為 HTML / PPTX 可編輯文字。

## 新增或調整頁面

頁面資料集中在 `tools/build_deck.mjs` 的 `slides` 陣列。新增頁面時，請複製既有物件並調整：

- `type`：版型類型，例如 `cinematic_cover`、`quote_wall`、`interaction_card`、`section_transition`、`tool_cards`、`process_flow`、`case_breakdown`。
- `section`：章節標籤。
- `title`、`subtitle`、`cards`、`steps` 等：頁面可編輯文字。
- `image`：要使用的 `assets/visuals/` 圖片路徑。

新增主視覺頁時，優先用半透明遮罩或文字底卡處理可讀性，不要降低整張圖片透明度。

## 替換圖片

若要替換主視覺，請把新圖放入 `assets/visuals/`，並盡量沿用原檔名。替換後執行重建指令即可同步更新 HTML、PPTX、PDF 與 PNG 預覽。

圖片規則：

- 不使用外部圖片。
- 不使用外部 CDN。
- 不把中文文字燒進圖片。
- 圖片與文字對比不足時，使用深藍半透明遮罩或米白文字卡。

## 重建簡報

在本機或另一台電腦的 Codex 工作環境中，先確認已進入專案資料夾，接著執行：

```powershell
& '<Node.js 執行檔路徑>' tools\build_deck.mjs
& '<Python 執行檔路徑>' -X utf8 tools\pngs_to_pdf.py dist\png_preview dist\preview.pdf
```

如果在另一台電腦，Codex 的 runtime 路徑可能不同；可先讓 Codex 讀取工作區相依環境，再用回傳的 Node.js 與 Python 路徑執行同樣兩個腳本。

## 部署到 GitHub Pages

確認完整 42 頁完成並檢查無誤後，再 commit 並 push 到 GitHub。GitHub Pages 入口通常為：

- 主簡報：`https://smallcannon-arch.github.io/Gender-related-incident-prevention-workshop/`
- 手機互動頁：`https://smallcannon-arch.github.io/Gender-related-incident-prevention-workshop/audience.html`
- 結果頁：`https://smallcannon-arch.github.io/Gender-related-incident-prevention-workshop/dashboard.html`

目前 12 頁樣張尚未推送，請先確認風格後再部署。
