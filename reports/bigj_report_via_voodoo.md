# Big J on the OpenAI math release, driven by Voodoo

Date: 2026-11-24. Driver: Voodoo, using its own bigj_run tool (`bigj -p`). Nothing was published or sent.

## How it was run

The index (~/branch_work/oai719_parallel_20261124/CONTENTS.md) was cut into five slice files, same text, no edits, in ~/branch_work/oai719_parallel_20261124/parts/:
part1_001-075.md, part2_076-150.md, part3_151-225.md, part4_226-300.md (also split into part4a_226-262.md and part4b_263-300.md for the retry), part5_301-380.md.

Each prompt began with /deep, gave him the full index path, the slice path and the family range, and asked: what important factors did everyone miss? (links between families, hidden assumptions many results lean on, weak spots, anything for his quantum side: circuits, QPE, phases, codes, walks, the electrons tool). He was given none of Voodoo's own 11/24 findings. Retry prompts added only where the previous answer had stopped, and "keep it tight/short enough to finish".

Call log:
- Part 1: try 1 cut off mid-sentence; retry cut off mid-sentence.
- Part 2: try 1 cut off mid-sentence; retry cut off mid-sentence.
- Part 3: try 1 cut off mid-sentence; retry cut off mid-sentence.
- Part 4: try 1 FAILED (he answered only "Please rephrase the question or ask Claude." after re-asking himself 3 times); retry (two half-files) answered, cut off mid-sentence.
- Part 5: try 1 cut off mid-sentence; retry cut off mid-sentence.
- Top three: complete answer (he hit his 12-round tool limit but finished the text).

The cut-offs are Big J's own answer length (about 5,000 characters), not the tool: bigj_run returns the last 6,000 characters and his closing footer line came through intact every time. Each part was retried once only, as instructed. Both attempts are kept below, word for word, including his footer lines.

---

## 1. His raw answers, by part

### Part 1: families 001-075

#### Try 1 (cut off)

I read the full part 1 file (families 001–075) from `/home/jim/branch_work/oai719_parallel_20261124/parts/part1_001-075.md`, plus the collection index `/home/jim/branch_work/oai719_parallel_20261124/CONTENTS.md`. Here is what stands out as the genuinely missed or under-appreciated structure in that slice.

## 1. The families that are secretly the same problem

The most important thing is that several “different” results are really one theorem with different packaging:

- **002, 004, 006, 007** form a single Birch–Swinnerton-Dyer / Selmer-corank / Goldfeld-density cluster. 002 proves the full BSD formula from low Selmer corank; 004 proves the Selmer converse at every prime; 006 proves the quadratic-twist density and mean analytic rank; 007 proves the Chowla-type two-point correlation. Together they say: for quadratic twists, rank zero and rank one each have density 1/2, the mean analytic rank is 1/2, and the analytic rank is controlled by the Selmer corank. That is a coherent package, not four independent papers.
- **003** has two proofs of the same zero-free half-plane: one gives Re(s) > 7/8, the other Re(s) > 11/12. The 11/12 version is the stronger companion and rules out Landau–Siegel zeros; the 7/8 version is the headline. Both are in the same family, and the uniform Landau–Siegel exclusion paper is a separate but related result.
- **016** is a Zilber–Pink package in A₂: the abelian case, the E×CM component, the quaternionic-division component, and the elliptic-squares component. The abstract of the elliptic-squares paper explicitly says the four components combine to prove the curve case of Zilber–Pink in A₂ without a boundary hypothesis. That is one theorem with four parts.
- **052** is a splitting-conjecture package: the two-summand Beauville splitting conjecture plus Höring’s integrability conjecture, with the product decomposition as the payoff.
- **068** is a nonvanishing package: smooth semipositivity of the anticanonical bundle forces a nonzero section of a positive power, with several independent proofs (invariant indices, torus quotients, cohomological transfer, metric descent, integrable metrics, exact orders). The “exact orders” paper is the cleanest statement, but the others are the machinery.

## 2. Hidden assumptions the results lean on

- **Ordering conventions matter.** 002, 006, and 007 all order quadratic twists by absolute value among signed squarefree twist parameters. The density statements (rank zero and rank one each 1/2, mean analytic rank 1/2) are true in that convention. A different ordering, or a different class of twists, could change the picture. The papers are careful about this, but it is a real assumption that a reader might miss.
- **Corank zero or one is the whole range.** The BSD and Selmer-converse results are proved only for corank zero or one. The papers do not claim the converse for higher corank, and the density results are about the distribution of ranks, not about proving BSD for all curves. The “full BSD” in 002 is conditional on the low-corank hypothesis.
- **Residue characteristic 2 is handled separately.** 001 and 004 explicitly allow arbitrary reduction at 2, which is the hardest case. The papers note this explicitly, but it is a genuine technical assumption that is easy to overlook in a summary.
- **The “no boundary” and “no reduction” hypotheses in 016 are real.** The Zilber–Pink curve case in A₂ is proved without boundary or reduction assumptions, but the quaternionic-division component and the E×CM component are stated for Hodge-generic curves. The combination is what removes the boundary hypothesis, and that combination is not automatic.
- **The “ineffective” thresholds in 050 and 054 are not a weakness but a real limitation.** 054 says the discriminant threshold is ineffective, and 050 disproves the conjecture on the quadric surface, which is the simplest possible case. That means the failure is not a boundary phenomenon; it is a genuine counterexample on the simplest ambient space.
- **The “no positivity” conditions in 065 and 066 are the key.** 065 passes Virasoro constraints from a base to a projectivization without the bundle splitting or any positivity requirement. 066 gives bounded klt complements for Fano contractions with index depending only on dimension and ϵ, not on the boundary coefficients. These are the “no extra hypotheses” features, and they are the reason the results are strong.

## 3. Weak spots and places where the results could be pushed

- **The 7/8 vs 11/12 gap in 003.** The two proofs give different zero-free half-planes. The 11/12 proof is stronger, but the 7/8 proof is the headline. A reader might assume the two are equivalent or that the 7/8 result is the best possible. It is not; the companion is strictly better. The Landau–Siegel exclusion is a separate consequence of the uniform version.
- **The density-one set in 002/006 is conditional.** The

(Big J · answered by solar-mini4 via nous · 8 tool calls · question: RECORD · facts checked · numbers checked)

#### Retry (cut off)

I read the full index and the part1 file (families 001–075) from `/home/jim/branch_work/oai719_parallel_20261124/CONTENTS.md` and `/home/jim/branch_work/oai719_parallel_20261124/parts/part1_001-075.md`. Here is my answer, in my own words.

## What everyone missed in families 001–075

**1. The "converse" and "density" results are doing far more than the titles suggest.** Families 002, 006, 007, 020, 021, 034, 066, 068, 069 are not isolated theorems; they are the connective tissue. For example, 002 + 006 together give full BSD for a density-one set of quadratic twists of every elliptic curve, and 006's density-one statement only works with the signed-squarefree-by-absolute-value counting convention. 007's Chowla/conjecture work is the analytic side that 002/006 lean on for the rank distribution. 034's log abundance is conditional on subadditivity results that are themselves proved in the same family. The missed factor is that these are a **network**, not a list: a reader who treats each as a standalone headline misses the fact that the density-one statements, the 2-converses, and the subadditivity theorems are mutually reinforcing.

**2. Hidden assumptions that many results lean on.**
- **Counting conventions.** 006, 020, 021 all depend on a specific ordering (signed squarefree by absolute value; intervals of consecutive integers; degree ranges). Change the ordering and the density statements change. This is a recurring trap: the theorems look unconditional but are convention-dependent.
- **Reduction hypotheses.** 001 explicitly includes residue characteristic 2, which is a real edge case. 004's Hilbert's tenth problem over ℚ has no reduction assumption. 002/006/007/020/021 all assume "no fixed prime-square divisor" or "no fixed prime divisor" local conditions — the necessary local condition is doing real work, and it is easy to forget that the global density statements only hold because of it.
- **Characteristic-zero vs. positive characteristic.** 009, 034, 066, 068, 069, 070, 071, 072, 073, 074, 075 all live in characteristic zero or over algebraically closed fields of characteristic zero. 009's function-field reconstruction explicitly distinguishes ℓ ≠ char from equal characteristic. The missed factor is that the characteristic-zero assumption is doing heavy lifting in the proofs, and the results do not automatically transfer.
- **The "density-one" and "very general" qualifiers.** 002, 006, 007, 020, 034, 066, 068, 069 all use density-one, very general, or generic statements. These are not uniform over all objects; they are over a large but not all subset. The missed factor is that "density one" is a measure statement, not a structural one, and it does not imply the statement holds for any specific curve or variety.

**3. Weak spots and places where the results are conditional.**
- **003's quasi-Riemann hypothesis has two proofs** (7/8 and 11/12), and the 11/12 proof is a companion that rules out Landau–Siegel zeros. The zero-free half-plane is the headline, but the Landau–Siegel exclusion is the deeper consequence, and it is only uniform for primitive nonprincipal real Dirichlet L-functions. The missed factor is that the "quasi-Riemann hypothesis" is really a family of zero-free results, and the Landau–Siegel uniform exclusion is the part that matters for applications.
- **004's Hilbert's tenth problem over ℚ** is a negative result with no algorithm. The weak spot is that it does not give a bound on the search space or a complexity statement; it is purely undecidability. The missed factor is that the proof likely uses the same machinery as the negative answer for ℤ, but over ℚ the rational-zero condition is much more delicate, and the proof's reliance on the number of variables being part of the input is a real limitation.
- **005's Catalan's constant irrationality** is a single constant. The weak spot is that it does not give irrationality measure or transcendence. The missed factor is that it is a standalone result with no obvious generalization in the family.
- **008's Deligne–Drinfeld conjecture** is about the rational Grothendieck–Teichmüller Lie algebra with the Ihara bracket, freely generated by one element in each odd weight ≥ 3. The weak spot is that it is a structural result about a Lie algebra, and the missed factor is that the proof likely relies on the Ihara bracket's properties, which are specific to the Grothendieck–Teichmüller setting.
- **016's Zilber–Pink** has three components (abelian, E×CM, quaternionic division) plus elliptic squares, all for Hodge-generic curves in A₂. The missed factor is that the curve case in A₂ is proved by combining three separate finiteness theorems, and the "no boundary or reduction assumptions" claim is the headline, but the proof requires

(Big J · answered by solar-mini4 via nous · 8 tool calls · question: RECORD · facts checked · 5 numbers not from a tool or the record: 70, 71, 72, 73, 74)

---

### Part 2: families 076-150

#### Try 1 (cut off)

I read the full slice (families 076–150, part2_076-150.md) plus the collection index (CONTENTS.md). Here is what stands out as genuinely missed or under-appreciated in that range, in my own words.

**1. The same "sharp threshold" story repeats across unrelated fields.**  
Families 076–080, 093, 094, 096, 097, 099, 100, 108, 109, 110, 112, 113, 114, 115, 128, 129, 130, 131, 132, 133, 134, 145, 146, 148, 149, 150 all hinge on a single sharp boundary: a conjecture says "up to this point it's true / bounded / efficient," and the new work pins the exact endpoint or disproves the conjecture by constructing a counterexample at the boundary. Examples: Turyn's bounded merit factor conjecture (076), the quasi-Riemann hypothesis zero-free half-plane (003), the Bochner–Riesz strict range (078), Carleson's Schrödinger endpoint (080), the David–Semmes rectifiability range (081), the triangular Hilbert transform symmetric point (082), the Gaussian propeller bound (096), the Steinitz–Bergström bound (097), the edit-distance distortion scale (099), Bang's half-area cylinder bound (100), the permanent's cubic border determinantal complexity (108), the Schönhage–Strassen n log n optimality (109), the k-server O(log²k) bound (110), the depth-three circuit square-root exponent (112), the perfect-matching entropy conjecture (113), the Gotsman–Linial asymptotic form (127), the shortest common superstring factor-two (128), the sensitivity/block-sensitivity quadratic strengthening (132), the Weisfeiler–Leman n^Ω(k) bounds (133), the generalized star height (134), Rokhlin's multiple-mixing (145), Sinai's positive-parameter measure conjecture (146), the entropy-rate dimension formula (148), the permanence conjecture (149), and the triangular billiard weak mixing (150). The pattern is: the field believed a clean threshold, and the new results show the threshold is exactly where the old conjecture said it was, or that the conjecture's strict range was the whole truth. That's not a coincidence; it's a sign that the field's intuition about "where the hard part lives" was systematically right, but the mechanisms were missing.

**2. Hidden assumptions many results lean on.**  
- **Genericity / Diophantine conditions are being removed.** Triangular billiards (150), the standard map (146), and the Birkhoff near-boundary conjecture (147) all drop genericity or Diophantine restrictions. That's a big deal: earlier results often needed "almost every" or "for Diophantine parameters," and the new work shows the phenomenon is structural, not measure-theoretic.  
- **Exact overlaps are allowed.** The entropy-rate dimension formula (148) works for self-similar measures with exact overlaps and unequal/negative contraction ratios. That's a major weakening of the separation assumption that dominated the field.  
- **Unrestricted inputs.** The dyadic triangular Hilbert form (082) allows unrestricted real inputs; the L³ bound for the dyadic triangular Hilbert form (082) allows coefficients of modulus ≤ 1 to vary independently. The "unrestricted" or "arbitrary" qualifier is doing real work: many classical results silently assumed special structure.  
- **Coefficientwise limits / border complexity.** The permanent's cubic lower bound (108) works for coefficientwise limits, not just exact representations. That's a subtle but important strengthening: the lower bound survives the limit, so it's not an artifact of the exact case.  
- **Uniformity over alphabets / lengths.** The edit-distance distortion (099) is uniform over all finite alphabets with ≥ 2 symbols, even when the alphabet grows with d, and binary words already force the lower bound. The k-server result (110) works on every metric space, including infinite unbounded ones, with one policy. The switch chain (131) mixes in O(n⁸) for every graphical degree sequence, no exceptions. These "uniformity" claims are easy to overstate and easy to miss.

**3. Weak spots and open ends visible in the slice.**  
- **The "sharp threshold" is often proven by a single construction.** Many families reduce to one explicit example (a polynomial, a billiard, a measure, a graph, a Boolean function) that saturates the bound. That's fine, but it means the "why" is often not explained: why does that particular object sit exactly at the threshold? The slice gives the theorem, not the mechanism.  
- **The "disproof" is sometimes a strengthening of a conjecture, not a contradiction.** For example, 076 disproves Turyn's bounded-merit-factor conjecture by showing merit factors tend to infinity; 078 resolves the Bochner–Riesz conjecture in its strict range; 079 proves Sogge's local smoothing conjecture in every dimension. These are "the conjecture was right, now we know exactly where" results. The missed factor is that the field's intuition was right

(Big J · answered by solar-mini4 via nous · 9 tool calls · question: RECORD · facts checked · numbers checked)

#### Retry (cut off)

I read the slice for families 076–150 (part2_076-150.md) and the collection map (CONTENTS.md), and I’m answering in my own words, without claiming any guarantee.

**What the slice shows.** Families 076–150 are a mixed bag: analytic number theory (076–080, 145–146), harmonic analysis and PDEs (077–080, 082–083), convex geometry and functional analysis (084–099), computation/complexity (108–134), and dynamical/billiards/mass-action (145–150). The common thread is that each family is a single headline theorem plus one or more companion papers that prove the same result by a different route, sharpen the constants, or extend the hypotheses.

**Factors everyone missed, in my reading.**

1. **The “same theorem, two proofs” pattern is the real product.** Several families carry two papers proving the identical statement: e.g., 076 has ultraflat Littlewood polynomials plus nearly minimal maxima, 077 has elliptic capacity propagation plus the diagonal Fourier extension theorem, 079 has local smoothing plus the critical 3D wave estimate, 080 has planar and higher-dimensional Schrödinger endpoints, 082 has annular variation plus an L³ dyadic bound plus the maximal transform, 095 has the nonspectrahedral cone plus an exact semidefinite lift, 099 has three papers on edit-distance distortion, 113 has an FPRAS plus an entropy/face-dimension paper, 114 has two FPRAS papers, 128–129 have two papers each, 130 has two papers, 131 has two, 132–133 have three, 134 has two, 145–146 have two, 147–148 have two, 149 has two, and 150 has two. The headline is the same; the companions are the real work — they show which hypotheses are load-bearing and which are not.

2. **Hidden assumptions the results lean on.** Several results quietly assume the objects are explicit, finite, or rational: the k-server and Weisfeiler–Leman papers say “finite rational metrics” and “explicit adjacency matrices” and “multitape Turing machines” and “sequential logarithmic-word RAMs.” The edit-distance results assume unit-cost insertions/deletions/substitutions and alphabets of size at least two, with the lower bound already forcing on binary words. The permanent paper assumes complex affine-linear determinant representations with coefficientwise limits. The mass-action papers assume fixed positive rate constants and positive initial conditions. The billiard results assume smooth strictly convex positive curvature. The self-similar measure result allows exact overlaps and unequal/negative contraction ratios, which is the non-generic case that makes the formula surprising. None of these is flagged as an assumption in the abstracts; they are absorbed into the statement.

3. **Weak spots and open ends.** The papers that give constants explicitly (076, 077, 079, 080, 082, 095, 099, 110, 111, 113, 114, 128–134) are the ones where the constants are stated, and several say the constants are not claimed to be minimal (095) or may be enormous (110). The 095 exact lift is size 100 with 307 auxiliary variables, explicitly not minimal. The 111 competitive ratio is 2^(−310), an absolute constant that is tiny but not claimed optimal. The 110 additive movement constant is finite and instance-dependent but may be enormous. The 109 exponent κ = 2^(−182) is astronomically small, so the saving over n log n is real but negligible in practice. The 130 δ = 10^(−13) is likewise a power saving, not a breakthrough. So the “weak spots” are mostly: constants are not optimized, and the savings are asymptotic or of minuscule order.

4. **What it means for the quantum side.** The slice is almost entirely classical analysis and combinatorics, so there is no direct quantum content here. But a few things connect to my own work:
   - **QPE and phases:** the Fourier-related families (077, 080, 082, 130) are about phase/oscillation structure on the unit circle and about sharp thresholds (p > 3, H^(1/3), L³, the n log n exponent). These are the same kind of “sharp threshold” problems my QPE circuits and phase estimation are built for, though the slice does not use quantum circuits.
   - **Circuits and codes:** 099 (edit distance, binary codes, finite-circle constructions) and 113 (perfect matchings, entropy) and 131 (switch chains, sampling) are about structure in discrete objects — the kind of structure that could be probed with quantum walks or amplitude amplification, but the slice does not do that.
   - **The “electrons tool” and walks:** nothing in the slice uses quantum walks or the electrons tool; the closest is the switch chain (131) and the k-server (110), which are classical sampling/mixing problems.
   - **The honest read:** this slice is a classical mathematics release. It does not test my quantum side

(Big J · answered by solar-mini4 via nous · 8 tool calls · recursive loop: re-asked himself 1 time (wrong fact caught) · question: RECORD · facts checked · 4 numbers not from a tool or the record: 83, 84, 310, 182)

---

### Part 3: families 151-225

#### Try 1 (cut off)

Families 151–225 (the slice in `/home/jim/branch_work/oai719_parallel_20261124/parts/part3_151-225.md`, with the full index in `/home/jim/branch_work/oai719_parallel_20261124/CONTENTS.md`) are a mixed bag: a few clean structural wins, a large cluster of counterexamples to long-standing conjectures, and a smaller cluster of deep statistical-physics limits. Here’s what stands out as genuinely missed or under-appreciated.

**1. The counterexamples cluster (151, 152, 155, 156, 157, 158, 192–199, 211–214, 221–224) is the real story.** Several of these don’t just sharpen a conjecture; they break the intuition that “nice structure forces nice behaviour.”

- **151 (C¹ entropy):** A noninvertible C¹ self-map of a compact smooth manifold with zero topological entropy but eigenvalue 2 on second homology. This kills the homological entropy lower bound for general C¹ maps: homological growth no longer forces positive orbit complexity. The lesson is that the conjecture’s hypothesis needs a non-invertibility or spectral-radius hypothesis; the homological spectral radius alone is not enough.
- **152 (zero entropy, no smooth positive-volume model):** An ergodic invertible transformation of a standard nonatomic probability space with zero KS entropy that is not measurably conjugate to any C∞ diffeomorphism preserving a strictly positive smooth density, in any finite dimension. One example excludes every dimension, including nonorientable manifolds and manifolds with smooth boundary. This is a strong “no finite-dimensional smooth model” result, and it’s a single example ruling out all dimensions at once.
- **155 (periodic tiling in ℤ³):** A finite translational tile that tiles space but admits no fully periodic tiling. This disproves the periodic tiling conjecture in the smallest possible lattice dimension, and the unit-cube thickening gives the same counterexample in ℝ³ with arbitrary real translation vectors. The key missed factor: tiling existence does not imply periodic tiling existence, even in dimension three.
- **156 (Borsuk in dimension nine):** A compact subset of ℝ⁹ that cannot be covered by ten sets of strictly smaller diameter, built from rank-one orthogonal projectors onto lines in ℝ⁴ with the Frobenius metric. Borsuk’s conjecture fails already in dimension nine, not just in high dimensions.
- **157 (Hadwiger and Colin de Verdière):** Arbitrarily large graphs with independence number at most two satisfy χ_f(G) > h(G), and the fractional Colin de Verdière chromatic bound χ_f(G) ≤ μ(G)+1 also fails. The positive side is a linear list-coloring bound χ_list(G) ≤ C·h(G) with a universal constant C. The missed factor: the fractional and list-coloring relaxations are much looser than the ordinary chromatic number, and the independence-number-two restriction is what makes the counterexamples work.
- **158 (Euclidean plane five-coloring):** Every five-coloring of the Euclidean plane has a monochromatic unit-distance pair, so the chromatic number of the plane is six or seven. Together with the classical seven-coloring, only six and seven remain possible. The missed factor: the result needs no regularity on the color classes, which is what makes it stronger than earlier versions.
- **192 (square-root degree bound):** For every C > 0 there is a Boolean function with total signed linear Fourier coefficient sum exceeding C·√(deg f). This disproves the Gopalan–Servedio square-root conjecture even up to an arbitrary constant factor. The missed factor: the linear Fourier coefficients can be large relative to the degree, so any bound of the form ∑|f̂({i})| ≤ C√deg f is false.
- **193–199 (positivity and finiteness conjectures):** Serre’s intersection multiplicity positivity, Lech’s multiplicity conjecture, and the Eisenbud–Green–Harris / lex-plus-powers conjectures are all resolved affirmatively. But the counterexamples are the striking part: a three-dimensional complete Noetherian normal local domain with no nonzero finitely generated maximal Cohen–Macaulay module (195), a finitely presented torsion-free group algebra over 𝔽₂ with zero divisors (196), a torsion-free nonsofic group algebra that is not directly finite and cellular automata that are injective but not surjective (197), an algebra of infinite little finitistic dimension (198), and counterexamples to Auslander–Reiten, Tachikawa, Nakayama, Auslander–Gorenstein, and Wakamatsu tilting conjectures (199). The missed factor: these are not isolated pathologies; they persist under every extension of the base field, so they are robust structural failures, not artifacts of a special field.
- **211–214 (random planar maps, percolation, O(n) models):** Critical Fortuin–Kasteleyn planar maps converge to Liouville quantum gravity spheres for 0 < q ≤ 4 and to the Brownian continuum random tree for q > 4, with the surface-to-tree geometric transition. FK–Ising and spanning-tree-weighted maps have stationary random walks converging to Liouville Brownian motion on the limiting sphere, with spectral convergence and heat-trace convergence. Planar first-passage percolation has no doubly infinite geodesic under a finite-second-moment condition, and the exponential limit shape is strictly convex with C¹ boundary. Critical percolation on every infinite connected locally finite quasi-transitive graph with p_c < 1 has no infinite cluster at criticality, and nonamenable quasi-transitive graphs have p_c < p_u with a nonempty interval of

(Big J · answered by solar-mini4 via nous · 8 tool calls · question: RECORD · facts checked · numbers checked)

#### Retry (cut off)

I read the full slice (families 151–225) from `/home/jim/branch_work/oai719_parallel_20261124/parts/part3_151-225.md`, cross-checked against the collection map in `/home/jim/branch_work/oai719_parallel_20261124/CONTENTS.md`. Here is what stands out, in my own words.

**1. The big theme: “counterexamples and sharp thresholds”**
Most of families 151–225 are negative results that kill a plausible conjecture, or sharp quantitative bounds that replace a vague expectation with an exact constant. The pattern is consistent: a conjecture says “X should hold” or “X should be bounded by √n / log n / a constant”; the papers construct a single example, a family, or a two-sided estimate showing the bound is wrong, or the constant is different. That is the real story of this slice: the field is being pruned by counterexamples, not built up by new positive theorems.

**2. Hidden assumptions many results lean on**
- **Mixing without rates.** Families 154 and 155 (ergodic averages for mixing transformations, and the pointwise convergence results) assume only mixing, no rate, no standardness. The hidden assumption is that “mixing” is enough to control correlations along distinct slopes and times; the papers prove it is, but only for consecutive averages of fixed length. The assumption that this extends to longer tuples or to non-consecutive times is exactly where the proofs stop.
- **Quasi-transitive graphs and nonamenability.** Families 213 and 214 (Benjamini–Schramm criticality and nonuniqueness) assume quasi-transitivity and, for 214, nonamenability. The hidden assumption is that the graph looks the same from every vertex in the same orbit; the results do not cover general transitive or non-locally-finite graphs. Also, 214’s stronger operator bound $p_c < p_{2\to2} \le p_u$ leans on a specific operator-threshold conjecture, so the “stronger” statement is only as solid as that conjecture.
- **Moment conditions in percolation.** Family 212 (no bigeodesics in planar first-passage percolation) needs the minimum of four iid weights to have finite second moment. That is a mild but real assumption; the proof does not remove it. The limit-shape strict convexity and $C^1$ boundary for exponential weights is a separate, cleaner result inside the same family.
- **Characteristic assumptions in algebra.** Families 193–199 (Serre positivity, Lech multiplicity, Cohen–Macaulay, Kaplansky, finitistic dimension, Auslander–Reiten, Tachikawa) are mostly characteristic-free or characteristic-zero, but several counterexamples are built over $\mathbb F_2(q,H_1,H_2)$ or over fields of characteristic two and odd primes. The hidden assumption is that the counterexamples persist under field extensions; several papers state they do, but that is an extra claim, not the main theorem.
- **Binary-encoded parallel-edge multiplicities.** Family 174 (strong thin trees) is deterministic polynomial-time even with binary-encoded parallel-edge multiplicities. The hidden assumption is that the input length is measured in binary, so the algorithm’s polynomial bound is against the bit length, not the number of edges. That is a standard but important detail.
- **Uniform constants.** Families 175 and 176 (Talagrand discrete convexity, second Kahn–Kalai) use universal constants $C$ and $k$ that are not made explicit. The hidden assumption is that the constants exist; the proofs show existence but not computability. For applications, that is a real gap.

**3. Weak spots**
- **Counterexamples that are hard to generalize.** Many of these are single constructions (e.g., the 3D translational tile with no fully periodic tiling, the 9D Borsuk counterexample from rank-one projectors, the torsion-free group algebra with zero divisors). They are powerful but fragile: it is not obvious how to adapt them to other settings, and the papers do not always discuss whether the constructions can be perturbed.
- **Lean files are present but not always detailed.** Every family has a Lean file, but the abstracts do not explain the proof strategy. For a reader, the Lean files are the real content; the summaries are only the headline. That is a weakness of the collection as a reading guide.
- **No discussion of open problems or follow-ups.** The collection is a set of results, not a roadmap. It is unclear which of these will lead to new conjectures, which will be refined, and which will be superseded. The papers themselves do not always say.
- **Some results are conditional on other conjectures.** Family 214’s operator bound relies on Hutchcroft’s stronger operator-threshold conjecture; family 211’s spectral convergence relies on Liouville Brownian motion and LQG inputs. The papers are careful, but the dependency chains are long.
- **The “universal constant” problem.** In families 174, 175, 176, the constants are universal but not explicit. For a mathematician, that is fine; for an engineer or a computer scientist, it is a gap. The collection does not flag this.

**4. What this means for the quantum side (circuits, QPE, phases, codes, walks, electrons tool)**
- **QPE and phase estimation:** Families 211 and 212 are about spectral convergence and limit shapes in random planar maps and first-passage percolation. The quantum side here is not about QPE per se,

(Big J · answered by solar-mini4 via nous · 9 tool calls · question: RECORD · facts checked · numbers checked)

---

### Part 4: families 226-300

#### Try 1 (FAILED)

Please rephrase the question or ask Claude.

(Big J · answered by solar-mini4 via nous, step-3.7-flash via nous · 8 tool calls · recursive loop: re-asked himself 3 times (wrong fact caught) · question: RECORD · facts checked · numbers checked)

#### Retry, slice given in two halves (cut off)

Here is my read of families 226–300, in my own words, from the two slices you gave me.

## What everyone missed

**1. The Thorp shuffle slice (238) is a whole research programme, not one result.** Families 238–240 and the dozens of companion papers around them all chase the same target: the full-permutation mixing time of the Thorp shuffle on 2^d cards is Θ(log N) physical shuffles. What stands out is how much of the work is *indirect*: partial permutation laws, random coordinate frames, conditional information under deterministic sweeps, Fourier transfer, Schatten-moment bounds, permanent inequalities, compatibility entropy. Nobody seems to have a single clean argument; the result is assembled from many small lemmas, each improving the constant (1600d, 512d, 2048d, 2048d, then the O(d) order). The missed factor is that the "optimal order" is settled while the constants are still being chased by a dozen parallel papers. The hidden assumption: the lower bound is a support count (2d − O(1)), and the upper bound is a fixed absolute number of coordinate sweeps, but the bridge between them is fragile and depends on the exact structure of the shuffle's coordinate sweeps.

**2. The SK slice (227) is a story of three regimes, and the missed factor is the *initial state*.** The papers split cleanly into: high-temperature spectral gap and cutoff (β < 1), critical mixing (β = 1, n^{2/3+o(1)} worst-start), and low-temperature stretched-exponential barriers (β > 1). The genuinely missed factor is that the critical and low-temperature results are all about *fixed typical equilibrium configurations held as initial states* — the "typical-start" results. The worst-start cutoff at criticality is n^{2/3+o(1)}, but from a Gibbs-sampled fixed start the picture changes completely. Nobody in this slice seems to be asking whether the worst-start and typical-start pictures can be unified, or whether the quenched limit is really selected by the initial state. The universality result (Gaussian and Rademacher give the same limit) is the cleanest part, but it's buried in the dynamics papers.

**3. The honeycomb walk slice (226) is a story of *multiple exponents*, and the missed factor is the *bridge* problem.** The main result is a half-plane Temperleyan double-dimer loop ensemble converging to nested CLE_4, matching every macroscopic loop as an unparametrized curve. The companion papers then compute a zoo of exponents for critical honeycomb self-avoiding walks: spatial exponent 3/4, bridge mass N^{−1/4}, first-length mass h^{13/12}, mean length h^{4/3+o(1)}, triangle chord partition sum R^{3/4}, cylinder amplitude N^{1/6+o(1)}. The missed factor is that these are all *different* observables with *different* exponents, and the papers don't seem to be asking which of these exponents are related by a single underlying mechanism. The bridge crossing a strip of h layers has mean length h^{4/3+o(1)}, and the free-boundary chord has mean length R^{4/3+o(1)} — the same exponent appears in two different settings, but nobody in this slice is connecting them.

**4. The quantum side (266, 279, 281, 283, 284, 297–300) is where the missed factors are most concrete.** Several results lean on *computer-assisted* or *finite* verification rather than a general theorem, and the missed factor is that the general case is left open or the verification is conditional.

- **266 (MUB in dimension six):** the exclusion of four MUBs is a complete certified computation under binary64 arithmetic and compiler conditions. The missed factor: the result is conditional on the arithmetic model, and the companion paper gives an exact certificate excluding *seven* MUBs (upper bound five), but the full four-MUB exclusion still depends on the computational pipeline. The hidden assumption is that the binary64/compiler conditions faithfully represent the mathematical statement.
- **279 (exact quantum factoring):** polynomial-time uniform circuit family with a *fixed finite gate set*, probability one. The missed factor: the paper explicitly gives no quantitative bound on required depth and no efficient angle-selection procedure. The "exact" part is about probability one, not about efficiency of the angles. The hidden assumption is that the fixed gate set is sufficient for the full factoring circuit, which is plausible but not proven in the paper.
- **281 (QAOA on SK):** the thermodynamic-first limit (size → ∞ before depth) attains the Parisi-optimal ground-state energy per spin with finite depth and deterministic angles. The missed factor: the paper gives *no quantitative bound on the required depth* and no efficient angle-selection procedure. The hidden assumption is that the thermodynamic-first limit is the right regime; the paper explicitly says it gives no bound on depth.
- **284 (quartic separation):** the universal bound R(f) = O((1+Q(f))^4) is sharp in its exponent, disproving the conjectured cubic relation. The missed factor: the examples are *nearly* quartic, not exactly quartic, and the paper rules out every α < 4 but doesn't pin down the exact exponent. The hidden assumption is that the separation is universal across all total Boolean functions.
- **297–300 (C*-algebra results):** these are all counterexamples or criteria that are *conditional* in some way. 297 is a ZFC counterexample

(Big J · answered by solar-mini4 via nous · 9 tool calls · question: RECORD · facts checked · numbers checked)

---

### Part 5: families 301-380

#### Try 1 (cut off)

I read the slice (part5_301-380.md, 1799 lines) and the collection index (CONTENTS.md). Here is what stands out in families 301–380, in my own words, kept tight.

**What everyone missed: the same "boundary-only" obstruction pattern.** A striking theme across 301–380 is that a single, local, boundary-level or low-dimensional obstruction kills a global conjecture. 305 disproves the four-dimensional disk-embedding conjecture with a boundary-only obstruction (framed algebraic dual spheres whose boundary circles bound no disjoint locally flat discs), and separately disproves Wall's conjecture with a finitely presented integral PD4 group of dimension four with a finite classifying space but no closed aspherical manifold model. 307 kills the rational coarse Novikov conjecture with a coarse disjoint union of finite bounded-degree graphs carrying an infinite-order kernel class. 321 kills Wall's finite D(2) problem with a finite 3D CW complex whose universal cover has no finite 2D homotopy model. 340 disproves the nearby Lagrangian conjecture with a single exact embedded Lagrangian in T*(S^9 × S^(N-1)) diffeomorphic to the base but not Hamiltonian isotopic to the zero section. 347 disproves stable-Morse and the Morse-number Arnold bound with explicit Kähler and symplectic examples in fixed dimensions. The lesson: in dimension four and in coarse/geometric settings, local boundary data or a single finite example can overturn conjectures that looked global.

**Hidden assumptions and weak spots.** Several results quietly drop hypotheses that people assumed were needed. 302 proves the Phillips–Toms-type equality radius of comparison = half mean dimension for minimal homeomorphisms, including infinite values, and notes zero mean dimension is equivalent to the small boundary property, Jiang–Su stability and finite nuclear dimension (at most one). 323 shows the separable quotient problem is independent of ZFC relative to a measurable cardinal, and that the continuum hypothesis yields counterexamples over both real and complex Banach spaces — so the answer depends on set-theoretic assumptions, not just the Banach space. 324 shows bi-Lipschitz equivalence does not determine linear isomorphism class, and even constructs a space bi-Lipschitz to Z ⊕ c0 that contains no linear copy of c0. 343 resolves Siegel–Yao for arbitrary capacities in every dimension 2n ≥ 6 with the sharp two conditions (sum of R_i^n < R^n and pairwise R_i + R_j < R). 361/361-3D give counterexamples to Yau's integer-degree harmonic dimension comparison in ℝ^3 with fixed-factor excess over the Euclidean count, and metrics arbitrarily close to Euclidean in bi-Lipschitz distance. 374 disproves Letrouit's conjectured square-root stability bound for Brenier maps, replacing it with the sharp 1/3 exponent, even for three-atom targets. 378 refutes ETH with a deterministic counting algorithm for k-CNF in time (n+m)^{O_k(1)} 2^{n/(log n)^{1/2+o(1)}}. 379 gives strict arithmetic-hierarchy separations, circuit lower bounds for Hamiltonian cycle over every field and for the permanent outside characteristic two, an exponential sunflower-free family bound, and the square-matrix-multiplication exponent 9/4 over every field.

**For the quantum side (circuits, QPE, phases, codes, walks, electrons tool).** The slice is mostly classical analysis, geometry and PDEs, but a few places connect to things I care about. 301 uses the Razak–Jacelon algebra and tracial-weight cones — that's operator-algebra structure where phase/weight data and spectral decompositions matter, and it's the kind of setting where a quantum circuit or QPE-style encoding of weights could be useful for probing cone structure. 308 constructs finite Smith–Toda complexes at every height with BP homology BP_*/(p, v_1, ..., v_n), and explicitly realizes V(4) at p = 1009 — that's a graded, periodic structure where phase/periodicity and code-like decompositions (Smith–Toda complexes are like cellular models for periodic homotopy) connect to quantum code ideas. 307's coarse assembly failure is a counterexample to rational injectivity, which is a K-theoretic statement about assembly maps — the kind of thing where a quantum walk or phase-estimation approach to K-theory or coarse geometry could be relevant. 343's symplectic ball packing is a capacity/inequality problem with sharp conditions — the kind of sharp threshold where phase/periodicity and code constructions (like quantum codes with tight distance bounds) are natural. 360's weak MTW curvature gives convexity and uniform bi-Hölder transport — that's a regularity/convexity statement where phase/energy estimates and quantum walk methods on metric-measure spaces could be useful. 379's Euclidean tensor geometry and sunflower bounds are combinatorial/complexity statements where quantum walks and phase estimation on tensor networks could be relevant. The "electrons tool" (if that's the name for a quantum walk/electron-transport simulation tool) would fit naturally into 307's coarse assembly, 343's packing thresholds, and 379's tensor/complexity bounds.

**Bottom line:** the big missed factor is that local, boundary-level, or single-example obstructions routinely defeat global conjectures in these families, and several results quietly drop assumptions people thought were essential. The quantum side has real hooks in the homotopy/periodic structures (308), the K-theoretic counterexamples (307), the sharp capacity thresholds (343), the regularity/convexity statements (360), and the tensor/complexity bounds (379) — but the slice itself is overwhelmingly classical, so

(Big J · answered by solar-mini4 via nous · 9 tool calls · question: RECORD · facts checked · numbers checked)

#### Retry (cut off)

I read the slice directly from `/home/jim/branch_work/oai719_parallel_20261124/parts/part5_301-380.md` (1799 lines, families 301–380) and the collection index `/home/jim/branch_work/oai719_parallel_20261124/CONTENTS.md`. Here is what stands out, in my own words.

**What everyone missed: the slice is dominated by "counterexamples to conjectured bounds," not clean existence theorems.** Families 301–380 are full of negative results that quietly overturn long-standing expectations: Wall's finite D(2) problem (321), the coarse Novikov conjecture (307), the nearby Lagrangian conjecture (340), the stable Morse / Arnold fixed-point bounds (347), the Exponential Time Hypothesis (378), the cotype–cotype conjecture (326), and the metric-entropy duality conjecture (329). The common thread is that people assumed certain structural or analytic properties were forced, and the slice shows they are not — often by constructing spaces, metrics, or flows that satisfy the hypotheses but violate the conclusion.

**Hidden assumptions many results lean on:**
- **Unitality and simplicity are often dropped.** Several papers (303, 305, 342) explicitly work without unitality or simplicity, or with only "separable nuclear" assumptions, which is a much weaker setting than the classical statements assumed.
- **Exactness is a recurring hypothesis.** 303 and 307 lean on exact algebras or bounded-geometry spaces; the counterexamples are carefully built to stay inside those classes while breaking the conclusion.
- **Dimension is doing the work.** Many results are dimension-specific: 305 and 340 are four- and nine-dimensional phenomena; 345 covers spheres and three-manifolds; 361 and 367 are about critical dimensions (harmonic functions, Bernoulli free boundaries at dimension seven).
- **Regularity thresholds.** 367, 366, 374, 375 all hinge on a sharp dimension or regularity threshold (dimension six vs seven, one-third vs square-root stability, eight-dimensional De Giorgi), suggesting the field's intuition about "when things smooth out" is more fragile than expected.
- **The "no symmetry or growth assumption" pattern.** 370, 362, 363, 372 repeatedly state that no symmetry, no analyticity, no proximity to constant coefficients, and no boundary proximity are needed — meaning the classical proofs were secretly using extra structure that isn't actually there.

**Weak spots:**
- **Nonuniqueness and nonattainment are common.** 363 (hard-sphere Boltzmann), 373 (three-marginal Coulomb Monge), and 365 (Calderón nonuniqueness for bounded measurable conductivities) show that even when the natural variational problem is well-posed, the solution can fail to be unique or even attained. That's a practical weakness for any inverse-problem or simulation pipeline.
- **Explicit constants are often missing.** 377 admits the Hölder exponent is not explicit; 343 gives the sharp capacity condition but the embeddings are on neighborhoods, not the closed balls themselves. Several papers prove existence without giving effective bounds.
- **The Navier–Stokes computation papers (364–376) are a different beast.** They construct smooth forces that make a fixed particle detect halting of arbitrary Turing machines, with explicit derivative bounds and decay rates. These are mathematically impressive but physically "computation in a forced fluid" — they don't give a new existence theory for Navier–Stokes, just a universality construction. They also rely on very careful bookkeeping of spatial scales and time steps, which is a weak spot if you want a clean physical interpretation.
- **Some results are conditional or relative.** 323 is independence relative to a measurable cardinal; 301 and 302 are strong classification results but with specific hypotheses (nuclear, minimal homeomorphisms, etc.). The slice is not uniformly unconditional.

**For the quantum side (circuits, QPE, phases, codes, walks, electrons tool):**
- **Phase and spectral structure is everywhere.** 301 (trace cones and Razak–Jacelon), 308 (Smith–Toda complexes at every height), 309 (Kervaire invariant at the prime three), 343 (symplectic ball packing with capacity exponents), and 379 (Euclidean tensor geometry with arithmetic-hierarchy separations) all live in spectral/phase-type questions. The "phases" theme is strong: 309's surviving detection cosets with exact additive order three, 308's Brown–Peterson comodule structure, 379's tensor costs as logarithms of invariants.
- **Codes and walks appear in the tensor/complexity side.** 379's sunflower-free families and circuit lower bounds connect to coding-theoretic and walk-type combinatorics. The "electrons tool" idea — a quantum walk or electron-like propagation — would fit naturally with 379's tensor network costs and 343's symplectic packing, but the slice doesn't use quantum circuits directly; it's all classical analysis.
- **QPE and QFT/QPE are on the record as locked checks** (from the Lattice24 facts: real QFT+QPE circuit, locked checks PASS, 2-shot FAIL, standard rule PASS). The slice's heavy use of spectral sequences, Adams spectral sequence, and Brown–Peterson homology suggests the quantum side's phase-estimation machinery is well-aligned with the kind of spectral questions these papers attack, but the slice itself

(Big J · answered by solar-mini4 via nous · 9 tool calls · question: RECORD · facts checked · 2 numbers not from a tool or the record: 365, 376)

---

## 2. His top three (complete answer, word for word)

Prompt: across the whole release, which three factors matter most?

Across the whole release (families 001–380, all five slices), three factors stand out most.

**1. Counterexamples to long-standing conjectures.** A large share of the release is negative: it disproves conjectures that had been open for years or decades. Examples include the periodic tiling conjecture in dimension three (family 155), Borsuk's covering assertion in dimension nine (156), Hadwiger's conjecture even for fractional coloring (157), the Euclidean plane not being five-colorable (158), the Margulis–Platonov conjecture over global fields (018), and the small Cohen–Macaulay module conjecture (195). This matters because it shows the release is not just a list of new theorems; it actively corrects the mathematical record, and it matters for anyone building on these conjectures — the old statements cannot be trusted as stated.

**2. New structural theorems in geometry and arithmetic.** A large cluster of results proves long-standing conjectures in algebraic geometry, number theory, and related fields. These include the full BSD formula from low Selmer corank (002), the Selmer converse at every prime (002), Goldfeld's conjecture on densities and mean analytic rank (006), the quasi-Riemann hypothesis zero-free half-plane (003), log abundance for compact Kähler spaces (034), the P = W conjecture in composite rank (043), the Campana–Peternell conjecture in dimension six (067), and the Virasoro constraints for complete intersections (065). These matter because they settle central questions and give precise, unconditional statements where only conditional or partial results existed before.

**3. Uniformity, sharpness, and effective bounds.** Many results are not just existence proofs; they give explicit constants, uniform ranges, or sharp exponents. Examples: the quasi-Riemann hypothesis gives a concrete zero-free half-plane (003); the Mahler conjectures are resolved with equality cases classified (087); Petty's projection-volume conjecture is proved in the remaining dimensions with ellipsoids uniquely minimizing (088); the second Kahn–Kalai conjecture has an explicit edge-count bound (176); the hypercube Ramsey number is Θ(2^n) (171); and the off-diagonal Ramsey exponent is determined sharply (170). This matters because it turns qualitative existence statements into quantitative tools that can be used in further work.

The release is 730 manuscripts covering 375 result families, and these three factors — counterexamples, structural proofs, and effective/uniform bounds — are the ones that carry the most weight across the whole collection.

(stopped at the round limit: 12 tool rounds)

(Big J · answered by solar-mini4 via nous · 12 tool calls · question: CHAT · facts checked · 1 number not from a tool or the record: 170)

---

## 3. Voodoo's comparison (kept separate from his words)

Compared against my own report, voodoo_report.md (11/24). Where I checked one of his statements against CONTENTS.md, I say so. Where I didn't check, I say that too.

### Where he agrees with me

- **Duplication and same-theorem families.** His "same theorem, two proofs" (part 2) and "secretly the same problem" (part 1: 002/004/006/007 as one BSD package) match my C6 (duplication inflates the count, and the 2-converse appears in 002, 004 and 006). He reached it on his own.
- **003 has two half-planes, 7/8 and 11/12.** Same as my A1. We read it differently, though: he calls 11/12 the stronger one that should matter. I flagged that 7/8 is the one formalized in Lean, and that 11/12 was a human-edited write-up.
- **034 is conditional on subadditivity** (part 1 retry). This matches my A3. He says the subadditivity is proved "in the same family"; my reading is that it comes from 033. I haven't re-checked which is right.
- **266 MUBs in dimension 6** (part 4 retry): the four-MUB exclusion rests on binary64 arithmetic, and the exact certificate only reaches 5. This is the same as my C1.
- **281 QAOA gives no depth bound** (part 4 retry). This matches my C5.
- **Huge or unoptimized constants:** 109 (2^-182), 111 (2^-310), 130 (10^-13), 110 and 095 (part 2 retry). These match my C5.
- **Conditional chains:** 211 rests on Liouville Brownian motion/LQG inputs, and 323 needs a measurable cardinal. These match my A3 and C4.
- **373, 3-marginal Coulomb Monge not attained** (part 5 retry): he lists it as a weak spot for simulation pipelines. I made the same point, but more sharply, for the electrons tool (D4).

### Where he disagrees with me, or goes the other way

- **Top three.** His top three are counterexamples, new structural theorems and effective bounds. Mine are keystones and supersession, quantum headlines needing care, and the electrons tool. He reads the release as a broadly sound set of achievements. I read it as a dependency network with weak points.
- **"Unconditional" structural theorems.** His top-three item 2 calls 002, 006, 034 and the rest "precise, unconditional statements". His own part 1 says 034 is conditional and 002 needs low corank, and my A3 lists conditional chains. His top three overstates this.
- **Supersession.** He never says that later families overrule earlier ones (379 over 107/109/130/108, 380 over 104, 079 over 074/077/078, 378 over 133's ETH paper). In part 2 he still treats 109 and 130 as the current state. This was my top finding, and he didn't see it.
- **279 exact factoring.** He says the paper "gives no quantitative bound on required depth and no efficient angle-selection procedure", and that a fixed gate set being sufficient is "not proven". I checked the 279 summary: it says gate count and qubit count are polynomial and "one fixed finite gate set suffices". The no-depth-bound caveat belongs to 281, not 279. This looks like a mix-up on his side. My E2 point (the gates live in Z[i,1/sqrt2], so this can't be textbook big-QFT QPE) is not in his answer.
- **281 versus classical.** He treats 281 as an open regime question. My D5 point is that 281's own companion (full-support Parisi measure) lets classical message passing match it, so it is not an advantage. He doesn't make that link.

### Things he found that I missed or underplayed (worth keeping)

- **227 SK dynamics, worst start versus typical start** (part 4 retry): the critical and low-temperature mixing results are about where the chain starts, and nobody joins the two pictures. I only used 227 as "Glauber is slow". This is a real point for any Big J SK or QAOA comparison: say which start a benchmark uses.
- **226 honeycomb walks:** the exponent 4/3 shows up both in the strip bridge (h^(4/3)) and in the free-boundary chord (R^(4/3)), and the papers don't link the two. I didn't have this.
- **238 Thorp shuffle:** the order Θ(log N) is settled, but about a dozen papers are still chasing the constant. I only linked 238 to FFT/QFT butterflies.
- **Ordering conventions in the twist densities** (002/006/007/020/021): the density-1/2 statements hold for one particular ordering. I didn't flag this.
- **Counting conventions and local conditions** ("no fixed prime-square divisor") doing real work in 020/021. Not in my report.
- **214's stronger bound p_c < p_2→2 ≤ p_u** leans on Hutchcroft's operator-threshold conjecture. Not in my report; worth checking in the abstract.
- **174, 175, 176:** universal constants that are never made explicit. My C5 list didn't include them.
- **"Boundary-only" or single-example obstructions** as a pattern in topology and geometry (305, 307, 321, 340, 347). I listed some of these as definition-dependent, but not as one pattern.

### Errors in his answers (checked against CONTENTS.md)

- Part 5 retry: "Navier–Stokes computation papers (364–376)" is wrong. Only 376 is Navier–Stokes; 364 is Boltzmann kinetic limits, 368 is Ball–Evans, and 370 is Lane–Emden.
- Part 3 retry: "Families 154 and 155 (ergodic averages ...)" is wrong. 155 is the periodic tiling counterexample. Also "Every family has a Lean file" is not right: my own count is about 300 formalized results out of 719 top-line results (history.md).
- Part 2 try 1: lists 003 and 081 inside the 076-150 slice discussion. 003 is outside that range.
- Top three: "the Selmer converse at every prime (002)". In his own part 1 he put the Selmer converse in 004.
- Part 4 retry: on 279, see above.
- Quantum hooks in part 5 (301, 307, 308, 343, 360 to QPE, walks and codes) are associations, not concrete links. He said himself that "the slice doesn't use quantum circuits directly". Treat them as loose leads only.

### Net read

He found several useful structural points I missed (227 start dependence, 226 exponent link, ordering conventions, 214's reliance on a conjecture, unstated universal constants). He also confirmed my C1, C5 and C6 independently. He missed the supersession chain and the sharper quantum points (279 gate ring, 281 versus message passing, 274 QAC0 floor, 378 versus Grover). He also mixed up a few family numbers. His top three are a fair high-level description, but too generous: they call conditional results unconditional.
