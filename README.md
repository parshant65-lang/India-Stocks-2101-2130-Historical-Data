# India-Stocks-2101-2130-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 2101 to 2130)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-2101-2130-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (2101 to 2130)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 2101 | `SANOFI` | Sanofi India Limited | `SANOFI.NS` |
| 2102 | `SANOFICONR` | Sanofi Consumer Healthcare India Limited | `SANOFICONR.NS` |
| 2103 | `SANSTAR` | Sanstar Limited | `SANSTAR.NS` |
| 2104 | `SANWARIA` | Sanwaria Consumer Limited | `SANWARIA.NS` |
| 2105 | `SAPPHIRE` | Sapphire Foods India Limited | `SAPPHIRE.NS` |
| 2106 | `SAPPL` | Shree Ajit Pulp & Paper Limited | `SAPPL.NS` |
| 2107 | `SAREGAMA` | Saregama India Limited | `SAREGAMA.NS` |
| 2108 | `SARLAPOLY` | Sarla Performance Fibers Limited | `SARLAPOLY.NS` |
| 2109 | `SARVESHWAR` | Sarveshwar Foods Limited | `SARVESHWAR.NS` |
| 2110 | `SASKEN` | Sasken Technologies Limited | `SASKEN.NS` |
| 2111 | `SATIA` | Satia Industries Limited | `SATIA.NS` |
| 2112 | `SATIN` | Satin Creditcare Network Limited | `SATIN.NS` |
| 2113 | `SAURASHCEM` | Saurashtra Cement Limited | `SAURASHCEM.NS` |
| 2114 | `SAYAJIHOTL` | Sayaji Hotels Limited | `SAYAJIHOTL.NS` |
| 2115 | `SAYAJIIND` | Sayaji Industries Limited | `SAYAJIIND.NS` |
| 2116 | `SBC` | SBC Exports Limited | `SBC.NS` |
| 2117 | `SBCL` | Shivalik Bimetal Controls Limited | `SBCL.NS` |
| 2118 | `SBFC` | SBFC Finance Limited | `SBFC.NS` |
| 2119 | `SBGLP` | Suratwwala Business Group Limited | `SBGLP.NS` |
| 2120 | `SBIFUNDS` | SBI Funds Management Limited | `SBIFUNDS.NS` |
| 2121 | `SCANSTL` | Scan Steels Limited | `SCANSTL.NS` |
| 2122 | `SCHAND` | S Chand And Company Limited | `SCHAND.NS` |
| 2123 | `SCILAL` | Shipping Corporation of India Land and Assets Limited | `SCILAL.NS` |
| 2124 | `SCODATUBES` | Scoda Tubes Limited | `SCODATUBES.NS` |
| 2125 | `SCPL` | Sheetal Cool Products Limited | `SCPL.NS` |
| 2126 | `SDBL` | Som Distilleries & Breweries Limited | `SDBL.NS` |
| 2127 | `SEAMECLTD` | Seamec Limited | `SEAMECLTD.NS` |
| 2128 | `SECMARK` | SecMark Consultancy Limited | `SECMARK.NS` |
| 2129 | `SECURKLOUD` | SECUREKLOUD TECHNOLOGIES LIMITED | `SECURKLOUD.NS` |
| 2130 | `SEDEMAC` | SEDEMAC Mechatronics Limited | `SEDEMAC.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream SANOFI 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-2101-2130-Historical-Data/main/SANOFI/1m/2026/10/SANOFI_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
