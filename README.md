# gary-tour-test

福岡 5 天 4 夜（3/9–3/13）行程網站，部署在 GitHub Pages。

**線上網址：<https://kkdaygary.github.io/gary-tour-test/>**

## 內容

以福岡為基地的五天行程：博多屋台、太宰府・柳川、由布院溫泉、別府地獄、天神採買。
頁面包含：為什麼選福岡、3 月上旬限定看點、逐日行程、必吃清單、美食名店、
必玩景點、伴手禮與實用提醒。

## 檔案結構

```
site/
├── index.html          頁面骨架與渲染邏輯
└── assets/
    ├── style.css       樣式（支援深淺色）
    ├── data.js         行程主內容（日程、必吃、必玩、提醒）
    ├── extra.js        補充內容（howto、喝什麼、伴手禮、季節限定、最新情報）
    └── credits.js      照片版權資訊（Wikimedia Commons）
```

要改文字內容只需要動 `site/assets/data.js` 與 `site/assets/extra.js`。

## 本機預覽

```bash
cd site && python3 -m http.server 8899
# 開 http://127.0.0.1:8899/
```

## 部署

採 **Deploy from a branch**：`gh-pages` 分支根目錄的內容就是線上內容。

```bash
git checkout gh-pages
git checkout main -- site && cp -r site/. . && rm -rf site
git add -A && git commit -m "Update site" && git push origin gh-pages
```

推送後 GitHub 會自動跑 `pages build and deployment`，約 1 分鐘生效。

> 註：這個 repo 原本是用來測試 GitHub Pages 部署。改用 `gh-pages` 分支而非
> GitHub Actions，是因為 Actions 的內建 token 無法自動建立 Pages 站台
> （`Create Pages site failed: Resource not accessible by integration`）。
