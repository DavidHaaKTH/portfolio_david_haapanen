# Prediction of Municipal Solid Waste Generation and its corresponding Lower Heating Value in the EU

**Typ:** Kandidatexamensarbete (KTH, 2024)  
**Roll:** Självständigt arbete – ansvarade för hela projektet med projektpartner (datainsamling, modellering, analys och rapport).

**Språk:** MATLAB  

---

## Syfte
Huvudsyftet av projektet var att undersöka hur maskininlärning kan användas för att stödja **långsiktig hållbar energi- och resursplanering** genom dataanalys. Således utvecklades två prediktiva modeller för att uppskatta mängden **energi som kan återvinnas från avfall i EU-länder**, baserat på data om avfallsflöden, materialkomposition och socio-ekonomiska riktmärken. 

Projektet jämförde en **Artificial Neural Network (ANN)** med en klassisk **Multiple Linear Regression (MLR)**-modell för att bedöma skillnader i noggrannhet och generaliseringsförmåga. Efter den slutgiltiga modelen blivit vald tillämpades den i samband med en fallstudie för Rumänien. 

---

### Metod och implementation
- **Datakällor:** Insamling av avfalls- och energidata samt mått på socio-ekonomisk förhållanden för EU-länder utfördes m.h.a.Eurostat och The World Bank Group.
- **Datahantering:** Preprocessing (logaritmering och normalisering), borttaggning av datapunkter och urval av prediktorer. 
- **ANN-arkitektur:**
ANN modelen utvecklades med en 70%/15%/15% training/validation/test split där antalet gömda neuroner baserades på vad som gav lägsta mediana validation error baserat på 100 individuella nätverk utvecklade på tränings datan (se längre ned).
![ANN-arkitektur](net_overview.png)
  - 5 inputs som representerar socio-ekonomiska metriker
  - Ett dolt lager med 23 gömda noder, sigmoidaktivering
  - 7 outputs som representerade mängd av respektive avfallstyp
  - Tränad med backpropagation (Levenberg–Marquardt-algoritmen)
- **Baslinje:** MLR tränad på samma dataset  
- **Utvärderingsmått:** R, R², RMSE, MAPE, MdAPE, APE

**Flowchart som illustrerar av alla steg som utfördes under projektets**
<img src="flow_chart2.png" width="600">

**Training och validation error i samband med ökande mängd gömda neuroner**
<img src="train_val_error.png" width="600">

---

## Resultat
ANN-modellen generaliserade bättre till test datan samt visade bättre prestanda utifrån de valda utvärderingsmåtten. Modellerna användes även sedan för att förutsäga den framtida energiåtervinningen för Rumänien år 2025 och 2035.

- **Modellprestanda** baserat på test data
  
| **Utvärderingsmått** | **ANN** | **MLR** |
|--------------------|:-------:|:-------:|
| MSE | 0.0076* | 0.0104* |
| R (test)* | **0.9133** | **0.8661** |
| R² | 0.6332 | 0.5375 |
| RMSE [Mt] | 1.7223 | 1.9340 |
| MAPE [%] | 60.33 | 97.98 |
| MdAPE [%] | 38.24 | 51.44 |

---

## Lärdomar
- Skillnader mellan linjära och icke-linjära modeller i praktiska energisystem.  
- Hur feature-val och dataskalning påverkar ANN-prestanda.  
- Förmågan att kombinera teknisk modellering med hållbarhetsanalys.

---
### Rapport
Hela kandidatarbetet finns publicerat i KTH:s DiVA-databas:  
📄 [Prediction of Municipal Solid Waste Generation and its corresponding Lower Heating Value in the EU: A Case Study of Romania](https://kth.diva-portal.org/smash/get/diva2:1897134/FULLTEXT01.pdf)
