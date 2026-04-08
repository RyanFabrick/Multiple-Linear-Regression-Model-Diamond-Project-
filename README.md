# Diamond Price Prediction Project

This is a regression analysis project predicting diamond prices using a dataset of 53,943 observations from Kaggle. This project builds and evaluates linear regression models to predict diamond prices using carat, cut, color, clarity, and physical dimensions. It covers descriptive statistics, simple linear regression, log-log transformation, model selection, and multicollinearity diagnostics.

## Table of Contents

- [Why Did I Build This?](#why-did-i-build-this)
- [Results](#results)
- [Outline & Analysis](#outline--analysis)
- [Rendered PDF](#rendered-pdf)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)
- [Acknowledgements & References](#acknowledgements--references)

## Why Did I Build This?

I built this for a Linear Regression upper division elective course during my third year at UCSB as a Statistics and Data Science major. This was a final project assignment and received full credit for code accuracy, code justifications, result interpretations, and overall analysis. This course specifically dove in depth on the mathematical theory and proofs behind different linear regression models. The coding portion for this course was taught in R, thus I completed the project in R.

## Results

| Model | Adjusted R² |
|---|---|
| SLR: `price ~ carat` | 0.8563 |
| Log-Log SLR: `log(price) ~ log(carat)` | 0.9372 |
| Full MLR (all variables) | 0.9833 |
| Final Model (log_carat + cut + color + clarity) | 0.9829 |

**Final Prediction** — 0.7 carat, Ideal cut, G color, VS2 clarity:
- Fitted price: $2,777.41
- 95% CI: ($2,727.04, $2,828.71)
- 95% PI: ($2,140.57, $3,603.72)

## Outline & Analysis

For more in depth explanations, code, reasoning, thought process, justification, and analysis, go to the [main file](main.rmd). For a brief outline and analysis look below. And for full rendered PDF report, scroll down or [click here](Rendered%20PDF.pdf).

### Part 1 — Data Description
- Random sample of 2,000 diamonds from the full dataset
- Histograms for continuous variables (carat, depth, table, price, x, y, z)
- Bar plots for categorical variables (cut, color, clarity)
- Correlation matrix revealing strong carat price correlation (r = 0.93) and multicollinearity among x, y, z

### Part 2 — Simple Linear Regression
- Baseline SLR: price ~ carat
- Assumption diagnostics (residuals vs. fitted, QQ plot, Scale-Location, leverage)
- Log-log transformation to resolve non-linearity and heteroscedasticity
- Sequential variable addition tracking adjusted R² improvement

### Part 3 — Multiple Linear Regression
- Backward AIC, Backward BIC, and Stepwise AIC model selection
- VIF diagnostics (x: 673.23, y: 668.20 — severe multicollinearity confirmed)
- Final model removes x, y, z; all VIF values below 1.15

## Rendered PDF

To view the rendered PDF from the [main file](main.RMD) that is produced, [click here](Rendered%20PDF.pdf).

## Dependencies

```r
library(ggplot2)
library(GGally)
library(dplyr)
library(patchwork)
library(corrplot)
library(car)
```

## License

**© 2026 Ryan Fabrick. All rights reserved. This project may not be reused, adapted, or submitted for academic coursework without explicit written permission from the author.**

## Author

**Ryan Fabrick**
- Statistics and Data Science (B.S) Student, University of California Santa Barbara
- GitHub: [https://github.com/RyanFabrick](https://github.com/RyanFabrick)
- LinkedIn: [www.linkedin.com/in/ryan-fabrick](https://www.linkedin.com/in/ryan-fabrick)
- Email: ryanfabrick@gmail.com

## Acknowledgements & References

- **[Kaggle Dataset](https://www.kaggle.com/datasets/nancyalaswad90/diamonds-prices)** — Diamonds Prices 2022, the source dataset containing 53,943 diamond observations with price, carat, cut, color, clarity, and physical dimension attributes
- **[R Project](https://www.r-project.org/)** — The statistical computing language used to build, evaluate, and visualize all regression models in this project
- **[R Markdown](https://rmarkdown.rstudio.com/)** — The authoring framework used to combine R code, output, and written analysis into a single reproducible PDF report
- **[ggplot2](https://ggplot2.tidyverse.org/)** — Tidyverse package used for all data visualizations including histograms, bar plots, and scatter plots
- **[corrplot](https://cran.r-project.org/web/packages/corrplot/)** — R package used to generate the correlation matrix heatmap for visualizing relationships between numerical variables
- **[car](https://cran.r-project.org/web/packages/car/)** — R package used for Variance Inflation Factor (VIF) diagnostics to detect and address multicollinearity

________________________________________________
Built with ❤️ for UCSB

This project demonstrates my interest in machine learning, predictive modeling, and statistics. It received full credit for an undergraduate course in Linear Regression Models.