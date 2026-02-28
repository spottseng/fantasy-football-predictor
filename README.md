# Fantasy Football Weekly Prediction Model (2024–2025)
## Overview

This was a one-evening experiment to build a machine learning model that predicts next-week fantasy football points using 2024 full-season data and 2025 data through October.

The problem was framed as a regression task:

> Given historical weekly player data, predict fantasy points for the following week.

---

## What the Model Did

- Loaded weekly player data  
- Created basic lag-based features from prior performance  
- Split into train/test sets  
- Trained a regression model  
- Generated next-week predictions  
- Evaluated using standard regression metrics  

Predictions were sorted to produce weekly rankings.

---

## Results

The model showed **limited predictive power**.

It captured general trends (good players tend to score more than bad players), but struggled where it matters:

- Predicting spike weeks  
- Identifying breakout games  
- Adjusting to role changes or injuries  
- Accurately ranking top performers  

In practice, it would not be reliable for competitive lineup decisions.

---

## Why This Is Not a Good Model

### 1. High Variance Domain  
Fantasy scoring is noisy and heavily influenced by touchdowns, game script, injuries, and matchup dynamics.

### 2. Weak Feature Set  
Key predictive signals were missing, including:
- Rolling usage trends  
- Red-zone opportunities  
- Opponent strength  
- Vegas totals  
- Injury status  

The model largely learned regression to the mean.

### 3. Suboptimal Objective  
Fantasy football is fundamentally a ranking problem, but the model optimized for point prediction (e.g., RMSE), not top-N accuracy.

### 4. Minimal Validation & Tuning  
No rolling time-series cross-validation, limited model experimentation, and no ensemble approaches.

---

## Takeaway

This is **not** a strong predictive model.

It is:
- A clean end-to-end ML pipeline  
- A functional proof of concept  
- A foundation for iteration  

With better features, proper time-aware validation, and a ranking-based objective, this could evolve into a competitive weekly forecasting system.