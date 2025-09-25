# House Price Prediction Analysis
The housing market is the system through which homes are bought, sold, and rented, and it plays a central role in both individual lives and the overall economy. It affects homebuyers, sellers, real estate agents, developers, financial institutions, and even governments that rely on housing data for policy and planning.
House prices are influenced by a wide range of factors such as location, property size, number of bedrooms and bathrooms, and neighbourhood amenities. Understanding these drivers is critical for making informed decisions, whether you are an investor seeking profitable opportunities, a financial institution assessing mortgage risk, or a policymaker monitoring housing affordability.

### Table of Contents
 * Dataset
 * Data preparation
 * Methods
 * Tools & Technologies
 * Key Insights
 * Limitations
 * Key Findings & Insights
 * How to Use
 * Screenshots
 * Future Work

### Dataset
Dataset 545 records with the following features:
price,area, bedroom, bathroom, stories, mainroad, guestroom, basement, hotwaterheating, airconditioning, parking, perfarea, furnishingstatus.

### Data cleaning and Prepartions Steps 
 * Imported dataset into Power BI (545 records).
 * Verified datatypes for numeric and categorical features.
 * Check for missing data across all features (validated in the dashboard). 
  
Method 
  * Exploratory Data Analysis (EDA)
    * Conducted summary statistics and distribution checks
    * Visualizing trends, correlations(Pearson correlation for numeric feature and AVOVA for categorical variables and multicollinearity analysis
 * Modeling Approaches:
    * Applied log transformation to right-skewed numerical variables to normalize.
    * Performed Outlier analysis (before and after transformation).
    * Linear Regression
    * Multiple linear regression
    * Model evaluation using RMSE, MAE, R²
      
### Tools & Technologies
  * Power BI → Data import, transformation, dashboarding.
  * R → Statistical analysis (correlation, ANOVA, regression modeling).

### Key Model Insights

Simple Linear Regression: logPrice ~ logArea
* R = 0.58, R² = 0.34, p < 2.5E-50.
* ~34% of variance in logPrice explained by logArea.

Multiple Regression: 
* Adjusted R² = 0.704.
* MAPE = 16% → predictions ~16% off actual values.
* Error rate in 10–20% range → moderately strong performance.

### Limitations
Multicollinearity
Predictors like bedroom and furnishing show moderate pairwise correlations (r ≈ 0.51–0.64).
VIF values > 5 suggest partial multicollinearity → reduces interpretability but overall reliability unaffected.

Other Limitations
Imbalanced categories in categorical variables reduce accuracy for minority classes.
Omitted real-world factors: neighborhood quality, property age, amenities, market timing.
Model uncertainty higher for luxury homes (>10M) → suggests need for expert appraisal.

### Key Findings & Insights

* Primary Market Insights
  * Property size (area + bedrooms) is the strongest predictor of price.
  * Explains ~70% of variation across the dataset.
  * Larger homes consistently command higher market value.

* Pricing Patterns for Decision-Making
  * Homes near main roads sell for ~$1.6M more on average (5.0M vs 3.4M).
  * Furnishing status creates ~$1.5M difference (unfurnished ~4.0M vs furnished ~5.5M).

* Provides actionable benchmarks for buyers, sellers, and investors.
  * Investment & Valuation Implications
    * Model predicts within ~$735K accuracy for typical properties.
    * Undervalues luxury homes → prestige, exclusivity, and unique features not captured by size.
    * Use caution when applying model to high-end properties.
  * Technical Limitation with Business Impact
    * Area and Bedrooms overlap strongly (confirmed by PCA loadings on PC1).
    * Incremental effect of bedrooms alone is misleading.
    * Investors should focus on total property size rather than bedroom count in isolation.

5. How to Reproduce

Follow the steps below to reproduce the analysis and dashboard:

### Requirements

* Power BI Desktop (latest version)
* R (≥ 4.0.0) installed locally
* R libraries: install.packages(c("dplyr", "ggplot2", "car", "stats"))

### Steps
* Open the .pbix file in Power BI Desktop.
* Connect the dataset (CSV/Excel file provided in the repo).
* Ensure R is enabled in Power BI (File > Options > R scripting).
* Run the R scripts included for correlation, ANOVA, and regression modeling.
* Explore the dashboard:
* Outlier analysis
* Correlation heatmap
* Regression results
* Distribution plots

### Screenshots
<img width="774" height="437" alt="image" src="https://github.com/user-attachments/assets/c747032d-cb76-4c68-9a6b-7381b230826b" />
<img width="787" height="448" alt="image" src="https://github.com/user-attachments/assets/f8725936-4548-493b-9db2-6dc8a39da0ff" />

### Future Work
* Add more advanced machine learning models
* Incorporate external economic indicators (interest rates, inflation)
* Include real-world factors: neighborhood quality,location, property age, amenities, market timing
* Deploy interactive web dashboards


