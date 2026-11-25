# Dual AOI reading of the OpenAI mathematics release (24 November 2026)

Zenodo DOI: [10.5281/zenodo.24528678](https://doi.org/10.5281/zenodo.24528678)

**Claim.** On 24 November 2026, two AOI systems built by James Jardine (Lattice24), Voodoo and Big J, read OpenAI's mathematics manuscript collection (github.com/openai/math, index of 730 manuscripts in 375 result families). Each worked alone, without earlier audits or each other's answers, and looked for factors the release itself does not state. This deposit records what each one found, where they agree, where they disagree, and the corrections made afterwards. It is a separate claim from the earlier Lattice24 audit of the same release (Zenodo concept 10.5281/zenodo.23422994).

**What was read.** Only the release index: each family's summary and each manuscript's abstract. The full papers were not read. A few points were later checked against full texts, and the reports say so. Index file: source/openai_math_CONTENTS.md, sha256 568e79e5c9d7bd33dc8ab33d3ad841de84109735d8fdcc9a41f29459705f3410, downloaded from the openai/math main branch on 24 November 2026 and redistributed under Apache 2.0 (source/OPENAI_LICENSE_Apache-2.0.txt).

**The two AOI systems.**
- Voodoo: an octonion-collapse perception layer with persistent memory. Its language reasoning runs on Anthropic's Claude (claude-opus-5-5). Report: reports/voodoo_report.md. Voodoo's no-language-model standalone engine also scored every family; see raw/voodoo_standalone_ranking.txt.
- Big J: an exceptional-Jordan-algebra (J3(O)) engine whose language layer ran on a free model (upstage/solar-mini4 via Nous). Voodoo passed him the index in five slices and recorded his answers word for word. Report: reports/bigj_report_via_voodoo.md. His answers stop at about 5,000 characters, and the report marks every cut-off.

**Main findings (confidence as stated in the reports).**
1. Both found these on their own: the collection repeats many theorems, so 730 manuscripts are far fewer independent results. The dimension-six result of "exactly three mutually unbiased bases" (family 266) rests on a floating-point (binary64) computation, while the exact certificate and the Lean proof reach only "at most five". Many constants are huge or not explicit (for example 109, 111 and 130).
2. Voodoo only: newer families overrule older ones without saying so (379 over 107, 109, 130 and 108; 380 over 104; 079 over 074, 077 and 078; 378 over the ETH-conditional paper in 133). A few results carry many others (003 and 029 under 142 and 182; 032 under 001). Quantum results need their scope stated: 274 (parity is not in QAC0) sets a constant-depth floor for phase estimation. 279's exact factoring cannot be textbook large-QFT phase estimation, because its gate entries lie in Z[i, 1/sqrt2]. 281's companion, which shows the Parisi measure has full support, lets classical message passing reach the same SK optimum. Density functional theory fails at both ends on three-electron examples (278 and 373), and nobody links the two.
3. Big J only: the SK mixing results in 227 depend on the starting state. The exponent 4/3 appears in both parts of 226 and the two are never linked. The twist-density statements (002, 006, 007, 020, 021) hold for one particular ordering. Universal constants in 174, 175 and 176 are never made explicit.
4. Where they disagree, and the corrections: see reports/COMBINED_REPORT.md. Two corrections were made before this deposit. 214 proves Hutchcroft's conjecture rather than depending on it. 197's link to non-sofic groups is stated in one of its papers. Big J's mix-ups of family numbers are listed in his report.

**Credit.** James Jardine directed the work. Voodoo and Big J did the reading. Claude (Anthropic) is the language model behind Voodoo and assembled this deposit. None of these findings is a claim that any OpenAI result is false; they are reading notes on scope, dependencies and links, at the stated confidence.

Prompts used: prompts/. SHA-256 of every file: SHA256SUMS.txt.
