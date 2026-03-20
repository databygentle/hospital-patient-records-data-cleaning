Hospital Patient Records Data Cleaning

Overview:
This dataset contains hospital patient records where input variables are used to predict an outcome — length of stay of a patient for healthcare management efficiency purposes. The data was inspected for data quality issues and found issues like data type mismatch and few missing values, and no duplicates were found. The data quality issues have been resolved and the dataset is now ready for analysis.

Dataset:
The original source is Analytics Vidhya website but via Kaggle, with 318,438 rows and 18 columns. The features include Available Extra Rooms in Hospital — number of extra rooms available in the hospital, Type of Admission — admission type registered by the hospital, and Severity of Illness — severity of the illness recorded at the time of admission, to predict the label Stay — length of stay of a patient.

Objectives:
Assess the dataset for data quality issues — duplicates, missing values, data type mismatches
Detect and handle those issues and logically reason why those issues occurred
Fill in blank fields based on the distribution of each column and categorical columns
Validate by checking if all missing values were zero in all columns, duplicates were zero and data types matched

Tools & Libraries:
Python was the tool used in Anaconda Jupyter Notebook environment. The specific libraries used are pandas — for this healthcare dataset helps identify issues, address them and validate — and numpy for working with numbers and arrays faster.

Process Summary:
Imported the necessary Python libraries to clean the data
Loaded the dataset into Jupyter Notebook
Looked at the dataset to get an overview, understand the information it contains and reviewed its data dictionary to understand what each column means
Conducted data profiling to understand the dataset's structure, content and data types of each column
Ran the code to get the statistical summary of the dataset and understand the distribution of each column to determine its appropriate imputation method
Calculated the percentage of missing values in each column to identify the column with the most missing values
Checked if there were any duplicated rows in the dataset and found none
Used various imputation methods to fill in blank fields
Converted the data type of columns with mismatches to their appropriate data type
Verified the full dataset is clean and ready for analysis

Key Findings:
The following issues were identified — missing values were found but were low, no duplicates were found in the rows, and two data type mismatches were detected.
For missing values, the type of missingness was reasoned first:
City_Code_Patient — MNAR: not every place has a city code, patients may be living in rural areas
Stay — MAR: may depend on type of admission if emergency or trauma, and available extra rooms in the hospital
Bed Grade, patientid, and the rest — MCAR: truly random, small percentages, no clear pattern
Imputation methods applied:
Mean imputation for Bed Grade — normally distributed
Median imputation for patientid, City_Code_Patient and Visitors with Patient — all have outliers
Mode imputation for categorical columns — Type of Admission, Severity of Illness, Age and Stay
Bed Grade and City_Code_Patient had the wrong data type — float with decimal — and were converted to integer. City_Code_Patient had the highest percentage of missing values in the dataset.

How to Run:
Clone this repository or download the .ipynb file
Install the required libraries: pip install pandas numpy
Download the dataset from Kaggle: https://www.kaggle.com/datasets/nehaprabhavalkar/av-healthcare-analytics-ii
Place the dataset in the same folder as the notebook
Open Jupyter Notebook and run the cells in order
