# R17 checkpoint-repair handoff

**UNVERIFIED direct analytical work. Original exact-profile target OPEN.**

The complete derivations are in PROOF_ATTEMPT.md. No mathematical programs, numerical arrays, solvers, further agents/models, services, truth-store edits, formal submissions, or publication were used. The invocation stayed within the two assigned substantive approaches. The primary Ye--Liu v2 hard-function construction, including Appendix A, was inspected directly. Its R_n equals this project's W_n; no extra factor two was imported.

## What is concrete

1. A full lossless scalar multi-checkpoint prototype is now instantiated, with exact physical updates, both star rows, every directed interpolation defect, a sufficient capped-coordinate completion, and its cost at the single original starting point. Nonterminal blocks have x=(1+a)q, g=q, f=(1/2+a)q^2, and a is remaining block mass. At a root H>1, the next block gradient is q_next=-(H-1)q/(1+s_next), with the terminal cap age included in that denominator when needed.

2. Its complete directed row is R_uv=a_v q_v(q_v-q_u). Only same-sign amplitude revisits can fail. A later smaller magnitude causes the forward deficit; a later larger magnitude causes the reverse deficit. This makes the directed endpoint repair eta=1 available in the forward-only case, at M_flat=A(P+1)^2/(H-1).

3. For the unshifted corrected data, all u_i are zero. The exact common-minimizer radius is ||Proj_C X_0||^2, C=cone{G_i}. Thus merely summing independent coordinate radii is not a necessary cost. Core helpers are translated to this form before analyzing a newly chosen minimizer.

## All-depth obstruction to the greedy scalar completion

For h=(1,4)^k,1, n=2k+1, the greedy terminal-core prototype has q_j=(-3/2)^(j-1) and E=q_(k+1)^2. Any interpolation-feasible completion by an arbitrary finite family of orthogonal disappearing capped coordinates satisfies

    E/||X_0-x_star||^2 <= 216/[5(5k-9)^2], k>=2,

for EVERY compatible minimizer, including the closest one for a newly constructed interpolation. Helpers may share repairs across rows, use arbitrary amplitudes and selected roots, or even die at a unit step. Mixtures of core and flat variants are covered.

The proof uses one exact late reverse defect, (20/81)E. Its last five physical steps have total mass 11, so any repair requires late squared-slope sum at least (2/81)E. The positive cone ray G_t+(2/3)G_(t+2), where t=2k-4, cancels the scalar gradient and has late helper weights 1 or 5/3. It forces an original-radius cost at least (5/216)(5k-9)^2 E even after minimizer coupling. This is not a restarted norm argument.

Accepted B_n<=1+4n^log_2(3) makes the repaired-witness ratio to 1/B_n tend to zero. However the same word has a genuine fixed symmetric Huber witness with score 8/25 at every depth. Therefore this is an obstruction to greedily maximizing every core transfer and then repairing it, not an obstruction to the original lower bound or to every scalar prototype choice. Nonzero checkpoint cap ages survive this test.

## Actual Ye--Liu geometry and zero-turning cost

For the genuine source construction, with d_i=D_i rho_i, actual local displacements P_i,Q_i, and local steps equal to half the physical steps, the common minimum set is exactly

    x_i<=A_i,
    x_(i+1)>=B_i+epsilon_i(x_i-A_i),
    x_(k+1)<=ell_(k+1),

where A_i=ell_i+D_i-d_i(epsilon_i+P_i) and B_i=ell_(i+1)+d_i. Thus its radius is a coupled polyhedral projection; the conservative source parameter A is not itself an optimal radius price.

The exact local inactive-region condition nevertheless requires

    T_i=D_i/d_i>=epsilon_i+P_i+(1+Q_i)/epsilon_i.

Every common minimizer also has radius squared at least

    d_1^2[(epsilon_1+P_1)^2+(1+Q_1)^2].

The gamma=0 case is reconstructed as an actual finite-dimensional static function instead of invoking the gamma>0 lemma at an excluded endpoint. Its local gradient is constantly (epsilon_i,-1), so P_i=epsilon_i S_i and Q_i=S_i, where S_i is half the physical block mass. Defining the formal comparison score

    I_0=[2(1+s_tail)]^(-1) product_i [b_i/(1+S_i)]^2,

with b_i half the physical checkpoint step, the actual function's payoff, even at its closest common minimizer, obeys

    payoff/I_0
      <= (1+epsilon_1^2)^(-1)
          product_(i=2)^k [epsilon_i/(1+epsilon_i^2)]^2
      <= 4^(-(k-1)).

This remains true with a separately chosen epsilon_i at every checkpoint. Removing true turning therefore reintroduces a factor of at least four per subsequent checkpoint in this exact source architecture. The improvement from a closer first minimizer cannot erase later transfer costs.

## Boundary and useful next mathematical input

No uniform original-word lower bound at (1-o(1))/B_n has been obtained. No assertion about a negative answer to the original minimax problem is made. The two restrictions are explicit: disappearing orthogonal cap helpers in the first result, and the source's unchanged local inactive-region architecture with zero actual turning in the second.

The remaining higher-dimensional route must retain actual turning or provide coordinates that activate later. Its relevant costs are the full original common-minimum geometry and the actual directed defects, not a collection of free root ports. A uniform small-defect theorem or global cost bound relative to B_nE remains a theorem-level missing step.

Manual checks completed: every physical index in the (1,4)^k,1 family; zero-step/empty-block treatment in the general prototype; forward/reverse orientation; eta=1 and H=eta=1 endpoint meaning; the cone-ray constant 15/16; core-to-flat translations; source local/global factor 1/2; the actual gamma=0 function's zero regions and smoothness; and the distinction between a witness upper price, a required radius, and the original minimax value.
