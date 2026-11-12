# Data Sources
## Exchange rates used in the analysis 
| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Bank Al-Maghrib, official API(cours virement, middle rate), via its developer portal | 2015-2025 | 11/11/2026 | Salma | Middle rate = moyen where publishes ; for older dates , the average of the buying and selling rates. Matches the website's reference rates on the dates checked (29/12/2025 , 16/03/2015). 2870 dates retrieved; no rates on Moroccan public holidays or 25-26 December ([n] days)
|Final clean series (fx_rates.csv) | Built from the row above  | 2015-2025 | 11/11/2026 | Rayane | One row per weekday; holidays filled with the previous working day's rate; 1 January 2015 takes the first available rate. Flag check on the official data : to be added |

## Sources tested and not used

| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Yahoo Finance, using yfinance (EURMAD=X, USDMAD=X, GBPMAD=X) | 2015-2025 | 04/11/2026 | Salma and Rayane | USD/MAD flagged 399 days (EUR 6 , GBP 20) by a spike test. EUR checked against Bank-Al Maghrib by Salma; GBP rebuilt as a cross rate by Rayane; USD rebuilt as a cross rate by Salma and Rayane. Compared with Bank-AlMaghrib's offical rates (by Salma), EUR/MAD was on average about 2.9% lower on the 3 days tested, and the cross rates inherited the gap. Tests kept in 'yahoo_test.ipynb' |
| Daily EUR/GBP rate | Yahoo Finance (EURGBP=X) | 2015-2025 | 10/11/2026 | Rayane | Used to calculate GBP/MAD cross rates (EUR/MAD ÷ EUR/GBP). Flagged movements compared with Bank Al-Maghrib rates; corrections and missing official rates recorded in a cleaning log. |
| Bank Al-Maghrib website , read by code | bkam.ma, cours de référence pages | 2015-2025 | 11/11/2026 | Salma | The site blocks automated requests (403 Forbidden), so the official API was used instead. |

## Other data

| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Dirham fluctuation band changes | Bank Al-Maghrib press releases | 2018, 2020 | 10/11/2026 | Rayane | Research into the effective dates and changes in the dirham fluctuation band. Official press-release links to be included. |
| USD/TND (Tunisia) | to be added  | 2015-2025 | to be added | Salma | Comparison only |
| USD/EGP (Egypt) | to be added | 2015-2025 | to be added  | Rayane | Comparison only |

## Background reading
| Title | Source and link | Date published | Found by | Read by | Used for |
| --- | --- | --- | --- | --- | --- |
| The Role of a Flexible Foreign Exchange System in Macroeconomic Adjustment: The Case of Morocco (policy brief, Abdelaaziz Ait Ali) | [Policy Center for the New South] (https://www.policycenter.ma/index.php/publications/role-flexible-foreign-exchange-system-macroeconomic-adjustment-case-morocco) | January 2019 | Rayane | Salma | Why a flexible rate helps Morocco absorb shocks; the 2018 widening to ±2.5% as a first step towards a managed float |
| Morocco: 2026 Article IV Consultation and Review Under the Flexible Credit Line Arrangement (IMF Country Report No. 26/72) | [IMF] (https://www.imf.org/-/media/files/publications/cr/2026/english/1marea2026001-source-pdf.pdf) | March 2026 | Rayane | Salma | The latest offcial view : band widened in 2018 and 2020; dirham near the stronf end of the bans since mid-2025; plan for an inflation target, possibly in 2027; why the reform is gradual |



