Neural networks built from scratch in NumPy: from a single perceptron to a fully tuned multi-layer network. 
Covers optimizers, regularization, initialization, batch normalization and hyperparameter search.

## Notebooks

| # | Notebook | Topics |
|---|----------|--------|
| 1 | [Introduction to Neural Networks](1_intro_NN.ipynb) | Perceptron, AND / XOR networks, forward pass in matrix form, activation functions (Sigmoid, tanh, ReLU, Leaky ReLU, ELU, GELU, Swish, Softmax), the link between a single neuron and linear regression, gradient descent |
| 2 | [Gradient Descent and Its Alternatives](2_gradient_descents_alternatives.ipynb) | Mini-batch GD, exponentially weighted averages & bias correction, Momentum, Nesterov, AdaGrad, Adadelta, RMSProp, Adam, Adamax, AMSGrad, Nadam |
| 3 | [Other Improving Techniques](3_other_improving_techniques.ipynb) | Cross-entropy vs. MSE, L1 / L2 regularization and weight decay, dropout, other regularization methods, learning-rate decay, local optima |
| 4 | [Improving a Network in Practice](4_try_to_improve_network.ipynb) | He initialization, baseline vs. improved network, hyperparameter tuning (scales, "pandas vs. caviar", Optuna), batch normalization (training and test time), satisficing vs. optimizing metrics |

Notebooks 2–4 share the same synthetic dataset, split and baseline network, so every technique is measured against the same reference.

## Requirements
pip install numpy pandas matplotlib scikit-learn optuna jupyter
