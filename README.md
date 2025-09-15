# MMM Mediation Assessment

**Repository name suggestion:** `mmm-mediation-assessment`

Repository containing the `MMM_Mediation_Assessment.ipynb` notebook.  
This README embeds all plot images extracted from the notebook.

---

## Project Description

This project implements **MMM Modeling with a Mediation Assumption**.

### Context
- 2-year weekly dataset with media metrics, direct response levers (email/SMS), price, followers, promotions, and revenue.

### Task
- Build a machine learning model explaining **Revenue** as a function of inputs.  
- Treat **Google spend as mediator** between social/display (FB/TikTok/Snap) and revenue.  
- Deliver reproducible notebook, diagnostics, and recommendations.

### Delivery requirements
1. **Data prep**: handled seasonality, trend, zero-spend, scaling.  
2. **Modeling**: regularized regression, tree-based, Bayesian, with time-aware validation.  
3. **Causal framing**: Google spend as mediator, DAG-consistent features.  
4. **Diagnostics**: time CV, residual checks, sensitivity to price/promotions.  
5. **Insights**: defend drivers, note collinearity and mediation risks.

### Methodology
- **Feature engineering**: adstock transforms, lags, seasonality.  
- **Models**: Ridge/Lasso/ElasticNet, LightGBM, Bayesian MMM.  
- **Validation**: blocked time CV.  
- **Mediation**: Google spend modeled in two-stage regression.  
- **Diagnostics**: residuals, forecast stability, sensitivity analysis.

---

## Figures

### Figures 1–8 (Cell 7)
**Caption:** Revenue time-series visualization  
_Description_: Multiple time-series plots of **revenue vs. time** across 2 years. Each shows trend and seasonal patterns.  

```python
spend_cols = [c for c in df.columns if "spend" in c]
target = "revenue"
# revenue: time series plot
plt.figure(figsize=(12,4))
plt.plot(df.index, df[target], label="revenue", linewidth=2)
