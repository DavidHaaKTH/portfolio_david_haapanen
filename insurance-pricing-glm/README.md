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
- **Databehandling:** Skapande av tariffgrupper (baserat på risk homogenitet)och kategorisering av variabler.
  ### Tariffgrupperingat och modellval

| **Tariffgrupp** | **Beskrivning** | **Kategorier** | **Inkluderad i reducerad modell** |
|-----------------|-----------------|----------------|:--------------------------------:|
| **NoPGroup** | Antal personer försäkrade per företag – påverkar skadefrekvensen. | 2–4, 5–9, 10–24, 25–49, 50+ | ✅ |
| **ActivityGroup** | Branschtillhörighet; olika yrken med olika risknivåer. | Industrial, Service, Other | ❌ |
| **CompanyAgeGroup** | Företagets ålder, äldre bolag anses stabilare och gör färre skador. | New (0–2), Emerging (3–10), Established (11–25), Mature (26–50), Seasoned (50+) | ❌ |
| **TravelGroup** | Resområde; längre resor antas innebära högre risk. | Scandic, Euro, International | ✅ |
| **FinancialGroup** | Kreditbetyg; svagare ekonomi korrelerar med högre skadefrekvens. | High (AAA), Upper-Mid (AA–A), Mid (BBB–BB), Low (B–C), Other (IR, AN, missing) | ✅ |

---

### 💡 Tolkningsnotis
De tre grupper som behölls i den **reducerade modellen (✅)** visade sig ge bäst balans mellan modellkomplexitet och förklaringsgrad.  
Faktorerna **ActivityGroup** och **CompanyAgeGroup** togs bort eftersom deras inverkan var svag och överlappade med övriga variabler (AIC och LR-test visade ingen signifikant förbättring).

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

