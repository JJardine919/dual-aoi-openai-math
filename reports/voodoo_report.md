# Voodoo report: what the OpenAI math release missed

Date: 2026-11-24. Reader: Voodoo, working alone.

## What I read, and what I couldn't

I read every family summary and every abstract in CONTENTS.md: 375 families and 730 manuscripts, numbered 001 to 380 with 045, 061, 070, 123 and 163 missing. I also read the release's own README.md and history.md, and the Lean "Comparator challenge" statement files for the results I lean on below. These were in the partly downloaded math.tar.gz.

The archive is truncated (`gzip: unexpected end of file`). preprints/ and lean/docs/ did not come out, so I read no full proofs. Everything below comes from abstracts, family summaries, release notes and Lean theorem statements. I did not open bigj_answer.txt, any prior audit, or anything listed as off-limits.

Confidence scale: **High** means it is stated directly in the abstracts or Lean files. **Medium** means it is my inference from stated facts plus standard mathematics. **Low** means it is a plausible lead that needs the full paper.

---

## A. Hidden keystones: one result many others lean on

### A1. One zero-free region under four number-theory families. Confidence: high for the links, medium for the risk.
- **003** proves Dirichlet L-functions (and ζ) have no zeros in Re s > 7/8. This is Lean-formalized (QuasiRiemannHypothesis, DirichletSevenEighths, HeckeSevenEighths, SiegelZeros).
- **182** (prime-argument paper) says it "uses the companion zero-free half-plane theorem for Dirichlet L-functions".
- **142** (deterministic polynomial factoring over F_p with no GRH) says it "uses the uniform Hecke zero-free theorem from the companion paper *Primitive roots for every admissible integer base*" (**029**).
- The second paper in **029** (simultaneous primitive roots) "assumes four explicitly stated analytic and sieve inputs from the companion paper".
- Why it matters: 142 and 029 have **no Lean formalization**. The zero-free theorem 142 actually uses is a different, unformalized "uniform Hecke" theorem inside 029, not the formalized 003. A reader of 142 alone sees "no GRH needed" and misses that it rests on a new, unformalized analytic theorem.
- The README says 003 (and 032) were the two results **not** made by the standard pipeline, and the 11/12 write-up was human-edited. Inside 003 the two write-ups state different half-planes (7/8 and 11/12). The 7/8 one is the one formalized.
- Consequence nobody states: a zero-free half-plane Re s > 7/8 for ζ gives a prime number theorem error term of about x^(7/8+ε). That would be a headline result in itself, and no family mentions it. Confidence medium; this is standard theory, but I haven't checked it against the paper.

### A2. The Hodge chain already broke once. Confidence: high.
- **032** (rational Hodge for CM abelian varieties) is the other result made outside the standard pipeline. **001** (Milne) uses it directly. The 032 summary also claims, through it, the Tate conjecture for all abelian varieties over finite fields and the Hodge standard conjecture.
- history.md (Oct 7): a sign error in "Algebraicity of Weil classes on split abelian eightfolds" forced withdrawal of that paper and two papers built on it, including Kuga–Satake and K3-product Hodge papers.
- Family 032 still holds closely related papers on Weil classes (Oct 6), a K3 Kuga–Satake locus (Sep 30), and a "conditional reduction" Kuga–Satake paper (Sep 10). This is the one area where a dependency chain has already failed in public, and the surviving neighbours share its methods. It deserves the most scrutiny of the algebraic-geometry block.

### A3. Conditional chains inside families. Confidence: high.
Many families state a result **assuming** a sibling paper's result. The chain closes only if the sibling holds:
- 014: Arthur enhancements assume the "finite-level Ramanujan–Arthur decomposition"
- 029: four inputs from a sibling
- 034: the whole family title is conditional on log Iitaka subadditivity, which comes from 033; one paper also assumes abundance
- 211: "stated Brownian/LQG inputs"
- 216: center-magnetization "assuming critical-height, renormalization, spin-field inputs"
- 218: "assuming deterministic critical-reference estimates"
- 224: two papers take Cardy's formula as input
- 260: the charged Penrose result uses the neutral one
- 335 and 348: each uses a companion classification as a stated premise

The MMP and abundance stack (033 → 034 → 036 → 056) is the largest. history.md shows 6 of its manuscripts needed repair on Oct 7, and one paper in 033 failing would sink roughly five families.

---

## B. Newer results quietly overrule older ones (the index never says so)

### B1. The Nov 24 additions supersede at least four older families. Confidence: high.
- **379** (Nov 24) gives the finite Fourier transform cost as N(log N)^(1/2+o(1)) and integer multiplication as n(log n)^(1/2+o(1)). That makes **130** (saving of 10^-13 in the log exponent) and **109** (saving κ = 2^-182) obsolete.
- **379** states ω = 9/4 "over every field", with a matching lower bound n^(9/4)/2. Older family **107** proves ω ≤ 9/4 only over ℂ, and gives only ω < 2.371 "over every fixed field".
- **379** gives VP ≠ VNP and superpolynomial permanent and Hamiltonian-cycle circuit bounds, which overtake **108**'s cubic bound.
- **380** (strongly polynomial LP) gives strongly polynomial deterministic mean-payoff games and polynomial stochastic games. That overtakes **104**'s quasipolynomial algorithms.
- **079** (Oct 25, local smoothing in every dimension) implies **074** (Kakeya 3D/4D), **078** (Bochner–Riesz 3D) and most of **077**.
- **378** (Oct 25, ETH is false; Lean-formalized as SubexponentialSAT) removes the premise of the 133 paper whose n^Ω(k) Weisfeiler–Leman bound holds "under positive-rate ETH". The unconditional sibling in 133 survives.

Why it matters: anyone quoting 107, 109, 130 or 104 as the current state is out of date by the release's own later papers.

### B2. Possible change of definition between 107 and 379. Confidence: medium.
The Lean statement behind "ω = 9/4 over every field" is about `formalOmega`, a cost model of formal arithmetic programs with "wire weights". 379's abstract says "the upper bound was known", but the only upper bound in the release (107) is over ℂ. Either the positive-characteristic upper bound comes from somewhere not in the release, or `formalOmega` is not the textbook ω. Check this before repeating "ω = 9/4" as a fact. Note that 379's lower bound, if it holds for the textbook ω, would end the long-held expectation that ω = 2.

### B3. 378 and 379 share the exponent 1/2. Confidence: low (a lead only).
378's SAT algorithm runs in 2^(n/(log n)^(1/2)). 379's multiplication bound is n(log n)^(1/2), and its matching lower bound assumes "Weak ETH". In Lean, Weak ETH is defined as "no 2^(v^(1-η)) algorithm for 3-SAT", which 378 does not refute. The same 1/2 suggests the same tensor machinery. If 378's method were pushed further it would strike exactly the hypothesis 379's optimality rests on.

---

## C. Weak spots you only see across the whole set

### C1. MUBs in dimension 6: the headline is not formally certified. Confidence: high.
Family **266** says the maximum is exactly three. The upper bound is "a complete certified computation under the stated binary64 arithmetic and compiler conditions", which means floating point. The companion's exact rational certificate only reaches **≤ 5**. The Lean challenge (MUBSix.lean) proves only `n ≤ 5`. So the quantum-information headline "exactly 3" rests on a floating-point C++ run, not on exact arithmetic or Lean. history.md (Oct 26) restored that C++ source and its records, with a Python consistency checker.

### C2. Computer-certificate dependence elsewhere. Confidence: high.
- 090: interval arithmetic
- 119: "finite exact arithmetic certificates"
- 189: 3,099 cases checked by programs
- 222: numerical certificate for the jamming exponents
- 229: exact-arithmetic polynomial inequalities
- 187: Snaky certificate

These are fine where the arithmetic is exact; 266 is the only one on floating point.

### C3. Internal tension in 095. Confidence: high.
One paper builds an explicit cone (degree 16, 23 variables) with no spectrahedral representation. A sibling then gives an **exact semidefinite lift** of that same cone. So that cone is not a counterexample to the Projected Lax conjecture. The family's "no SD lift at all" headline rests only on the separate Oct 5 example.

### C4. Results that hinge on a definition. Confidence: high.
- 260: the Kerr–Newman Penrose inequality is violated if J is the bare ADM angular momentum with O(r^-2) tails, and proved with total J including the EM part.
- 350: Yau's nodal bound holds in dimension 2 and fails in 3, 4 and 5.
- 351: Ricci-flow extension holds in dimension 4 and fails in high dimension.
- Results that depend on set theory: 323 (needs a measurable cardinal), 240 (under CH), 244, 297.

Quoting any of these without the scope says something false.

### C5. Huge constants and no explicit bounds. Confidence: high.
- 109: κ = 2^-182
- 111: competitive ratio 2^-310
- 130: δ = 10^-13
- 053: genus 10^60
- 054: ineffective discriminant
- 028: "nonexplicit"
- 183: "nonquantitative"
- 191: "extremely small" η
- 227: exp(n^(1/10000))
- 300: 5×10^8 ε^-2
- 281: QAOA with "no quantitative bound on the required depth"

Many results are existence-only and have no practical use as stated.

### C6. Duplication inflates the count. Confidence: high.
These families repeat the same theorem by different routes: 237 (13 manuscripts), 260 (13), 238 (12), 376 (9), 331 (7). Family 056 has two manuscripts with the identical title. The 2-converse for elliptic curves appears separately in 002, 004 and 006. "730 manuscripts" is far more than the number of independent results; history.md itself counts 719 top-line results, of which 300 are formalized.

---

## D. Links between families that nobody draws

### D1. Hilbert's tenth problem over ℚ sits on elliptic-curve rank control. Confidence: medium.
Family **004** contains, besides the H10 paper, "A pointwise 2-converse for elliptic curves with rational two-torsion". That is the same BSD and Selmer machinery as 002 and 006. The negative answer for ℚ likely needs that rank control, and nothing says so.

### D2. 197 implies a non-sofic group exists. Confidence: medium-high.
Direct finiteness and Gottschalk surjunctivity are known to hold for all sofic groups. So **197**'s counterexamples (described as "nonsofic") prove that a finitely presented non-sofic group exists. That has been a famous open problem (Gromov and Weiss), and it is never headlined. Related cross-links:
- Kaplansky's conjectures split by characteristic: they fail in characteristic 2 (196, 197) and odd p (197), and the idempotent conjecture holds in characteristic 0 (207).
- 248 combined with 251: Thompson's group F is nonamenable, so by 251 it is neither unitarizable nor strongly Ulam stable.

### D3. Complex cobordism inside a C*-algebra family. Confidence: high.
Family **302** (radius of comparison equals half the mean dimension) includes "Filtered products and boundary-preserving compression in complex cobordism". An MU-theory result from stable homotopy is doing work in topological dynamics and C*-algebras. Nobody draws this bridge.

### D4. Both ends of density functional theory crack. This matters for the electrons tool. Confidence: medium.
- **278**: the Kohn–Sham ensemble picture fails for a 3-electron, 2-nucleus molecule. This is the weak-correlation end.
- **373**: the three-marginal Coulomb Monge problem is not attained. Strictly-correlated-electron DFT assumes "co-motion" maps, which are Monge maps. So the standard ansatz at the strong-correlation end fails for N = 3.
- **275** makes approximating continuum Coulomb ground energy QMA-hard, even with unit-charge nuclei.
- **263** bounds ionization at Z + CM electrons.
- **262** gives sharp matrix Lieb–Thirring constants.

No family connects 278 and 373.

### D5. The QAOA-on-SK result does not show an advantage. Confidence: medium-high.
- **281**: QAOA reaches the SK ground energy, with system size taken to infinity before depth and no depth bound.
- Its own companion proves the zero-temperature Parisi measure has **full support** (no gaps).
- Full support (no overlap gap) is exactly the hypothesis Montanari's classical message-passing algorithm needed to reach the SK optimum in polynomial time.
- So the same family removes the obstacle for the classical algorithm. QAOA attaining SK is parity with classical, not an advantage.
- **227** shows plain classical Glauber dynamics is slow at low temperature, which is why the comparison must be against message passing, not MCMC.
- **102** proves the Unique Games Conjecture and Goemans–Williamson Max-Cut hardness on unweighted graphs. So no polynomial-time method, quantum included unless NP ⊆ BQP, beats 0.878 in the worst case. **096** relies on 102.

### D6. More cross-links. Confidence: medium.
- 076 (ultraflat ±1 polynomials, merit factor → ∞) and 179 (Barker sequences only up to length 13): the binary-autocorrelation landscape behind the LABS benchmark is now settled at both ends.
- 156: the Borsuk counterexample lives on rank-one projectors on ℝ⁴, which are real two-qubit pure states.
- 238: the Thorp shuffle is a butterfly network, the same wiring as FFT and QFT butterflies, and it mixes in Θ(log N) rounds.
- 145 feeds 154: mixing implies mixing of all orders, which enables the pointwise multiple averages.

---

## E. Factors for Big J's quantum side

**E1. Constant-depth QPE has a hard floor. Confidence: medium-high.**
**274** proves parity is not in QAC0, with two independent proofs and Lean (QACParity). Parity and fan-out are equivalent in constant depth, so QAC0 cannot do fan-out. Constant-depth QFT and phase estimation constructions need fan-out gates, so they are impossible in plain QAC0. Big J's QPE depth must grow unless fan-out is a native gate. This also caps the "shallow circuit" story behind the HLF run: HLF shows a constant-depth win, and 274 shows where it stops.

**E2. Exact factoring on a finite gate set means it is not standard QPE. Confidence: high on the gate set, medium on the inference.**
**279** is Lean-stated (ExactQuantumFactoring). It uses only {X, CNOT, Toffoli, H, S}, with inverse and one extra control, which is 20 gates. Every matrix entry lies in ℤ[i, 1/√2]. An exact QFT on 2^k for k ≥ 4 needs e^(iπ/8), which is outside that ring. So the probability-one factoring cannot be textbook QPE with a large exact QFT; it must reach exact phases another way. For Big J's QPE add-on (where an earlier lock failed on "phase on the QPE grid"), this route is the one worth studying.

**E3. Grover on SAT no longer beats the best classical method. Confidence: high on the statements, medium on the reading.**
**378** counts k-SAT solutions classically and exactly in about 2^(n/√log n), which is eventually far below Grover's 2^(n/2). **138** solves Subset Sum classically in 2^(0.49n). "Quadratic quantum speedup for SAT" claims measured against brute force no longer mean a speedup.

**E4. Optimization claims (QAOA, DQI, Max-Cut, XORSAT). Confidence: medium-high.**
See D5. With 102 (UGC) proven, the approximation thresholds for 2-CSPs are NP-hard boundaries. QAOA and DQI cannot pass them in the worst case unless NP ⊆ BQP, and on SK the classical algorithm matches the QAOA result (281 companion).

**E5. Electrons tool. Confidence: medium.**
See D4. Worst-case electronic ground energy is QMA-hard even for a quantum computer (275), and both standard DFT ansätze fail on 3-electron examples (278, 373). The tool should claim estimates, never a general solver.

**E6. A spin-one chain check Big J's MPS layer can run. Confidence: high on the statement.**
**268** proves a gap on even periodic spin-one Heisenberg rings. For odd open chains with endpoint field h = 3/5, the gap exceeds ln(10)/392 ≈ 0.00587 for every chain of 2L+1 sites with L ≥ 960, with topological index −1. This is a concrete external number the MPS add-on can be checked against.

**E7. Gapped 2D ground states are classically representable. Confidence: high.**
**265** gives a 2D area law from a global gap alone, plus PEPS approximations with polynomial bond dimension. This is existence only, but it limits quantum-advantage claims for gapped 2D ground states.

**E8. Noise, channels and codes. Confidence: high on the statements.**
- 276: classical capacity of generalized amplitude damping is the one-shot Holevo value and is additive. This is directly usable for Big J's amplitude-damping noise model.
- 272: a bound-key entangled state in 10×10, and the PPT² conjecture is false.
- 277: parallel repetition for entangled games, finite dimension only.
- 177: bounded-degree coboundary expanders in every dimension, which are the raw material for quantum LDPC and locally testable codes.
- 178: deterministic Ramanujan graphs, which give the best possible spectral gap for walks.

**E9. Quantum walks with disorder. Confidence: medium.**
261 shows the 2D Anderson model is localized at every disorder, while 3D at weak disorder has absolutely continuous spectrum. 219 gives GOE statistics on random regular graphs with weak disorder. Disordered quantum walks should stall in 2D and can spread in 3D or on expanders. That is a clean prediction for the Szegedy and quantum-walk add-ons.

**E10. Limits on quantum query and synthesis claims. Confidence: high.**
284 shows quartic is the largest possible randomized-vs-quantum query gap for total functions. 283 gives unitary synthesis from a Boolean oracle using H, T, T† and CNOT, with no efficient way to construct the oracle.

**E11. Classical Fourier transforms got cheaper. Confidence: high.**
130 and 379 bring the classical cost of Fourier transforms down to N(log N)^(1/2+o(1)), using tensor-power savings on Hadamard-type matrices. Classical-versus-QFT cost comparisons should use the new figure.

---

## The three findings that matter most

1. **Keystones and supersession.** A few results carry many others, and the release never marks which papers newer ones overrule: 003/029 under 142/182, 032 under 001, 379/380/079/378 overruling 107/109/130/104/074/133.
2. **The quantum headlines need care.** 266's "exactly 3" is floating point only; 281 gives no QAOA advantage once its own full-support companion is applied; 274 sets a constant-depth floor for QPE; 279's exact factoring cannot be textbook QFT-based QPE.
3. **Electrons.** DFT fails at both ends (278, 373) and ground energy is QMA-hard (275), so the electrons tool must present outputs as estimates.
