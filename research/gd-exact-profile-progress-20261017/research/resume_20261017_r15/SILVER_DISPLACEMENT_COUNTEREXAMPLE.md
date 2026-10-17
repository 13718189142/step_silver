# An actual three-dimensional obstruction to a displacement-surplus invariant

**UNVERIFIED analytical draft.** The construction and its support/update arithmetic were independently checked by the nonunit-join branch within R15. No formal verifier was used.

This is a counterexample to the proposed strengthening
\[
E_{\rm std}\ge\kappa A_{\rm end},\qquad \kappa>0,
\]
already on the exact three-step Silver word. It does not contradict standard Silver convergence, the weaker fixed-theta history input, or the original minimax conjecture.

## 1. One fixed function and the physical word

Let
\[
r=\sqrt2-1,\quad h=1+r=\sqrt2,\quad
a=3+r,\quad b=\sqrt{1+3r},\quad C=5+2r.
\]
Thus \(r^2=1-2r\), and \(C=1+h+2+h\) is the capacity of the physical word \((h,2,h)\).

In \(\mathbb R^3\), define
\[
g_0=(2,0,1),\qquad p=(1,b,0),\qquad w=(1,-b,0),
\]
\[
K=\operatorname{conv}\{0,g_0,p,w\},\qquad
f(x)=\max_{g\in K}\{\langle x,g\rangle-\tfrac12\|g\|^2\}.
\]
The body is a full-dimensional simplex with zero as a vertex. The function is finite-valued, convex, differentiable, and 1-smooth, with gradient \(P_Kx\). Zero is an attained minimizer with value zero.

Set \(q=(1,rb,0)\), which lies on the segment \([p,w]\), and prescribe the normal vectors
\[
y_0=(4+3r,b,-3),\quad
y_1=(a,0,-a),\quad
y_2=(h,0,-a),\quad
y_3=(0,0,-a).
\]
The gradients are \((g_0,p,w,q)\), and the query positions are their sums with the corresponding normals:
\[
x_0=(6+3r,b,-2),\quad
x_1=(4+r,b,-a),\quad
x_2=(2+r,-b,-a),\quad
x_3=(1,rb,-a).
\]
They satisfy exactly
\[
x_1=x_0-hg_0,\qquad x_2=x_1-2p,\qquad x_3=x_2-hw.
\]

To verify that these are the actual gradients of the one fixed function, it suffices to check that \(y_i\) supports \(K\) at the proposed \(g_i\). The support values on its three nonzero vertices are

| normal | value at \(g_0\) | value at \(p\) | value at \(w\) |
|---|---:|---:|---:|
| \(y_0\) | \(5+6r\) | \(5+6r\) | \(3\) |
| \(y_1\) | \(a\) | \(a\) | \(a\) |
| \(y_2\) | \(r-1\) | \(h\) | \(h\) |
| \(y_3\) | \(-a\) | \(0\) | \(0\) |

Every row also includes the value zero at the vertex zero. The maximum is attained at the proposed gradient in each case; \(q\) lies in the maximizing segment for \(y_3\). Therefore \(P_Kx_i=g_i\) at every physical query. This verifies all interpolation constraints through an explicit function, not through a free Gram matrix.

## 2. The standard history residual is zero

Write \(S=C-1\), and define
\[
E_{\rm std}
=2\sum_{i=0}^2 h_i(f_i-f_3)
-\sum_{i=0}^2 h_i(h_i-1)\|g_i\|^2
-(C^2-C)\|q\|^2.
\]
For a projection-model trajectory with selected minimizer zero, every \(Q_{\star i}\) vanishes. Since \(x_3=q+y_3\), the exact history identity consequently simplifies to
\[
E_{\rm std}=\|x_0\|^2-\|Cq+y_3\|^2.
\]
Here
\[
\|x_0\|^2=50+21r,\qquad
\|q\|^2=13r-4,\qquad C^2=29+12r,\qquad
\|y_3\|^2=10+4r,\qquad \langle q,y_3\rangle=0.
\]
It follows that
\[
\|Cq+y_3\|^2
=(29+12r)(13r-4)+(10+4r)=50+21r.
\]
Hence \(E_{\rm std}=0\).

## 3. The proposed extra surplus is strictly positive

Use the same original interpolation rows as elsewhere,
\[
Q_{ij}=2(f_i-f_j)-2\langle g_j,x_i-x_j\rangle-\|g_i-g_j\|^2.
\]
In the projection model these rows equal
\[
Q_{ij}=2\langle y_i,g_i-g_j\rangle.
\]
Define
\[
A_{\rm end}=\sum_{i=0}^2h_iQ_{3i}.
\]
The support table gives \(Q_{30}=2a\) and \(Q_{31}=Q_{32}=0\). Therefore
\[
\boxed{A_{\rm end}=2ha=8+4r>0,\qquad E_{\rm std}=0.}
\]
The claimed inequality \(E_{\rm std}\ge\kappa A_{\rm end}\) is false for every \(\kappa>0\), even at this single exact Silver word. It cannot serve as an all-depth invariant without changing its statement.

The leaf inequality with \(\kappa=1/\sqrt2\) is nevertheless true, and several scalar Huber families also saturate it at larger root heights. The three-dimensional example shows why those cases did not establish the proposed general invariant.

For the genuinely requested weaker history coefficient \(\theta<1\), this example instead has
\[
E_\theta=E_{\rm std}+(1-\theta)C^2\|q\|^2>0.
\]
It therefore supplies no counterexample to the theta=49/100 input or to the original exact-profile objective problem.
