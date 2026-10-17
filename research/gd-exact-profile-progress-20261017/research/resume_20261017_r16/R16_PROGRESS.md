# R16: a cheaper actual repair and an all-depth nonlocal-support estimate

**Original minimax target: OPEN. Application Goal: ACTIVE.** The new results are analytical drafts. The finite repair received a sequential independent manual audit; none of this round's results has been accepted by the Danus verifier.

This was a fresh bounded wave: two gpt-6-astra / ultra analytical calls and, after the complete repair lemma was written, one gpt-6-astra / ultra finished-object audit. No mathematical programs, numerical arrays, solver batches, formal submissions, or old worker restarts were used. R15's grants remained closed.

## 1. An actual repair that works at any long root

The strongest constructive change is in [HUBER_DATA_REPAIR.md](HUBER_DATA_REPAIR.md). It repairs arbitrary directed cross-block interpolation deficits by one additional capped coordinate and then interpolates the complete data by one static admissible function.

Let H>1 be any selected root, P the total physical mass before it, and Delta the largest cross-block deficit in either orientation. There is no prefix-maximum assumption. The two variants pay
\[
M_{\rm flat}\le\frac{(2P+H+1)^2}{2(H-1)}\Delta,
\qquad
M_{\rm core}\le\frac{2(P+H)^2}{H-1}\Delta.
\]
Both preserve the originally selected minimizer and the terminal objective. The second also preserves a zero appended terminal position, so a genuine prototype terminal-core condition survives. The original normalized payoff is exactly
\[
\frac{2f_n^0}{\|x_0^0\|^2+M}.
\]

This removes the inverse prefix-product sensitivity of R15's quadratic repair and permits repeated or larger earlier steps. The repair root is genuinely non-diagonal; this is why the old diagonal-root impossibility does not apply.

The [independent audit](../audit_huber_repair_20261017_r16/AUDIT.md) checked every physical update, both directions of every row, the unchanged star, full interpolation, both original-radius costs, and all degenerate cases. Its minor wording/scale clarifications are incorporated in the lemma. This is manual acceptance of the finite lemma, not the missing all-word theorem.

Additional parent analysis gives exact restricted-class prices in [CAP_REPAIR_OPTIMALITY.md](CAP_REPAIR_OPTIMALITY.md). With directional deficits A and B_i and remaining prefix masses P_i, the least terminal-core cost among independently admissible constant-gradient-prefix/stationary-tail repairs is
\[
(P+H)^2\max_{i\le r}\frac{A+B_i}{H-1+P_i}.
\]
For uniform deficits A=B_i=Delta and H>=2P+3, allowing a terminal flat displacement reduces the least cost to 4(P+1)Delta, independent of H.

**Remaining lower-route gap.** Actual near-benchmark prototypes, a uniformly small normalized defect, and a bound on the globally transported total cost are still missing. Explicit nodewise prices do not prove that their sum is negligible.

## 2. A full-depth result for a specified nesting mechanism

The [normal-geometry proof](../normal_geometry_20261017_r16/PROOF_ATTEMPT.md), Sections 1--3, now applies to any actual finite-dimensional convex 1-smooth function, not only projection envelopes. It retains the actual parameters
\[
\epsilon=(4m)^{-1},\quad \beta=1-\epsilon,\quad
c=(1+\sqrt2)(1+\epsilon),\quad a=\beta/c,
\]
\[
H_{j+1}=(H_j,1+ac^j,H_j),\quad C_j=1+\sum H_j.
\]

Its structural assumptions are essential: at every join on the left spine, the right child has a constant gradient, and both root-to-terminal interpolation rows vanish. All nonlocal original rows still have to hold. The first new right query tested against an older left query gives an inequality absent from the free scalar recurrence.

If p_l are the actual left-spine endpoint gradients and d_l=p_l-p_(l+1), that nonlocal row yields
\[
\|d_{l-1}\|\le2\|d_l\|,\qquad
\sum_l C_l^2\|d_l\|^2\le7C_J^2\|p_J\|^2.
\]
The exact history split and the uniform scalar defect bound then prove
\[
E_J^{\rm std}\ge-49\epsilon C_J^2\|p_J\|^2.
\]
In particular the needed theta=49/100 history inequality holds in this entire mechanism at every depth, including dimension growing with m.

The same argument gives its actual objective bound, for every originally selected minimizer:
\[
\frac{2(f_{\rm end}-f_\star)}{\|x_0-x_\star\|^2}
\le\frac1{1+(32/17)(C_J-1)}.
\]
Thus this class of nested normal-direction examples cannot refute the candidate upper bound by changing the selected minimizer or increasing its dimension.

**Remaining upper-route gap.** This is not a bound on the unrestricted supremum W(H_J). Nonconstant right-child trajectories and nonzero endpoint-row budgets are outside the proof. Extending the nonlocal estimate to those terms, with a paid error budget, is a concrete next target.

## 3. A correct reserve theorem and a stronger countercheck

The [terminal-reserve proof](../terminal_reserve_20261017_r16/PROOF_ATTEMPT.md) obtains a complete all-depth identity for the EXACT, unperturbed Silver hierarchy:
\[
E_j^{\rm std}+\rho C_j^2\|g_e\|^2
\ge\rho\|g_0\|^2,\qquad 0\le\rho\le2-\sqrt2.
\]
It provides all nonnegative row coefficients and the complete normal-displacement square. The actual subcritical leaf also has an explicit full PSD certificate. The all-depth exact-Silver identity does not automatically transfer to the perturbed words.

A different proposed simultaneous input was rejected by one static three-dimensional function:
\[
E^{\rm std}+\rho C^2\|q\|^2
\ge\sigma\|x_{\rm start}-x_{\rm end}+q\|^2.
\]
An affine-right equality family forces sigma<=rho/sqrt(2). In particular sigma=sqrt(2)-1 fails even with the full rho=0.51 reserve available for the theta=0.49 target. The fixed example continues to violate this charged inequality on the actual inherited three-step word for every m>=1536, with residual below -7/8.

This rejects the stronger charged invariant, not the requested weak history inequality. An earlier scratch sign error in a proposed affine-right exclusion was withdrawn, corrected, and replaced by the actual function; it is not used in any result.

## 4. Research judgment and next concrete work

The nonlocal old-query inequality is the most useful new ingredient for the previous upper-bound route. The natural continuation is to replace the constant right gradient by its actual varying trajectory and prove that the added terms are paid by retained interpolation rows, quadratic-face revisits, and the explicit terminal reserve. Repeating the disproved charged-displacement coefficient would not advance that task.

The capped-coordinate lemma is a usable second mechanism. It should be applied to a concrete hard-function prototype with measurable directed deficits, for example an ideal checkpoint construction. A further abstract deficit formulation, without a global estimate, would not close the lower route.

One parent lead for that application needs careful minimizer accounting. If a compact active face K_0 does not contain zero, one may run its projection-gradient prototype and then use K_alpha=conv{0,K_0 x {alpha}} with start (x_0,T/alpha). For each fixed finite word, a strict choice T>max_i[-<g_i,x_i-g_i>] keeps all queries on the active face for sufficiently small alpha. The closest polar-minimizer squared radius is exactly
\[
\max_{v\in K_0}\frac{(T+\langle x_0,v\rangle)_+^2}{\|v\|^2+\alpha^2},
\]
and the terminal numerator tends to \(2(F_{K_0}(x_n)+T)\). This differs from charging the full vertical starting coordinate relative to zero. It selects a valid original minimizer for the newly constructed instance; it does not permit silently changing the denominator of an existing witness. No concrete all-word near-benchmark prototype was produced from this lead, so it is not counted as a target result.

No complete original-target proof, certified asymptotic separation, unrestricted all-depth history input, or all-word negligible-cost construction was obtained. The exact original problem and W=2R normalization remain unchanged.
