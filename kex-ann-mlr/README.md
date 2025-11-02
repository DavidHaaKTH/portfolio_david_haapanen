# Prediction of Municipal Solid Waste Generation and its corresponding Lower Heating Value in the EU
A Case Study of Romania

**Typ:** Kandidatexamensarbete (KTH, 2024)  
**Roll:** Självständigt arbete – ansvarade för hela projektet med projektpartner (datainsamling, modellering, analys och rapport).  
**Språk:** MATLAB  

---

## Syfte
Syftet var att utveckla prediktiva modeller för att uppskatta mängden **energi som kan återvinnas från avfall i EU-länder**, baserat på data om avfallsflöden och materialkomposition. Projektet jämförde en **Artificial Neural Network (ANN)** med en klassisk **Multiple Linear Regression (MLR)**-modell för att bedöma skillnader i noggrannhet och generaliseringsförmåga.

---

## Metod
- Datainsamling av avfalls- och energidata för EU-länder (Eurostat och litteraturdata).  
- Implementation av ANN och MLR i MATLAB.  
- Modellutvärdering med \( R^2 \), RMSE och MAPE.  
- Test av modellernas känslighet mot olika fraktionssammansättningar i avfall.

---

## Resultat
- **ANN-modellen** uppnådde högre förklaringsgrad och lägre fel än MLR.  
- Modellerna användes för att förutsäga framtida energiåtervinning (t.ex. Rumänien 2025–2035).  
- Känslighetsanalysen visade att ökade andelar plast och papper höjde det beräknade LHV-värdet.

---

## Lärdomar
- Skillnader mellan linjära och icke-linjära modeller i praktiska energisystem.  
- Hur feature-val och dataskalning påverkar ANN-prestanda.  
- Förmågan att kombinera teknisk modellering med hållbarhetsanalys.

---
Full rapport: [`report/KEX_Slutinläming_2024-05-23.pdf`](./report/KEX_Slutinläming_2024-05-23.pdf)
