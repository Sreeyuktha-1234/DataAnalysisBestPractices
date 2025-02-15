"This project is focused on learning and applying various data analysis techniques to develop best practices in the field."

In the **Data Wrangling** process, I have demonstrated multiple techniques to handle missing values based on their data types:

1. **Handling Missing Values in Birthdate Column:**  
   - The missing values in the `Birthdate` column are filled with the most frequently occurring birthdate (mode).  
   - This ensures that missing values are replaced with a realistic and commonly observed value in the dataset.

2. **Handling Missing Values in Last Seen Column:**  
   - The `Last Seen` column, which contains datetime values, is first converted into a proper datetime format using `pd.to_datetime()`.  
   - Any errors during conversion are coerced into `NaT` (Not a Time).  
   - The median of the `Last Seen` column is then computed and used to replace missing values.  
   - This approach helps maintain the chronological integrity of the dataset.

3. **Handling Missing Values in Categorical Columns (City & State):**  
   - Missing values in the `City` and `State` columns are replaced with the most frequently occurring value (mode) in their respective columns.  
   - This ensures that the most common category fills in the missing entries, preserving categorical consistency.

4. **Handling Missing Values in the Zip Column Using KNN Imputation:**  
   - The `Zip` column, which contains numerical values, is first converted into a numeric format using `pd.to_numeric()`, ensuring that any non-numeric values are coerced into `NaN`.  
   - A **K-Nearest Neighbors (KNN) Imputer** with `n_neighbors=5` is then applied to estimate and fill the missing values based on the similarity of nearby data points.  
   - This technique leverages patterns in the dataset to provide more accurate imputations compared to simple statistical methods.

By implementing these strategies, the dataset is effectively cleaned, ensuring minimal data loss while maintaining the integrity of the information.
