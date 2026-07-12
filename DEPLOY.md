# SWING LAB 部署交接（給 Claude Code）

目標：把本資料夾部署到 GitHub Pages，綁定 `swing.launchdock.app`（Cloudflare DNS）。
git repo 已初始化並 commit 完成，剩下步驟如下。

## 1. 建 GitHub repo 並推送

```bash
cd ~/github/swing-lab
gh repo create 589411/swing-lab --public --source=. --push
# 若 gh 不可用：在 GitHub 網頁建 589411/swing-lab 後
# git remote add origin git@github.com:589411/swing-lab.git && git push -u origin main
```

## 2. 開啟 GitHub Pages

repo → Settings → Pages → Source「Deploy from a branch」→ `main` / `(root)`。
（根目錄已有 `CNAME` 檔，內容 `swing.launchdock.app`，Pages 會自動認得。）

## 3. Cloudflare DNS

launchdock.app zone 新增 CNAME：

- 名稱：`swing`
- 目標：`589411.github.io`
- Proxy 狀態：**DNS only（灰雲）**——重要！橘雲會跟 GitHub SSL 憑證打架。

## 4. 等 SSL 簽好後

repo → Settings → Pages → 勾 **Enforce HTTPS**。

## 已知踩坑（來自 static-site-deploy skill）

- push 被拒「fetch first」：多半是 Pages UI 自動 commit 了 CNAME。
  `git pull --rebase origin main`，CNAME 衝突就
  `printf 'swing.launchdock.app\n' > CNAME && git add CNAME && git rebase --continue`。
- git lock 卡住：`rm -f .git/HEAD.lock .git/index.lock`。

## 檔案結構

- `index.html` — 主程式（單檔，含手機版面 + PWA 註冊）
- `swing-lab.html` — 舊檔名副本（與 index.html 相同，可刪）
- `manifest.webmanifest` / `sw.js`（network-first）/ `icons/` — PWA
- `CNAME` — 自訂網域

## 上線後驗證

1. 手機 Safari/Chrome 開 https://swing.launchdock.app
2. iPhone：分享鈕 ⬆️ → 加入主畫面（LINE 內建瀏覽器沒有此選項，要先「用 Safari 開啟」）
3. 開飛航模式重開 App，確認離線可載入
4. 之後改版：更新 `sw.js` 裡的 `CACHE` 版本字串（v1→v2）
