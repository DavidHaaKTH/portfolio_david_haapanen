# ROCKET-Based Time-Series Classification for Edi Catheter Positioning in Neonates

**Typ:** Examensarbete inom tillämpad matematik (KTH, 2026)  
**Samarbete:** Getinge  
**Roll:** Självständigt examensarbete – utveckling, implementation och utvärdering av ett ramverk för tidsserieklassificering och bedömning av Edi-kateterposition, med analys av generalisering mellan neonatala och vuxna patientpopulationer.

**Språk:** Python och MATLAB

---

## Syfte

Examensarbetet undersökte hur **maskininlärning och tidsserieklassificering** kan användas för att stödja bedömningen av Edi-katetrars position hos neonatala patienter.

Edi-katetrar används bland annat för att mäta diafragmans elektriska aktivitet vid respiratorisk övervakning och ventilatorbehandling. Korrekt positionering är därför viktig, samtidigt som bedömningen kan försvåras av exempelvis variationer i fysiologiska signaler och patientrörelser.

Projektets mål var att utveckla och utvärdera ett ramverk som kombinerade **god klassificeringsprestanda, beräkningseffektivitet och robusthet** under begränsad tillgång till klinisk data.

---

## Metod och implementation

Jag utvecklade en Python-baserad pipeline för bearbetning och klassificering av multivariata fysiologiska tidsserier.

Arbetet omfattade bland annat:

- Bearbetning och annotering av multivariata Edi-härledda fysiologiska signaler med **MATLAB och Python**, inklusive framtagning av hjärtslagscentrerade tidsseriesegment för vidare modellering.
- Feature extraction med **MiniROCKET** och utvärdering av **Detach-ROCKET**.
- Utvärdering av flera klassificeringsmetoder, däribland Ridge Classification, Multinomial Logistic Regression (MLR) och Support Vector Machines (SVM).
- Systematisk utvärdering av feature-dimension, regularisering, sampling och class balancing.
- Patientbaserad Cross-Validation och Leave-One-Out Cross-Validation för att undersöka generalisering till tidigare osedda patienter.
- Cross-domain-experiment mellan neonatala och vuxna patientpopulationer för att undersöka modellernas överförbarhet.
- Analys av avvägningen mellan klassificeringsprestanda, robusthet och beräkningskostnad.

Den slutliga lösningen använde ett tvåstegsramverk. Först klassificerade ML-modellen lokala elektrodgrupper som **för högt**, **välpositionerade** eller **för lågt**. Dessa prediktioner kombinerades därefter i ett deterministiskt inferensramverk för att uppskatta kateterns övergripande position och dess förändring över tid.

---

## Resultat

Den slutliga MiniROCKET-baserade modellen uppnådde på ett separat neonatalt testdataset:

| Utvärderingsmått | Resultat |
|------------------|:--------:|
| Accuracy | **0.8536** |
| Macro F1-score | **0.8492** |
| Weighted F1-score | **0.8558** |

MiniROCKET i kombination med Ridge Classification gav den mest fördelaktiga balansen mellan **klassificeringsprestanda, generalisering och beräkningseffektivitet** av de undersökta metoderna.

Analysen visade samtidigt betydande variation mellan enskilda patienter och begränsad överförbarhet mellan neonatala och vuxna patientpopulationer. Resultaten underströk därför vikten av patientbaserad validering och analys av generalisering vid utveckling av ML-modeller för kliniska data.

---

## Lärdomar

- Utveckling av en komplett ML-pipeline för komplexa multivariata tidsserier.
- Systematisk experimentdesign och reproducerbar modellutvärdering.
- Praktisk förståelse för regularisering, generalisering och modellkomplexitet vid begränsad datatillgång.
- Patientbaserad validering för att minska risken för optimistiska resultat orsakade av korrelerade observationer.
- Analys av generalisering och transfer learning mellan olika patientpopulationer.
- Avvägning mellan modellprestanda, robusthet, tolkningsbarhet och beräkningskostnad.

---

## Teknik och verktyg

- **Python**
- **MATLAB**
- **Machine Learning & Time-Series Classification**
- **MiniROCKET & Detach-ROCKET**
- **scikit-learn**, **PyTorch**, **NumPy**, **pandas**, **matplotlib**
- **Cross-Validation & LOOCV**
- **Transfer Learning / Cross-Domain Evaluation**

---

## Rapport

Examensarbetet genomfördes i samarbete med **Getinge**. Dataset, källkod och internt material är proprietärt och publiceras därför inte i detta repository.

📄 Läs hela rapporten här: http://kth.diva-portal.org/smash/record.jsf?pid=diva2:2118102.
