# R17 progress: mixed right-child mechanisms, and the cost of restoring the proposed lower bound

**Original exact-profile minimax target: OPEN. Application Goal: PAUSED at the operator's explicit October 17 request.**

This round made mathematical progress, but did not establish either the requested all-word matching lower bound or an unrestricted asymptotic separation. All new results remain UNVERIFIED in Danus. One finished structural lemma received a separate independent manual audit; that is explicitly distinguished below.

## 1. The strongest actual-parameter result

Use one fixed enclosing m>=1536 in every descendant:
\[
e=(4m)^{-1},\quad\beta=1-e,\quad
c=(1+\sqrt2)(1+e),\quad a=\beta/c,
\]
\[
H_0=(),\quad H_{j+1}=(H_j,1+ac^j,H_j),\quad
C_j=1+\sum H_j.
\]
For an actual trajectory define
\[
E_J^{\rm std}
=2\sum_i h_i(f_i-f_e)-\sum_i h_i(h_i-1)\|g_i\|^2
-(C_J^2-C_J)\|g_e\|^2.
\]

The completed mixed theorem allows each entire right child along the left spine, independently at each level, to have either constant gradients or constant normal coordinates x_i-g_i. It permits arbitrary switches between these two mechanisms. Endpoint interpolation rows need not vanish. Under exactly this structural hypothesis,
\[
E_J^{\rm std}\ge-\rho_m C_J^2\|g_e\|^2,\qquad
\rho_m=\frac{3+63\lceil\log_2(4m)\rceil}{4m}<\frac4{25},
\]
simultaneously for every finite depth J. Hence the needed history coefficient 49/100 is valid on this class. A direct certificate using the original selected minimizer gives
\[
\frac{2(f_e-f_\star)}{\|x_0-x_\star\|^2}
\le\frac1{1+(32/17)(C_J-1)}.
\]

The mechanism is quantitative. A maximal consecutive constant-gradient run costs at most 63e of terminal reserve, independently of its length. A constant-normal block preserves the reserve, and at level at least ceil(log_2(4m)) its actual right-child surplus resets the reserve to 3e. The proof counts the finitely many runs before the first reset and retains all row payments.

This strictly extends the two separate structural cases. It still excludes general right children in which gradients and normal coordinates both change. Even a scalar quadratic of curvature strictly between zero and one need not satisfy the structural hypothesis. No mixture or extremal-reduction theorem has been proved. Therefore this is not an upper bound on unrestricted W(H_J).

Complete mixed proof and original-radius certificate:
../variable_right_20261017_r17/PROOF_ATTEMPT.md, Sections 3--4.
The parent read the complete packet and manually checked the run-port transport, reset inequality, reserve count, and final star-row certificate.

## 2. Independently audited component

AFFINE_RIGHT_WITH_SLACK.md removes the zero-endpoint-row assumption from the earlier affine-right theorem. Under constant-gradient right children it proves
\[
E_J^{\rm std}\ge-63e\,C_J^2\|g_e\|^2
\]
at every depth, plus the original-radius objective bound above. The independent auditor reconstructed the identities, the constants, and the arbitrary-original-minimizer argument. No fatal error was found.

The auditor requested explicit residual definitions and the l>=2 range for the local nonlocal recurrence. Those editorial corrections were applied and read back. Final audited source SHA-256:
8bfbe3d16d6673b02e50ba906fa14d628e5b0820d916ce3f4c74eb3319f69ba8.

Audit and handoff:
../audit_affine_slack_20261017_r17/AUDIT.md,
../audit_affine_slack_20261017_r17/HANDOFF.md.

This is independent MANUAL audit acceptance only. The later mixed theorem and normal-moment theorem were not part of that audit.

The complementary parent derivation is in NORMAL_RIGHT_RESERVE.md. It gives the exact arbitrary-right fixed-reserve identity, and proves a 3e reserve bound when right normals are constant. This packet has no separate independent audit.

## 3. A new full-class quantity, with an explicit parameter boundary

At EXACT Silver parameters, the variable-right branch proved
\[
E_j^{\rm std}+\rho C_j^2\|g_e\|^2
\ge\rho\left\|\frac1{C_j}\sum_i h_i(y_i-y_e)\right\|^2,
\quad y_i=x_i-g_i,\quad 0\le\rho\le51/100,
\]
for every actual convex 1-smooth history and every depth. There is no constant-gradient or constant-normal restriction in this statement. Its recursive full-vector PSD test has an explicit upper bound 37/50<1.

The weighted normal moment is precisely the correlation term left by the averaged original-row cycle. It vanishes on constant-normal blocks, unlike the unweighted displacement strengthening already disproved in R16.

The proof uses exact Silver parameters and recursively halves the child reserve. The actual perturbed hierarchy introduces a nonzero defect term, so importing this statement directly would assume an unproved child inequality. The full actual-parameter moment charge remains a missing theorem.

Complete certificate and boundary:
../variable_right_20261017_r17/PROOF_ATTEMPT.md, Sections 2 and 5.

Two actual growing-depth tests in Section 6 also close unproductive payment shortcuts. A right child killed by its first step disproves paying a capacity times its first forward row from a bounded same-scale right budget. A unit quadratic disproves a uniform bound on the positive physical squared-gradient sum. The signed cancellations must be retained.

## 4. Restoring the proposed lower-bound construction

The checkpoint branch instantiated a complete lossless scalar prototype and computed every directed row:
\[
R_{uv}=a_vq_v(q_v-q_u).
\]
This identifies changed-amplitude revisits in the same direction as the missing constraints. It supplied a full capped-coordinate completion and accounted for its initial radius at the original start.

It then allowed shared repairs, core-to-flat translations, and a newly selected closest compatible common minimizer. For the greedy prototype on h=(1,4)^k,1, every completion by the specified disappearing orthogonal caps has score at most
\[
\frac{216}{5(5k-9)^2}.
\]
The proof uses a positive cone combination of actual gradients to lower-bound every compatible original radius. Thus minimizing the radius jointly cannot make this repair free. This is an obstruction to that repair architecture, not to the original lower bound: the same word has a genuine fixed Huber witness with score 8/25.

The branch also reconstructed the actual zero-turning version of the Ye--Liu hard function, including its common-minimum polyhedron. Relative to its formal zero-overhead transfer score, the actual payoff is at most 4^{-(k-1)}, even after selecting a closest common minimizer and varying the local parameters. Removing genuine turning therefore does not restore a costless multi-checkpoint argument.

Actual turning, a different prototype selection, and other correction mechanisms remain possible. The proposed manuscript's free gluing step has not been repaired into an all-word theorem.

Full derivations:
../checkpoint_repair_20261017_r17/PROOF_ATTEMPT.md.

## 5. Source check and next proof requirement

The primary [Ye--Liu v2 construction](https://arxiv.org/html/2609.09152v2) was inspected directly. Its R_n is normalized by (L/2)||x_0-x_star||^2 and equals this project's W_n; no extra factor two was inserted.

A fresh primary-source check also inspected [Chikhi's terminal-certificate paper](https://arxiv.org/html/2609.13765v2) and [the recursive-composition phase paper](https://arxiv.org/html/2609.11788v1). Their stated results do not supply the missing actual-parameter unrestricted history inequality. No literature claim was substituted for that proof.

The most concrete upper-bound continuation is to combine the averaged cyclic identity with a paid weighted-normal-moment estimate on general actual right children. It must preserve the signed right residual and gradient-action cancellations. A complete proof of E_j(49/100)>=0 for every actual child 1<=j<m would activate the already established full-word implication; another exact-Silver-only result or an unproved reduction to the mixed class would not.

The lower-bound continuation must retain real turning and price the complete common-minimum geometry uniformly over words. The finite repair lemma alone and the zero-turning source family are insufficient.

## 6. Operational receipt

Two exploratory native calls and one sequential finished-object audit used gpt-6-astra / ultra. All three returned final handoffs before the hard deadline. No mathematical programs, arrays, solver runs, services, formal submissions, truth-store writes, publication, or further model calls were used in this wave.

Existing accepted fact files: 18. New accepted facts: 0. No TARGET.md exists. Original PROBLEM.md SHA-256 is unchanged:
3ecc3159a696e8528ebc727776d42f657cfbc6842e9212b28c870fcd05edb89d.

The unrelated untracked Target_A/ remains untouched. The mathematical wave closes with concrete progress, not completion. After an interrupted administrative closeout, the operator explicitly requested "保存目前进度后暂停, 上传已有进度到git". The Goal is PAUSED, all three native calls are completed, and no new research is authorized until an explicit resumption.

The subsequent GitHub upload is separately authorized administrative preservation of these existing results. It does not change their mathematical evidence status or reopen a research grant.
