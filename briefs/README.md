# 每日早報（Claude 自動彙整）

- `latest.json`：最新一份，網站「全球事件」頁讀這個檔。
- `YYYY-MM-DD.json`：每天一份存檔，不覆寫舊日期。
- 由 Claude 雲端排程每天台北早上產生並直接提交 main（不開 PR），網站自動讀取，不需要合併或重新發布。
- 只放公開新聞的標題、原文連結、來源名稱與 Claude 自己寫的一句話摘要；不放全文、私人持股、成本或任何秘密。
- 摘要可能漏掉或寫錯，以原文為準；早報不進選股分數、不改買賣規則。

格式（version 1）：`{version, date, generatedAt, summary, items:[{title, fact, source, url, theme, publishedAt}]}`，最多 20 則；`theme` 為 tw / company / trade / export / rates / fx / energy / geo / demand / supply / other。
