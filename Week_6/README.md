# Week 6 – Limit Cycles
* Perform dimensional analysis on the predator-prey systems given in _Danby_[1]. Then anaylse for fixed points character. Plot orbits, is there any special behaviour?
    * Starter system,
        * $\dot{r} = α_r r - p_{r f} r f$
        * $\dot{f} = -δ_f f + p_{f r} r f$
    * Logistic Growth for Prey,
        * $\dot{r} = α_r r (1 - \frac{r}{r_\infty}) - p r f$
        * $\dot{f} = -δ_f f + p r f$
    * Logistic Growth for Both,
        * $\dot{r} = α_r r (1 - \frac{r}{r_\infty}) - p r f$
        * $\dot{f} = α_f f (1 - \frac{s f}{r})$
    * Saturatable Predation,
        * $\dot{r} = α_r r - p f \frac{r r_p}{r + r_p}$
        * $\dot{f} = -δ_f f + p f \frac{r r_p}{r + r_p}$
* We analysed in class the system of logistic growth for both species with saturable predation,
    * $\dot{r} = α_r r (1 - \frac{r}{r_\infty}) - p r f$
    * $\dot{f} = α_f f (1 - \frac{s f}{r})$
    * See how far you can get with an analytic analysis of the fixed points.
        * How many are there? Can Mathematica find them all? Do they have critical values?
    * This system reduces to the "Catastophic" bifurcation system of last week when $\dot{f} → 0$. Explore this correspondance.

[1] Danby, J. M. A. Computer Modeling : From Sports to Spaceflight, from Order to Chaos. Richmond, Va: Willmann-Bell, 1997. Print. Chapter 6
  
