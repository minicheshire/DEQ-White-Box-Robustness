White-Box Robustness Evaluation Protocol for DEQs

This repo contains the source code for our NeurIPS 2022 paper: [A closer Look at the Adversarial Robustness of Deep Equilibrium Models](https://openreview.net/forum?id=_WHs1ruFKTD). There are four directories in this repo. 

First, use the codes in the either of the following two directories to train a robust DEQ by adversarial training.

- deq-exact-trained.     Use the exact gradient in adversarial training.
- deq-unrolling-trained. Use the unrolling-based phantom gradient in adversarial training.

After obtaining a robust DEQ checkpoint, use the following two directories for the real white-box robustness evaluation, with intermediate state attacks and adaptive defense strategies proposed in our [paper](https://openreview.net/forum?id=_WHs1ruFKTD).

- deq-evaluation-with-simultaneous-adjoint.   Intermedate gradients approximated with the proposed simultaneous adjoint (Sec 4.1);
- deq-evaluation-with-unrolled-intermediates. Intermedate gradients approximated by directly unrolling the intermediate states (Sec 4.2).