# Primary-source check during R15

This is a literature and normalization note, not a new theorem or a claim that the unrestricted minimax question has been settled. The original PROBLEM.md is preserved verbatim.

1. [Liu, Chen, Jiang, Wang, Optimal Recursive Composition and Dyadic Phase Laws for Gradient Descent with Predetermined Stepsizes, arXiv:2609.11788v2](https://arxiv.org/html/2609.11788v2), dated 12 October 2026, proves balanced optimality for the symmetric recursive family and a nonconstant limiting phase for the asymmetric recursive family. Its closure hypotheses concern those certificate families. It does not supply the missing arbitrary-word adversary or the perturbed hierarchy history input used here.

2. [Grimmer, Shu, Wang, Composing Optimized Stepsize Schedules for Gradient Descent](https://arxiv.org/html/2410.16249) provides the composability framework; its OBS-F minimax claim is stated as a conjecture. This describes that source's claim status, not an argument against a later proof.

3. **Normalization correction in the background literature description.** The currently retrieved [Ye-Liu arXiv:2609.09152v2](https://arxiv.org/html/2609.09152v2) defines its R_n in equation (1) with denominator (L/2)||x_0-x_star||^2. It therefore equals this project's W_n, rather than this project's R_n=W_n/2. Its Theorem 1.1 states a lower bound with no extra leading factor 2 in that normalization. The historical PROBLEM.md background section describes a differently normalized R_n and inserts a factor 2; that attribution should not be copied as a faithful quotation of this version. The distinction has no effect on the original exact-profile target, nor on the current conditional PD calculations, which consistently use W=2(f_n-f_star)/(L||x_0-x_star||^2).

Only these primary-source statements are used. No secondary review or search snippet is treated as mathematical authority. The research objective remains the original comparison with the exact all-integer-split B_n.
