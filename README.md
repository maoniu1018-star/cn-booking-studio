# CN Booking Studio｜線上預約平台

此儲存庫獨立存放 CN Booking Studio，不與 CN Creative Studio 作品集混用。

## 網站入口
- `index.html`：平台首頁
- `platform.html`：平台管理員登入及店家清單
- `platform-dashboard.html`：店家服務與預約管理
- `demo.html`：本機展示版（不連雲端，不可當正式預約）

## Supabase 設定
SQL 執行順序：
1. `supabase/schema.sql`
2. 先在 Supabase Auth 建立管理員帳號，並確認管理員 UID。
3. `supabase/platform-admin.sql`（其中 UID 必須與管理員帳號一致；目前檔案使用已確認的管理員 UID）
4. 若未來要開放店家自行註冊，再評估啟用 `supabase/onboarding.sql`；目前平台由管理員建立店家。

前端只使用 Supabase Project URL 與公開 Publishable/anon key。絕不可將 service_role 或 Secret key 放入網站。

## 權限規則
- 平台管理員建立及管理店家。
- 店家自行註冊暫不開放；只有平台正式銷售並決定開通時才啟用。
- 顧客預約不需要平台帳號。
- 顧客不得讀取預約清單或其他顧客個資。

## 目前狀態
此版本已搬入管理頁、店家後台及 Supabase SQL。正式顧客雲端預約頁、時段管理、付款及通知尚待完成與測試。
