# R15 tree-energy handoff

**UNVERIFIED direct analytical draft. Original exact-profile problem OPEN. The all-depth history input is not proved or disproved.**

The complete derivations are in `PROOF_ATTEMPT.md` in this directory. This worker used one invocation, at most two substantive approaches, and zero mathematical programs, numerical arrays, solvers, formal submissions, extra agents/models, or services. Only this file and `PROOF_ATTEMPT.md` were created. The hard deadline was 2026-10-17 04:20:00 UTC; the packet was completed before that deadline.

## 1. What is established in the manual draft

Fix one enclosing `m>=1536`, `e=1/(4m)`, `beta=1-e`, `c=(1+sqrt(2))(1+e)`, `a=beta/c`, and the same-parameter hierarchy

\[
H_0=(),\qquad H_{j+1}=(H_j,1+k_j,H_j),\qquad
k_j=ac^j,\qquad C_j=1+\sum H_j.
\]

For a physical word with capacity `C` define

\[
\mathcal E(J)=2\sum_i h_i(f_i-f_{\rm end})
-\sum_i h_i(h_i-1)\|g_i\|^2-(J-C)\|g_{\rm end}\|^2.
\]

The original R15 request is `E((7/10) C_j^2)>=0` for every `1<=j<m` and every actual convex 1-smooth trajectory. The parent subsequently reported a conditional PD join permitting the smaller coefficient `49/100`. Neither physical input is established here.

Set

\[
B_l=\frac{3C_l+k_l}{C_l-k_l},\qquad
P_1=C_1^2,\quad P_{l+1}=B_lP_l,\quad
D_l=P_l-B_lk_l^2,\quad A_l=P_l-C_l^2.
\]

The following are the concrete new conclusions:

- **Uniform localization:** `D_l>0` for every `l>=21`, throughout `e<=1/6144`. More precisely,
  \[
  \frac{P_l}{B_lk_l^2}\ge(1-49e)[1+(5/2)e]^{l-1}.
  \]
  Also `P_l/C_l^2>=1-48e`, so the root reserve is positive at either terminal coefficient under consideration.
- **Uniform negative low coefficient:** `D_2<-e C_2^2` on the entire same parameter interval. This follows from `F_2'(0)=112 sqrt(2)-160<-3/2` for `F_2=D_2/C_2^2`, together with the explicitly bounded `|F_2''|<64`.
- **Exact repetition and conservation:** a depth-`J` tree has total inherited weight
  \[
  \Omega_{l,J}=\prod_{r=l+1}^{J-1}(1+B_r)
  \]
  on height-`l` bare terms. The identities
  \[
  D_l=(1+B_l)A_l-A_{l+1},\qquad
  \sum_{l=1}^{J-1}D_l\Omega_{l,J}=C_J^2-P_J
  \]
  retain the cancellations among all repeated subtrees.
- **Actual obstruction to root-only repair:** the symmetric Huber function started at `x0=C_J` has gradient 1 at every query, zero original interpolation rows, and zero leaf squares. Its height-2 negative mass `N_(2,J)` satisfies
  \[
  \frac{N_{2,J}}{P_J}>\frac e8(7/6)^{J-3}.
  \]
  At `J=m-1` this diverges with `m`, although its actual target residual is `(1-theta) C_J^2>0`. Thus no depth-independent bound can absorb all low negative terms into the retained rows, leaf squares, and a bounded root budget after discarding positive internal coefficients. Those positive terms must be transported across levels.

These statements use actual interpolation rows and an actual Huber trace. They do not infer feasibility from a free gradient vector or a negative eigenvector.

## 2. The reciprocal-P candidate: scalar success, physical failure

The parent proposed

\[
\bar P_1=C_1^2,\qquad
\bar P_{l+1}=\max\{C_{l+1}^2,B_l\bar P_l\},\qquad
J_l^{\rm cap}=C_l^4/\bar P_l.
\]

The scalar estimate is valid in the manual derivation. Put

\[
R=\frac{c+1}{c^2(3-c)}.
\]

Then

\[
\frac{J_l^{\rm cap}}{C_l^2}\ge R^{-(l-1)}
\ge\exp(-1/\sqrt2-(5/2)e)>49/100
\qquad(1\le l<m).
\]

This uses `q(r)=(3+r)/[(1-r)(2+r)^2]`, which is increasing, `q(k_l/C_l)<=R`, and `(log R)''<20`. It also gives the uniform limiting lower bound `exp(-1/sqrt(2))`.

**The unmodified physical invariant `E(J_l^cap)>=0` is nevertheless false.** Here is the complete actual witness:

1. Let `r0=1/(1+sqrt(2))`. Exact formulas give `r1=k1/C1<r0<r2=k2/C2`. Consequently `barP2=C2^2` and `barP3=B2 C2^2`.
2. Set `r=r2` and take the static function with gradient `clamp(x,-r,1)`, with quadratic middle and affine tails.
3. Run the literal `H3=(H2,1+k2,H2)` from `x0=C2`. The left child has gradient 1 throughout and ends at 1. The bridge goes to `-k2`. The right child has gradient `-r` throughout and ends at `-r`, since `k2=C2 r`.
4. All minimizer rows at the original minimizer zero vanish, and
   \[
   \mathcal E_3(J_3^{\rm cap})
   =C_2^2\left[1-\frac{r^2(2+r)^4}{B(r)}\right]<0.
   \]
5. For an exact sign check set `t=r(2+r)` and `u=(1+r)/(1-r)`. Then
   \[
   r^2(2+r)^4-B(r)
   =(t-1)\{(t+1)(2+r)^2-u\}>0
   \]
   because `r0<r<5/12`.

This witness is admissible for every `m>=1536`; depth 3 is within the required internal range. It refutes the particular reciprocal physical invariant, not the requested fixed `theta=7/10` or `theta=49/100` inequalities. It also does not rule out a different initial prefactor.

## 3. A precise O(e) seed repair of that witness

The modified scalar sequence

\[
\bar P^{(4)}_1=(1+4e)C_1^2,\qquad
\bar P^{(4)}_{l+1}=\max\{C_{l+1}^2,B_l\bar P^{(4)}_l\},\qquad
J_l^{(4)}=C_l^4/\bar P_l^{(4)}
\]

satisfies

\[
\frac{J_l^{(4)}}{C_l^2}
\ge\exp(-1/\sqrt2-(13/2)e)>49/100
\quad(1\le l<m,\ m\ge1536).
\]

It repairs the displayed actual `H3` witness. In detail, with
`K(r)=r^2(2+r)^4/B(r)`, the derivative bounds give

\[
K(r_2)\le e^{7e/4},\qquad q(r_1)\ge e^{-9e/5},\qquad
K(r_2)/q(r_1)\le e^{71e/20}\le1+4e.
\]

Therefore

\[
\bar P^{(4)}_3/C_3^2
\ge q(r_2)q(r_1)(1+4e)
\ge[r_2(2+r_2)]^2,
\]

which is exactly the threshold for nonnegativity on that witness. Its leaf coefficient is valid as well, being smaller than `C1^2`.

**This is not an all-history repair.** No proof is given for `E(J_l^(4))>=0` at all depths, or even for every depth-3 history. The established facts are the scalar margin and the removal of this specific actual obstruction.

## 4. What must not be claimed

- Positive bare coefficients from height 21 onward do not prove the tree energy nonnegative.
- A bounded low-level subtree cannot be certified at coefficient `P_l` by fixed-depth compactness: an affine history gives `E(P_l)=C_l^2-P_l`, which is negative at suitable fixed depths for small positive `e`.
- The capped reciprocal scalar bound does not imply a physical history inequality; the unmodified candidate is explicitly false.
- The `1+4e` seed repair has not been checked against all histories, and no modified reciprocal family is declared universally valid or universally impossible.
- No actual violation of the requested `theta=7/10` or newly sufficient `theta=49/100` input is produced. No original minimax resolution or accepted Danus fact is produced.

The remaining all-depth step is a signed transfer of endpoint energy that keeps the positive internal coefficients and the original interpolation rows together. The root-only absorption route is ruled out by an actual trace, and the exact unmodified reciprocal candidate should not be sent for a global proof without correcting its seed or its invariant.
