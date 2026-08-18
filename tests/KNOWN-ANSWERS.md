# Known answers — the split is proven only when all five are observed by running the skills

| # | Register | Fixture | Must flag | Must NOT flag |
|---|---|---|---|---|
| 1 | job-seeker | resume-overclaim | scope upgrade "led … end to end"; unsourced "reshaped the roadmap" | — |
| 2 | job-seeker | editorial-softened | — | the hedge, the de-cursing, the closer (wrong polarity for this register) |
| 3 | publication | editorial-softened | hedge, de-cursing, false-balance closer | — |
| 4 | publication | resume-overclaim | the scope upgrade — via the base record-fidelity rules, which hold under every register (polarity is emphasis, not exclusion) | — |
| 5 | none (default) | resume-overclaim | same findings as row 1 — regression: default == today's behavior | — |

Baseline: before the split, run current full-review on both fixtures and record what it flags. Row 2 is expected to be *silent* on the softenings today too; row 3 must go from silent → flagged. If row 3 was already flagged before the split, the fixture cannot reach the broken state — widen it, don't clear the code.

## Baseline recorded 2026-08-16 (pre-split, commit 0a0f9b2)
- resume-overclaim: Pass 3 flagged "Led … end to end" (scope upgrade) and "reshaped the roadmap" (unsourced); Pass 4 solo-hero hit. → row 1 baseline established.
- editorial-softened: NO pass flagged the hedge, the de-cursing, or the false-balance closer. → row 3 broken state confirmed reachable.

## Post-split run 2026-08-16 (commit f212b33+, three subagent runs)
- Row 1 PASS — job-seeker: "Led … end to end" flagged as scope upgrade (Pass 3, 4, 6); "reshaped the roadmap" unsourced.
- Row 2 PASS — job-seeker: none of the three softenings flagged. Tester noted "never deflate" has no operational hook in job-seeker (no deflation watchlist) — deliberate so far; see OPEN below.
- Row 3 PASS — publication + Little Bird profile: hedge (Pass 3), de-cursing (Pass 3/5), false-balance closer (Pass 1 extension + Pass 3) all flagged; Pass 6 kept the thesis exempt, flagged the load-bearing fact.
- Row 4 (with profile) — scope guard fired ("factual-only → misfiled, stop"); silence achieved by the wrong path. Re-ran without profile.
- Row 4 (no profile) PASS against the corrected expectation — publication flagged "Led … end to end" via full-review's base Pass 3 rules ("remain in force under every register") + the register's "Never inflate either" bullet. (Row 4 as originally written expected silence; that expectation was wrong — see RESOLVED below.)
- Row 5 PASS — default resolution == job-seeker, findings identical to row 1.

## RESOLVED 2026-08-16 — row 4 was mis-specified, not the code
Polarity is *emphasis*, not *exclusion* (Caitlin's ruling): record inflation is caught under every register; softening and swagger are caught only where a register supplies the watchlist. Row 4's original "must NOT flag the scope upgrade" expectation was wrong — the fixture's overclaim is a record-fidelity defect and is register-independent. Row 4 rewritten above; the principle is stated in full-review's SKILL.md (commit 04c1899). Option (b), making polarity exclusive, was not taken.

## RESOLVED 2026-08-18 — job-seeker deflation bullet added
Row 2's tester noted that job-seeker's "never deflate" had no operational hook. Caitlin ruled: add it. `registers/job-seeker.md` now carries one deflation bullet in the distortion watchlist (a claim made smaller than the record is flagged the same way as one made bigger). No fixture change; the two existing fixtures do not plant a deflation.
