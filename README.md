# Lotka-Volterra Model Fitting

This project recovers the parameters of a Lotka-Volterra predator-prey ODE system from noisy time-series observations. Starting from synthetically generated data with added Gaussian noise, we formulate parameter estimation as a nonlinear least-squares problem and solve it using both local optimisation (gradient-based) and global optimisation (differential evolution) to assess sensitivity to initial guesses and to find the true underlying dynamics. The results, methodology, and analysis are documented in the accompanying PDF report.

## Methods and Tools

- **Lotka-Volterra ODE model** -- classical two-species predator-prey system integrated with `scipy.integrate.solve_ivp`
- **Local optimisation** -- gradient-based minimisation of the residual sum of squares (`scipy.optimize.minimize`)
- **Global optimisation** -- differential evolution for robust parameter recovery without dependence on initial guesses (`scipy.optimize.differential_evolution`)
- **Libraries**: NumPy, SciPy, Matplotlib, Jupyter

## Project Structure

```
├── main(run_me).ipynb                          # Main notebook -- run this
├── src/
│   ├── model.py                                # Lotka-Volterra ODE definition
│   ├── optimization.py                         # Local and global optimisation routines
│   ├── utils.py                                # Plotting and data-loading utilities
│   └── __init__.py
├── data/
│   └── predator-prey-data.csv                  # Noisy predator-prey observations
├── Reverse Engineering Predator-Prey System.pdf  # Written report
└── old/
    └── main.py                                 # Earlier prototype script
```

## Requirements

- Python 3.9+
- NumPy, SciPy, Matplotlib, Jupyter

## Usage

```bash
jupyter notebook "main(run_me).ipynb"
```

The notebook loads the data, runs both optimisation approaches, and plots the fitted trajectories against the noisy observations.

## Course

Scientific Computing, University of Amsterdam, 2024
