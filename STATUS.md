# SWING LAB 專案狀態

## 專案簡介
爵士鼓節奏練習 Web App（PWA），支援四聲部（Ride/HH/Snare/Kick）、三連音網格、12 種內建節奏型、學生跨裝置紀錄同步。

## 當前狀態
✅ **已上線** — GitHub Pages 部署完成
🟡 **等待 DNS 生效** — Cloudflare CNAME 需手動設定
⏸️ **Firebase 未啟用** — 雲端同步功能未設定，目前只存本機

## 已完成
- [x] GitHub repo 建立：https://github.com/589411/swing-lab
- [x] GitHub Pages 啟用（main branch / root）
- [x] CNAME 檔案已存在並被 Pages 識別（swing.launchdock.app）
- [x] Pages 建置完成（status: built）

## 卡點
**等待手動操作**：Cloudflare DNS 設定
- 到 `launchdock.app` zone 新增 CNAME：
  - 名稱：`swing`
  - 目標：`589411.github.io`
  - Proxy 狀態：**DNS only（灰雲）**
- DNS 生效後才能訪問 https://swing.launchdock.app

## 下一個具體動作
1. **立即**：手動設定 Cloudflare DNS（上述 CNAME）
2. **DNS 生效後**（1-5 分鐘）：執行 `gh api repos/589411/swing-lab/pages -X PUT -f https_enforced=true` 啟用強制 HTTPS
3. **可選**：設定 Firebase 雲端同步（需 Firebase 專案資訊，參考 DEPLOY.md §5）

## 技術棧
- 單檔 HTML（index.html）+ PWA（manifest + sw.js）
- Firebase Firestore（可選，跨裝置同步）
- GitHub Pages + Cloudflare DNS

## 重要連結
- Repo：https://github.com/589411/swing-lab
- 目標網址：https://swing.launchdock.app（DNS 生效後）
- Pages 暫存：https://589411.github.io/swing-lab/（會自動 301 到自訂網域）

## 最後更新
2026-07-12 — 完成 GitHub Pages 部署，等待 DNS 設定
