# Data Sources

| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Yahoo Finance, using yfinance(EURMAD=X, USDMAD=X, GBPMAD=X) | 2015-2025 | 04/11/2026 | Salma and Rayane |USD/MAD not used, replaced with Bank Al-Maghrib ; Yahoo USD/MAD empty on 22/05/2019: 5 isolated weekdays missing (11/07/2017 ,16/11/2017 ,08/11/2019 ,11/11/2019 ,14/11/2019) ; no rows on market holidays. 
|Daily reference rate USD/MAD | Bank Al-Maghrib  | 2015-2025 | 09/11/2026 | Salma | Replaces Yahoo USD/MAD |
# Data Sources

| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Yahoo Finance, using yfinance (EURMAD=X, USDMAD=X, GBPMAD=X) | 2015-2025 | 04/11/2026 | Salma and Rayane | Yahoo USD/MAD not used; replaced with Bank Al-Maghrib reference rates. Yahoo USD/MAD empty on 22/05/2019; 5 isolated weekdays missing (11/07/2017, 16/11/2017, 08/11/2019, 11/11/2019, 14/11/2019); no rows on market holidays. |
| Daily reference rate USD/MAD | Bank Al-Maghrib | 2015-2025 | 09/11/2026 | Salma | Used instead of Yahoo USD/MAD because the Yahoo series was considered unreliable. |
| EUR/MAD corrections | Bank Al-Maghrib, cours de référence | 6 dates | 10/11/2026 | Salma | Flagged unusual movements checked against Bank Al-Maghrib. Four Yahoo values replaced; one date without an official rate (24/04/2023) set to missing; one genuine movement retained (05/08/2024). |
| Daily EUR/GBP rate | Yahoo Finance (EURGBP=X) | 2015-2025 | 10/11/2026 | Rayane | Used to calculate GBP/MAD cross rates (EUR/MAD ÷ EUR/GBP). Flagged movements compared with Bank Al-Maghrib rates; corrections and missing official rates recorded in a cleaning log. |
| Daily EUR/USD rate | Yahoo Finance (EURUSD=X) | 2015-2025 | 10/11/2026 | Salma | Used to calculate USD/MAD cross rates (EUR/MAD ÷ EUR/USD). Flagged movements checked against Bank Al-Maghrib; final corrections recorded in a cleaning log. |
| Dirham fluctuation band changes | Bank Al-Maghrib press releases | 2018, 2020 | 10/11/2026 | Rayane | Official announcements used to identify the effective dates and changes in the dirham fluctuation band. |
