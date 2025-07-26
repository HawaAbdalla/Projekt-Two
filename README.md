
# Analyze Anaconda Data – Multivariate Statistics Poster
----
This project is an R based statistical analysis of biological measurements from anacondas. The analysis investigates whether there is a significant difference between male and female anacondas using multivariate statistical methods. All key steps are performed in a single R Markdown script and summarized in a final poster.
----

## Data Preparation

We begin by loading the dataset `T6-19` from the `st514` package. The dataset includes length, weight, and gender for 56 anacondas. The columns are renamed for clarity, and the data is split into two groups based on gender: `anacondaMale` and `anacondaFemale`. Only the numeric variables (length and weight) are used in the analysis.


## Mean Vectors and Covariance Matrices

We calculate the mean vector and covariance matrix for each gender group. The mean vector gives us the average length and weight for male and female anacondas. The covariance matrix describes how the variables (length and weight) vary together.

- Female anacondas show higher variance in both length and weight.
- The covariance between length and weight is stronger for females, indicating a more consistent relationship.

This provides early evidence that the two groups may differ both in average values and in the way the variables relate.



## Visualization

We use a scatterplot to visualize the relationship between length and weight. Female anacondas are shown in magenta and males in dark blue.

- The plot shows a clear positive relationship between length and weight.
- This trend is stronger among female anacondas, supporting the findings from the covariance matrices.



## Test for Multivariate Normality

Before running any formal multivariate tests, we check whether the data follows a multivariate normal distribution.

- Mahalanobis distances are calculated for each individual in both groups.
- Q-Q plots are created, comparing these distances to a theoretical chi-squared distribution.
- The plots help assess whether the data aligns with the assumptions required for Hotelling’s T² test.

Both groups show reasonable alignment with the expected distribution, meaning the assumption of multivariate normality holds well enough for further analysis.


## Hotelling’s T² Test

This test evaluates whether there is a significant difference between the mean vectors (length and weight) of the male and female groups.

- The test considers both variables at once and produces a test statistic and a p-value.
- A low p-value indicates that the groups are significantly different.

**Result:**
- Test statistic: 7.96  
- p-value: 0.0009

This result shows a statistically significant difference between male and female anacondas in terms of body size.


## Box’s M Test

To assess whether the covariance structures** (how length and weight vary together) are equal between the two groups, we use Box’s M test.

- A low p-value would indicate significantly different covariance matrices.

**Result:**
- p-value: 0.059

Since this value is slightly above 0.05, we do not reject the null hypothesis. However, it is close enough that some caution should be used in assuming the groups have equal covariance.


## Conclusion

This project uses multivariate statistical methods to explore gender differences in anacondas.

- Female anacondas are generally larger and more variable in size.
- There is a stronger correlation between length and weight in females.
- Hotelling’s T² test confirms a significant difference between the groups.
- Box’s M test suggests the covariance structures may be similar, but not conclusively so.

All steps and results are presented in the final poster: `poster1.pdf`.
