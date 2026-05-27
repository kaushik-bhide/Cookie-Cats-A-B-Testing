# 📄 Experimentation Spec: First Paywall Placement

## 1. Problem Statement
* **What is happening:** Currently, players hit their first forced wait-time (gate) at Level 30. 
* **The Business Pain:** We suspect that hitting a paywall this early might cause frustration, leading to high early-churn rates and lower overall engagement.

---

## 2. Hypothesis
> **IF** we delay the first gate from Level 30 to Level 40...
> **THEN** players will experience a longer uninterrupted gaming experience, which will increase their total rounds played and improve both Day 1 and Day 7 retention.

---

## 3. Metrics for Success
* **Primary Metric:** Day 7 Retention *(Are we building long-term habits?)*
* **Secondary Metric:** Day 1 Retention *(Does this impact immediate drop-off?)*
* **Guardrail Metric:** Total Gamerounds *(Are we accidentally decreasing overall engagement by changing the Gate Level?)*

---

## 4. Experiment Design & Scope
* **Audience:** 100% of new players who install the game during the 14-day test period.
* **Traffic Allocation:** A 49/51 randomized split.
    * **Control (A):** Gate remains at Level 30.
    * **Treatment (B):** Gate moved to Level 40.
* **Duration:** The test will run until we achieve a minimum sample size of ~90,000 users to ensure statistical power.

---

## 5. Rollout Strategy (The "What Ifs")
1. **Scenario 1: Treatment Wins.** If Level 40 shows a statistically significant increase in Day 7 retention without hurting revenue, we roll out to 100% of users.
2. **Scenario 2: Treatment Loses (Actual Result).** If Level 40 decreases retention or engagement, we kill the experiment and keep the gate at Level 30.
3. **Scenario 3: Neutral.** If there is no statistical difference, we keep the gate at Level 30 to minimize engineering debt and product complexity.
