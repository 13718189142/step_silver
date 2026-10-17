# R16 normal geometry: an all-depth exclusion of affine-right nesting

**UNVERIFIED manual analytical draft. The full theta=49/100 history assertion and the original exact-profile minimax problem remain OPEN.**

The complete result below concerns a specified structure of actual trajectories on any convex 1-smooth function. It allows arbitrary finite dimension, including dimension growing with the enclosing parameter, and controls both the history residual and the final objective at the originally selected minimizer. It excludes a natural way of nesting the new equality geometry. It does not assume that every trajectory has this structure. The original projection-envelope argument was extended to the full function class by the parent through the exact auxiliary-value identity (1.4); that extension was independently re-expanded here.

Two approaches were used: (1) actual normal geometry and its cumulative support constraints; (2) an exact growing-depth phase of the symmetric-Huber range map. No mathematical program, array, solver, additional model call, child agent, service, truth-store operation, or formal submission was used.

## 1. Parameters and the actual-history structure

Fix the same enclosing integer throughout:

\[
m\ge1536,\quad e=1/(4m),\quad \beta=1-e,\quad
c=(1+\sqrt2)(1+e),\quad a=\beta/c,
\]
\[
H_0=(),\qquad H_{j+1}=(H_j,1+k_j,H_j),\qquad
k_j=ac^j,\qquad C_j=1+\sum H_j.
\]

Thus C_0=1, C_1=2+a and C_(j+1)=2C_j+k_j. Write r_j=k_j/C_j. The finite-parameter bounds used below are

\[
2/5<a<1/2,\qquad 2/5<r_j<5/12\ (j\ge1),\qquad
C_1>12/5,\quad C_j>23/4\ (j\ge2).
\tag{1.1}
\]

These follow from the closed capacity formula in the R15 tree-energy packet. In particular, with c_0=1+sqrt(2), t=2/c and

\[
\zeta=\frac{(5+2\sqrt2)e+c_0^2e^2}{1-e}<9e,
\]
\[
C_j=c^j\frac{1+\zeta t^j}{1+\zeta},\qquad
r_j=\frac{c-2}{1+\zeta t^j}<c-2<5/12.
\tag{1.2}
\]

For an elementary check of the ranges, sqrt(2)>24/17 and (1-e)/(1+e)>34/35 give a>2/5. Also a<sqrt(2)-1<1/2. The formula gives C_j<=c^j, hence r_j>=a. Using sqrt(2)<99/70 gives c<29/12, so r_j<c-2<5/12. Finally beta>99/100 gives C_2=2C_1+beta>24/5+99/100>23/4. The estimate zeta<9e follows from (8+6e)/(1-e)<9. These checks apply on the whole parameter interval, not only at its limit.

Let f be one finite-dimensional convex differentiable function with 1-Lipschitz gradient and an attained minimum. At every actual query define

\[
g_i=\nabla f(x_i),\qquad y_i=x_i-g_i,\qquad
u_i=\langle g_i,x_i\rangle-f_i-\tfrac12\|g_i\|^2.
\tag{1.3}
\]

The original smooth-convex interpolation rows satisfy the exact identity

\[
Q_{ij}=2(f_i-f_j)-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2
=2\{u_j-u_i-\langle y_i,g_j-g_i\rangle\}\ge0.
\tag{1.4}
\]

In particular, equal gradients imply equal u values, by applying both directed rows. No interpolation sufficiency theorem or auxiliary realizing function is used.

For a depth-J physical word, set p_l=g_(2^l-1), v_l=x_(2^l-1), and y_l=v_l-p_l along its left spine, for 1<=l<=J. Consider the following **restricted nesting mechanism**:

* For every 1<=l<J, every query in the right H_l block of the prefix H_(l+1), including its first and terminal queries, has the constant gradient p_(l+1).
* The two root endpoint rows vanish: Q_(v_l,v_(l+1))=Q_(v_(l+1),v_l)=0.

All other original interpolation inequalities are retained. In particular, the proof below uses an old left query against the first new right query. No free Gram matrix, separate child function, or independent block reset is allowed.

The affine-right H_2 equality gadget found by the terminal-reserve branch can be a seed for this mechanism. The result does not assert that its literal fixed function remains in this mechanism after further roots.

## 2. An old-query interpolation row prevents cheap repeated affine flips

For this section take J>=2; the J=1 conclusions follow directly from the leaf identity in Section 3. Put d_l=p_l-p_(l+1), for 1<=l<J. The physical endpoint update and the two zero rows give

\[
y_{l+1}=y_l-k_l p_l-C_l p_{l+1},
\]
\[
\langle k_l p_l+C_l p_{l+1},p_l-p_{l+1}\rangle=0.
\]

Consequently

\[
\|p_{l+1}\|^2=r_l\|p_l\|^2+(1-r_l)\langle p_l,p_{l+1}\rangle,
\tag{2.1}
\]
\[
\|p_l\|^2-\|p_{l+1}\|^2
=\frac{1-r_l}{1+r_l}\|d_l\|^2,
\qquad
\|p_l\|\le\frac{\|p_{l+1}\|}{r_l}.
\tag{2.2}
\]

The last bound follows by using <p_l,p_(l+1)> >= -||p_l||||p_(l+1)|| in (2.1); when the terminal gradient is zero, (2.1) forces p_l=0.

For l>=2, let U_l denote u at the endpoint v_l. The previous and current zero rows, both with source v_l, give

\[
U_{l-1}-U_{l+1}=\langle y_l,p_{l-1}-p_{l+1}\rangle.
\]

The first physical right query has gradient p_(l+1), hence auxiliary value U_(l+1), and proximal coordinate

\[
n_l=y_l-k_l p_l-p_{l+1}.
\]

Its original interpolation row against the old query v_(l-1), divided by two, is therefore exactly the inner product in

\[
\boxed{\langle k_l p_l+p_{l+1},p_{l-1}-p_{l+1}\rangle\ge0.}
\tag{2.3}
\]

This is the nonlocal interpolation condition that the freely repeated scalar flip omits. On projection envelopes it is literally a normal support inequality. From (2.1)--(2.2), it becomes

\[
A_l\|d_l\|^2-B_l\|d_{l-1}\|^2-\langle d_l,d_{l-1}\rangle\ge0,
\tag{2.4}
\]
\[
A_l=\frac{r_l(C_l-1)}{1+r_l},\qquad
B_l=\frac{(k_l+1)r_{l-1}}{1+r_{l-1}}.
\]

The symbol B_l here is local to (2.4), not the R15 tree multiplier. The actual ranges (1.1) yield

\[
A_l\le\frac5{17}(C_l-1),\qquad
B_l\ge\frac4{35}C_l+\frac27>\frac{33}{35},
\]
\[
A_l+2-4B_l
\le-\frac{97}{595}C_l+\frac{67}{119}
<-\frac{891}{2380}<0.
\tag{2.5}
\]

If d_l is nonzero, (2.4) and Cauchy give A_l+z-B_l z^2>=0, where z=||d_(l-1)||/||d_l||. The expression is decreasing for z>=2, and is negative at 2 by (2.5). If d_l=0, (2.4) forces d_(l-1)=0. Thus

\[
\boxed{\|d_{l-1}\|\le2\|d_l\|\quad(2\le l<J).}
\tag{2.6}
\]

Since C_l/C_(l-1)=2+r_(l-1)>12/5, the weighted quantities w_l=C_l^2||d_l||^2 obey w_(l-1)<(25/36)w_l whenever nonzero. Moreover, (2.2) gives ||d_(J-1)||<=(7/2)||p_J||. Summing the geometric bound gives

\[
\begin{aligned}
\sum_{l=1}^{J-1}C_l^2\|d_l\|^2
&\le\frac{36}{11}C_{J-1}^2\|d_{J-1}\|^2\\
&\le\frac{1225}{176}C_J^2\|p_J\|^2
<7C_J^2\|p_J\|^2
\end{aligned}
\tag{2.7}
\]

when p_J is nonzero. If p_J=0, every term on the left is zero. The weaker non-strict bound with constant 7 is valid in all cases. Nothing in this argument bounds the ambient dimension.

## 3. Uniform history bound and actual final objective

For any physical word of capacity C define

\[
E^{\rm std}=2\sum_i h_i(f_i-f_{\rm end})
-\sum_i h_i(h_i-1)\|g_i\|^2-(C^2-C)\|g_{\rm end}\|^2.
\]

In the mechanism of Section 1, each right child has E_R^std=0. Its other cross rows vanish because its gradient is constant and the root endpoint rows vanish. The exact R13/R15 split consequently reduces to

\[
E_{l+1}^{\rm std}=E_l^{\rm std}
-C_l^2(r_l^2+2r_l-1)\|d_l\|^2.
\tag{3.1}
\]

The actual leaf has h=1+a<sqrt(2), so

\[
E_1^{\rm std}=(h+1)Q_{01}+Q_{10}+(2-h^2)\|g_0-g_1\|^2\ge0.
\]

The finite-parameter defect bound is uniform in l:

\[
r_l^2+2r_l-1<c^2-2c-1
=(4+2\sqrt2)e+c_0^2e^2<7e.
\tag{3.2}
\]

For the last comparison one may use sqrt(2)<10/7, c_0^2<6 and 6/6144<1/7. Negative early defects in (3.1) only improve the lower bound. Equations (2.7)--(3.2) give

\[
\boxed{E_J^{\rm std}\ge-49e C_J^2\|p_J\|^2.}
\tag{3.3}
\]

Define E_J(theta)=E_J^std+(1-theta)C_J^2||p_J||^2. In particular, simultaneously for every J>=1,

\[
\boxed{E_J(49/100)\ge(51/100-49e)C_J^2\|p_J\|^2\ge0.}
\tag{3.4}
\]

This is an all-depth result for the explicitly stated trajectory structure on the full smooth-convex function class. It does not remove the two structural assumptions in Section 1.

It also controls the requested final objective, without changing the selected minimizer. Put C=C_J, S=C-1,

\[
\Gamma=(1-49e)C^2-C,\qquad
t=1+\frac{15}{17}S,\qquad B=S+t=1+\frac{32}{17}S.
\]

For any originally selected minimizer x_star, use the weights omega=(h,t), including the actual terminal query, and Q_(star,i)=2(f_star-f_i)+2<g_i,x_i-x_star>-||g_i||^2>=0. Direct expansion of the retained dominance residual gives

\[
D=E_\Gamma+[\Gamma-t(t-1)]\|p_J\|^2.
\tag{3.5}
\]

Here D is exactly

\[
\|x_0-x_\star\|^2-\sum_i \omega_iQ_{\star i}
-2B(f_{\rm end}-f_\star)
-\left\|x_0-x_\star-\sum_i \omega_i g_i\right\|^2.
\]

The remaining coefficient is positive:

\[
\Gamma-t(t-1)=
\left(\frac{64}{289}-49e\right)C^2-\frac{94}{289}C+\frac{30}{289}
>\frac15C^2-\frac13C>0,
\tag{3.6}
\]

using 49e<1/100 and C>12/5. Equations (3.3), (3.5), and the nonnegative original star rows therefore give the actual bound

\[
\boxed{
\frac{2(f_{\rm end}-f_\star)}{\|x_0-x_\star\|^2}
\le\frac1{1+(32/17)(C_J-1)}.
}
\tag{3.7}
\]

This holds for every trajectory satisfying Section 1, including a closest minimizer if it was selected for that final instance. Thus choosing a different valid original minimizer cannot turn this nesting mechanism into a counterexample to the desired candidate objective bound. Equation (3.7) is not an upper bound for W(H_J), whose supremum also includes trajectories outside Section 1.

## 4. The literal R15 simplex is absorbed at the next root

This separate calculation uses the exact K and start supplied in R15. Write r=sqrt(2)-1, b=sqrt(1+3r), A=3+r, and

\[
g_0=(2,0,1),\quad p=(1,b,0),\quad w=(1,-b,0),
\quad K=\operatorname{conv}\{0,g_0,p,w\},
\]
\[
x_0=(6+3r,b,-2),\qquad q=(1,rb,0),\qquad y=(0,0,-A).
\]

Use the static projection envelope f_K(x)=sup_(g in K){<x,g>-||g||^2/2}. Its gradient is P_K x, so it is convex and 1-smooth, and 0 is a selected minimizer with value 0. For this subclass u_i=0 and Q_ij=2<y_i,g_i-g_j>.

At the exact Silver H_2 endpoint x_3=q+y. The next bridge has excess c_0=1+sqrt(2), and sends it to x_4^0=-c_0q+y. Its support values at the three nonzero vertices are

\[
\langle x_4^0,g_0\rangle=-(7+3r),\quad
\langle x_4^0,p\rangle=-(3+4r),\quad
\langle x_4^0,w\rangle=-r^2.
\tag{4.1}
\]

Thus P_K x_4^0=0, and every subsequent gradient is zero.

This persists uniformly for the actual enclosing parameters. The inherited first three steps are (h_e,2-e,h_e), with h_e=h-d, h=sqrt(2), d=2re/(1+e)<e. Every gradient in K has norm at most sqrt(5), and the three update maps with step at most two are nonexpansive. Comparing the actual and limiting updates gives

\[
\|x_3(e)-x_3(0)\|<7e,\qquad
\|g_3(e)-q\|<7e.
\]

The next bridge is 1+c_0(1-e^2)<7/2. Hence

\[
\|x_4(e)-x_4^0\|<32e.
\tag{4.2}
\]

Each support value changes by less than 72e<=3/256, whereas the smallest negative margin in (4.1) is r^2>1/6. Therefore P_K x_4(e)=0 exactly for every m>=1536. All H_J, J>=3, begin with these four steps and then remain at x_4(e).

The actual final objective is consequently zero at every such depth. Also

\[
\|x_0\|^2=50+21r,\qquad \|x_4^0\|^2=16+9r,
\]

and (4.2) changes the latter squared norm by less than 321e. Every selected-zero minimizer row of f_K is zero. Thus

\[
E_J(\theta)=\|x_0\|^2-\|x_4(e)\|^2>34
\quad(J\ge3)
\tag{4.3}
\]

for every theta. Reusing this fixed simplex supplies neither an all-depth history counterexample nor an objective counterexample. A successful new geometry must actually rebuild the function across depth.

## 5. What the normal identity does and does not charge

For an arbitrary physical equal-child join, let p be the left endpoint gradient, q the terminal gradient, G the right displacement, C its child capacity, k its bridge excess, and D=k p+G+q. In this paragraph J is an arbitrary scalar certificate coefficient: E_R(J) has terminal penalty J-C. Write

\[
A_v=\sum_R h_iQ_{vi},\quad A_y=\sum_Rh_iQ_{yi},\quad
\eta=\frac{C-k}{C+k},
\]
\[
R=\frac{kA_v+CA_y+kQ_{vy}+CkQ_{yv}}{C+k}\ge0.
\]

Direct elimination of the right displacement identities gives the exact full-space port identity

\[
\boxed{k^2\|p\|^2+\eta\|D\|^2=J\|q\|^2+E_R(J)+R.}
\tag{5.1}
\]

The parent identified this as its normalized optimized V0 identity; it is reconstructed here for its geometric meaning, not claimed as a new independent certificate. In the projection subclass, D is the terminal normal displacement across the bridge and right child.

At exact Silver, a zero sharp residual forces every used child residual and every used row to vanish. Let p_l,y_l be the left-spine endpoint gradients and proximal coordinates, now also including l=0. With D_l=y_l-y_(l+1), (5.1), including the leaf, telescopes to

\[
\boxed{\|g_0\|^2+c_0\sum_{l=0}^{J-1}\|D_l\|^2
=C_J^2\|q\|^2,\qquad X+q=g_0+\sum_{l=0}^{J-1}D_l.}
\tag{5.2}
\]

The root equalities also give <D_l,p_l>=<D_l,p_(l+1)>=||D_l||^2/[(1+r)C_l]. Thus these normal increments cannot be chosen as independent favorable vectors. A bare Cauchy estimate from (5.2) is only

\[
\|X+q\|^2\le(1+J/c_0)C_J^2\|q\|^2.
\tag{5.3}
\]

This loses depth and does not pay the required uniform reserve. The quantitative repair in Sections 2--3 uses the additional old-query support row and the affine-right hypothesis. No comparable all-depth estimate for general nonconstant right children is obtained.

## 6. Approach 2: one exact growing-depth symmetric-Huber phase

Use the single symmetric Huber function with gradient clamp(x,-1,1). For a step of excess k, the radius range map and its lower inverse are

\[
M_k(R)=\max\{k\min(R,1),R-1-k\},\qquad
T_k(s)=\begin{cases}s/k,&0\le s\le k,\\s+1+k,&s>k.\end{cases}
\]

Images of centered intervals are centered intervals, so these range maps compose exactly. Let M_j be the range map for H_j and F_j its lower inverse. Palindromicity gives

\[
F_{j+1}=F_j\circ T_{k_j}\circ F_j.
\tag{6.1}
\]

The R15 tail identity is M_j(R)=R-(C_j-1) for R>=C_j. Set A=beta^2/c=a beta. Then

\[
\boxed{M_j(k_j)=A\quad\hbox{for every }j\ge1.}
\tag{6.2}
\]

For j=1 this is M_1(beta)=a beta. For j>=2, k_j>=C_(j-1): it holds at j=2 because k_2-C_1=2re/(1+e)-c_0e^2>0, and the ratio k_j/C_(j-1) increases by (1.2). Also k_j/C_(j-1)<1+9e, so 0<=k_j-C_(j-1)<(45e/2)k_(j-1)<2k_(j-1). The first child therefore produces radius 1+k_j-C_(j-1); the middle step is on its plateau and produces k_(j-1); the last child gives (6.2) inductively.

For s>a, one has the exact inverse tail F_j(s)=s+C_j-1. This follows by induction because s+C_j-1>k_j. Put v_j=F_j(A). Then

\[
v_1=\beta,\qquad
\boxed{v_{j+1}=C_j-1+v_j/k_j\quad(j\ge1).}
\tag{6.3}
\]

To justify the branch choice uniformly, v_2=C_1, and induction gives C_(j-1)-1+a<v_j<=C_(j-1) for j>=2. Hence

\[
1/2<\frac{3}{4(1+9e)}<v_j/k_j\le1,
\]

and a<1/2, so the final F_j in (6.1) is in its exact tail.

This entire phase satisfies

\[
\boxed{v_j\ge A C_j\quad(j\ge1).}
\tag{6.4}
\]

The first base uses a C_1<1. The second is C_1>A C_2: multiplying by c reduces it to C_1(c-2beta^2)>beta^3; use C_1>=c_0-e and c-2beta^2>r+6e to make the left side greater than 1. For j>=2, (6.3), r_j<c-2 and A/r_j=beta C_j/c^j>=1-10e give

\[
v_{j+1}-AC_{j+1}
\ge C_j[1-A(2+r_j)]-1+A/r_j
>C_j(1-\beta^2)-10e
>\tfrac32e-\tfrac{23}{4}e^2>0.
\]

There is an actual initial point of radius v_j attaining terminal absolute position A, because the continuous range map attains its lower inverse. It is in the quadratic core. Thus its actual final normalized objective is A^2/v_j^2<=1/C_j^2, and its history residual at theta=49/100 is at least (51/100)C_j^2 A^2. This whole-depth critical phase cannot yield the requested obstruction. Other inverse-map phases and the full smooth-convex class are not settled by (6.4).

## 7. Completion boundary and source receipt

The complete new mechanism-level result is Sections 2--3: repeated affine-right, zero-endpoint-row nesting cannot defeat either the weak history input or its desired objective bound, even in growing dimension and on an arbitrary convex 1-smooth function. The decisive inequality is the old-query interpolation row (2.3). The literal R15 simplex also becomes absorbed after four physical steps, uniformly in the actual enclosing parameter.

No actual family violating E_j(49/100) at j growing with m is constructed, and no full-class proof of that input is supplied. Nonconstant right-child revisits and nonzero endpoint-row budgets remain outside the mechanism-level theorem. The parent corrected a proposed normal-motion-only obstruction by an actual old-face quadratic revisit; no such obstruction is claimed here.

Read sources: OPERATOR.md; original PROBLEM.md; R16 WAVE.md; R15 SILVER_DISPLACEMENT_COUNTEREXAMPLE.md, HALF_HISTORY_PD_JOIN.md and R15_PROGRESS.md; R15 tree-energy and nonunit-join proofs; R12_RELAXED_PD_JOIN_LEAD_20261009.md; and the R13 relaxed-history proof. The official [Zhang--Jiang article](https://arxiv.org/html/2410.12395v2) was checked at Proposition 8/Corollary 9 only to confirm the primitive-to-dominant normalization; the perturbed theorem above is not attributed to that article. The memory registry was used only for the existing evidence boundary, not as mathematical input.

All new algebra is manual and unverified by the Danus verifier. Several guessed source paths were absent and were replaced by bounded filename searches; truncated combined outputs were followed by focused reads. Those read errors are not success claims. Only this file and HANDOFF.md are written by this invocation. The hard analytical deadline remains 2026-10-17 05:05:00 UTC; no renewal is requested or inferred.
