# The complementary constant-normal mechanism

**UNVERIFIED analytical result, 2026-10-17. No independent audit or Danus acceptance is claimed.** This is a complementary structural result, not the unrestricted history inequality. The same-enclosing-m hierarchy and all notation are as in AFFINE_RIGHT_WITH_SLACK.md.

## 1. An exact reserve identity for arbitrary right histories

At one join let the child capacity be C, the bridge be 1+k, r=k/C, R=2+r, and the parent capacity be RC. Let p be the gradient immediately before the bridge and q the final gradient. For the right child put
\[
G=\sum_{i\in R_{\rm child}}h_i g_i,\quad Z=G+q,\quad
D=kp+Z=(v-p)-(y-q),
\]
\[
A_v=\sum_{i\in R_{\rm child}}h_iQ_{vi},\qquad
A_y=\sum_{i\in R_{\rm child}}h_iQ_{yi},
\]
\[
\ell=\frac{1+r}{1-r},\quad B_0=\frac{3+r}{1-r},\quad
\delta=B_0r^2-1.
\]
Here y in the subscripts is the final physical point, not the normal coordinate. Write E_L,E_R,E_P for the standard history residuals.

Two exact identities, obtained by expanding the original interpolation rows and physical displacements, are
\[
E_P=E_L+B_0E_R+\ell(A_v+A_y+Q_{vy}+kQ_{yv})
+\delta C^2(\|q\|^2-\|p\|^2),
\tag{1}
\]
and, for any scalar b,
\[
\begin{aligned}
&(b+b/r)E_R+bA_v+(b/r)A_y+bQ_{vy}+bC Q_{yv}\\
&\qquad=bC^2r(1+r)\|p\|^2-b(1+r)C^2/r\,\|q\|^2
+b(1-r)/r\,\|D\|^2.
\end{aligned}
\tag{2}
\]
These are the general identities recorded in R16 terminal_reserve, equations (10) and (16); neither assumes the sign of E_R.

There is a useful exact simplification:
\[
\delta=\ell(r^2+2r-1),\qquad
\delta(1-r^2)=[r(2+r)]^2-1.
\tag{3}
\]
Choose a fixed reserve rho and put b=(rho+delta)/(r(1+r)). Subtracting the row combination in (2) from (1) gives
\[
\begin{aligned}
E_P+\rho R^2C^2\|q\|^2
={}&E_L+\rho C^2\|p\|^2\\
&+\frac{1-\rho}{r^2}
\left\{E_R-\big([rR]^2-1\big)C^2\|q\|^2\right\}\\
&+(\ell-b)(A_v+Q_{vy})+(\ell-b/r)A_y\\
&+C(\ell r-b)Q_{yv}
+b(1-r)/r\,\|D\|^2.
\end{aligned}
\tag{4}
\]
All rows and the square on the last two lines have nonnegative coefficients provided
\[
0\le\rho\le1,\qquad
\rho+\delta\ge0,\qquad
\rho\le1-r^2(r+2).
\tag{5}
\]
The last condition is exactly b<=ell*r; it also pays the A_y coefficient. Formula (4) applies to arbitrary actual right histories. Its brace has NOT been shown nonnegative in that generality.

## 2. Constant normal coordinates give an exact surplus

Suppose every right-child query, including its first and terminal queries, has the same normal coordinate
\[
x_i-g_i=z.
\tag{6}
\]
The physical updates then imply
\[
g_{i+1}=(1-h_i)g_i.
\]
If the right child is H_l, its odd length and the hierarchy give
\[
q=-\tau_l t,\qquad
\tau_l=\prod_{i\in H_l}(h_i-1)
=\frac{\beta^{2^l-1}}{c^l}>0,
\tag{7}
\]
where t is its first gradient. This product follows from tau_0=1 and tau_(l+1)=k_l tau_l^2, with k_l=beta*c^(l-1).

Both directed interpolation rows between points with the same normal vanish: writing u_i=<g_i,x_i>-f_i-||g_i||^2/2, their sum is zero, and each row is nonnegative. Thus A_y=0. Also G=t-q, so Z=t. The general right-history identity E_R+A_y=||Z||^2-C_l^2||q||^2 now gives exactly
\[
E_R=(\tau_l^{-2}-C_l^2)\|q\|^2.
\tag{8}
\]
It follows that the brace in (4) is
\[
\left[\tau_l^{-2}-\{C_l r_l(2+r_l)\}^2\right]\|q\|^2\ge0,
\tag{9}
\]
because
\[
\tau_l C_l r_l(2+r_l)
=\beta^{2^l}\frac{2+r_l}{c}<1.
\tag{10}
\]
The strict inequality uses 0<beta<1 and r_l<c-2. In the zero-gradient case the same conclusion follows directly; there is no division by a gradient norm.

Thus this physical right-child behavior supplies precisely the surplus that would be lost if E_R were replaced by only a weak terminal lower bound.

## 3. All-depth constant-normal-right theorem

Fix m>=1536, e=1/(4m), beta=1-e, c=(1+sqrt(2))(1+e). Suppose every right H_l child along the left spine of H_J satisfies (6). The left leaf is otherwise arbitrary. Then
\[
\boxed{
E_J^{\rm std}+3e\,C_J^2\|p_J\|^2
\ge3e\,\|g_0\|^2.}
\tag{11}
\]

Here are the parameter checks needed to iterate (4) with rho=3e.
The exact hierarchy formula shows r_l increases with l. Since C_1=2+beta/c<1+sqrt(2),
\[
r_l\ge r_1=\beta/C_1>(\sqrt2-1)\beta.
\]
Put r_*=sqrt(2)-1. If delta_l<0, then r_l<r_*, ell_l<1+sqrt(2), and
\[
r_l^2+2r_l-1
\ge-2r_*(1+r_*)e.
\]
Consequently delta_l>-2sqrt(2)e>-3e. If delta_l>=0, the required rho+delta_l>=0 is immediate.
Further, r_l<5/12 gives
\[
1-r_l^2(r_l+2)>\frac{1003}{1728}>\frac12,
\qquad 3e\le1/2048.
\]
Thus every coefficient in (4) is nonnegative.

On the actual one-step leaf h=1+a<sqrt(2), the exact leaf reserve identity from R16 terminal_reserve, equations (4)--(7), gives
\[
E_1^{\rm std}+\rho C_1^2\|g_1\|^2\ge\rho\|g_0\|^2
\quad(0\le\rho\le2-\sqrt2).
\tag{12}
\]
In particular rho=3e is permitted. Apply (4), (9) at each left-spine join and then (12). This proves (11) for every depth.

As with the affine-right theorem, choosing Gamma=(1-3e)C_J^2-C_J in the original star-row dominance identity yields
\[
\frac{2(f_e-f_\star)}{\|x_0-x_\star\|^2}
\le\frac1{1+(32/17)(C_J-1)}
\tag{13}
\]
for every originally selected minimizer with nonzero original distance. The final scalar remainder is even larger than in AFFINE_RIGHT_WITH_SLACK.md, Section 5.

## 4. What is still missing

Equations (4) and (10) identify a complementary mechanism to the affine-right nonlocal estimate. Constant gradients are controlled by nonlocal original rows; constant normals produce a positive right-history surplus. Neither hypothesis covers a general right child, and no decomposition of all smooth convex trajectories into these two classes is asserted.

In particular, alternating arbitrary normal and gradient changes cannot be replaced by a convex mixture of the two proved cases without a new proof. A uniform payment for the brace in (4), together with its correlations with earlier left-spine points, is still needed for the original unrestricted target.
