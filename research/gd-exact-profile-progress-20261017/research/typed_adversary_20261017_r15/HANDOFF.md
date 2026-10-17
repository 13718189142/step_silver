# R15 typed-adversary handoff

**UNVERIFIED. Original all-word minimax target OPEN.**

The two authorized analytical approaches are finished: actual signed/conjugate boundary ports, and a classified obstruction plus a constructive repair. No mathematical programs, numerical arrays, solvers, new models/agents, services, fact/global-memory mutations, or formal submissions were used. The accompanying PROOF_ATTEMPT.md is the complete derivation. The deadline is 2026-10-17 04:20:00 UTC; this handoff does not authorize renewal.

## Main salvage: an actual cross-block repair with an exact price

Suppose finite prototype data satisfy gradient-descent updates, all star rows for the same selected minimizer zero, and all rows within the left and right blocks. They may violate cross-block rows. At a root \(H=h_r>1\) which is a strict prefix maximum, put

\[
p_i=\prod_{t<i}(1-h_t/H)>0,\qquad
\Delta_i=\max_{j>r}\max(0,-R^0_{ij},-R^0_{ji}),
\]

\[
M=\max_{i\le r}\frac{2H^2\Delta_i}{(H-1)p_i^2}.
\]

Append the finite scalar quadratic data with curvature \(1/H\), initial coordinate \(\sqrt M\), and the original physical word. The coordinate is annihilated at the root, so its terminal position, gradient, and objective are zero. Every cross row in either direction receives \((H-1)p_i^2M/(2H^2)\), enough to repair the full defect. All internal and star rows remain nonnegative.

**This adds finite data to a possibly globally infeasible prototype, then applies full smooth-convex interpolation. It is not an assertion that a global base function exists to which a separable quadratic can simply be added.** The resulting single static function may be coupled.

The full original radius and terminal objective give exactly

\[
\mathcal W_n(h)\ge
\frac{2f_n^0}{\|x_0^0\|^2+M}.
\]

The start is nonzero when \(f_n^0>0\). A prototype's terminal-core port is preserved. Its initial and root ports are changed and must be carried forward with their actual coordinates.

If prefix steps obey \(h_t\le qH\), \(q<1\), and \(P=\sum_{t<r}h_t\), then

\[
p_i\ge \exp[-S_i/(H(1-q))],\qquad
M\le\frac{2H^2}{H-1}
\exp[2P/(H(1-q))]\max_i\Delta_i.
\]

Thus in a regime with \(P/H\) bounded, \(q\) bounded away from one, and \(H=O(B_n)\), normalized defects \(o(2f_n^0)\) make the repair asymptotically cheap. Defects of order \(2f_n^0/H\) cost only order \(2f_n^0\). No such defect estimate or uniform root conditioning has been proved for arbitrary high-mass words.

This is the usable new construction. Read PROOF_ATTEMPT.md §4.1–§4.4 first.

## A height-for-radius refinement, with its limitation

The same non-star repairs are obtained from

\[
z_i=(p_i-\theta)\sqrt M,\quad
g_i^{\rm aux}=p_i\sqrt M/H,\quad
f_i^{\rm aux}=p_i^2M/(2H),
\]

where \(p_i=0\) after the root. The combined star rows are valid iff

\[
0\le\theta\le
\min_{i\le r}\left[
\frac{H u_i^0}{Mp_i}+\frac{1-1/H}{2}p_i
\right].
\]

For \(0\le\theta\le1\), the initial cost becomes \((1-\theta)^2M\) and terminal objective remains unchanged. The original minimizer remains zero, but the terminal fresh position is \(-\theta\sqrt M\); an exact terminal-core port is lost. This is usable directly for a final objective join, not as an unchanged recursive core port.

Crucially, the old diagonal root has \(u_r^0=0\), which forces \(\theta<(1/2)\), leaving more than \(M/4\) of the initial cost. Positive heights at earlier times alone do not make the repair free. A \(\theta\) near one needs a genuinely non-diagonal root with the displayed height reserve and new terminal-displacement bookkeeping. See §4.5.

## Two structural exclusions that the revised package must respect

**Additive cap ages have a finite budget.** For a genuine trace ending at \(x_N=g_N=q\ne0\), the exact operation

\[
x_i\mapsto x_i+\tau q,\qquad
f_i\mapsto f_i+\tau\|q\|^2
\]

preserves all physical and non-star rows. It preserves the same minimizer iff

\[
\tau\le\min_{\langle g_i,q\rangle<\|q\|^2}
\frac{u_i}{\|q\|^2-\langle g_i,q\rangle}.
\]

Writing \(E=\|x_0\|^2/\|q\|^2\) and \(A=\langle x_0,q\rangle/\|q\|^2\), its exact objective payoff is

\[
\frac{1+2\tau}{E+2A\tau+\tau^2}.
\]

For projection traces with all \(u_i=0\), any positive cap age forces \(\|x_0\|\ge(1+\sum h_i)\|q\|\). An accelerated gradient trace in this class consequently has no positive additive-cap range. The absent resource is actual conjugate height, not another scalar gradient bound. See §2.1–§2.2.

**Unchanged-child, diagonal-root correction coordinates cannot do the advertised repair.** If an independently star-feasible auxiliary has all internal child residuals zero and both root ports diagonal, its left block must be an orthogonal cap plus quadratic trace,

\[
g_i=c+p_i^Ld,\quad y_i=P_i c,\quad
\ell_i=P_i\|c\|^2,\quad u_i=0,\quad c\perp d.
\]

Its right block is forced quadratic. Every left-to-right cross residual is zero; only the reverse direction can receive

\[
(1+a p_j^R)P_i\|c\|^2.
\]

The original initial cost is \((1+P)^2\|c\|^2+\|d\|^2\). With a nonannihilating right word, a zero terminal gradient forces all cross repair to vanish. The draft's arbitrary directed terminal-dead coordinates therefore fail structurally, not just by an uncounted norm. See §3.1–§3.3.

## Actual signed-port gluing and what remains

For projection children, an exact static crossing is available by setting \(K=\operatorname{conv}(K_L\cup K_R)\), with left terminal \(q\) and right initial \(-a q\). Every original child query survives iff all mutual normal guards hold:

\[
\langle y_i^L,g_j^R\rangle\le\ell_i^L,\qquad
\langle y_j^R,g_i^L\rangle\le\ell_j^R.
\]

Under those guards the payoff is exactly \((a^2/D_L^2)w_R\). A scalar denominator alone does not establish them. Exact diagonal points also fix their entire convex hull as a quadratic region, so a nested Huber child cannot be inserted into an already saturated inner interval. See §2.3–§2.4.

The remaining new mechanism is now specific: choose actual high-mass-word children and embeddings with controlled cross defects and cap-height budgets, then show the *globally transported* total original-radius repair cost is \(o(B_n\,2f_n)\). Alternatively, a non-diagonal root must supply sufficient real height reserves for §4.5 while retaining all original-minimizer and terminal-displacement information. The scalar \(\Omega/G\) recurrences do not establish either property.

No general all-word small-defect theorem, uniform product conditioning, or recursive cost summation is supplied. Neither the affirmative asymptotic theorem nor a negative resolution follows. The low-total-mass Huber region remains the accepted complementary asset.

## Audit and recovery

The derivation was self-audited analytically, not independently verified. Particular checks included both directed rows, all star rows, zero steps, root ties, the nonzero start, original-radius accounting, the singular cap-payoff candidate, and the distinction between data addition and a sum of globally defined functions.

For later selective review, the quadratic-data repair in §4.1–§4.3 is a self-contained candidate lemma. Do not submit the original minimax theorem on the basis of this file. Do not restart an old worker or invoke a further model from this handoff.
