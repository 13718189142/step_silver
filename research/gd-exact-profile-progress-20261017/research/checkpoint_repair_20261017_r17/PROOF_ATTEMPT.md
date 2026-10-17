# R17 checkpoint repair: concrete prototypes and costs at a common minimizer

**UNVERIFIED analytical draft. The original exact-profile minimax target remains OPEN.**

This invocation develops two approaches: (I) the lossless alternating-cap checkpoint prototype, completed by any shared family of the audited disappearing capped coordinates; (II) the actual Ye--Liu construction with its turning removed, including its true common-minimum geometry. Both calculations give all-depth limitations of specified constructions. Neither is a negative answer to the original minimax problem.

The allocation is one direct analytical invocation, no further agents or model calls, no mathematical programs or solver batches, no services, no truth-store changes, no formal submissions, and no publication. The hard deadline is 2026-10-17 05:50:00 UTC. Only this file and HANDOFF.md are written.

## 1. Normalization and inspected evidence

We set L=1 and use W=2(f_n-f_star)/||x_0-x_star||^2. The benchmark remains B_n=2S_bullet(n)+1, with the original all-integer Omega/G recurrences. No decimal constant or exponent-only target replaces 1/B_n.

Read locally: OPERATOR.md, the original PROBLEM.md, R17 WAVE.md, R16 HUBER_DATA_REPAIR.md and CAP_REPAIR_OPTIMALITY.md, the independent R16 capped-repair AUDIT.md, R15 typed-adversary PROOF_ATTEMPT.md, and accepted fact b98bb807d514e80d. The last fact supplies both the limitation of the displayed single-cut functional and the bound B_n <= 1+4n^p, p=log_2(3)<2.

The primary source was inspected directly: [Ye--Liu, arXiv:2609.09152v2](https://arxiv.org/html/2609.09152v2), Section 3.1 and Appendix A, especially equations (7)--(12), (26)--(40). Its R_n in equation (1) has denominator (L/2)||x_0-x_star||^2 and therefore equals this project's W_n. Appendix A.3 computes twice the displayed Lemma 2.2 bound before discarding that factor. The historical background convention does not supply another factor two here.

For finite data define

    y_i = x_i-g_i,
    ell_i = f_i-||g_i||^2/2,
    u_i = <g_i,y_i>-ell_i,
    R_ij = ell_j+u_i-<g_i,y_j>.

Thus

    R_ij = f_j-f_i-<g_i,x_j-x_i>-||g_j-g_i||^2/2.

The star datum (0,0,0) requires ell_i,u_i >= 0. Physical updates and all directed rows are required. All new mathematical statements below are direct derivations, not accepted fact-graph entries.

## 2. Approach I: an explicit lossless checkpoint prototype

### 2.1 Data for any chosen checkpoint set

Partition a nonnegative physical word into k+1 intervening blocks, with masses s_1,...,s_(k+1), separated by selected roots H_1,...,H_k > 1. A block may contain zero steps or no steps. Let tau >= 0 be a terminal cap age. Put

    A_j = 1+s_j                 (1 <= j <= k),
    A_(k+1) = 1+s_(k+1)+tau.

Choose q_1 != 0 and recursively set

    q_(j+1) = -(H_j-1)q_j/A_(j+1).

All q_j are nonzero and their signs alternate. At a query t in a nonterminal block j, let a_t be the sum of the steps remaining in that block before its selected root. At a query in the last block, let a_t be tau plus its remaining steps. Prescribe the scalar data

    x_t = (1+a_t)q_j,
    g_t = q_j,
    f_t = (1/2+a_t)q_j^2.                         (2.1)

Inside a block, decreasing a_t by h_t gives x_(t+1)=x_t-h_t g_t. At a root the left age is zero, so its update is

    q_j-H_jq_j = -(H_j-1)q_j = A_(j+1)q_(j+1),

exactly the next block's initial position. Both star rows hold:

    y_t=a_tq_j, ell_t=a_tq_j^2 >= 0, u_t=0.       (2.2)

These are genuine complete finite prototype data, not a globally admissible function assertion. Their terminal numerator and initial radius are

    E = 2f_n = (1+2tau)q_(k+1)^2,
    ||x_0||^2 = (1+s_1)^2 q_1^2.

Consequently their formal uncorrected payoff is exactly

    E/||x_0||^2
      = (1+2tau)/(1+s_(k+1)+tau)^2
        * product_(j=1)^k [(H_j-1)/(1+s_j)]^2.   (2.3)

At tau=s_(k+1), the first factor is 1/(1+2s_(k+1)). This is a precise lossless multiple-checkpoint candidate with the exact H-1 crossing and the exact terminal Huber factor. At k=1 it is the accepted single-cut witness. At k>=2 its all-pair constraints still have to be checked.

### 2.2 Every directed defect

For any source query u in block i and target query v in block j, direct substitution gives

    R_uv = a_v q_j(q_j-q_i).                     (2.4)

This includes the same-block rows, which vanish, and all nonadjacent rows. Opposite signs make both orientations nonnegative. For equal signs, write m_i=|q_i|. The two deficits for an earlier block i and later block j are precisely

    (-R_uv)_+ = a_v m_j(m_i-m_j)_+,
    (-R_vu)_+ = a_u m_i(m_j-m_i)_+.               (2.5)

Only one orientation can be negative for a particular unequal pair. A target at age zero has no incoming deficit. The maximum age in a nonterminal block is s_j, and in the terminal block it is s_(k+1)+tau. These facts handle zero steps, empty blocks, root queries, and the terminal query without a separate limiting argument.

Thus the missing mechanism is a same-direction revisit with a changed amplitude. An alternating sign by itself does not guarantee feasibility once a third block appears.

### 2.3 A complete capped-coordinate completion and its exact costs

Here is one explicit completion, although the obstruction below allows arbitrary shared completions rather than insisting on this assignment. Assign a pair of distinct blocks to the earlier block i and its following root. For that root define

    A_i^def = max_(j>i, same sign) [a_j^max m_j(m_i-m_j)_+],
    D_i^def = m_i max_(j>i, same sign)(m_j-m_i)_+,

where a_j^max is the maximum age in block j and an empty maximum is zero. The forward demand is A_i^def. At a query u of block i the reverse demand is a_u D_i^def; earlier prefix queries have no assigned demand at this root.

Let P_i be the total physical mass before this selected root. Choose 1<eta_i<H_i and append the audited unshifted capped coordinate of squared slope sigma_i. Its initial position is (P_i+eta_i)sqrt(sigma_i); it has that constant slope until the root and has value and gradient zero afterward. It contributes

    (H_i-eta_i)sigma_i

to every forward row crossing the root, and

    (P_i-S_u+eta_i-1)sigma_i

to the reverse row ending at a prefix query u, where S_u is the mass before u. A sufficient exact amplitude for the assigned rows is

    sigma_i = max{ A_i^def/(H_i-eta_i),
                   s_i D_i^def/(s_i+eta_i-1) }.  (2.6)

The second expression is zero if s_i=0. Its sufficiency follows because a/(a+eta_i-1) is increasing for a>=0, and P_i-S_u=a_u inside block i. Every correction is nonnegative on all other rows. Summing (2.6) over the selected roots therefore repairs every directed row in (2.5), not just adjacent pairs.

With the same zero minimizer the full, globally transported initial radius is exactly

    R_zero^2 = (1+s_1)^2q_1^2
               + sum_i (P_i+eta_i)^2 sigma_i,   (2.7)

and the terminal numerator remains E. The P_i are the original full prefixes, not restarted local prefixes. Full smooth-convex interpolation constructs one admissible static function from these repaired data.

For the corresponding core-preserving restricted repair, optimizing the directed demands gives

    sigma_i^min = max{ A_i^def/(H_i-1),
                       (A_i^def+s_i D_i^def)/(H_i-1+s_i) },
    M_i,core^min = (P_i+H_i)^2 sigma_i^min.        (2.8)

In particular a forward-only demand has optimal flat choice eta_i=1,

    sigma_i=A_i^def/(H_i-1),
    M_i,flat=A_i^def(P_i+1)^2/(H_i-1).           (2.9)

The endpoint eta_i=1 is legitimate for the continuously differentiable Huber cap. One must not replace (2.9) by a symmetric 2Delta estimate. Equations (2.6)--(2.9) establish feasibility and prices for this concrete prototype; they do not imply that their sum is negligible.

### 2.4 The common closest minimizer must be optimized jointly

The independent coordinate sum (2.7) is an available upper price, not a universal necessary price. All unshifted corrected data still have u_t=0. Let

    C = cone{G_0,...,G_n},
    K = conv{0,G_0,...,G_n},

where G_t are the full repaired gradients. The complete rows say that Y_t=X_t-G_t supports K at G_t. Hence the single function

    F_K(X)=max_(v in K) {<X,v>-||v||^2/2}

realizes every value and gradient. Its minimum set is C^polar. Every minimizer of any other admissible interpolation of these same zero-star data must also satisfy <G_t,z><=0 for all t. Thus the best compatible selected-minimizer distance is exactly

    R_min^2 = dist(X_0,C^polar)^2 = ||Proj_C X_0||^2. (2.10)

This also legitimizes constructing a new interpolation with that chosen minimizer datum. It does not silently change the denominator of an already fixed instance.

A core helper with parameter eta_i is a common translation of its unshifted helper by (H_i-eta_i)sqrt(sigma_i). Translating the query positions and the selected minimizer together preserves their distance. Therefore (2.10) also treats arbitrary mixtures of core and flat helpers after putting them in the unshifted coordinates. Positive core conjugate heights cannot be counted as an independent free resource.

## 3. An all-depth obstruction that survives shared repair and a new minimizer

The following statement concerns the particular greedy prototype (2.1), not arbitrary adversaries for the word.

**Draft proposition.** For any integer k>=2, take

    h = (1,4)^k,1,  n=2k+1,
    q_j=(-3/2)^(j-1),  1<=j<=k+1,

and put one unit step in each constant-gradient block, including the terminal block. Use terminal age tau=0. Append any finite family of orthogonal disappearing capped coordinates of the form in Section 2.3, with arbitrary amplitudes and arbitrary annihilation roots. Even allow annihilation at a unit step with H=eta=1. Suppose the resulting full data are interpolation-feasible. Then for every compatible selected minimizer, including the closest common minimizer,

    2F_n/||X_0-x_star||^2
       <= 216/[5(5k-9)^2].                      (3.1)

The same statement holds for translated core versions of these helpers.

**Derivation.** Each block starts at 2q_j, its unit step reaches q_j, and its root 4 sends q_j to -3q_j=2q_(j+1). The last unit step ends at q_(k+1), so E=q_(k+1)^2. All star rows and physical updates are as in Section 2.

Let t=2k-4 be the start of block k-1. Its age is one and q_t=q_(k+1)/(3/2)^2. The terminal gradient has the same sign, and its magnitude is larger. Equation (2.5) gives the single necessary reverse deficit

    -R_(n,t) = (20/81)E.                        (3.2)

Only helpers whose annihilation lies at or after t can contribute to this row. The five remaining steps are 1,4,1,4,1, with total mass 11. For a helper of squared slope sigma annihilating at r>=t, its reverse contribution is

    [S_r-S_t+eta_r-1] sigma
       <= [S_r-S_t+h_r-1] sigma <= 10 sigma.     (3.3)

Write Sigma_late for the sum of all such squared slopes, including multiple helpers at a root. Feasibility of (3.2) forces

    Sigma_late >= (2/81)E.                      (3.4)

This is only an amplitude requirement. To obtain a genuine selected-minimizer distance requirement, first translate all helpers to their zero-height flat form. Consider the positive conic combination

    v = G_t+(2/3)G_(t+2).                       (3.5)

The scalar prototype part cancels because the next block gradient is -(3/2)q_t. Helpers annihilated before t are zero in both gradients. Helpers annihilated at t or t+1 have coefficient 1 in v; helpers annihilated at t+2 or later have coefficient 5/3. Thus v is a ray in C supported entirely on the late helper coordinates. Every compatible minimizer z obeys <v,z><=0.

The original prefix mass is S_t=5(k-2). Set L=S_t+1=5k-9. Every late helper's initial coordinate, divided by its nonnegative slope, is S_r+eta_r>=L. If Sigma_A and Sigma_B are the squared-slope sums for the two coefficient groups, then

    <X_0,v> >= L(Sigma_A+(5/3)Sigma_B),
    ||v||^2 = Sigma_A+(25/9)Sigma_B.

For c=5/3 and nonnegative a,b,

    (a+cb)^2/[(a+c^2b)(a+b)] >= 4c/(1+c)^2=15/16,

as follows by expanding

    (c+1)^2(a+cb)^2-4c(a+b)(a+c^2b)
       =(c-1)^2(a-cb)^2 >= 0.

Cauchy--Schwarz with <v,z><=0 therefore yields

    ||X_0-z||^2 >= <X_0,v>^2/||v||^2
                 >= (15/16)L^2 Sigma_late
                 >= (5/216)(5k-9)^2 E.          (3.6)

The vector v is nonzero by (3.4), so the division is legitimate. Equation (3.1) follows. This argument permits helpers to repair many rows at once and permits the new closest minimizer; neither sharing nor core-height translations evade it.

Since accepted fact b98bb807d514e80d gives B_n<=1+4n^p with p=log_2(3)<2, the ratio of every such repaired witness score to 1/B_(2k+1) tends to zero. The uncorrected prototype score, meanwhile, is (3/2)^(2k)/4. A large formal transfer surplus does not by itself make this completion useful.

The word is not a counterexample to the original minimax lower bound. On the contrary, the fixed symmetric Huber function

    f(x)=x^2/2 for |x|<=1, and f(x)=|x|-1/2 otherwise,

started at x_0=5/2, alternates block starts +/-5/2 and root queries +/-3/2 under (1,4)^k. Its last unit step ends at +/-3/2. Thus it gives the constant score 8/25 for every k. Retaining nonzero checkpoint ages, instead of maximizing every local core transfer, entirely avoids the amplitude-revisit defect on this all-depth family.

The conclusion is precise: a proof cannot take an arbitrary greedy lossless scalar prototype and infer a negligible completion price from the finite capped-repair lemma. The proposition does not exclude a schedule-dependent choice of different prototypes, active/rotating correction coordinates, or other higher-dimensional adversaries.

## 4. Approach II: the actual Ye--Liu minimum geometry

This section derives the minimum geometry from the primary hard-function construction before taking a zero-turning limit. It does not use the scalar obstruction as a surrogate for higher-dimensional geometry.

### 4.1 Exact common-minimum polyhedron

In the source's local block i, let epsilon_i>0, let P_i,Q_i be the actual two-coordinate displacements of equation (7), and let rho_i be its positive spatial scale. Write

    d_i=D_i rho_i,
    D_(i+1)=b_i d_i,
    ell_(i+1)=Q_i d_i,

where b_i is the local checkpoint step, equal to half the physical checkpoint step. Here P_i is a local horizontal displacement, not the global prefix P_i of Section 2. Denote the translated support center by (A_i,B_i):

    A_i=ell_i+D_i-d_i(epsilon_i+P_i),
    B_i=d_i(1+Q_i)=ell_(i+1)+d_i.               (4.1)

Every arc generator lies in the cone spanned by the two endpoint vectors (c_i,0) and (epsilon_i,-1), and both endpoints belong to the finite support set used by the source. A support function vanishes exactly on its polar cone. Its Moreau envelope has the same zero set. Since every component and the terminal Huber term are nonnegative, the actual global half-sum has the exact minimum set

    M = { x : x_i<=A_i,
                  x_(i+1)>=B_i+epsilon_i(x_i-A_i), 1<=i<=k,
                  x_(k+1)<=ell_(k+1) }.          (4.2)

Thus the selected-minimizer cost is dist(e_1,M)^2. It is a coupled polyhedral projection, not the sum of the local shift squares and not the source's arbitrary conservative A parameter.

The local zero-region requirement at the local origin forces, from the terminal supporting plane,

    T_i := D_i/d_i
        >= epsilon_i+P_i+(1+Q_i)/epsilon_i.       (4.3)

This is necessary for this actual local construction with its specified inactive region. It is not a claim about every conceivable finite-data prototype.

The source's backward trajectory also satisfies

    r_0=(epsilon_i+P_i,-1-Q_i),
    (1+Q_i)/(epsilon_i+P_i)<=1/epsilon_i.

Consequently r_0 belongs to the cone of the endpoint vectors. For the first component, e_1-(A_1,B_1)=d_1 r_0. Every common minimizer lies in that component's translated polar cone. The closest point of that component's zero set alone is its support center, and therefore

    dist(e_1,M)^2
       >= d_1^2[(epsilon_1+P_1)^2+(1+Q_1)^2].    (4.4)

This bound holds for every common minimizer and remains valid after all legitimate choices of a nearer original minimizer. The other components can only increase the distance from their intersection.

### 4.2 A genuine zero-turning family

Set the circle shift gamma to zero. Rather than invoke a lemma requiring gamma>0, construct the local function directly. For any epsilon_i>0 put

    v_i=(epsilon_i,-1), c_i=sqrt(1+epsilon_i^2),
    K_i=conv{0,(c_i,0),v_i}.

Let the local intervening steps be alpha=h/2, with total S_i=s_i/2. At a query with local remaining mass A>=0, take

    r=(1+A)v_i, gradient v_i.

Indeed v_i is the Euclidean projection of (1+A)v_i onto K_i: its radial normal has nonpositive inner product with both other vertex differences. The backward GD identities hold exactly. In particular

    P_i=epsilon_i S_i, Q_i=S_i,
    r_start=(1+S_i)v_i.                          (4.5)

Use the support center prescribed by (4.1), the local Moreau envelope, and the original source's coordinate scaling. It is enough to choose

    T_i >= max{(1+S_i)(epsilon_i+epsilon_i^(-1)),
               epsilon_i(S_i+b_i)},
    b_i >= 1+epsilon_i^(-2).                     (4.6)

The first inequality ensures the local origin and its required quadrant belong to the zero region. The second term gives U_i>=0. The bound on b_i makes the old component zero on the full vertical half-line required during the next block. These claims follow by testing the two endpoint support planes; the same finite-component half-sum and terminal Huber construction is then an actual admissible static 1-smooth function. No infeasible limit of the gamma>0 lemma is being passed off as a function.

Explicitly, put rho_i=1/T_i and z_i^circ=(1,0)-rho_i(1+S_i)v_i, and define

    f_i(z)=env_1 sigma_(rho_i K_i)(z-z_i^circ),
    Phi_i(x)=D_i^2 f_i((x_i-ell_i)/D_i, x_(i+1)/D_i),
    F(x)= (1/2)sum_(i=1)^k Phi_i(x)
             +(1/2)H_delta(x_(k+1)-ell_(k+1)),
    delta=D_(k+1)/(1+s_tail), D_1=1, ell_1=0.

Here sigma is the support function, env_1 its Moreau envelope, and H_delta is the one-sided Huber primitive with derivative min{delta,max{0,z}} and value zero at zero. Each Phi_i is convex, nonnegative, and 1-smooth on its two coordinates. Each coordinate appears in at most two terms before the factor 1/2, so F is convex and 1-smooth. Its minimum is zero, and (4.6) gives the zero regions that keep exactly one component active on each prescribed block. The global physical step is h and the active local step is h/2. This supplies a finite-dimensional static admissible function for every finite list of blocks satisfying (4.6).

For completeness, at the end of the local intervening block r=v_i. After its step b_i, the old point is (1-b_i)v_i. Along the subsequent vertical half-line starting at the pre-step height, the worst terminal-plane test is 1+(1-b_i)epsilon_i^2<=0; its horizontal endpoint test is also nonpositive. This is exactly the last condition in (4.6).

### 4.3 Exact all-depth loss even after choosing a common nearest minimum

Let s_tail be the physical suffix mass after the last checkpoint. The source's terminal Huber calculation, in this project's W normalization, gives the terminal numerator

    E = D_(k+1)^2/[2(1+s_tail)].                 (4.7)

For every selected common minimizer, (4.4)--(4.5) give

    R^2 >= d_1^2(1+S_1)^2(1+epsilon_1^2).       (4.8)

Also D_(i+1)=b_i d_i and d_i=D_i/T_i. Therefore even the largest normalized score obtainable by selecting a minimizer of this actual function is bounded above by

    E/R^2
       <= b_1^2/[2(1+s_tail)(1+S_1)^2(1+epsilon_1^2)]
          * product_(i=2)^k (b_i/T_i)^2.         (4.9)

Define only for this comparison the formal zero-overhead transfer score

    I_0 = [2(1+s_tail)]^(-1)
          * product_(i=1)^k [b_i/(1+S_i)]^2.     (4.10)

It is not asserted to be a feasible lower bound or to equal 1/B_n. Using the necessary first inequality of (4.6) in (4.9) gives the exact all-depth ratio bound

    (E/R^2)/I_0
       <= 1/(1+epsilon_1^2)
          * product_(i=2)^k
              [epsilon_i/(1+epsilon_i^2)]^2
       <= 4^(-(k-1)).                           (4.11)

The last step is (epsilon+epsilon^(-1))^2>=4. It permits different epsilon_i at every checkpoint. This is a loss of at least a factor four at each checkpoint after the first, including after optimization over the common closest minimizer. It is a constant loss when k>=2 is fixed and an exponential-in-depth loss when k grows. It cannot be reclassified as a uniform 1-o(1) multiplier.

For k=1 there is no repeated-depth factor; the first arbitrary spatial scale can indeed disappear after the minimizer is chosen correctly. The accepted single-cut insufficiency explains why this isolated improvement does not settle the all-word target.

For the genuinely rotated construction, (4.3)--(4.4) instead give the diagnostic bound

    (E/R^2)/I_0
       <= (1+S_1)^2/[(epsilon_1+P_1)^2+(1+Q_1)^2]
          * product_(i=2)^k
             [(1+S_i)/(epsilon_i+P_i+(1+Q_i)/epsilon_i)]^2. (4.12)

Unlike (4.11), this expression need not suffer a fixed factor at each large block. Actual turning can make the horizontal displacement comparable to S_i while controlling Q_i, so it is the surviving mechanism. A uniform summable bound over every physical word and the exact all-integer benchmark is not supplied by (4.12).

## 5. Disposition for the original target

The original target is unresolved. Section 2 supplies complete physical prototypes and every directed defect, plus an explicit full interpolation completion. Section 3 gives a quantified all-depth obstruction to treating that completion as free, and it remains valid under shared repairs, positive core heights, and a newly chosen closest compatible minimizer. Section 4 checks the real primary-source construction and identifies the unavoidable repeated loss when turning is genuinely removed.

Neither obstruction rules out a successful rotating construction, a different schedule-dependent prototype selection, or correction coordinates that become active later rather than carrying a constant gradient through the full original prefix. A proof of the original affirmative target still needs such a mechanism together with a uniform original-radius estimate at 1+o(1) relative to B_nE. No such estimate or original-target theorem has been established in this invocation.
