# Optimization of Spare Parts Allocation using Marginal Allocation and Dynamic Programming

**Typ:** Projekt inom kursen Systems Engineering, KTH 2024  
**Roll:** Implementation av optimeringsalgoritmer, simulering och rapportskrivning i sammarbete med projektpartner


**Språk:** MATLAB  

---

## Syfte
Projektet syftade till att tillämpa teorin bakom **spare-parts-optimering** på ett flygunderhållsscenario och jämföra två metoder:
- **Marginal Allocation (MA)** för att identifiera effektiva lösningar under en budgetbegränsning.  
- **Dynamic Programming (DP)** för att finna den globala optimala lösningen.

Uppgiften modellerade hur ett flygbaslager bör dimensioneras för att minimera antalet markbundna flygplan (**Expected Backorders, EBO**) givet en fast budget för reservdelar.

---

## Metod och implementation

### Problemformulering
- Nio olika **Line Replaceable Units (LRU)** representerar komponenter som hjul, motorer och radar.  
- Varje komponenttyp har:
  - **λ**: felhastighet  
  - **T**: genomsnittlig reparationstid  
  - **c**: inköpskostnad  
- Målet: minimera \(EBO(**s**)\) under budgetbegränsningen \(C(**s**) ≤ C_budget\).  

### Marginal Allocation (MA)
- Utvärderade **hur EBO minskar** när nya reservdelar läggs till.  
- Effektiva punkter beräknades upp till \(C_budget = 500 kr\).  
- Varje iteration valde den LRU med **högst marginalnytta per kostnad**.  

### Dynamic Programming (DP)
- Problemets rekursiva struktur utnyttjades för att hitta **globala optima** vid olika budgetnivåer.  
- Definierade:
  - *Stages:* komponenttyper (LRU1–LRU9)  
  - *States:* kvarvarande budget  
  - *Decision variable:* antal reservdelar per LRU  
- Beräknade optimala lösningar för budgetnivåer {0, 100, 150, 350, 500} [kr].  

---

## Resultat

### Effektiva punkter vid tillämpning av Marginal Allocation  
Budget: C<sub>budget</sub> = 500  

| **Eff. Point** | **s₁** | **s₂** | **s₃** | **s₄** | **s₅** | **s₆** | **s₇** | **s₈** | **s₉** | **EBO(s)** | **C(s)** |
|:--------------:|:------:|:------:|:------:|:------:|:------:|:------:|:------:|:------:|:------:|:----------:|:--------:|
| 1 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 7.7120 | 0 |
| 2 | 0 | 0 | 0 | 1 | 0 | 0 | 0 | 0 | 0 | 6.9148 | 21 |
| 3 | 0 | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 6.6289 | 32 |
| 4 | 1 | 0 | 0 | 1 | 1 | 0 | 0 | 0 | 0 | 6.2943 | 45 |
| 5 | 1 | 0 | 1 | 1 | 1 | 0 | 0 | 0 | 0 | 5.7436 | 68 |
| 6 | 1 | 0 | 1 | 2 | 1 | 0 | 0 | 0 | 0 | 5.2699 | 89 |
| 7 | 1 | 1 | 1 | 2 | 1 | 0 | 0 | 0 | 0 | 4.9490 | 106 |
| 8 | 1 | 1 | 1 | 2 | 1 | 1 | 0 | 0 | 0 | 4.2654 | 159 |
| 9 | 1 | 1 | 1 | 2 | 1 | 1 | 1 | 0 | 0 | 3.3514 | 235 |
| 10 | 1 | 1 | 1 | 3 | 1 | 1 | 1 | 0 | 0 | 3.1359 | 256 |
| 11 | 1 | 1 | 1 | 3 | 1 | 1 | 2 | 0 | 0 | 2.4329 | 332 |
| 12 | 1 | 1 | 1 | 3 | 1 | 1 | 2 | 0 | 1 | 2.2223 | 355 |
| 13 | 1 | 1 | 1 | 3 | 1 | 1 | 2 | 1 | 1 | 1.9307 | 387 |
| 14 | 1 | 1 | 2 | 3 | 1 | 1 | 2 | 1 | 1 | 1.7395 | 410 |
| 15 | 1 | 1 | 2 | 3 | 1 | 2 | 2 | 1 | 1 | **1.4200** | **463** |

| **Budget** | **Optimal konfiguration** | **EBO(s)** | **Kostnad** |
|-------------|---------------------------|-------------|-------------:|
| 0 | [0,0,0,0,0,0,0,0,0] | 7.71 | 0 |
| 150 | [1,1,1,3,1,0,0,0,1] | 4.52 | 150 |
| 500 | [2,1,2,3,1,1,3,1,1] | **1.23** | **499** |

**Visualisering av effektiva lösningar (MA) och globala optimum (DP):** blåa punkter kommer från 
<img src="img/ebo_vs_cost.png" width="550">

---

## Lärdomar
- Marginal Allocation ger en snabb överblick över effektiva trade-offs mellan kostnad och prestanda.  
- Dynamic Programming ger den exakta globala lösningen men är beräkningsmässigt mer krävande.  
- Projektet illustrerade praktisk tillämpning av **optimering, rekursiva metoder och resursplanering** inom systems engineering.  

---

## Rapport
📄 [Optimization of Spare Parts Allocation (KTH, 2024)](./HA2_group35.pdf)

---

## Kod
💻 MATLAB-implementation av Marginal Allocation och Dynamic Programming finns i projektmappen:  
📂 [`optimization`](https://github.com/DavidHaaKTH/portfolio_david_haapanen/tree/main/optimization)
