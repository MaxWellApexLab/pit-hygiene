# The PIT Hygiene Pledge

[![PIT Hygiene](https://img.shields.io/badge/PIT%20Hygiene-pledged-2ea44f)](https://github.com/MaxWellApexLab/pit-hygiene)

**Five commitments for pipelines that feed models from staggered-arrival data.**

[![PIT Hygiene](https://img.shields.io/badge/PIT%20Hygiene-pledged-2ea44f)](https://github.com/MaxWellApexLab/pit-hygiene)

If the entities in your data report on different dates — companies filing statements,
clinics reporting cases, agencies publishing revisions — then the panel you train on is
assembled out of records that arrived over time. Almost every leakage bug in that setting
comes from forgetting it. The pledge below is a self-declared statement that your pipeline
does not forget it.

This is a **pledge, not an audit**. There is no gatekeeper, no application, no review.
You read the five commitments, decide whether your pipeline meets them, and add the badge
if it does — the same way projects adopt Contributor Covenant or a code-style convention.

---

## The five commitments

**1. As-of joins everywhere.**
No value is read before its availability timestamp.
*Why:* a join on the period a value describes, rather than the moment it became knowable,
silently imports the future into every row it touches.

**2. Arrival timestamps are kept, not discarded.**
Every record carries when it became available, not only what period it describes.
*Why:* you cannot audit what you did not record — once the arrival time is dropped, no
later analysis can reconstruct what was knowable when.

**3. No silent restatement backfill.**
Revised values enter as new vintages; they never overwrite the value that was originally
published.
*Why:* overwriting history makes yesterday's backtest unreproducible and quietly upgrades
the past with knowledge nobody had at the time.

**4. Completeness is gated, not assumed.**
Cross-sectional and derived values state how much of their group had arrived when they were
computed.
*Why:* a cross-sectional quantity computed before the group finished reporting is estimated
on a partial population, and a correct as-of join over a partial population is still a
correct join over a biased sample.

**5. Leakage is screened, not presumed absent.**
Derived signals get a susceptibility screen before release — any tool; ours is
`pip install pit-release-gate`.
*Why:* "we used point-in-time data" answers whether values were readable, not whether the
set of entities that had reported was a selected sample. Those are different failures with
different fixes.

---

## Adopting the pledge

1. Read the five commitments and check them honestly against your pipeline.
2. Copy a badge snippet from [badge-snippets.md](badge-snippets.md) into your README.
3. Optionally link the badge to a short note in your own repo saying how each commitment is
   met — that is what makes the badge worth reading rather than worth scrolling past.

There is nothing to submit and no one to notify. If you later find your pipeline does not
meet a commitment, remove the badge. Questions are answered in [FAQ.md](FAQ.md).

---

## References

The completeness and arrival-selection commitments (4 and 5) are developed in three
publicly available preprints:

1. Wu, K.-T., & Wu, K.-I. (2026). *Correct-by-Construction Factor Computation: A Verifiably
   Point-in-Time Engine for Tradeable Signals.* figshare.
   [doi:10.6084/m9.figshare.32952482](https://doi.org/10.6084/m9.figshare.32952482)
2. Wu, K.-T., & Wu, K.-I. (2026). *Measuring Incomplete-Cross-Section Leakage: A Matched
   Placebo, a Susceptibility Screen, and Evidence from Taiwan and US As-Filed Data that the
   Channel Is Benign and Correctable.* figshare.
   [doi:10.6084/m9.figshare.33061955](https://doi.org/10.6084/m9.figshare.33061955)
3. Wu, K.-T., & Wu, K.-I. (2026). *Susceptibility-Graded Release Control: Preventing
   Incomplete-Cross-Section Leakage in Financial Machine-Learning Pipelines without a Blanket
   Timeliness Penalty.* figshare.
   [doi:10.6084/m9.figshare.33158615](https://doi.org/10.6084/m9.figshare.33158615)

The broader leakage literature these build on:

4. Kaufman, S., Rosset, S., Perlich, C., & Stitelman, O. (2012). Leakage in data mining:
   Formulation, detection, and avoidance. *ACM Transactions on Knowledge Discovery from Data*,
   6(4), 1–21. [doi:10.1145/2382577.2382579](https://doi.org/10.1145/2382577.2382579)
5. Kapoor, S., & Narayanan, A. (2023). Leakage and the reproducibility crisis in
   machine-learning-based science. *Patterns*, 4(9), 100804.
   [doi:10.1016/j.patter.2023.100804](https://doi.org/10.1016/j.patter.2023.100804)

---

Maintained by Max Well Apex LLC. Text of this pledge is CC BY 4.0 — copy it, fork it,
translate it, no permission needed.
