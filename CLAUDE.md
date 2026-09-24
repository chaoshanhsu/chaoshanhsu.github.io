# chaoshan-site — Hugo 學術個人網站

這是 Chao-Shan Hsu 的學術個人網站，用 Hugo + PaperMod 主題建置，部署在 GitHub Pages（https://chaoshanhsu.github.io），透過 GitHub Actions 自動部署（`.github/workflows/hugo.yml`）。

## 工作流程

每次我編輯完 `content/` 或 `static/` 裡的檔案後，如果我說「推送」、「push」、「幫我上傳」、「commit 一下」之類的話，請自動執行：

1. `git status` 確認改了哪些檔案
2. `git add .`
3. `git commit -m "..."` — commit message 請根據實際改動內容自己判斷寫一句簡短英文說明（例如 "add JAAC paper", "update profile picture", "fix Estetika paper date"）
4. `git push`

如果 push 要求輸入帳號密碼，停下來告訴我，讓我自己手動輸入 personal access token，不要嘗試自己猜測或處理憑證。

## 常見任務

- **新增一篇論文**：複製 `content/papers/` 裡任一篇現有的 `.md` 檔，改檔名為下一個號碼（例如 `6.md`），更新 `title`、`date`、`url`（改成對應的 `/6/`）、摘要（`description` 和 `summary`）、`editPost`（期刊或狀態連結）、內文的 Abstract 和 Citation 區塊。
- **更新論文狀態**（例如從 under review 變成 accepted）：找到對應的 `content/papers/X.md`，更新 `date`、`editPost`、summary 裡的狀態文字，以及內文的 Citation。
- **新增會議發表**：同樣的邏輯用在 `content/talks/` 資料夾。
- **換照片或 CV**：檔案直接放進 `static/` 資料夾，檔名維持 `picture.jpg` 和 `cv.pdf` 不變。
- **改自我介紹文字**：在 `config.yml` 裡找 `subtitle:` 那一行。

## 部署後確認

推送完成後，可以到 https://github.com/chaoshanhsu/chaoshanhsu.github.io/actions 確認 workflow 是否成功（綠色打勾），網站約 1-2 分鐘後會在 https://chaoshanhsu.github.io 更新。
