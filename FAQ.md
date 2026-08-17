# FAQ

### Is this a certification?

**No.** It is self-declared, with zero gatekeeping. There is no body that checks your
pipeline, no application to file, and nobody to grant you anything. You read the five
commitments, decide for yourself whether your pipeline meets them, and add the badge — the
same model Contributor Covenant uses for codes of conduct.

If you want an outside look at a specific claim about a specific dataset or pipeline, that is
a different thing, and it lives in the
[PIT audit registry](https://github.com/MaxWellApexLab/pit-audit-registry).

### Do I need `pit-release-gate`?

**No.** Commitment 5 says *screen for leakage*, not *screen with our tool*. Any susceptibility
screen counts, including one you write yourself. `pit-release-gate` is named as the one we
maintain and can support, because a commitment with no runnable tool behind it tends to stay
aspirational — but the pledge is deliberately not tied to it.

### Someone pledged and their pipeline is obviously broken. Now what?

The pledge is a claim by its author, not a finding by anyone else, and a self-declared badge
carries exactly as much weight as the person who put it there. If a specific claim looks
wrong, the useful move is to open an issue on *their* repo with the reproduction.

If you think a case is worth documenting properly, the audit registry publishes reproducible
findings on public datasets and pipelines. Those are measurements with commands attached, not
opinions about someone's badge.

### Who runs this?

Max Well Apex LLC. The completeness and arrival-selection commitments come out of three
publicly available preprints listed in the [README references](README.md#references); the
reference implementation of the screen is the MIT-licensed
[`pit-release-gate`](https://github.com/MaxWellApexLab/pit-release-gate).

### Can I use the pledge text in my own project / language / organisation?

Yes. The text is CC BY 4.0. Fork it, translate it, adapt the wording to your domain. If your
adaptation is good, open an issue and we will link to it.

### My data is not financial. Does this apply?

If your entities report on staggered dates and you compute anything cross-sectional over
them, yes. Public-health surveillance with backfilling case reports, administrative panels
with rolling submission deadlines, and sensor networks with heterogeneous upload lags all
have the same structure. The commitments are written to be domain-neutral; only the examples
in the references are financial.

### What if I meet four of the five?

Then say so, in your own words, in your own repo — "we meet 1–4; 5 is on the roadmap" is more
useful to a reader than a badge. The pledge is not graded and there is no partial badge.
