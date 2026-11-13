# 📰 NewsSphere: Landing Page Performance & User Engagement Analysis

An A/B test analysis to find out whether NewsSphere's redesigned landing page actually brings in more subscribers than the old one.

## 📌 Business Problem

NewsSphere, an online news portal, saw a decline in new monthly subscribers compared to last year. Leadership suspected the existing landing page wasn't engaging enough to push visitors toward subscribing. The design team built a new page with a better layout and more relevant content, and the Data Science team ran an experiment to test it.

**Experiment setup:** 100 randomly selected users split equally into two groups.
- **Control (50 users):** saw the old landing page
- **Treatment (50 users):** saw the new landing page

All tests use a **5% significance level**.

## ❓ Questions Answered

1. Do users spend more time on the new landing page than on the old one?
2. Is the conversion rate higher for the new page than for the old page?
3. Are conversion and preferred language independent or related?
4. Is the time spent on the new page the same across different language users?

## 🗂️ Dataset

| Column | Description |
|---|---|
| `user_id` | Unique ID of the user |
| `group` | Control or treatment |
| `landing_page` | Old or new |
| `time_spent_on_the_page` | Time spent on the page (minutes) |
| `converted` | Whether the user became a subscriber |
| `language_preferred` | Language chosen to view the page (English, French, Spanish) |

100 rows, 6 columns, no missing values, no duplicate users.

## 🛠️ Tech Stack

- **Python**: pandas, NumPy
- **Visualization**: Matplotlib, Seaborn
- **Statistics**: SciPy, statsmodels
- **Environment**: Jupyter Notebook

## 🔍 Approach

1. **Data overview and cleaning:** checked shape, data types, missing values and duplicates
2. **EDA:** univariate and bivariate analysis of time spent, conversion and language
3. **Hypothesis testing:** a structured 7-step process for each question, from defining hypotheses to drawing the inference
4. **Assumption checks:** Shapiro-Wilk for normality and Levene's test for equal variances before running ANOVA

## 📊 Statistical Tests and Results

| # | Question | Test | p-value | Decision |
|---|---|---|---|---|
| 1 | Time spent: new vs old page | Welch's two-sample t-test (one-tailed) | 0.0001 | Reject H₀ |
| 2 | Conversion rate: new vs old page | Two-sample proportion z-test (one-tailed) | 0.008 | Reject H₀ |
| 3 | Conversion vs preferred language | Chi-square test of independence | 0.213 | Fail to reject H₀ |
| 4 | Time spent on new page across languages | One-way ANOVA | 0.432 | Fail to reject H₀ |

**Assumption checks for the ANOVA:** Shapiro-Wilk p = 0.804 (normality holds), Levene's p = 0.467 (equal variances hold).

## 💡 Key Findings

- **Users engage more with the new page.** The difference in time spent is statistically significant (p = 0.0001).
- **The new page converts better.** 66% of users converted on the new page (33 of 50) versus 42% on the old page (21 of 50), and the difference is significant (p = 0.008).
- **Language doesn't drive conversion.** There's no evidence that conversion depends on preferred language.
- **The new page works across languages.** Time spent doesn't differ meaningfully between English, French and Spanish users.

## ✅ Recommendation

Roll out the new landing page. It keeps visitors on the page longer and converts a significantly larger share of them into subscribers, and that holds across all language groups.

## ⚠️ Limitations

- The sample is small (100 users), so results should be validated on a larger test before full rollout.
- Failing to reject H₀ for language doesn't prove language has no effect, only that this dataset doesn't show one.

## 📁 Repository Structure

```
├── NewsSphere_Landing_Page_Performance___User_Engagement_Analysis.ipynb
├── NewsSphere_data.csv
└── README.md
```

## 👤 Author

**Karan**
[LinkedIn](https://www.linkedin.com/in/karanmeher/) · [GitHub](https://github.com/karan-meher)
