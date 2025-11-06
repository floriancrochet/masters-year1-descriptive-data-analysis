# Analyse des disparités économiques entre départements français  
*Étude économétrique sur les déterminants du revenu moyen annuel en France.*

---

## 📘 Overview
Ce projet vise à **analyser les disparités économiques et sociales entre les départements français** à travers une étude économétrique du revenu moyen annuel.  
Il a été réalisé dans le cadre du **Master 1 Économétrie et Statistiques, parcours Économétrie Appliquée**, sous la supervision de **Youssoufa Sy (Université de Nantes / CREM Rennes 1)**.

**Objectives**
- Identifier les facteurs économiques, sociaux et territoriaux influençant le revenu moyen départemental  
- Appliquer des méthodes d’analyse descriptive, d’ACP et de régression multiple  
- Évaluer l’impact des variables explicatives sur les inégalités de revenu en France  

---

## ⚙️ Features
- Statistiques descriptives univariées et bivariées (tests de Wilcoxon, Khi-2, corrélations de Spearman)  
- Analyse en Composantes Principales (ACP) pour réduction dimensionnelle  
- Modélisation économétrique linéaire multiple  
- Détection des valeurs atypiques (test de Rosner)  
- Visualisations dynamiques sous R : histogrammes, boxplots, cercles de corrélation, cartes de chaleur  

---

## 🧰 Tech Stack
**Langage :** R  
**Bibliothèques principales :**  
`tidyverse`, `FactoMineR`, `factoextra`, `corrplot`, `PerformanceAnalytics`, `car`, `lmtest`, `sjPlot`, `EnvStats`, `MASS`, `leaps`, `AER`, `gridExtra`.

---

## ⚙️ Installation
Cloner le dépôt et ouvrir le script principal sous RStudio :

```bash
git clone https://github.com/<your-username>/analyse-disparites-france.git
cd analyse-disparites-france
```

Installer les dépendances nécessaires :
```r
install.packages(c("tidyverse","FactoMineR","factoextra","corrplot","PerformanceAnalytics",
                   "car","lmtest","sjPlot","EnvStats","MASS","leaps","AER","gridExtra"))
```

Charger le script :
```r
source("script_analyse.R")
```

---

## 📚 Usage Example
```r
# Chargement de la base
base <- read.xlsx("data/french_departments_socioeconomic_data.xlsx", startRow = 2, colNames = TRUE)

# Analyse descriptive
summary(base)

# ACP
ACP1 <- PCA(base[,quantis], scale.unit = TRUE, graph = TRUE)

# Régression linéaire multiple
modele <- lm(revenu ~ pib + population + education + surface, data = base)
summary(modele)
```

Des exemples complets sont disponibles dans le dossier `notebooks/`.

---

## 📂 Project Structure
```
analyse-disparites-france/
│
├── data/                        # Données socio-économiques départementales
├── src/                         # Scripts R d’analyse
│   ├── analyse_descriptive.R
│   ├── acp.R
│   └── regression_lineaire.R
├── outputs/                     # Graphiques, résultats ACP et modèles
├── notebooks/                   # Étapes exploratoires et analyses complémentaires
├── requirements.R               # Bibliothèques à installer
└── README.md
```

---

## 📊 Results
Les résultats mettent en évidence :
- L’importance du **PIB**, de la **population** et de la **surface verte par habitant** sur le revenu moyen.  
- Un effet significatif de la **mortalité** et de la **présence d’une métropole**.  
- Une **tension entre le taux d’éducation et le revenu**, suggérant un déséquilibre socio-économique entre territoires.

![ACP projection](./assets/acp_correlation_circle.png)

---

## 🧠 References
- Hyndman & Athanasopoulos, *Forecasting: Principles and Practice*  
- Hamilton, *Time Series Analysis*  
- Wooldridge, *Introductory Econometrics: A Modern Approach*  
- Sy, Y. (2025). *Directives d’analyse de données et d’économétrie appliquée*【13†Webmail Etudiants __ Analyse des données et descriptive.pdf】  

---

## 📜 License
Ce projet est diffusé sous licence **MIT**.  
© 2025 Pierre Quintin de Kercadio & Florian Crochet.

---

## 👤 Authors
**Pierre Quintin de Kercadio**  
**Florian Crochet**  
*Étudiants en Master 1 Économétrie et Statistiques – Université de Nantes*  
📫 [LinkedIn](> À compléter) | [Email](> À compléter)

---

## 💬 Acknowledgments
Merci à **Youssoufa Sy**, enseignant-chercheur au CREM Rennes 1, pour son encadrement et ses conseils méthodologiques.  
Remerciements également à la communauté R et aux auteurs des packages open-source utilisés dans ce projet.
