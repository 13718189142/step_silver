# R16 terminal-reserve handoff

**UNVERIFIED. Requested actual-parameter all-depth E_j(49/100)>=0: unresolved. Original exact-profile target: OPEN.**

One fresh analytical invocation under the R16 grant; requested model/effort gpt-6-astra / ultra. At most two substantive approaches were used. No additional agent or model was called. Mathematical programs, arrays, solvers, formal submissions, service operations, truth-store writes, and publication are zero. The hard deadline was 2026-10-17 05:05:00 UTC; this invocation is closing before that deadline and has no renewal.

## Concrete positive result

For the EXACT Silver hierarchy, every finite dimension, every actual convex 1-smooth history, and every

\[
0\le\rho\le2-\sqrt2,
\]

the proof attempt derives

\[
E_j^{\rm std}+\rho C_j^2\|g_{\rm end}\|^2
\ge\rho\|g_{\rm start}\|^2.
\]

Equation (14) in PROOF_ATTEMPT.md is a complete recursive equality with nonnegative original-row coefficients, a retained right-child residual, and an explicit normal-displacement square. Iterating down the left spine and using the leaf identity proves the displayed bound. No displacement surplus is taken for free.

The leaf version is also valid for every actual leaf 1<h<=sqrt(2), including h=1+a with the same enclosing m. Equations (4)--(6) give the full two-vector PSD remainder. Thus rho=51/100 is a valid actual leaf input.

This is NOT the requested actual all-depth result. If the sharp right-child input is replaced by the same weak history input, the reserve accounting becomes (19); at the exact ratio it maps a common rho to 2rho-rho^2. The new initial-gradient bound alone does not prevent this double charge.

## Concrete counterexample to the suggested charged input

The parent-suggested stronger input

\[
E^{\rm std}+\tfrac12 C_j^2\|q\|^2
\ge(\sqrt2-1)\|X+q\|^2
\]

is false already at H_2, on one explicit static three-dimensional function whose right leaf has constant gradient. It also fails with terminal coefficient 51/100.

Use h=sqrt(2), C=1+h, r=h-1, Y=(C/2)sqrt(2h-1), and any gamma>0. Define

\[
a=(C^2/2,Y,\gamma),\quad
p=(-C/2,Y,\gamma),\quad
q=(1,0,\gamma),
\]
\[
K=\operatorname{conv}\{0,a,p,q\},\qquad
f(x)=\max_{g\in K}\{x\cdot g-\|g\|^2/2\}.
\]

With N=2C gamma+C/(2 gamma), take gradient/normal pairs

\[
\begin{array}{c|c|c}
i&g_i&y_i\\\hline
0&a&(0,hY,N)\\
1&p&(0,0,N-h\gamma)\\
2&q&(r/2,-Y,N-(h+2)\gamma)\\
3&q&(-C/2,-Y,N-2C\gamma).
\end{array}
\]

The points x_i=g_i+y_i obey the exact word (h,2,h). The complete support table is (27), with a particularly simple table at gamma=1/2 in (28). This is an actual function with selected minimizer zero, not an abstract Gram witness.

The exact quantities are

\[
E^{\rm std}=0,\qquad A_{\rm end}=C^3,\qquad
\|q\|^2=1+\gamma^2,\qquad
\|X+q\|^2=C^4(\sqrt2+\gamma^2).
\]

The parent capacity is C_j=C^2. Therefore any uniform charged input

\[
E^{\rm std}+\rho C_j^2\|q\|^2\ge\sigma\|X+q\|^2
\]

must satisfy sigma<=rho/sqrt(2), by letting gamma decrease through positive values. This sharpens the necessary restriction supplied by the earlier R15 gadget. It does not rule out smaller sigma.

At gamma=1/2, keep the SAME K and x_0 and run the ACTUAL inherited word (h_epsilon,2-epsilon,h_epsilon). Section 7.1 gives a uniform comparison for every m>=1536:

\[
E_\epsilon^{\rm std}+\tfrac12 C_\epsilon^2\|q_\epsilon\|^2
-r\|X_\epsilon+q_\epsilon\|^2<-11/8.
\]

Increasing the reserve to 51/100 still leaves the residual below -7/8. This excludes that particular charged coefficient on the actual words, not only at epsilon=0.

The weaker target E_j(49/100)>=0 is not refuted. On the exact gadget it equals (51/100)C^4(1+gamma^2)>0. No growing-depth failure of the precise target was constructed.

## Correction and continuation boundary

An early scratch argument used the wrong sign in z_0-z_1 and claimed affine-right H_2 could not create positive A_end. That claim was explicitly withdrawn to both the parent and normal-geometry branch, and the proof file replaces it with the actual construction above. Do not reuse the earlier message as a premise.

The new endpoint q is a vertex of K, while the R15 endpoint was interior to a segment. Its current normal nevertheless co-supports p and q. The normal-geometry branch checked that a straightforward new capped line still encounters an old-query support restriction. An exposed terminal vertex alone is not a nesting theorem.

The remaining mathematical task is still a complete, dimension-uniform actual history proof through all j<m, with nonnegative original rows and the full remainder, or a genuine growing-depth violating family. Neither the exact reserve theorem nor the new fixed-depth charged-input counterexample supplies that result. No formal-review candidate for the original target is offered.

Full derivations: [PROOF_ATTEMPT.md](PROOF_ATTEMPT.md).
