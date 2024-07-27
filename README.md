# Data Cleaning and Analysis of Application Data

## Introduction
This project involves the cleaning and analysis of a dataset called `application_data.csv`, which contains information on loan applications. The goal is to clean the data by handling missing values, removing unwanted columns, and exploring various features through visualizations.

## Importing Libraries
Necessary libraries like `numpy`, `pandas`, `matplotlib`, `seaborn`, and `warnings` are imported to handle data manipulation, visualization, and suppressing warnings.

## Data Loading
The application data is read into a DataFrame using `pd.read_csv("application_data.csv")`.

## Initial Data Exploration
- **Shape**: The initial number of rows and columns is checked using `df.shape`.
- **Info**: Detailed information about the DataFrame is obtained using `df.info('all')`.
- **Null Values**: The percentage of missing values in each column is calculated.

## Handling Missing Values
- **Dropping Columns with >40% Missing Values**: Columns with more than 40% missing values are dropped.
- **Null Values Verification**: The percentage of missing values is checked again after dropping columns.

## Column-Specific Missing Values Treatment
- **AMT_ANNUITY**: Missing values are filled with the median value.
- **Rows with >40% Missing Values**: Rows having more than 40% missing values are dropped.
- **Unwanted Columns**: Several columns deemed unnecessary are dropped from the dataset.

## Handling 'XNA' Values
- **CODE_GENDER**: Rows with 'XNA' values are updated to 'F' based on the majority value.
- **ORGANIZATION_TYPE**: Rows with 'XNA' values are dropped.

## Data Type Conversion
Numeric columns are converted to the appropriate data types using `pd.to_numeric`.

## Binning Income and Credit Amounts
- **AMT_INCOME_TOTAL**: Binned into various ranges for better analysis.
- **AMT_CREDIT**: Binned into various ranges for better analysis.

## Dataset Splitting
The dataset is split into two based on the `TARGET` column:
- `target0_df`: Clients without payment difficulties.
- `target1_df`: Clients with payment difficulties.

## Imbalance Calculation
The imbalance ratio between the majority (`target0_df`) and minority (`target1_df`) classes is calculated.

## Visualization
Several visualizations are created to understand the distribution of various features:
- **Income Range Distribution**: Plotted by `CODE_GENDER`.
- **Income Type Distribution**: Plotted by `CODE_GENDER`.
- **Contract Type Distribution**: Plotted by `CODE_GENDER`.
- **Organization Type Distribution**: Plotted on a logarithmic scale.

## Correlation Analysis
Correlation matrices are computed for both target classes and visualized using heatmaps.

## Outlier Detection
Box plots are used to detect outliers in various features:
- **Income Amount**: Distribution visualized for `target0_df`.
- **Credit Amount**: Distribution visualized for both `target0_df` and `target1_df`.
- **Annuity Amount**: Distribution visualized for both `target0_df` and `target1_df`.

## Additional Visualizations
- **Credit Amount vs Education Status**: Visualized using box plots.
- **Income Amount vs Education Status**: Visualized using box plots.

## Previous Application Data
- **Data Loading**: Previous application data is read into `df1`.
- **Missing Data Handling**: Columns with more than 40% missing values are dropped.
- **'XNA' and 'XAP' Values**: Rows with these values are removed.
- **Data Merging**: The cleaned previous application data is merged with the application data.
- **Column Renaming**: Columns are renamed for better understanding.

## Visualization of Merged Data
- **Contract Status Distribution**: Visualized with purposes.
- **Purposes Distribution by Target**: Visualized with a count plot.
- **Credit Amount vs Loan Purpose**: Visualized using box plots.
- **Credit Amount vs Housing Type**: Visualized using bar plots.

## Conclusion
The data cleaning and analysis process involves handling missing values, updating specific columns, binning continuous variables, splitting the dataset, visualizing distributions, and merging with previous application data. This comprehensive approach ensures a clean dataset for further analysis and modeling.
