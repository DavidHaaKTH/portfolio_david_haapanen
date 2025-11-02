# Pricing of Insurance Premiums using Generalized Linear Models (GLM)

**Typ:** Projekt inom kursen Regressionsanalys (KTH, 2025)  
**Roll:** Ansvarade för modellering, implementation i Python, resultatvisualisering och rapport skrivning
**Språk:** Python  

---

## Syfte
Projektet genomfördes i samarbete med **If Insurance** och syftade till att bygga en prediktiv modell för **prissättning av företagsreseförsäkringar**. Målet var att uppskatta en rättvis premie baserad på riskfaktorer såsom företagsstorlek, bransch, kreditrating och reseområde, med hjälp av **Generalized Linear Models (GLM)**.

---

### Metod och implementation
- **Datakälla:** Historiska försäkringsdata (149 000 observationer, 10 variabler) från If (2018–2022).  
- **Databehandling:** Hantering av outliers, skapande av tariffgrupper och kategorisering av variabler.  
- **Modellering:** innefattas både för hur ofta ett företag ber om reseförsäkring och hur mycket
  - Frekvensmodell → Poisson-GLM med log-länk
  - Severitymodell → Gamma-GLM med log-länk
  - Premie = Frekvens × Severity
- **Modelljämförelse:** Full vs. reducerad modell utvärderad med:
  - Gini-koefficient
  - Likelihood-ratio-test
  - AIC-värden


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

