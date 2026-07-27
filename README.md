# gary-tour-test

GitHub Pages 靜態 HTML 部署測試專案。

- 線上網址：<https://kkdaygary.github.io/gary-tour-test/>
- 部署方式：**Deploy from a branch** — 推送到 `gh-pages` 分支的內容會自動發佈
- 頁面原始碼：`main` 分支的 [`site/index.html`](site/index.html)（發佈時複製到 `gh-pages` 分支根目錄）

## 更新頁面

```bash
# 修改 site/index.html 後
git checkout gh-pages
cp site/index.html index.html   # 或直接編輯 gh-pages 上的 index.html
git commit -am "Update page"
git push origin gh-pages
```

推送後約 1 分鐘內生效。
