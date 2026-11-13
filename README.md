# UK Insurance Consumer Duty Analysis

A practical data analytics project using Python, SQL, and Power BI to analyze customer outcomes, fair value, and service standards in UK financial services against FCA Consumer Duty rules.

## About The Project

In the UK, financial companies must follow rules set by the Financial Conduct Authority (FCA) called Consumer Duty. The main idea behind Consumer Duty is simple: financial firms should treat their customers fairly, offer products that deliver genuine value, provide responsive customer service, and ensure that vulnerable people are never disadvantaged.

I built this project to learn how data analysts measure and monitor these requirements in practice. By combining official UK benchmark statistics with a simulated customer dataset, this project investigates whether an insurance firm is meeting regulatory expectations or leaving certain customer groups with poor outcomes.

This analysis focuses on four key areas:
1. Products and Services: Checking whether customers are enrolled in products that actually fit their needs.
2. Price and Value: Comparing internal claims payout ratios against published FCA market benchmarks to see if customers receive fair value for the premiums they pay.
3. Consumer Support: Measuring complaint resolution times across different contact channels like phone, email, and mobile apps.
4. Vulnerability Disparities: Checking whether vulnerable customers face higher complaint rates or lower claim acceptance rates compared to non-vulnerable customers.

## How The Project Works

The analysis follows four main steps from raw data processing to final reporting:

1. Data Sources and Preparation
   The project uses real public datasets published by the UK Financial Conduct Authority and the Financial Ombudsman Service (FOS), including general insurance value measures and complaint statistics. To simulate an operational firm without using sensitive personal data, I paired these public benchmarks with a synthetic portfolio of 50,000 customers, policy sales records, and complaint logs.

2. Data Cleaning and Loading (Python)
   Python scripts clean the incoming Excel files and CSVs, validate data consistency, calculate customer age groups and vulnerability flags, and load the processed tables into a local SQLite database.

3. Metric Calculation and Analysis (SQL)
   I wrote specialized SQL scripts to answer specific governance questions, such as calculating claims acceptance ratios by product line, finding the average days taken to close complaints, and detecting disparities in customer outcomes.

4. Visualization and Reporting (Power BI and Excel)
   The final findings are brought into Power BI to create an interactive reporting dashboard. This allows reviewers to filter metrics by product category, customer segment, and communication channel.

## Key Findings From The Analysis

- Claims Payout Gaps: While motor and home insurance products maintained healthy claims payout ratios above 55%, certain add-on protection policies showed payout ratios below 30%, which indicates a potential fair value risk under FCA guidelines.
- Support Channel Delays: Customer complaints submitted by post or web form took an average of six days longer to resolve than inquiries made through digital chat channels.
- Vulnerability Impact: Customers flagged with health or financial vulnerabilities experienced an 11% higher complaint rate and slightly lower initial claim acceptance, highlighting a clear area where customer support processes need improvement.

## Technologies Used

- Python (pandas, openpyxl, sqlite3, pytest): Used for reading Excel and CSV datasets, data transformation, database population, and running automated tests.
- SQL (SQLite): Used for table schemas, aggregations, window functions, and business metric queries.
- Power BI: Used for data modeling, DAX measure creation, and visual dashboard presentation.
- Excel and CSV: Used for raw regulatory data ingestion, benchmark tables, and data validation.

## Repository Structure

- data/: Contains raw FCA spreadsheets and processed data tables.
- scripts/: Python scripts for data ingestion, database creation, and running the pipeline.
- queries/: SQL scripts covering products and services, price and value, customer support, and vulnerability analysis.
- powerbi/: Power BI report files and dashboard screenshot previews.
- reports/: Detailed documentation, briefing notes, and DAX measure reference guides.
- tests/: Pytest scripts to verify database schema integrity and data completeness.
- requirements.txt: Python libraries required to run the scripts.

## How To Run This Project Locally

### 1. Clone the repository
```bash
git clone https://github.com/sharmi2112-hub/uk-consumer-duty-analysis.git
cd uk-consumer-duty-analysis
```

### 2. Set up a Python virtual environment
```bash
python -m venv venv
```

On Windows:
```bash
venv\Scripts\activate
```

On macOS or Linux:
```bash
source venv/bin/activate
```

### 3. Install required packages
```bash
pip install -r requirements.txt pytest
```

### 4. Run the data scripts
```bash
python scripts/build_star_schema.py
python scripts/ingest_to_sqlite.py
```

This processes the raw data files and builds the SQLite database containing all customer, policy, and complaint records.

### 5. Run the test suite
```bash
pytest
```

This checks that the SQLite database has all required tables, non-empty rows, and expected column types.

### 6. Inspect the SQL queries and Dashboard
- Open the .sql files in the queries/ directory using DB Browser for SQLite or any SQL editor to review the metric logic.
- Open the .pbix file in the powerbi/ directory using Power BI Desktop to view the interactive outcome dashboards.

## What I Learned From Building This

Working on this project taught me several practical data analytics lessons:
- How to interpret and apply real regulatory frameworks like FCA Consumer Duty to data analysis problems.
- How to connect multi-table relational datasets across customers, policies, and complaint logs.
- How to compare internal operational metrics against published industry benchmarks to detect business risks.
- How to communicate complex compliance and fairness findings in a clear, human way that non-technical readers can easily understand.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
