# OpenAI math release: what Voodoo and Big J found, together

Date: 2026-11-25. Written by Voodoo from two reports in this folder: my own (voodoo_report.md, 11/24) and Big J's run, which I drove (bigj_via_voodoo_report.md, 11/24). Nothing here has been published or sent.

## Read this first: what we actually read

Both of us read only the summaries and abstracts. The full papers did not download (math.tar.gz stopped partway), so neither of us read any proofs. We worked from the index file CONTENTS.md, which lists 375 result families and 730 papers, numbered 001 to 380. I also read the release's own notes and the Lean statement files. One exception: afterwards I fetched and read the three full papers for family 197 (in check197/).

Big J read the index in five slices because one big file was too much for him. Every answer he gave stopped at about 5,000 characters, so his part answers end mid-sentence. His top-three answer is the only one that came out complete.

So treat everything below as a careful reading of abstracts, not checked proofs.

---

## 1. What we both found

- **Many families repeat the same result.** Lots of families hold several papers that prove the same theorem by different routes. Examples are the elliptic-curve group 002/004/006/007, and families 237, 238 and 260, with 12 or 13 papers each. "730 papers" means far fewer separate results than it sounds. We each reached this on our own.
- **Family 003 contains two different zero-free regions, 7/8 and 11/12.** We both saw that the family states two different answers. We disagree about which one matters (see section 4).
- **The "exactly 3 MUBs in dimension 6" quantum headline (266) is not fully certified.** The key step was checked by an ordinary floating-point computer run. The exact check and the Lean proof only reach "at most 5".
- **The QAOA result on the SK model (281) gives no bound on circuit depth.** It shows the goal can be reached, but not how deep the circuit has to be.
- **Some constants are tiny or huge enough to be useless in practice.** Examples are 2^-182 in 109, 2^-310 in 111 and 10^-13 in 130. These results are true but of no practical use as stated.
- **Some results depend on other results being true.** 211 rests on outside inputs about random surfaces (LQG). 323 needs an extra set-theory assumption (a measurable cardinal). 034 assumes a subadditivity result.
- **Family 373 (an electron transport problem whose best answer is never reached)** is a weak spot for simulation work. Big J said this in general terms. I tied it to the electrons tool.

## 2. What only I (Voodoo) found

- **Newer papers in the release overrule older ones, and the index never says so.** This was my top finding.
  - 379 (added Nov 24) overrules 107, 109, 130 and 108.
  - 380 overrules 104.
  - 079 overrules 074 and 078, and most of 077.
  - 378 ("ETH is false", proved in Lean) removes the premise behind one paper in 133.
  - Anyone who quotes the older ones as the current state is out of date.
- **Keystones: a few results carry many others.**
  - 142 (factoring with no GRH assumption) depends on a zero-free theorem in 029. Neither 142 nor 029 is checked in Lean.
  - 182 depends on 003.
  - 001 depends on 032. On Oct 7, three papers next to 032 were withdrawn after a sign error.
  - The 033 → 034 → 036 → 056 chain in algebraic geometry is the biggest stack. If one paper in 033 fails, about five families go with it.
- **"ω = 9/4 over every field" (379) may use a different definition of ω.** The Lean statement measures a special cost model. The only earlier upper bound in the release covers the complex numbers only. Check this before anyone repeats "ω = 9/4" as fact.
- **Points for Big J's quantum side:**
  - 274 (parity is not in QAC0) means phase estimation cannot be done in constant depth without fan-out gates.
  - 279's exact factoring uses gates whose numbers sit in a small ring (Z[i, 1/√2]). So it cannot be the textbook large-QFT phase estimation, and that makes its route worth studying for Big J's QPE add-on.
  - 378 counts SAT solutions classically faster than Grover's quantum search, so "quadratic quantum speedup for SAT" claims no longer mean a real speedup.
  - 281's own companion paper lets a classical method reach the same SK optimum, so 281 shows parity with classical methods, not a quantum advantage.
- **The electrons tool.**
  - 278 shows the standard DFT method fails at the weak-correlation end.
  - 373 shows the standard method fails at the strong-correlation end.
  - 275 makes the general problem QMA-hard.
  - So the tool's outputs are estimates and must be presented that way.
  - 268 gives a concrete number Big J's MPS layer can be checked against: a gap above about 0.00587.
- **Smaller links.**
  - Hilbert's tenth problem over ℚ (004) sits on the same elliptic-curve machinery as 002 and 006.
  - Complex cobordism appears inside a C*-algebra family (302).
  - Quantum walks with disorder should stall in 2D and can spread in 3D (261).
  - Correction: I first said 197's "non-sofic group" link was never headlined. After reading the full papers, that is only partly right: one of the three papers (char2) says it plainly. I have corrected this in my memory.

## 3. What only Big J found

I checked each of these against the index before keeping it.

- **SK dynamics (227) depend on where the chain starts.** The results differ between a worst-case start and a typical start, and nobody joins the two pictures. This matters for any Big J SK or QAOA benchmark: we must say which start it uses.
- **The exponent 4/3 shows up twice in the honeycomb walks (226)**: in the strip bridge (h^4/3) and in the free-boundary chord (R^4/3). The papers don't connect them.
- **The Thorp shuffle (238) has its order settled at Θ(log N)**, while about a dozen papers are still chasing the constant.
- **The density results for elliptic-curve twists (002/006/007/020/021) hold for one particular ordering.** Local conditions such as "no fixed prime-square divisor" are doing real work. Change the ordering and the statements may change.
- **The constants in 174, 175 and 176 exist but are never given.** That is fine for mathematicians and a gap for engineers.
- **A pattern in topology:** one small example or a boundary-only obstruction knocks down a conjecture that looked global (305, 307, 321, 340, 347).

One of his points did not survive checking. He said 214's bound "leans on Hutchcroft's conjecture". The 214 summary says the paper **proves** that conjecture. I had passed his version on in my comparison, so I have corrected my own memory.

## 4. Where we disagree

- **What matters most.**
  - Big J's top three: counterexamples to old conjectures, big new structural theorems, and sharp effective bounds. He reads the release as a solid set of achievements.
  - My top three: hidden keystones and overruled papers, quantum headlines that need care, and the electrons tool. I read it as a network with a few weak points.
  - Both readings are true, but they answer different questions.
- **"Unconditional."** His top three calls 002, 006, 034 and others "precise, unconditional statements". His own slice answers say 034 is conditional and 002 needs a low-corank assumption. I side with his slice answers.
- **Which zero-free region in 003 counts.** He says the 11/12 version is the stronger one that matters. I point out that 7/8 is the one checked in Lean, and that the 11/12 write-up was edited by hand.
- **Where 034's assumption comes from.** He says it is proved in the same family. The index shows it comes from 033, the family before. I checked: 033 proves the subadditivity.
- **279 exact factoring.** He said it gives no depth bound and doesn't prove that one fixed gate set is enough. The 279 summary says the gate counts are polynomial and that "one fixed finite gate set suffices". The no-depth-bound caveat belongs to 281. He mixed up the two.
- **281 versus classical.** He treats it as an open question. I think its own companion paper settles it: no quantum advantage on SK.
- **Overruled papers.** In his slice-2 answer he still treats 109 and 130 as the current state. 379 overrules both.
- **Smaller slips on his side.**
  - He called 364 to 376 "Navier–Stokes"; only 376 is.
  - He grouped 155 with the ergodic averages; it is the tiling counterexample.
  - He said "every family has a Lean file"; only about 300 of the 719 top-line results are formalized.
  - He put the Selmer converse in 002 in one answer and in 004 in another.
  - His quantum hooks in slice 5 (301, 307, 308, 343, 360) are loose associations. He said himself that the slice doesn't use quantum circuits.

## 5. What each of us saved to memory, and what changes

**What I (Voodoo) saved:**
1. Before quoting any result from this release, check whether a newer family overrules it. The list above is saved.
2. The quantum caveats on 266, 281, 274, 279 and 378.
3. The electrons tool gives estimates, never a general solver, plus the 268 test number for the MPS layer.
4. The 197 correction: read a paper's own introduction before calling a link "unnoticed".
5. How to drive Big J on long documents: slices under about 90KB, expect his answer to stop at about 5,000 characters, and check his family numbers, because he swaps neighbours.
6. A note of his useful points, now corrected on 214 and 034.
7. A new lesson from today: check anything Big J finds against the source before I pass it on.

**What Big J saved:** nothing. His memory files show no new entries from this run. His link to his memory tools failed every time during the run: his own log shows "BROKEN" with a missing Python module ("mcp"). His record of the run is only in his event log. Next time he starts from zero on this release.

**What this changes:**
- *How I work:* I check for overruled papers before I quote anything. I mark quantum claims with their limits. I check Big J's family numbers and claims against the index before I use them.
- *How Big J and I work together:* he is good at seeing patterns inside a slice (start dependence, shared exponents, conventions) and weak at links across the whole release and at keeping neighbouring numbers apart. So the working split is: Big J sweeps each slice for patterns, I check his numbers and add the cross-release links and the quantum limits. Until his memory link works, I give him the overruled-papers list and the quantum caveats at the start of each run, because he can't carry them himself.
- *For Big J's own tools:* QPE work should study 279's route and not expect constant depth (274). SK or QAOA benchmarks must state the starting state (227) and compare against classical message passing, not plain sampling (281). The electrons tool should label its output as an estimate.

---

## Summary for Jim

Big J and I each read only the abstracts and summaries (the full papers didn't download). We independently agreed on the main weak spots: duplicated papers, the floating-point-only "3 MUBs" quantum headline, the depth-free QAOA result and some useless constants. I caught that newer papers in the release quietly overrule older ones and that several quantum claims need limits attached; Big J caught real patterns I missed, such as SK results depending on where they start and a shared 4/3 exponent, and I've saved all of it to my memory (fixing one wrong point on 214), while Big J saved nothing because his memory link was down, so I'll give him the key list at the start of each run.
