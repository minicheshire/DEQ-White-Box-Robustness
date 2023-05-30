Use unrolled intermediates for different white-box attacks

Place the trained DEQ checkpoint at ./MDEQ-Vision/output/cifar10/cls_mdeq_LARGE_reg/{real/unroll}-checkpoint.pth.tar

python tools/cls_valid_observe_train.py --cfg experiments/cifar/cls_mdeq_[A]_reg.yaml --TrainGrad [B] --AttackGrad [C] --attack [D]

[A] DEQ Size. 
    choices: LARGE, XL

[B] unrolling-trained or exact-trained. 
    choices: unroll, real

[C] gradient used in the attack. [C] = [C1]unroll-[C2]-[C3], where
    [C1] = "M" when lambda = 0.5, and "F" when lambda = 1
    [C2] indicates the [C2]-th intermediate state to be unrolled (0~7)
    [C3] indicates the unrolling steps. [C3] can be 1, 5, 9 or others.

[D] attack technique, together with specified defense. xxx as the robustness of the final state or the early state (can be found in the output). Specifically, xxx-es-0 refers to the ensemble defense
    choices: pgd, pgd-es-0, apgd-ce, apgd-ce-es-0, apgd-t, apgd-t-es-0, fab-t, fab-t-es-0, square, square-es-0

