# Multiple Linear Regression model for predicting BMI

**Typ:** Projekt inom kursen Regressionsanalys (KTH, 2025)  
**Roll:** Ansvarade för databehandling, modellering, resultatpresentation och rapport skrivning

**Språk:** R  

---

## Syfte
Projektets syfte var att använda **multiple linear regression (MLR)** för att utveckla en regressions modell som utifrån kropssmått kunna förutsäga en persons **Body Mass Index (BMI)**. Fokus låg på att utveckla en färdig modell där man tog i åtanke dess predektiva förmåga och residualstruktur mot teoretiska antaganden för linjära modeller.

---

## Metod och implementation
- **Datakälla:** Simulerad eller öppen hälsodata innehållande 242 datapunkter och 13 prediktorer relaterade till antropometriska kropps mått.
- ## Metod och implementation
Utvecklingen av den slutgiltiga regressionsmodellen genomfördes stegvis enligt följande metodik:

1. **Modellantaganden och validering**  
Säkerställde att grundläggande antaganden för linjär regression uppfylldes, inklusive linjäritet, normalfördelade residualer och konstant varians. Detta utfördes på den initiella modellen som använde alla 13 predikatorer m.h.a. Q-Q plots och residual vs. fitted values plots.

2. **Identifiering av outliers och inflytelserika observationer**  
   Analyserade leverage-värden (från "hat-matrix"), Cook’s distance och DFFITS för att upptäcka datapunkter som hade starkt inflytande på modellen. 

3. **Multikollinearitet**  
   Undersökte korrelationer mellan prediktorer genom correlation matrix vilket indikerade samband mellan predikatorer. Genom beräkning av VIF (Variance Inflation Factor) och egen-värdes analys (condition number) uteslöts variabler som ansågs bidra med multikollinearitet. Detta ledde således till en reducerad modell.

4. **Variabelurval**  
   Använde stegvis urval (Forward-/Backward Stepwise Selection) baserat på AIC och statistisk signifikans för att simplare modeller som ev. kan generalisera bättre. Detta ledde till ytterligare två kandidat modeller.

5. **Slutgiltig modell** 
Alla modeller hade liknande prestanda baserat på MSE ifrån 10-fold CV. Då den reducerade modellen visade minst kollinearitet valdes den som den slutgiltiga modellen.

---

### Rapport
Hela rapporten finns tillgänglig här:  
📄 [Prediction of BMI using MLR – Regression Analysis Project (KTH, 2025)](./Regression_BMI_Report.pdf)


