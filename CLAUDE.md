# 給在這個專案工作的 AI 助手

**Haidian Hidden Library 電視牆**（tv.twranger.com）：圖書室那台 LG 電視輪播的圖片與影片。沒有人會去點它，是遠遠看的。

**動手前先讀完下面這份共用規範**（twranger 全部網站都遵守同一份）：

@WEB-STANDARDS.md

這個專案沒有 `DESIGN.md`。它是電視輪播，共用規範裡「互動」那一節（按鈕、點擊範圍、鍵盤）大多用不到；要顧的是：**字要大到三公尺外看得清楚、對比要夠、動畫要平順、長時間開著不能越跑越慢**。

## 這個專案怎麼運作

- 只有一個 `index.html`，沒有建置步驟；圖片與影片在 `images/`。部署在 GitHub Pages（`CNAME`）。
- **電視是 LG webOS 4（瀏覽器約 Chromium 53）**：不能用新的 JavaScript 或 CSS 語法；影片在同一頁只能成功播一次，所以播完會整頁重新整理。動手前先讀 `TV-DEBUG-NOTES.md`，裡面有試過失敗的做法，不要重試。
- 影片的 `.frames` 由 `.github/workflows/frames.yml` 用 `tools/make-frames.sh` 產生，不要手動改。
- 影片網址用 `tv.twranger.com`，不要用 `github.io`。
- 改完在電腦上測（網址加 `#reload`、`#debug`），但**電腦上正常不代表電視上正常**，回報時要說清楚沒有在實機驗證。

## 上線基本功還缺的（2026-11-26 用 Impeccable 4.11.1 檢查，尚未逐項人工確認）

README、減少動態效果的設定、顏色還沒定義成變數。網站圖示、分享預覽圖、404 頁對電視牆不是必要。改到相關地方時順手補上。

## 和其他對話串協調

對話串之間不能直接傳訊息。做了會影響別人的決定就寫進這一頁；合併前先把 `origin/main` 併進自己的分支再測一次。
推到 `main` 就會直接上線（GitHub Pages），所以合併等於部署：要等使用者明確說「合併」。
