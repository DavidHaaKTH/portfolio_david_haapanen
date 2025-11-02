# Prediction of Municipal Solid Waste Generation and its corresponding Lower Heating Value in the EU

**Typ:** Kandidatexamensarbete (KTH, 2024)  
**Roll:** Självständigt arbete – ansvarade för hela projektet med projektpartner (datainsamling, modellering, analys och rapport).  
**Språk:** MATLAB  

---

## Syfte
Huvudsyftet av projektet var att undersöka hur maskininlärning kan användas för att stödja **långsiktig hållbar energi- och resursplanering** genom dataanalys. Således utvecklades två prediktiva modeller för att uppskatta mängden **energi som kan återvinnas från avfall i EU-länder** inför 2025 och 2035, baserat på data om avfallsflöden, materialkomposition och socio-ekonomiska riktmärken. 

Projektet jämförde en **Artificial Neural Network (ANN)** med en klassisk **Multiple Linear Regression (MLR)**-modell för att bedöma skillnader i noggrannhet och generaliseringsförmåga. Efter den slutgiltiga modelen blivit vald tillämpades den på en fallstudie för Rumänien. 

---

### Metod och implementation
- **Datakällor:** Insamling av avfalls- och energidata samt mått på socio-ekonomisk förhållanden för EU-länder utfördes m.h.a.Eurostat och The World Bank Group.
- **Datahantering:** Preprocessing, borttaggning av datapunkter och urval av prediktorer. 
- **ANN-arkitektur:**  
  - Ett dolt lager med 23 gömda noder, sigmoidaktivering
  - 7 outputs som representerade mängd av respektive avfallstyp  
  - Tränad med backpropagation (Levenberg–Marquardt-algoritmen)
Nedan visas den artificiella neurala nätverkets arkitektur som användes i projektet:

![ANN-arkitektur](ann_architecture.png)
- **Baslinje:** MLR tränad på samma dataset  
- **Utvärderingsmått:** R, R², RMSE, MAPE, MdAPE, APE


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
