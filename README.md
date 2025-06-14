# Bayesian Optimisation Capstone Competition: Strategy Reflection


## Bayesian Optimisation Capstone Competition – Individual Reflection

Throughout the Bayesian Optimisation capstone competition, I tackled eight diverse black-box optimisation problems that simulated real-world challenges across scientific and business domains. This activity offered the opportunity to apply Gaussian Process (GP)-based surrogate modelling, acquisition strategies, and domain-specific heuristics to search efficiently for optimal points with minimal function evaluations.

This document summarises my approach to each function, outlines the strategies I adopted overall, and reflects on the lessons learned from the competition.


## Function-specific Strategies and Outcomes


## Overall Strategy

Across the competition, my general strategy included:
- Fitting a Gaussian Process model with a Matern kernel.
- Using Expected Improvement or Upper Confidence Bound as the acquisition function.
- Rescaling inputs using MinMaxScaler to stabilise model convergence.
- Employing trust-region logic or manual bound narrowing in functions with clear optima.
- Visualising predictions with 3D surface plots and parallel coordinate plots.
- Using permutation-based feature importance to guide dimension fixing.


## Key Lessons Learned

- **Visual intuition is crucial**: Exploratory plots provided critical insight into behaviour, especially when models struggled.
- **Exploration-exploitation balance varies**: Noisy functions benefited from broader exploration (Function 2), while known multimodal functions needed targeted sampling (Function 1).
- **Dimensionality is a challenge**: Higher-dimensional functions (7 and 8) significantly strained GP models. Dimensionality reduction or hybrid models might be needed in future competitions.
- **Surrogate model tuning matters**: Choosing the right kernel, adjusting bounds, and scaling inputs all impacted performance.
- **Iterative refinement improves performance**: Weekly feedback could guide model retraining or feature-bound adjustment.


The Bayesian optimisation competition deepened my understanding of model-based optimisation, surrogate modelling, and hyperparameter tuning in low-data scenarios. These lessons will directly benefit my ongoing work in sports tech and retail optimisation challenges.


## Evolution of Approach Across Functions

As the competition progressed, my approach to the various functions evolved significantly. Initially, I applied a uniform strategy across all functions using Gaussian Process (GP) regression with Expected Improvement (EI) as the acquisition function. However, the diversity of function characteristics required more nuanced strategies. Here are the main changes:

- For Function 1, I quickly realised it had two distinct peaks, so I implemented region-specific Bayesian optimisation to explore each mode independently.
- In Function 2, the high noise led me to switch to Upper Confidence Bound (UCB) instead of EI, favouring broader exploration.
- Function 3 included a clue suggesting one compound had minimal impact. I ran feature importance analysis to confirm and reduced the dimensionality of the search space.
- Function 4 involved tuning a surrogate model, which mirrored the capstone's objective closely. I tuned the GP kernel and prioritised frequent residual checks.
- For Function 5, I adapted a trust-region approach to focus around known high-yield points and added 3D visualisations to understand interactions.
- Function 6 introduced multiple conflicting objectives. I adopted a strategy of minimising absolute values to approximate a target of zero.
- In Functions 7 and 8, the high dimensionality led me to try random restarts, tighter bounds around good observations, and more robust standardisation of inputs.

