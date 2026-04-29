# Standardize Security Code

This project aims to provide integrated link tables between [ISIN](https://en.wikipedia.org/wiki/International_Securities_Identification_Number) and many other company/security identity codes.

**If you find any link to be outdated, please email me (wenzhi.ding@outlook.com) and I will update it.**

Some link tables are too large to be hosted on GitHub. Please email me to obtain them (see ⚠️ marks below).

Just in case you are interested in similar data tools, I also constructed:
- [Standardized Country Code](https://github.com/Wenzhi-Ding/Std_Country_Code)
- [Fama French Industry to SIC Link](https://github.com/Wenzhi-Ding/FamaFrenchIndustry)

Please star the projects if you feel it is useful! Many thanks for your appreciation and support!

## Usage

The data format is [Parquet](https://parquet.apache.org/docs/). To read these files:

- In Python, you can use `pandas.read_parquet` ([Doc](https://pandas.pydata.org/docs/reference/api/pandas.read_parquet.html)).
- In R, you can follow Apache's official [guidance](https://arrow.apache.org/docs/r/reference/read_parquet.html).
- In MATLAB, see MathWorks [guidance](https://www.mathworks.com/help/matlab/parquet-files.html?lang=en).
- In Stata, I have not tested the `stata-parquet` ([GitHub](https://github.com/mcaceresb/stata-parquet)). You can use Python to transform them into CSV or `.dta` format.

You can use URL to always read the most updated version of link tables:

```python
import pandas as pd

df = pd.read_parquet('https://github.com/Wenzhi-Ding/Std_Security_Code/blob/main/isin/a4_orgid.pq?raw=true')
```

## Table of Contents (ISIN-centered)

- `a4_orgid`: Thomson Reuters/Refinitiv (LSEG) ESG (formerly ASSET4) OrgID.
- `cik`: U.S. SEC's [Central Index Key](https://en.wikipedia.org/wiki/Central_Index_Key)
- `ciq_company_id-cusip`: Capital IQ Company ID to CUSIP. ⚠️ **Too large for GitHub. Email me to obtain.**
- `ciq_company_id-ticker`: Capital IQ Company ID to ticker
- `ciq_company_id`: Capital IQ Company ID. ⚠️ **Too large for GitHub. Email me to obtain.**
- `company_fkey`: Company Fkey from Audit Analytics
- `company_name`: Company name (If you are doing a fuzzy match on the company name, try this dataset!) ⚠️ **Too large for GitHub. Email me to obtain.**
- `cusip`: [CUSIP](https://en.wikipedia.org/wiki/CUSIP).
- `ds_code`: Thomson Reuters/Refinitiv (LSEG) Datastream Code.
- `ds_infocode`: Thomson Reuters/Refinitiv (LSEG) Datastream InfoCode.
- `ein`: U.S. [Employer Identification Number](https://en.wikipedia.org/wiki/Employer_Identification_Number)
- `fisd_issue_id`: FISD issue ID
- `fisd_issuer_id`: FISD issuer ID
- `gvkey_iid`: Global Company Key (GVKEY) and Issue ID (IID).
- `gvkey`: Global Company Key (GVKEY)
- `ibes_ticker`: IBES ticker.
- `reprisk_id`: RepRisk ID.
- `ric`: Thomson Reuters/Refinitiv (LSEG) RIC. ⚠️ **Too large for GitHub. Email me to obtain.**
- `sedol`: [SEDOL](https://en.wikipedia.org/wiki/SEDOL).
- `sp_institutionid`: S&P Global institution ID.
- `stkcd_china`: China stock code.
- `ticker`: Stock ticker.
- `ws_sctyppi`: Thomson Reuters/Refinitiv (LSEG) Worldscope Permanent ID.

## Table of Contents (Other)

Here I provide some other link. Mostly from WRDS. Please make sure you have rights to access the corresponding link table. This is just for your convenient of downloading link tables.

- `cik_cusip`: CIK to CUSIP mapping.
- `cik_gvkey`: CIK to GVKEY mapping.
- `cik_names`: CIK to company name mapping.
- `cik_ticker`: CIK to ticker mapping.
- `gvkey_permco_permno`: Compustat's GVKEY to CRSP's PERMNO and PERMCO.

## Important Notes

- **Static Link Relationships:** This dataset captures only static identifier linkages at the time of construction. Certain mappings may have been valid only during specific historical periods and may no longer reflect current relationships. Users should be aware of this temporal limitation and exercise appropriate caution when interpreting the data.

- **Intended Use:** This dataset is primarily suited for preliminary exploration and rapid validation of ideas. It is **not recommended** for direct use in published research or formal reports without independent verification of the underlying linkages.

- **Data Types:** Where applicable, fields that can be represented as integers (e.g., GVKEY) are stored as integer types rather than zero-padded strings. Users who require string-formatted values with leading zeros should perform the necessary formatting conversions themselves.
