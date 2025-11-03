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
   - Fördelning av 80/20 train–test-split    

2. **Förbehandling**
   - **Numeriska variabler:** Standardiserades med `StandardScaler`  
   - **Kategoriska variabler:** Ändrades binära värden med `OneHotEncoder`  
   - Båda stegen kombinerades via `ColumnTransformer` och inkluderades i en `Pipeline`  

3. **Dimensionalitetsreduktion**
   - **PCA** tillämpades för modeller som baseras på distans mellan punkter (särskilt k-NN) för att minska effekten av hög dimension och förbättra beräkningshastighet.

4. **Modellering**
   Följande klassificeringsmetoder implementerades och jämfördes:
   - k-Nearest Neighbors (k-NN)  
   - k-NN med PCA    
   - Random Forest  
   - AdaBoost applicerad på Decision Trees 
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

## Resultat

| **Modell** | **Accuracy** | **F1-score** | **Precision** | **Recall** |
|-------------|:------------:|:-------------:|:--------------:|:------------:|
| k-NN | 0.918 | 0.920 | 0.920 | 0.920 |
| k-NN + PCA | **0.929** | **0.930** | **0.930** | **0.930** |
| Random Forest | 0.902 | 0.900 | 0.900 | 0.900 |
| AdaBoost | 0.897 | 0.900 | 0.900 | 0.890 |
| SVM (RBF kernel) | 0.902 | 0.902 | 0.902 | 0.902 |
| Neural Network | 0.880 | 0.880 | 0.882 | 0.880 |
| Gaussian Process | 0.891 | 0.890 | 0.890 | 0.890 |

**Bästa modell:** k-NN med PCA (Accuracy = 92.9%)  
→ Enkel men effektiv metod som presterade bäst tack vare reduktion av dimensionsbrus.  

---

---

## Lärdomar
- Praktisk erfarenhet av en full ML-pipeline: preprocessing → modellval → utvärdering.  
- Hur val av metrik påverkar modelljämförelser.  
- Vikten av databalans och cross-validation vid medicinska dataset.

---
Full rapport: [`report/SF2930Project1-DavidHaapanen-GustavKarlander.pdf`](./report/SF2930Project1-DavidHaapanen-GustavKarlander.pdf)

