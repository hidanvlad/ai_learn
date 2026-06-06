# 🎓 GHID COMPLET DE EXAMEN — Inteligență Artificială

### 📚 Tot ce trebuie să știi — structurat pe categorii, cu subiecte reale din examen

> 💡 **Cum folosești:** citește **cuprinsul** → sari la categoria dorită → la final recapitulează **Secțiunea 17** (cheat sheet examen).
>
> 📎 Resurse: [README.md](README.md) (intro RO) · [README_EN.md](README_EN.md) (intro EN) · `questions.js` (bancă întrebări)

---

## 📑 CUPRINS — unde începe fiecare categorie

| # | Categorie | Secțiune | Emoji |
|---|-----------|----------|-------|
| 0 | Prescurtări & simboluri | [§0](#-0-prescurtări--simboluri) | 📋 |
| 1 | Problema de căutare | [§1](#-1-problema-de-căutare) | 🧩 |
| 2 | Căutare neinformată (USS) | [§2](#-2-căutare-neinformată-uss) | 🔲 |
| 3 | Căutare informată (ISS) | [§3](#-3-căutare-informată-iss) | 🎯 |
| 4 | Căutare locală | [§4](#-4-căutare-locală) | ⛰️ |
| 5 | Algoritmi evolutivi (EA / GA) | [§5](#-5-algoritmi-evolutivi-ea--ga) | 🧬 |
| 6 | Particle Swarm (PSO) | [§6](#-6-particle-swarm-optimization-pso) | 🐦 |
| 7 | Ant Colony (ACO) | [§7](#-7-ant-colony-optimization-aco) | 🐜 |
| 8 | Jocuri & Minimax | [§8](#-8-jocuri--minimax) | ♟️ |
| 9 | Sisteme bazate pe cunoștințe | [§9](#-9-sisteme-bazate-pe-cunoștințe-kbs) | 📚 |
| 10 | Fuzzy & incertitudine | [§10](#-10-fuzzy-systems--incertitudine) | 🌫️ |
| 11 | Machine Learning | [§11](#-11-machine-learning) | 🤖 |
| 12 | Clustering | [§12](#-12-clustering) | 🔍 |
| 13 | Rețele neuronale (ANN) | [§13](#-13-rețele-neuronale-ann) | 🧠 |
| 14 | Deep Learning & CNN | [§14](#-14-deep-learning--cnn) | 🎨 |
| 15 | Decision Trees & GP | [§15](#-15-decision-trees--genetic-programming) | 🌳 |
| 16 | Formule & compatibilități | [§16](#-16-formule--compatibilități-de-memorat) | 📐 |
| 17 | Cheat sheet examen | [§17](#-17-cheat-sheet-examen-din-questionsjs) | ⚡ |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 📋 §0. PRESCURTĂRI & SIMBOLURI
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** dicționar rapid — când vezi o abreviere la examen, știi instant despre ce e vorba.

| Abbr. | Semnificație | La examen |
|-------|--------------|-----------|
| **USS / ISS** | Neinformată / Informată | BFS = USS; A* = ISS |
| **BFS / DFS** | Lățime / Adâncime | BFS = nivel cu nivel |
| **A\*, g, h, f** | f(n)=g(n)+h(n) | h admisibilă → A* optimal |
| **EA / GA** | Algoritmi evolutivi | Populație + fitness + crossover/mutație |
| **PSO** | Roi de particule | Velocity, position, inertia, memory |
| **ACO** | Colonie de furnici | Feromon τ, vizibilitate η, α, β |
| **TSP** | Agent de vânzări | Cel mai bun caz pentru ACO |
| **KBS / RBS / KB / IE** | Cunoștințe / Reguli / Bază / Inferență | Forward vs backward chaining |
| **TP FP FN TN P R F1** | Metrici clasificare | F1 = media armonică P și R |
| **ANN / CNN** | Rețele / Convoluționale | Feed-forward = legături ponderate între straturi |
| **GP** | Programare genetică | Individ = **program**, nu biți |
| **OX / PMX** | Crossover permutări | Order Crossover la TSP |
| **ReLU / BCE / CE / MSE** | Activare / Loss-uri | Vezi §16 compatibilități |

**Simboluri fuzzy/logică:** AND=MIN · OR=MAX · NOT=1−a · ∀ ∃ ∧ ∨ ¬

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🧩 §1. PROBLEMA DE CĂUTARE
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** orice problemă AI are 5 piese — fără ele nu alegi algoritmul.

| # | Componentă | Ce e | De ce |
|---|------------|------|-------|
| 1 | **Search Space** 🗺️ | Toate stările + operatorii | Definește limitele |
| 2 | **Initial State** 🟢 | Start | Poate fi >1 |
| 3 | **Final State** 🟥 | Ținta | Știi când te oprești |
| 4 | **Paths** 🛤️ | Secvențe start→țintă | Soluția = adesea drum |
| 5 | **Operators** ⚙️ | Mutări permise | Doar acțiuni valide |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🔲 §2. CĂUTARE NEINFORMATĂ (USS)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** cauți **fără busolă** — când nu ai heuristică sau vrei garanții.

| Algoritm | Ce face | De ce îl folosești | ⚠️ |
|----------|---------|-------------------|-----|
| **BFS** | Nivel cu nivel (val) | Cel mai scurt drum (pași egali) | Multă memorie |
| **DFS** | Adânc, apoi backtrack | Puțină memorie | Nu garantează optim |
| **Bi-directional** | Start + țintă, se întâlnesc | Reduce spațiul dramatic | — |

### 📝 La examen — BFS

Ordinea vizitării = **nivel cu nivel, stânga→dreapta** (ex: 50 → 17 → 72 → 12 → 23 → 54 → 76 → …).

> ⚠️ USS explorează mult inutil → de aceea există **ISS**.

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🎯 §3. CĂUTARE INFORMATĂ (ISS)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** cauți cu **heuristică** (busolă) — mult mai rapid.

```
f(n) = g(n) + h(n)
```

| Simbol | Semnificație | Regulă |
|--------|--------------|--------|
| **g(n)** | Cost real start→n | Nu ignora drumul parcurs |
| **h(n)** | Estimare n→țintă | Heuristica |
| **f(n)** | Scor total | Mai mic = mai promițător |

| Strategie | Formula / comportament |
|-----------|------------------------|
| **Best-First** | Cel mai bun f(n) |
| **Greedy** | Doar h(n) — rapid, nu neapărat optimal |
| **A\*** | g+h — **optimal dacă h admisibilă** (h ≤ cost real) |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# ⛰️ §4. CĂUTARE LOCALĂ
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** îmbunătățești **o soluție** — nu construiești arbore uriaș. Contează **rezultatul**, nu drumul.

| Metodă | Ideea | Risc |
|--------|-------|------|
| **Hill Climbing** ⛰️ | Cel mai bun vecin | Optimum local |
| **Simulated Annealing** 🔥 | Acceptă probabil mutări rele; T↓ | Parametri de reglat |
| **Tabu Search** 📋 | Evită stări recent vizitate | Anti-ciclu |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🧬 §5. ALGORITMI EVOLUTIVI (EA / GA)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** imită **evoluția** — populație de soluții, fitness, selecție, variație. **Foarte des la examen.**

### 🔄 Proces EA

```
1. Populație inițială (random, uniform distribuită dacă posibil)
2. Evaluează fitness
3. Selecție (cei buni au șanse mai mari)
4. Crossover (2 părinți) + Mutație (1 părinte)
5. Repetă până la stop
```

### 👥 Populație & generații

| Concept | Ce e | La examen |
|---------|------|-----------|
| **Individ** | Candidat la soluție | Nu e „animal” — e **soluție posibilă** |
| **Fitness** | Valoare adaptare | Asociază scor fiecărei soluții; reflectă adaptarea |
| **Generational (gg=1)** | Toată populația înlocuită | Fiecare individ supraviețuiește 1 generație; μ offsprings |
| **Steady-state (gg=1/μ)** | Înlocuiești doar dacă copilul e mai bun | Părintele rămâne dacă copilul e slab |
| **Elitism** 👑 | Păstrezi cei mai buni k | Nu pierzi best solution |

### 🧬 Genotype vs Phenotype

| | Genotype | Phenotype |
|---|----------|-----------|
| **Ce e** | Reprezentare internă (biți, permutare) | Soluția reală evaluată |
| **Fitness pe** | — | **Phenotype** |

### 📊 Reprezentări — la examen

| Problemă | Reprezentare corectă | ❌ Greșit |
|----------|---------------------|----------|
| **N-Queens** | Permutare size n (non-binary, discrete) | Binary |
| **Subset sum / knapsack** | Șir binary (1=include, 0=exclude) | — |
| **TSP** | Permutare | — |

**Fitness N-Queens:** numărul de regine care **se atacă reciproc** (minimizezi).

**Fitness subset cu sumă țintă S:** `−|(suma selectate) − S|` (maximizezi → suma cât mai aproape de S).

**Fitness 2 subseturi fără elemente comune, aceeași sumă:** diferența în valoare absolută între sumele celor două subseturi.

### 🔀 Variație

| Tip | Arity | Exemple |
|-----|-------|---------|
| **Mutație** | 1 părinte | Bit flip, swap, creep |
| **Crossover** | 2 părinți | Uniform (binary), OX (permutări), PMX |

> 📝 **Crossover binary la examen:** Uniform crossover ✅ · Insertion mutation ≠ crossover

> 📝 **Reprezentarea influențează:** tipul operatorilor de variație + expresia fitness-ului (NU neapărat mărimea populației)

### 🎲 Selecție (memorează toate)

| Metodă | La examen |
|--------|-----------|
| **Roulette-wheel** (proportional) | ✅ |
| **Tournament** | ✅ |
| **Rank-based** | ✅ |
| **Elitism (truncation)** | ✅ |
| **Gradient-descent selection** | ❌ NU e selecție EA |

### 🧬 Genetic Programming (GP)

| | EA clasic | GP |
|---|-----------|-----|
| **Individ** | Cromozom (biți, numere) | **Program / arbore** |
| **Crossover** | Gene | **Sub-arbori** |
| **Dezavantaj** | — | Bloating; depinde de parametri; precizie variabile |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🐦 §6. PARTICLE SWARM OPTIMIZATION (PSO)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** particule = soluții în mișcare; **cooperare** + **memorie**. Inspirat din **păsări / pești în școală**.

### 🌟 Elemente PSO (toate corecte la examen)

| Element | Rol |
|---------|-----|
| **Position** 📍 | Soluția curentă |
| **Velocity** 🚀 | Direcția și viteza |
| **Inertia (w)** ⚙️ | Menține direcția; constant sau descendent; balanță explorare/exploatare |
| **Memory** 💭 | Cea mai bună poziție personală (P_best) |
| **Social** 👥 | Influență de la G_best (global best) |

### 📐 Formula vitezei (memorează!)

```
v_id = w·v_id + c1·rand()·(P_best_d − x_id) + c2·rand()·(G_best_d − x_id)
```

| Simbol | Ce e |
|--------|------|
| **v_id** | Viteza particulei (NU actualizează direct poziția — viteza o face) |
| **w** | Inertia |
| **c1, c2** | Coeficienți cognitive / social (fixi, nu determinați automat) |
| **x_id** | Poziția curentă (apare indirect prin diferențe) |

**Viteza depinde de:** viteza veche + inertia + coeficient social + poziția curentă (prin P_best/G_best).

### 🆚 PSO vs GA

| | PSO | GA |
|---|-----|-----|
| **Memorie** | Particulele **au** memorie (P_best) | Indivizii **nu** au memorie individuală |
| **Cooperare** | Da (G_best) | Prin populație |

### 🛑 Condiții de stop PSO

- ✅ Număr prestabilit de **iterații**
- ✅ Fitness evaluat de **k ori** (k prestabilit)
- ❌ Nu rulează la infinit
- ❌ Nu te oprești când găsești c1 și c2

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🐜 §7. ANT COLONY OPTIMIZATION (ACO)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** furnici lasă **feromon** pe trasee — comunicare **indirectă**. Ideal pentru **graf orientat / TSP**.

### ⚙️ La examen — esențial

| Aspect | Detaliu |
|--------|---------|
| **Problema NP-hard → ACO** | Transformă în **drum optim pe graf orientat** |
| **Baza** | Urma de **feromon** (τ), NU evoluție / inerție PSO |
| **Operatori** | **Constructivi** — adaugă elemente la soluție parțială |
| **Căutare** | **Cooperativă**, ghidată de calitatea relativă |
| **Comunicare** | Prin **matrice feromon** / depozit chimic — NU direct |

### 📊 Probabilitatea alegerii următorului nod

Depinde de (toate la examen):

- **τ** — matrice feromon (trail)
- **η** — vizibilitate noduri (visibility)
- **α** — importanță feromon
- **β** — importanță vizibilitate
- ❌ NU crossover genetic

### 🐜 Comportament furnică

- ✅ Memorie (evită noduri deja vizitate în tur)
- ✅ Cooperare prin feromon
- ✅ Se mișcă și depune feromon pe traseu
- ❌ NU înlocuiește cei slabi cu cei buni (ăla e EA)

### 📋 Variante ACO

| Variantă | Când depune feromon |
|----------|---------------------|
| **AS** | După tur complet |
| **ACS** | La fiecare pas |
| **MMAS** | Doar cea mai bună; limite [min, max] |

### 🔄 Pași iterație ACO

1. Crește soluția parțială cu un element
2. Modifică feromonul pe trasee parcurse
3. Inițializare (la început)
4. ❌ NU mutație ca la GA

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# ♟️ §8. JOCURI & MINIMAX
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** doi jucători — tu **maximizezi**, adversarul **minimizează**.

| Concept | La examen |
|---------|-----------|
| **Minimax** | MAX tu, MIN adversar; propagare sus |
| **α-β pruning** | Taie ramuri fără a schimba rezultatul |
| **AND-OR trees** | OR=tu alegi, AND=adversar face orice; rădăcină=OR |
| **Strategii lineare** | Simetrie, perechi, paritate, DP |

| Tip joc | Exemplu |
|---------|---------|
| Deterministic + perfect info | Șah |
| Non-deterministic | Backgammon |
| Imperfect info | Poker |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 📚 §9. SISTEME BAZATE PE CUNOAȘTERE (KBS)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** raționament cu **fapte + reguli** — ca un expert codificat.

### 🏗️ Arhitectura RBS

```
KB (Facts + Rules) → Inference Engine → Concluzii
```

| KB conține | La examen |
|------------|-----------|
| **Facts** | ✅ |
| **Rules** | ✅ |
| **Optimum solutions** | ❌ |
| **Positions** | ❌ |

### 🔗 Inferență

| Tip | Direcție | Când |
|-----|----------|------|
| **Forward chaining** ➡️ | Date → concluzie | Ai fapte noi |
| **Backward chaining** ⬅️ | Țintă → explicație | Diagnostic |

**Forward chaining la examen (toate corecte):**
- IE poate trage concluzii noi
- Fapte în **working memory** (actualizată continuu)
- Acțiuni: adaugă/șterge din working memory
- Reguli: **LHS ⇒ RHS**

### 📋 Raționament

| Tip | Direcție |
|-----|----------|
| **Deduction** | Cauză + Regulă → Efect (sigur) |
| **Abduction** | Efect → Cauză probabilă (diagnostic) |
| **Induction** | Observații → Regulă nouă |

### ⚙️ Conflict resolution

First Applicable · Most Specific · Recency (LRU) · Best Rule (prioritization)

### 🕸️ Rețele semantice

Meronymy (parte) · Holonymy (tot) · Hyponymy (tip) · Hypernymy (general) · Synonymy · Antonymy

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🌫️ §10. FUZZY SYSTEMS & INCERTITUDINE
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** adevăr **parțial** [0,1] — nu doar da/nu.

### 🔄 Proces fuzzy

```
1. FUZZIFICATION  → input crisp → grade de apartenență μ
2. INFERENCE      → reguli fuzzy (IF temp low THEN cold)
3. DEFUZZIFICATION → fuzzy → valoare crisp (Centroid, etc.)
```

> 📝 **Defuzzification** = transformă fiecare regiune fuzzy într-o valoare crisp → **Adevărat**

### ⚙️ Operații

| Op | Formula |
|----|---------|
| AND | MIN(a,b) |
| OR | MAX(a,b) |
| NOT | 1−a |

**Mamdani:** output = fuzzy set pe variabilă de ieșire.

### 🎲 Bayes & Certainty Factors

| | Ce e |
|---|------|
| **Bayes** | Fapte/reguli cu probabilități |
| **CF** | Grad încredere 0–100% sau 0–1 |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🤖 §11. MACHINE LEARNING
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** înveți din **exemple** — nu scrii fiecare regulă manual.

### 🎓 Tipuri de învățare

| Tip | Labels? | La examen |
|-----|---------|-----------|
| **Supervised** | Da (perechi in/out) | Cauți funcție cunoscută input→output |
| **Unsupervised** | Nu | Găsești structură/model în date |
| **Reinforcement** | Reward/penalty | Trial and error |
| **Active** | Parțial | Cere date utile |

### 🎯 Probleme ML (la examen)

✅ **Regression** · ✅ **Classification** · ✅ **Planning** · ❌ doar etică/morală

**Obiectivul** algoritmului ML = reprezentat ca **funcții numerice** (și probabilistice).

### 📊 Train vs Test

| Regulă | La examen |
|--------|-----------|
| Aceeași **distribuție** | ✅ Obligatoriu |
| Seturi **disjuncte** (disjoint) | ✅ Dacă posibil |
| Test=real, train=teoretic | ❌ |

### 📈 Metrici clasificare

| Metrică | Formula | Când contează |
|---------|---------|---------------|
| **Accuracy** | corecte/total | Clase echilibrate |
| **Precision (P)** | TP/(TP+FP) | False positive costisitor |
| **Recall (R)** | TP/(TP+FN) | Ratăm ceva grav |
| **F1** | 2PR/(P+R) | **Media armonică** P și R |

### 🔬 Comparare algoritmi

✅ **Performance measures** · ✅ **Confidence intervals** · ❌ Divergence of accuracy

### 📏 Standardizare

= transformarea valorilor brute în **z-scores** (nu discretizare, nu scale effect introdus).

### 🎯 Alegerea algoritmului

Factor principal: **alinierea cu datele dorite / tipul problemei** (nu doar complexitatea).

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🔍 §12. CLUSTERING
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** grupezi date **fără etichete** — unsupervised learning.

| Afirmație | Corect? |
|-----------|---------|
| Folosește bază de date **nelabelată** | ✅ |
| Alt nume pentru **unsupervised learning** | ✅ |
| Proces în 2 pași: training + testing | ✅ |
| Folosește date labelate | ❌ |

**Obiectiv:** similaritate **mare** în cluster, **mică** între clustere.

| Tip | Când |
|-----|------|
| **Agglomerative** | Ierarhic, fuzionezi clusteri |
| **K-Means** | Știi k; rapid |
| **Density-Based** | Forme arbitrare |
| **Grid-Based** | Volume mari |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🧠 §13. REȚELE NEURONALE (ANN)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** neuroni + ponderi învățate — **cel mai testat topic** din questions.js.

### 🔌 Feed-Forward ANN

| Afirmație | Răspuns examen |
|-----------|----------------|
| Neuronii conectați prin **legături ponderate** | ✅ |
| Conexiuni între neuroni **din același strat** | ❌ False |
| Semnal backward în forward pass | ❌ |

**Structură `A:B:C:D`** = A intrări : B primul ascuns : C al doilea ascuns : D ieșiri.

> 📝 **Câți weights are un neuron din stratul ascuns?** = numărul de neuroni din **stratul anterior** (fără bias).
> - Ex: `226:15:10:2` → primul neuron ascuns = **226** weights
> - Ex: `4:6:2` → al 4-lea neuron ascuns = **4** weights
> - Ex: `150:15:20:2` → neuron din **ultimul strat** = **20** weights (de la stratul anterior)

### ⚡ Procesul unui neuron (fire process)

1. **Suma ponderată** a intrărilor (produs scalar input·weights)
2. **Funcție de activare** (transfer function)

| Funcție activare | La examen |
|------------------|-----------|
| Sigmoid, Linear, Gaussian, **Constant** | ✅ posibile |
| **Error function** | ❌ NU e activare |

**Transfer function (liniar):** ecuația unui **hiperplan** — limitează capacitatea neuronului.

### 🚫 Limite Perceptron

| Poate rezolva | Nu poate |
|---------------|----------|
| AND, OR | **XOR** |
| Separare **liniară** | Probleme non-lineare |

**Depășire limite:** ✅ **mai mulți neuroni / straturi** · ✅ **non-linearitate** · ❌ threshold continuu singur · ❌ „limitele nu pot fi depășite"

### 📚 Perceptron vs Delta Rule

| | Perceptron Rule | Delta Rule (Gradient Descent) |
|---|-----------------|-------------------------------|
| **Date** | O instanță | **Toate datele** (batch) |
| **Start** | Ponderi random | Ponderi random |
| **Convergență globală garantată** | ❌ | ❌ |
| **O singură trecere** | ❌ | ❌ |

**Perceptron algorithm:**
- Eroare = diferența y_real − o_calculat
- Modifică ponderile pe baza erorii per instanță
- Bazat pe **minimizarea erorii**

### 🔄 Backpropagation

| Corect | Greșit |
|--------|--------|
| Algoritm de **training** ANN | Garantează optimum global |
| Forward propagate → calculează output | Doar pentru rețele shallow |
| Backward propagate **eroarea** | Modifică structura (add/remove nodes) |
| Ajustare weights ∝ **learning rate × gradient** | Insensibil la funcția de activare |

**Pași backprop (corecte):** forward propagate · stabilește eroarea · backward propagate eroarea · distribuie erori pe conexiuni proporțional cu weights.

**Eroare la clasificare:** diferența output real − output dorit al rețelei.

### 🏁 Inițializare ANN

✅ **Ponderi random** (ex: [-1, 1]) · ❌ nu există inițializare · ❌ inputs zero · ❌ outputs random

### 📊 Capacitate model & adâncime

| | Corect |
|---|--------|
| **Non-linearitate** depășește capacitate limitată | ✅ |
| **Mai multe straturi în adâncime** | ✅ (universal approximation) |
| Reducere neuroni | ❌ |
| Adâncime = evită overfitting | ❌ (de fapt risc overfitting) |

**Teorema aproximării universale:** orice funcție poate fi aproximată cu rețea suficient de mare (condiții de continuitate).

### ⚠️ Probleme training

| Problemă | Cauză |
|----------|-------|
| **Vanishing gradient** | Sigmoid + **prea multe straturi** ascunse |
| **Dying ReLU** | Valorile **derivatei** (=0 pentru x≤0 → neuron „moare") |
| **ReLU** | **NU** are vanishing gradient când x>0; corectează probleme sigmoid |
| **Logistic/Sigmoid** | Suferă vanishing gradient; NU e linear |

### 🏗️ Structură exemplu clasificare

5 atribute, 4 clase → **`5:6:4`** (intrări : ascuns : ieșiri)

**150 pixeli B&W, cerc da/nu, 2 clase** → **Classification** (nu regression)

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🎨 §14. DEEP LEARNING & CNN
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** CNN pentru **imagini** — convolution + pooling + feature learning.

### 📦 Tensor

Generalizare scalar/vector/matrică la **orice număr de indici** — obiect matematic (NU doar imagine).

**Convoluție** = sumă finită (implementare practică a sumării infinite) cu **input + kernel**.

### 🖼️ ConvNet — 3 etape

```
1. CONVOLUTION   → filtre (kernel) pe pixeli
2. ACTIVATION    → ReLU etc. (detector stage)
3. POOLING       → reduce dimensiunea
```

| Afirmație | Corect? |
|-----------|---------|
| Greutățile kernel-ului se **învață** la training | ✅ |
| Rezultatele filtrelor **se combină** | ✅ (NU „never combined") |
| Feature learning **minimizează loss** extrăgând features utile | ✅ |
| Feature learning **înainte** de training | ❌ |
| Preprocesare ConvNet **mai mică** decât alte algo clasificare | ✅ |

### 🔍 Filtre & pooling

- **Convoluție pe imagini:** kernel glisează peste imagine
- **Max Pooling:** returnează **valoarea maximă** din zona acoperită de kernel
- **Avantaj ConvNet:** arhitectură inspirată din cortex; **preprocesare redusă**

### 📊 Loss & output layers — vezi §16

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 🌳 §15. DECISION TREES & GENETIC PROGRAMMING
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Scop:** arbori de decizie (interpretabili) + GP (evoluezi programe).

### 🌳 Decision Trees

| | Corect | Greșit |
|---|--------|--------|
| **Scop** | Împarte colecția în seturi mai mici prin reguli succesive | Noduri decizie la frunze |
| **Induction** | Construcție **din training data**; top-down sau bottom-up | Etichetare date noi (= solving) |
| **Pruning** | Elimină ramuri zgomot/excepții (post) sau oprește creșterea (pre) | — |
| **Selecție atribut** | Poate fi **random** | — |

**Information Gain Ratio** = Information Gain / Split Information → reduce bias spre atribute multivalued.

### 🧬 GP vs EA

| GP individ | EA individ |
|------------|------------|
| **Program** (arbore) | Cromozom (biți, permutare) |

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# 📐 §16. FORMULE & COMPATIBILITĂȚI DE MEMORAT
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

### 🔍 Căutare

```
f(n) = g(n) + h(n)     |     h admisibilă: h(n) ≤ cost real
```

### 🤖 ANN — compatibilitate activare ↔ loss (EXAMEN!)

| Output | Distribuție | Strat output | Loss |
|--------|-------------|--------------|------|
| **Continuous** | Gaussian | **Linear** | **MSE** |
| **Discrete (multi-class)** | Multinoulli | **Softmax** | **Cross Entropy** |
| **Binary** | Bernoulli | **Sigmoid** | **Binary Cross Entropy (BCE)** |

> ❌ Softmax + MSE · ❌ Linear + Cross Entropy pentru multi-class · ❌ Cross Entropy + arctangent

### 📉 Loss functions

| Loss | Detaliu |
|------|---------|
| **MSE** | Regresie, output linear |
| **Cross Entropy** | Clasificare; diferența între distribuții probabilitate; **cu Softmax** |
| **BCE** | Clasificare binară + Sigmoid |
| **L1 (MAE)** | Media sumei diferențelor **absolute** actual vs predicted |

### 🐦 PSO

```
v = w·v + c1·rand()·(P_best − x) + c2·rand()·(G_best − x)
```

### 🐜 ACO probabilitate

Depinde de: **τ** (feromon), **η** (vizibilitate), **α**, **β**

### 🌫️ Fuzzy

AND=MIN · OR=MAX · NOT=1−x

### 📊 ML metrici

```
Precision = TP/(TP+FP)    Recall = TP/(TP+FN)    F1 = 2PR/(P+R)
Accuracy = corecte/total
```

---

<div align="center">

# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
# ⚡ §17. CHEAT SHEET EXAMEN (din questions.js)
# ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

</div>

> 🎯 **Recapitulare rapidă** — ce apare cel mai des la examen.

### ✅ Adevărat — memorează

| Topic | Răspuns scurt |
|-------|---------------|
| Perceptron rezolvă | Separare liniară, AND, OR |
| Perceptron NU rezolvă | **XOR** |
| Depășire limite perceptron | Mai mulți neuroni / straturi + **non-linearitate** |
| Feed-forward conexiuni | **Weighted links** între straturi diferite |
| ANN init | **Random weights** |
| Weights neuron ascuns | = nr. neuroni strat anterior |
| Backprop | Training algo; eroare **backward**; Δw ∝ lr × gradient |
| Vanishing gradient | Prea multe straturi + **sigmoid** |
| Dying ReLU | Problema **derivatei** (=0) |
| ReLU | NU vanishing gradient când x>0 |
| Universal approximation | Orice funcție aproximabilă cu rețea suficientă |
| Tensor | Generalizare matrice, orice nr. indici |
| ConvNet | Convoluție + activare + pooling; kernel weights learned |
| Max pooling | **Max** din regiunea kernel |
| Clustering | Unsupervised, unlabeled, train+test |
| F1 | Media armonică P și R |
| Train/Test | Aceeași distribuție, seturi disjuncte |
| DT induction | Din **training data** |
| GP encoding | **Computer program** |
| EA individ | **Candidate solution** |
| Fitness | Asociază valoare; reflectă adaptare |
| GA selection | Roulette, Tournament, Rank, Elitism |
| Binary crossover | **Uniform** |
| Generational EA | gg=1; părinți înlocuiți complet; μ offsprings |
| PSO vs GA | PSO: particule **cu memorie** |
| PSO elements | Inertia, Memory, Velocity, Position |
| PSO stop | Iterații sau k evaluări fitness |
| ACO | Graf orientat; feromon; τ, η, α, β |
| ACO operators | **Constructivi**, cooperativi |
| Forward chaining | Working memory, LHS⇒RHS, concluzii noi |
| KB RBS | **Facts + Rules** |
| Defuzzification | Fuzzy → crisp (**True**) |
| Softmax | Output → **probabilități** clase |
| Standardizare | **Z-scores** |
| Gradient descent | Eroare pe **tot setul** de train |

### ❌ Fals — capcane frecvente

| Capcană | De ce e fals |
|---------|--------------|
| Perceptron rezolvă XOR | Nu e linear separable |
| Conexiuni intra-layer feed-forward | Doar între straturi |
| Backprop garantează optimum global | Poate minime locale |
| Cross-entropy fără softmax | Se folosește **cu** softmax |
| Clustering cu labels | E **unsupervised** |
| ACO = PSO / evoluție | Baza = **feromon** |
| Dying ReLU = vanishing gradient | E vorba de **derivata** ReLU |
| ReLU: y=0 when x>0 | E invers: y=0 când x≤0 |
| Sparsity ReLU când x>0 | y=0 când x≤0 |
| Adding depth evită overfitting | Risc **overfitting** |
| DT: decision nodes at leaves | Decision=intern, result=frunze |
| Induction = label new data | Induction=**build**; solving=apply |

---

<div align="center">

## 🍀 SUCCES LA EXAMEN!

**Ordine recomandată de studiu:** §0 → §13 (ANN) → §5-7 (EA/PSO/ACO) → §11-12 (ML) → §16 → §17

</div>
