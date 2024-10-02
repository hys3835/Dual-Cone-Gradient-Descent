# Dual Cone Gradient Descent for Training Physics-Informed Neural Networks

This is the official code repository for the 2024 NeurIPS paper [Dual Cone Gradient Descent for Training Physics-Informed Neural Network] (https://arxiv.org/abs/2409.18426).

## Abstract
Physics-informed neural networks (PINNs) have emerged as a prominent approach for solving partial differential equations (PDEs) by minimizing a combined loss function that incorporates both boundary loss and PDE residual loss. Despite their remarkable empirical performance in various scientific computing tasks, PINNs often fail to generate reasonable solutions, and such pathological behaviors remain difficult to explain and resolve. In this paper, we identify that PINNs can be adversely trained when gradients of each loss function exhibit a significant imbalance in their magnitudes and present a negative inner product value. To address these issues, we propose a novel optimization framework, Dual Cone Gradient Descent (DCGD), which adjusts the direction of the updated gradient to ensure it falls within a dual cone region. This region is defined as a set of vectors where the inner products with both the gradients of the PDE residual loss and the boundary loss are non-negative. Theoretically, we analyze the convergence properties of DCGD algorithms in a non-convex setting. On a variety of benchmark equations, we demonstrate that DCGD outperforms other optimization algorithms in terms of various evaluation metrics. In particular, DCGD achieves superior predictive accuracy and enhances the stability of training for failure modes of PINNs and complex PDEs, compared to existing optimally tuned models. Moreover, DCGD can be further improved by combining it with popular strategies for PINNs, including learning rate annealing and the Neural Tangent Kernel (NTK).

## Setup
Please Install the required dependencies:

```pip install -r requirements.txt```

## Benchmark equations
For experiment of the main benchmark equations, run the bash file

```bash run_dcgd.sh```

or

``` python main.py --equation=${equation} --dcgd=${dcgd_type} --lr=${lr} --optim='adam' --depth=3 --width=50 --batch=128 ```

## PINNs variants
 

## Citation
```
@inproceedings{hwang2024dual,
  title     = {Dual Cone Gradient Descent for Training Physics-Informed Neural Networks},
  author    = {Hwang, Youngsik and Lim, Dong-Young},
  booktitle = {Advances in Neural Information Processing Systems (NeurIPS)},
  year      = {2024},
}
```
