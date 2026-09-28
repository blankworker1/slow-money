# Two Ledgers — Financial Literacy Test

An online multiple-choice test that measures financial literacy on two axes at once: how well a person is adapted to the current money system, and how well they understand the structure and risks of that system.

Origin: designed in September 2026. The first working prototype is a single HTML file (add it to this folder as `index.html`).

## Why two modules

The standard international benchmark is the OECD/INFE Toolkit for Measuring Financial Literacy, used by Banca d'Italia (in its IACOFI survey) and dozens of other countries. It is a good instrument, but it measures adaptation to the existing monetary system, not analysis of it. It treats bank saving as the default, inflation as a fact of nature rather than a policy outcome, and every financial product as something held through an intermediary. It has no concept of a bearer asset, self-custody or counterparty risk.

Rather than rewrite the benchmark, the test keeps it intact and adds a second, parallel module.

- **Module 1 — OECD/INFE core.** The standard knowledge, behaviour and attitude items, kept intact so scores stay comparable with national data, including Banca d'Italia benchmarks.
- **Module 2 — Monetary Sovereignty & Structural Risk.** Currency debasement, counterparty risk, fractional reserve banking, physical cash, gold and Bitcoin. Cash and physical assets carry equal weight with Bitcoin; an early draft over-weighted Bitcoin and was rebalanced.

## Design decisions

- **Audience:** adults 18+, matching the OECD and Banca d'Italia standard. (Versions for younger ages belong to the wider Slow Money series and are not yet designed.)
- **Shape:** both modules use the same 7 + 9 + 5 structure: 7 knowledge items, 9 behaviour items, and attitude items worth up to 5 points. Each module produces a composite score from 0 to 21.
- **No pass or fail:** there is no threshold. The result is a position, not a grade.
- **Learning as well as measuring:** each question is preceded by a short framing paragraph, so the test doubles as a learning tool. In Module 1 the framing gives only context and stakes, never the answer, to protect comparability with national scores.
- **Attitude scoring:** a simplified conversion rather than the OECD's exact Annex A formula. Each Likert response is normalised to 0–1, reversed where needed, averaged across items, then scaled to 5.
- **Results screen:** the two totals shown side by side, plus a scatter plot placing the person on both axes at once.
- **Wording:** the OECD questionnaire is written to be read aloud by an interviewer and is copyrighted. Final Module 1 wording should be taken from the official source and lightly adapted for self-administered online use.

## Language

Italian first for public use, with English maintained alongside.

## Next steps

Development continues as part of the Slow Money project. The original design chat has been renamed to mark it as part of Slow Money.

- [ ] **Check alignment with Slow Money.** Review both existing modules against the [Manifesto](../../00-manifesto.md) before building further. In particular, check whether the test still treats the individual as the only unit, when Slow Money treats the household as the first economy.
- [ ] **Add a third module: Family Ledger.** Questions about the household as an economic unit: how money is discussed at home, whether combined earnings are known as well as shared spending, which exchanges are recorded and which are given freely, and what financial habits and mindset were inherited or are being passed on.
- [ ] **Decide how the third module scores and displays.** The current results screen places a person on two axes; a third module needs its own place in the results.
- [ ] **Consider a household version.** Taken together at the kitchen table by two or three generations, where the most useful output is where family members answer differently.

## References

- OECD/INFE Toolkit for Measuring Financial Literacy, Inclusion and Well-Being: https://www.oecd.org/en/publications/oecd-infe-toolkit-for-measuring-financial-literacy-inclusion-and-well-being-2026_92f2d439-en.html
- Existing Italian quizzes for comparison: quellocheconta.gov.it, AlfaFin
