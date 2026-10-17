# R17 variable-right investigation: a complete mixed-right theorem and a uniform normal-moment charge

**UNVERIFIED manual analytical draft. The unrestricted same-parameter history assertion and the original exact-profile minimax problem remain OPEN.**

This packet gives two complete, explicitly scoped derivations. First, the affine-right and constant-normal-right mechanisms can be switched arbitrarily along the left spine, with all endpoint-row slack retained. The resulting all-depth reserve is less than 4/25, and the desired original-radius objective bound follows on this mixed class. Second, at exact Silver parameters a weighted normal moment has a uniform full-class charge, unlike the unweighted displacement candidate excluded in R16. The actual-parameter extension of that moment charge is not supplied.

The general cyclic-row identities are recorded before the scoped theorem, so the remaining variable-right payment is explicit. Two actual growing-depth tests rule out particular shortcuts for paying it. They are not counterexamples to the requested history inequality.

## 1. Scope, parameters, and original rows

Fix one enclosing integer throughout every descendant:
\[
m\ge1536,\quad e=(4m)^{-1},\quad \beta=1-e,\quad
c=(1+\sqrt2)(1+e),\quad a=\beta/c,
\]
\[
H_0=(),\qquad H_{j+1}=(H_j,1+k_j,H_j),\qquad
k_j=ac^j,\qquad C_j=1+\sum H_j.
\]
Write \(r_j=k_j/C_j\), so \(C_{j+1}=(2+r_j)C_j\). For an actual history of a single finite-dimensional convex differentiable 1-smooth function, put
\[
g_i=\nabla f(x_i),\quad y_i=x_i-g_i,\quad
u_i=\langle g_i,x_i\rangle-f_i-\tfrac12\|g_i\|^2,
\]
\[
Q_{ij}=2(f_i-f_j)-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2
=2\{u_j-u_i-\langle y_i,g_j-g_i\rangle\}\ge0.
\tag{1.1}
\]
For a word of capacity C and terminal gradient q, define
\[
E^{\rm std}=2\sum_i h_i(f_i-f_e)-\sum_i h_i(h_i-1)\|g_i\|^2
-(C^2-C)\|q\|^2,
\quad F(\rho)=E^{\rm std}+\rho C^2\|q\|^2.
\tag{1.2}
\]
Thus the requested history expression is \(E_j(49/100)=F_j(51/100)\).

The uniform bounds inherited from the closed capacity formula are
\[
C_1>12/5,\quad C_j>23/4\ (j\ge2),\quad
2/5<r_j<5/12,\quad 12/5<C_{j+1}/C_j<5/2.
\tag{1.3}
\]
In particular,
\[
C_j=c^j\frac{1+\zeta(2/c)^j}{1+\zeta},\qquad
r_j=\frac{c-2}{1+\zeta(2/c)^j},\qquad 0<\zeta<9e,
\tag{1.4}
\]
so the ratios increase. Put \(r_*=\sqrt2-1\), \(c_*=1/r_*\). Direct identities give
\[
c_*\beta-C_1=e\left[-c_*+\frac{2r_*}{1+e}\right]<0,
\]
\[
c_*\beta c-C_2=e\left[1+\frac{4r_*}{1+e}-c_*^2e\right]>0.
\tag{1.5}
\]
The second sign uses \(c_*^2<6\) and \(6e<1\). Consequently \(r_1<r_*<r_j\) for every \(j\ge2\).

## 2. Exact variable-right identities and the unresolved payment

At a join, use left endpoint v with gradient p, first right query \(w=v-(1+k)p\), and terminal query z with gradient q. Let \(C\) be the right capacity, \(S=C-1\), and
\[
G=\sum_R h_i g_i=w-z,\quad Z=G+q,\quad
D=kp+Z=y_v-y_z,\quad V=Z-Cq.
\]
For an older actual query a with gradient \(p_a\), the first-right cyclic identity is
\[
\langle kp+g_w,p_a-q\rangle
=\tfrac12(Q_{wa}-Q_{wz}-Q_{va}+Q_{vz}).
\tag{2.1}
\]
This follows immediately by cancelling the four u values in (1.1). In particular the forward row \(Q_{wz}\) has a negative sign and must be paid.

There is another routing which uses the entire right child. For each right query i, define
\[
N_i=y_v-y_i,\quad M_i=y_i-y_z.
\]
The exact path identity is
\[
\langle N_i,p_a-q\rangle+\langle M_i,g_i-q\rangle
=\tfrac12(Q_{vz}+Q_{zi}+Q_{ia}-Q_{va}).
\tag{2.2}
\]
It corresponds to replacing the edge \(v\to a\) by the path \(v\to z\to i\to a\); every function-value coefficient is preserved. With the physical weights put
\[
\mathcal M_R=\sum_Rh_i(y_i-y_z),\quad
A_z=\sum_Rh_iQ_{zi},\quad B_z=\sum_Rh_iQ_{iz}.
\]
Summation of (2.2) gives
\[
\begin{aligned}
\mathcal C_R
&=(S D-\mathcal M_R)\cdot(p_a-q)+\tfrac12(A_z+B_z)\\
&=\tfrac12\left[S(Q_{vz}-Q_{va})+A_z+\sum_Rh_iQ_{ia}\right].
\end{aligned}
\tag{2.3}
\]
Its complete gradient-space form is
\[
\mathcal C_R=S D\cdot(p_a-q)-\mathcal M_R\cdot p_a
+\tfrac12\|Z\|^2-\tfrac12\|q\|^2
+\tfrac12\sum_Rh_i(h_i-2)\|g_i\|^2.
\tag{2.4}
\]
Indeed, \(M_i=\sum_{t\ge i}h_tg_t+q-g_i\), so
\[
\sum_Rh_i M_i\cdot g_i
=\tfrac12\|Z\|^2-\tfrac12\|q\|^2
+\tfrac12\sum_Rh_i(h_i-2)\|g_i\|^2.
\]

A coefficient of order e on (2.3) consumes only order \(eC\) of the old reverse row and order e of the full right-row sums. This avoids the particular first-query obstruction in Section 6. It does not make (2.4) nonnegative: the normal moment and the signed gradient action must be handled jointly.

For reference the exact right-displacement payment is
\[
\|Z\|^2=C^2\|q\|^2+E_R^{\rm std}+A_z,
\]
\[
\|V\|^2\le2E_R^{\rm std}+2A_z+4C^2\|q\|^2.
\tag{2.5}
\]
The second difference is \(\|Z+Cq\|^2\ge0\). The signed \(E_R^{\rm std}\) in (2.5) has not been dropped.

The general fixed-reserve identity from the parent's NORMAL_RIGHT_RESERVE.md is also retained. Set
\[
\ell=\frac{1+r}{1-r},\quad B=\frac{3+r}{1-r},\quad
\delta=Br^2-1,\quad \gamma=[r(2+r)]^2,
\quad b=\frac{\rho+\delta}{r(1+r)}.
\]
Then
\[
\begin{aligned}
F_P(\rho)={}&F_L(\rho)+\frac{1-\rho}{r^2}
\{E_R^{\rm std}-(\gamma-1)C^2\|q\|^2\}\\
&+(\ell-b)(A_v+Q_{vz})+(\ell-b/r)A_z
+C(\ell r-b)Q_{zv}+b(1-r)\|D\|^2/r.
\end{aligned}
\tag{2.6}
\]
Its displayed row and square coefficients are nonnegative for \(3e\le\rho\le51/100\). The unbounded-history problem is precisely to pay the brace and its earlier-query correlations for a general varying right child. Neither (2.3) nor (2.5) alone does so.

## 3. Complete theorem for arbitrary switches between the two mechanisms

### 3.1 Structural hypothesis and conclusion

Run an actual \(H_J\) trajectory on one function as in Section 1, with an attained minimum. For every join level \(1\le l<J\) along its left spine, assume that its entire right \(H_l\) block, including the first and terminal queries, satisfies at least one of:

* **G:** its gradients \(g_i\) are constant;
* **N:** its normal coordinates \(y_i=x_i-g_i\) are constant.

The choice may change arbitrarily between levels. No endpoint interpolation row is assumed zero. The remaining left leaf is arbitrary. Define
\[
L=\lceil\log_2(4m)\rceil,\qquad
\rho_m=(3+63L)e.
\tag{3.1}
\]
Then for every finite depth \(J\ge1\), every allowed dimension, and every such actual trajectory,
\[
\boxed{E_J^{\rm std}\ge-\rho_m C_J^2\|g_e\|^2,
\qquad \rho_m<4/25.}
\tag{3.2}
\]
Consequently \(E_J(49/100)\ge0\). The bound is simultaneous in all depths; in particular it covers every \(1\le J<m\).

### 3.2 An affine run costs 63e, independently of its length

Let levels \(A,A+1,\ldots,B\), with \(A\ge2\), form a consecutive G run. Write
\[
p_l=g(v_l),\quad d_l=p_l-p_{l+1},\quad
F_l=Q_{v_l,v_{l+1}}/2,\quad R_l=Q_{v_{l+1},v_l}/2,
\quad z_l=C_l p_l.
\]
The parent's affine-right derivation uses only the joins within the run. Thus its weighted-difference estimate and exact history split hold with the starting residual retained:
\[
\sum_{l=A}^{B}C_l^2\|d_l\|^2
\le9\|z_{B+1}\|^2+41\sum_{l=A}^{B}C_lF_l
+65\sum_{l=A}^{B}C_lR_l,
\tag{3.3}
\]
\[
\begin{aligned}
E_{B+1}^{\rm std}\ge{}&E_A^{\rm std}-63e\|z_{B+1}\|^2\\
&+\sum_{l=A}^{B}(2C_{l+1}-287eC_l)F_l
+\sum_{l=A}^{B}(2-455e)C_lR_l.
\end{aligned}
\tag{3.4}
\]
For clarity, the nonlocal recurrence behind (3.3) is
\[
w_{l-1}\le(25/36)w_l+L_l,\qquad w_l=C_l^2\|d_l\|^2,
\]
\[
L_l\le C_lR_l+(21/4)C_{l-1}F_{l-1}
+(41/4)C_{l-1}R_{l-1}.
\]
It is used only for \(A+1\le l\le B\), where both adjacent levels are G. Its terminal bound and geometric sum give (3.3), including the single-level run. The exact split being summed is
\[
E_{l+1}^{\rm std}=E_l^{\rm std}
-(r_l^2+2r_l-1)C_l^2\|d_l\|^2
+2C_{l+1}F_l+2C_lR_l,
\]
and \(r_l^2+2r_l-1<7e\). This explains the constants in (3.4).

The run can also transport an incoming terminal reserve. On a G block the exact port identity reduces to
\[
k_l^2\|p_l\|^2+\frac{1-r_l}{1+r_l}\|k_lp_l+C_lp_{l+1}\|^2
=C_l^2\|p_{l+1}\|^2+rac{2k_lC_l}{C_l+k_l}(F_l+R_l).
\tag{3.5}
\]
After dropping its nonnegative square,
\[
\|z_l\|^2
\le\frac{\|z_{l+1}\|^2}{[r_l(2+r_l)]^2}
+\frac{2C_l}{r_l(1+r_l)}(F_l+R_l).
\]
For every level in this run, (1.5) gives \(r_l>r_*\), and \(2/[r_l(1+r_l)]<25/7\). Iteration therefore yields
\[
\|z_A\|^2\le\|z_{B+1}\|^2
+(25/7)\sum_{l=A}^{B}C_l(F_l+R_l).
\tag{3.6}
\]
Suppose \(E_A^{\rm std}+\rho\|z_A\|^2\ge0\) with \(0\le\rho\le51/100\). Combining (3.4) and (3.6) gives
\[
\boxed{E_{B+1}^{\rm std}+(\rho+63e)\|z_{B+1}\|^2\ge0.}
\tag{3.7}
\]
Every remaining row coefficient is nonnegative. The smaller one is bounded below by
\[
2-455e-(25/7)\rho
\ge 5/28-455/6144>0.
\tag{3.8}
\]
The forward coefficient is larger, since \(2C_{l+1}/C_l>24/5\) and \(287e<455e\).

### 3.3 A normal block preserves the reserve and eventually resets it

On an N right child of depth l, its actual gradients obey \(g_{i+1}=(1-h_i)g_i\). Thus, with t its first gradient,
\[
q=-\tau_l t,\qquad \tau_l=\beta^{2^l-1}/c^l,
\qquad E_R^{\rm std}=(\tau_l^{-2}-C_l^2)\|q\|^2.
\tag{3.9}
\]
These identities do not divide by a gradient. The right endpoint rows vanish because the right normals are equal, and \(G+q=t\).

Allow different incoming and outgoing reserves \(\rho_L,\rho_P\), with \(3e\le\rho_L\le51/100\). Equation (2.6), after adding \((\rho_P-\rho_L)C_{l+1}^2\|q\|^2\), gives exactly
\[
\begin{aligned}
F_{l+1}(\rho_P)={}&F_l(\rho_L)\\
&+\frac{C_l^2}{r_l^2}
\left\{\frac{1-\rho_L}{(\tau_lC_l)^2}
-(1-\rho_P)[r_l(2+r_l)]^2\right\}\|q\|^2
+\mathcal P_l,
\end{aligned}
\tag{3.10}
\]
where \(\mathcal P_l\) is exactly the nonnegative row-and-square combination on the last line of (2.6), evaluated at \(\rho_L\).

For \(\rho_P=\rho_L\) the brace is nonnegative at every level, since
\[
\tau_l C_l r_l(2+r_l)=\beta^{2^l}\frac{2+r_l}{c}<1.
\tag{3.11}
\]
For \(l\ge L\), an N root can instead set \(\rho_P=3e\), regardless of its incoming \(\rho_L\le51/100\). Indeed \(C_l\le c^l\), and \(2^l-1\ge4m-1\), so
\[
\tau_lC_l\le\beta^{2^l-1}
\le\frac1{1+(2^l-1)e}
\le\frac1{2-e}<\frac35.
\tag{3.12}
\]
The middle inequality follows from \((1-e)^{-N}\ge1+Ne\). Hence
\[
\frac{1-\rho_L}{(\tau_lC_l)^2}>\frac{49}{36}
>\left(\frac{145}{144}\right)^2
>[r_l(2+r_l)]^2(1-3e).
\tag{3.13}
\]
The reset in (3.10) is therefore paid by the actual right surplus.

### 3.4 Initialization and reserve count

The actual leaf has \(E_1^{\rm std}\ge0\). At join level 1, a G block has \(r_1^2+2r_1-1<0\), so the exact affine split gives \(E_2^{\rm std}\ge E_1^{\rm std}\ge0\). An N block gives \(F_2(3e)\ge F_1(3e)\ge0\) by (3.10)--(3.11) and the valid leaf reserve. Thus, in either case, depth 2 starts with reserve \(3e\).

From level 2 onward, process maximal G runs using (3.7) and N roots using (3.10). N roots below L preserve the reserve; N roots at or above L reset it to \(3e\). Before the first reset there are at most L maximal G runs, even if the final one extends far beyond L. After any reset, at most one G run occurs before the next reset. Therefore every reserve used is at most \((3+63L)e\).

This upper bound is less than 4/25, so all uses of the provisional bound \(\rho\le51/100\) are justified by induction. To check it without a decimal logarithm, let \(t=\lfloor m/100\rfloor\ge15\). The inequality \(2^t\ge400(t+1)\) holds at 15 and is preserved by incrementing t. Since \(4m<400(t+1)\), it follows that \(L\le t\le m/100\). Consequently
\[
\rho_m\le\frac{3}{4m}+\frac{63}{400}
\le\frac1{2048}+\frac{63}{400}<\frac4{25}.
\tag{3.14}
\]
This completes (3.2), with J=1 handled by its sharp leaf inequality.

## 4. Original-radius objective on the mixed class

Let \(C=C_J\), \(S=C-1\), and keep any originally selected minimizer \(x_\star\). Use the actual physical weights h and terminal weight
\[
\omega=1+(15/17)S,\qquad B=S+\omega=1+(32/17)S.
\]
For \(J\ge2\) put \(\Gamma=(1-\rho_m)C^2-C\). The exact star-row identity is
\[
\begin{aligned}
D={}&\|x_0-x_\star\|^2-\sum_i u_iQ_{\star i}
-2B(f_e-f_\star)
-\left\|x_0-x_\star-\sum_i u_i g_i\right\|^2\\
={}&E_\Gamma+[\Gamma-\omega(\omega-1)]\|q\|^2.
\end{aligned}
\tag{4.1}
\]
Here \(u=(h,\omega)\) denotes only the fixed certificate weights. All star rows are nonnegative for the same original minimizer. Equation (3.2) supplies \(E_\Gamma\ge0\). Moreover
\[
\begin{aligned}
\Gamma-\omega(\omega-1)
&=(64/289-\rho_m)C^2-(94/289)C+30/289\\
&>(3/50)C^2-C/3>0,
\end{aligned}
\tag{4.2}
\]
because \(64/289-4/25>3/50\), \(94/289<1/3\), and \(C\ge C_2>23/4>50/9\). At J=1 use \(\rho=0\) and the sharp leaf; its scalar remainder is positive since \(C_1>12/5\).

Dropping only nonnegative quantities in (4.1) gives
\[
\boxed{\frac{2(f_e-f_\star)}{\|x_0-x_\star\|^2}
\le\frac1{1+(32/17)(C_J-1)}.}
\tag{4.3}
\]
The initial distance is assumed nonzero, as in the original problem. This conclusion allows arbitrary switches between G and N, arbitrary dimension, and any valid originally selected minimizer. It is not a bound on the unrestricted supremum \(\mathcal W(H_J)\).

## 5. A uniform full-class normal-moment charge at exact Silver

This section changes parameters explicitly to the exact Silver hierarchy: \(r=\sqrt2-1\), \(C_j=(1+\sqrt2)^j\), \(k_j=rC_j\). It imposes no G or N structure. For an actual word define
\[
\mathcal M_j=\sum_i h_i(y_i-y_e),\qquad m_j=\mathcal M_j/C_j.
\]
For every depth, every actual convex 1-smooth history, and \(0\le\rho\le51/100\),
\[
\boxed{E_j^{\rm std}+\rho C_j^2\|g_e\|^2\ge\rho\|m_j\|^2.}
\tag{5.1}
\]
The proof gives recursive nonnegative original-row coefficients and a PSD full-vector remainder.

At a parent, \(C_P=C/r\), \(B=1/r^2\), and the exact moment recursion is
\[
\mathcal M_P=\mathcal M_L+\mathcal M_R+(1+r)CD,
\qquad m_P=r m_L+r m_R+r(1+r)D.
\tag{5.2}
\]
Allocate reserves \(\rho_L=\rho_R=\rho/2\) in the exact-Silver transfer identity. Since the required parent reserve is
\(\rho_L+(1-\rho_L)\rho_R=\rho-\rho^2/4\), one obtains
\[
F_P(\rho)\ge F_L(\rho/2)
+B(1-\rho/2)F_R(\rho/2)+\frac{\rho}{2r}\|D\|^2.
\tag{5.3}
\]
The omitted terms are the nonnegative original rows from the transfer identity and \((\rho^2/4)C_P^2\|q\|^2\). Their coefficients are nonnegative because \(\rho/2<2-\sqrt2\).

For \(\rho>0\), induction and weighted Cauchy--Schwarz give a full-vector PSD comparison. Its scalar Schur-complement test is
\[
\rho\left\{\frac{r^2}{\rho/2}
+\frac{r^2}{(\rho/2)B(1-\rho/2)}
+\frac{r^2(1+r)^2}{\rho/(2r)}\right\}
=2r^2+\frac{2r^4}{1-\rho/2}+4r^3<1.
\tag{5.4}
\]
For an elementary rational check, \(r<5/12\) and \(1-\rho/2>7/10\) make these three terms respectively less than \(7/20\), \(9/100\), and \(3/10\). Their sum is \(37/50<1\). Thus the quadratic form from the right side of (5.3) dominates \(\rho\|m_P\|^2\).

At a leaf, let \(h=\sqrt2\) and \(Y=y_0-y_1=r g_0+g_1\). The exact leaf reserve identity gives
\[
F_1(\rho)\ge(\rho/r)\|Y\|^2,
\qquad m_1=hrY.
\]
Since \(h^2r^3=2r^3<1\), this proves the base. For \(\rho=0\), (5.1) is the standard sharp Silver history theorem, obtained recursively from its nonnegative-row identity.

This moment is exactly the one in (2.3)--(2.4). The argument does not transfer (5.1) to the actual perturbed hierarchy: the reserve halving in (5.3) asks for progressively smaller child reserves, and the actual perturbation term in (2.6) does not disappear. Assuming these child inequalities would assume part of the missing result.

## 6. Two actual growing-depth obstructions to termwise payment

### 6.1 The first forward row cannot carry an extra capacity factor

Let \(h_0=1+a\) be the inherited leaf step and use the single scalar function \(f(x)=x^2/(2h_0)\). It is convex, 1-smooth, and has minimizer zero. Start any actual \(H_j\) with first gradient t. Its first step reaches zero, and every later gradient is zero. Hence, for every depth,
\[
q=0,\qquad E_j^{\rm std}=h_0\|t\|^2,
\qquad Q_{{\rm start},e}=(h_0-1)\|t\|^2.
\tag{6.1}
\]
Because \(C_j\to\infty\), no constants \(K<\infty\), \(\kappa>0\), independent of depth, can make
\[
\kappa C_jQ_{{\rm start},e}
\le K\{E_j^{\rm std}+\rho C_j^2\|q\|^2\}
\tag{6.2}
\]
valid on all actual histories. This excludes paying the \(eC_jQ_{wz}\) debt in (2.1) from a bounded multiple of the same-scale right residual and terminal reserve alone. It does not exclude a joint cancellation with the earlier history.

### 6.2 The physical squared-gradient sum is not a bounded right budget

Use the actual unit quadratic \(f(x)=x^2/2\), start with gradient 1, and retain the same enclosing parameters. Let
\[
\tau_j=\beta^{2^j-1}/c^j,\qquad
T_j=\sum_{i\in H_j}h_i^2 g_i^2.
\]
All original interpolation rows vanish, all normal coordinates are zero, and
\[
g_e=-\tau_j,\qquad E_j^{\rm std}+C_j^2g_e^2=1.
\tag{6.3}
\]
The exact physical recursion is
\[
T_{j+1}=\{1+a^2\beta^{2(2^j-1)}\}T_j+(1+k_j)^2\tau_j^2,
\qquad T_1=h_0^2.
\tag{6.4}
\]
Indeed the first right gradient is \(k_j\tau_j=a\beta^{2^j-1}\).

Take \(j=\lfloor\tfrac12\log_2m\rfloor\), which tends to infinity and remains below m. For every \(l<j\), Bernoulli's inequality gives
\[
\beta^{2(2^l-1)}\ge1-2(2^l-1)e>1/2.
\]
Since \(a>2/5\), (6.4) yields
\[
T_j\ge h_0^2(27/25)^{j-1}\longrightarrow\infty.
\tag{6.5}
\]
Thus the physical squared-gradient sum cannot be bounded by a depth-independent multiple of \(E_j^{\rm std}+C_j^2g_e^2\), even on actual same-enclosing-parameter trajectories. Any such bound on the signed action in (2.4) must retain its cancellations or introduce a further paid quantity. Equations (6.3)--(6.5) do not contradict the target history inequality: this is a normal-constant trajectory whose right surplus is favorable.

## 7. Completion boundary and receipt

The mixed theorem (3.2) and objective (4.3) are complete manual derivations conditional only on their stated G/N trajectory structure and the displayed original-row identities. The exact-Silver normal-moment theorem (5.1) is full-class but uses exact Silver parameters. Neither is asserted to be a Danus fact or an unrestricted proof for the actual hierarchy.

The full missing assertion remains: for all sufficiently large enclosing m, every \(1\le j<m\), every finite-dimensional convex 1-smooth function with an attained minimum, and every actual \(H_j\) trajectory, prove \(E_j(49/100)\ge0\), or obtain an equally sufficient full-word original-radius objective certificate. A right child with simultaneous, nonconstant gradient and normal changes is not covered by the mixed theorem. No convex-mixture reduction to G and N is assumed.

Sources read: OPERATOR.md; the original project PROBLEM.md; R17 WAVE.md; R16 normal_geometry and terminal_reserve proof attempts; R15 tree_energy and nonunit_join proof attempts; R15 HALF_HISTORY_PD_JOIN.md; the R13 relaxed-history proof; and the parent's R17 AFFINE_RIGHT_WITH_SLACK.md and NORMAL_RIGHT_RESERVE.md. The affine-right parent packet was independently audited separately; the mixed extension and normal-moment theorem in this file were not included in that audit. The memory registry was used only to preserve evidence-status boundaries; live project sources control this packet.

One authorized invocation, at most two substantive approaches: (1) cyclic-row/normal-moment payment and the mixed-right closure; (2) actual growing-depth tests of proposed termwise payments. Mathematical programs, arrays, solvers, additional agents/models, services, truth-store operations, formal submissions, and publication: zero. Only this PROOF_ATTEMPT.md and HANDOFF.md are written by this worker. No worker-private memory was read.
