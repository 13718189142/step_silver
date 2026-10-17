# R16 normal-geometry handoff

**UNVERIFIED analytical draft. Original target OPEN. Full-class E_j(49/100) remains unproved.**

The principal result is an all-depth exclusion of an actual-history nesting mechanism. On any one convex 1-smooth function, allow arbitrary finite dimension and the actual same-enclosing-m H_J. Suppose every right child along the left spine has constant gradient and both root endpoint interpolation rows vanish. Keeping the original interpolation row from the first new right query to the preceding left-spine endpoint gives

\[
\sum_{l=1}^{J-1}C_l^2\|p_l-p_{l+1}\|^2\le7C_J^2\|p_J\|^2.
\]

Therefore E_J^std>=-49epsilon C_J^2||p_J||^2 and

\[
E_J(49/100)\ge(51/100-49\epsilon)C_J^2\|p_J\|^2\ge0
\]

for every J, with no dimension or fixed-depth limitation. The same bound gives an actual retained dominance certificate of total 1+(32/17)(C_J-1) for each such trajectory, at any originally selected minimizer:

\[
2(f_{\rm end}-f_\star)/\|x_0-x_\star\|^2
\le[1+(32/17)(C_J-1)]^{-1}.
\]

This rules out affine-right, zero-endpoint-row nesting as a way to defeat the desired candidate bound. It does not bound W(H_J) over all trajectories. Full proof and constants: PROOF_ATTEMPT.md Sections 1--3. The key original-row inequality is (2.3); the finite-parameter loss is (3.2). The parent supplied the extension from projection envelopes to general convex 1-smooth functions through u_i=<g_i,x_i>-f_i-||g_i||^2/2; its row identity and extension were independently checked here.

Additional concrete checks:

* The literal R15 three-dimensional simplex is absorbed at its fourth physical step, for every actual m>=1536. All H_J with J>=3 then have final objective exactly zero and E_J(theta)>34. Equations (4.1)--(4.3) check every vertex support margin uniformly.
* At exact Silver equality, the normal port identity telescopes along the entire left spine to ||g_0||^2+c_0 sum||D_l||^2=C_J^2||q||^2. The direct Cauchy consequence still loses a factor 1+J/c_0 and is not a uniform reserve theorem.
* A symmetric-Huber critical phase closes at every depth: A=beta^2/c, M_j(k_j)=A, v_j=F_j(A), v_(j+1)=C_j-1+v_j/k_j, and v_j>=A C_j. Its actual core endpoint objective is at most 1/C_j^2. No claim covers all inverse-map phases.

The terminal-reserve branch found a different affine-right H_2 equality gadget; the earlier sign-based claim excluding all such gadgets was corrected and is not used here. The new mechanism theorem allows such a seed, but prevents its zero-row affine-right repetition from accumulating a damaging loss. An all-depth adversarial construction must use nonconstant right-child revisits or spend nonzero endpoint rows. Those alternatives are not resolved in this invocation.

Resource receipt: one fresh native invocation; two approaches; no mathematical programs, arrays, solvers, new agents/models, services, truth stores, formal submissions, publication, or shutdown. Only PROOF_ATTEMPT.md and HANDOFF.md were created. No full original-target candidate is supplied for formal verification.
