# R16 terminal reserve: an exact all-depth coercivity identity, and the remaining perturbed gap

**UNVERIFIED analytical draft. The requested actual-parameter all-depth history inequality is NOT proved. No growing-depth counterexample to it is constructed. The original exact-profile problem remains OPEN.**

This invocation has one fresh grant, at most two substantive approaches, and a hard deadline of 2026-10-17 05:05:00 UTC. No mathematical program, array, symbolic package, solver, additional agent/model, service operation, truth-store write, formal submission, or publication was used. The two approaches were (i) a charged displacement/terminal-port invariant and (ii) an initial-gradient coercivity invariant with an explicit retained right-child payment. The second gives the all-depth exact-Silver result below. It does not extend automatically to the actual perturbed hierarchy.

## 1. The requested statement and source boundary

For one enclosing integer m >= 1536, the requested physical words use the SAME parameters in every descendant:

\[
\epsilon=(4m)^{-1},\qquad \beta=1-\epsilon,\qquad
c=(1+\sqrt2)(1+\epsilon),\qquad a=\beta/c,
\]
\[
H_0=(),\qquad H_{j+1}=(H_j,1+ac^j,H_j),\qquad
C_j=1+\sum H_j.
\]

For an actual trajectory of a word with capacity C and terminal gradient q, write

\[
\mathcal E(J)=2\sum_i h_i(f_i-f_e)
-\sum_i h_i(h_i-1)\|g_i\|^2-(J-C)\|q\|^2.
\tag{1}
\]

The missing premise is

\[
\mathcal E_j((49/100)C_j^2)\ge0
\qquad(1\le j<m)
\tag{2}
\]

for all actual finite-dimensional convex 1-smooth trajectories, eventually in m. The accepted benchmark implication identified by the parent does not supply (2).

The public sources read were OPERATOR.md, PROBLEM.md, the R16 WAVE.md, the R15 HALF_HISTORY_PD_JOIN.md and SILVER_DISPLACEMENT_COUNTEREXAMPLE.md, the nonunit-join and tree-energy R15 proof attempts, R15_PROGRESS.md, R12_RELAXED_PD_JOIN_LEAD_20261009.md, and the relevant public R13 proof sections. No worker-private memory was read. The memory registry was used only to preserve the distinction between handoff integrity and mathematical correctness.

All calculations below are manual. Original interpolation rows are

\[
Q_{ij}=2(f_i-f_j)-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2\ge0.
\tag{3}
\]

The arguments use only these actual rows and physical GD updates. They do not require the existence of a minimizer, so their stated scope includes the class in (2).

## 2. A leaf reserve controls the initial gradient

Let 1 < h <= sqrt(2), C=1+h, and let p=g_0 and q=g_1 be the gradients before and after the one physical step. Put

\[
r_h=h-1,\qquad z=2-h^2,\qquad
0\le\rho\le2-\sqrt2,\qquad d=\frac{\rho(h+2)}2.
\]

The exact leaf identity and the symmetric row sum are

\[
\mathcal E(C^2)=(h+1)Q_{01}+Q_{10}+z\|p-q\|^2,
\]
\[
Q_{01}+Q_{10}=2r_h\|p\|^2+2(2-h)\langle p,q\rangle-2\|q\|^2.
\]

Consequently

\[
\begin{aligned}
\mathcal E(C^2)+\rho C^2\|q\|^2-\rho\|p\|^2
={}&(h+1-d)Q_{01}+(1-d)Q_{10}\\
&+A\|p\|^2+2B\langle p,q\rangle+D\|q\|^2,
\end{aligned}
\tag{4}
\]

where

\[
A=\rho(h-1)+(1-\rho)z,\qquad
B=\rho-(1-\rho/2)z,\qquad
D=\rho C+(1-\rho)z.
\tag{5}
\]

The row coefficients are nonnegative because

\[
d\le\frac{(2-\sqrt2)(2+\sqrt2)}2=1.
\]

The FULL two-vector determinant is

\[
AD-B^2
=\rho z\{2(1-\rho)C-(1-3\rho/4)z\}\ge0.
\tag{6}
\]

For example, throughout this range rho < 3/5, C>2, and 0<=z<1. The expression in braces is greater than 8/5-1=3/5. For rho>0, A>0, so the last line of (4) can be written explicitly as

\[
A\left\|p+\frac BA q\right\|^2+\frac{AD-B^2}{A}\|q\|^2.
\]

For rho=0 it is simply z||p-q||^2. Hence (4) gives the full-class leaf inequality

\[
\boxed{\mathcal E((1-\rho)C^2)\ge\rho\|g_0\|^2.}
\tag{7}
\]

In particular rho=51/100 is admissible for the actual leaf h=1+a. This is an actual-parameter statement, not a limiting substitution.

At h=sqrt(2), put r=sqrt(2)-1 and C=1/r. Then z=0, and (4) simplifies to

\[
\mathcal E(C^2)+\rho C^2\|q\|^2-\rho\|p\|^2
=(h+1-d)Q_{01}+(1-d)Q_{10}
+\rho r\|p+Cq\|^2,
\quad d=\rho(C+1)/2.
\tag{8}
\]

## 3. The bridge identity with its full normal-displacement square

Take equal child capacities C, physical bridge b=1+k, and positions

\[
x\longrightarrow v\longrightarrow w=v-bp\longrightarrow y,
\qquad p=g(v),\quad q=g(y).
\]

Write

\[
G=w-y,\qquad Z=G+q,\qquad D_0=kp+Z=(v-p)-(y-q),
\]
\[
r=k/C\in(0,1),\qquad
\ell=\frac{1+r}{1-r},\qquad B_0=1+2\ell=\frac{3+r}{1-r},
\]
\[
A_v=\sum_R h_iQ_{vi},\qquad A_y=\sum_R h_iQ_{yi}.
\]

For arbitrary child coefficient J and nonnegative b_0,c_0, the R15 transfer identity is

\[
\begin{aligned}
&(b_0+c_0)\mathcal E_R(J)+b_0A_v+c_0A_y+b_0Q_{vy}+b_0C Q_{yv}\\
&\quad=2b_0Ck\|p\|^2+2b_0(C-k)\langle p,Z\rangle
+(c_0-b_0)\|Z\|^2-(b_0+c_0)J\|q\|^2.
\end{aligned}
\tag{9}
\]

Set c_0=b_0/r. Its complete square form is

\[
\begin{aligned}
&(b_0+b_0/r)\mathcal E_R(J)+b_0A_v+(b_0/r)A_y
+b_0Q_{vy}+b_0C Q_{yv}\\
&\quad=b_0C^2r(1+r)\|p\|^2
-b_0(1+r)J/r\,\|q\|^2
+b_0(1-r)/r\,\|D_0\|^2.
\end{aligned}
\tag{10}
\]

No assumption on the sign of E_R is needed for (9) or (10). The normal-geometry branch independently supplied the equivalent identity

\[
k^2\|p\|^2+\frac{C-k}{C+k}\|D_0\|^2
=J\|q\|^2+\mathcal E_R(J)
+\frac{kA_v+CA_y+kQ_{vy}+CkQ_{yv}}{C+k}.
\tag{11}
\]

Equivalence follows by multiplying (11) by b_0(1+r)/r. Thus the normal-displacement term is retained in the calculations below.

## 4. A complete all-depth exact-Silver reserve theorem

This section concerns the EXACT Silver hierarchy only:

\[
c_*=1+\sqrt2,\qquad r=1/c_*=\sqrt2-1,
\qquad \widehat C_j=c_*^j,
\]
\[
\widehat H_0=(),\qquad
\widehat H_{j+1}=(\widehat H_j,1+r\widehat C_j,\widehat H_j).
\]

Let E_j^std denote E_j(C_j^2) on this word. Then, for every finite depth j>=1, every actual convex 1-smooth history, and every rho in [0,2-sqrt(2)],

\[
\boxed{E_j^{\rm std}+\rho\widehat C_j^2\|g_e\|^2
\ge\rho\|g_0\|^2.}
\tag{12}
\]

Here is a recursive certificate with explicit nonnegative coefficients. At a parent use C=C_j, k=rC, C_P=C/r, ell=1/r, and B_0=1/r^2. The sharp standard identity is

\[
E_P^{\rm std}=E_L^{\rm std}+B_0E_R^{\rm std}
+\ell(A_v+A_y+Q_{vy}+kQ_{yv}).
\tag{13}
\]

It first establishes E_j^std>=0 by induction from the sharp leaf identity.

In (10), choose

\[
b_0=\frac\rho{r(1+r)},\qquad c_0=b_0/r,
\qquad J=C^2.
\]

Subtract this subcombination from (13), retaining the complete square from (10). The result is the exact identity

\[
\begin{aligned}
E_P^{\rm std}+\rho C_P^2\|q\|^2
={}&E_L^{\rm std}+\rho C^2\|p\|^2
+B_0(1-\rho)E_R^{\rm std}\\
&+\left(\ell-\frac\rho{r(1+r)}\right)(A_v+Q_{vy})\\
&+\left(\ell-\frac\rho{r^2(1+r)}\right)A_y\\
&+C\left(1-\frac\rho{r(1+r)}\right)Q_{yv}\\
&+\frac{\rho(1-r)}{r^2(1+r)}\|D_0\|^2.
\end{aligned}
\tag{14}
\]

All displayed coefficients are nonnegative. The tight restriction is

\[
\rho\le r(1+r)=2-\sqrt2.
\]

In particular, the right-child residual and its terminal-return row are explicitly paid for; they are not silently dropped when extracting the initial-gradient reserve. Iterating (14) down the left spine and applying (8) at the first leaf proves (12). This gives a nonnegative original-row certificate and all PSD remainders for every dimension and every exact depth.

The same identity shows, for each left-spine descendant with capacity C_d and terminal gradient p_d,

\[
E_j^{\rm std}+\rho C_j^2\|g_e\|^2
\ge E_d^{\rm std}+\rho C_d^2\|p_d\|^2.
\tag{15}
\]

This is a real use of terminal reserve. It does not assert E_std >= kappa A_end, the R15-disproved statement.

## 5. Why (14) has not proved the requested perturbed theorem

For the actual parameters, set

\[
R=2+r,\qquad \delta=B_0r^2-1=B_0-R^2.
\]

The exact sharp-coefficient split becomes

\[
E_P^{\rm std}=E_L^{\rm std}+B_0E_R^{\rm std}
+\ell(A_v+A_y+Q_{vy}+kQ_{yv})
+\delta C^2(\|q\|^2-\|p\|^2).
\tag{16}
\]

Suppose one tries to transfer a left terminal reserve rho_L by setting

\[
b_0=\frac{\rho_L+\delta}{r(1+r)},\qquad c_0=b_0/r.
\]

Provided these are nonnegative and fit in the available row coefficients, the leftover coefficient on the sharp right residual is exactly

\[
B_0-b_0-c_0=\frac{1-\rho_L}{r^2}.
\tag{17}
\]

If the right input were SHARP, the required parent reserve would obey

\[
\rho_P=
\frac{\rho_L+\delta(1-r^2)}{[r(2+r)]^2}.
\tag{18}
\]

However, the actual right input is precisely what is missing. Substituting only a weak right bound E_R^std+rho_R C^2||q||^2>=0 instead changes the necessary reserve accounting to

\[
\boxed{\rho_P=
\frac{\rho_L+(1-\rho_L)\rho_R+\delta(1-r^2)}{[r(2+r)]^2}.}
\tag{19}
\]

At the exact ratio r=sqrt(2)-1, the two-child case rho_L=rho_R=rho gives rho_P=2rho-rho^2. Thus (19) cannot justify keeping the fixed 0.51 terminal budget by substituting the weak premise in both children. This calculation is a boundary on the proposed use of (14), not a theorem that the physical target fails.

The positive initial-gradient term in (12) is insufficient by itself to repair this accounting. On the actual asymmetric-Huber witness from R15, the initial gradient is constant on the entire left child. The added term rho||g_start||^2 is O(1), whereas the loss between a retained weak left residual and its parent is O(epsilon C^2). A unit-left architecture does not acquire the needed growing-depth payment from (12).

## 6. Charged displacement and terminal ports: unresolved approach

For any word, put X=x_start-x_end and

\[
A_e=\sum_i h_iQ_{e i}.
\]

The exact relation is

\[
\mathcal E(J)+A_e=\|X+q\|^2-J\|q\|^2.
\tag{20}
\]

The investigated stronger input was a charged version such as

\[
E^{\rm std}+\rho C^2\|q\|^2\ge\sigma\|X+q\|^2,
\tag{21}
\]

with a positive sigma and an explicitly bounded rho. The R15 counterexample to a free displacement surplus does not refute (21), since (21) spends terminal reserve.

For a parent, the displacement appearing in (21) is Z_L+D_0, where Z_L is the left child's X+p. Its square contains the full term 2<Z_L,D_0>. Neither (11) nor initial-gradient coercivity controls this correlation. Retaining a child inequality with the same coefficient on ||Z_L||^2 leaves that cross term with no unused left square. Discarding it or treating Z_L as a favorable scalar would invalidate the full gradient-space remainder.

The complete terminal-port retargeting identity in R15 introduces V=sum_i v_i g_i and the correlation <V-Uq,v-y>. For the standard recursive certificate, the outgoing port has the explicit recursion

\[
V_P=B_0V_R+\ell G+\ell k p,
\qquad U_P=B_0U_R+\ell.
\tag{22}
\]

This right-spine structure is compatible with the explicit right-child payment in (14). No uniform port-coercivity bound sufficient for (21), and no valid nonuniform internal routing with its full PSD remainder, was obtained here. Equation (22) is not promoted to a missing inequality.

The parent suggested the candidate rho=1/2, sigma=sqrt(2)-1 after checking necessary examples. The actual construction in Section 7 disproves that candidate. It does not disprove (21) with a smaller positive sigma, and it does not disprove the requested weak history input (2).

## 7. An actual affine-right equality gadget disproves the proposed charged coefficient

The first scratch calculation for this section used the wrong sign in z_0-z_1 and incorrectly excluded creation of positive A_e with an affine right leaf. That claim was withdrawn immediately in messages to the parent and parallel branch. The correct original row has the opposite sign. The construction below replaces that claim completely.

Put

\[
h=\sqrt2,\quad C=1+h,\quad r=h-1=1/C,\quad
s=\sqrt{2h-1},\quad Y=Cs/2.
\]

For any gamma>0 define three gradients in R^3,

\[
a=(C^2/2,Y,\gamma),\qquad
p=(-C/2,Y,\gamma),\qquad
q=(1,0,\gamma),
\tag{23}
\]

and the full-dimensional simplex and fixed function

\[
K=\operatorname{conv}\{0,a,p,q\},\qquad
f(x)=\max_{g\in K}\{\langle x,g\rangle-\tfrac12\|g\|^2\}.
\tag{24}
\]

This f is finite-valued, convex, differentiable and 1-smooth, with grad f=P_K. The selected point zero is a minimizer with value zero.

Let

\[
N=2C\gamma+\frac C{2\gamma},
\]
\[
\begin{aligned}
y_0&=(0,hY,N),\\
y_1&=(0,0,N-h\gamma),\\
y_2&=(r/2,-Y,N-(h+2)\gamma),\\
y_3&=(-C/2,-Y,N-2C\gamma).
\end{aligned}
\tag{25}
\]

Set x_0=a+y_0, x_1=p+y_1, x_2=q+y_2, x_3=q+y_3. The physical updates are

\[
x_0-x_1=ha,\qquad x_1-x_2=2p,\qquad x_2-x_3=hq.
\tag{26}
\]

For example, a-p=(hC^2/2,0,0), y_0-y_1=(0,hY,h gamma), and their sum is ha. The other two updates follow directly from (25). Thus the physical word is exactly (sqrt(2),2,sqrt(2)).

Here is a complete support check valid for every gamma>0. Let M_i=y_i dot q. Then

\[
\begin{array}{c|c|c|c|c}
i&M_i&y_i\cdot a&y_i\cdot p&y_i\cdot q\\\hline
0&C/2+2C\gamma^2&M_0+hY^2&M_0+hY^2&M_0\\
1&C/2+(C+1)\gamma^2&M_1&M_1&M_1\\
2&h(1+\gamma^2)&M_2-(1/2+5h/4)&M_2-(1+3h/2)&M_2\\
3&0&-(10+7h)/4&0&0
\end{array}
\tag{27}
\]

Every row also has value zero at the vertex zero. All M_0,M_1,M_2 are positive. Therefore y_0 supports K at a, y_1 supports at p, and y_2,y_3 support at q. This proves P_K x_i=(a,p,q,q)_i for the ONE fixed function (24), including all interpolation constraints.

For the especially simple choice gamma=1/2, N=2C and the support values on (a,p,q) become

\[
\begin{array}{c|ccc}
0&3+9h/4&3+9h/4&1+h\\
1&1+3h/4&1+3h/4&1+3h/4\\
2&-1/2&-1-h/4&5h/4\\
3&-(10+7h)/4&0&0.
\end{array}
\tag{28}
\]

The right leaf is genuinely affine: its gradient is q at both physical queries. For the projection-envelope function,

\[
Q_{ij}=2\langle y_i,g_i-g_j\rangle.
\]

The support table shows that all rows in the standard H_2 certificate vanish: Q_01,Q_10,Q_23,Q_32,Q_12,Q_13,Q_31. The exact leaf remainders vanish because h=sqrt(2). Hence

\[
E_{H_2}^{\rm std}=0.
\tag{29}
\]

Nevertheless,

\[
A_e=hQ_{30}+2Q_{31}+hQ_{32}
=h\frac{10+7h}{2}=7+5h=C^3>0.
\tag{30}
\]

The parent capacity is C_P=1+h+2+h=C^2. Since ||q||^2=1+gamma^2, (20), (29), and (30) give

\[
\|X+q\|^2=C^4(1+\gamma^2)+C^3
=C^4(h+\gamma^2).
\tag{31}
\]

Thus a universal exact-Silver charged displacement inequality (21), even restricted to H_2, must satisfy

\[
\rho(1+\gamma^2)\ge\sigma(h+\gamma^2)
\quad\text{for every }\gamma>0.
\]

Letting gamma decrease to zero through positive values gives the necessary condition

\[
\boxed{\sigma\le\rho/\sqrt2.}
\tag{32}
\]

Every member of this limiting family is an actual finite-dimensional function with an attained minimizer; the limit gamma=0 is not used as an admissible function.

For the parent-suggested pair rho=1/2, sigma=r, the explicit choice gamma=1/2 already has

\[
E^{\rm std}+\tfrac12C_P^2\|q\|^2-r\|X+q\|^2
=\tfrac34C^4(r-\tfrac12)<0.
\tag{33}
\]

This is a counterexample to that simultaneous input. The target weak history remains strictly positive here: E_H2(49/100)=(51/100)C^4(1+gamma^2)>0. No counterexample to (2) follows.

The terminal gradient q is a vertex of K, whereas the R15 example's terminal gradient lay inside a nontrivial segment. The current terminal normal still supports the face containing p and q. Whether this new vertex geometry can be nested at growing depths requires every old support inequality to be checked; no nesting theorem is claimed in this file.

### 7.1 The same charged candidate fails on every requested actual H_2

Fix gamma=1/2, K, and x_0 from (23)--(25). Run the actual inherited word

\[
H_2(\epsilon)=(h_\epsilon,2-\epsilon,h_\epsilon),\qquad
h_\epsilon=1+r(1-\epsilon)/(1+\epsilon).
\]

In this subsection the subscript ref denotes the exact epsilon=0 TERMINAL quantity; thus y_ref is the vector y_3 in (25), not the initial normal y_0.

Its first/last step difference satisfies

\[
d=h-h_\epsilon=2r\epsilon/(1+\epsilon)<\epsilon.
\]

Every actual or exact step lies in [0,2]. For convex 1-smooth f, x -> x-t grad f(x) is nonexpansive on this interval, by expanding its squared difference and applying cocoercivity. Moreover max_K||g||<7/2. For the largest vertex a this follows from

\[
\|a\|^2=(23+16h)/4<49/4;
\]

the other two vertices have smaller squared norms. Comparing the three physical updates consequently gives

\[
\|x_e(\epsilon)-x_e(0)\|
\le(7/2)(2d+\epsilon)<11\epsilon,
\qquad \|q_\epsilon-q_{\rm ref}\|<11\epsilon.
\tag{34}
\]

Write C_epsilon=1+sum H_2(epsilon), so |C_epsilon-C^2|<3epsilon and C_epsilon<6. Put

\[
y_\epsilon=x_e(\epsilon)-q_\epsilon,\qquad
Z_\epsilon=x_0-y_\epsilon,\qquad
T_\epsilon=y_\epsilon+C_\epsilon q_\epsilon.
\]

Then

\[
\|y_\epsilon-y_{\rm ref}\|<22\epsilon,\quad
\|Z_\epsilon-Z_{\rm ref}\|<22\epsilon,\quad
\|C_\epsilon q_\epsilon-C^2q_{\rm ref}\|<71\epsilon,\quad
\|T_\epsilon-T_{\rm ref}\|<93\epsilon.
\tag{35}
\]

The exact norms satisfy ||x_0||=||T_ref||<8, ||Z_ref||<8, and ||C^2q_ref||<7. For reference,

\[
\|x_0\|^2=(105+74h)/4,\qquad
\|Z_{\rm ref}\|^2=113/4+20h,\qquad
\|C^2q_{\rm ref}\|^2=(5/4)(17+12h).
\]

For any trajectory on this projection-envelope function, all selected-zero minimizer rows vanish. Therefore

\[
E_\epsilon^{\rm std}=\|x_0\|^2-\|T_\epsilon\|^2.
\]

Define the charged residual actually being tested by

\[
F_\epsilon=E_\epsilon^{\rm std}
+\tfrac12\|C_\epsilon q_\epsilon\|^2-r\|Z_\epsilon\|^2.
\]

The elementary inequality | ||u||^2-||v||^2 | <= (2||v||+||u-v||)||u-v||, together with epsilon<=1/6144, gives

\[
|E_\epsilon^{\rm std}-E_{\rm ref}^{\rm std}|<1490\epsilon,
\]
\[
\left|\|C_\epsilon q_\epsilon\|^2-\|C^2q_{\rm ref}\|^2\right|<995\epsilon,
\qquad
\left|\|Z_\epsilon\|^2-\|Z_{\rm ref}\|^2\right|<353\epsilon.
\]

Since r<1/2,

\[
|F_\epsilon-F_{\rm ref}|<2164\epsilon<3/8.
\tag{36}
\]

On the other hand (33), C^4>33, and sqrt(2)<10/7 imply

\[
-F_{\rm ref}=\tfrac34 C^4(1/2-r)>\frac{99}{56}>\frac74.
\]

Thus the same one fixed function and start give

\[
\boxed{F_\epsilon<-11/8\qquad(m\ge1536).}
\tag{37}
\]

This uniformly excludes the particular charged input rho=1/2, sigma=sqrt(2)-1 on the ACTUAL same-enclosing-m H_2. It remains a counterexample to a proposed strengthening, not to E_H2(49/100)>=0.

It also excludes sigma=r when the full 51/100 terminal reserve is spent. Indeed (35) gives ||C_epsilon q_epsilon||<7+1/16, whose square is below 50. Increasing rho from 1/2 to 51/100 therefore adds less than 1/2 to F_epsilon. The resulting charged residual is still less than -7/8 for every m>=1536. A successful charged displacement input at this reserve must use a smaller sigma or a different quantity.

## 8. Source and completion status

The official [Grimmer--Shu--Wang paper](https://arxiv.org/html/2410.16249v2) was inspected at the definitions and equivalent s-composability condition. It supplies the standard sharp framework, not the charged reserve assertion (21) or the actual perturbed conclusion (2). The new derivations in Sections 2--7 use the displayed original-row identities, rather than importing an unverified stronger theorem from that source.

The concrete positive result of this invocation is (12), with its full recursive certificate (14), plus the actual-leaf identity (4). The concrete negative result is the actual static affine-right equality gadget (23)--(31), which forces (32) and excludes the proposed charged coefficient even on the actual perturbed H_2 by (37). These are manual all-function derivations or explicit-function checks, pending independent review. They are not Danus facts.

The requested all-depth actual-parameter input (2) remains unproved. There is no actual growing-depth counterexample to (2), no full-class objective bound for the perturbed H_m established here, and no candidate submitted for formal verification.
