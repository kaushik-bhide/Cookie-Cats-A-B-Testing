# Cookie-Cats-A-B-Testing
## 🚀 Executive Summary
This project analyzes a 90,000+ player A/B test for a casual mobile game. The core objective was to evaluate the business and user engagement impact of moving the first in-game monetization paywall (gate) from Level 30 to Level 40. 

**The Business Verdict:** Delaying the paywall to Level 40 provided zero increase in daily engagement but caused a statistically significant drop in 7-Day Retention. Moving the gate would cost the business an estimated **$49,000 annually** in lost Lifetime Value (LTV). The recommendation is to halt the rollout and strictly keep the gate at Level 30.

---

## 📂 Strategic Documentation
*To view the product strategy behind this analysis, please read the [Experimentation PRD (Product Requirements Document)](PRD.md) attached to this repository.*

---

## 📊 The Business Problem
In free-to-play mobile games, "gates" act as forced pauses where players must either wait or make an in-app purchase to progress. 
* **Control Group:** Gate at Level 30.
* **Treatment Group:** Gate pushed back to Level 40.

The product hypothesis was that giving players a longer uninterrupted "honeymoon" phase (up to Level 40) would increase their overall engagement and keep them playing longer. 

---

## 🛠️ Methodology & Funnel Analysis
Instead of blindly applying basic averages, the dataset was rigorously tested for underlying assumptions, leading to a split testing strategy for continuous vs. categorical metrics.

1. **Top-of-Funnel (Engagement):** * Evaluated total game rounds played. The data was heavily right-skewed with extreme outliers (e.g., a "whale" playing 49,000+ rounds).
   * Applied **Welch’s T-Test** and the **Mann-Whitney U Test** to accommodate the non-parametric distribution.
   * *Result:* No statistically significant difference in total rounds played between the two gates (p = 0.75).
   
2. **Bottom-of-Funnel (Retention Leak):** * Mapped the user retention funnel from Install -> Day 1 -> Day 7.
   * Evaluated using the **Chi-Square Test of Independence**.
   * *Result:* Day 1 retention was unaffected, but the Funnel Analysis revealed a statistically significant leak at Day 7 (p = 0.0027).

---

## 💰 Revenue Impact Analysis
Statistical significance must translate to business value. To quantify the Day 7 retention leak, I conducted a revenue impact analysis using industry LTV benchmarks for casual puzzle games.

* **Absolute Retention Drop:** 0.82% (Retention fell from 19.02% to 18.20%).
* **Relative Drop:** 4.3% of the existing 7-day player base.

**Revenue Simulation:**
Assuming a conservative baseline of 100,000 new monthly downloads and a $5.00 Average Lifetime Value (LTV) for a retained player:
* **Monthly Players Lost:** ~820
* **Monthly Revenue Lost:** $4,100
* **Annual Revenue Impact:** **-$49,200**

---

## 📈 Key Visualizations
*(Note: Upload your Seaborn charts to your repository and replace these links)*

* **The Retention Funnel (Day 1 vs. Day 7):**
  ![Retention Funnel](retention_funnel.png)
* **Engagement Distribution (The Skew):**
  ![Engagement Skew](engagement_skew.png)

---

## 💻 Tech Stack & Workflow
* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Statistical Inference:** `scipy.stats` (Chi-Square, Mann-Whitney U, Welch's T-Test, Shapiro-Wilk)
* **Data Visualization:** `matplotlib`, `seaborn`
* **Workflow:** Led the statistical strategy and business analysis, leveraging LLMs (Gemini) as a coding copilot for rapid syntax generation and visualization formatting.

---

## 📁 Repository Structure & Data Sourcing
* `notebook.ipynb`: The complete end-to-end Jupyter Notebook containing the EDA, statistical testing, and business translations.
* `cookie_cats.csv`: The raw telemetry data (90,189 rows).
* `PRD.md`: The Experimentation Spec detailing the product strategy.

***Data Source Note:** This public dataset was originally provided by Tactile Entertainment and sourced via DataCamp/Kaggle.*
