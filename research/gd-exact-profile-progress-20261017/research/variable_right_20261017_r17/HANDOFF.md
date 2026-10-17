# R17 variable-right handoff

**UNVERIFIED. Original target OPEN. No unrestricted actual-parameter history certificate is claimed.**

## Complete scoped result

For the actual same-enclosing-m hierarchy, each right child along the left spine may independently have either constant gradients or constant normal coordinates x-g. The two behaviors may switch arbitrarily; all endpoint-row slack is retained. For every m>=1536 and every depth J,

    E_J^std >= -rho_m C_J^2 ||g_end||^2,
    rho_m = (3 + 63 ceil(log_2(4m))) / (4m) < 4/25.

Therefore E_J(49/100)>=0 throughout this mixed structural class. The actual original-minimizer objective bound is

    2(f_end-f_star)/||x_start-x_star||^2
       <= 1 / [1+(32/17)(C_J-1)].

The proof is Sections 3--4 of PROOF_ATTEMPT.md. Each affine run costs only 63e regardless of its length. Its incoming reserve is transported by the exact affine port with no norm-Cauchy loss. Normal roots preserve a reserve >=3e and, at levels at least ceil(log_2(4m)), reset any reserve <=.51 back to3e using their actual right surplus. Level1 is handled separately. No independence, dimension restriction, changed minimizer, or zero endpoint-row assumption occurs.

## Full-class exact-Silver tool

For exact Silver only, with M_j=sum_i h_i[(x_i-g_i)-(x_end-g_end)], every actual smooth convex history satisfies

    E_j^std + rho C_j^2 ||g_end||^2 >= rho ||M_j/C_j||^2

for 0<=rho<=.51 and every depth. Section 5 supplies the reserve allocation, exact moment recursion, leaf check, and full-vector PSD scalar criterion. The criterion is bounded above by37/50<1. Its perturbed extension is not assumed: recursive reserve halving requires child bounds unavailable for the actual hierarchy.

## General variable-right interface

The averaged cyclic path v->end->i->older, weighted by the physical right h_i, has the exact identity

    2C_R = (C-1)(Q_v,end-Q_v,older)
           +sum_R h_i Q_end,i +sum_R h_i Q_i,older.

Its complete quadratic remainder is equation(2.4). It includes the weighted normal moment and the signed physical gradient action. The signed right residual remains in equation(2.5). No uniform payment for the full combination was obtained.

Two actual growing-depth tests in Section 6 prevent shortcuts: an early-kill quadratic excludes paying C*Q_start,end by bounded right residual/terminal reserve; the actual unit quadratic excludes a uniform bound on sum h_i^2||g_i||^2 by the same residual budget. Neither is a counterexample to E(.49).

## Scope and next mathematical requirement

The original full finite-dimensional quantifiers still require right children with simultaneous, nonconstant changes of gradients and normal coordinates. No decomposition of these histories into the G/N classes has been proved. The next concrete interface is to pay equation(2.4) jointly, preserving the normal-constant surplus in equation(2.6), or to extend the moment charge to actual parameters with a complete child-reserve budget. Merely importing the exact-Silver moment bound would be circular.

This worker used one invocation and two approaches. No mathematical program, solver, new agent/model, service, truth-store mutation, verification submission, or publication was used. New results are manual drafts, outside the separate completed audit of the parent's affine-right theorem. Only this file and PROOF_ATTEMPT.md were written.
