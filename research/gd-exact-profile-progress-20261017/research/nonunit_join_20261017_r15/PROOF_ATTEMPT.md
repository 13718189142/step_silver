# R15 nonunit history join: terminal-port transport and its unresolved coercivity

**UNVERIFIED analytical research draft. No all-depth weak-history theorem, actual counterexample, or original-target resolution is claimed.**

This is one authorized native analytical invocation, with hard deadline 2026-10-17 04:20:00 UTC. Mathematical programs, arrays, solvers, formal submissions, new agents/models, services, truth-store mutations and publication are zero. The only output files are this file and `HANDOFF.md` in the present directory. The original minimax target remains OPEN.

## 1. Fixed problem and sources

Normalize smoothness to one. Fix one enclosing integer m >= 1536 and use the SAME parameters in every subtree:

\[
\epsilon=(4m)^{-1},\quad \beta=1-\epsilon,\quad
c=(1+\sqrt2)(1+\epsilon),\quad a=\beta/c,
\quad H_0=(),\quad H_{j+1}=(H_j,1+ac^j,H_j).
\]

Set C_j=1+sum H_j. The requested history expression is

\[
E_j(\theta)=2\sum_i h_i(f_i-f_e)
-\sum_i h_i(h_i-1)\|g_i\|^2
-(\theta C_j^2-C_j)\|g_e\|^2.
\]

The dispatch asks for theta=7/10 at every 1 <= j < m on every actual finite-dimensional smooth convex trajectory. During this invocation the parent derived a less demanding conditional PD interface with theta=49/100; that interface is a separate unverified draft and does not prove the history premise.

The governing local reads were OPERATOR.md, PROBLEM.md, the completed R13 `relaxed_history_for_pd_join_20261009_r13/PROOF_ATTEMPT.md`, `R12_RELAXED_PD_JOIN_LEAD_20261009.md`, the recovered R14 interruption note, and the parent's `resume_20261017_r15/HALF_HISTORY_PD_JOIN.md`. The old dense-history root note and R5 handoff were read only to avoid duplicating already scoped interfaces. The memory registry supplied the evidence boundary; current files and the new dispatch control this invocation.

The original rows are

\[
Q_{ij}=2(f_i-f_j)-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2\ge0.
\]

No result below substitutes arbitrary algebraic gradients for an actual trajectory when claiming a function-class statement. Free-gradient tests are used only to test a claimed PSD remainder.

## 2. A full original-row transfer identity

Let the left and right physical masses be s=C-1, let the bridge be b=1+k, and write the path as x -> v -> w -> y, where p=g(v), q=g(y), w=v-bp, G=w-y, and Z=G+q. The right history has coefficient Gamma=J-C. Define

\[
A_v=\sum_R h_iQ_{vi},\qquad A_y=\sum_R h_iQ_{yi}.
\]

For arbitrary nonnegative b_0,c_0, put

\[
V_0=(b_0+c_0)E_R+b_0A_v+c_0A_y+b_0Q_{vy}+b_0C Q_{yv}.
\]

Direct cancellation of every function value gives the EXACT identity

\[
V_0=2b_0Ck\|p\|^2+2b_0(C-k)\langle p,Z\rangle
+(c_0-b_0)\|Z\|^2-(b_0+c_0)J\|q\|^2. \tag{2.1}
\]

Here no positivity of E_R was used in deriving the identity. To check it, the identities needed are

\[
E_R+A_y=\|Z\|^2-J\|q\|^2,
\]

\[
A_v=-E_R+sQ_{vy}-\|Z\|^2-2k\langle p,Z\rangle
+2C\langle q,kp+Z\rangle-J\|q\|^2,
\]

\[
Q_{vy}+Q_{yv}=2\langle p-q,kp+Z\rangle.
\]

For 0<r=k/C<1, choose c_0=b_0/r. Completing one square gives

\[
V_0=b_0C^2r(1+r)\|p\|^2
-b_0(1+r)J/r\,\|q\|^2
+b_0(1-r)/r\,\|Z+kp\|^2. \tag{2.2}
\]

Consequently the endpoint transfer ratio is exactly J/k^2. This choice also minimizes the ratio among c_0>b_0: the ratio before minimization is

\[
\frac{(1+z)J}{C^2[2r-(1-r)^2/(z-1)]},\qquad z=c_0/b_0,
\]

and differentiating the rational expression or completing its difference from J/k^2 yields the minimizer z=1/r.

This is a useful signed-energy identity, not an all-depth induction. If it is used only to pay a negative bridge coefficient in the old unit-left join, the best resulting terminal coefficient is J_parent=J^2/k^2, subject also to the available row budgets. The parent independently derived the same recurrence. It is the unstable scalar recurrence, not the desired reciprocal-P law.

## 3. Retargeting a COMPLETE child certificate

This operation retains the child's genuine internal rows. It therefore differs materially from replacing the missing left function flow by cross rows alone.

Consider any fixed word h_0,...,h_(n-1), endpoint v=x_n, p=g_n, and s=sum h_i. Suppose an algebraic certificate has been constructed:

\[
E_\Gamma=\sum_{i\ne j}\lambda_{ij}Q_{ij}+R(g_0,\ldots,g_{n-1},p),\qquad
\lambda_{ij}\ge0,\quad R\succeq0. \tag{3.1}
\]

The remainder need not be diagonal or rank one. Define the terminal ports

\[
u_i=\lambda_{i,n},\qquad v_i=\lambda_{n,i},\qquad
U=\sum_{i<n}u_i,\quad V=\sum_{i<n}v_i g_i.
\]

Let y be any other ORIGINAL query, with q=g(y), and set D=v-y. Form T_y by replacing the terminal label n by y in every terminal-incident row and replacing the terminal gradient p by q in R. Leave every strictly internal row unchanged. All resulting rows are original interpolation rows, and the retargeted R remains PSD. Hence T_y >= 0 on actual data whenever (3.1) is an actual certificate.

The exact transport formula is

\[
\boxed{T_y=E_\Gamma+2s(f_v-f_y)+\Gamma(\|p\|^2-\|q\|^2)
+2\langle V-Uq,D\rangle.} \tag{3.2}
\]

This identity holds for the full remainder, including its terminal cross terms. Here is a coefficient proof. Write

\[
R=R_{\mathrm{int}}+2\langle M,p\rangle+d\|p\|^2,
\]

where M is a fixed linear combination of the internal gradients. Function-value balance and endpoint diagonal balance give

\[
\sum_i(u_i-v_i)=s,\qquad \sum_i(u_i+v_i)=\Gamma+d.
\]

Mixed-coefficient balance gives

\[
\sum_i u_i(x_i-v-g_i)=V+M.
\]

Indeed, the coefficient at g_t on the left is h_t sum_(i<=t)u_i-u_t, and the coefficient of <g_t,p> in the row sum is twice v_t minus twice this quantity; it is the negative of the remainder's mixed coefficient. Expanding the retargeted rows therefore changes the row sum by

\[
2s(f_v-f_y)+(\Gamma+d)(\|p\|^2-\|q\|^2)
+2\langle V-Uq,D\rangle+2\langle M,p-q\rangle.
\]

The change R(...,q)-R(...,p) cancels the d and M terms exactly, proving (3.2).

This provides a full, coefficient-level left-internal operation. It does not supply the missing PSD certificate at all depths: the new vector V must be controlled, not dropped.

## 4. Exact nonunit join after retargeting

Let alpha=1-delta with 0<=delta<=1. Mix alpha times the original left certificate with delta times its retargeted certificate. The right child has the same Gamma. Set

\[
T'=C+k-\delta s,\qquad
t-u=T'-\lambda s,\qquad B=1+\lambda+\mu,
\]

with lambda,mu,t,u nonnegative. Then E_parent has the exact representation

\[
E_P=\alpha E_L+\delta T_y+B E_R
+\lambda A_v+\mu A_y+tQ_{vy}+uQ_{yv}+\mathcal R. \tag{4.1}
\]

The quadratic remainder, on the FULL variables p,q,G and the left internal vector V, is

\[
\begin{aligned}
\mathcal R={}&[\alpha J+\delta-k^2-2ku]\|p\|^2
+[(B+\delta)\Gamma-\Gamma_P+\mu s+t+u]\|q\|^2\\
&+(\lambda-\mu)\|G\|^2
+2[tk-u+\delta Ub]\langle p,q\rangle
+2(\lambda k-u)\langle p,G\rangle\\
&+2[t-\mu+\delta U]\langle q,G\rangle
-2\delta\langle V,bp+G\rangle.
\end{aligned} \tag{4.2}
\]

This includes all the newly introduced left-gradient terms. Setting V to zero or treating it as a freely favorable scalar would be invalid. If the child PSD remainders have already been consumed by the nonnegative terms in (4.1), (4.2) has no V-square term and cannot be PSD for delta>0 with a nonzero terminal outgoing port. A viable proof must retain additional quantitative child information or change the internal rows further.

## 5. Actual-function obstruction to convex terminal retargeting

The retargeting operation above is not a successful repair. It fails on the same static asymmetric Huber family that detects full-left retention, and the following obstruction allows an arbitrary child PSD remainder.

Fix an actual child height j>=3, C=C_j, k=ac^j, r=k/C, and theta in {7/10,49/100}. Use

\[
f_r(z)=\begin{cases}-rz-r^2/2,&z\le-r,\\z^2/2,&-r\le z\le1,\\z-1/2,&z\ge1.\end{cases}
\]

Start the parent at x_0=C. The left queries have gradient 1 and end at v=p=1. The bridge goes to -k. The right queries have gradient -r, and the parent endpoint is y=q=-r. This is one static convex differentiable 1-smooth function with unique minimizer zero. It uses every physical step of the actual same-enclosing-m word.

With Gamma=theta*C^2-C, the actual values are

\[
E_L=(1-\theta)C^2,\qquad
E_P=C^2\{1-\theta[r(2+r)]^2\}<E_L. \tag{5.1}
\]

For completeness, the actual inherited ratio is

\[
r=\frac{c-2}{1+\zeta(2/c)^j},\qquad
\zeta=\frac{(5+2\sqrt2)\epsilon+(1+\sqrt2)^2\epsilon^2}{1-\epsilon}<9\epsilon.
\]

Writing c_*=1+sqrt(2), r_*=1/c_*, one has c-2=r_*+c_*epsilon. For j>=3,

\[
r_*\zeta(2/c)^j<72\epsilon/c_*^4<c_*\epsilon,
\]

because c_*^5=41+29sqrt(2)>72. Hence r>r_* and r(2+r)>1, proving the strict inequality in (5.1). This is the actual same-enclosing-m ratio, not an epsilon=0 substitution. Also r<c-2<5/12: use sqrt(2)<99/70, epsilon<=1/6144, and 178345/430080<179200/430080=5/12. Consequently (5.1) remains positive for both fixed theta values, since (7/10)(145/144)^2<1.

For ANY child certificate (3.1), all left internal gradients equal 1, so V=sum v_i=U-s. Let d>=0 be the coefficient of its terminal gradient squared in its PSD remainder. Endpoint balance gives 2U=s+Gamma+d. Substitution in (3.2) gives

\[
\boxed{T_y-E_L=2\Gamma(1+r)+d(1+r)^2>0.} \tag{5.2}
\]

For clarity, before simplification the difference is

\[
(s+\Gamma)(1-r^2)+2[U(1+r)-s](1+r).
\]

Here Gamma>0 because C>2^j>=8 and theta>=49/100. Thus no representation or inequality with all additional terms nonnegative can have

\[
E_P\ge (1-\delta)E_L+\delta T_y+\text{nonnegative terms},
\quad 0\le\delta\le1. \tag{5.3}
\]

The right side is at least E_L, contradicting (5.1). This conclusion does not depend on a free-gradient PSD test or a particular choice of the child certificate.

The same conclusion holds for retargeting to ANY right query z<=-r. Its gradient is -r, and direct substitution yields

\[
T_z-E_L=(1+r)\{2\Gamma+d(1+r)+(-z-r)(\Gamma+d-s)\}. \tag{5.4}
\]

At j>=3, Gamma-s=theta*C^2-2C+1>0, so (5.4) is positive. Therefore any nonnegative convex combination of the original left certificate and its complete retargetings to right queries has value at least E_L on this witness. Such a combination cannot be the desired retained nonunit input.

The scope is specific: the coefficients of these original/retargeted complete certificates sum to one, and the remaining terms are nonnegative. The result does not exclude a different left internal redistribution, a different simultaneous invariant, or the requested E_j(theta)>=0 itself. Indeed, (5.1) stays positive for the fixed theta values here.

## 6. A genuine internal redistribution was tested

Let z_i=x_i-g_i denote the original proximal-coordinate variable. For distinct indices a,b,c, the exact path-splitting identity is

\[
Q_{ab}+Q_{bc}-Q_{ac}=2\langle g_c-g_b,z_a-z_b\rangle. \tag{6.1}
\]

Consequently an existing row a->c of weight t can be replaced by the two internal rows a->b and b->c of weight t. This preserves every function-value coefficient and keeps every row coefficient nonnegative. The remainder changes by minus the right side of (6.1). Thus this is an actual internal redistribution, not a cross-only repair.

One explicit port-balancing construction was derived and rejected by its full diagonal check. Given terminal incoming weights u_i, outgoing weights v_i, totals U=sum u_i and v=sum v_i, replace each outgoing terminal row n->i by paths n->j->i with weights u_j*v_i/U. The terminal outgoing weights become v*u_j/U, so the terminal net flow is nonnegative at every query:

\[
u_j-vu_j/U=su_j/U\ge0.
\]

The new strictly internal rows have weights u_j*v_i/U. All are nonnegative and the function-value balance is exact. When the original certificate has zero terminal cross remainder, write U_<i=sum_(j<i)u_j and r_i=h_i-1. The change in the remainder diagonal at g_i is

\[
\frac2U\{h_i v_iU_{<i}-r_i u_i(v-v_i)\}
=\frac2U\{v_i^2-r_i u_i v\}, \tag{6.2}
\]

where the last equality uses v_i=h_i U_<i+r_i u_i from mixed-coefficient cancellation.

This redistribution already fails at the exact limiting Silver H_2. Put c_*=1+sqrt(2), h=sqrt(2), so H_2=(h,2,h). The standard recursive original-row certificate has, at the bridge query i=1,

\[
u_1=v_1=c_*,\qquad U=6c_*+2,\qquad v=2c_*^2,\qquad r_1=1.
\]

The new remainder diagonal is

\[
\frac{2c_*^2}{6c_*+2}(1-2c_*)<0. \tag{6.3}
\]

The limiting certificate has zero initial remainder; adding any weak terminal-only reserve changes only the final gradient diagonal and cannot repair (6.3). Thus uniform incoming-port redistribution is not a valid PSD repair. This tests a concrete nonnegative internal coefficient construction; it does not exclude nonuniform path routing or a richer simultaneous invariant.

## 7. Displacement-surplus alternative: an actual H_2 counterexample

For any word set X=x_start-x_end and

\[
A_{\rm end}=\sum_i h_iQ_{{\rm end},i}.
\]

The identity

\[
E_\Gamma+A_{\rm end}=\|X+q\|^2-J\|q\|^2
\]

suggests trying a stronger simultaneous input E_std>=kappa*A_end. At the exact Silver leaf h=sqrt(2), kappa=1/sqrt(2) follows immediately from

\[
E_{h(h+1)}=(h+1)Q_{01}+Q_{10},\qquad A_{\rm end}=hQ_{10}.
\]

Such a higher-depth invariant would retain a displacement square and would avoid the large terminal-port coefficients. However, the parent subsequently supplied the actual H_2 construction below, and its updates, support inequalities, row equalities and norm calculation were independently checked here. It disproves this unmodified stronger invariant for EVERY kappa>0. Leaf validity cannot be promoted even to H_2. This is the second substantive approach of the invocation, and it is closed by the actual counterexample below.

The parent supplied a projection-model diagnostic, and it was re-expanded directly here. For a closed convex set K containing zero, let

\[
f_K(x)=\sup_{u\in K}\{\langle x,u\rangle-\|u\|^2/2\},\qquad g=P_Kx.
\]

Write the terminal x_n=q+y, q=P_Kx_n, y in N_K(q), and Z=Cq+y. All selected-zero minimizer rows vanish, and direct expansion gives

\[
E^{\rm std}=\|x_0\|^2-\|Z\|^2,\qquad
A_{\rm end}=2\langle y,Z-x_0\rangle.
\]

Thus on this subclass the proposed displacement surplus is equivalent to

\[
\|x_0+\kappa y\|^2\ge\|Z+\kappa y\|^2. \tag{7.1}
\]

This is a diagnostic on a specific static-function subclass, not a reduction of all smooth convex histories to that subclass.

There is an exact continuum of equality tests at the limiting Silver ratio r_*=sqrt(2)-1. Give the asymmetric Huber caps +1 and -t, 0<=t<r_*, start a parent at x_0=C, and use k=r_*C. Its entire left child has gradient +1; the bridge lands at -k; its entire right child has gradient -t. The endpoint is x_n=-k+(C-1)t<=-t. With q=-t and y=C(t-r_*), direct simplification yields

\[
\frac{E^{\rm std}}{A_{\rm end}}
=\frac{1-r_*-(1+r_*)t}{2(r_*-t)}
=\frac{1+r_*}{2}=\frac1{\sqrt2}. \tag{7.2}
\]

The denominator is positive for t<r_*. Hence any proposed uniform displacement surplus at exact Silver must satisfy kappa<=1/sqrt(2), at every root height, not merely at the leaf. The actual perturbed absorbing case t=0 similarly forces kappa<=(1-r)/(2r)<1/sqrt(2); the terminal relaxation does not change this test because its final gradient is zero. These necessary conditions do not establish the proposed surplus at any higher depth.

### 7.1 Static three-dimensional H_2 counterexample

This construction was supplied by the parent during the invocation and then independently re-expanded here. Put

\[
r=\sqrt2-1,\quad h=1+r,\quad A=3+r,\quad b=\sqrt{1+3r},\quad C=5+2r,
\]

and let

\[
a=(2,0,1),\quad p=(1,b,0),\quad w=(1,-b,0),
\qquad K=\operatorname{conv}\{0,a,p,w\}.
\]

Use the single static function f_K defined above. Its unique maximizing gradient is P_K x, so it is convex and 1-smooth and has the selected minimizer zero. Define the four gradient and normal pairs

\[
\begin{array}{c|c|c}
i&g_i&y_i\\\hline
0&a&(4+3r,b,-3)\\
1&p&A(1,0,-1)\\
2&w&(h,0,-A)\\
3&q=(1,rb,0)&(0,0,-A).
\end{array}
\]

Take x_i=g_i+y_i. The initial point and every update are explicit:

\[
x_0=(6+3r,b,-2),\quad
x_1=(4+r,b,-A),\quad
x_2=(2+r,-b,-A),\quad
x_3=(1,rb,-A),
\]

\[
x_1=x_0-hg_0,\qquad x_2=x_1-2g_1,\qquad x_3=x_2-hg_2.
\]

Thus these are precisely the steps (sqrt(2),2,sqrt(2)) of limiting Silver H_2. The projection conditions are complete because the support comparisons against every vertex are

\[
y_0\cdot a=y_0\cdot p=5+6r>y_0\cdot w=3>y_0\cdot0=0,
\]

\[
y_1\cdot a=y_1\cdot p=y_1\cdot w=A>y_1\cdot0=0,
\]

\[
y_2\cdot p=y_2\cdot w=h>y_2\cdot0=0>y_2\cdot a=r-1,
\]

\[
y_3\cdot0=y_3\cdot p=y_3\cdot w=0>y_3\cdot a=-A.
\]

Also q is a convex combination of p and w, since 0<r<1. Hence each y_i belongs to N_K(g_i), so P_K x_i=g_i. No unverified interpolation realization theorem is needed.

For this support-envelope function,

\[
Q_{ij}=2\langle y_i,g_i-g_j\rangle.
\]

All rows in the standard recursive H_2 certificate vanish: Q_01,Q_10,Q_23,Q_32,Q_12,Q_13,Q_31. Thus E_std=0. Independently, using r^2=1-2r,

\[
\|x_0\|^2=50+21r,
\]

\[
\|Cq+y_3\|^2=(29+12r)(13r-4)+(10+4r)=50+21r,
\]

which verifies E_std=0 by the projection-model identity.

On the other hand Q_30=2A, while Q_31=Q_32=0. Therefore

\[
\boxed{A_{\rm end}=hQ_{30}+2Q_{31}+hQ_{32}=2hA=8+4r>0.} \tag{7.3}
\]

This actual three-dimensional trajectory disproves E_std>=kappa*A_end for every positive kappa. It also shows why the scalar Huber equality tests in (7.2) were not sufficient to validate the proposed invariant.

The target E_j(theta)>=0 is not contradicted: adding its weakened terminal penalty gives E_theta=(1-theta)C^2||q||^2>0 on this limiting example. The counterexample is to the stronger displacement-surplus input, not to the required weak history or the original minimax claim.

### 7.2 Quantitative continuation to the actual same-enclosing-m H_2

Keep the exact K and x_0 from Section 7.1 fixed. Run the actual inherited word

\[
H_2(\epsilon)=(h_\epsilon,2-\epsilon,h_\epsilon),\qquad
h_\epsilon=1+(\sqrt2-1)(1-\epsilon)/(1+\epsilon).
\]

Let d=h-h_epsilon=2r*epsilon/(1+epsilon)<epsilon. The map x -> x-t grad f_K(x) is nonexpansive for 0<=t<=2: expanding its squared difference and using cocoercivity leaves the term -t(2-t)||g(x)-g(z)||^2<=0. All three actual and limiting steps lie in this interval. Also every gradient is in K and has norm at most sqrt(5). Successive comparison of the three updates therefore gives

\[
\|x_3(\epsilon)-x_3(0)\|
\le\sqrt5(2d+\epsilon)<3\sqrt5\epsilon<7\epsilon.
\]

The terminal gradients satisfy the same Lipschitz comparison. With y=x_3-q and Z=x_3+(C-1)q, one obtains

\[
\|y_\epsilon-y_0\|<14\epsilon,\qquad
\|Z_\epsilon-Z_0\|<3\sqrt5(C_0+1)\epsilon<47\epsilon,
\]

where C_0=5+2r<6 and |C_epsilon-C_0|=2d+epsilon<3epsilon. The original radius and limiting Z norm are equal and less than 8, and ||y_0||=A<4. Thus, for epsilon<=1/6144,

\[
|E^{\rm std}_\epsilon|
\le(16+47\epsilon)47\epsilon<753\epsilon,
\]

\[
|A_{{\rm end},\epsilon}-A_{{\rm end},0}|
<824\epsilon+1316\epsilon^2<825\epsilon.
\]

Since A_end,0=8+4r>48/5, it follows that A_end,epsilon>47/5. Consequently any claimed universal actual-H_2 displacement surplus must satisfy

\[
E^{\rm std}_\epsilon\ge\kappa A_{{\rm end},\epsilon}
\quad\Longrightarrow\quad
\kappa<\frac{3765}{47}\epsilon<81\epsilon. \tag{7.4}
\]

This is an actual same-enclosing-m obstruction to any fixed positive kappa, not just a limiting-parameter objection. It still says nothing negative about the requested weakened terminal coefficient: the subtracted quantity here is E_std, and the target adds a substantial positive terminal-gradient term.

## 8. Independent dependency check of the theta=49/100 PD join

The parent note `../resume_20261017_r15/HALF_HISTORY_PD_JOIN.md` was checked algebraically within this invocation. This is not a formal verifier acceptance.

Using its notation d=32-15/C, A=d+32(1+r), T=A/d, tau=(A-17)/(d+17r), t=r*tau, gamma=1+tC, one obtains

\[
B_R=Cd/17,\quad B_P=CA/17,\quad
A_q/C^2=\theta-t^2,\quad B_q/C=r(T-\tau^2),\quad C_q=T-\tau^2.
\]

Thus det/C^2=(theta-r^2*T)(T-tau^2). The parent identity with a general t also checks:

\[
\det/C^2=(\theta-r^2T)(T-\tau^2)-T(t-r\tau)^2.
\]

For C>7/3 and 2/5<r<5/12, d>179/7 and d<32. The polynomial

\[
F(d,r)=2d^2+d(353r-225)+9248r^2
\]

has positive d and r derivatives on this rectangle. At its lower corner,

\[
F(179/7,2/5)=789623/1225,
\quad (1+2/5)F=5527361/6125>900.
\]

The denominator d(d+17r)^2<439922/9<49000. Hence C_q>1/60. Also

\[
49/100-37225/77328=66572/7732800>1/120.
\]

The parent's r^2T upper bound therefore yields det>C^2/7200. Tau>1 and t=r*tau>r give gamma>b. All these conclusions are conditional on the actual left weak history and actual right dominance inputs; no history input was manufactured.

## 9. Current continuation boundary

Two exact tools have been derived: the signed endpoint transfer (2.1)--(2.2), and the full terminal-port retargeting identity (3.2) with its complete nonunit remainder (4.2). The latter convex-retargeting closure is excluded by the actual function in Section 5. A concrete genuine internal redistribution is excluded by Section 6. Neither exclusion settles the full class of internal coefficient changes.

During the invocation the parent and tree-energy agent separately found an H_3 asymmetric-Huber violation of the exact capped reciprocal-P history coefficient. That proposed coefficient is not used as an input here. The scalar product bound alone is not a physical history theorem, and the fixed-depth violation of that stronger proposal does not refute the fixed theta=49/100 premise.

The remaining task is to construct nonnegative internal row changes and a different quantitative simultaneous invariant, while retaining a terminal factor at least 49/100 uniformly for j<m. The unmodified E_std>=kappa*A_end invariant is now excluded for every positive kappa. The existing cross-only obstruction and the R13 asymmetric-Huber witness remain applicable in their stated scopes.

The original complete all-depth request is still unresolved. No formal-review candidate has been produced.

## 10. Source and execution closeout

The direct formulas and witness calculations above were derived manually. No mathematical code, symbolic package, numerical array or solver was run. Read-only searches, text reads, file writes and final file hashes are administrative operations.

The official arXiv HTML for [Zhang--Jiang](https://arxiv.org/html/2410.12395) was checked at Definition 7 and the two primitive/dominant concatenation proofs. Those statements do not supply the displacement-surplus invariant considered here. The official HTML for [Chikhi](https://arxiv.org/html/2609.13765) was checked for the constant-schedule factorized certificate; it was not used as a theorem for the present perturbed variable schedule.

Two read-only searches used unsupported wildcard path syntax and returned a filename-syntax error; subsequent bounded reads and file enumeration supplied the needed public materials. Some combined read outputs were truncated, and the relevant displayed identities were reread or independently reconstructed. No error was treated as successful research or verification.

Two substantive approaches were used. No new grant, agent, model call, formal submission, service, truth-store operation or outward action was started. The final output is limited to the two authorized files in this directory. The mathematical outcome is incomplete, and all new results retain the UNVERIFIED label.
