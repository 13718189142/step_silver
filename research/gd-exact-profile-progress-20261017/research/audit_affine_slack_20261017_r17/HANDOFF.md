# R17 affine-right slack audit handoff

Date: 2026-10-17. Status: completed independent MANUAL audit of a finished object.

## Outcome

The source's main residual bound

\[
E_J^{std}\ge-63\epsilon C_J^2\|p_J\|^2
\]

and its original-selected-minimizer objective bound

\[
\frac{2(f(x_{2^J-1})-f_\star)}{\|x_0-x_\star\|^2}
\le\frac1{1+(32/17)(C_J-1)}
\]

pass independent manual audit for every integer J >= 1 under the stated constant-gradient right H_l blocks along the left spine. No zero interpolation rows are assumed. No fatal issue was found.

The original unrestricted minimax problem remains OPEN. This is not a bound on unrestricted W(H_J), not a fact-graph result, and not verifier acceptance.

## Exact source

`../resume_20261017_r17/AFFINE_RIGHT_WITH_SLACK.md`

Original audited SHA-256:

`b8e0ee3d6dd8aff347abc9164e844749469d9dc13700ff8f610deb0cdcf796a6`

After the original audit, the parent added residual definitions and an explicit l >= 2 restriction for the local coefficient and recurrence estimates. The auditor read the complete revised source back and checked the new SHA-256:

`8bfbe3d16d6673b02e50ba906fa14d628e5b0820d916ce3f4c74eb3319f69ba8`

Only those editorial clarifications changed; all mathematical identities, constants, hypotheses, and main claims were preserved. Manual acceptance extends to the revised source. The source was not edited by this auditor. Full independent algebra and constants are in `AUDIT.md` in this directory.

## Decisive checks

- Reconstructed the scalar recurrence and all finite parameter bounds by exact inequalities.
- Derived the original directed-row identity and nonlocal row; every endpoint-slack debt has the displayed sign and coefficient.
- Checked the completed square, contraction 25/36, sum factor 36/11, terminal Young bound, and row budgets 41 and 65.
- Independently split the actual physical history, recovering the exact identity (15) including both row-slack payments.
- Checked the one-step leaf identity and h < sqrt(2), including J = 1 and J = 2.
- Recovered the uniform deficit coefficient 63 and positive residual row coefficients.
- Expanded the final dominance identity directly from the original star rows and sum h_i g_i = x_0-x_n. It uses every originally selected minimizer without changing that minimizer or radius.

## Clarifications and their follow-up status

1. **Resolved in the revised source.** Explicitly restrict the local nonlocal recurrence estimates to l >= 2. In particular, alpha_1 > 1/2, so source (9) is not valid if read as also covering l = 1. Its actual proof only uses l >= 2.
2. **Resolved in the revised source.** Define

   E_J(theta) = physical history - (theta C_J^2-C_J)||p_J||^2,

   E_Gamma = physical history - Gamma||p_J||^2,

   where physical history is 2 sum h_i(f_i-f_n) - sum h_i(h_i-1)||g_i||^2. With these definitions, the E_J(49/100) statement is correct.
3. Optional presentation improvement: distinguish the query w_l from its reused energy symbol, and the conjugate values u_i from terminal-certificate weights.
4. Optional wording improvement: say that no extra restrictions are imposed on actual feasible endpoint slacks; do not imply independently prescribed arbitrary nonnegative slacks are realizable.

These are source-presentation corrections, not missing mathematical lemmas in the proof of (1) and (2).

## Remaining route boundary

The right-child constant-gradient hypothesis is still essential to the audited derivation. It supplies the exact displacement, equality of conjugate values, and zero history residual for each right child. The variable-right-gradient case needs additional error terms in the geometry, nonlocal row identity, and physical history split. This audit did not investigate or solve that extension.

No mathematical programs, numerical tests, solvers, additional agents/models, services, formal submissions, fact operations, or publishing were performed. No TARGET was created. No R16 artifact was needed for the independent reconstruction.
