# Socioeconomic Disparities Across French Departments  
*A data-driven econometric and statistical analysis of income determinants in France.*

---

## 📘 Overview
This project conducts an in-depth **exploratory and econometric analysis of socioeconomic disparities** among French departments.  
It was developed as part of the **Master’s program in Econometrics and Statistics (Applied Econometrics track)** at the University of Nantes.

**Objectives**
- Analyze the determinants of **average annual income** across French departments  
- Explore the **economic, demographic, and geographic factors** influencing disparities  
- Apply **descriptive statistics, PCA**, and **multiple regression models** for interpretation  
- Ensure methodological rigor, **reproducibility**, and **clarity** in applied econometric analysis  

---

## ⚙️ Features
- Descriptive statistical analysis with visualization of quantitative and qualitative variables  
- Principal Component Analysis (PCA) for dimensionality reduction and variable synthesis  
- Multiple linear regression models for assessing factor influence  
- Statistical testing (normality, Wilcoxon, Chi-squared)  
- Automated generation of descriptive graphics in R (histograms, boxplots, correlation plots)  

---

## 🧰 Tech Stack
**Language:** R  
**Libraries:** `tidyverse`, `openxlsx`, `FactoMineR`, `factoextra`, `corrplot`, `PerformanceAnalytics`, `sjPlot`, `gridExtra`, `EnvStats`, `AER`, `lmtest`  

---

## ⚙️ Installation
Clone the repository and install required R libraries:

```bash
git clone https://github.com/<your-username>/french-socioeconomic-analysis.git
cd french-socioeconomic-analysis
Rscript -e 'install.packages(c("tidyverse","openxlsx","FactoMineR","factoextra","corrplot","PerformanceAnalytics","sjPlot","gridExtra","EnvStats","AER","lmtest"))'
```

---

## 📚 Usage Example

```r
# Load dataset
base <- read.xlsx("data/french_departments_socioeconomic_data.xlsx", startRow = 2, colNames = TRUE, rowNames = TRUE)

# Perform PCA
library(FactoMineR)
ACP1 <- PCA(base[, 1:11], scale.unit = TRUE)

# Visualize correlation circle
library(factoextra)
fviz_pca_var(ACP1, col.var = "cos2", gradient.cols = c("skyblue", "red"), repel = TRUE)
```

Additional examples and visual outputs are available in the `notebooks/` and `reports/` directories.

---

## 📂 Project Structure

```
french-socioeconomic-analysis/
│
├── data/                     # Dataset of French departments
├── src/                      # R scripts for analysis
├── notebooks/                # R Markdown notebooks
├── reports/                  # Final PDF and HTML outputs
├── assets/                   # Figures and plots
├── requirements.R            # List of required packages
└── README.md
```

---

## 📊 Results
The study identifies several key determinants of income disparities among French departments:

- **Economic variables** such as GDP and population size strongly influence average income.  
- **Demographic indicators** (birth and death rates) define regional dynamism.  
- **Environmental and educational factors** (green space per capita, education rate) have nuanced, sometimes counterintuitive effects.  
- The **PCA** revealed four main components explaining 52% of the total variance, highlighting latent structures such as *demographic dynamism*, *quality of life*, *economic concentration*, and *socio-educational tension*.

Example visualization:

![Correlation Circle](./assets/pca_correlation_circle.png)

---

## 🧠 References
For theoretical and methodological background:
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Hamilton, *Time Series Analysis*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Youssoufa Sy, *Économétrie avancée* (course materials, 2024–2025)  

---

## 📜 License
This project is released under the **MIT License**.  
© 2025 Florian Crochet & Pierre Quintin de Kercadio

---

## 👤 Author
**Florian Crochet**  
*Master’s Student in Econometrics & Statistics — Applied Econometrics*  
📫 [LinkedIn](> À compléter) | [Email](> À compléter) | [Portfolio](> À compléter)

---

## 💬 Acknowledgments
Supervised and guided by **Dr. Youssoufa Sy (CREM-Rennes 1, European Doctorate in Law and Economics)**.  
Special thanks to the open-source R community and university collaborators.
