# Standardize Security Code

This project aims to provide an integrated link tables between [ISIN](https://en.wikipedia.org/wiki/International_Securities_Identification_Number) and many other company/security identity codes.

Since many link tables are too large, please refer to this [Dropbox](https://www.dropbox.com/sh/uab0vzoxh47wt2j/AACynrEpzjjrH_WD0F8VXX2Ra?dl=0) folder.

## Usage

The data format is [Parquet](https://parquet.apache.org/docs/). To read these files:

- In Python, you can use `pandas.read_parquet` ([Doc](https://pandas.pydata.org/docs/reference/api/pandas.read_parquet.html)).
- In R, you can follow Apache's official [guidance](https://arrow.apache.org/docs/r/reference/read_parquet.html).
- In MATLAB, see MathWork's [guidance](https://www.mathworks.com/help/matlab/parquet-files.html?lang=en).
- In Stata, I have not tested the `stata-parquet` ([GitHub](https://github.com/mcaceresb/stata-parquet)). You can use Python to transform them into CSV format.

You can use URL to always read the most updated version of link tables:

```python
import pandas as pd

df = pd.read_parquet('https://github.com/Wenzhi-Ding/Std_Security_Code/blob/main/isin/a4_orgid.pq?raw=true')
```

## Table of Contents

- `a4_orgid`: Refinitiv ESG (formerly ASSET4) OrgID.
- `cik`: U.S. SEC's [Central Index Key](https://en.wikipedia.org/wiki/Central_Index_Key)
- `ciq_company_id-cusip`: Capital IQ Company ID to CUSIP
- `ciq_company_id-ticker`: Capital IQ Company ID to ticker
- `ciq_company_id`: Capital IQ Company ID.
- `company_name`: Company name.
- `cusip`: [CUSIP](https://en.wikipedia.org/wiki/CUSIP).
- `ds_code`: Refinitiv Datastream Code.
- `df_infocode`: Refinitiv Datastream InfoCode.
- `ein`: U.S. [Employer Identification Number](https://en.wikipedia.org/wiki/Employer_Identification_Number)
- `gvkey`: Global Company Key (GVKEY)
- `gvkey_iid`: Global Company Key (GVKEY) and Issue ID (IID).
- `ibes_ticker`: IBES ticker.
- `reprisk_id`: RepRisk ID.
- `sedol`: [SEDOL](https://en.wikipedia.org/wiki/SEDOL).
- `sp_institutionid`: S&P Global institution ID.
- `ticker`: Stock ticker.
- `ws_sctyppi`: Refinitiv Worldscope Permanent ID.

