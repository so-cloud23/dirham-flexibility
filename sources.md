# Data Sources

| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Yahoo Finance, using yfinance(EURMAD=X, USDMAD=X, GBPMAD=X) | 2015-2025 | 04/11/2026 | Salma and Rayane |USD/MAD not used, replaced with Bank Al-Maghrib ; Yahoo USD/MAD empty on 22/05/2019: 5 isolated weekdays missing (11/07/2017 ,16/11/2017 ,08/11/2019 ,11/11/2019 ,14/11/2019) ; no rows on market holidays. 
|Daily reference rate USD/MAD | Bank Al-Maghrib  | 2015-2025 | 09/11/2026 | Salma | Replaces Yahoo USD/MAD |

# Data Sources

| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Yahoo Finance, using yfinance (EURMAD=X, USDMAD=X, GBPMAD=X) | 2015-2025 | 04/11/2026 | Salma and Rayane | USD/MAD not used, replaced with Bank Al-Maghrib; Yahoo USD/MAD empty on 22/05/2019; 5 isolated weekdays missing (11/07/2017, 16/11/2017, 08/11/2019, 11/11/2019, 14/11/2019); no rows on market holidays. |
| Daily reference rate USD/MAD | Bank Al-Maghrib | 2015-2025 | 09/11/2026 | Salma | Replaces Yahoo USD/MAD. |
| Daily EUR/GBP rate | Yahoo Finance (EURGBP=X) | 2015-2025 | 10/11/2026 | Rayane | Used to calculate GBP/MAD cross rates (EUR/MAD ÷ EUR/GBP). Flagged movements compared with Bank Al-Maghrib rates; corrections and missing official rates recorded in a cleaning log. |
| Dirham fluctuation band changes | Bank Al-Maghrib press releases | 2018, 2020 | 10/11/2026 | Rayane | Research into the effective dates and changes in the dirham fluctuation band. Official press-release links to be included. |
