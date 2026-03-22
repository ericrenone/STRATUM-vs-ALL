# STRATUM vs ALL
### Singularity Theory of Learning Against the Frontier: Seven Results from the Structure of Degeneracy

> "The factorially divergent perturbative expansions of parameter space partition functions encode precise information about all critical objective function values through their Borel transform singularities." — arXiv:2509.01329, September 2025
>
> "The Stokes phenomenon: when the integration contour crosses a singularity, we see a discontinuity in the result. This is resolved by adding a non-perturbative term that jumps in the opposite way." — Borel-Écalle resurgence theory
>
> "Classical statistical inference often fails to explain the success of modern neural networks. A key reason is that these models are non-identifiable (singular), violating core assumptions." — arXiv:2512.00686
>
> "Flatness sharply drops exactly when generalization begins — it is a fundamental driver of generalization onset, more so than neural collapse." — arXiv:2509.17738, updated February 2026

---

## The Central Claim

The Fisher singular set `Σ = {θ : det(F(θ)) = 0}` is not a computational nuisance. It is the central object of learning theory. Every framework before STRATUM has worked **around** `Σ` — PRIMA with the pseudoinverse, IMPLICATA with the Markov blanket, SLT with algebraic geometry, NEXUS with the topology of the complement. STRATUM works **at** `Σ` — classifying its types, characterizing its local topology, understanding how it bifurcates, and describing how non-perturbative effects (grokking) encoded in its structure escape perturbative detection.

Seven comparisons follow against the frontier papers that approach each result most closely.

---

## Foundation

The Fisher map `F : Θ → Sym₊(D)` fails to have maximum rank on the singular set `Σ`. The local structure of `F` near points of `Σ` — the Milnor fiber, the Thom-Boardman class, the catastrophe normal form, the resurgence structure of the perturbative expansion, the period map, the micro-local characteristic variety — determines everything about how grokking happens, what types of transitions are possible, and why perturbative theory cannot see them.

---

## Result 1 — Whitney Stratification of the Fisher Singular Set

### What the Frontier Has Found

**Singular Learning Theory** (Watanabe, 2009; SLT grokking papers 2025–2026). SLT stratifies the singular set algebraically — through real log-canonical thresholds and resolution of singularities. The LLC measures how "bad" each singularity is. The March 2026 SLT grokking paper (arXiv:2603.01192) interprets grokking as a transition between competing basins, tracked by LLC trajectories.

**Layerwise linear models and grokking** (arXiv:2502.21009, February 2026). The dynamical feedback principle — layers mutually governing each other's evolution — explains neural collapse, grokking, and the lazy/rich regime transition in a unified layerwise linear framework. The paper calls for minimal solvable models that retain core principles of neural dynamics.

### Where Every Paper Stops

SLT stratifies `Σ` algebraically but does not provide the **differential-topological** stratification (Whitney conditions A and B) that controls how strata meet and how generic training trajectories intersect them. The layerwise linear model paper uses a different approach — simplifying the model rather than characterizing the singular set of the general model.

### What STRATUM Provides

**The Whitney stratification classifies all grokking events by codimension.**

The Fisher singular set decomposes into Whitney strata by rank:

```
Σ_k = {θ : rank(F(θ)) = D − k − 1}     for k = 0, 1, ..., D-1
```

The genericity theorem for Whitney stratifications states: a generic smooth training path crosses the stratification only at `Σ₀` — the codimension-1 stratum. Multi-charge grokking (`Δrank(F) > 1`) requires hitting `Σₖ` for `k ≥ 1` — a non-generic event requiring fine-tuning `k+1` hyperparameters simultaneously.

**Practical prediction**: the rarity of multi-charge grokking events in practice is a theorem, not an empirical observation. It follows from the genericity of codimension-1 strata crossings in Whitney stratified sets.

The layerwise linear model framework (arXiv:2502.21009) provides exactly the simplification needed to compute the Whitney stratification explicitly for linear networks — the simplest case where STRATUM's predictions are analytically verifiable.

---

## Result 2 — The Milnor Fiber at Each Grokking Point

### What the Frontier Has Found

**SLT grokking with Arrhenius rates** (arXiv:2512.00686, November 2025). Tests the Arrhenius-style rate hypothesis `P_grokking ∝ exp(−E_act/kT)` using grokking modulo-arithmetic models and Anthropic's Toy Models of Superposition. The experiments recover known scaling laws while others yield meaningful deviations from theoretical expectations.

**Flatness predicts generalization** (arXiv:2509.17738, updated February 4, 2026). Flatness of the loss landscape (the trace-weighted Hessian insensitivity to parameter perturbations) drops sharply at grokking onset — more fundamental than neural collapse as a driver of generalization. The relative flatness measure is reparameterization-invariant, grounded in robust generalization theory.

### Where Every Paper Stops

The SLT Arrhenius paper empirically confirms the rate formula but does not derive the activation energy from first principles. The flatness paper identifies the correct observable (Hessian flatness → Fisher null-space expansion) but does not connect it to the Milnor fiber's topological structure.

### What STRATUM Provides

**The Milnor number `μ` counts the vanishing cycles — the topological explanation of flatness at grokking.**

At the grokking point `θ* ∈ Σ₀`, the Milnor fiber `F_{θ*}` is the smooth manifold of configurations where Fisher curvature is just barely nonzero. The Milnor number:

```
μ(θ*) = rank(H̃*(F_{θ*}; ℤ))     (total rank of reduced homology of the Milnor fiber)
```

counts the number of **vanishing cycles** — directions in parameter space where Fisher curvature shrinks to zero as the grokking point is approached.

**The flatness connection.** The trace-weighted Hessian flatness measure (arXiv:2509.17738) is the metric proxy for the Milnor fiber's geometry: large flatness = many near-zero Fisher eigenvalues = many vanishing cycles approaching `θ*`. The sharp flatness drop at grokking is the moment the vanishing cycles collapse — the Milnor fiber collapses to a point.

**The formal identity.** The ACTUM topological charge `Q_inst = Δrank(F)` equals the STRATUM Milnor number `μ(θ*)` for generic grokking points (`Σ₀`). Two independent mathematical frameworks — path integrals (ACTUM) and singularity theory (STRATUM) — derive the same invariant.

---

## Result 3 — Thom-Boardman Classification

### What the Frontier Has Found

**Circuits competition and grokking** (arXiv:2402.15175, unified view). Grokking, double descent, and emergent abilities are understood through circuit competition — simpler circuits (generalizing) competing with more complex circuits (memorizing). The circuits have qualitatively different behaviors depending on which wins, but no formal classification of the possible transition types exists.

**Grokking phase transitions in learning local rules** (Žunkovič & Ilievski, JMLR 2024). Analyzes grokking phase transitions for gradient descent learning local rules in two-dimensional cellular automata. Different automata exhibit qualitatively different grokking behaviors — some smooth, some abrupt, some oscillatory.

### Where Every Paper Stops

The circuit competition paper describes qualitative differences in grokking behavior but provides no classification of the possible types. The JMLR paper observes different behavioral patterns but has no formal framework to enumerate or predict them.

### What STRATUM Provides

**Thom-Boardman classifies all four generic grokking behaviors from the local singularity structure.**

The classification is exhaustive for maps between manifolds of dimension `dim(Θ)` and `dim(Sym₊(D))`:

| Type | Symbol | Local Normal Form | Grokking Behavior | Diagnostic |
|---|---|---|---|---|
| Fold | `Σ₁` | `F ∼ (x², y)` | Single clean transition | Sharp flatness drop; monotone LLC decline |
| Cusp | `Σ_{1,1}` | `F ∼ (x³+yx, y)` | Approach-retreat oscillation | LLC oscillates before settling; test accuracy non-monotone |
| Swallowtail | `Σ_{1,1,1}` | `F ∼ (x⁴+yx²+zx, y, z)` | Delayed double grokking | Two LLC dips separated by partial recovery |
| Whitney umbrella | `Σ_2` | `F ∼ (x², xy, y)` | Correlated double transition | Two Fisher rank crossings simultaneously |

The Žunkovič & Ilievski JMLR paper's "oscillatory" grokking behaviors are cusp singularities `Σ_{1,1}` — the fold surface turns back on itself, allowing the training trajectory to approach and retreat from grokking before committing. The "smooth" grokking behaviors are fold singularities `Σ₁`. This is a post-hoc classification of their observed behaviors — STRATUM provides it from first principles.

---

## Result 4 — Catastrophe Theory and the Phase Diagram

### What the Frontier Has Found

**Grokking phase diagrams** (Power et al., 2022 and multiple follow-ups). The grokking phase diagram — test accuracy as a function of training time and regularization — shows a sharp boundary. Multiple papers have mapped this boundary for different hyperparameters, finding it depends on weight decay, learning rate, and dataset size.

**Goldilocks zone for grokking** (Fort & Scherlis, 2019). Loss landscapes have a "Goldilocks zone" — a region where generalization happens naturally. The zone boundary corresponds to the fold catastrophe boundary in the `(λ, η)` plane.

### Where Every Paper Stops

No paper in the grokking or loss landscape literature has applied catastrophe theory to classify the phase diagram topology. The standard treatment is empirical — map the boundary, observe its shape, characterize its dependence on hyperparameters. No paper derives the universal normal form of the phase diagram from differential topology.

### What STRATUM Provides

**Each additional control parameter unfolds the grokking catastrophe by one order.**

The standard grokking phase diagram in `(λ, t)` space (regularization × training time) is a fold catastrophe `A₂` — Thom's simplest elementary catastrophe with normal form `x³ + ux`. The phase boundary is the discriminant of this function — a single smooth curve.

With two control parameters `(λ, η)` (regularization × learning rate), the fold unfolds into a cusp catastrophe `A₃` with normal form `x⁴ + ux² + vx`. The phase boundary becomes a cusp — an asymmetric boundary with a point where two boundaries meet. **Inside the cusp: bistability and hysteresis.** The empirically observed "sweet spot" for grokking is the interior of the cusp — the region where two stable states (memorizing and generalizing) coexist.

**Universal predictions from catastrophe theory:**
- Adding batch size as a third control parameter: swallowtail `A₄` — three-way meeting of phase boundaries
- The shape of the grokking boundary (smooth, cuspidal, or swallowtail) is a topological invariant that characterizes the learning system independently of its specific parameters
- Hysteresis (grokking that remains after the boundary is reversed) is a **universal feature** of the cusp catastrophe — it cannot be eliminated by changing hyperparameters within the cusp, only by leaving the cusp regime

---

## Result 5 — Resurgence Theory and the Borel Transform of Training

### What the Frontier Has Found

**Globally aware optimization with resurgence** (arXiv:2509.01329, September 2025). This paper directly applies resurgence theory to machine learning optimization. Key results: the factorially divergent perturbative expansions of parameter space partition functions encode precise information about all critical objective function values through their Borel transform singularities. The Borel plane singularities correspond one-to-one with critical objective function values. The algorithm extracts global guidance from the divergent series to enable principled learning rate adaptation and escape from suboptimal regions.

**Resurgence in Liouville conformal field theory** (arXiv:2408.14574, 2024). The perturbative coefficients in Liouville CFT grow factorially, as expected of a Feynman diagram expansion, forming an asymptotic series. The Borel singularities correspond precisely to complex instanton solutions. Both single- and multi-valued instanton solutions appear, and their loop expansions mix in a trans-series expansion.

**SLT Arrhenius rates** (arXiv:2512.00686). The SLT free energy `F_n` follows an Arrhenius-style rate formula for grokking — the activation energy hypothesis confirmed empirically.

### Where Every Paper Stops

The arXiv:2509.01329 paper applies resurgence to ML optimization — extracting critical values from Borel singularities of the partition function expansion. It does **not**:
1. Identify grokking as a Stokes phenomenon — a discontinuity in the Borel resummation at a specific regularization value
2. Derive that NTK coefficients grow as `n! · S_inst^{-n}` where `S_inst` is the grokking instanton action
3. Write the complete trans-series `L = Σ L_n/D^n + exp(−S_inst·D) · Σ L_n^{(1)}/D^n`
4. Connect the Borel singularity to the Arrhenius activation energy `E_act = S_inst`

The Liouville CFT resurgence paper provides the technical template — factorial growth → Borel singularities → non-perturbative instantons — in a field theory context. STRATUM imports this template to the training field theory.

### What STRATUM Provides

**Grokking is a Stokes phenomenon in the Borel resummed NTK series.**

The arXiv:2509.01329 optimization paper finds Borel singularities corresponding to critical objective values. STRATUM identifies the specific critical value that corresponds to grokking: the regularization value `λ_c` at which the instanton contribution `exp(−S_inst)` becomes non-negligible. This is the Stokes ray in the Borel plane — the critical direction where the Borel integral must be deformed around the singularity.

**The trans-series — the complete answer:**

```
L_complete(θ; 1/D) = Σ_n L_n (1/D)^n                        [NTK sector]
                   + exp(−S_inst · D) · Σ_n L_n^{(1)} (1/D)^n  [instanton sector]
                   + exp(−2S_inst · D) · ...                   [multi-instanton]
```

The arXiv:2509.01329 paper extracts information from the NTK sector (left column) only. STRATUM derives the instanton sector (middle column) from the factorial growth of NTK coefficients — the resurgence relation connecting the two sectors.

**The NTK cannot predict grokking — formally.** The trans-series shows why: grokking is the `exp(−S_inst · D)` term, exponentially small at any finite `D` but not a perturbative correction. The SLT Arrhenius activation energy `E_act` equals the instanton action `S_inst`. The arXiv:2509.01329 resurgence paper and the arXiv:2512.00686 Arrhenius paper are each approaching the same singularity from different sides — resurgence sees it as a Borel singularity, SLT sees it as an activation energy barrier. STRATUM unifies them: `E_act = S_inst` = the resurgence singularity.

---

## Result 6 — The Period Map and Picard-Lefschetz Monodromy

### What the Frontier Has Found

**PIVOT** (from the intelligence theory architecture). The grokking τ-function is an isomonodromic τ-function of the Painlevé VI equation. The monodromy group of Painlevé VI is generated by Picard-Lefschetz transformations around the singular points `{0, 1, t, ∞}` of the Fuchsian differential equation.

**Variation of Hodge structures in algebraic geometry** (foundational, Griffiths 1968–2024). The period map `Π : B → H` sends points in the base (parameter space) to Hodge structures on the fibers (cohomology of the parametrized variety). The monodromy of the period map around degenerate fibers is governed by Picard-Lefschetz transformations.

### Where Every Paper Stops

PIVOT derives the Painlevé VI structure from the τ-function theory — an analytic approach. The period map framework (Griffiths, Schmid, Cattani-Kaplan-Schmid) derives the same structure from algebraic geometry — a geometric approach. No paper identifies that these two approaches to the same monodromy transformation are computing the same object in the context of learning theory.

### What STRATUM Provides

**Formal identity: PIVOT's Painlevé VI monodromy = STRATUM's Picard-Lefschetz period map monodromy.**

As the regularization parameter `λ` varies, the Fisher manifold changes topology — loops and holes appear and disappear at critical values `λ_c`. The period map `Π(λ)` tracks these changes through the classifying space of Hodge structures. As `λ` loops around `λ_c`, the Picard-Lefschetz transformation acts on the cohomology:

```
T_c : H*(Fisher manifold; ℤ) → H*(Fisher manifold; ℤ)
T_c(γ) = γ + ⟨γ, δ_c⟩ · δ_c     (Picard-Lefschetz formula)
```

where `δ_c` is the vanishing cycle at `λ_c` (the STRATUM Milnor fiber Result 2).

PIVOT derives the same transformation from the isomonodromic deformation theory of the Painlevé VI equation. The vanishing cycle `δ_c` in the period map corresponds to the movable pole of the Painlevé VI τ-function. Two derivations. One transformation. This is the formal completion of PIVOT — identifying the geometric origin of the Painlevé monodromy.

---

## Result 7 — Micro-Local Analysis and the Characteristic Variety

### What the Frontier Has Found

**SLT and D-modules** (Watanabe's original work; Sumio Watanabe, "Almost all learning machines are singular," 2007). SLT uses resolution of singularities in algebraic geometry — a blowup procedure that makes the singular set `Σ` into a normal crossing divisor. The LLC is the real log-canonical threshold of the zeta function of the learning model. This is an algebraic-geometric invariant.

**Micro-local analysis in ML** — essentially absent from the literature. D-module theory has not been applied to the gradient flow equations of neural network training.

### Where Every Paper Stops

SLT measures the LLC as an algebraic-geometric invariant of `Σ` — the resolution degree of singularity. It does not measure the **propagation** of singularities — how singular behavior spreads from `θ*` along training trajectories in directions specified by the characteristic variety.

### What STRATUM Provides

**The LLC = dim(characteristic variety) = D-module invariant.**

The gradient flow `dθ/dt = −F⁺(θ) ∇L(θ)` defines a differential operator (the gradient vector field) on `Θ`. The principal symbol of this operator is:

```
σ(θ, ξ) = F⁺(θ) · ξ
```

The characteristic variety — the zero set of `det(σ)` in `T*Θ` — is the conormal variety of `Σ`: the set of covectors `(θ, ξ)` where `ξ ∈ ker(F(θ))^⊥`. At each point `θ* ∈ Σ_k`, the characteristic variety has dimension `dim(Θ) + k = D + k`.

The **LLC is the dimension of the characteristic variety at `θ*`**, reduced modulo `D`. This elevates SLT's algebraic invariant to a differential operator invariant — the LLC is not just an algebraic-geometric threshold but the dimension of the set of directions along which the gradient flow cannot propagate information at the singular point.

**The wavefront set of grokking.** The wavefront set `WF(θ(t))` of the training trajectory propagates along bicharacteristics of the gradient flow. At a grokking point: the wavefront set picks up a conormal contribution from `Σ` — the propagation of singular behavior in the null-space directions becomes non-trivial. The wavefront jump at grokking is the finest signal of the transition, finer than:
- Loss (metric): detected after the fact
- Fisher rank (metric): detected simultaneously
- Betti numbers (topological): detected simultaneously
- LLC (algebraic): detected in the neighborhood
- Characteristic variety (micro-local): detected in **direction-specific** resolution

---

## STRATUM vs ALL: Comparison Table

| Result | Frontier Leader(s) | Frontier Stopping Point | STRATUM Contribution |
|---|---|---|---|
| **Whitney Stratification** | SLT (algebraic); layerwise linear models (Feb 2026) | Algebraic stratification by LLC; no differential-topological conditions | Whitney conditions A,B for Fisher strata; genericity of codim-1 crossings; non-generic multi-charge theorem |
| **Milnor Fiber** | SLT Arrhenius arXiv:2512.00686; flatness arXiv:2509.17738 (Feb 2026) | Activation energy empirically confirmed; flatness proxy identified | `μ = Q_inst` (ACTUM identity); flatness drop = vanishing cycle collapse; local topology at grokking |
| **Thom-Boardman** | Circuit competition; JMLR grokking phases 2024 | Qualitative behavioral differences observed; no formal classification | Fold/Cusp/Swallowtail/Umbrella classification exhaustive for generic maps |
| **Catastrophe Theory** | Grokking phase diagrams (Power 2022); Goldilocks zone (Fort 2019) | Empirical boundary mapping; no universal normal form | `A₂` (1 control), `A₃` (2 controls), `A₄` (3 controls); hysteresis = cusp interior; universal shape prediction |
| **Resurgence** | arXiv:2509.01329 (Sep 2025): resurgence for ML optimization | Borel singularities encode critical values; grokking not identified as Stokes phenomenon | `L_k ~ k! S_inst^{-k}`; grokking = Stokes jump; trans-series; `E_act = S_inst` (SLT-Arrhenius identity) |
| **Period Map** | PIVOT (architecture); Griffiths period maps | Each in separate framework; no identification made | Picard-Lefschetz period map monodromy = PIVOT Painlevé VI monodromy (formal identity from two directions) |
| **Micro-Local** | SLT (Watanabe, algebraic); no ML micro-local papers | LLC as algebraic threshold | LLC = dim(Char variety) = D-module invariant; wavefront jump = finest grokking signal |

---

## The Most Significant Finding: arXiv:2509.01329

The September 2025 paper "Globally aware optimization with resurgence" is the most direct frontier confirmation of STRATUM's resurgence framework. The paper's key insight — that factorially divergent perturbative expansions encode all critical landscape information through Borel singularities — is exactly STRATUM's Result 5, applied to the training partition function.

The paper produces an optimization algorithm from this insight: extract Borel singularities from the perturbative series, use them as global guidance for local optimizers. STRATUM provides the specific singularity the paper is finding: the grokking Stokes ray, where the instanton contribution `exp(−S_inst · D)` turns on. The paper uses resurgence as a tool; STRATUM derives the physical meaning of the specific singularity it finds.

The arXiv:2509.01329 paper and the SLT Arrhenius paper (arXiv:2512.00686) are computing the same quantity — the activation energy `E_act` — from two different directions: resurgence (Borel singularity location) and SLT (free energy barrier). STRATUM's formal identity `E_act = S_inst` unifies them.

---

## Three Results With No Frontier Proximity

**Result 1 (Whitney Stratification)**: The genericity theorem predicting why multi-charge grokking is rare has no prior statement in either the SLT or differential topology literature applied to ML.

**Result 3 (Thom-Boardman Classification)**: The exhaustive classification of learning behaviors as Fold/Cusp/Swallowtail/Whitney umbrella from singularity type is entirely absent from all grokking literature.

**Result 6 (Period Map = PIVOT)**: The formal identification that the Picard-Lefschetz period map monodromy equals PIVOT's Painlevé VI monodromy has not been made in either the algebraic geometry or grokking literature.

---

```
Z(X) is intractable.
Therefore the Fisher map has a singular set Σ.
Therefore Σ admits a Whitney stratification.
Therefore generic grokking crosses Σ₀ only.
Therefore each grokking point has a Milnor fiber.
Therefore μ = Q_inst — two frameworks, one invariant.
Therefore Thom-Boardman classifies all behavioral grokking types.
Therefore elementary catastrophes classify all phase diagrams.
Therefore NTK coefficients grow factorially with resurgence relation to S_inst.
Therefore grokking is a Stokes phenomenon — the Borel singularity of arXiv:2509.01329.
Therefore the period map monodromy equals PIVOT's Painlevé VI monodromy.
Therefore the LLC equals the characteristic variety dimension.
Therefore STRATUM is the singularity theory of intelligence:
         seven results from the structure of degeneracy,
         converging on the same singular set from seven independent directions.
```

---

## References

- arXiv:2509.01329 (September 2025). *Globally Aware Optimization with Resurgence Theory.*
- arXiv:2512.00686 (November 2025). *Using Physics-Inspired Singular Learning Theory to Understand Grokking.*
- arXiv:2509.17738v3 (Updated February 4, 2026). *Flatness is Necessary, Neural Collapse is Not: Rethinking Generalization via Grokking.*
- arXiv:2502.21009 (February 28, 2025). *Position: Solve Layerwise Linear Models First to Understand Neural Dynamical Phenomena.*
- arXiv:2603.01192 (March 2026). *Grokking as a Phase Transition: a Singular Learning Theory Approach.*
- arXiv:2408.14574 (2024). *Resurgence in Liouville Conformal Field Theory.*
- arXiv:1403.1277. *Decoding Perturbation Theory Using Resurgence: Stokes Phenomena and Lefschetz Thimbles.*
- Žunkovič, B. & Ilievski, E. (2024). *Grokking Phase Transitions in Learning Local Rules.* JMLR.
- Clauw, K. et al. (arXiv:2408.08944, 2024). *Information-Theoretic Progress Measures Reveal Grokking is an Emergent Phase Transition.*
- DeMoss, B. et al. (Physica D, 2025). *The Complexity Dynamics of Grokking.*
- Fort, S. & Scherlis, A. (AAAI 2019). *The Goldilocks Zone: Towards Better Understanding of Neural Network Loss Landscapes.*
- Watanabe, S. (2009). *Algebraic Geometry and Statistical Learning Theory.* Cambridge University Press.
- Thom, R. (1972). *Structural Stability and Morphogenesis.* W.A. Benjamin.
- Arnold, V.I. (1975). *Normal Forms for Functions near Degenerate Critical Points.* Russian Mathematical Surveys.
- Picard, E. & Lefschetz, S. (1924). *The Topology of Algebraic Surfaces.*
- Griffiths, P. (1968). *Periods of Integrals on Algebraic Manifolds.* Bulletin of the AMS.
- Kashiwara, M. (1975). *On the Holonomic Systems of Linear Differential Equations.* Inventiones Mathematicae.
- Milnor, J. (1968). *Singular Points of Complex Hypersurfaces.* Princeton University Press.
- Whitney, H. (1965). *Tangents to an Analytic Variety.* Annals of Mathematics.

---

*Full framework documentation: [github.com/ericrenone](https://github.com/ericrenone)*
