# 台股量價研究室公開資料更新排程

這個專案只包含公開網站的固定更新網址與排程，不包含個人持股、成本、帳號、秘密或主程式。主程式仍在原本的私人儲存庫。

台北時間一般交易時段09:00–13:30目標每10分鐘；其他時間目標每30分鐘。GitHub cron使用UTC；網站伺服器另外比對證交所年度開休市表及重複時段。臨時停市公告尚未自動辨識。盤中價格可能延遲，日線排名仍僅使用完整收盤，財報仍依實際公告期別與6小時來源快取。

排程以 POST 呼叫固定刷新端點，使用 Actions secret CRON_KEY 的 X-Cron-Key header 驗證；秘密不寫入儲存庫或輸出日誌。主刷新後另檢查全市場驗證封存，再讀取公開資料健康。沒有個人持股、券商登入或下單權限。permissions設為空，不使用外部Actions、checkout、套件安裝或寫入儲存庫。每輪最多5分鐘、同時最多一輪，無產物上傳。來源問題保留在網站健康資料與Actions日誌，不另寄使用者更新報告；工作完成只表示完成嘗試，不代表各來源成功。

[網站](https://taiwan-momentum-lab-joey-1027.plumjelly7.chatgpt.site) · [資料健康](https://taiwan-momentum-lab-joey-1027.plumjelly7.chatgpt.site/api/health)

[標準GitHub執行器在公開專案免費](https://docs.github.com/en/actions/concepts/billing-and-usage)。[排程可能因負載延遲，公開專案60天無活動可能自動停用](https://docs.github.com/en/actions/how-tos/troubleshoot-workflows)，因此這是更新目標，不是準點服務承諾。原ChatGPT每小時排程改為停用，避免重複執行與例行通知。

更新日誌：2026-10-28建立；替代平台每小時上限的排程。未改其他舊專案。

2026-10-29：改為受驗證 POST；新增全市場前瞻封存健康檢查。私人持股模擬另由本機 Codex 盤中每10分鐘喚醒，需電腦與應用程式運作；這個雲端工作只刷新公開市場與驗證資料，不操作私人帳戶。

