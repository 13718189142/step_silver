# R15 whole-tree energy: uniform coefficient localization and an actual obstruction to root-only repair

**UNVERIFIED manual mathematics. The requested all-depth history inequality and the original exact-profile minimax problem remain OPEN.**

This packet uses one direct analytical invocation and two approaches: (1) exact whole-tree expansion with uniform coefficient estimates; (2) actual-trajectory tests of the proposed repair. No mathematical program, solver, numerical array, additional model, service, truth-store operation, or formal submission was used.

The main result is a precise restriction on the repair, not a proof or counterexample to the requested history inequality. Every negative bare coefficient is confined to heights below 21, but the total repeated negative mass at height 2 grows exponentially relative to the root reserve. A literal Huber trajectory makes all retained interpolation rows and all leaf squares zero. Consequently, the negative mass cannot be absorbed from those rows and a bounded multiple of the root reserve after discarding the positive internal coefficients. Those positive coefficients must participate in an exact transfer across heights. A second actual Huber history disproves the parent's unmodified capped reciprocal physical invariant at depth 3. A seed increase of only \(4e\) repairs that particular witness and preserves scalar size above \(49/100\); its all-history validity remains open.

## 1. Target and notation

Fix the same enclosing integer throughout every descendant:

\[
m\ge1536,\qquad e=\frac1{4m},\qquad \beta=1-e,\qquad
c=(1+\sqrt2)(1+e),\qquad a=\frac\beta c.
\]

Let

\[
H_0=(),\qquad H_{j+1}=(H_j,1+k_j,H_j),\qquad
k_j=ac^j,\qquad C_j=1+\sum H_j.
\]

Thus

\[
C_0=1,\qquad C_1=2+a,\qquad C_{j+1}=2C_j+k_j.
\tag{1}
\]

For an actual convex 1-smooth GD history on a word of mass \(C-1\), endpoint gradient \(q\), and a scalar \(J\), write

\[
\mathcal E(J)=2\sum_i h_i(f_i-f_{\rm end})
-\sum_i h_i(h_i-1)\|g_i\|^2-(J-C)\|q\|^2.
\tag{2}
\]

The initially requested input is \(\mathcal E((7/10)C_j^2)\ge0\) for every \(1\le j<m\), every finite dimension, and every actual history. During this invocation the parent reported a new conditional PD join permitting the weaker coefficient \(49C_j^2/100\). That join is not audited here. None of the arguments below establishes either coefficient at all depths.

Use the original nonnegative interpolation rows

\[
Q_{ij}=2f_i-2f_j-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2.
\tag{3}
\]

The governing public sources read were the project PROBLEM.md, the completed R13 proof attempt, R12_RELAXED_PD_JOIN_LEAD_20261009.md, and the recovered R14_INTERRUPTED_NOTES.md. OPERATOR.md supplied the current authorization and deadline. The memory registry was used only to preserve the distinction between accepted facts, drafts, and handoff integrity.

## 2. Approach 1: exact tree expansion

### 2.1 One physical join

Consider a node whose equal children have depth \(l\), capacity \(C=C_l\), mass \(s=C-1\), and bridge excess \(k=k_l\). Let \(p\) be the actual left endpoint gradient, \(q\) the actual right endpoint gradient, and \(G\) the right physical displacement. Put

\[
\ell_l=\frac{C_l+k_l}{C_l-k_l},\qquad
B_l=1+2\ell_l=\frac{3C_l+k_l}{C_l-k_l}.
\tag{4}
\]

All denominators are positive; the bounds below give \(k_l/C_l<5/12\). With

\[
A_v=\sum_{i\in R}h_iQ_{v i},\qquad
A_y=\sum_{i\in R}h_iQ_{y i},
\]

the R13 identity, reconstructed by substituting its two displacement identities, is

\[
\begin{aligned}
\mathcal E_{l+1}(J_{l+1})={}&
\mathcal E_{l,L}(J_l)+B_l\mathcal E_{l,R}(J_l)\\
&+\ell_l(A_v+A_y+Q_{vy}+k_lQ_{yv})\\
&+(J_l-B_lk_l^2)\|p\|^2
 +(B_lJ_l-J_{l+1})\|q\|^2.
\end{aligned}
\tag{5}
\]

This is an equality on the physical history; neither child residual is assumed nonnegative.

Set

\[
P_1=C_1^2,\qquad P_{l+1}=B_lP_l,\qquad
D_l=P_l-B_lk_l^2,\qquad A_l=P_l-C_l^2.
\tag{6}
\]

The choice \(J_l=P_l\) eliminates the last term in (5). Every leaf retains the exact identity, with \(h=1+a\),

\[
\mathcal E_1(C_1^2)
=(h+1)Q_{01}+Q_{10}+(2-h^2)\|g_0-g_1\|^2.
\tag{7}
\]

Here \(1<h<\sqrt2\), so every retained leaf term is nonnegative.

### 2.2 The full weighted identity, including repetitions

In a depth-\(J\) tree give the root weight 1. At a split with child depth \(l\), the left child keeps its parent's weight and the right child receives \(B_l\) times that weight. Let \(W_v\) denote the resulting weight of a node. Then

\[
\begin{aligned}
\mathcal E_J(\theta C_J^2)={}&\mathcal R_J+\mathcal L_J\\
&+\sum_{l=1}^{J-1}D_l
  \sum_{\substack{v:\text{child depth }l}}W_v\|p_v\|^2\\
&+(P_J-\theta C_J^2)\|g_{\rm end}\|^2.
\end{aligned}
\tag{8}
\]

Here \(\mathcal R_J\) is the sum of all original rows from (5) and (7), with their positive inherited coefficients; \(\mathcal L_J\) is the weighted sum of the squares in (7). Both are nonnegative on every actual trajectory. A shared physical endpoint may appear in several original-row terms; no such row or inherited weight has been deleted.

The total inherited weight of the height-\(l\) bare endpoint terms is exactly

\[
\Omega_{l,J}=\prod_{r=l+1}^{J-1}(1+B_r).
\tag{9}
\]

To see (9), start with one node of height \(l+1\). Each additional ancestor contributes the sum of its two branch weights, \(1+B_r\). This counts all repeated copies, rather than treating a low subtree as though it occurred only once.

There is also a useful exact conservation identity. Define

\[
\Delta_l=B_lk_l^2-C_l^2.
\]

Direct multiplication using \(C_{l+1}=2C_l+k_l\) gives

\[
B_lC_l^2-C_{l+1}^2=\Delta_l.
\]

Consequently

\[
A_{l+1}=B_lA_l+\Delta_l,\qquad
D_l=(1+B_l)A_l-A_{l+1}.
\tag{10}
\]

Since \(A_1=0\), multiplication by (9) and telescoping yield

\[
\boxed{\sum_{l=1}^{J-1}D_l\Omega_{l,J}=C_J^2-P_J.}
\tag{11}
\]

Equation (11) is the constant-gradient cancellation that any global repair must preserve.

## 3. Uniform coefficient bounds

These estimates apply to the full parameter interval \(0\le e\le1/6144\); they are not fixed-depth Taylor claims.

### 3.1 Closed capacities and product bounds

Let \(c_0=1+\sqrt2\), \(t=2/c\), and

\[
\zeta=\frac{(5+2\sqrt2)e+c_0^2e^2}{1-e},\qquad z_l=\zeta t^l.
\]

Solving (1) gives

\[
C_l=c^l\frac{1+z_l}{1+\zeta},\qquad
\frac{k_l}{C_l}=\frac{c-2}{1+z_l},\qquad
B_l=\frac{c+1+3z_l}{3-c+z_l}.
\tag{12}
\]

Elementary rational bounds give

\[
0\le\zeta<9e,\quad t<5/6,\quad
2/5<a<1/2,\quad c<29/12,\quad
0<k_l/C_l<5/12,\quad B_l<6.
\tag{13}
\]

For example, \(c_0<169/70\) follows from \(\sqrt2<99/70\), and multiplication by \(1+1/6144\) gives \(c<29/12\). The expression for \(\zeta\) then gives its stated bound directly. In particular,

\[
\sum_{r=1}^{\infty}z_r<45e.
\tag{14}
\]

Put

\[
B_\infty=\frac{c+1}{3-c},\qquad R=\frac{B_\infty}{c^2}.
\]

The exact factorization

\[
\frac{B_r}{B_\infty}
=1-\frac{4(c-2)z_r}{(c+1)(3-c+z_r)}
\ge1-z_r
\]

uses \(4(c-2)/[(c+1)(3-c)]<1\), which follows already from (13). Therefore

\[
\prod_{r=1}^{l-1}\frac{B_r}{B_\infty}\ge1-45e.
\tag{15}
\]

The product inequality follows inductively from \(\prod(1-u_r)\ge1-\sum u_r\) for nonnegative \(u_r\) whose sum is below 1.

Two scalar prefactors are controlled by logarithmic differentiation. Their values at \(e=0\) are 1, and

\[
\frac{d}{de}\log\frac{C_1^2}{B_\infty\beta^2}>-4,
\qquad
\frac{d}{de}\log\frac{C_1^2}{c^2}>-3.
\]

For the first derivative, use \(|C_1'|<1\), \(C_1>12/5\), \(c_0<5/2\), \(3-c>7/12\), \(c+1>3\), and \(2/\beta\ge2\). The resulting lower bound is \(-83/21>-4\). The second derivative is bounded below by \(-5/6-2>-3\). Hence

\[
\frac{C_1^2}{B_\infty\beta^2}\ge1-4e,
\qquad \frac{C_1^2}{c^2}\ge1-3e.
\tag{16}
\]

Finally,

\[
\frac{d}{de}\log R
=\frac{c_0}{c+1}+\frac{c_0}{3-c}-\frac{2}{1+e}>\frac52.
\]

Indeed the first term is greater than \(2/3\), the second greater than 4, and the last at least \(-2\). Thus

\[
R\ge1+(5/2)e.
\tag{17}
\]

### 3.2 Every height at least 21 has a positive bare coefficient

Using \(B_l\le B_\infty\), (15)--(17) give

\[
\begin{aligned}
\frac{P_l}{B_lk_l^2}
&=\frac{C_1^2}{B_l\beta^2}R^{l-1}
  \prod_{r=1}^{l-1}\frac{B_r}{B_\infty}\\
&\ge(1-49e)[1+(5/2)e]^{l-1}.
\end{aligned}
\tag{18}
\]

For \(l\ge21\), Bernoulli's inequality bounds the right side below by

\[
(1-49e)(1+50e)=1+e-2450e^2>1
\]

whenever \(0<e\le1/6144\). Therefore

\[
\boxed{D_l>0\quad\text{for every }l\ge21.}
\tag{19}
\]

This establishes the previously conjectural bounded-height localization, with an explicit bound 21. It does not establish positivity of (8).

Similarly, (12) and (15)--(17) give

\[
\begin{aligned}
\frac{P_l}{C_l^2}
&=\frac{C_1^2}{c^2}R^{l-1}
  \prod_{r=1}^{l-1}\frac{B_r}{B_\infty}
  \frac{(1+\zeta)^2}{(1+z_l)^2}\\
&\ge1-48e.
\end{aligned}
\tag{20}
\]

Thus the root coefficient in (8) is positive for both \(\theta=7/10\) and \(\theta=49/100\).

### 3.3 Height 2 is uniformly negative

Write \(F_l=D_l/C_l^2\), and use a prime for differentiation with respect to \(e\) at fixed \(l\). Differentiating (12) at zero yields, with \(t_0=2/c_0\),

\[
\left.\frac{d}{de}\frac{P_l-C_l^2}{C_l^2}\right|_{e=0}
=2\sqrt2(l-1)-(24-4\sqrt2)(1-t_0^{l-1}),
\tag{21}
\]

and therefore

\[
F_l'(0)=2\sqrt2(l-1)-(32+2\sqrt2)
 +(48-8\sqrt2)t_0^{l-1}.
\tag{22}
\]

In particular,

\[
F_2'(0)=112\sqrt2-160<-3/2.
\tag{23}
\]

For completeness, a uniform second-derivative bound makes this a finite-parameter conclusion. Let

\[
r_1=\beta/C_1,\quad r_2=\beta c/C_2,\quad u=C_1/C_2,
\quad B(r)=(3+r)/(1-r).
\]

Then \(F_2=B(r_1)u^2-B(r_2)r_2^2\). On the full interval in question,

\[
\begin{gathered}
|r_1'|<3/5,\quad |r_1''|<9/10,\quad
|r_2'|<1/4,\quad |r_2''|<3/2,\\
0<u<1/2,\quad |u'|<5/12,\quad |u''|<9/8,\\
B<6,\quad |B'|<12,\quad |B''|<42.
\end{gathered}
\tag{24}
\]

Here the derivatives of \(B\) are with respect to its argument. The bounds follow by quotient differentiation from \(C_1>12/5\), \(C_2>23/4\), \(|C_1'|<1\), \(|C_1''|<2\), \(|C_2'|<3\), \(|C_2''|<4\), and
\(\beta c=c_0(1-e^2)\), whose first derivative has magnitude below \(1/1000\) and second derivative below 5.

The second derivative of the first term in \(F_2\) has magnitude below 22. For \(V(r)=B(r)r^2\), the bounds \(|V'|<9\), \(|V''|<93/2\) make the second derivative of \(V(r_2)\) smaller than \(525/32<17\). Consequently \(|F_2''|<64\). Taylor's formula and (23) now give

\[
F_2(e)\le-\tfrac32e+32e^2<-e,
\qquad
\boxed{D_2<-e C_2^2.}
\tag{25}
\]

Thus the negative low-level mass is present throughout the requested enclosing-parameter range; it is not only a possible sign seen in a fixed-depth derivative.

## 4. Approach 2: an actual trajectory obstruction to root-only absorption

### 4.1 The exact Huber history

Use the single scalar convex 1-smooth function

\[
f(x)=\begin{cases}x^2/2,&|x|\le1,\\ |x|-1/2,&|x|\ge1.\end{cases}
\]

For a depth-\(J\) word start at \(x_0=C_J\). Every query is

\[
x_i=1+\sum_{t=i}^{N_J-1}h_t\ge1,
\qquad g_i=1,
\qquad x_{N_J}=1.
\tag{26}
\]

These are the actual updates of the same static function. Every original row \(Q_{ij}\) between these queries is zero, not just the rows used in (8). Every leaf square is also zero. Directly from (2),

\[
\mathcal E_J(\theta C_J^2)=(1-\theta)C_J^2>0.
\tag{27}
\]

This is not a counterexample to the desired inequality.

### 4.2 Exponentially repeated negative mass

For this history, the magnitude of the height-2 negative contribution in (8) is

\[
N_{2,J}=(-D_2)\prod_{r=3}^{J-1}(1+B_r).
\]

Equations (6), (13), and (25) imply

\[
\begin{aligned}
\frac{N_{2,J}}{P_J}
&>e\frac{C_2^2}{C_1^2B_1B_2}
  \prod_{r=3}^{J-1}\left(1+\frac1{B_r}\right)\\
&>\frac e8\left(\frac76\right)^{J-3}.
\end{aligned}
\tag{28}
\]

For the last prefactor use \(C_2>23/4\), \(C_1<5/2\), and \(B_1B_2<36\), giving \(C_2^2/(C_1^2B_1B_2)>529/3600>1/8\).

Take \(J=m-1\). Since \(e=1/(4m)\), the right side of (28) tends to infinity with \(m\). The positive root reserve is at most \(P_J\), while the original-row energy and the leaf-square energy on this history are both zero. Therefore there is no constant \(K\), independent of \(m,J\), for which the negative height-2 mass can be bounded by

\[
K\{\mathcal R_J+\mathcal L_J+P_J\|g_{\rm end}\|^2\}
\tag{29}
\]

on every actual history. Replacing \(P_J\) by the smaller positive root reserve only strengthens the contradiction. Adding nonnegative gradient-difference squares that vanish on constant gradients does not change this obstruction.

This rules out the concrete strategy of discarding the positive internal coefficients and then absorbing all repeated low-level defects into the original rows, leaf squares, and a bounded root budget. It also explains why finite-depth coercivity does not alone supply the needed all-depth estimate: the repetition weights in (28) must enter the argument.

### 4.3 A bounded subtree cannot simply be certified at coefficient P

On the same constant-gradient trajectory restricted to any subtree,

\[
\mathcal E_l(P_l)=C_l^2-P_l=-A_l.
\tag{30}
\]

The derivative formula (21), for example at \(l=4\), is positive. Hence \(A_4>0\) for all sufficiently small positive \(e\). More generally (21) is positive at every fixed sufficiently large height. Thus a fixed low block cannot be replaced by a universally nonnegative \(\mathcal E_l(P_l)\) merely because the later bare coefficients are nonnegative. The endpoint debt in (30) must remain in any such replacement.

The full affine cancellation is exactly (11): the exponentially large positive and negative internal masses leave \(C_J^2-P_J\), and adding the root coefficient leaves (27). No negative coefficient or negative free-vector test is being promoted into a real counterexample to the target.

## 5. Additional actual-function check within Approach 2

A symmetric Huber trajectory has an exact scalar range calculus. For a single excess \(k=h-1>0\), the largest absolute image of an interval \([-R,R]\) is

\[
M_k(R)=\begin{cases}
kR,&0\le R\le1,\\
k,&1\le R\le1+2k,\\
R-(1+k),&R\ge1+2k.
\end{cases}
\tag{31}
\]

The update is continuous and odd, so the image of the interval is the entire interval \([-M_k(R),M_k(R)]\). Range maps therefore compose exactly, including under the word recursion. This supplies actual Huber trajectories for every value in the calculated range, rather than arbitrary gradient vectors.

For every depth one obtains

\[
M_{H_j}(R)\le1\quad(0\le R\le C_j),\qquad
M_{H_j}(R)=R-(C_j-1)\quad(R\ge C_j).
\tag{32}
\]

The induction uses \(k_j<C_j\). If the first child input is below \(C_j\), its range is at most 1 and the bridge range at most \(k_j\). If the input lies between \(C_j\) and \(C_{j+1}\), the first child tail and the bridge have range at most \(C_j\). Beyond \(C_{j+1}\), both child tails and the bridge tail apply.

This range calculation does not yield the relative-radius bound needed for (2); knowing that the terminal gradient is at most 1 is insufficient. It did not supply an actual violating family. No full-class claim is drawn from it.

## 6. The capped reciprocal coefficient has sufficient scalar size

### 6.1 Uniform scalar bound

The parent proposed the following capped candidate, to avoid the affine obstruction at early depths:

\[
\bar P_1=C_1^2,\qquad
\bar P_{l+1}=\max\{C_{l+1}^2,B_l\bar P_l\},\qquad
J_l^{\rm cap}=\frac{C_l^4}{\bar P_l}.
\tag{33}
\]

The following scalar estimate is uniform and does not assume a history inequality. Let \(Z_l=\bar P_l/C_l^2\), so \(Z_l\ge1\). Then

\[
Z_{l+1}=\max\{1,q(r_l)Z_l\},\qquad
r_l=k_l/C_l,\qquad
q(r)=\frac{3+r}{(1-r)(2+r)^2}.
\tag{34}
\]

For \(0\le r<1\),

\[
\frac{d}{dr}\log q(r)
=\frac{2(r^2+4r+1)}{(3+r)(1-r)(2+r)}>0.
\]

Since \(r_l<c-2\),

\[
q(r_l)\le q(c-2)=\frac{c+1}{c^2(3-c)}=R.
\]

Here \(R>1\) by (17), and \(RZ_l\ge1\). Induction in (34) therefore gives the exact bound

\[
\boxed{\frac{J_l^{\rm cap}}{C_l^2}=Z_l^{-1}\ge R^{-(l-1)}.}
\tag{35}
\]

At zero, \(\log R=0\) and \((\log R)'=2\sqrt2\). On \(0\le e\le1/6144\),

\[
\begin{aligned}
(\log R)''
&=c_0^2\left[-\frac1{(c+1)^2}+\frac1{(3-c)^2}+\frac2{c^2}\right]\\
&<6\left(\frac{144}{49}+\frac{25}{72}\right)<20.
\end{aligned}
\]

Taylor's formula yields \(\log R\le2\sqrt2 e+10e^2\). Hence, simultaneously for every \(1\le l<m\),

\[
\boxed{\frac{J_l^{\rm cap}}{C_l^2}
\ge\exp\!\left(-\frac1{\sqrt2}-\frac52e\right)>\frac{49}{100}.}
\tag{36}
\]

The strict rational comparison in (36) needs no numerical evaluation of the exponential. First,

\[
\frac1{\sqrt2}+\frac5{12288}
<\frac{99}{140}+\frac5{12288}<\frac{71}{100}.
\]

For \(0\le x<3\), the elementary factorial bound \(n!\ge2\cdot3^{n-2}\) for \(n\ge2\) gives

\[
e^x\le1+x+\frac{x^2}{2(1-x/3)}.
\]

At \(x=71/100\), the last expression is \(93441/45800<100/49\), because \(93441\cdot49=4578609<4580000\). This proves the last inequality of (36).

In particular,

\[
\liminf_{m\to\infty}\ \min_{1\le l<m}
\frac{J_l^{\rm cap}}{C_l^2}\ge\exp(-1/\sqrt2).
\tag{37}
\]

Thus this candidate has enough scalar size for the parent's reported \(49/100\) conditional PD join, already for every \(m\ge1536\). The physical assertion does not follow from that size. In fact, the next subsection gives a real counterexample to the unmodified candidate.

### 6.2 An actual depth-3 counterexample to the unmodified capped invariant

Write \(r_0=1/c_0\). Exact algebra gives

\[
c_0\beta-C_1=e\left[-c_0+\frac{2r_0}{1+e}\right]<0,
\]

and

\[
c_0\beta c-C_2
=e\left[1+\frac{4r_0}{1+e}-c_0^2e\right]>0.
\tag{38}
\]

Thus \(r_1<r_0<r_2\) throughout the actual parameter interval. Since \(q\) in (34) is increasing and \(q(r_0)=1\), the cap recursion gives

\[
\bar P_2=C_2^2,\qquad \bar P_3=B_2C_2^2.
\tag{39}
\]

Set \(r=r_2\), and use the single asymmetric Huber function

\[
f_r(x)=\begin{cases}
-rx-r^2/2,&x\le-r,\\
x^2/2,&-r\le x\le1,\\
x-1/2,&x\ge1.
\end{cases}
\tag{40}
\]

Start the actual word \(H_3=(H_2,1+k_2,H_2)\) at \(x_0=C_2\). The left child stays on the positive affine branch with gradient 1 and ends at 1. The bridge sends it to \(-k_2\). The right child stays on the negative affine branch with gradient \(-r\) and ends at \(-r\), because \(k_2=C_2r\). These statements hold at every physical query, since a prefix of either child has mass between 0 and \(C_2-1\).

Every minimizer row at the original minimizer zero vanishes. Telescoping (or direct substitution in (2)) therefore gives

\[
\begin{aligned}
\mathcal E_3(J_3^{\rm cap})
&=C_2^2-J_3^{\rm cap}r^2\\
&=C_2^2\left[1-\frac{r^2(2+r)^4}{B(r)}\right]<0.
\end{aligned}
\tag{41}
\]

Here is an exact sign check. Let \(R_*=2+r\), \(t_*=rR_*\), and \(u_*=(1+r)/(1-r)\). Then

\[
B(r)-R_*^2=u_*(t_*-1),
\]

so

\[
r^2R_*^4-B(r)
=(t_*-1)\{(t_*+1)R_*^2-u_*\}>0.
\tag{42}
\]

Indeed \(r>r_0\) gives \(t_*>1\), while \(r<5/12\) gives \(u_*<17/7\), and the other term in braces is greater than 8. This sign factorization was also obtained independently by the parent during the invocation.

The proposed unmodified capped reciprocal physical invariant is therefore false, for every \(m\ge1536\), at the admissible fixed internal depth 3. This does not contradict the R13 fixed-depth robustness result for a fixed coefficient \(7/10\): the reciprocal candidate approaches the sharp standard coefficient 1 as \(m\) grows. It also does not refute the requested \(7/10\) or newly reported \(49/100\) history inequalities; the same witness has ample positive reserve at either fixed coefficient.

### 6.3 A seed increase of 4e repairs this witness and keeps scalar sufficiency

The obstruction (41) does not rule out an \(O(e)\) reduction of the candidate. In particular, define

\[
\bar P^{(4)}_1=(1+4e)C_1^2,\qquad
\bar P^{(4)}_{l+1}=\max\{C_{l+1}^2,B_l\bar P^{(4)}_l\},\qquad
J_l^{(4)}=C_l^4/\bar P_l^{(4)}.
\tag{43}
\]

The scalar induction for (35) now gives

\[
\frac{J_l^{(4)}}{C_l^2}
\ge\frac{R^{-(l-1)}}{1+4e}
\ge\exp\!\left(-\frac1{\sqrt2}-\frac{13}{2}e\right)>
\frac{49}{100}
\quad(1\le l<m).
\tag{44}
\]

For the final comparison, \(99/140+13/12288<71/100\), so the same rational exponential bound used for (36) applies.

It remains to check the advertised repair of (41). Put

\[
K(r)=\frac{r^2(2+r)^4}{B(r)}.
\]

On \(r_0\le r\le5/12\),

\[
\frac{d}{dr}\log K(r)
=\frac2r+\frac4{2+r}-\frac4{(1-r)(3+r)}<7.
\]

Since \(K(r_0)=1\) and (24) implies \(0<r_2-r_0<e/4\),
\(K(r_2)\le\exp(7e/4)\). Also \(|(\log q)'|<3\) on the actual ratio interval and \(|r_1'|<3/5\), so \(q(r_1)\ge\exp(-9e/5)\). Consequently

\[
\frac{K(r_2)}{q(r_1)}\le\exp(71e/20)\le1+4e.
\tag{45}
\]

For the last inequality, use \(\exp z\le1/(1-z)\) for \(0\le z<1\), and

\[
(1+4e)(1-71e/20)=1+(9/20)e-(71/5)e^2\ge1
\]

on \(e\le1/6144\). The recursion (43) then yields

\[
\frac{\bar P^{(4)}_3}{C_3^2}
\ge q(r_2)q(r_1)(1+4e)
\ge q(r_2)K(r_2)
=[r_2(2+r_2)]^2.
\tag{46}
\]

Equation (46) is exactly the condition making the actual Huber residual in (41) nonnegative after replacing \(J_3^{\rm cap}\) by \(J_3^{(4)}\). The leaf coefficient is also valid because \(J_1^{(4)}<C_1^2\). No claim is made that (43) repairs every fixed-depth witness or gives a valid all-depth history invariant. It repairs the displayed counterexample while preserving the scalar margin needed by the parent's new join.

## 7. Remaining closure and resource receipt

The following parts are concrete manual derivations in this packet, pending independent verification:

1. The weighted identity (8), its exact repetition factors (9), and the conservation law (11).
2. Uniform positivity of every bare coefficient at height at least 21 and positivity of the root reserve, (19)--(20).
3. Uniform negativity of the height-2 coefficient, (25).
4. The actual Huber obstruction (28)--(29) to root-only absorption after discarding positive internal terms.
5. The capped reciprocal coefficient's uniform scalar lower bound (36), which exceeds the parent's new sufficient threshold \(49/100\).
6. An actual depth-3 counterexample (41) to that unmodified capped physical invariant, and the specific seed correction (43) that repairs this witness while retaining (44).

The missing result is a transfer of positive internal coefficients across heights that remains nonnegative on all actual histories and uses the original interpolation rows with their valid signs. Neither (19) nor the obstruction (29) settles that result. No actual history with \(\mathcal E_J((7/10)C_J^2)<0\), or with the newly suggested coefficient \(49C_J^2/100\), is constructed.

The uncapped coefficient \(C_j^4/P_j\) cannot be used at early depths, since \(P_2<C_2^2\). The unmodified capped variant has the rigorous manual scalar estimates (35)--(37), but its physical history inequality is false by (41). The seed-corrected variant (43) remains an unproved all-history candidate. The scale \(\exp(-1/\sqrt2)\) is a proved scalar product bound here, not a certified history coefficient.

One invocation; at most two substantive approaches; mathematical programs, solvers, numerical arrays, additional agents/models, services, and formal submissions: zero. The only files created by this worker are PROOF_ATTEMPT.md and HANDOFF.md in its designated directory. No worker-private memory was read. No claim of original-target resolution, finalization, publication, or verifier acceptance is made.
