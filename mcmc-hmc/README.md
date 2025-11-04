# Bayesian Inference using MCMC and Hamiltonian Monte Carlo

**Typ:** Projekt inom kursen *Computer Intensive Methods in Mathematical Statistics (KTH, 2025)*  
**Roll:** Implementering av Gibbs-, Metropolis-Hastings- och Hamiltonian Monte Carlo-metoder  

**Språk:** MATLAB  

---

## Syfte
Projektet syftade till att tillämpa **Markov Chain Monte Carlo (MCMC)**-metoder för två olika problem:
1. **Bayesiansk analys av kolgruveexplosioner**: sampling från en posterior fördelning med flera brytpunkter m.h.a hybrid sampling.
2. **Hamiltonian Monte Carlo (HMC)**: för sampling från cirkulär formad posterior fördelning.

---

## Metod och implementation
- **Del 1: MCMC för Poissonprocess (Coal Mine Disasters)**
  - Modell: Inhomogen Poisson-process med intensiteter $` \lambda_i `$ och brytpunkter $` t_i `$.  
  - Priors: $` \lambda_i \sim \Gamma(2, \theta), \ \theta \sim \Gamma(2, \vartheta) `$
  - Hybrid MCMC:
    - Gibbs-sampling för $` \lambda, \theta `$
    - Metropolis–Hastings för brytpunkter $` t_i `$, med en random walk propsal.
  - Testade olika värden för $` \vartheta `$ och olika antal brytpunkter.

- **Del 2: Hamiltonian Monte Carlo (HMC)**
  - Modell: $` y_i \sim N(\theta_1^2 + \theta_2^2, \sigma^2) `$
  - HMC implementerades med Leapfrog-integrator (stegstorlek $` \epsilon `$, antal steg $` L `$).
  - Jämfördes mot vanlig Metropolis–Hastings med en bivariate randomwalk proposal, med parametrar: $` \sigma = 2, \Sigma = \text{diag}(5, 0.5) `$.
  - Utvärdering och jämförelse mellan metoderna baserades på acceptance rate och autokorrelation mellan samples. 

---

## Resultat
- MCMC-kedjan för kolgruveproblemet konvergerade snabbt för 2–3 brytpunkter.
- HMC visade effektivare utforskning av posteriorytan jämfört med vanlig MH:  
  - Högre aacceptance rate och lägre autokorrelation.  
  - Bra balans mellan stegstorlek och antal Leapfrog-steg.  

---

## Lärdomar
- Förståelse för hybrid MCMC och dess stabilitet vid komplexa posteriors.  
- Implementering av HMC med praktisk parameterkalibrering.  
- Jämförelse av MCMC-metoder med avseende på effektivitet och mixing.  

---

📄 [Full report – MCMC and HMC for Bayesian Inference (KTH, 2025)](./MCMC_report.pdf)
