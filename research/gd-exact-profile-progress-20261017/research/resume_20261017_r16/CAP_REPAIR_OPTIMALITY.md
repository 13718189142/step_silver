# Exact cost within the constant-gradient / stationary correction class

**UNVERIFIED parent analytical extension.** The underlying construction in HUBER_DATA_REPAIR.md was independently audited; the optimization and restricted-class lower bound in this note are additional manual derivations. They do not establish an all-word minimax lower bound.

Use the notation of HUBER_DATA_REPAIR.md: root H>1, prefix mass P, remaining prefix masses P_i, forward deficit A, and reverse deficits B_i. Consider an independently star-feasible auxiliary of any finite dimension which has one constant gradient g throughout the prefix, vanishes in gradient and function value after the root, and leaves every within-block interpolation residual zero. Its post-root position may be any minimizer. This is a restriction on the repair architecture, not on arbitrary admissible repairs.

## 1. Necessary scalar resources

Write s=||g||^2. The case s=0 can repair no nonzero deficit and is handled by the zero correction. For s>0 let ell be the root value minus s/2. The root star constraints give ell>=0 and
\[
\langle g,x_r^{\rm aux}\rangle\ge s+\ell.
\]
Physical updates and the zero within-prefix residuals imply
\[
x_i^{\rm aux}=x_r^{\rm aux}+P_i g,\qquad
f_i^{\rm aux}=s/2+\ell+P_i s.
\]
After the root, x_+^{aux}=x_r^{aux}-H g and both gradient and value are zero. Direct substitution into the two directed interpolation rows gives
\[
R^{\rm aux}_{i,+}=(H-1)s-\ell,\qquad
R^{\rm aux}_{+,i}=\ell+P_i s.
\]
Hence repairing the specified deficits requires
\[
\ell\ge\max\{0,\max_i(B_i-P_i s)\},\qquad
\ell\le(H-1)s-A.
\tag{1}
\]
These conditions are feasible exactly when
\[
\boxed{s\ge s_{\min}:=\max_{i\le r}\frac{A+B_i}{H-1+P_i}.}
\tag{2}
\]
Indeed i=r has P_r=0, so (2) already includes s>=A/(H-1). Every other inequality in (1) is equivalent to its corresponding term in (2). Deficits all zero permit s=0 and cost zero.

## 2. Optimal terminal-core cost

If the appended terminal position must also be zero, then x_r^{aux}=H g and x_0^{aux}=(P+H)g. Consequently every auxiliary in this restricted class pays exactly (P+H)^2 s. Thus its least possible squared initial distance is
\[
\boxed{M_{\rm core}^{\min}
=(P+H)^2\max_{i\le r}\frac{A+B_i}{H-1+P_i}.}
\tag{3}
\]
This lower bound is attained. Choose s=s_min>0 and ell=(H-1)s-A, which satisfies (1), and set eta=1+ell/s in [1,H]. The translated one-sided Huber construction realizes these data, including the endpoint cases eta=1 or eta=H; its derivative is continuous at both breakpoints. The root and every prefix query have conjugate height A. No additional dimension or hidden perpendicular initial component is needed.

The proof covers arbitrary auxiliary dimensions: terminal-core preservation forces x_r^{aux}=H g, so extra perpendicular directions cannot reduce the radius.

## 3. Optimal cost when a terminal flat displacement is allowed

For any auxiliary in the same class, Cauchy-Schwarz and the root star constraint give
\[
\|x_0^{\rm aux}\|^2
\ge \frac{\langle g,x_0^{\rm aux}\rangle^2}{s}
\ge \frac{((P+1)s+\ell)^2}{s}.
\]
Equality is attained by the unshifted one-sided Huber construction with x_r^{aux}=(1+ell/s)g. Its post-root point is in the flat minimum because ell<=(H-1)s.

For fixed s>=s_min, the least feasible ell is
\[
L(s)=\max\{0,\max_i(B_i-P_i s)\}.
\]
It follows that the exact restricted-class optimum is
\[
\boxed{
M_{\rm flat}^{\min}
=\inf_{s\ge s_{\min},\,s>0}
\frac{((P+1)s+L(s))^2}{s}.
}
\tag{4}
\]
This is a one-variable convex minimization with an explicit attained objective when any deficit is nonzero. In fact, writing S_i=P-P_i,
\[
\frac{((P+1)s+L(s))^2}{s}
=\max_{i\le r}\left[
\frac{B_i^2}{s}+2(1+S_i)B_i+(1+S_i)^2s
\right].
\tag{5}
\]
The root term i=r dominates the possible extra term (P+1)^2s, so no term is missing in (5). Each displayed function is convex on s>0; their maximum is convex and tends to infinity as s tends to infinity. The lower endpoint is positive for nonzero deficits.

For the conservative uniform reverse demand B_i=B>=0, the root term dominates all others. If A+B>0, (4) simplifies to
\[
M_{\rm flat}^{\min}=
\begin{cases}
4B(P+1),&B(H-P-2)\ge A(P+1),\\[2mm]
\dfrac{[A(P+1)+B(P+H)]^2}{(A+B)(H-1)},&B(H-P-2)<A(P+1).
\end{cases}
\tag{6}
\]
The first case with A+B>0 necessarily has B>0. It comes from the unconstrained optimizer s=B/(P+1); otherwise s=s_min=(A+B)/(H-1).

In particular, for A=B=Delta>0,
\[
M_{\rm flat}^{\min}=
\begin{cases}
4(P+1)\Delta,&H\ge2P+3,\\[1mm]
\dfrac{(2P+H+1)^2}{2(H-1)}\Delta,&1<H<2P+3.
\end{cases}
\tag{7}
\]
For a root sufficiently large relative to its prefix, the best flat-terminal cost is independent of H. The terminal-core variant does not enjoy that saving.

## 4. Limitation relevant to the original goal

The same correction has an exact history-energy price, which differs from its radius price. Its terminal gradient and value are zero, so its contribution to any terminal-gradient history coefficient is
\[
E_{\rm aux}=s(P+H)(P+2\eta-H).
\tag{8}
\]
One can obtain (8) either by summing the displayed cap values or by subtracting the terminal squared position from the initial squared position in the unshifted projection model. Translating all query positions does not change this history functional.

For the optimal terminal-core construction with ell=(H-1)s-A and eta=H-A/s,
\[
E_{\rm aux}=(P+H)^2s-2(P+H)A.
\tag{9}
\]
The second term is exactly the sum of the shifted prefix minimizer-row credits. For the balanced choice used in the original finite lemma, s=2Delta/(H-1) is a sufficient amplitude and eta=(H+1)/2, giving
\[
E_{\rm aux}=\frac{2(P+H)(P+1)}{H-1}\Delta.
\tag{10}
\]
These formulas provide a concrete test when repairing a negative-history prototype: its negative margin must exceed the total added history energy, not merely pass a free-matrix test.

These are exact prices within a stated family of independently admissible corrections. They do not show that arbitrary child witnesses can be joined at those prices while retaining the Zhang-Jiang resource bounds. In particular the defects A,B_i still come from actual child positions, values, gradients, and embeddings, and every recursive cost must be propagated back to the original initial point.

Adding one independent correction per recursive node can incur repeated costs. A proof of negligible total cost requires a genuine global estimate or shared coupling; the explicit finite prices alone do not provide it.
