# Predictive Modeling using Multiple Linear Regression (BMI Case Study)

**Typ:** Projekt inom kursen Regressionsanalys (KTH, 2025)  
**Roll:** Ansvarade för databehandling, modellering och resultatpresentation  
**Språk:** R  

---

## Syfte
Projektets syfte var att använda **multipel linjär regression (MLR)** för att undersöka hur olika variabler såsom ålder, kön, aktivitetsnivå och kostvanor påverkar individers **Body Mass Index (BMI)**.  
Fokus låg på att jämföra modellens förklaringsgrad och residualstruktur mot teoretiska antaganden för linjära modeller.

---

## Metod och implementation
- **Datakälla:** Simulerad eller öppen hälsodata innehållande demografiska och livsstilsfaktorer.  
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

**Exempel på regressionsmodell i R:**
```r
model <- lm(BMI ~ Age + Gender + ActivityLevel + CalorieIntake, data = df)
summary(model)

