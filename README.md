# Instagram Explore vs Hashtag Engagement Analysis

## Project Overview
This project analyzes Instagram post-level engagement data to understand what factors increase the likelihood that a post is distributed via the **Explore page** rather than primarily through **hashtag discovery**.

Rather than focusing on raw reach alone, the analysis emphasizes **engagement efficiency** and **deep interaction signals** such as saves, shares, and follows — behaviors more closely aligned with platform recommendation algorithms.

## Business Question
**What engagement behaviors increase the probability that an Instagram post is Explore-driven instead of hashtag-driven?**

Understanding this helps content creators and marketing teams optimize posts for algorithmic distribution rather than manual discovery.

## Data & Features
The dataset contains post-level metrics including:

- Impressions (total reach)
- Reach sources (Explore vs Hashtags)
- Engagement signals:
  - Likes
  - Comments
  - Shares
  - Saves
  - Follows
- Derived engagement-rate features (normalized by impressions)

A binary target variable was engineered to indicate whether a post was **Explore-driven** or **Hashtag-driven** based on relative reach contribution.

## Exploratory Analysis
Key exploratory findings include:

- Explore-driven posts tend to show higher **engagement efficiency**, not just higher raw impressions
- Saves and shares appear more strongly associated with Explore reach than likes alone
- Several high-impression outliers exhibit low engagement rates, reinforcing the importance of normalization

Visualizations include:
- Engagement Rate vs Impressions (colored by reach source)
- Bubble plots with bubble size representing follows gained

## Modeling Approach
A **logistic regression model** was selected as an interpretable baseline to estimate the probability that a post is Explore-driven.

**Why logistic regression?**
- Binary classification problem
- Interpretability of coefficients
- Strong baseline for probabilistic modeling

**Evaluation metric:**
- **ROC-AUC**, chosen due to class imbalance and focus on ranking performance rather than raw accuracy

## Results
- **ROC-AUC:** 0.76  
- Model performance significantly exceeded a naive baseline
- Engagement quality metrics (saves, shares, follow rate) were stronger predictors than likes alone

## Limitations
- Data is static and does not capture early engagement velocity
- Temporal dynamics (first-hour performance) are not available
- Results reflect correlation rather than causal effects

## Next Steps
With additional data, future iterations could include:
- Time-based engagement features
- Non-linear models (e.g., gradient boosting)
- Content-based features (caption length, posting time)

## Tools Used
- Python
- Pandas
- Matplotlib / Seaborn
- Scikit-learn

## Key Takeaway
Posts that generate **meaningful engagement signals** — especially saves and shares — are more likely to receive algorithmic distribution via Explore, even when controlling for total impressions.
