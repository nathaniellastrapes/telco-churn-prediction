# Business Framing: SaaS Customer Churn Prediction

**Project:** Telco Customer Churn Prediction  
**Author:** Nathaniel Lastrapes
**Date:** March 2026  
**Stage:** 1 of 5 — Business Problem Framing

---

## Problem Statement

As VP of Customer Success, retaining existing customers is my highest-leverage responsibility — acquiring a new customer costs 5–7x more than retaining one, and every churned account represents lost lifetime value that is difficult to recover. Today, my team operates reactively: we learn a customer is leaving only after they have decided to go. With a retention team that can meaningfully engage only a limited number of at-risk accounts each week, I cannot afford to spray outreach broadly and hope for the best. What I need is a ranked list of the customers most likely to churn — so my team's finite capacity is focused on the accounts where intervention will have the highest impact. The right question isn't "who might churn?" — it's "given that we can only make *k* calls this week, which customers should be at the top of that list?"

---

## Business Objective

Proactively identify and prioritize customers at highest risk of churning so that a capacity-constrained retention team can direct outreach toward the accounts where intervention will generate the greatest return in saved lifetime value.

---

## Key Metric: Precision@k

Because the retention team can only contact a fixed number of customers per week, the model's primary job is to ensure that the top *k* flagged accounts are as likely to churn as possible. Standard metrics like AUC or accuracy optimize for performance across all customers — Precision@k optimizes for the decision that actually matters: **who do we call on Monday morning?**

- **Primary metric:** Precision@k (k to be defined in Stage 5 based on team capacity assumptions)
- **Secondary metrics:** AUC-ROC, recall (to monitor coverage), F1

---

## Success Criteria

| Criterion | Definition |
|---|---|
| Business clarity | Model output translates directly into a prioritized call list |
| Precision@k | Top-k predictions are meaningfully more accurate than random selection |
| Interpretability | Key churn drivers are explainable to a non-technical VP |
| ROI framing | Stage 5 recommendation quantifies estimated revenue saved vs. cost of retention program |

---

## Assumptions & Constraints

- Retention team capacity (*k*) is finite and will be defined concretely in Stage 5
- Customer lifetime value (LTV) is used to frame business savings — specific LTV estimates to be derived from dataset in Stage 5
- Dataset: IBM Telco Customer Churn (Kaggle) — treated as a SaaS/subscription business analog
- This is a batch prediction use case (weekly scored list), not real-time inference

---

## Stages Overview

| Stage | Focus | Timeline |
|---|---|---|
| 1 | Business problem framing *(this document)* | Week 1 |
| 2 | Opinionated EDA — every chart answers a business question | Week 1–2 |
| 3 | Feature engineering & preprocessing | Week 2 |
| 4 | Modeling — logistic regression, Random Forest, XGBoost | Week 3–4 |
| 5 | Business recommendation with estimated ROI | Week 5 |

---

*This document is a living artifact. Update assumptions and success criteria as the project evolves.*