# 個人工具入口網站（專案藍圖）

> 本檔為跨 Agent 通用的專案藍圖。任何 Agent 的每個 session 都應先讀本檔＋`handoff.md`。
> ⚠️ 本 repo 是 **public**，本檔與 handoff.md 會公開，不要寫入敏感資訊。

## 專案簡介

潘湘如醫師（家醫科）的個人工具入口網站，網址 **https://philia81301-commits.github.io/**。
純靜態 GitHub Pages，推 main 自動部署（約 1–2 分鐘生效，瀏覽器端另有 10 分鐘快取）。
各工具留在自己的 repo，這裡只是卡片入口。

## 設計語彙（已多次迭代確認，別自行退回舊版）

- Noto Serif TC 襯線標題＋暖白紙感背景
- 單一強調色：**暖沙金 #9a6b2a**（曾否決：青綠色、等高線底圖、卡片上直接放 QR）
- hero 為純 CSS 漸層暈染（無圖檔），偏深的琥珀金
- QR code 收成「QR」小按鈕，點擊彈窗放大（適合演講投影）
- 卡片：直角、細框、留白、細線 SVG 圖示

## 路線圖

- [x] P1 上線：三分區 10 張卡片、AI 教學介紹頁、QR 彈窗、README 維護說明（2026-08-21）
- [ ] 之後有新工具隨時上架（步驟見 README.md）

## 資料夾結構

```
index.html            首頁（門診臨床工具／社區篩檢／教學與演講）
ai-teaching/          AI 教學介紹頁＋教材檔（代管自 private 的 agent-roadshow）
assets/qr/            預產 QR SVG（本機 Python qrcode 套件產生）
rdq/                  需求規格卡（.gitignore，不公開）
README.md             維護說明（加新工具的完整步驟）
```

## 固定原則

- 署名「潘湘如醫師｜家醫科」，不放服務單位
- 上架前掃頁面確認無病人資料；收案類工具卡片加註記
- 詳細需求與排除項見本機 `rdq/` 規格卡（未公開）
