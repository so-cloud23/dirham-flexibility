# Data Sources
## Exchange rates used in the analysis 
| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Bank Al-Maghrib, official API(cours virement, middle rate), via its developer portal | 2015-2025 | 11/11/2026 | Salma | Middle rate = moyen where publishes ; for older dates , the average of the buying and selling rates. Matches the website's reference rates on the dates checked (29/12/2025 , 16/03/2015). 2628 dates retrieved; no rates on Moroccan public holidays or 25-26 December| 
| Daily EUR/MAD, USD/MAD , GBP/MAD | Bank Al-Maghrib, official API (cours virement, middle rate), via its developer portal | 2015-2025 | 11/11/2026 | Salma | The API returned no rates for 242 weekdays : 140 Moroccan public holidays plus 25-26 December, and 102 other days (mostly in 2020-2021) for which the API holds no data (tested on 15/04/2020 : 0 entries with any date , time or currency option)  |
| Daily EUR/MAD, USD/MAD , GBP/MAD for 102 API gaps | Bank Al-Maghrib website, cours de référence page, entered by hand ('fx_bam_manual.csv') | 2015-2025 | 12/11/2026 | Salma(2015-2020) & Rayane (2021-2025) | Rates confirmed on the website for days missing from the API (checked first on 15/04/2020). Middle rate , or the average of buying and selling rates where only those are shown |
|Final clean series (fx_rates.csv) | Built from the row above  | 2015-2025 | 13/11/2026 | Rayane | One row per weekday; holidays filled with the previous working day's rate; 1 January 2015 takes the first available rate. Flag check on the official data : to be added |
|Inflation (annual average CPI) |[HCP – IPC releases] (https://www.hcp.ma/Actualite-Indices-des-prix-a-la-consommation-IPC_r349.html) | 2015–2025 | Salma | From HCP's December CPI release of each year ("IPC annuel moyen"), one page per year. CPI base changed from 2006 to 2017 in 2020; yearly % changes remain comparable. To be checked against World Bank FP.CPI.TOTL.ZG (Rayane). |


## Trade and external date 

| Data | Source | Period | Downloaded | By | Notes 
| --- | --- | --- | --- | --- | --- |
| Exports by product group | [WITS - World Bank] (https://wits.worldbank.org) | 2023 | 17/11/2026 | Salma | Grouping "Sector" , sheet "Product"  | Grouped into 6 categories. Total US$ 42.46bn (goods only) | 
| Exports by partner | [WITS - World Bank] (https://wits.worldbank.org) | 2023 | 17/11/2026 | Salma | Sheet "Partner", grouped into eurozone (20 countries) , UK, US, rest of the world.| 
| Exports , import, remittance (% of GDP), REER| [World Bank - WDI] (https://data.worldbank.org) via 'wbgapi' |2015 - 2025 | 17/11/2026 | Salma | NE.EXP.GNFS.ZS, NE.IMP.GNFS.ZS, BX.TRF.PWKR.DT.GD.ZS, PX.REX.REER, 2015–2025.| 
| Remittances (US$ and MAD) | [World Bank – WDI] (https://data.worldbank.org) via 'wbgapi' | 2015-2025 | 17/11/2026 | Salma | BX.TRF.PWKR.CD.DT, 2015–2025. Converted to MAD with the yearly average BAM USD/MAD rate. | 
| Remittances check | [Office des Changes] (https://www.oc.gov.ma/fr/publications) | 2019 , 2023 | 17/11/2026 | Salma |"Recettes MRE", December issues: 64.86bn MAD (2019), 115.15bn MAD (2023). World Bank is 3.2% and 3.4% higher, because it also includes compensation of employees. | 


## Sources tested and not used

| Data | Source | Period | Downloaded | By | Notes |
| --- | --- | --- | --- | --- | --- |
| Daily exchange rates: EUR/MAD, USD/MAD, GBP/MAD | Yahoo Finance, using yfinance (EURMAD=X, USDMAD=X, GBPMAD=X) | 2015-2025 | 04/11/2026 | Salma and Rayane | USD/MAD flagged 399 days (EUR 6 , GBP 20) by a spike test. EUR checked against Bank-Al Maghrib by Salma; GBP rebuilt as a cross rate by Rayane; USD rebuilt as a cross rate by Salma and Rayane. Compared with Bank-AlMaghrib's offical rates (by Salma), EUR/MAD was on average about 2.9% lower on the 3 days tested, and the cross rates inherited the gap. Tests kept in 'yahoo_test.ipynb' |
| Daily EUR/GBP rate | Yahoo Finance (EURGBP=X) | 2015-2025 | 10/11/2026 | Rayane | Used to calculate GBP/MAD cross rates (EUR/MAD ÷ EUR/GBP). Flagged movements compared with Bank Al-Maghrib rates; corrections and missing official rates recorded in a cleaning log. |
| Bank Al-Maghrib website , read by code | bkam.ma, cours de référence pages | 2015-2025 | 11/11/2026 | Salma | The site blocks automated requests (403 Forbidden), so the official API was used instead. |
| Exports by product and partner | [OEC ] [oec.world](https://oec.world) | 2023 | 17/11/2026 | Salma | Detailed downloads need a paid Pro account, so WITS was used instead. | 
| CPI weights | [HCP – Brefs du Plan n° 3] (https://hcp.ma/file/230486) | 2014 survey | Salma | Weights from a 2018 note, published before the base 2017 CPI. They differ slightly from the official file (e.g. education 6.25% vs 5.64%), so the official file was used. |
for
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
### Tourism receipts

- **Primary source:** Office des Changes – [Evolution des recettes de voyages](https://www.oc.gov.ma/sites/default/files/Evol_recettes_Voyages_16.xlsx).
- **Data collected:** Annual tourism receipts for 2015–2025, converted from MAD millions to MAD billions.
- **Output file:** `data/clean/oc_tourism.csv`.
- **Cross-check:** World Bank indicator `ST.INT.RCPT.CD` (International tourism receipts, current US$).
- **Limitation:** The World Bank API returned a missing value (`NaN`) for Morocco in 2023. Therefore, a comparison with Office des Changes could not be completed for that year.
- **Decision:** Office des Changes figures are retained as the primary tourism receipts dataset.
### Transportation imports and exports

- **Source:** World Bank WITS – Morocco trade data, 2023.
- **Import file:** `wits_imports_product_2023.xlsx`.
- **Export file:** `wits_exports_product_2023.xlsx`.
- **Method:** Compared WITS Transportation imports with Transportation exports, using USD millions.
- **Result:** Imports were $8,383.10 million and exports were $9,252.99 million. The imports-to-exports ratio was 90.60%.
- **Output:** `data/clean/transport_imports_exports_ratio.csv`.
- **Limitation:** WITS Transportation is a broad product group and does not isolate car parts or vehicle exports. Therefore, this ratio is a sector-level proxy, not an exact measure of imported car parts used in Moroccan car production.


