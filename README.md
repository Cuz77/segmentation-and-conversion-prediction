# Bertelsmann/Arvato customer segmentation and conversion



## Motivation

This project has been created as a part of the Nanodegree Data Scientist program. The project was driven by two primary questions: How does the company's customer base compare to the general population of Germany, and what is the conversion level for the target audience of the given marketing campaign? Addressing these questions required a comprehensive analysis of demographic data, with the ultimate goal of enhancing the company's marketing efforts through targeted customer segmentation and predictive modeling.

 An [article](https://medium.com/@belibels/data-science-approach-to-marketing-strategies-customer-segmentation-and-campaign-conversion-cfc08086b97a) has been posted on Medium to share the findings.



## Dependencies

Libraries used for this project:

- pandas
- matplotlib
- numpy
- sklearn for modeling, testing, and assesing
- xgb
- imblearn



## Summary

This project is a part of the Nanodegree Data Scientist program, focusing on analyzing a company's customer base in comparison to the general population of Germany and assessing the conversion level for a specific marketing campaign. The primary objective is to enhance marketing strategies through targeted customer segmentation and predictive modeling, utilizing demographic data.

The analysis is based on three data files, predominantly featuring numerical (continuous or ordinal) and some categorical variables. These variables encompass a wide range of factors, including demographic details, living conditions, political beliefs, economic status, and purchasing behaviors. The azdias dataset, being the most comprehensive, was used for initial data cleaning, with the process later applied to the other files.
The first part of the project involves data preparation, including handling mixed data types, redundant columns, and missing values. Six columns with mixed data types were identified, with decisions made to retain or transform certain columns based on their relevance to purchasing decisions or demographic significance. Features with less than 85% of values present were dropped, and rows with more than 6 missing values were excluded. Binary and numerical features were treated differently for missing value imputation and scaling.

In the second part, customer segmentation was approached with the aim of aiding predictions for a mailing campaign. Dimensionality reduction using PCA was performed, with 235 components explaining 95% of the variance selected for further analysis. K-means clustering was chosen for its simplicity and effectiveness, with 11 clusters identified as optimal based on the elbow method. The segmentation revealed that the company's traditional customer base is primarily focused on three segments.

The final part addresses predicting the response (conversion) rate, highlighting the challenge of dataset imbalance where the converted customer class is severely underrepresented. Strategies to mitigate this issue included resampling techniques, selecting appropriate evaluation metrics, and cost-sensitive training. Oversampling of the minority class was chosen to maintain a sufficient dataset size. The ROC AUC metric was selected for model evaluation, with the Gradient Boosting classifier identified as the most promising model after parameter tuning.



## Structure

The directory structure for this project looks like follows:

    boston_aribnb
    ├── dataset/
    ├── .gitignore
    ├── 1_data_analysis_and_cleaning.ipynb
    ├── 2_customer_segmentation.ipynb
    ├── 3_predictions.ipynb
    └── README.md

- **dataset** folder used for data storage in the development (not including source files in the repo due to t&cs limitations and Github storage limitations)
- **1_data_analysis_and_cleaning.ipynb** the file used to analyse and clean the dataset
- **2_customer_segmentation.ipynb** the file used to segment and compare populations
- **3_predictions.ipynb** the file with predictions of the conversion for the recipients of a marketing campaign
- **.gitignore** file used mostly to avoid uploading jupiter checkpoints and source data



## Dataset

The dataset consists of four csv filesfrom by Bertelsmann Arvato Analytics provided by Udacity:

1. Azdias file contains demographic data for the general population of Germany with almost 400 features and 900 K entries

2. Customers file contains data for existing customers and as such includes additional 3 columns describing the customer:
 - customer group
 - online purchase flag
 - product group

3. Mailout train file contains largely the same information but for targets of a marketing campaign

4. Mailout test is virtually same as above but for testing purposes only (lacking target label though since the competition is tested secretly)



## Acknowledgements

The data has been provided by Bertelsmann Arvato Analytics.

The image picturing a vintage printed catalog for ordering machine learning products on the top of the article has been generated by PlusOne, an AI developed by Prosus.
