# Project Overview
The project explores Classification which is a fundamental task in supervised learning, where the goal is to assign predefined labels to new data based on patterns learned from a labeled dataset. This assignment involves building and evaluate different classification models to predict the grade of loans based on their features. It also analyze how the classification performance may differ between two datasets from before and after LendingClub’s 2015 controversy, which involved data integrity issues that could have impacted loan grading practices

# Contents
- [Data Source](https://github.com/Reena-Sajad/ML-Assignment-2/edit/main/README.md#data-source)
- [Folder Structure](https://github.com/Reena-Sajad/ML-Assignment-2/edit/main/README.md#folder-structure)
- [Objectives](https://github.com/Reena-Sajad/ML-Assignment-2/edit/main/README.md#objectives)
- [Tasks](https://github.com/Reena-Sajad/ML-Assignment-2/edit/main/README.md#tasks)
- [Contributors](https://github.com/Reena-Sajad/ML-Assignment-2/edit/main/README.md#contributors)
- [License](https://github.com/Reena-Sajad/ML-Assignment-2/edit/main/README.md#license)

# Data Source
- The raw dataset contains 100000 rows of data and 151 columns
-  It contains information about lenders, such as the `loan_amnt`, `grade`, `emp_length`, `home_ownership`, `annual_inc`, `verification_status`, `issue_d` etc.

# Folder Structure

    ├── data/
    │   ├── Dataset                 # Dataset
    │   ├── README.md               # Describes the data sources
    ├── tasks/
    │   ├── EDA                  # EDA 
    │   ├── PreProcessing        # Preprocessing 
    │   ├── Models/              # Different models 
    │   ├── Logistic Regression  # Logistic Regression
    │   ├── KNN                  # K Nearest Neighbor
    │   ├── SGD                  # Stochastic Gradient Descent 
    └── README.md                # This README file

# Objectives:
1. Perform EDA on the data set.
2. Do preprocessing.
3. Build 3 classification models.

# Tasks
* **EDA**: Perform EDA and find insights focusing on any differences between the
two time periods of concern (before and after the controversy).
* **Preprocessing**:
  * Standardize the numerical features and encode the categorical features
  * Identify and remove up to 1% of rows as outliers based on standardized `dti`, `annual
income`, and `delinq_2yrs` variables. Standardize the columns, add them up, and then identify outliers using IQR
method.
* **Classification Task**:
  * Split the data into Train-Validate-Test
  * Build a logistic model to accurately predict the High-Low response.
  * Build two KNN models predicting both responses (High-Low and High-Medium-Low)
  * Build two SGDClassifier models predicting both responses (High-Low and High-
Medium-Low)
  * Compare the accuracy of all final models (overall accuracy, precision, recall).

# Limitations
* **Correlation Analysis**: Handling of NaN values: We dropped the NaN values from the dataset assuming there is no significant difference in the data analysis. 
* **Price Analysis**:
1- **Data Skewness**: Pricey homes can totally mess up the average prices. The median's probably better for seeing what homes in a neighborhood actually go for. 
2- **Missing Key Variables**: The analysis skips over stuff like the season, the quality of the property, and amenities—things that all affect prices. It also does not look at occupancy rates. 
* **Neighborhood Comparison**:
1 - Missing Data: Some neighborhoods do not have review scores listed and hence were excluded from the analysis, which might result in an incomplete comparison. 
2 - Unequal Distribution: Some neighborhoods could have many listings while others may have fewer. The average rating thus may not accurately reflect guest experiences in neighborhoods with fewer listings. 
3 - Outliers: Since we do not capture extreme values, a few listings with very extreme ratings could influence the overall average of a neighborhood. 
* **Outlier Detection**:
1- Sensitivity of Methods: IQR and Z-score methods could flag legit cases, like luxury homes or long-term rentals, as outliers, especially if the data's a bit skewed. 
2- Over-simplification of Stay Durations: Places designed for longer stays could get wrongly flagged as outliers because of their minimum night stays. 
3- Static Data: The analysis does not consider price changes over time, meaning the outliers it detects might only be temporary. 
* **Text Length**: Blank Reviews: Some listing_id values did not have associated reviews. In the code, we handled this by excluding those rows, assuming their absence would not significantly impact the overall data analysis. Similarly for some listing_id there were no review score associated so we excluded those rows as well. 
* **Keyword Extraction**:
1 - Keyword Limitations: The selected keywords, although common, may not fully capture the entire scope of guest experiences. Additional keywords or specific vocabulary could enhance the analysis. 
2 - Keyword Context: The approach counts keyword occurrences without considering the context. For example, the word “clean” may appear in both positive and negative scenarios (e.g., not clean). More advanced techniques, like NLP, could be used to address this. 
3 - Review Availability: The availability of few or no reviews may not provide meaningful data for analysis, which can lead to incomplete insights for listings. 


# License
This project is licensed under the MIT License. Feel free to use, modify, and distribute as needed.
