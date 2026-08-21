# 個人工具入口網站（專案藍圖）

> 本檔為跨 Agent 通用的專案藍圖。任何 Agent 的每個 session 都應先讀本檔＋`handoff.md`。
> ⚠️ 本 repo 是 **public**，本檔與 handoff.md 會公開，不要寫入敏感資訊。

## 專案簡介

潘湘如醫師（家醫科）的個人工具入口網站，網址 **https://philia81301-commits.github.io/**。
純靜態 GitHub Pages，推 main 自動部署（約 1–2 分鐘生效，瀏覽器端另有 10 分鐘快取）。
各工具留在自己的 repo，這裡只是卡片入口。

## 設計語彙（已多次迭代確認，別自行退回舊版）

- Noto Serif TC 襯線標題＋暖白紙感背景（帶縱向光澤漸層）
- 單一強調色：**暖沙金 #9a6b2a**（曾否決：青綠色、等高線底圖、卡片上直接放 QR、純 CSS 暈染 hero）
- hero：**399麵包坊出爐麵包照**（assets/bread-hero.webp）＋左側奶油遮罩＋
  **玫瑰金玫瑰浮水印**（assets/rose-mark-blend.webp，#B76E79 左粉右金過渡、背景帶光暈）置於標題左側；
  窄螢幕（<1080px）玫瑰縮小移到右上角
- QR code 收成「QR」小按鈕，點擊彈窗放大（適合演講投影）
- 卡片：懸浮陰影、浮凸徽章圖示（漸層底＋高光＋內陰影）、細線 SVG

## 路線圖

- [x] P1 上線：三分區卡片、AI 教學介紹頁、QR 彈窗、README（2026-08-21）
- [x] 視覺迭代定稿：麵包 hero＋玫瑰金玫瑰＋立體化（2026-08-21）
- [x] 優化包：OG 分享卡、favicon、教材線上閱讀版、手機小玫瑰、QR 總表、404（2026-08-22）
- [x] 卡片擴充至 12 張（新增 weight-clinic-reports 月報索引、減重大冒險、肌少症衛教小測驗）
- [ ] 之後有新工具隨時上架（步驟見 README.md；記得 qr/index.html 也加一格）

## 相關產出

- **399麵包坊品牌素材畫布**（Logo／圓形貼紙／IG 社群圖）：
  https://claude.ai/code/artifact/2cac14cb-ca2c-40f3-8f1d-27e40c82f84f

## 資料夾結構

```
index.html            首頁（門診臨床工具／社區篩檢／教學與演講，12 張卡片）
ai-teaching/          AI 教學介紹頁＋教材檔＋線上閱讀版（guide.html／manual.html）
qr/                   QR 總表（A4 可列印）
404.html              品牌風格錯誤頁
assets/               hero 底圖、玫瑰浮水印、OG 分享圖、favicon、qr/ SVG
rdq/                  需求規格卡（.gitignore，不公開）
README.md             維護說明（加新工具的完整步驟）
```

## 固定原則

- 署名「潘湘如醫師｜家醫科」，不放服務單位
- 上架前掃頁面確認無病人資料；收案類工具卡片加註記
- 詳細需求與排除項見本機 `rdq/` 規格卡（未公開）
