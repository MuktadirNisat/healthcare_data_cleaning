# Healthcare Data Cleaning Pipeline

An automated end-to-end data cleaning pipeline built with Python and Pandas to preprocess and standardize raw healthcare records (55,000+ rows).

## Key Cleaning Operations
- **Text Standardization:** Title-cased patient names, normalized gender values, and stripped stray symbols (`#`, `,`) from doctor and hospital records.
- **Missing Value Imputation:** Applied mean imputation for numerical columns (`Age`, `Billing Amount`), mode imputation for low-cardinality categories (`Gender`, `Blood Type`), and `"Unknown"` / `"Not Assign"` placeholders for high-cardinality fields.
- **Regex & Currency Parsing:** Cleaned `"USD"` suffixes from billing amounts, rounded decimals, and collapsed duplicate `+/-` signs in blood types using regular expressions.
- **Date Normalization:** Unified mixed date formats (`YYYY-MM-DD`, `DD/MM/YYYY`, `.` separators) into standard datetime objects.

## How to Run
```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python scripts/clean_data.py