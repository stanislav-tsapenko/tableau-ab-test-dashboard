# AB Test Analysis & Statistical Evaluation

## 📋 Project Overview
This project focuses on evaluating the results of A/B tests to optimize e-commerce user conversion funnels. By combining statistical rigor with interactive data visualization, I identified which test variations led to statistically significant improvements in user behavior and identified "noise" in the data.

## 🛠 Tech Stack
- **Data Extraction & SQL:** Google BigQuery (analyzing large-scale e-commerce behavioral logs).
- **Data Processing & Statistics:** Python (Pandas for data transformation, Statsmodels for Z-test calculations).
- **Visualization:** Tableau Public (interactive dashboard for business stakeholders).

## 🔍 Analytical Approach
1. **Data Extraction:** Connected to BigQuery via Python API to retrieve and join user session logs with A/B test metadata.
2. **Statistical Testing:** Implemented Z-tests for proportions to compare conversion rates between Control (A) and Treatment (B) groups for four core metrics: `add_payment_info`, `add_shipping_info`, `begin_checkout`, and `new_account`.
3. **Significance Evaluation:** Applied a p-value threshold (p < 0.05) to distinguish between meaningful performance impacts and statistical fluctuations.
4. **Visualization:** Developed a multi-layered Tableau dashboard, allowing for detailed segmentation by device, channel, and geographic region.

## 📊 Key Insights
Four A/B tests, four funnel metrics each (16 comparisons), Z-test for proportions, α = 0.05. 6 of 16 comparisons are statistically significant:

- **Test 1 — clear improvement:** variant B is higher on `add_payment_info` (+0.55 pp, p = 0.00009), `add_shipping_info` (+0.44 pp, p = 0.009) and `begin_checkout` (+0.56 pp, p = 0.003).
- **Tests 3 and 4 — decline:** `begin_checkout` went down (−0.46 pp, p = 0.012 and −0.28 pp, p = 0.046); in test 4 `new_account` also went down (−0.29 pp, p = 0.018).
- **Test 2:** no significant differences.
- **Recommendation:** the change tested in test 1 is a candidate for rollout; changes in tests 3 and 4 should not be rolled out without further testing.
- **Caution:** four metrics per experiment were tested without a multiple-comparison correction, so results with p close to 0.05 should be treated carefully.

## 🔗 Project Links
- [View Interactive Tableau Dashboard](https://public.tableau.com/views/ABTestAnalysis_17504420018160/ABtest?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
- [Statistical analysis (Jupyter Notebook and results)](https://github.com/stanislav-tsapenko/ab-test-ecommerce-analysis)
- 
## 📸 Visualization
<img width="625" height="866" alt="image" src="https://github.com/user-attachments/assets/9a882c91-7e17-4cfd-9c49-5d70f8beb1ee" />

