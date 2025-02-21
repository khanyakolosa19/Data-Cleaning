# Data Cleaning in SQL

## Project Overview
This project focuses on cleaning and preprocessing messy data using SQL. The goal is to ensure data consistency, accuracy, and usability for analysis. The dataset undergoes various cleaning techniques such as handling missing values, removing duplicates, standardizing formats, and correcting inconsistencies.

## Dataset
- The dataset contains records related to [company, location, industry, total laid off, percentage laid off, date, stage, country, and funds raised(in millions)].
- The raw data includes issues such as missing values, duplicate entries, incorrect date formats, and inconsistent text capitalization.

## Technologies Used
- SQL
- Database Management System: MySQL

## Data Cleaning Steps
1. **Removing Duplicates**: Identifying and deleting duplicate records to avoid redundancy.
2. **Standardising Formats**:
   - Converting date formats (e.g., `MM/DD/YYYY` to `YYYY-MM-DD`).
   - Normalising text fields (e.g., removing white spaces).
3. **Handling NULL Values**: Replacing missing data with     
appropriate default values or dropping incomplete rows.
4. **Correcting Inconsistencies**: Fixing inconsistent spelling and data entry errors.

## SQL Queries Used
```sql
-- Removing duplicates
WITH duplicate_cte AS 
(
SELECT *,
ROW_NUMBER() OVER(
PARTITION BY company, location, industry, total_laid_off, percentage_laid_off, `date`, stage, funds_raised_millions) AS row_num
FROM layoffs_staging
)
DELETE
FROM duplicate_cte
WHERE row_num > 1;
```

## How to Use
1. Load the dataset into your SQL database.
2. Run the provided SQL scripts to clean the data.
3. Verify the cleaned data by querying the processed table.

## Results & Insights
- After cleaning, the dataset is free from duplicates and inconsistencies, ensuring better accuracy in data analysis.
- Improved data integrity allows for better decision-making.

## Future Enhancements
- Automate data cleaning using stored procedures.
- Integrate Python for advanced data preprocessing.
- Use BI tools like Power BI or Tableau for visualisation.

## Contributing
If you’d like to contribute, feel free to fork the repository and submit pull requests!

## Contact
For any questions or suggestions, reach out via khanyakolosa19@gmail.com.


