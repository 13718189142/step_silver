# Independent manual audit of the R17 affine-right slack lemma

Date: 2026-10-17. Evidence level: **independent MANUAL derivation audit only**.

**Editorial follow-up checked:** after the initial audit, the parent added explicit residual definitions and the l >= 2 scope clarification. The auditor read the complete revised file back. Its SHA-256 is `8bfbe3d16d6673b02e50ba906fa14d628e5b0820d916ce3f4c74eb3319f69ba8`. These edits resolve the two principal presentation issues below; no mathematical identity, constant, hypothesis, or main claim changed. Manual acceptance extends to this revised version. The detailed findings below retain the original-snapshot chronology.

## 1. Verdict and exact audit target

The main inequalities (1) and (2) in the designated source pass this independent manual audit under the stated constant-gradient right-block hypothesis, for every integer depth J >= 1. No fatal algebraic, sign, normalization, indexing, or minimizer-quantifier error was found in the proof used for these two conclusions.

This is not verifier acceptance, a fact-graph entry, an unrestricted bound on W(H_J), or a resolution of the original minimax problem. The latter remains OPEN.

Audited source:

`runtime/projects/gd-exact-profile-20260926/research/resume_20261017_r17/AFFINE_RIGHT_WITH_SLACK.md`

SHA-256 checked before the audit:

`b8e0ee3d6dd8aff347abc9164e844749469d9dc13700ff8f610deb0cdcf796a6`

The source was not edited by this auditor. The parent subsequently made only the editorial follow-up recorded above. OPERATOR.md, the initialization marker, and the project PROBLEM.md were read. No mathematical program, numerical test, solver, external model, subagent, service, formal submission, fact operation, or publication was used. The R16 packet was not needed: the decisive derivations below are self-contained.

Two local presentation issues identified in the original snapshot, and now resolved by the checked editorial follow-up, were:

1. The coefficient estimates (9), and the nonlocal recurrence (8)--(12), must explicitly have l >= 2. In particular, the assertion alpha_l < 1/2 is false at l = 1. The proof only applies these estimates for l >= 2, so this does not invalidate (1) or (2).
2. E_J(theta) and E_Gamma are not defined in the standalone source. The natural intended definitions are stated in Section 9 below. With those definitions, the displayed E_J(49/100) corollary and the final use of E_Gamma are correct. Without a definition, the former is an ambiguous notation-level claim rather than a standalone specified conclusion.

The phrase that endpoint slacks "may be any nonnegative values" should mean that no additional zero or upper-bound assumption is imposed on their actual feasible values. It should not be read as a realizability assertion for independently prescribed arbitrary slack values.

## 2. Objects, assumptions, and ranges

Write epsilon for the source's scalar e, to distinguish it from its terminal-query subscript. Let

\[
t=1+\sqrt2,\quad 0<\epsilon=\frac1{4m}\le\frac1{6144},\quad
\beta=1-\epsilon,\quad c=t(1+\epsilon),\quad a=\frac\beta c.
\]

The schedule H_l has n_l = 2^l - 1 steps. Its total step sum is C_l - 1. Since H_l is the left prefix of H_J for l <= J, its endpoint is the actual query

\[
v_l=x_{n_l},\qquad p_l=\nabla f(v_l).
\]

For 1 <= l <= J - 1, the root step after v_l has size 1 + k_l, where k_l = a c^l. Its next query is

\[
w_l=x_{2^l}=v_l-(1+k_l)p_l.
\]

The right H_l block begins at w_l and ends at v_(l+1). The hypothesis says that every query in this block, including both endpoints, has gradient p_(l+1). Hence

\[
v_l-v_{l+1}=(1+k_l)p_l+(C_l-1)p_{l+1}.
\tag{A1}
\]

No endpoint row is assumed zero. The nonlocal row using v_(l-1) is needed only for 2 <= l <= J - 1. For J = 1, no right-block hypothesis is imposed. For J = 2, no nonlocal recurrence is used.

Convexity and 1-smoothness give all the original interpolation inequalities

\[
Q_{ij}=2(f_i-f_j)-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2\ge0.
\]

For completeness, this follows without invoking any interpolation realization theorem: apply the smooth descent inequality to F(x) = f(x) - <g_j,x>, whose attained minimum is at x_j, at the point x_i - (g_i-g_j). Thus F(x_i)-F(x_j) >= ||g_i-g_j||^2/2. All rows used in this audit are rows of the actual given function and queries.

## 3. Scalar recurrence and finite bounds

The physical concatenation gives

\[
C_{l+1}=2C_l+k_l,\qquad C_0=1.
\]

Solving this scalar recurrence directly gives

\[
C_l=\frac{a}{c-2}c^l+\left(1-\frac{a}{c-2}\right)2^l.
\]

Define

\[
\zeta=\frac{c-2}{a}-1
=\frac{(5+2\sqrt2)\epsilon+(1+\sqrt2)^2\epsilon^2}{1-\epsilon}>0.
\]

Then exactly

\[
C_l=c^l\frac{1+\zeta(2/c)^l}{1+\zeta},\qquad
r_l=\frac{k_l}{C_l}=\frac{c-2}{1+\zeta(2/c)^l}.
\]

The stated zeta < 9 epsilon follows, for example, from sqrt(2) < 3/2 and

\[
8+\frac{25}{4}\epsilon<9(1-\epsilon),
\]

which holds since 61 epsilon / 4 < 1. Also C_l <= c^l because 2/c < 1.

One fully rational check for c < 29/12 is sqrt(2) < 99/70 and

\[
c<\frac{169}{70}\frac{6145}{6144}<\frac{29}{12}.
\]

Together with beta > 99/100, this gives

\[
a>\frac{297}{725}>\frac25,\qquad
\frac25<r_l<c-2<\frac5{12}.
\]

Consequently

\[
C_1=2+a>\frac{12}{5},\quad
C_2=2C_1+\beta>\frac{24}{5}+\frac{99}{100}>\frac{23}{4}.
\]

C_l is increasing, so the last lower bound holds for all l >= 2. Furthermore

\[
\frac{C_l}{C_{l-1}}=2+r_{l-1}\in\left(\frac{12}{5},\frac{29}{12}\right)
\subset\left(\frac{12}{5},\frac52\right),\qquad l\ge2.
\]

This checks every bound in source (3), including the slightly stronger ratio upper bound needed in its beta_l estimate.

## 4. Endpoint geometry and the nonlocal row

Set y_i = x_i - g_i and u_i = <g_i,x_i> - f_i - ||g_i||^2/2. Direct expansion gives source (4):

\[
\frac12Q_{ij}=u_j-u_i-\langle y_i,g_j-g_i\rangle.
\]

If g_i = g_j, the two directed rows imply u_i = u_j. In particular, u_(w_l) = u_(v_(l+1)).

For d_l = p_l - p_(l+1), let F_l = Q_(v_l,v_(l+1))/2 and R_l = Q_(v_(l+1),v_l)/2. Both are nonnegative. From (A1),

\[
y_{v_l}-y_{v_{l+1}}=k_lp_l+C_lp_{l+1},
\]

so T_l = F_l + R_l satisfies

\[
T_l=\langle k_lp_l+C_lp_{l+1},d_l\rangle
=(C_l+k_l)\langle p_l,d_l\rangle-C_l\|d_l\|^2.
\]

This proves source (5). Replacing p_(l-1) by p_l + d_(l-1) in the preceding instance gives, for l >= 2,

\[
\langle p_l,d_{l-1}\rangle
=-\frac{r_{l-1}}{1+r_{l-1}}\|d_{l-1}\|^2
+\frac{T_{l-1}}{C_{l-1}+k_{l-1}},
\]

which is source (6).

The root step gives y_(w_l) = y_(v_l) - k_l p_l - p_(l+1). Substituting this and the equality of the u values into Q_(w_l,v_(l-1))/2 yields

\[
\frac12Q_{w_l,v_{l-1}}
=\langle k_lp_l+p_{l+1},d_{l-1}+d_l\rangle+R_{l-1}-F_l.
\tag{A2}
\]

This verifies the orientation and both signs in source (7).

With the source's A_l, B_l, alpha_l, beta_l, expanding p_(l+1) = p_l - d_l and using (5)--(6) yields

\[
\langle k_lp_l+p_{l+1},d_{l-1}+d_l\rangle
=N_l+\alpha_lT_l+\beta_lT_{l-1},
\]

where

\[
N_l=A_l\|d_l\|^2-B_l\|d_{l-1}\|^2-\langle d_l,d_{l-1}\rangle.
\]

Using (A2) therefore gives exactly

\[
N_l=\frac12Q_{w_l,v_{l-1}}+(1-\alpha_l)F_l
-\alpha_lR_l-\beta_lF_{l-1}-(1+\beta_l)R_{l-1}.
\]

Every debt term in source (8) has the correct sign and coefficient. No zero-row substitution occurred.

## 5. Local coefficient bounds and the completed square

All estimates in this section have l >= 2. From r_l > 2/5 and r_(l-1)/(1+r_(l-1)) > 2/7,

\[
B_l>\frac4{35}C_l+\frac27,\qquad
A_l<\frac5{17}(C_l-1).
\]

Hence

\[
4B_l-A_l-2>
\frac{97}{595}C_l-\frac{67}{119}
>\frac{891}{2380}>0.
\]

The alpha_l estimate follows from

\[
(1-r_l)C_l>\frac7{12}\frac{23}{4}>2,
\]

which is equivalent to 0 < alpha_l < 1/2. For beta_l, dividing numerator and denominator by C_(l-1) gives

\[
\beta_l
=\frac{r_l(C_l/C_{l-1})+1/C_{l-1}}{1+r_{l-1}}
<\frac{145/144+5/12}{7/5}
=\frac{1025}{1008}<\frac{21}{20}.
\]

The source's completed-square identity (10) is exact: expansion of its right side leaves (4B-1)||d||^2 + (1/4-B)||e||^2, precisely its left side. Since B_l - 1/4 > 0, source (8) and the nonnegative square and coefficient term give

\[
\|d_{l-1}\|^2\le4\|d_l\|^2+
\frac{\alpha_lR_l+\beta_lF_{l-1}+(1+\beta_l)R_{l-1}}
{B_l-1/4}.
\]

This is source (11), valid even if either vector or any gradient is zero.

The range clarification is real: at l = 1, k_1 = beta and C_1 = 2+a, so

\[
\alpha_1=\frac{1+\beta}{2+a+\beta}>\frac12,
\]

because beta > a = beta/c. Thus the source should explicitly restrict (9) to l >= 2. Its proof uses precisely that range and needs no l = 1 instance.

## 6. Energy recursion and all constants

Use z_l = C_l^2 ||d_l||^2 in this audit, to avoid the source's reuse of w_l for both a query and an energy. From the bounds above,

\[
\frac{C_{l-1}^2}{B_l-1/4}
<\frac{25}{144}\frac{35}{4}C_l
=\frac{875}{576}C_l<2C_l.
\]

Multiplying (11) by C_(l-1)^2 and using C_(l-1)/C_l < 5/12 gives

\[
z_{l-1}\le\frac{25}{36}z_l+L_l,
\]

where the debt is bounded by

\[
L_l\le C_lR_l+\frac{21}{4}C_{l-1}F_{l-1}
+\frac{41}{4}C_{l-1}R_{l-1}.
\]

The last two coefficients come from 2 C_l beta_l < (21/10) C_l < (21/4) C_(l-1) and 2 C_l(1+beta_l) < (41/10) C_l < (41/4) C_(l-1). Thus source (12) is valid.

Let W = sum_(l=1)^(J-1) z_l. For J >= 3, summing the preceding recurrence over l = 2,...,J-1 gives

\[
\frac{11}{36}W\le z_{J-1}-\frac{25}{36}z_1+
\sum_{l=2}^{J-1}L_l
\le z_{J-1}+\sum_{l=2}^{J-1}L_l.
\]

For J = 2, W = z_1, so the same stated upper bound holds directly. This proves source (13), including the boundary case.

To bound z_(J-1), put q = p_J, d = d_(J-1), C = C_(J-1), r = r_(J-1), and T = T_(J-1). Source (5) becomes

\[
r\|d\|^2+(1+r)\langle q,d\rangle=T/C.
\]

Young's inequality in the form

\[
(1+r)|\langle q,d\rangle|
\le\frac r2\|d\|^2+\frac{(1+r)^2}{2r}\|q\|^2
\]

gives

\[
\|d\|^2\le\frac{2}{rC}T+\left(\frac{1+r}{r}\right)^2\|q\|^2
\le\frac5C T+\frac{49}{4}\|q\|^2.
\]

Using the factor 4 from (13), its terminal contribution is bounded by

\[
20C_{J-1}(F_{J-1}+R_{J-1})
+49C_{J-1}^2\|q\|^2
\le20C_{J-1}(F_{J-1}+R_{J-1})
+\frac{1225}{144}C_J^2\|q\|^2.
\]

Since 1225/144 < 9, this gives the claimed 9. In 4 sum L_l, the F coefficients are at most 21 after reindexing, and the R coefficients are at most 4+41 = 45. Bounding the terminal row contribution by 20 times each full corresponding nonnegative sum gives exactly

\[
W\le9C_J^2\|q\|^2
+41\sum_{l=1}^{J-1}C_lF_l
+65\sum_{l=1}^{J-1}C_lR_l.
\tag{A3}
\]

This verifies source (14). The loose constants deliberately avoid any reliance on disjointness of endpoint supports.

## 7. Exact history split and the leaf

For a constant-gradient block with gradient q and step sum S, the two directed equal-gradient rows give f_i-f_end = (sum of remaining steps)||q||^2. Therefore

\[
2\sum_i h_i(f_i-f_{end})-\sum_i h_i(h_i-1)\|q\|^2
=(S^2+S)\|q\|^2.
\]

For S = C_l - 1, its standard residual is exactly zero, as used in the source.

To check source (15), abbreviate C = C_l, k = k_l, C' = 2C+k, p = p_l, q = p_(l+1), and Delta f = f(v_l)-f(v_(l+1)). Direct splitting of the physical steps gives

\[
\begin{aligned}
E_{l+1}^{std}-E_l^{std}
={}&2(C+k)\,\Delta f
+(C^2-C-k-k^2)\|p\|^2\\
&+(-3C^2-4Ck-k^2+C+k)\|q\|^2.
\end{aligned}
\tag{A4}
\]

The original rows, with the original physical displacement (A1), are

\[
F_l=\Delta f-\tfrac12\|p\|^2-k\langle p,q\rangle
-(C-\tfrac12)\|q\|^2,
\]

\[
R_l=-\Delta f+(k+\tfrac12)\|p\|^2+C\langle p,q\rangle
-\tfrac12\|q\|^2.
\]

Expanding

\[
-(k^2+2kC-C^2)\|p-q\|^2+2C'F_l+2CR_l
\]

has zero <p,q> coefficient and exactly the coefficients in (A4). Hence

\[
E_{l+1}^{std}=E_l^{std}
-(r_l^2+2r_l-1)C_l^2\|d_l\|^2
+2C_{l+1}F_l+2C_lR_l
\]

is an exact identity, not a zero-slack specialization.

At the one-step leaf h = 1+a, a < 1/(1+sqrt(2)) = sqrt(2)-1, so 0 < h < sqrt(2). Expanding the two actual leaf rows gives

\[
E_1^{std}=(h+1)Q_{01}+Q_{10}+(2-h^2)\|g_0-g_1\|^2\ge0.
\]

The coefficient of ||g_1||^2 on both sides is -h(h+1), equal to -(C_1^2-C_1). All factors of 2 agree with the source's Q convention.

## 8. Small deficit and the main residual bound

The function r -> r^2+2r-1 is increasing for r >= 0, so r_l < c-2 gives

\[
r_l^2+2r_l-1<c^2-2c-1
=(4+2\sqrt2)\epsilon+(3+2\sqrt2)\epsilon^2<7\epsilon.
\]

For an exact check of the last bound, sqrt(2) < 10/7 gives a coefficient at most (48+41 epsilon)/7 < 7, since 41 epsilon < 1. No numerical estimate is used.

Iterating the exact history identity, using the nonnegative leaf residual, and then applying (A3) gives

\[
\begin{aligned}
E_J^{std}\ge{}&-63\epsilon C_J^2\|p_J\|^2\\
&+\sum_{l=1}^{J-1}(2C_{l+1}-287\epsilon C_l)F_l
+\sum_{l=1}^{J-1}(2-455\epsilon)C_lR_l.
\end{aligned}
\]

Both sets of row coefficients are strictly positive under epsilon <= 1/6144. For example, 2 C_(l+1)/C_l > 24/5 while 287 epsilon < 1, and 455 epsilon < 1. Dropping them proves source (1). For J = 1, it follows directly from the leaf residual and the nonnegative squared norm.

Thus the deficit constant 63 = 7 times 9 is justified uniformly at every depth. Negative early values of r_l^2+2r_l-1 only strengthen the estimate.

## 9. Missing residual definitions and the terminal certificate

The definitions consistent with every displayed formula are

\[
E_J(\theta):=
2\sum_{i=0}^{n-1}h_i(f_i-f_n)
-\sum_{i=0}^{n-1}h_i(h_i-1)\|g_i\|^2
-(\theta C_J^2-C_J)\|g_n\|^2,
\]

and, for a scalar Gamma,

\[
E_\Gamma:=
2\sum_{i=0}^{n-1}h_i(f_i-f_n)
-\sum_{i=0}^{n-1}h_i(h_i-1)\|g_i\|^2
-\Gamma\|g_n\|^2.
\]

These are explicit recommendations, not edits to the audited source. Under these definitions,

\[
E_J(49/100)=E_J^{std}+\frac{51}{100}C_J^2\|g_n\|^2\ge0,
\]

because 51/100 - 63 epsilon > 0. Also Gamma = (1-63 epsilon) C_J^2 - C_J gives E_Gamma >= 0 directly from (1).

## 10. Dominance identity and arbitrary selected minimizers

Fix any x_star in argmin f, without changing it. Let n = 2^J - 1, C = C_J, S = C-1, q = g_n, and

\[
\omega=1+\frac{15}{17}S,\quad
B=S+\omega=1+\frac{32}{17}S.
\]

Use lambda_i = h_i for i = 0,...,n-1 and lambda_n = omega. These weights are positive. Set

\[
H=\sum_{i=0}^{n-1}h_ig_i=x_0-x_n,\quad
G=H+\omega q,\quad z=x_0-x_\star.
\]

Since the selected point is a minimizer, g_star = 0 and

\[
Q_{\star i}=-2(f_i-f_\star)+2\langle g_i,x_i-x_\star\rangle-\|g_i\|^2\ge0.
\]

Expanding the source's D gives

\[
\begin{aligned}
D
={}&2\sum_i\lambda_i(f_i-f_n)
+2\sum_i\lambda_i\langle g_i,x_0-x_i\rangle
-\|G\|^2+\sum_i\lambda_i\|g_i\|^2.
\end{aligned}
\]

The physical GD recursion supplies

\[
2\sum_{i=0}^{n-1}h_i\langle g_i,x_0-x_i\rangle
=\|H\|^2-\sum_{i=0}^{n-1}h_i^2\|g_i\|^2.
\]

The terminal part is 2 omega <q,H>. These terms cancel the corresponding terms in ||H+omega q||^2, leaving exactly

\[
D=2\sum_{i=0}^{n-1}h_i(f_i-f_n)
-\sum_{i=0}^{n-1}h_i(h_i-1)\|g_i\|^2
-\omega(\omega-1)\|q\|^2
=E_\Gamma+[\Gamma-\omega(\omega-1)]\|q\|^2.
\]

Thus the dominance identity holds for the originally selected minimizer and its original radius. No projection, alternate minimizer, or radius comparison enters.

Since omega = (15C+2)/17, direct multiplication gives

\[
\Gamma-\omega(\omega-1)
=\left(\frac{64}{289}-63\epsilon\right)C^2
-\frac{94}{289}C+\frac{30}{289}.
\]

The exact comparisons

\[
\frac{64}{289}-\frac15=\frac{31}{1445}>\frac{63}{6144},\qquad
\frac{94}{289}<\frac13,
\]

give

\[
\Gamma-\omega(\omega-1)>\frac15C^2-\frac13C>0,
\]

using C > 12/5. Therefore D >= 0. Returning to its original definition yields

\[
\|x_0-x_\star\|^2
\ge 2B(f_n-f_\star)+\sum_i\lambda_iQ_{\star i}
+\|z-G\|^2
\ge2B(f_n-f_\star).
\]

For any nonzero original initial distance, division proves source (2) with the correct factor 2. The argument remains valid for zero terminal or intermediate gradients and for nonunique minimizers.

## 11. Scope and recommended source-only clarifications

The audited theorem is uniform over all finite dimensions, all convex differentiable 1-smooth functions with an attained minimum, all originally selected minimizers, and all actual histories satisfying the stated constant-gradient right-block condition. It requires no zero endpoint rows.

It does not bound the supremum W(H_J) over histories with variable gradients in a right block. It therefore supplies neither an unrestricted schedule certificate nor a negative answer to the original profile-matching problem. The source correctly states this boundary.

Recommended clarifications, without changing the mathematics:

- State J is a positive integer and write physical query indices 0,...,n with n = 2^J - 1.
- State 2 <= l <= J-1 for (7)--(12), and l >= 2 for (9).
- Define E_J(theta) and E_Gamma explicitly as above.
- Avoid reusing w_l for a query and an energy, and u_i for conjugate values and final weights.
- Replace the sentence about arbitrary nonnegative slack values by "No zero-row or additional upper-bound assumption is imposed on the actual feasible endpoint slacks."

**Final audit status:** main claims (1) and (2) independently MANUALLY ACCEPTED in their stated restricted trajectory scope for both recorded source versions. The revised source also explicitly defines and supports its E_J(49/100) corollary and scopes (8)--(12) to l >= 2. Further symbol and wording refinements above are optional presentation improvements. No source modification by this auditor and no verifier acceptance.
