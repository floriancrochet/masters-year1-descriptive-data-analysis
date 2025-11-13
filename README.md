# Data Analysis of French Departments  
*A statistical and econometric exploration of socioeconomic disparities across French departments.*

---

## 📘 Overview
This project analyzes **economic, social, and environmental factors** influencing the **average annual income** of French departments.  
It was developed as part of the **Master 1 in Econometrics and Statistics (Applied Econometrics track)** at the University of Nantes.

**Objectives**
- Study regional income disparities using socioeconomic and demographic indicators  
- Identify the main variables affecting income distribution  
- Apply descriptive statistics, Principal Component Analysis (PCA), and multiple linear regression  
- Provide interpretable, reproducible, and visually supported results  

---

## ⚙️ Features
- Comprehensive **descriptive statistics** (univariate, bivariate, multivariate)  
- **Visualization** of distributions, correlations, and categorical dependencies  
- **Normality and independence tests** (Shapiro–Wilk, Chi-squared, Wilcoxon–Mann–Whitney)  
- **Principal Component Analysis (PCA)** with eigenvalue selection and correlation circles  
- **Multiple linear regression** to quantify determinants of income disparities  

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:** tidyverse, FactoMineR, factoextra, corrplot, PerformanceAnalytics, sjPlot, lmtest, EnvStats, AER, MASS, car  

---

## ⚙️ Installation
To run the project locally:

```bash
git clone https://github.com/<your-username>/french-departments-data-analysis.git
cd french-departments-data-analysis
Rscript -e "install.packages(c('tidyverse','FactoMineR','factoextra','corrplot','PerformanceAnalytics','sjPlot','lmtest','EnvStats','AER','MASS','car','openxlsx','gridExtra','outliers','reshape2'))"
```

---

## 📚 Usage Example

```r
# Load data
base <- read.xlsx("data/french_departments_socioeconomic_data.xlsx", startRow = 2, colNames = TRUE, rowNames = TRUE)

# Run PCA
library(FactoMineR)
ACP1 <- PCA(base[, c("revenu", "population", "chomage", "pib", "esperance",
                     "natalite", "mortalite", "education", "voiture", "social", "surface")],
            scale.unit = TRUE, graph = FALSE)

# Visualize results
library(factoextra)
fviz_pca_var(ACP1, axes = c(1,2), col.var = "cos2", gradient.cols = c("skyblue", "red"))
```

---

## 📂 Project Structure

```
data-analysis/
│
├── data/               # French departments socioeconomic dataset
├── src/                # R scripts for analysis (code add.Rmd)
├── outputs/            # Generated figures and tables
├── report/             # Final report (PDF)
├── requirements.R      # List of required packages
└── README.md
```

---

## 📊 Results
The analysis highlights key insights:

- **PCA Results:** Four main components explain ~52% of total variance.  
  - Axis 1: demographic dynamics (natality, mortality)  
  - Axis 2: quality of life (surface, life expectancy, unemployment, car ownership)  
  - Axis 3: economic concentration (GDP, population)  
  - Axis 4: socioeconomic imbalance (income vs. education)

- **Regression Findings:** GDP, population, and green surface per inhabitant significantly affect income; mortality and metropolitan presence are also key explanatory factors.

Example visualization:

![PCA Correlation Circle](./assets/pca_correlation_circle.png)

---

## 🧠 References
For theoretical background and statistical methodology:
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Hamilton, *Time Series Analysis*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Youssoufa Sy (2025), *Course guidelines and evaluation criteria for data analysis report*, University of Nantes【13†Webmail Etudiants】  

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Pierre Quintin de Kercadio and Florian Crochet

---

## 👤 Authors
**Pierre Quintin de Kercadio**  
[GitHub Profile](https://github.com/PierreQDK)  

**Florian Crochet**  
[GitHub Profile](https://github.com/floriancrochet)

*Master 1 – Econometrics & Statistics, Applied Econometrics Track*

---

## 💬 Acknowledgments
Special thanks to **Dr. Youssoufa Sy** (CREM–Rennes 1, EDLE program) for his academic guidance and methodological insights.  
The authors also acknowledge the **open-source R community** for providing robust and reproducible statistical tools.

---
