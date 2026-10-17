# A half-history sufficient condition for the separating PD join

**UNVERIFIED analytical draft, 2026-10-17. Original minimax target OPEN.**

This strengthens the conditional joining calculation in R12_RELAXED_PD_JOIN_LEAD_20261009.md. Its all-depth history hypothesis is weakened from theta=7/10 to theta=1/2, while the same physical words and dominance totals are retained. The new hypothesis is not proved here. No mathematical program, numerical solver, or verifier submission is used.

The same proof below in fact permits theta=49/100, with a uniform determinant margin, or the pointwise threshold theta=r^2 T with a positive semidefinite remainder.

## 1. Original-space inputs and identity

Normalize smoothness to one and translate the originally selected minimizer and its value to zero. For actual queries define
\[
Q_{ij}=2f_i-2f_j-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2\ge0,
\qquad
Q_{\star i}=-2f_i+2\langle g_i,x_i\rangle-\|g_i\|^2\ge0.
\]

A left word of physical mass s runs from x to v, with p=grad f(v). Set C=1+s and suppose its actual retained history satisfies
\[
E_L=\|x\|^2-\sum_L h_iQ_{\star i}-2s f(v)-\|v\|^2-\Gamma\|p\|^2\ge0,
\qquad
\Gamma\ge \tfrac12C^2-C.
\]
Equivalently,
\[
E_L=2\sum_L h_i(f_i-f(v))-\sum_L h_i(h_i-1)\|g_i\|^2-\Gamma\|p\|^2.
\]

The physical bridge has size b=1+k and sends v to w=v-bp. A right word of the same physical mass s runs to y. Let its fixed nonnegative certificate weights have total
\[
B_R=1+\frac{32}{17}s,\qquad U=\sum_R u_i g_i.
\]
The right hypothesis is
\[
D_R=\|w\|^2-\sum_Ru_iQ_{\star i}-2B_R f(y)-\|w-U\|^2\ge0.
\]
The sum includes the actual right terminal query. All quantities refer to the same function and original minimizer.

For parent weights (h_left, gamma, tau*u_right), put B_P=s+gamma+tau B_R and A_Q=sum_R u_i Q_(v,i). Direct expansion, retaining the actual child quantities, gives
\[
D_P=E_L+\left(\tau+\frac{s+\gamma}{B_R}\right)D_R
+\frac{s+\gamma}{B_R}A_Q
+A_q\|p\|^2+2B_q\langle p,U\rangle+C_q\|U\|^2,
\]
where
\[
A_q=\Gamma+s+2\gamma-\gamma^2,\quad
B_q=\frac{(s+\gamma)k}{B_R}+\tau(b-\gamma),\quad
C_q=\frac{s+\gamma}{B_R}-\tau(\tau-1).
\]

For reference, the algebra uses
\[
2B_R(f(v)-f(y))
=B_R\|p\|^2+2k\langle p,U\rangle+\|U\|^2+D_R+A_Q.
\]
Thus a positive semidefinite two-by-two matrix with entries A_q,B_q,C_q suffices.

## 2. A parameter choice adapted to the bridge

Suppose
\[
C>\frac73,\qquad \frac25<r:=\frac{k}{C}<\frac5{12}.
\]
These are the inherited ranges of the existing candidate hierarchy. Prescribe
\[
B_P=1+\frac{32}{17}(2s+b).
\]
Define
\[
d=32-\frac{15}{C},\qquad
A=d+32(1+r),\qquad
T=\frac{A}{d},
\]
\[
\tau=\frac{A-17}{d+17r},\qquad
t=r\tau,\qquad
\gamma=1+tC.
\]
Here d>179/7, d<32, and all denominators are positive. Moreover
\[
\tau-1=\frac{15(1+r)}{d+17r}>0.
\]
The prescribed weight sum holds exactly: B_R=Cd/17, B_P=CA/17, and
\[
17(1+t)+\tau d=A.
\]
Consequently, with v_0=(s+gamma)/B_R,
\[
v_0+\tau=T.
\]

At the minimal allowed input Gamma=theta*C^2-C, theta=1/2, the matrix becomes
\[
\frac{A_q}{C^2}=\theta-t^2,\qquad
\frac{B_q}{C}=r(T-\tau^2),\qquad
C_q=T-\tau^2.
\]
Indeed s+gamma=(1+t)C and b-gamma=(r-t)C. A larger Gamma only increases A_q. In particular,
\[
\frac{A_q C_q-B_q^2}{C^2}
=(\theta-r^2T)(T-\tau^2)
\]
at equality in the history threshold.

## 3. Uniform rational margins

First,
\[
T=1+\frac{32(1+r)}d
<1+\frac{32(17/12)}{179/7}=\frac{1489}{537}.
\]
Therefore
\[
r^2T<\frac{25}{144}\frac{1489}{537}
=\frac{37225}{77328},
\]
and
\[
\frac12-r^2T>\frac{1439}{77328}>\frac1{60}.
\]
The last comparison is 1439*60=86340>77328.

Second, an exact expansion gives
\[
T-\tau^2=
\frac{(1+r)\left[2d^2+d(353r-225)+9248r^2\right]}
{d(d+17r)^2}.
\]
Write F(d,r)=2d^2+d(353r-225)+9248r^2. On the indicated rectangle,
\[
\partial_d F=4d+353r-225
>\frac{716}{7}+\frac{706}{5}-225
=\frac{647}{35}>0,
\]
and partial_r F=353d+18496r>0. Hence
\[
F(d,r)>F(179/7,2/5)=\frac{789623}{1225}.
\]
The numerator in the displayed expression for T-tau^2 is greater than
\[
\frac75\frac{789623}{1225}
=\frac{5527361}{6125}>900.
\]
Its positive denominator is less than
\[
32(32+17\cdot5/12)^2
=\frac{439922}{9}<49000.
\]
It follows that
\[
C_q=T-\tau^2>\frac9{490}>\frac1{60}.
\]
Thus, even at the minimal history input,
\[
\boxed{A_qC_q-B_q^2>\frac{C^2}{3600}>0.}
\]
Since C_q>0 and the determinant is positive, A_q>0 also. The full two-vector remainder is positive definite for every ambient dimension. No interpolation row has been discarded with a negative coefficient.

The new bridge weight also dominates the physical bridge:
\[
\gamma-b=(t-r)C=r(\tau-1)C>0.
\]
If right physical weights dominate their physical steps, this property is preserved by the parent, since tau>1 and the left physical weights are unchanged.

### The sharper threshold and its scope

The preceding parameter choice works whenever theta>=r^2 T. In particular, theta=49/100 has
\[
\theta-r^2T>\frac{49}{100}-\frac{37225}{77328}
=\frac{66572}{7732800}>\frac1{120},
\]
and hence determinant greater than C^2/7200.

For these fixed physical masses and certificate totals, this is the smallest pointwise theta allowed by this specific two-vector retained identity. Indeed any gamma can be written as gamma=1+tC. The prescribed total forces v_0+tau=T, so for every such choice the determinant satisfies the exact identity
\[
\frac{\det}{C^2}
=(\theta-r^2T)(T-\tau^2)-T(t-r\tau)^2.
\]
If C_q=T-tau^2>0, positive semidefiniteness requires theta>=r^2T. If C_q=0, positive semidefiniteness forces B_q=0, so t=r tau and A_q>=0 again requires theta>=r^2T. A negative C_q is impossible. Our choice t=r tau attains the threshold and has C_q>0.

This optimality statement concerns only the retained identity with left weights h_left, one bridge weight, and a uniformly scaled right certificate of the prescribed total. It is not an optimality claim about the history inequality or arbitrary GD certificates.

## 4. Conditional all-depth consequence

For one enclosing integer m>=1536, retain the exact old parameters
\[
\epsilon=\frac1{4m},\quad \beta=1-\epsilon,\quad
c=(1+\sqrt2)(1+\epsilon),\quad a=\beta/c,
\]
\[
H_0=(),\qquad H_{j+1}=(H_j,1+ac^j,H_j),\qquad C_j=1+\sum H_j.
\]
The same parameters are used in every child. The old mass estimates give C_j>7/3 and 2/5<ac^j/C_j<5/12 for every j>=1.

The actual leaf h=1+a lies in (1,sqrt(2)). Its exact identity
\[
E_{h(h+1)}
=(h+1)Q_{01}+Q_{10}+(2-h^2)\|g_0-g_1\|^2\ge0
\]
supplies the half-history input, because
\[
h(h+1)-\left[\tfrac12(1+h)^2-(1+h)\right]
=\tfrac12(1+h)^2>0.
\]
The same identity supplies the existing leaf dominance weights
\[
u_0=h,\qquad u_1=1+\frac{15}{17}h,
\]
whose total is 1+(32/17)h and whose dominance residual is E_(u_1(u_1-1)). Indeed u_1(u_1-1)<h(h+1).

**Unproved hypothesis:** for every sufficiently large enclosing m and every 1<=j<m, the actual inherited word H_j satisfies
\[
\boxed{
2\sum_i h_i(f_i-f_{\rm end})
-\sum_i h_i(h_i-1)\|g_i\|^2
-\left[\tfrac12 C_j^2-C_j\right]\|g_{\rm end}\|^2\ge0
}
\]
for every convex 1-smooth trajectory.

If this hypothesis holds, the original-space identity and the new parameter choice inductively establish a dominance certificate on H_m with total 1+(32/17)S_m. It yields
\[
\mathcal W_{2^m-1}(H_m)
\le\frac1{1+(32/17)S_m}
<\frac{17}{16(1+2S_m)}.
\]
The accepted benchmark implication 931b9653ce0f7201 would then give a fixed-factor subsequence separation from the original Zhang-Jiang benchmark. An eventual-in-m history hypothesis suffices for this asymptotic conclusion.

This note proves only the conditional transfer and its explicit margins as a direct analytical draft. It does not establish the boxed all-depth hypothesis, does not supply an actual counterexample to the original conjecture, and has not been submitted to the verifier.

The boxed hypothesis may throughout be weakened further by replacing 1/2 with 49/100, or at each j by the pointwise value r_j^2 T_j. The leaf still satisfies each version, since these coefficients are less than one.
