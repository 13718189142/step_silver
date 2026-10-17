# Research progress saved on 17 October 2026

**Research is PAUSED by the operator. The original exact-profile minimax problem remains OPEN.**

This is an incremental preservation of the completed R15--R17 work. It contains every new or changed Markdown research document since the 14 October repository snapshot, plus the three round closeout receipts. The previous full archive remains available in the repository; its repeated bodies are not concatenated again here.

The pause request was: "保存目前进度后暂停, 上传已有进度到git". Saving and uploading existing progress is authorized. No new proof search, worker, verification request, or automatic research restart is authorized until the operator explicitly resumes. Historical ACTIVE labels describe earlier states and do not override this pause.

## Read in this order

1. [Current progress and exact remaining gap](research/resume_20261017_r17/R17_PROGRESS.md).
2. [Original problem, preserved byte for byte](PROBLEM.md).
3. [Latest mixed-right proof and exact-Silver normal-moment estimate](research/variable_right_20261017_r17/PROOF_ATTEMPT.md).
4. [Independently audited affine-right component](research/resume_20261017_r17/AFFINE_RIGHT_WITH_SLACK.md) and its [manual audit](research/audit_affine_slack_20261017_r17/AUDIT.md).
5. [Reconstruction and costs of the proposed lower-bound route](research/checkpoint_repair_20261017_r17/PROOF_ATTEMPT.md).
6. [R16 synthesis](research/resume_20261017_r16/R16_PROGRESS.md) and [R15 synthesis](research/resume_20261017_r15/R15_PROGRESS.md) for the immediate dependencies.

The proof sources retain their original bytes and relative research-directory layout. Older dependencies already published in the 14 October snapshot are indexed by [BASELINE_REFERENCE_MAP.csv](BASELINE_REFERENCE_MAP.csv). Resolve its repository_path entries from the repository root. The full baseline remains at research/gd-exact-profile-all-markdown-20261014/.

## What is established at the draft level

The actual perturbed hierarchy uses one enclosing m>=1536, e=1/(4m), beta=1-e, c=(1+sqrt(2))(1+e), a=beta/c, H_0=(), H_(j+1)=(H_j,1+a*c^j,H_j), and C_j=1+sum H_j.

The latest complete structural derivation allows each entire right child along the left spine to have either constant gradients or constant normal coordinates x_i-g_i, with arbitrary switches between these choices and no zero-endpoint-row assumption. It obtains an all-depth terminal reserve

    rho_m = (3+63*ceil(log_2(4m)))/(4m) < 4/25

and the original-selected-minimizer objective bound

    2(f_e-f_star)/||x_0-x_star||^2 <= 1/[1+(32/17)(C_J-1)].

This is a structural trajectory theorem. It does not cover a general varying right child and is not an upper bound on unrestricted W(H_J).

A separate derivation controls the weighted normal moment for the full smooth-convex class at EXACT Silver parameters. Its extension to the perturbed hierarchy remains open. The explicit paid identity and the failed termwise estimates are retained in the latest proof packet.

On the lower-bound side, the submitted free-gluing idea was reconstructed into concrete finite data and repair costs. Shared disappearing-coordinate repairs and a closest compatible minimizer do not make the greedy multi-checkpoint construction free. The genuine zero-turning Ye--Liu family also incurs a repeated loss. These are scoped obstructions, not a negative solution of the original minimax problem.

## Evidence boundary

- New Danus-accepted facts in R15--R17: zero.
- Existing accepted fact records: 18, retained in the previous repository snapshot.
- The affine-right component and the earlier capped-coordinate repair received independent MANUAL audits.
- The later mixed-right and normal-moment results are complete manual draft derivations, without separate Danus verifier acceptance.
- The full minimax target has neither a complete proof nor a complete counterexample. No TARGET.md was created.
- [Submitted candidate](external_candidate/COMPLETE_RESOLUTION_SUBMITTED.txt) is preserved as the operator-supplied proposal. Its claim of complete resolution is not accepted; see the typed-adversary and checkpoint-repair analyses.

The original PROBLEM.md is preserved verbatim. Its historical attribution of the Ye--Liu normalization is corrected explicitly in the later source-check notes: the primary paper's R_n uses denominator (L/2)||x_0-x_star||^2 and equals this project's W_n. Do not introduce another factor two.

## Preservation and later recovery

The local source project is D:\Danus\runtime\projects\gd-exact-profile-20260926. This local handoff is D:\Danus\runtime\handoffs\gd-exact-profile-progress-20261017. The publication checkout is D:\Danus\runtime\publishing\step_silver-20261014.

All three R17 native agents completed. The Goal is paused. Docker's Linux-engine pipe was unavailable at the pause check; no Docker service or worker was started. Completed research used gpt-6-astra / ultra; these settings are historical metadata, not an instruction to start a model now.

After an explicit resumption, the substantive upper-bound task is a uniform paid estimate for right children with simultaneously varying gradients and normal coordinates. The lower-bound task must retain genuine turning and control the full original common-minimum radius uniformly over words. Repeating a conditional reduction alone does not complete either task.

[MANIFEST.json](MANIFEST.json) records source paths, byte counts, and SHA-256 values. Copy integrity does not certify mathematical correctness. The remote commit is verified separately after publication.
