# gary-tour-test

日本六個候選地點的 5 天 4 夜行程網站，部署在 GitHub Pages。

**線上網址：<https://kkdaygary.github.io/gary-tour-test/>**

## 內容

大阪、福岡、仙台、神戶、茨城、札幌，每個地點都有：特色、5 天 4 夜逐日行程、
必吃清單、必玩景點、實用提醒。首頁的總覽有六地比較表與選擇建議。

## 檔案結構

```
site/
├── index.html          頁面骨架與渲染邏輯
└── assets/
    ├── style.css       樣式（支援深淺色）
    └── data.js         所有地點內容都在這裡
```

要改文字內容只需要動 `site/assets/data.js`；要新增地點就往 `DESTINATIONS`
陣列加一筆，並在 `OVERVIEW` 補上比較表資料，頁籤會自動生成。

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
