# Unlocking Customer Insights: A Statistical Investigation

A statistical analysis of a US retail customer dataset — exploring spending behavior, demographic patterns, and engagement using Python, hypothesis testing, and data visualization.

## Business Problem

A mid-sized retail company has years of customer transaction data but no clear understanding of what drives spending and engagement across its customer base. This project applies descriptive statistics, exploratory data analysis, and formal hypothesis testing to answer five specific business questions and turn raw transaction data into actionable insight.

## Dataset

- **Source:** Synthetic customer dataset, 10,675 transaction-level rows across 1,000 unique US customers
- **Attributes:** Demographics (Age, Gender, Education, Marital Status, State), behavioral signals (Monthly Spend, Days Since Last Interaction, Pet Ownership)
- **Note:** Spend values follow a right-skewed Gamma distribution, intentionally mimicking real-world retail spending patterns where most customers spend moderately and a smaller group spends heavily.

## Methodology

The analysis follows a structured investigation pipeline:

1. **Data Understanding** — schema check, null inspection, and a key data-design decision: aggregating transaction-level rows into a customer-level table (1 row per customer) before running any test that assumes independent observations
2. **Descriptive Statistics** — central tendency and spread for spend, age, and engagement
3. **Visualization** — distribution plots, boxplots, and KDEs to surface shape and skew before testing
4. **Bivariate Analysis** — correlation matrix and grouped comparisons across demographic segments
5. **Hypothesis Testing** — five formal tests (t-test, ANOVA ×2, chi-square, Pearson correlation), each with explicit null/alternate hypotheses and assumption checks (normality, equal variance)
6. **Business Translation** — converting statistical results into specific, defensible recommendations

## Key Findings

| Question | Test | Result | Takeaway |
|---|---|---|---|
| Does gender affect spend? | Independent t-test | Not significant (p = 0.886) | Gender-targeted campaigns aren't justified by this data |
| Does education affect spend? | One-way ANOVA | Not significant (p = 0.697) | Spend doesn't vary meaningfully by education level |
| Is marital status linked to pet ownership? | Chi-square | **Significant** (p = 0.006) | Married customers show notably higher pet ownership — a real cross-sell signal |
| Are older customers less engaged? | Pearson correlation | Not significant (r ≈ 0) | Disengagement risk is evenly spread across age groups |
| Does spend vary by state? | One-way ANOVA | Not significant (p = 0.433) | Geographic personalization isn't supported by this dataset |

**Bigger picture:** of five demographic hypotheses tested, only one held up statistically. This is itself a useful finding — it shows that the "obvious" demographic splits don't explain spending behavior here, and the business should look beyond surface demographics for segmentation.

## Tools & Libraries

`Python` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `SciPy (stats)`

## Repository Structure

```
├── Customer_Insights_Statistical_Investigation.ipynb   # Full analysis notebook
├── US_Customer_Insights_Dataset.csv                    # Source dataset
└── README.md
```

## How to Run

1. Clone the repo
2. Install dependencies: `pip install pandas numpy matplotlib seaborn scipy jupyter`
3. Open `Customer_Insights_Statistical_Investigation.ipynb` in Jupyter and run all cells (update the file path in the first cell to match your local dataset location)

## Author

**Priya Sankar Mandal**
B.Tech, Electrical Engineering — Techno International New Town, Kolkata
