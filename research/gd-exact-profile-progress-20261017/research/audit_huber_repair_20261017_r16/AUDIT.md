# Independent audit of the R16 capped-coordinate data repair

**Verdict: MANUALLY ACCEPTED within the finite-data scope stated below.** All substantive formulas and implications in the inspected object are valid. Two qualitative sentences need the harmless qualifier `b > 0`, and the asymptotic paragraph should define its comparison scale `B_n > 0`. These edits do not change the finite repair or its cost. This is a manual finished-object audit, not verifier acceptance and not a resolution of the original exact-profile minimax problem.

## 1. Object, authority, and accepted scope

The inspected source is `research/resume_20261017_r16/HUBER_DATA_REPAIR.md`, SHA256 `f3ec09994edffe985742f80ae8603bc97da5864165689c07dfbd89ded770422b`. The hash matched the parent dispatch. Governing scope was checked against the current `OPERATOR.md`, R16 `WAVE.md`, the original `PROBLEM.md`, and the R15 `typed_adversary_20261017_r15/PROOF_ATTEMPT.md`. The latter was used for the interpolation convention and the meaning of a terminal-core port, not as an authority that establishes the new repair.

This audit used exact manual derivations. No mathematical program, numerical array, solver, further agent/model, service, truth-store operation, formal submission, or publication was used. Only this audit and its handoff are written. The wave deadline is 2026-10-17 05:05:00 UTC.

The accepted statement has the following hypotheses. Let `n >= 1`, let all steps `h_t` be finite and nonnegative, and select an index `0 <= r < n` with `H = h_r > 1`. Prototype vectors belong to a finite-dimensional Euclidean space. The data satisfy the physical GD recursion, both star rows for the fixed datum `(0,0,0)`, and every directed interpolation row within each of the two blocks `L = {0,...,r}` and `R = {r+1,...,n}`. Their terminal value is positive. Cross-block rows alone are permitted to fail. No bound, ordering, or distinctness condition on other steps is used.

For any datum set, write

\[
y_i=x_i-g_i,\qquad
\ell_i=f_i-\tfrac12\|g_i\|^2,\qquad
u_i=\langle g_i,y_i\rangle-\ell_i.
\]

The source's orientation convention is consistent because

\[
R_{ij}=\ell_j+u_i-\langle g_i,y_j\rangle
=f_j-f_i-\langle g_i,x_j-x_i\rangle
-\tfrac12\|g_j-g_i\|^2.
\tag{A1}
\]

Thus its two star rows are exactly `R_{star,i} = ell_i` and `R_{i,star} = u_i`. No orientation is being silently reversed.

## 2. The auxiliary function and the complete physical trajectory

For `b > 0`, the derivative of the proposed one-sided Huber function is

\[
\varphi_b'(z)=\min\{b,\max\{0,z\}\}.
\]

It is continuous, nondecreasing, and 1-Lipschitz. Consequently the displayed primitive is finite, convex, differentiable, and 1-smooth. Its minimum value is zero, attained on the whole half-line `z <= 0`. For `b = 0`, the stipulated function is identically zero and has the same regularity bound.

Set

\[
P=\sum_{t<r}h_t,\qquad
P_i=\sum_{i\le t<r}h_t\quad(0\le i\le r).
\]

Choose `1 < eta < H` and start at `z_0=(P+eta)b`. For `b > 0`, induction gives

\[
z_i=(P_i+\eta)b>b,\qquad \varphi_b'(z_i)=b
\quad(0\le i\le r).
\tag{A2}
\]

The induction step is decisive for arbitrary prefixes:

\[
z_i-h_i b=(P_i-h_i+\eta)b=(P_{i+1}+\eta)b>b
\quad(i<r).
\tag{A3}
\]

Here `P_i >= h_i` follows from nonnegative steps. Even a prefix step equal to or larger than `H` cannot exit the capped region, because the initial position has already paid for the entire prefix mass. Zero prefix steps simply repeat the same datum. No inverse product or strict-prefix-maximum property appears.

At the root, `P_r=0`, so

\[
z_r=\eta b,\qquad z_{r+1}=z_r-Hb=(\eta-H)b<0.
\tag{A4}
\]

The gradient there is zero. Therefore every later physical update leaves this coordinate exactly at `(eta-H)b`, regardless of the sizes of later steps, and every later auxiliary function value and gradient is zero. For `b=0`, all positions, gradients, and values are zero throughout, and (A2)--(A4) hold with their strict inequalities replaced by equalities where appropriate. The source already separates the strict assertion at the root from this degenerate case.

## 3. Every row and both directed corrections

For the unshifted auxiliary data, exact substitution gives

| Block | Position `z` | Gradient | Value | `y` | `ell` | `u` |
| --- | --- | --- | --- | --- | --- | --- |
| `i in L` | `(P_i+eta)b` | `b` | `(P_i+eta-1/2)b^2` | `(P_i+eta-1)b` | `(P_i+eta-1)b^2` | `0` |
| `j in R` | `(eta-H)b` | `0` | `0` | `(eta-H)b` | `0` | `0` |

Both star resources are nonnegative. Within `L`, the same gradient `b` cancels the second point's `ell`; within `R`, all terms in the residual are zero. Thus every directed within-block auxiliary residual is exactly zero, including rows between nonadjacent times.

For `i in L` and `j in R`, the two distinct orientations are

\[
R_{ij}^{\rm aux}=0+0-b(\eta-H)b=(H-\eta)b^2,
\tag{A5}
\]

\[
R_{ji}^{\rm aux}=(P_i+\eta-1)b^2+0-0
=(P_i+\eta-1)b^2.
\tag{A6}
\]

These are the source's formulas, with the correct prefix index on the second denominator. Both coefficients are strictly positive before multiplication by `b^2`: `H-eta > 0` and `P_i+eta-1 >= eta-1 > 0`.

With the source's finite maxima `A` and `B_i`, the prescribed value

\[
b^2=\max\left\{\frac{A}{H-\eta},
\max_{i\le r}\frac{B_i}{P_i+\eta-1}\right\}
\tag{A7}
\]

is finite and nonnegative. Equations (A5)--(A7) separately dominate every negative left-to-right row and every negative right-to-left row. In particular, repairing one orientation does not rely on symmetry of the prototype residuals. If `Delta=0`, all the numerators in (A7) vanish and `b=0`; the prototype is already fully feasible. Conversely, this selected `b` can vanish only when `Delta=0`.

Append the coordinate orthogonally:

\[
X_i=(x_i^0,z_i),\qquad G_i=(g_i^0,g_i^{\rm aux}),\qquad
F_i=f_i^0+f_i^{\rm aux}.
\tag{A8}
\]

The physical recursions hold componentwise. Orthogonality makes `ell`, `u`, and every residual exactly additive. Hence the complete combined set satisfies all star rows, all within-block rows, and both orientations of every cross-block row. This list exhausts every ordered pair in the finite data set; no special root or terminal row is omitted.

## 4. Explicit static interpolation, including a globally infeasible prototype

The following construction verifies the needed interpolation statement without assuming that a prototype function already exists. All quantities in this subsection refer to the combined data (A8). Include the star index with `X_star=G_star=Y_star=0` and `F_star=ell_star=u_star=0`, and define on the same Euclidean space

\[
a(v)=\max_{i\in\{\star,0,\ldots,n\}}
\{\langle Y_i,v\rangle-\ell_i\},\qquad
q(v)=\tfrac12\|v\|^2+a(v),\qquad F=q^*.
\tag{A9}
\]

The finite maximum is a finite continuous convex function. The star affine term is zero, so `a >= 0`; the star rows `ell_i >= 0` also give `a(0)=0`. Thus `q` is proper, closed, 1-strongly convex, and bounded below by `||v||^2/2`.

For every queried index `i`, the complete rows imply

\[
\langle Y_j,G_i\rangle-\ell_j\le u_i
\quad\text{for every }j.
\]

Equality holds at `j=i`. Hence `a(G_i)=u_i`, its `i`th affine piece is active, and `Y_i` is a subgradient of `a` at `G_i`. It follows that `X_i=G_i+Y_i` is a subgradient of `q` there.

For every `X`, the maximum defining `q^*(X)` is attained at a unique vector, because `q(v)-<X,v>` is strongly convex and coercive. If its maximizing vectors at `X` and `X'` are `G` and `G'`, strong monotonicity gives

\[
\|G-G'\|^2\le\langle X-X',G-G'\rangle,
\]

so the maximizer map is 1-Lipschitz. The two defining maximum inequalities bound the increment of `F` between the corresponding affine increments; the Lipschitz estimate then shows that `F` is differentiable with gradient equal to this maximizer. Therefore `F` is finite, convex, and 1-smooth on the entire ambient space. At each query it has gradient `G_i` and value

\[
F(X_i)=\langle X_i,G_i\rangle-q(G_i)
=\tfrac12\|G_i\|^2+\ell_i=F_i.
\tag{A10}
\]

Since `q(0)=0` and `q(v)>=||v||^2/2`, one has `F(0)=0` and `F(X)>=0` everywhere. Thus the same selected origin is an actual global minimizer of the constructed static function. The recursion and (A10) make the combined data its actual entire GD trajectory from `X_0`.

This interpolation occurs in dimension `d+1`, where `d` is the prototype dimension. The conjugate construction does not add a lifting coordinate. The global function can differ from any candidate one might have imagined for the prototype, but the lemma only promises a function interpolating the repaired data. It makes no false separable-sum assertion for an infeasible prototype and does not replace the selected minimizer.

## 5. Exact original radius, objective normalization, and nonzero start

The unshifted coordinate has final value and gradient zero. Therefore `F_n=f_n^0>0`, while

\[
\|X_0\|^2=\|x_0^0\|^2+(P+\eta)^2b^2.
\tag{A11}
\]

The selected minimizer is the original origin, so (A11) is the actual starting squared distance used by the objective definition. It is not a distance from a restarted root and not a distance to a newly selected closer minimizer. Its denominator is positive: if the actual start were the selected minimizer, zero gradient would make GD stationary and its positive terminal value impossible. In fact the prototype's star rows and physical recursion already exclude a zero prototype start with positive terminal value.

The definition with smoothness one consequently gives exactly

\[
\mathcal W_n(h)\ge
\frac{2f_n^0}{\|x_0^0\|^2+(P+\eta)^2b^2}.
\tag{A12}
\]

There is no missing factor of two. For general prescribed smoothness `L>0`, replacing this constructed function by `L F` gives the stated physical update with `h_t/L` and leaves the normalized ratio unchanged.

When `b>0`, the unshifted terminal auxiliary position is `(eta-H)b != 0` even though its gradient and value vanish. Accordingly, an existing prototype identity `x_n^0=g_n^0` does not remain the full identity `X_n=G_n`. The source correctly records this lost terminal-core port.

## 6. Translated terminal-core variant and conjugate heights

Let `c=(H-eta)b >= 0` and replace every auxiliary query position by `z_i'=z_i+c`, keeping the auxiliary values and gradients. These are actual data of

\[
\widetilde\varphi_b(z)=\varphi_b(z-c).
\]

For `b>0`, its minimum set is `(-infinity,c]`, which contains the unchanged selected origin. For `b=0` it is again the zero function. The star has not been translated: it remains the datum `(0,0,0)`.

On `L`, the translated data are

\[
z_i'=(P_i+H)b,\quad
y_i'=(P_i+H-1)b,\quad
\ell_i'=(P_i+\eta-1)b^2,\quad
u_i'=(H-\eta)b^2.
\tag{A13}
\]

On `R`, position, gradient, value, and both star resources are all zero. Every non-star residual is unchanged: a common position translation sends `y_j` to `y_j+c` and `u_i` to `u_i+g_i c`, and those two changes cancel in `R_ij`. The recomputed star quantities in (A13) are nonnegative, so this invariance is not incorrectly applied to a moved star.

The physical root query has position `Hb` and gradient `b`, and the root step sends it to zero. Subsequent auxiliary data stay zero. Thus an existing prototype terminal-core port is preserved in full. The exact added starting squared distance is

\[
M_{\rm core}=(P+H)^2b^2,
\tag{A14}
\]

with the same choice (A7). The larger initial distance is explicitly charged. The initial and root ports really have changed. At the root, the auxiliary normal is `(H-1)b`; before translation it was `(eta-1)b`. For a nontrivial repair these normals are nonzero, so the earlier obstruction requiring diagonal root ports does not apply.

The translated prefix heights are strictly positive when `b>0` and vanish when `b=0`. No height is borrowed from an unproved prototype resource, and no change of selected minimizer is needed to make the shifted function admissible.

## 7. Projection realization when the prototype heights vanish

Suppose `u_i^0=0` at every query and use the unshifted correction. Then all combined heights are zero. Let

\[
K=\operatorname{conv}\{0,G_0,\ldots,G_n\}.
\]

For every fixed `j`, all verified rows give

\[
\langle Y_j,G_i\rangle\le\ell_j
=\langle Y_j,G_j\rangle,
\]

and the star row gives the same inequality for the zero generator. Therefore `Y_j` is a supporting normal to `K` at `G_j`. Since `X_j=G_j+Y_j`, the Euclidean projection characterization yields `P_K(X_j)=G_j`.

The static projection model

\[
F_K(X)=\max_{v\in K}\{\langle X,v\rangle-\tfrac12\|v\|^2\}
\]

has gradient `P_K`, is convex and 1-smooth, and has minimum value zero at the origin. At every query its value is `||G_j||^2/2+ell_j=F_j`. Thus the stated hull realizes both gradients and values, in the same `d+1` dimensions. This claim needs every directed row and the zero generator; both are present. The shifted variant generally has nonzero heights and is correctly handled by full interpolation instead.

## 8. Uniform finite cost and the conditional asymptotic implication

With `eta=(H+1)/2`, both relevant denominators in (A7) are at least `(H-1)/2`. Hence

\[
b^2\le\frac{2\Delta}{H-1},\qquad
M_{\rm flat}\le\frac{(2P+H+1)^2}{2(H-1)}\Delta,
\qquad
M_{\rm core}\le\frac{2(P+H)^2}{H-1}\Delta.
\tag{A15}
\]

All constants are exact. The dependence on prefix mass is quadratic; there is no singularity at a prefix step tied with `H`. There remains the displayed singularity as the chosen root `H` approaches one. The finite lemma allows `1<H<2`, but the subsequent uniform implication deliberately assumes `H>=2`.

To make that implication fully explicit, define a positive comparison scale `B_n` and set `E_n=2f_n^0>0`. Suppose, uniformly over the family of words to which the construction is to be applied,

\[
H\ge2,\qquad H/B_n\le C,\qquad P/H\le K,
\qquad \Delta/E_n\le\delta_n\longrightarrow0,
\tag{A16}
\]

where `C,K` are finite constants. For either variant, (A15) yields

\[
\frac{M}{B_nE_n}
\le\frac{2H^2}{(H-1)B_n}(1+P/H)^2\frac{\Delta}{E_n}
\le4C(K+1)^2\delta_n\longrightarrow0.
\tag{A17}
\]

If, also uniformly, `||x_0^0||^2 <= (1+epsilon_n) B_n E_n` with `epsilon_n -> 0`, then

\[
\mathcal W_n(h)\ge
\frac{1}{B_n[1+\epsilon_n+4C(K+1)^2\delta_n]}.
\tag{A18}
\]

This checks the claimed conditional cost implication and its uniformity. In the intended benchmark comparison one should define

\[
B_n=(U_n^{\mathrm{ZJ}})^{-1}=2S_\bullet(n)+1.
\]

The cost estimate itself is valid for any positive comparison scale. Neither (A16) nor the near-benchmark prototype existence is proved by the finite repair. Words having no selected root above one are outside its stated hypotheses. A collection of separate nodewise estimates also does not establish a bound on the single original starting radius of a recursive construction; all transported coordinate costs still need a global estimate. These are the scope limitations already stated in the inspected object, not gaps in the finite lemma.

## 9. Correction ledger and final disposition

| Source location | Issue | Exact correction | Consequence |
| --- | --- | --- | --- |
| Section 3: "creates positive conjugate heights on every prefix query" | Degenerate-case wording: the displayed height is zero when `b=0`. | Insert "when `b>0`"; otherwise say "nonnegative conjugate heights". | No formula or conclusion changes. |
| Section 4: "the root is explicitly non-diagonal" | The computed normal is zero when `b=0`. | Insert "for a nontrivial repair (`b>0`)". | The no-contradiction explanation is valid; when `b=0` there is no correction to explain. |
| Section 4: first use of `B_n` | The positive comparison scale is not defined inside this otherwise self-contained object. | Define `B_n>0`; for the intended benchmark set `B_n=2S_bullet(n)+1`. | The conditional asymptotic calculation is unchanged. |

No counterexample or material error was found. The audit accepts the one-coordinate finite repair, both exact radius costs, the translated terminal-core version, the special projection realization, and the stated conditional asymptotic implication. The original all-word small-defect/prototype theorem and globally transported recursive cost bound remain unproved. The source should retain its draft/manual-audit evidence label until any separately authorized formal verification occurs.
