# Sequential Monte Carlo for Mobility Tracking

**Typ:** Projekt inom kursen *Computer Intensive Methods in Mathematical Statistics (KTH, 2025)*  
**Roll:** Implementering av SMC- och SISR-algoritmer, analys av resultat och rapportskrivning  


**Språk:** MATLAB  

---

## Syfte
Syftet med projektet var att tillämpa **Sequential Monte Carlo (SMC)**-metoder för att uppskatta rörelsebanor för ett rörligt objekt baserat på mottagna signalstyrkor (RSSI) från basstationer i ett mobilnät. Projektet utgick från en **Hidden Markov Model (HMM)** där position, hastighet och acceleration modellerades, och målet var att använda partikelfilter för att estimera positioner i realtid.

---

## Metod och implementation
- **Modellering:** för varje diskret tidpunkt $`n`$
  - Modellen för position $`\mathbf{X}_{n}`$ och hastighet var grundat ur ett stokastiskt system med Gaussian noise.
  - Observationsmodell baserad på signalstyrka $`\mathbf{Y}_{n}`$.
  - Antal basstationer: 6  
- **Algoritmer:**
  - Implementerade både **Sequential Importance Sampling (SIS)** och **Sequential Importance Sampling with Resampling (SISR)**.
  - Estimerade väntevärdet av fordenets position för varje diskret tidsteg: $`\tau_n = E[X_n | Y_{0:n}]\) via partiklar \((X_n^{(i)}, \omega_n^{(i)})`$.
- **Kalibrering av modellparametrar:**
  - Approximerad maximum likelihood-estimering av observationsbrusets standardavvikelse $`\sigma \in (0,3)`$.
  - Likelihood beräknad punktvis via Monte Carlo-approximation.
- **Antal partiklar:** $`N = 10\,000`$ 
- **Implementation:** Fullt vektoriserad MATLAB-kod för effektivitet.

---

## Resultat
- SIS-metoden visade hög viktdegeneration (låg effecive sample rate).
- SISR-metoden gav stabila estimeringar och korrekt följning av målets bana.
- Optimal parameterestimat $` \hat{\sigma} \approx ... `$.
- Visualisering av partikelfördelning och trajektorier visade god konvergens mot sann position.

---

## Lärdomar
- Förståelse för skillnaden mellan SIS och SISR vid filterdegeneration.  
- Implementering av SMC som en praktisk lösning på icke-linjära filterproblem.  
- Insikt i parameterestimering via Monte Carlo-baserad likelihoodapproximation.

---

📄 [Full report – Sequential Monte Carlo Mobility Tracking (KTH, 2025)](./SMC_report.pdf)
