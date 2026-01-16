# COVID-19 Impact on Passenger Traffic in Swiss Airports

This project analyzes the causal impact of the COVID-19 pandemic on passenger traffic in Swiss airports using Bayesian Structural Time Series models and Google’s `CausalImpact` package in R.

The analysis focuses on national airports and distinguishes between scheduled and charter flights to assess how different types of air traffic were affected.

---

## Project Overview

- **Time period:** January 2010 – June 2025 (monthly data)
- **Intervention:** March 2020 (start of COVID-19 travel restrictions)
- **Method:** Bayesian Structural Time Series (BSTS) via `CausalImpact`
- **Output:** Estimated pointwise and cumulative passenger losses attributable to COVID-19

---

## Data Source

Passenger data is sourced from the Swiss Federal Statistical Office (FSO) and includes:
- Airport
- Type of aviation (scheduled / charter)
- Monthly passenger counts

---

## Methodology (High Level)

The model is trained on pre-COVID data to learn long-term trends and seasonal patterns in passenger traffic. It then generates a counterfactual forecast representing expected passenger volumes in the absence of COVID-19.

The difference between observed and predicted values after March 2020 is interpreted as the causal impact of the pandemic.

Separate analyses are performed for scheduled and charter flights.

---

## Reproducibility

This project uses `renv` to ensure reproducible package versions.

After cloning the repository:

```r
install.packages("renv")
renv::restore()
