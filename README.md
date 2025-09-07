# Wine Types & Quality Analysis

This project analyzes the Wine Quality dataset from the UCI Repository to answer questions about wine classification and the relationship between alcohol content and quality.

## Contributors

martelli.2108093@studenti.uniroma1.it - Flavio Martelli • sevinc.2109191@studenti.uniroma1.it - Özberk Sevinç • oral.2122393@studenti.uniroma1.it - Çağan Oral

## Research Questions

1.  Do wines form distinct groups based on their chemical makeup alone, beyond just red and white?
2.  Is there a relationship between the quality of a wine and its alcohol percentage?

## The Dataset

*   **Source:** UCI Machine Learning Repository - Wine Tasting Dataset
*   **Samples:** 6497
*   **Composition:** 75% white wine, 25% red wine
*   **Data Quality:** No missing values

### Features

The dataset includes the following 11 chemical features:
- Fixed Acidity
- Volatile Acidity
- Citric Acid
- Residual Sugar
- Chlorides
- Free SO2
- Total SO2
- Density
- pH
- Sulphates
- Alcohol

## Analysis and Findings

### Data Exploration

Initial analysis shows that wine quality ratings range from 3 to 9, with the majority of ratings concentrated around the mean, following an approximately normal distribution.

### Clustering

To determine if wines form natural groups based on their chemical properties, K-Means clustering was applied. The optimal number of clusters was found to be 3 using the elbow method. The features were standardized before clustering to account for different scales and units.

The three clusters were interpreted as:
*   **Cluster 1: Sour** (Highest in fixed acidity)
*   **Cluster 2: Sweet/Low Alcohol** (Highest in residual sugar)
*   **Cluster 3: Dry** (Highest in alcohol)

### Alcohol Percentage vs. Quality

A one-way ANOVA test was conducted to examine the relationship between alcohol percentage and wine quality.

*   **ANOVA Result:** F-statistic = 384.48, p-value < 0.01. This indicates a statistically significant relationship.
*   **Tukey's HSD Test:** A post-hoc Tukey's HSD test was performed, which showed significant differences in mean alcohol content between various quality groups.

## Conclusions

1.  The analysis successfully identified three distinct types of wine based on their chemical properties, which we labeled as "Sour," "Sweet/Low Alcohol," and "Dry."
2.  The hypothesis was confirmed: a wine's alcohol percentage is significantly related to its quality rating.

## Visualizations in this Repository

*   `wine_quality_distribution.png`: Histogram of wine quality ratings.
*   `elbow_method.png`: Elbow method plot for determining the optimal number of clusters.
*   `boxplot_alcohol_by_quality_group.png`: Box plot showing alcohol content across different wine quality groups.
*   `correlation_matrix_orig.png`: Correlation matrix of the features.
*   `alcohol_histograms_by_quality_group.png`: Histograms of alcohol content for each quality group.
*   `tukey_hsd_matrix.png`: Matrix visualization of Tukey's HSD results.
