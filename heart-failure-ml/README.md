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
## Metod och implementation

Arbetsflödet implementerades som en **ML-pipeline** i Python (scikit-learn).  
Nedan följer huvudstegen:

1. **Datapreparation**
   - Separering av features och målvariabel  
   - Stratifierad 80/20 train–test-split  
   - Inga saknade värden upptäcktes  

2. **Förbehandling**
   - **Numeriska variabler:** Standardiserades med `StandardScaler`  
   - **Kategoriska variabler:** Enkodades med `OneHotEncoder`  
   - Båda stegen kombinerades via `ColumnTransformer` och inkluderades i en `Pipeline`  

3. **Dimensionalitetsreduktion**
   - **PCA** tillämpades för vissa modeller (särskilt k-NN) för att minska effekten av hög dimension och förbättra beräkningshastighet.

4. **Modellering**
   Följande klassificeringsmetoder implementerades och jämfördes:
   - k-Nearest Neighbors (k-NN)  
   - k-NN med PCA  
   - Decision Tree  
   - Random Forest  
   - AdaBoost  
   - Neural Network (MLP)  
   - Support Vector Machine (SVM)  
   - Gaussian Process Classifier  

5. **Hyperparametertuning och validering**
   - 10-fold cross-validation på träningsdata  
   - Grid search användes för att identifiera optimala parametrar  

6. **Utvärderingsmått**
   - **Accuracy**  
   - **Precision**  
   - **Recall**  
   - **F1-score**  
   - **Confusion matrix**

---

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

