# 匿名互動功能說明

本功能用於「校園性別事件處理實務」研習現場互動。

## 檔案角色

- `index.html`：講者投影主簡報
- `audience.html`：聽眾手機匿名互動頁
- `dashboard.html`：講者端即時統計與留言檢視頁
- `config.js`：正式設定檔，內含 GAS Web App URL
- `config.example.js`：設定範本
- `gas.gs`：Google Apps Script 後端程式，本機備份用
- Google Sheets：儲存匿名互動資料

## 隱私設計

本功能不要求登入，不蒐集姓名、email、IP，也不要求聽眾輸入個人資料。

留言區提醒聽眾不得輸入：

- 學生姓名
- 班級座號
- 學校真實個案細節
- 可識別當事人的資訊
- 未公開調查內容

留言最多 50 字。

## Google Sheets 與 GAS 設定

1. 建立一份 Google Sheets。
2. 開啟「擴充功能」→「Apps Script」。
3. 將 `gas.gs` 內容貼入 Apps Script。
4. 儲存專案。
5. 部署為 Web App。
6. 執行身分選擇「我」。
7. 存取權限選擇「任何人」。
8. 複製 Web App URL。

## 前端設定

1. 將 `config.example.js` 複製成 `config.js`。
2. 將 `GAS_ENDPOINT` 改成你的 GAS Web App URL。
3. 確認 `SESSION_ID` 是本次研習專用名稱，例如：

```javascript
SESSION_ID: "gender-seminar-2026-0520"