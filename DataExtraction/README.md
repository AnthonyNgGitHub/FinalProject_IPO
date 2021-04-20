# Data Extraction

## Sources

IPO Scoop

https://www.iposcoop.com/scoop-track-record-from-2000-to-present/

Alpha Vantage

https://www.alphavantage.co/documentation/

## Methodology

1. Initial list of IPOs in the United States from 2000 to 2020 was downloaded from www.iposcoop.com and saved in the "raw_dataset/downloaded_listing" folder, named as "downloaded_listing_ETL.xlxs"

2. The downloaded_listing_ETL.xlxs was transformed by appending all the tables in the SCOOP_Scorecard tab into one combined table on the Appended tab with a total of 3,633 records. 

- 2.1 Dupliicated symbols were identified, copied and pasted on the Removed tab. Total of 163 records were removed due to duplicated symbols. 
- 
- 2.2 The Final tab has a total of 3,470 records with unique symbols. This tab was copied and saved as a csv file, named as "IPO_SCOOP_Listing.csv", saved under the "raw_dataset" folder.

3. Under the "notebooks/from_apha_vantage" folder, there are 5 Jupyter Notebooks created to retrieve data from Alpha Vantage:

- 3.1.1 "company_overview_data" was created to loop through all of the symbols in the 
"IPO_SCOOP_Listing.csv" to retreive company overview data for each symbol via API requests, such as the exchange where the stock is listed, the industry of the company, and the sector of the company. 

- 3.1.2 Note: Out of the total of 3,470 records in the IPO_SCOOP_Listing, 785 of them were not found on Alpha Vantage. Therefore, there are 2,685 records retreived from this API request. The results were saved in "raw_dataset" folder, named as "company_overview.csv". The list of symbols not found on Alpha Vantage is saved in the same folder, named "company_overview_key_errors.csv".

- 3.2 "daily_adjusted_prices" was created to loop through all of the symbols in the "company_overview.csv" to retrieve daily adjusted prices for each symbol via API requests. The results were saved in "raw_dataset/daily_adjusted" folder where each symbol has its own CSV file.

- 3.3 "income_statement", "balance_sheet" and "cash_flow" were created to loop through all of the symbols in the "company_overview.csv" to retreive the quarterly financial data for each symbol via API requests. The results were saved in "raw_dataset/income_statement", "raw_dataset/balance_sheet", and "raw_dataset/cash_flow" folders where each symbol has its own CSV file.

4. Under the "notebooks/filter_statements" folder, there are 3 Jupyter Notebooks ("filter_balance_sheet", "filter_income_statement", and "filter_cash_flow") created to filter the financial data for each symbol:

- 4.1 Since the income statements, balance sheets, and cash flows retreived in step 3.3 contains many records of quarterly financial data for each symbol, each filter notebook is designed to filter for the record that is within +/- 45 days of the IPO date as identified on the "IPO_SCOOP_Listing". 

- 4.2 The results were saved in "raw_dataset/filtered_income_statement", "raw_dataset/filtered_balance_sheet", and "raw_dataset/filtered_cash_flow" folders where each symbol has its own CSV file. 

- 4.3 All of the above files are then further combined into 3 consolidated CSV files under the "raw_dataset" folder, named as "combined_filtered_income_statement.csv", "combined_filtered_balance_sheet.csv", and "combined_filtered_cash_flow.csv".

5. Under the "notebooks/three_month_return_calculation" folder, there is 1 Juypter Notebook created to perform the following:

- 5.1 retreive the Daily Adjusted Price 3 month after the IPO date, 

- 5.2 calculate the percentage return, and

- 5.3 clasify the return as either a gain or a loss

- 5.4 The results were saved in the "raw_dataset" folder, named as "three_month_return.csv"

6. The CSV files in the raw_dataset folder are used to create the SQL database. 

- Please refer to the "SQL" folder for futher details.
