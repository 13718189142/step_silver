# R15 typed cap/crossing reconstruction

**Status: UNVERIFIED analytical draft. The original minimax target remains OPEN.**

This invocation used two substantive approaches: (I) actual signed terminal-core ports and static conjugate/projection gluing; (II) an exact obstruction to residual-preserving repairs, followed by an explicit quadratic repair with its full original-radius cost. No mathematical programs, numerical arrays, solvers, further agents, services, fact/global-memory mutations, or formal submissions were used. Only this file and `HANDOFF.md` are written. Hard deadline: 2026-10-17 04:20:00 UTC.

Read sources: `OPERATOR.md`; the project `PROBLEM.md`; the supplied `Pasted text.txt`; public handoff chapters 04 and 05; and the statements/relevant proofs of accepted facts `1e0bf3f41457d8e4` and `b98bb807d514e80d`. The supplied one-step and two-step defects were taken as already established, not re-proved. The accepted projection-universality fact is equality of suprema; it does not promise preservation of the boundary ports below.

## 1. Normalization and the actual interpolation object

Set \(L=1\), select the original minimizer \(x_\star=0\), and normalize its value to zero. For every physical query, write

\[
g_i=\nabla f(x_i),\quad y_i=x_i-g_i,\quad
\ell_i=f_i-\tfrac12\|g_i\|^2,\quad
u_i=\langle g_i,y_i\rangle-\ell_i.
\]

The finite interpolation rows, including the star, are

\[
R_{ij}=\ell_j+u_i-\langle g_i,y_j\rangle\ge0,
\qquad \ell_i\ge0,\quad u_i\ge0.
\tag{1.1}
\]

The physical update is

\[
y_{i+1}=y_i+(1-h_i)g_i-g_{i+1}.
\tag{1.2}
\]

A **terminal-core port** has \(x_N=g_N=q\ne0\), hence \(y_N=\ell_N=u_N=0\). The initial point need not be parallel to \(q\), and its signed projection cannot be discarded.

Every new finite-data construction below is interpreted through the full smooth-convex interpolation theorem. In particular, once all rows hold, one may use

\[
\Psi(v)=\max_{i\in\{\star,0,\ldots,N\}}
\left\{\langle g_i,x_i\rangle-f_i+
\langle x_i,v-g_i\rangle+\tfrac12\|v-g_i\|^2\right\},
\quad f=\Psi^*.
\tag{1.3}
\]

This gives one finite-valued convex differentiable 1-smooth function, with the same selected star datum and all physical queries. It is not necessary that an intermediate, uncorrected prototype already be one global function.

## 2. Approach I: the cap age is a bounded, word-dependent port

### 2.1 Exact additive-cap extension

Start with any admissible trace ending at the terminal-core port \(q\). For a proposed age \(\tau\ge0\), set

\[
x_i^{(\tau)}=x_i+\tau q,\qquad
g_i^{(\tau)}=g_i,\qquad
f_i^{(\tau)}=f_i+\tau\|q\|^2.
\tag{2.1}
\]

Keep the original star at zero. The physical updates and every non-star row are exactly unchanged. The star resources become

\[
\ell_i^{(\tau)}=\ell_i+\tau\|q\|^2,\qquad
u_i^{(\tau)}=u_i+\tau\bigl(\langle g_i,q\rangle-\|q\|^2\bigr).
\tag{2.2}
\]

Consequently (2.1) is feasible **if and only if**

\[
0\le\tau\le\tau_{\max}:=
\min_{i:\langle g_i,q\rangle<\|q\|^2}
\frac{u_i}{\|q\|^2-\langle g_i,q\rangle},
\tag{2.3}
\]

where the minimum of the empty set is infinity. This is an actual sufficient construction as well as a necessary condition for this specified extension. It is not an assertion that every possible cap construction must be a translation.

Normalize the port by

\[
E=\frac{\|x_0\|^2}{\|q\|^2},\qquad
A=\frac{\langle x_0,q\rangle}{\|q\|^2}.
\]

Its exact objective payoff after extension is

\[
\frac{2f_N^{(\tau)}}{\|x_0^{(\tau)}\|^2}
=\frac{1+2\tau}{E+2A\tau+\tau^2}.
\tag{2.4}
\]

The full initial norm, including components perpendicular to \(q\), is present in \(E\). Wherever the denominator is positive, the derivative of (2.4) has the sign of \(E-A-\tau-\tau^2\). If \(E>A\), its positive candidate is

\[
\tau_*^2+\tau_*=E-A,
\qquad
\tau_*=\frac{\sqrt{1+4(E-A)}-1}{2},
\tag{2.5}
\]

When this candidate is feasible, its payoff is \(1/(A+\tau_*)\). The actual optimum is at the appropriate endpoint or this feasible point within \([0,\tau_{\max}]\); when \(E\le A\), the payoff is nonincreasing for \(\tau\ge0\). If \(E=A^2\) and \(A<0\), the formal candidate is the singular point \(\tau_*=-A\), not a feasible stationary point: feasibility with positive terminal value excludes a zero initial norm.

For the constant-gradient trace, \(S=\sum h_i\), \(x_0=(1+S)q\), and \(u_i=0\). Then \(E=(1+S)^2\), \(A=1+S\), \(\tau_{\max}=\infty\), and \(\tau_*=S\), recovering exactly \(1/(1+2S)\).

### 2.2 An obstruction to a free additive cap port

For a trace with \(u_i=0\) at every query, any positive age in (2.1) requires

\[
\langle g_i,q\rangle\ge\|q\|^2\quad\text{for every }i.
\]

Since \(x_0=q+\sum_i h_i g_i\), this gives

\[
\langle x_0,q\rangle\ge(1+S)\|q\|^2,
\qquad \|x_0\|\ge(1+S)\|q\|.
\tag{2.6}
\]

Thus an accelerated terminal-core trace with \(u_i=0\) and initial/terminal-gradient denominator strictly below \(1+S\) has **zero** additive-cap range under (2.1). In the projection model \(f=F_K\), with the natural selected minimizer zero, all \(u_i=0\). A separate scalar gradient guarantee cannot supply its accelerated trace with a positive cap age.

For general positive heights, feasibility also forces the weighted budget

\[
\sum_i h_i u_i\ge
\tau\left[(1+S)\|q\|^2-\langle x_0,q\rangle\right].
\tag{2.7}
\]

This follows by summing (2.2), and is useful when the bracket is positive. It does not itself give a bound on the initial distance.

The restriction \(u_i=0\) is essential. Translating a projection model to a different selected minimizer generally introduces nonzero affine conjugate heights. The accepted equality-of-suprema representation cannot be used to erase those heights while claiming to preserve the original radius or an exact terminal-core port.

### 2.3 A genuine static crossing join, with all its guards

For a compact convex set \(K\ni0\), put

\[
F_K(x)=\max_{g\in K}\{\langle x,g\rangle-\tfrac12\|g\|^2\}.
\]

Then \(\nabla F_K=P_K\), zero is an attained minimizer, and a projection trace has \(u_i=0\), \(\ell_i=\langle g_i,y_i\rangle\). Each child body may be replaced by the convex hull of zero and its queried gradients.

Take a left child ending at \(x_k^L=g_k^L=q\ne0\). At a root \(h=1+a>1\), rotate and scale an actual right child so that its initial point is \(x_0^R=-a q\). Embed the remaining right directions orthogonally to the remaining left directions. Define

\[
K=\operatorname{conv}(K_L\cup K_R).
\tag{2.8}
\]

Both entire child histories survive in this one static function exactly when their normal inequalities against the other body's generators hold:

\[
\langle y_i^L,g_j^R\rangle\le\ell_i^L,
\qquad
\langle y_j^R,g_i^L\rangle\le\ell_j^R
\quad\text{for every }i,j.
\tag{2.9}
\]

Internal rows follow from each child; (2.9) is precisely every cross-block row. The root physical update holds because \(q-(1+a)q=-a q\). The selected minimizer remains zero. No extra initial coordinate is introduced.

If \(D_L=\|x_0^L\|/\|q\|\), and the right child's objective score is \(w_R\), this guarded join has exactly

\[
w_{\rm parent}=\frac{a^2}{D_L^2}w_R.
\tag{2.10}
\]

If the right child also ends at a core port and has gradient denominator \(D_R\), the parent's gradient denominator is \(D_LD_R/a\). These are the draft's crossing algebra with the indispensable, actual guards (2.9) restored. Neither \(D_L\le C_k\) nor \(D_R\le C_m\) establishes (2.9).

In one dimension, a fixed asymmetric Huber function with \(g(x)=\operatorname{clip}(x,-b,a)\) automatically satisfies every row: \(u=0\), \(\ell=gy\), and \(R_{ij}=(g_j-g_i)y_j\ge0\). Using \(\xi\) for the next physical position, its backward branches are \(x=\xi+ha\), \(x=\xi/(1-h)\) when \(h\ne1\), and \(x=\xi-hb\), subject respectively to the positive-cap, quadratic-core, and negative-cap interval guards. At \(h=1\), the core branch maps the whole core to zero instead of permitting division by zero. The signs and visited ranges are part of the port, not replaceable by its terminal ratio.

### 2.4 Why an already saturated inner interval is not available for a new child

For any admissible function with selected minimizer zero, the set

\[
Q=\{x:f(x)=\tfrac12\|x\|^2\}
=\{x:\nabla f(x)=x\}
\tag{2.11}
\]

is convex. Indeed \(\tfrac12\|x\|^2-f(x)\) is convex and nonnegative, and its zero set is \(Q\). Equivalently this follows from the zero set of the nonnegative convex conjugate remainder \(f^*(g)-\|g\|^2/2\).

If a crossing preserves both diagonal points \(q\) and \(-a q\), the entire segment \([-a q,q]\) is therefore fixed quadratic. Let \(p_j^R=\prod_{t<j}(1-h_t^R)\). As long as

\[
-a p_j^R q\in[-a q,q]
\quad\Longleftrightarrow\quad -1/a\le p_j^R\le1,
\tag{2.12}
\]

the right child is forced to follow this quadratic trajectory. A different geometry can first act only after an actual exit from the saturated segment. Inserting a nonquadratic child inside that segment would change already fixed data. This identifies the exact visited-range obstruction to an unqualified nested-Huber argument; it does not rule out exits or other coupled functions.

## 3. Approach II: classify the proposed zero-slack repair before charging it

### 3.1 A local identity

For every pair of adjacent physical data, write \(d_i=y_{i+1}-y_i\). Direct substitution in (1.1)--(1.2) yields

\[
\|d_i\|^2+h_i(\ell_{i+1}-\ell_i)
=(h_i-1)R_{i,i+1}-R_{i+1,i}.
\tag{3.1}
\]

In particular, from a diagonal datum, if both adjacent residuals are zero, then

\[
\|y_{i+1}\|^2+h_i\ell_{i+1}=0.
\]

Star feasibility and \(h_i\ge0\) force the next datum diagonal, and \(g_{i+1}=(1-h_i)g_i\). The zero-step case also follows directly from the same interpolation rows.

### 3.2 Complete classification of a residual-preserving two-block repair

Consider an independently star-feasible auxiliary trace with the following exact properties:

1. every internal residual in each child block is zero, so adding it leaves those child residuals unchanged;
2. its two root ports are diagonal;
3. the root is \(1+a>1\).

Let the left word have total mass \(P\), remaining masses \(P_i=\sum_{t=i}^{k-1}h_t^L\), and products \(p_i^L=\prod_{t<i}(1-h_t^L)\). Then there are orthogonal vectors \(c,d\) such that

\[
g_i^L=c+p_i^L d,\qquad y_i^L=P_i c,\qquad
\ell_i^L=P_i\|c\|^2,\qquad u_i^L=0.
\tag{3.2}
\]

The left terminal vector is \(q=c+p_k^L d\). Every right datum is forced to be

\[
g_j^R=x_j^R=-a p_j^R q,\qquad
y_j^R=\ell_j^R=u_j^R=0.
\tag{3.3}
\]

To prove (3.2), the rows to the left terminal diagonal datum give \(u_i^L=0\) and \(\ell_i^L=\langle q,y_i^L\rangle\). All left rows then give \(\langle g_j^L-q,y_i^L\rangle=0\). For \(G=\operatorname{span}\{g_j^L-q\}\), all \(y_i^L\) lie in \(G^\perp\). Project (1.2) onto \(G\) and \(G^\perp\), and use the zero terminal \(y\), obtaining the quadratic and cap components in (3.2). Formula (3.3) follows by (3.1).

Every cross row and the original initial norm can now be read exactly:

\[
R_{L_i,R_j}=0,
\qquad
R_{R_j,L_i}=(1+a p_j^R)P_i\|c\|^2,
\tag{3.4}
\]

\[
\|x_0^{\rm aux}\|^2=(1+P)^2\|c\|^2+\|d\|^2.
\tag{3.5}
\]

This has three consequences.

* Such a repair cannot correct a negative left-to-right row at all, regardless of its dimension or initial norm.
* When the left block has positive mass, a nonzero cap component is feasible only if \(1+a p_j^R\ge0\) at every right time. A large root alone does not establish this guard.
* If the right terminal product is nonzero, requiring zero terminal gradient forces \(q=0\), hence \(c=0\). All its cross residuals then vanish. If the entire word has no unit step, the whole auxiliary trace is zero. Unit-step annihilation in the left block can leave a nonzero initial quadratic component, but it still contributes no cross repair.

Thus the draft's exact unchanged-child/diagonal-root architecture cannot supply arbitrary directed terminal-dead correction coordinates. This is stronger than simply observing an omitted norm cost. It concerns this architecture; auxiliary data that change internal residuals or root ports are not excluded.

### 3.3 A quantitative departure from this architecture

For a block starting at a diagonal datum, discard zero steps and sum (3.1) divided by \(h_i>0\). Define

\[
\mathcal A=\sum_i(1-1/h_i)_+R_{i,i+1}.
\]

Then every prefix satisfies

\[
\ell_j+\sum_{i<j}\frac{\|y_{i+1}-y_i\|^2}{h_i}\le\mathcal A.
\tag{3.6}
\]

Let \(p_j=\prod_{i<j}(1-h_i)\) and

\[
K_j=\sum_{r<j}h_r\left[\prod_{r<s<j}(1-h_s)\right]^2.
\]

Solving the forced gradient recurrence and applying weighted Cauchy--Schwarz gives

\[
\|g_j-p_j g_0\|^2\le K_j\mathcal A.
\tag{3.7}
\]

When \(K_j=0\), the deviation is zero. In particular, a terminal-dead nonquadratic repair with \(p_Ng_0\ne0\) must introduce a positive internal-row budget at least \(p_N^2\|g_0\|^2/K_N\). These estimates expose the actual word dependence; they are not a uniform original-radius estimate.

## 4. A real quadratic annihilation repair, including every row and the full radius

This is the constructive salvage. It deliberately changes internal rows and the full root port.

### 4.1 Hypotheses on a prototype

Fix a physical word \(h_0,\ldots,h_{n-1}\). Select a root \(r\) with

\[
H=h_r>1,\qquad h_t<H\quad(0\le t<r).
\tag{4.1}
\]

If a word has a step above one, its earliest global maximum supplies such a root. Let \((x_i^0,g_i^0,f_i^0)\) be finite **prototype** data satisfying the physical updates, the star rows, and every row within each of the blocks \(0,\ldots,r\) and \(r+1,\ldots,n\). Only their cross-block rows may fail. Assume \(f_n^0>0\).

For \(i\le r\), put

\[
p_i=\prod_{t<i}(1-h_t/H)>0,
\qquad
\Delta_i=\max_{j\ge r+1}\max\{0,-R^0_{ij},-R^0_{ji}\}.
\tag{4.2}
\]

### 4.2 Exact correction

Set \(\lambda=1/H\), and introduce one scalar quadratic trajectory

\[
z_0=\sqrt{M},\qquad z_{t+1}=(1-h_t/H)z_t,
\quad f_{\rm aux}(z)=\frac{z^2}{2H},
\tag{4.3}
\]

where

\[
\boxed{M=\max_{0\le i\le r}
\frac{2H^2\Delta_i}{(H-1)p_i^2}.}
\tag{4.4}
\]

The root annihilates it: \(z_j=0\) for every \(j\ge r+1\). Its interpolation residual for any ordered pair is

\[
R^{\rm aux}_{ij}
=\frac{\lambda(1-\lambda)}2(z_i-z_j)^2\ge0.
\tag{4.5}
\]

In particular every cross-root row, in either direction, receives

\[
R^{\rm aux}_{ij}
=\frac{H-1}{2H^2}p_i^2M\ge\Delta_i
\qquad(i\le r<j).
\tag{4.6}
\]

The corrected full data are

\[
X_i=(x_i^0,z_i),\quad G_i=(g_i^0,z_i/H),\quad
F_i=f_i^0+z_i^2/(2H),
\tag{4.7}
\]

with the selected star still \((0,0)\). Physical updates are exact. Star rows and within-block rows remain nonnegative because the quadratic contributes nonnegative rows. Equation (4.6) repairs every cross row. Thus (1.3) realizes all of (4.7) by one admissible function. The final function need not separate into a globally defined prototype function plus a quadratic; the finite interpolation argument is the correctness warrant.

The full radius and terminal value are exactly

\[
\|X_0\|^2=\|x_0^0\|^2+M,
\qquad F_n=f_n^0,
\tag{4.8}
\]

so the actual witness gives

\[
\boxed{\mathcal W_n(h)\ge
\frac{2f_n^0}{\|x_0^0\|^2+M}.}
\tag{4.9}
\]

The start is nonzero: otherwise the interpolated admissible function would keep GD at its minimizer, contradicting \(f_n^0>0\). If the prototype has a terminal-core port, it remains an exact terminal-core port because both auxiliary terminal position and gradient vanish. The initial port and the root port must be updated using (4.7); they cannot retain their old types.

Formula (4.4) is the smallest initial squared amplitude within this specified one-quadratic correction. A tie with an earlier root-sized step would make some \(p_i=0\), which explains the strict-prefix-maximum hypothesis rather than hiding a division by zero.

### 4.3 Prefix mass and conditioning

In this subsection only, \(q\) denotes a scalar prefix-step ratio, not the earlier terminal vector. Suppose that \(h_t\le qH\) for all \(t<r\), with \(0\le q<1\). Write \(S_i=\sum_{t<i}h_t\), \(P=S_r\), and \(\Delta=\max_i\Delta_i\). Since

\[
-\log(1-s)\le\frac{s}{1-q}\quad(0\le s\le q),
\]

we have

\[
p_i\ge\exp\left(-\frac{S_i}{H(1-q)}\right),
\tag{4.10}
\]

and hence

\[
\boxed{M\le\frac{2H^2}{H-1}
\exp\left(\frac{2P}{H(1-q)}\right)\Delta.}
\tag{4.11}
\]

The exact formula also gives \(M\ge2H^2\Delta/(H-1)\), because \(p_i\le1\). Thus this repair has cost of order \(H\Delta\) in a well-conditioned large-root regime, and can be much more expensive near a prefix tie or when \(P/H\) is large.

### 4.4 What would make the repair asymptotically cheap

Let \(E_n=2f_n^0>0\), and suppose a prototype already has

\[
\|x_0^0\|^2\le(1+\varepsilon_n)B_nE_n.
\]

Then (4.9) is

\[
\mathcal W_n(h)\ge
\frac{1}{B_n[1+\varepsilon_n+M/(B_nE_n)]}.
\tag{4.12}
\]

For example, if \(H\ge2\), \(H/B_n\le C\), \(P/H\le K\), and the scalar prefix ratio satisfies \(q\le q_0<1\), then

\[
\frac{M}{B_nE_n}
\le4C\exp\left(\frac{2K}{1-q_0}\right)\frac{\Delta}{E_n}.
\tag{4.13}
\]

Uniform \(\varepsilon_n=o(1)\) and \(\Delta/E_n=o(1)\) would suffice in this regime. A defect of size \(O(E_n/H)\) would cost only \(O(E_n)\), which is negligible compared with \(B_nE_n\) as \(B_n\to\infty\). Conversely, if \(H\ge cB_n\) and \(\Delta\ge c'E_n\), this particular repair costs a fixed positive fraction of \(B_nE_n\); increasing the horizon does not remove that relative added cost.

No bound of the form \(\Delta/E_n=o(1)\), no uniform \(q_0,K,C\), and no all-word prototype selection is established here. In a recursive construction all costs must be transported to the one original initial norm; per-node smallness without a summable global bound is insufficient.

### 4.5 Trading initial radius against actual conjugate-height reserves

There is a further exact refinement within the same finite-data repair. Assume \(M>0\), and continue \(p_i=0\) after the root. For \(0\le\theta\le1\), replace the auxiliary query data by

\[
z_i=(p_i-\theta)\sqrt M,\qquad
g_i^{\rm aux}=\frac{p_i\sqrt M}{H},\qquad
f_i^{\rm aux}=\frac{p_i^2M}{2H}.
\tag{4.14}
\]

The auxiliary star datum is still position, gradient, and value zero. Physical updates hold. Every non-star residual remains exactly (4.5), because the common position translation cancels. Its two star resources are

\[
\ell_i^{\rm aux}=\frac{M}{2H}(1-1/H)p_i^2,\qquad
u_i^{\rm aux}=\frac{M}{H}
\left[\frac{1-1/H}{2}p_i^2-\theta p_i\right].
\tag{4.15}
\]

The second quantity can be negative. Therefore these auxiliary data are not being asserted to be an independently admissible function. The *combined* data preserve the original zero minimizer exactly when

\[
\theta\le\theta_{\max}:=
\min_{i\le r}\left\{
\frac{H u_i^0}{Mp_i}+\frac{1-1/H}{2}p_i
\right\}.
\tag{4.16}
\]

The other star inequality is automatic. Cross rows remain repaired, within-block rows remain nonnegative, and interpolation once again supplies one admissible static function. Choosing any \(0\le\theta\le\min(1,\theta_{\max})\) gives the exact score

\[
\mathcal W_n(h)\ge
\frac{2f_n^0}{\|x_0^0\|^2+(1-\theta)^2M}.
\tag{4.17}
\]

The terminal gradient and objective are unchanged, but the terminal fresh position is \(-\theta\sqrt M\). Thus the original minimizer is retained and the initial norm is fully charged, while an exact terminal-core port is generally lost. This refinement is directly usable at a final objective join. It cannot be recycled as an unchanged terminal-core child in the next join.

For an arbitrary non-diagonal prototype, sufficiently large actual heights \(u_i^0\) could permit \(\theta=1\), eliminating the added initial norm. However, the diagonal root of the submitted crossing prototype has \(u_r^0=0\). In that case

\[
\theta_{\max}\le\frac{1-1/H}{2}p_r<\frac12,
\qquad
(1-\theta)^2M>\frac14M.
\tag{4.18}
\]

Positive heights only at earlier times do not bypass this root constraint. With all \(u_i^0=0\), the exact permissible maximum is \((1-1/H)p_r/2\), since the prefix products are nonincreasing. Hence this translation can improve a constant but cannot turn an order-\(B_nE_n\) repair into an asymptotically free one while preserving the old diagonal-root prototype.

Equations (4.15)--(4.18) identify a precise alternative resource: a genuinely non-diagonal root must supply the stated conjugate-height reserve, and any recursive use must also track its terminal flat displacement. Neither reserve is supplied by \(C_k\) or \(B_k\).

## 5. Result of this invocation and the precise unresolved mechanism

The submitted proof does not become valid by inserting an uncharged “directed coordinate.” Its exact residual-preserving architecture is classified by (3.2)--(3.5) and cannot repair one of the two orientations at all. The cap-age operation also has the nontrivial height budget (2.3), even before cross-block compatibility is considered.

There is nevertheless an actual salvage: equations (4.1)--(4.9) give one static admissible hard function from any two-block prototype, with all cross-time rows, the same selected minimizer, nonzero start, unchanged terminal objective, and an exact extra original-radius cost. Equations (4.10)--(4.13) isolate a concrete conditional regime in which that cost is asymptotically negligible. The translated data (4.14)--(4.18) give an additional exact height-for-radius tradeoff, with the diagonal-root limitation stated explicitly.

What remains is a new quantitative compatibility construction, not the scalar crossing algebra. It must select actual terminal-core children and their embeddings for every high-mass word, pay the cap-height budgets when a cap branch is used, and produce either a one-root deficit bound satisfying (4.12) uniformly or a recursively transported total repair cost \(o(B_nE_n)\). The scalar recurrences for \(\Omega\) and \(G\) supply none of these profile estimates. The low-mass Huber region remains covered by the accepted result; the complementary all-word region is not closed by this invocation.
