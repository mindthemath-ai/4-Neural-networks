# Neural Networks from Scratch

A hands-on introduction to neural networks, built step by step with **NumPy only**.
The notebooks start from a single perceptron and end with a regularised, tuned and batch-normalised
deep network, implementing every forward pass, backward pass and optimiser by hand so that nothing
is hidden behind a framework.

All notebooks are committed **with their outputs**, so they can be read directly on GitHub without
running anything.

---

## Table of Contents

- [Who is this for](#who-is-this-for)
- [Course structure](#course-structure)
- [Getting started](#getting-started)
- [Running the notebooks](#running-the-notebooks)
- [References](#references)

---

## Who is this for

Students and practitioners who know basic Python and linear algebra and want to understand
*what actually happens* inside a neural network before moving to PyTorch or TensorFlow.

**Prerequisites**

- Python and NumPy (array shapes, broadcasting, matrix products)
- Basic calculus (derivatives, chain rule)
- Basic linear algebra (vectors, matrices, dot product)

---

## Course structure

The material is split into four modules. Notebooks are meant to be read in order.

### Module 1 — Foundations

| # | Notebook | Content |
|:-:|---|---|
| 1.1 | [Perceptron and AND](1.1_perceptron_and_AND.ipynb) | The perceptron as a decision rule (village-fair example); the AND function learned by a single neuron. |
| 1.2 | [Activation functions](1.2_activation_functions.ipynb) | From one neuron to a network; sigmoid, tanh, ReLU, Leaky ReLU, ELU, GELU, Swish and Softmax, with pros and cons. |
| 1.3 | [XOR network](1.3_XOR_network.ipynb) | The main steps of building a network; a 2-layer network solving XOR, with forward and backward propagation derived and implemented. |
| 1.4 | [Gradient descent](1.4_gradient_descent.ipynb) | The intuition behind gradient descent; a single neuron as linear regression. |

### Module 2 — Optimisation algorithms

| # | Notebook | Content |
|:-:|---|---|
| 2.1 | [Dataset and baseline](2.1_dataset_and_baseline.ipynb) | Synthetic regression dataset, train/validation/test split, normalisation and a baseline network trained with full-batch gradient descent. |
| 2.2 | [Mini-batch gradient descent](2.2_minibatch_gradient_descent.ipynb) | Mini-batch GD and its comparison with batch and stochastic GD. |
| 2.3 | [Momentum and NAG](2.3_momentum_and_NAG.ipynb) | Exponentially weighted averages and bias correction; momentum; Nesterov accelerated gradient. |
| 2.4 | [Adaptive optimisers](2.4_adaptive_optimizers.ipynb) | AdaGrad, Adadelta, RMSProp, Adam, Adamax, AMSGrad and Nadam, each implemented from scratch. |

### Module 3 — Improving generalisation

| # | Notebook | Content |
|:-:|---|---|
| 3.1 | [Setup, initialisation and bias/variance](3.1_setup_init_and_bias_variance.ipynb) | Why we normalise inputs, weight initialisation, and diagnosing bias vs variance. |
| 3.2 | [Log loss](3.2_log_loss.ipynb) | Cross-entropy as a cost function and why it trains faster than MSE for classification. |
| 3.3 | [L1 and L2 regularisation](3.3_L1_L2_regularization.ipynb) | Lasso and Ridge penalties, weight decay, and their geometric intuition. |
| 3.4 | [Dropout and other regularisation](3.4_dropout_and_other_regularization.ipynb) | Dropout and why it works; data augmentation, early stopping and other methods. |
| 3.5 | [Learning-rate decay and local optima](3.5_learning_rate_decay_and_local_optima.ipynb) | Learning-rate schedules and the problem of local optima in high dimensions. |

### Module 4 — Putting it together

| # | Notebook | Content |
|:-:|---|---|
| 4.1 | [Baseline vs improved network](4.1_baseline_vs_improved.ipynb) | He initialisation, L2, dropout, data augmentation, early stopping and LR decay applied together and compared with the baseline. |
| 4.2 | [Hyperparameter tuning](4.2_hyperparameter_tuning.ipynb) | Choosing the right scale for hyperparameters; grid search and Bayesian optimisation with Optuna. |
| 4.3 | [Batch normalisation](4.3_batch_normalization.ipynb) | Batch normalisation implemented from scratch (training and inference) and compared with the previous models. |
| 4.4 | [Metrics and references](4.4_metrics_and_references.ipynb) | Satisfying vs optimising metrics, when metrics fail, and the references used throughout the course. |

---

## Getting started

**Requirements:** Python 3.10 or newer (tested on Python 3.12).

```bash
# 1. Clone the repository
git clone <repository-url>
cd <repository-folder>

# 2. Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# 3. Install the dependencies
pip install -r requirements.txt

# 4. Launch Jupyter
jupyter lab
```

---

## Running the notebooks

- **Self-contained setup.** Notebooks that build on earlier work start with a *Setup* cell that
  silently re-runs the notebook they depend on:

  | Notebook | Re-runs |
  |---|---|
  | 2.2, 2.3, 2.4 | 2.1 |
  | 4.2, 4.3 | 4.1 |

  Every notebook can therefore be opened and run on its own, as long as all notebooks sit in the
  same folder.

- **Execution time.** Most notebooks run in a few seconds. The notebooks in Module 4 retrain
  several networks and take longer on a typical laptop CPU:

  | Notebook | Approximate time |
  |---|---|
  | 4.1 | ~5 min |
  | 4.2 | ~20–25 min (re-runs 4.1, then grid search and 25 Optuna trials) |
  | 4.3 | ~2–5 min |

- **Theory-only notebooks.** 1.4, 3.4, 3.5 and 4.4 contain explanations and figures only, with no
  code to run.

- **Reproducibility.** Modules 2–4 use fixed random seeds. Module 1 initialises weights randomly,
  so losses and predictions vary slightly between runs.

---

## References

- M. Nielsen, [*Neural Networks and Deep Learning*](http://neuralnetworksanddeeplearning.com/), Determination Press, 2015.
- A. Chadha, [Coursera Deep Learning Specialization — notes and solutions](https://github.com/amanchadha/coursera-deep-learning-specialization/).
- A. Chadha, [aman.ai — Distilled AI](https://aman.ai/).
- Cornell University, [CS4780 *Machine Learning for Intelligent Systems*, Lecture Note 12](https://www.cs.cornell.edu/courses/cs4780/2024sp/lectures/lecturenote12.html).
- Wikipedia, [Empirical risk minimization](https://en.wikipedia.org/wiki/Empirical_risk_minimization).
