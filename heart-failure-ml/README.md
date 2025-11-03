# Heart Failure Classification using Machine Learning

**Typ:** Kursprojekt inom kursen Modern Methods of Statistical Learning (KTH, 2025)  
**Roll:** Ansvarade för modellering, utvärdering och rapportskrivning tillsammans med projektgrupp 


**Språk:** Python  
---

## Syfte
Syftet med projektet var att utveckla och jämföra flera maskininlärningsmodeller för att **förutsäga hjärtsvikt baserat på patientdata**, fokus låg på noggrannhet och generaliseringsförmåga.

---

## Dataset
- **Källa:** [Heart Failure Prediction Dataset (Kaggle)](https://www.kaggle.com/fedesoriano/heart-failure-prediction)  
- **Antal observationer:** 918 patienter  
- **Antal variabler:** 11 (ålder, kön, blodtryck, kolesterol, m.m.)  
- **Målfunktion:** Binär etikett (1 = hjärtsvikt, 0 = ingen hjärtsvikt)

---
## Metod
- Dataförberedelse: hantering av saknade värden, standardisering och kodning av kategoriska variabler.  
- Feature-reduktion med PCA för att minska dimension och brus.  
- Modellträning med:  
  - Logistic Regression  
  - k-Nearest Neighbors  
  - Random Forest  
  - Support Vector Machine  
  - Neural Network  
- Modellval baserat på korsvaliderad noggrannhet och F1-score.  
- Utvärdering via confusion matrix och ROC-kurvor.

---

## Resultat
- **Random Forest** och **SVM** presterade bäst med F1-score runt 0.84.  
- PCA förbättrade resultatet för enklare modeller (k-NN, Logistic Regression).  
- Feature-importance-analys visade att “ejection fraction” och “serum creatinine” var de mest betydelsefulla variablerna.

---

## Lärdomar
- Praktisk erfarenhet av en full ML-pipeline: preprocessing → modellval → utvärdering.  
- Hur val av metrik påverkar modelljämförelser.  
- Vikten av databalans och cross-validation vid medicinska dataset.

---
Full rapport: [`report/SF2930Project1-DavidHaapanen-GustavKarlander.pdf`](./report/SF2930Project1-DavidHaapanen-GustavKarlander.pdf)

