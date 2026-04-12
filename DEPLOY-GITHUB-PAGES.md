# GitHub Pages + Discord Activity 部署說明

這份版本已做成 **Discord Activity 較安全的純靜態頁**：
- 不再依賴 `cdn.tailwindcss.com`
- 不再依賴 Google Fonts 外鏈
- 圖片已改為 ASCII 安全路徑
- 保留原本外部重要連結
- 補了手機 / Discord 內嵌安全區處理

## 1. 發佈到 GitHub Pages
最簡單做法：
1. 把這個資料夾內的內容放到你的 GitHub Pages 發佈來源
2. 確認 `index.html` 位於發佈根目錄
3. 確認頁面能直接從公開網址打開

## 2. 在 Discord Developer Portal 設定 Activity
根據 Discord 官方文件，Activity 需要設定 **URL Mappings**，因為 Activity 會跑在 Discord 的 sandbox / proxy 裡。

建議做法：
- 把你 GitHub Pages 的公開網址當成 Activity 的公開端點
- 如果你目前是 `username.github.io/repo-name/` 這種 **子路徑 Pages**，而 Discord URL Mapping 對 path 支援不理想，建議改成：
  - 自訂網域，或
  - 直接用 root Pages 站點作為 Activity 入口

## 3. 測試時優先檢查
- Activity 裡的圖片是否全部正常
- 首頁按鈕、Discord / X / Pixiv 外鏈是否正常
- 手機 Activity 裡首屏是否被頂部安全區擠壓
- 世界地圖四個節點是否都能正確點擊

## 4. 如果畫面還是不一致
那通常就不是這份靜態頁本身，而是：
- Discord URL Mapping 沒對到正確公開網址
- 你實際啟動的 Activity 仍指向舊版頁面
- GitHub Pages 還沒刷新到新版檔案
