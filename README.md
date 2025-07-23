# Demographics and Morality Survey Analysis 📊
This repository contains a data analysis project exploring the relationships between various demographic variables and responses to moral dilemmas. The project was part of my CMSC320: Introduction to Data Science course, and it is based on survey data collected from students at the University of Maryland.

## Project Overview

The core objective of this project was to investigate whether demographic factors (such as political ideology, religiousness, gender, age, and academic year) significantly correlate with how individuals respond to morally ambiguous scenarios. The project involved a comprehensive data cleaning process, feature engineering, statistical hypothesis testing (two-sample t-tests), and data visualization.

While no statistically significant relationships were found at an alpha level of $0.05$, the analysis revealed interesting trends, particularly concerning religiousness.

## Key Deliverables

* **`survey_analysis.ipynb`**: A Jupyter Notebook (Google Colab format) containing all the Python code for data loading, cleaning, transformation, exploratory data analysis, hypothesis testing, and visualization. This notebook provides a step-by-step walkthrough of the entire analysis.
* **`survey_analysis_report.pdf`**: A formal report detailing the introduction, background, methodology, findings, and conclusions of the study. This report summarizes the insights gained from the data analysis.

## Analysis Highlights

### Data Cleaning and Preprocessing

* **Data Consolidation:** Merged four similar survey datasets from Fall 2023, Spring 2024, and Spring 2025.
* **Typo Correction:** Addressed inconsistencies and typos in survey questions and demographic entries (e.g., "Famale" to "Female", "Sophmore" to "Sophomore").
* **Missing Value Imputation:** Handled missing demographic data by filling NaN values with appropriate placeholders.
* **Feature Engineering:**
    * Combined "Religiousness" and "Spirituality" variables into a unified "Relig" category after confirming their statistical similarity via a 2-sample Kolmogorov-Smirnov test (p-value = $0.994$).
    * Transformed categorical demographic variables (e.g., political ideology, gender, year, age) into binary or simplified categories for hypothesis testing.
    * Created a quantitative `avg_jerk_score` variable to represent participants' average response to moral dilemmas, ranging from 1 (Not a jerk) to 3 (Strongly a jerk). Rows with insufficient answered questions were filtered out to ensure data quality.

### Methodology

* **Exploratory Data Analysis:** Visualized the distribution of `avg_jerk_score` using histograms to understand its spread.
* **Hypothesis Testing:** Employed two-sample independent t-tests to compare the `avg_jerk_score` distributions across different demographic groups.
    * **Null Hypothesis ($H_0$):** The mean `avg_jerk_score` is equal across demographic categories.
    * **Alternative Hypothesis ($H_A$):** The mean `avg_jerk_score` differs (or is greater/less than, depending on the one-tailed test) across demographic categories.
    * **Significance Level ($\alpha$):** Primarily set at $0.05$.

### Key Findings

* **Religiousness:** The most notable difference in mean `avg_jerk_score` was observed between "At least somewhat religious" (mean: $1.812$) and "Not religious at all" (mean: $1.771$) participants. A one-tailed t-test yielded a p-value of $0.052$. While not statistically significant at $\alpha=0.05$, it approaches significance, suggesting a potential trend.
* **Other Demographics:** No other demographic variables (personal political ideology, parental political ideology, gender, age, academic year) showed a statistically significant correlation with `avg_jerk_score` at $\alpha=0.05$. P-values for these tests ranged from $0.093$ to $0.413$.

### Conclusion

This study rigorously analyzed the relationship between demographics and responses to moral dilemmas. Despite thorough data cleaning and statistical testing, no statistically significant correlations were found at the $\alpha=0.05$ level. The observed difference related to religiousness, while not meeting the strict $0.05$ threshold, warrants further investigation with larger datasets or different methodologies.

## Technologies Used

* **Python**
* **Pandas**: For data manipulation and cleaning.
* **Matplotlib**: For data visualization.
* **SciPy (stats)**: For statistical hypothesis testing.
* **Google Colab**: For interactive analysis and documentation.

## How to View the Project

1.  **Clone the Repository:**
    ```
    git clone https://github.com/arikgershman/survey-analysis-320.git
    cd survey-analysis-320
    ```
2.  **View the Notebook:** Open `survey_analysis.ipynb` directly on GitHub for a rendered view, or open it with Google Colab or Jupyter Lab/Notebook on your local machine to interact with the code.
3.  **Read the Report:** Open `survey_analysis_report.pdf` to read the detailed findings and conclusions.
