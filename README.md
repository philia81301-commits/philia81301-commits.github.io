# 潘湘如醫師｜臨床工具集（個人入口網站）

網址：**https://philia81301-commits.github.io/**

純靜態網站，放在 GitHub Pages 上，零費用。各工具留在自己的 repo，
這裡只是入口：一張卡片＝一個工具（名稱＋一句話簡介＋連結＋QR code）。

## 檔案結構

```
index.html            首頁（三區：門診臨床工具／社區篩檢／教學與演講）
ai-teaching/          AI 教學介紹頁＋教材檔＋線上閱讀版（guide.html／manual.html）
qr/                   QR 總表（A4 可列印，張貼診間／演講會場用）
404.html              找不到頁面（品牌風格）
assets/qr/            預先產生的 QR code SVG
assets/               hero 底圖、玫瑰浮水印、OG 分享圖、favicon
rdq/                  需求規格卡（.gitignore 排除，不上傳）
```
加新工具時記得：首頁加卡片＋ `qr/index.html` 加一格。

## 之後怎麼加新工具

1. **確認新工具已有公開網址**（該 repo 開好 GitHub Pages）。
2. **產生 QR code**：在本資料夾執行（把網址和檔名換掉）：
   ```
   python -c "import qrcode, qrcode.image.svg; qrcode.make('https://工具網址/', image_factory=qrcode.image.svg.SvgPathImage, box_size=10, border=2).save('assets/qr/新工具.svg')"
   ```
3. **在 `index.html` 加一張卡片**：複製任一段 `<a class="card">…</a>`，
   改標題、簡介、連結、QR 圖檔名。放進對的分區（門診臨床工具／社區篩檢／教學與演講）。
4. **上架前檢查**：新工具頁面不得含病人資料或院內內部資訊；
   會收資料進 Google 試算表的工具，卡片要加 `<span class="badge">臨床使用工具…</span>` 標註。
5. **推上線**：
   ```
   git add -A
   git commit -m "新增工具：〇〇"
   git push
   ```
   推完約 1–2 分鐘後網站自動更新。

## 固定原則（來自需求規格）

- 署名「潘湘如醫師｜家醫科」，**不放服務單位**。
- 不上架：soapime、kaizhilin-hair、jianba。
- 不買自訂網域、不做英文版、不加流量統計。
- agent-roadshow 是 private repo：AI 教學教材由本 repo 的 `ai-teaching/files/` 代管，
  只放通用版（單位客製版簡報不公開）。教材更新時從 `C:\projects\agent-roadshow` 重新複製過來。
