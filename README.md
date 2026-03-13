# Analysis of Graphene Electrode Properties in R 

##  Project Objective
The main goal of this project is to analyze experimental data regarding the properties of graphene electrodes. The project focuses on identifying the key physicochemical and configurational factors that have the greatest impact on the **specific capacitance** (`Capacitance (F/g)`) of the tested materials.

##  Key Findings
A machine learning model (XGBoost) was built and used for feature importance analysis (Explainable AI). The most important findings from the analysis are:
* **Key predictors:** `Potential Window (V)` and `Current Density (A/g)` have the greatest impact on specific capacitance. 
* **Impact of configuration:** The `Electrode Configuration` variable is also highly significant for the final performance of the electrode.
* **Lack of strong correlations:** The correlation matrix analysis showed no strong, direct linear relationships between the numerical variables in the dataset, which justifies the use of non-linear models (such as XGBoost).

##  Data Preprocessing
The original dataset underwent a rigorous cleaning process to ensure high model quality:
1. **Dimensionality reduction:** The dataset was reduced from the initial 21 columns and 925 rows to 12 columns and 921 rows.
2. **Handling missing data:** Columns with over 60% missing data (mainly atomic variables and publication links) and rows with more than 4 missing values were removed.
3. **Imputation:** * Missing numerical data was replaced with the **median**.
   * Missing categorical variables were labeled as `"Unknown"`.

##  Technologies & Libraries Used
The project was entirely developed in **R**, utilizing the R Markdown environment to generate a comprehensive HTML report.

* **Data processing:** `dplyr`, `tidyr`, `stringr`, `tibble`
* **Visualization:** `ggplot2`, `plotly` (interactive plots), `ggcorrplot`, `GGally`
* **Machine Learning & XAI:** `xgboost`, `caret`
* **Report formatting:** `knitr`, `kableExtra`

##  How to Run the Project Locally

1. Clone this repository to your local machine.
2. Ensure you have R and RStudio installed.
3. The data file (`data.csv`) should be located in the `data/` folder in the project's root directory.
4. Install the required libraries (if you don't have them already):
   ```R
   install.packages(c("dplyr", "tidyr", "stringr", "tibble", "ggplot2", "plotly", "GGally", "ggcorrplot", "knitr", "kableExtra
