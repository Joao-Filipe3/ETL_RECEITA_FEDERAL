# ETL Receita Federal - Brazilian Companies Analysis

This project uses **PySpark** to perform an ETL (Extract, Transform, Load) pipeline on public data from the Brazilian Federal Revenue Service (Receita Federal). The goal is to identify and analyze Brazilian companies based on key characteristics such as **company size**, **registration status**, **location**, **economic activity**, and **foreign ownership**.

## Data Sources

Data files were obtained from Receita Federal’s official website:

- `Empresas.csv` – Company name, size, capital, legal nature.
- `Estabelecimentos.csv` – Trade name, registration status, full CNPJ, state (UF), head office or branch.
- `Socios.csv` – Shareholder information.
- `CNAEs.csv` – Main and secondary economic activity codes.
- Other metadata: Legal nature, shareholder qualification, etc.

##  Technologies Used

- [x] PySpark
- [x] Pandas (for final transformation and visualizations)
- [x] Matplotlib (for basic dashboard graphs)
- [x] Jupyter Notebook
- [x] Git & GitHub

## ETL Process

### Extraction
CSV files were read using `spark.read.csv`, with proper handling of encoding, delimiters, and schema inference.

### Transformation
- Table joins using keys such as `cnpj_basico`
- Construction of the complete CNPJ (`cnpj_basico + ordem + dv`)
- Casting of data types (strings, decimals)
- Use of temporary views to run SQL queries
- Null value treatment and category standardization

### Load
The transformed DataFrames were converted to `Pandas` for exploratory analysis and plotting.

## Key Analyses

-  Company count by **Size** (Micro, Small, Others)
-  Company count by **Registration Status** (Active, Inactive, Suspended)
-  Distribution by **State (UF)**
-  Top **Economic Activities (CNAE)**
-  Main activities of **Inactive/Suspended** companies


##  Sample Visualizations

| Chart                  | Description                                 |
|------------------------|-------------                                |
| Companies by Size      | Distribution of Micro, Small, and Others    |
| Registration Status    | Active, Inactive, Suspended...              |
| Companies by State     | Count of companies by UF (state)            |
| Top CNAEs              | Most common economic activity codes         |


## Key Takeaways

- Working with large-scale data using PySpark
- Efficient SQL queries over distributed DataFrames
- Exploratory data analysis and plotting techniques
- Git version control and project organization

## Project Structure
dados_receita/
├── empresas.csv
├── estabelecimentos.csv
├── socios.csv
├── cnaes.csv
ETL_Receita.ipynb
README.md
