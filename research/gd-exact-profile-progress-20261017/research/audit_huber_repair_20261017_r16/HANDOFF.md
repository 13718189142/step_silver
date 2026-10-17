# R16 capped-coordinate repair audit handoff

**Result: MANUAL ACCEPTANCE of the finite-data lemma, with only three local wording/definition clarifications.** This is not verifier acceptance or a resolution of the original minimax goal.

Audited object: `research/resume_20261017_r16/HUBER_DATA_REPAIR.md`, SHA256 `f3ec09994edffe985742f80ae8603bc97da5864165689c07dfbd89ded770422b`. Detailed independent derivations are in `AUDIT.md` beside this file. The original object was not edited.

The audit checks the entire original physical word, including arbitrary prefix steps equal to or larger than the root, zero steps, `b=0`, and `Delta=0`. Prefix motion is safe because `z_i-h_i b=(P_{i+1}+eta)b`; after the root the unshifted coordinate stays in a flat minimum. Every ordered interpolation row is accounted for. The two cross orientations receive exactly `(H-eta)b^2` and `(P_i+eta-1)b^2`.

Full interpolation is justified by an explicit same-dimension convex conjugate construction. The prototype need not already be globally feasible. The resulting single static function is finite, convex and 1-smooth, realizes the exact combined GD trajectory, retains the original selected zero minimizer and positive terminal value, and uses only one appended coordinate. There is no hidden dimension or minimizer charge.

Exact added original squared radii are `(P+eta)^2 b^2` for the unshifted version and `(P+H)^2 b^2` for the translated terminal-core version. Translation produces the stated prefix heights `(H-eta)b^2`; it preserves every non-star residual and the star remains at zero. The projection-hull realization is valid when all prototype heights vanish and the unshifted correction is used.

For `H>=2`, `H/B_n<=C`, and `P/H<=K`, either balanced variant satisfies the explicit uniform estimate

\[
M/(B_nE_n)\le4C(K+1)^2\,\Delta/E_n.
\]

This confirms the conditional negligible-cost claim; it supplies none of its missing all-word hypotheses.

Local clarifications for the parent:

1. "Positive conjugate heights" requires `b>0`; at `b=0` they are zero.
2. "Non-diagonal root" likewise refers to a nontrivial repair `b>0`.
3. Define the asymptotic comparison scale `B_n>0`; for the intended benchmark use `B_n=(U_n^ZJ)^(-1)=2S_bullet(n)+1`.

No further agents/models, mathematical programs, arrays, solvers, services, truth-store edits, formal submissions, publication, or original-source changes occurred. This one sequential finished-object audit is complete before the 2026-10-17 05:05:00 UTC deadline. No grant is renewed. The all-word small-defect construction and globally transported recursive cost remain open.
