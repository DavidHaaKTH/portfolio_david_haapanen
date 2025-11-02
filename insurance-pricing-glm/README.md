# Pricing of Insurance Premiums using Generalized Linear Models (GLM)

**Typ:** Projekt inom kursen Regressionsanalys (KTH, 2025)  
**Roll:** Ansvarade för modellering, implementation i Python, resultatvisualisering och rapport skrivning
**Språk:** Python  

---

## Syfte
Syftet med projektet var att analysera och bestämma priset för reseförsäkringspremier baserat på kunddata från **If Insurance**, med hjälp av **Generalized Linear Models (GLM)**.  
Projektet fokuserade på att identifiera vilka faktorer som bäst förklarar risken för försäkringsskador och hur dessa kan användas för att optimera prissättning och riskhantering.

Vi modellerade både **frekvens (antal skador)** och **severity (kostnad per skada)** med olika länkfunktioner och fördelningar, i syfte att uppskatta den förväntade totala kostnaden per kund.

---

### Metod och implementation
- **Datakälla:** Simulerat kunddata från If Insurance (2025) med variabler såsom ålder, fordonstyp, region, kreditrating och tidigare skadehistorik.  
- **Databehandling:** Rensning av outliers, omkodning av kategoriska variabler och transformation av kontinuerliga prediktorer.  
- **Modellerade komponenter:**
  - **Frekvensmodell:** Poisson-GLM med log-länk  
  - **Severitymodell:** Gamma-GLM med log-länk  
  - **Sammanlagd premie:** Multiplikation av förväntad frekvens och severity
- **Utvärdering:** Likelihood-ratio-test, AIC-jämförelse, samt **Gini-koefficient** för diskrimineringsförmåga.  
- **Visualisering:** Residualplots, prediktionsfördelningar och riskkurvor per kundsegment.

**Flödesskiss över arbetsprocessen:**
<img src="workflow_if_project.png" width="600">

---

## Resultat
Projektet visade att **ålder, region och kreditrating** hade starkast samband med skadekostnad.  
Den reducerade modellen (färre prediktorer) presterade **bättre Gini-koefficient** än den fulla, vilket tyder på minskad överanpassning och förbättrad generalisering.

- **Jämförelse mellan modeller**

| **Mått** | **Full modell** | **Reducerad modell** |
|-----------|:----------------:|:--------------------:|
| AIC | 1842.3 | **1795.8** |
| Gini | 0.312 | **0.349** |
| Pseudo-R² | 0.41 | 0.39 |

---

## Lärdomar
- Praktisk tillämpning av **GLM-metodik** för prediktiv prissättning.  
- Betydelsen av **modellurval** och risk för överanpassning i försäkringsdata.  
- Hur man kombinerar statistisk teori med **affärsrelevanta beslut** inom försäkring och riskanalys.

---

### Rapport
Hela rapporten finns tillgänglig här:  
📄 [Insurance Pricing using GLM – Regression Analysis Project (KTH, 2025)](https://github.com/DavidHaaKTH/portfolio_david_haapanen/blob/main/if-insurance/Insurance_GLM_Report.pdf)

