# An all-depth affine-right bound with arbitrary endpoint-row slack

**UNVERIFIED analytical draft, 2026-10-17.** This removes the zero-endpoint-row assumption from the R16 affine-right theorem. The right-child constant-gradient assumption remains essential to this proof. The original unrestricted minimax problem is still OPEN.

## 1. Statement and fixed parameters

Fix m>=1536, e=1/(4m), beta=1-e, c=(1+sqrt(2))(1+e), and a=beta/c. Use the same parameters in every descendant:
\[
H_0=(),\quad H_{j+1}=(H_j,1+k_j,H_j),\quad
k_j=ac^j,\quad C_j=1+\sum H_j,\quad r_j=k_j/C_j.
\]
For a fixed depth J>=1, run H_J on any finite-dimensional convex differentiable 1-smooth function with an attained minimum.

The only additional trajectory hypothesis is:

For every 1<=l<J, all queries in the right H_l block of the prefix H_(l+1), including the first and terminal queries, have one constant gradient p_(l+1).

No interpolation row is assumed zero. Define the left-spine endpoints
\[
v_l=x_{2^l-1},\qquad p_l=\nabla f(v_l),\qquad d_l=p_l-p_{l+1}.
\]
The standard history residual at depth J is
\[
E_J^{\rm std}=
2\sum_i h_i(f_i-f_e)-\sum_i h_i(h_i-1)\|g_i\|^2
-(C_J^2-C_J)\|p_J\|^2.
\]
The conclusion is
\[
\boxed{E_J^{\rm std}\ge-63e\,C_J^2\|p_J\|^2.}
\tag{1}
\]
In particular E_J(49/100)>=0. Moreover, for every originally selected minimizer x_star and every nonzero initial distance,
\[
\boxed{\frac{2(f_e-f_\star)}{\|x_0-x_\star\|^2}
\le\frac1{1+(32/17)(C_J-1)}.}
\tag{2}
\]
The statement permits arbitrary finite dimension and arbitrary endpoint-row slack. It is not a bound on W(H_J), which also includes nonconstant right children.

For clarity, define the coefficient-parametrized residual and the normalized version by
\[
E_{J,\Gamma}:=
2\sum_i h_i(f_i-f_e)-\sum_i h_i(h_i-1)\|g_i\|^2-\Gamma\|p_J\|^2,
\qquad E_J(\theta):=E_{J,\theta C_J^2-C_J}.
\]
Thus \(E_J^{\rm std}=E_{J,C_J^2-C_J}\). In Section 5, \(E_\Gamma\) abbreviates \(E_{J,\Gamma}\).

The finite parameter bounds used below are
\[
C_1>12/5,\quad C_l>23/4\ (l\ge2),\quad
2/5<r_l<5/12,\quad
12/5<C_l/C_{l-1}<5/2\ (l\ge2).
\tag{3}
\]
For completeness, solving C_(l+1)=2C_l+k_l gives
\[
C_l=c^l\frac{1+\zeta(2/c)^l}{1+\zeta},\quad
r_l=\frac{c-2}{1+\zeta(2/c)^l},\quad
\zeta=\frac{(5+2\sqrt2)e+(1+\sqrt2)^2e^2}{1-e}<9e.
\]
Here a>2/5, C_l<=c^l and c<29/12 imply (3); beta>99/100 gives C_2>24/5+99/100>23/4. The source of these same bounds is R16 normal_geometry, Section 1.

## 2. Original rows and the exact nonlocal identity

Use
\[
Q_{ij}=2(f_i-f_j)-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2\ge0,
\]
\[
y_i=x_i-g_i,\qquad u_i=\langle g_i,x_i\rangle-f_i-\tfrac12\|g_i\|^2.
\]
Then
\[
Q_{ij}/2=u_j-u_i-\langle y_i,g_j-g_i\rangle.
\tag{4}
\]
Equal gradients imply equal u values, by both directed rows.

For l>=1 set
\[
F_l=Q_{v_l,v_{l+1}}/2,\quad
R_l=Q_{v_{l+1},v_l}/2,\quad T_l=F_l+R_l.
\]
These quantities may be any nonnegative values. Since the right child has gradient p_(l+1) throughout, its displacement is (C_l-1)p_(l+1). Consequently
\[
T_l=\langle k_l p_l+C_l p_{l+1},d_l\rangle,
\]
\[
\langle p_l,d_l\rangle
=\frac{\|d_l\|^2}{1+r_l}+\frac{T_l}{C_l(1+r_l)}.
\tag{5}
\]
At l>=2 the preceding endpoint similarly gives
\[
\langle p_l,d_{l-1}\rangle
=-\frac{r_{l-1}}{1+r_{l-1}}\|d_{l-1}\|^2
+\frac{T_{l-1}}{C_{l-1}(1+r_{l-1})}.
\tag{6}
\]

Let w_l be the first actual query after the root step. Its gradient is p_(l+1) and
\[
y_{w_l}=y_{v_l}-k_l p_l-p_{l+1}.
\]
The nonlocal original row from w_l to the older query v_(l-1), together with (4), yields
\[
\frac12Q_{w_l,v_{l-1}}
=\langle k_l p_l+p_{l+1},p_{l-1}-p_{l+1}\rangle
+R_{l-1}-F_l.
\tag{7}
\]

Define
\[
A_l=\frac{r_l(C_l-1)}{1+r_l},\quad
B_l=\frac{(k_l+1)r_{l-1}}{1+r_{l-1}},
\]
\[
\alpha_l=\frac{k_l+1}{C_l+k_l},\qquad
\beta_l=\frac{k_l+1}{C_{l-1}+k_{l-1}}.
\]
The symbols B_l and beta_l here are local coefficients, not the benchmark or the hierarchy beta. Substituting (5)--(6) into (7) gives the exact identity
\[
\begin{aligned}
N_l:={}&A_l\|d_l\|^2-B_l\|d_{l-1}\|^2
-\langle d_l,d_{l-1}\rangle\\
={}&\tfrac12Q_{w_l,v_{l-1}}+(1-\alpha_l)F_l
-\alpha_lR_l-\beta_lF_{l-1}-(1+\beta_l)R_{l-1}.
\end{aligned}
\tag{8}
\]
This displays every endpoint-row debt; none has been declared zero.

## 3. Paying the endpoint-row debts

For l>=2, on (3),
\[
B_l\ge(4/35)C_l+2/7,\qquad
A_l\le(5/17)(C_l-1),
\]
\[
4B_l-A_l-2>\frac{891}{2380}>0,\qquad
0<\alpha_l<1/2,\qquad 0<\beta_l<21/20.
\tag{9}
\]
For the alpha bound, (1-r_l)C_l>2. For beta, the numerator is at most 145/144+5/12 and the denominator at least 7/5, giving 1025/1008<21/20.

For arbitrary vectors d,e, the following is an exact completed-square identity:
\[
(B-\tfrac14)(4\|d\|^2-\|e\|^2)
=A\|d\|^2-B\|e\|^2-\langle d,e\rangle
+(4B-A-2)\|d\|^2+\|d+e/2\|^2.
\tag{10}
\]
Equations (8)--(10) imply
\[
\|d_{l-1}\|^2
\le4\|d_l\|^2+
\frac{\alpha_lR_l+\beta_lF_{l-1}+(1+\beta_l)R_{l-1}}
{B_l-1/4}.
\tag{11}
\]
This is valid including zero gradients and zero d vectors.
The ranges of (8)--(12) are l>=2; no bound alpha_l<1/2 is asserted at l=1.

Put w_l=C_l^2||d_l||^2. Because
\[
\frac{C_{l-1}^2}{B_l-1/4}
<\frac{875}{576}C_l<2C_l,
\]
(11) gives
\[
w_{l-1}\le\frac{25}{36}w_l+L_l,
\]
\[
L_l\le C_lR_l+\frac{21}{4}C_{l-1}F_{l-1}
+\frac{41}{4}C_{l-1}R_{l-1}.
\tag{12}
\]
Let W=sum_(l=1)^(J-1) w_l. Summing this recurrence, for J>=2, gives
\[
W\le\frac{36}{11}\left[w_{J-1}+\sum_{l=2}^{J-1}L_l\right]
\le4\left[w_{J-1}+\sum_{l=2}^{J-1}L_l\right].
\tag{13}
\]
For J=2 the sum is empty and the same bound holds.

To control the last d, put q=p_J in (5):
\[
r\|d\|^2+(1+r)\langle q,d\rangle=T/C.
\]
Young's inequality and r>2/5 yield
\[
\|d\|^2\le\frac5C T+\frac{49}{4}\|q\|^2.
\]
Using C_(J-1)/C_J<5/12 in (13), and summing (12), therefore gives
\[
\boxed{
W\le9C_J^2\|q\|^2+
41\sum_{l=1}^{J-1}C_lF_l+
65\sum_{l=1}^{J-1}C_lR_l.}
\tag{14}
\]
For example, the terminal contribution before rounding is 1225 C_J^2||q||^2/144<9C_J^2||q||^2; its row contribution is at most 20 C_(J-1)(F_(J-1)+R_(J-1)). The recurrence contributes at most 21 sum C_lF_l+45 sum C_lR_l. This accounts for every constant in (14).

## 4. The history identity pays all those rows

For a constant-gradient right child, its standard history residual is zero. Direct splitting of the physical history, or substitution of both endpoint rows, gives
\[
\boxed{
E_{l+1}^{\rm std}
=E_l^{\rm std}-(r_l^2+2r_l-1)C_l^2\|d_l\|^2
+2C_{l+1}F_l+2C_lR_l.}
\tag{15}
\]
This equality does not require endpoint-row vanishing. One check is to use
\[
F_l=f(v_l)-f(v_{l+1})-\tfrac12\|p_l\|^2
-k_l\langle p_l,p_{l+1}\rangle
-(C_l-\tfrac12)\|p_{l+1}\|^2
\]
and T_l in (5).

The actual leaf h=1+a<sqrt(2) has
\[
E_1^{\rm std}=(h+1)Q_{01}+Q_{10}+(2-h^2)\|g_0-g_1\|^2\ge0.
\]
Also, uniformly in l,
\[
r_l^2+2r_l-1<c^2-2c-1
=(4+2\sqrt2)e+(1+\sqrt2)^2e^2<7e.
\tag{16}
\]
Negative early coefficients only help. Combining (14)--(16) proves the stronger displayed lower estimate
\[
\begin{aligned}
E_J^{\rm std}\ge{}&-63e C_J^2\|q\|^2\\
&+\sum_l(2C_{l+1}-287e C_l)F_l
+\sum_l(2-455e)C_lR_l.
\end{aligned}
\tag{17}
\]
All row coefficients here are nonnegative for e<=1/6144. This proves (1), including J=1 separately by the leaf identity, and
\[
E_J(49/100)\ge(51/100-63e)C_J^2\|q\|^2\ge0.
\]

## 5. The actual objective and selected minimizer

Set C=C_J, S=C-1 and Gamma=(1-63e)C^2-C. Use physical weights h and terminal weight omega=1+(15/17)S, of total B=1+(32/17)S. For any originally selected minimizer, the exact dominance identity is
\[
D=E_\Gamma+[\Gamma-\omega(\omega-1)]\|q\|^2,
\]
\[
D=\|x_0-x_\star\|^2-\sum_i u_iQ_{\star i}
-2B(f_e-f_\star)
-\left\|x_0-x_\star-\sum_i u_i g_i\right\|^2.
\]
Here u_i denotes these fixed weights only in this final display, not the conjugate values in (4). Equation (1) gives E_Gamma>=0. Moreover
\[
\Gamma-\omega(\omega-1)
=\left(\frac{64}{289}-63e\right)C^2-\frac{94}{289}C+\frac{30}{289}
>\frac15C^2-\frac13C>0.
\]
For the first inequality, 64/289-1/5=31/1445>63/6144 and 94/289<1/3. The second uses C>12/5. Dropping only nonnegative star rows and the squared norm gives (2).

This is an all-depth theorem for the stated actual-history structure. The missing extension is to variable right gradients; then extra displacement and function-value terms enter (5), (7), and (15), and must be paid rather than discarded.
