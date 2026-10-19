# 初星晨報｜Starry Dawn Morning Post

獨立網站；不修改技能交換公會或其素材。

## 這個檔案包做了什麼

以已確認的標題統一修正版為準，僅補齊部署及維護材料。
網頁body、CSS與JavaScript與原先已上傳的首頁一致，沒有重新設計。
新增日期存檔與分享中繼資料，兩篇標題、作者、按鈕及原href都保留。
整理時GitHub自動寫入回傳403，因此本包尚未由助手補傳。

## 上傳方法

1. 解壓縮本ZIP；看到 `index.html` 的這一層就是儲存庫根目錄。
2. 在 `hannahchen6134/Starry-Dawn-Morning-Post` 選 Add file → Upload files。
3. 上傳這一層的檔案與資料夾內容，保留原本資料夾結構。不要把ZIP檔直接上傳，也不要在外面多包一層「星晨報」。
4. Commit changes 到目前的 main；目前Pages已成功發布過，不需另建新網站。
5. 到 Actions 確認新的 pages build and deployment 成功，再檢查網站及分享圖。

## 哪些是網站檔、哪些是維護檔

- `index.html`：首頁。背景、CSS與JavaScript已內嵌；中文字型透過Google Fonts載入，不附字型檔。
- `2026-10-17/index.html`：本期固定頁面。新的日期不要覆蓋舊一期。
- `2026-10-17/cover.png`：1080×1350，已確認網站的真實4:5截圖，供LINE／IG手動附圖。
- `2026-10-17/og-preview.png`：1200×630，供網址的預覽中繼資料引用；不保證每個平台立即更新快取。
- `2026-10-17/LINE文字.txt`：上傳完成、驗證本期網址後可使用的文字。
- `.nojekyll`：純靜態檔案部署設定。
- `SKILL.md`、`issues/`：每次給AI更新時的規範與真實稿件資料。
- `assets/`：五張背景與固定版型來源。當前首頁已內嵌背景，因此沒有它們仍可顯示；每日換稿／換背景的生成工具會需要它們。
- `tools/`：在本機執行的製作工具；GitHub Pages不會因為上傳Python檔而自動執行。

## 網址

首頁：https://hannahchen6134.github.io/Starry-Dawn-Morning-Post/
本期：https://hannahchen6134.github.io/Starry-Dawn-Morning-Post/2026-10-17/
本期手動分享圖：https://hannahchen6134.github.io/Starry-Dawn-Morning-Post/2026-10-17/cover.png
本期網址預覽圖：https://hannahchen6134.github.io/Starry-Dawn-Morning-Post/2026-10-17/og-preview.png

本期日期頁和圖片只有在這次補檔成功後才會存在，不要提前對外分享尚未上傳的路徑。

## 每日更新

讀SKILL並準備2–3則已確認稿件，更新 `issues/YYYY-MM-DD.json`。
`draft` 與 `searchIndex` 分開控制；目前保留不收錄，不擅自改成可索引。

```sh
python tools/build.py issues/YYYY-MM-DD.json
python tools/render.py YYYY-MM-DD --web-fonts
python tools/check_deployment.py
```

同日期有意修訂才加 `--replace`；先保留本機備份。渲染需要Python套件playwright與Chromium；不附字型檔。
更新後才上傳首頁、新的日期資料夾與當日JSON／新增來源素材。
智堯原文未提供，本期只保留使用者指定的LINE入口，不新增原文或轉載聲明。

## 隱私

此儲存庫為公開。不要上傳未取得公開許可的子社群原文、私人備註、.env、密碼或API金鑰。
noindex不是權限或隱私保護。
