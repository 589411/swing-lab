# SWING LAB 專案狀態

## 專案簡介
爵士鼓節奏練習 Web App（PWA），支援八聲部完整鼓組（Crash/Ride/HH/Tom×3/Snare/Kick）+ 互動式 SVG 鼓組視覺化、三連音網格、12 種內建節奏型、學生跨裝置紀錄同步。

## 當前狀態
✅ **完全上線** — https://swing.launchdock.app 可正常訪問
✅ **SSL 已啟用** — 強制 HTTPS，憑證到期 2026-10-10
⏸️ **Firebase 未啟用** — 雲端同步功能未設定，目前只存本機

## 已完成
- [x] GitHub repo 建立：https://github.com/589411/swing-lab
- [x] GitHub Pages 啟用（main branch / root）
- [x] CNAME 檔案已存在並被 Pages 識別（swing.launchdock.app）
- [x] Pages 建置完成（status: built）
- [x] Cloudflare DNS 設定完成（swing.launchdock.app → 589411.github.io）
- [x] SSL 憑證簽發完成
- [x] 強制 HTTPS 已啟用
- [x] 網站正常訪問驗證通過
- [x] 擴充到 8 聲部鼓組（新增 Crash/Tom1/Tom2/Tom3）
- [x] SVG 互動式鼓組視覺化（點擊發聲 + 動畫）
- [x] WebAudio 合成音色（Tom 和 Crash 音色）

## 卡點
**無** — 功能開發與部署都已完成

## 下一個具體動作
**可選**：設定 Firebase 雲端同步（需 Firebase 專案資訊，參考 DEPLOY.md §5）
- 啟用後學生可用 6 碼同步碼跨裝置存取練習紀錄
- 未設定時自動降級為只存本機（目前狀態）

## 技術棧
- 單檔 HTML（index.html）+ PWA（manifest + sw.js）
- Firebase Firestore（可選，跨裝置同步）
- GitHub Pages + Cloudflare DNS

## 重要連結
- 線上網址：https://swing.launchdock.app
- GitHub repo：https://github.com/589411/swing-lab

## 最後更新
2026-07-12 — 新增 8 聲部鼓組 + SVG 視覺化介面，已部署上線
