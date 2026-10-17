# Cross-block interpolation repair by one capped coordinate

**UNVERIFIED analytical draft.** This is a complete finite-data repair lemma, not an all-word minimax proof. It improves the conditioning and root restrictions of the R15 quadratic-data correction, but a uniform globally transported cost estimate is still missing.

The completed finite lemma received an independent manual audit in ../audit_huber_repair_20261017_r16/AUDIT.md. The audit is not Danus verifier acceptance. Its requested degenerate-case and comparison-scale clarifications are incorporated below.

## 1. Prototype and deficits

Normalize smoothness to one and keep the originally selected minimizer at zero with value zero. A finite physical word h_0,...,h_(n-1) is nonnegative. Prototype data (x_i^0,g_i^0,f_i^0), i=0,...,n, satisfy the GD updates, both star constraints, and every smooth-convex interpolation row inside each of two consecutive blocks
\[
L=\{0,\ldots,r\},\qquad R=\{r+1,\ldots,n\}.
\]
Only rows between the two blocks may fail. Assume f_n^0>0, and choose any root H=h_r>1. No prefix-maximum condition or distinctness of steps is imposed.

Use
\[
y_i^0=x_i^0-g_i^0,\quad
\ell_i^0=f_i^0-\tfrac12\|g_i^0\|^2,\quad
u_i^0=\langle g_i^0,y_i^0\rangle-\ell_i^0,
\]
\[
R_{ij}^0=\ell_j^0+u_i^0-\langle g_i^0,y_j^0\rangle.
\]
The star constraints are ell_i^0,u_i^0>=0. Define
\[
A=\max_{i\le r<j}(-R_{ij}^0)_+,\qquad
B_i=\max_{j>r}(-R_{ji}^0)_+,\qquad
\Delta=\max\{A,\max_{i\le r}B_i\}.
\]
Let P=sum_(t<r) h_t, S_i=sum_(t<i)h_t, and P_i=P-S_i>=0 for i<=r.

## 2. A capped coordinate annihilated into a flat minimum

Choose 1<eta<H and b>=0. Consider the one-dimensional convex 1-smooth function
\[
\varphi_b(z)=
\begin{cases}
0,&z\le0,\\
z^2/2,&0\le z\le b,\\
bz-b^2/2,&z\ge b.
\end{cases}
\]
For b=0 this denotes the zero function. Start this coordinate at z_0=(P+eta)b and run the original word. At every prefix query i<=r,
\[
z_i=(P_i+\eta)b,\quad g_i^{\rm aux}=b,\quad
f_i^{\rm aux}=(P_i+\eta-\tfrac12)b^2.
\]
Every prefix point lies in the constant-gradient region. At the selected root,
\[
z_{r+1}=(\eta-H)b\le0,
\]
with strict inequality when b>0, and the coordinate remains at this point with gradient and value zero at every later query.

The star datum zero is an actual minimizer. On L its interpolation variables are
\[
y_i^{\rm aux}=(P_i+\eta-1)b,\quad
\ell_i^{\rm aux}=(P_i+\eta-1)b^2,\quad u_i^{\rm aux}=0.
\]
On R they are
\[
y_j^{\rm aux}=(\eta-H)b,\quad
\ell_j^{\rm aux}=u_j^{\rm aux}=0.
\]
Consequently all within-block rows vanish and the two cross orientations are exactly
\[
R^{\rm aux}_{ij}=(H-\eta)b^2,\qquad
R^{\rm aux}_{ji}=(P_i+\eta-1)b^2
\qquad(i\le r<j).
\]
Both are nonnegative, as are both star resources.

Taking
\[
\boxed{b^2=\max\left\{\frac{A}{H-\eta},
\max_{i\le r}\frac{B_i}{P_i+\eta-1}\right\}}
\]
repairs every cross row when the auxiliary data are appended orthogonally to the prototype. All other rows remain nonnegative, and every GD update holds. Full smooth-convex interpolation therefore gives one finite-dimensional static admissible function realizing the combined data and the same selected minimizer zero. The possibly infeasible prototype is not assumed to be a globally defined function.

The terminal objective is unchanged, and the exact original-radius cost is
\[
M_{\rm flat}=(P+\eta)^2b^2.
\]
Thus
\[
\boxed{\mathcal W_n(h)\ge
\frac{2f_n^0}{\|x_0^0\|^2+(P+\eta)^2b^2}.}
\]
The appended terminal position is nonzero when b>0, although its terminal gradient and objective are zero. An exact terminal-core port is therefore generally lost.

## 3. Uniform explicit cost and optional terminal-core preservation

The balanced choice eta=(H+1)/2 gives
\[
b^2\le\frac{2\Delta}{H-1},\qquad
\boxed{M_{\rm flat}\le
\frac{(2P+H+1)^2}{2(H-1)}\Delta.}
\]
This is polynomial in P/H. It has no product of inverse prefix factors and remains valid when prefix steps equal or exceed H.

If a zero appended terminal position is required, translate every auxiliary query by (H-eta)b without changing its gradients or values. These are actual data of the shifted function z -> phi_b(z-(H-eta)b), whose minimum set still contains zero.

The new initial position is (P+H)b, and the root query is Hb. The root sends this coordinate to zero, where all later queries stay. Every non-star row is unchanged. On L its star resources are now
\[
\ell_i^{\rm aux}=(P_i+\eta-1)b^2,\qquad
u_i^{\rm aux}=(H-\eta)b^2,
\]
so the same original minimizer is valid. Both resources vanish on R.

This variant preserves an existing terminal-core port of the prototype, with
\[
\boxed{M_{\rm core}=(P+H)^2b^2
\le\frac{2(P+H)^2}{H-1}\Delta.}
\]
It also creates positive conjugate heights on every prefix query when b>0 (zero heights when b=0). Its initial and root ports have changed and must be carried forward explicitly.

If the unshifted prototype has u_i^0=0 at every query, the unshifted corrected data also have u_i=0. In that special case a projection model itself realizes the correction: take the convex hull of zero and all combined gradient vectors. The verified rows are exactly its supporting-normal conditions. General prototypes or the shifted variant use the full interpolation theorem.

## 4. What this changes and what it does not prove

The R15 quadratic repair required a strict prefix maximum and paid inverse products p_i^(-2), where p_i=prod_(t<i)(1-h_t/H). The present construction works at any root H>1 and replaces that sensitivity by the displayed polynomial prefix-mass cost. It does so by allowing a cap at the root and, in the unshifted version, a nonzero terminal flat displacement.

This does not contradict the R15 zero-residual repair obstruction, which required diagonal root ports. For a nontrivial repair b>0, the root is explicitly non-diagonal: before translation its normal coordinate is (eta-1)b; after translation it is (H-1)b.

Let E_n=2f_n^0>0 and let B_n>0 be a comparison scale; in the intended application B_n=(U_n^ZJ)^(-1)=2S_bullet(n)+1. If near-benchmark prototypes with ||x_0^0||^2<=(1+o(1))B_n E_n can be chosen uniformly, and if H>=2, H/B_n<=C_0 and P/H<=K_0 with constants independent of the covered words, then either variant satisfies
\[
\frac{M}{B_nE_n}\le4C_0(K_0+1)^2\frac{\Delta}{E_n}.
\]
Thus a uniformly vanishing Delta/E_n makes the added relative cost vanish. No such all-word prototype or defect bound is asserted. For recursive use, every auxiliary cost must be transported to the single original starting point; summability cannot be inferred from a per-node estimate.

No new all-depth history input, original-profile upper bound, or asymptotically optimal all-word lower witness follows from this lemma alone.
