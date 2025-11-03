# Predictive Modeling using Multiple Linear Regression (BMI Case Study)

**Typ:** Projekt inom kursen Regressionsanalys (KTH, 2025)  
**Roll:** Ansvarade för databehandling, modellering, resultatpresentation och rapport skrivning

**Språk:** R  

---

## Syfte
Projektets syfte var att använda **multiple linear regression (MLR)** för att undersöka hur olika variabler såsom ålder, kön, aktivitetsnivå och kostvanor påverkar individers **Body Mass Index (BMI)**. Fokus låg på att utveckla en färdig modell där man tog i åtanke dess predektiva förmåga och residualstruktur mot teoretiska antaganden för linjära modeller.

---

## Metod och implementation
- **Datakälla:** Simulerad eller öppen hälsodata innehållande 242 datapunkter och 14 prediktorer relaterade till antropometriska kropps mått.
- ## Metod och implementation
Utvecklingen av den slutgiltiga regressionsmodellen genomfördes stegvis enligt följande metodik:

1. **Modellantaganden och validering**  
   Säkerställde att grundläggande antaganden för linjär regression uppfylldes, inklusive linjäritet, normalfördelade residualer och konstant varians.

2. **Identifiering av outliers och inflytelserika observationer**  
   Analyserade leverage-värden och Cook’s distance för att upptäcka datapunkter som hade oproportionerligt stort inflytande på modellen.

3. **Variabeltransformationer**  
   Utförde transformationer (t.ex. log eller kvadratrot) där nödvändigt för att stabilisera varians och förbättra linjäritet mellan variabler.

4. **Multikollinearitet**  
   Undersökte korrelationer mellan prediktorer och beräknade VIF (Variance Inflation Factor) för att upptäcka redundanta variabler.

5. **Variabelurval**  
   Använde stegvis urval (Stepwise Selection) baserat på AIC och statistisk signifikans för att finna den mest parsimoniska modellen.

6. **Prestandautvärdering**  
   Bedömde modellens kvalitet med Adjusted R², RMSE samt analys av residualplots för att verifiera prediktionsförmåga och antaganden.



- **Databehandling:**  
  - Hantering av saknade värden och outliers  
  - Normalisering och kodning av kategoriska variabler  
- **Modellering:**  
  - Multipel linjär regression (OLS)  
  - Test av interaktionseffekter (t.ex. kön × ålder)  
  - Modellurval baserat på AIC och Adjusted R²  
- **Utvärdering:**  
  - Residualdiagnostik (normalitet, homoskedasticitet, multikollinearitet)  
  - Modelljämförelse med transformationsförsök (t.ex. log-transform av BMI)

---

### Rapport
Hela rapporten finns tillgänglig här:  
📄 [Insurance Pricing using GLM – Regression Analysis Project (KTH, 2025)](./Insurance_GLM_Report.pdf)


