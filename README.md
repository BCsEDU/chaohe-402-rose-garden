# 🌹 402 數學互動課堂：《正方形玫瑰花圃（百格紙）》

對應四年級數學小數單元百格紙操作題（附件 20），採用 **GitHub Pages + Supabase + Edge Function (`rose-garden`)** 架構，支援全班 1～29 號學生兩兩一組、最多 15 組在 iPad 上同時觸控塗色與教師大螢幕展示。

## 檔案結構
- `index.html`：學生 iPad 操作頁（1～29 號組員選單、最多 15 組同時在線、10×10 觸控/滑動塗色、玫瑰花/純色塊切換、即時檢核與迷思提示、自動同步）
- `teacher.html`：教師後台與大螢幕展示系統（沿用 `teacher_config` 密碼、15 組進度與 1～29 號組隊覆蓋檢查、迷思統計、單組投影聚焦/數數編號模式、2～4 組並排對比、CSV 匯出、清空歸零）
- `supabase/migrations/20261117000001_create_rose_garden_groups.sql`：`rose_garden_groups` 資料表與最小權限 RLS
- `supabase/functions/rose-garden/index.ts`：Supabase Edge Function（已完成部署至 `ppdgubracsneozahujxl`）

## 上線前最後 1 個步驟（僅需執行一次）
1. 打開 Supabase Dashboard → `xueli-quiz` (`ppdgubracsneozahujxl`) → **SQL Editor**
2. 貼上並執行 `supabase/migrations/20261117000001_create_rose_garden_groups.sql`（或在 `teacher.html` 登入後直接點「📋 複製建表 SQL」）
