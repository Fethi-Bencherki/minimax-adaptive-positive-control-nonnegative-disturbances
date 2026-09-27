# Minimax Adaptive Positive Control under Nonnegative Disturbances

Jupyter Notebook example associated with the paper **“Minimax Adaptive Control of Positive Systems under Nonnegative Disturbances”** by Fethi Bencherki.

This repository contains the numerical experiment used to illustrate certainty-equivalence (CE) control of a positive linear system with a fixed but unknown input matrix and nonnegative disturbances. The experiment propagates an interval of models consistent with the observed transitions, adapts the positivity-preserving input bound as this interval contracts, and compares the adaptive controller with a benchmark that knows the true model.

## Repository Contents

- 📘 **Continuum uncertainty in the input matrix**  
  [interval_B_vector_ce.ipynb](interval_B_vector_ce.ipynb)  
  Simulates a two-state positive system with scalar input and componentwise interval uncertainty in the fixed input vector. The notebook computes the CE estimate directly from the interval endpoints, updates the consistency interval from the observed transitions, and adjusts the safe input bound using the models that remain feasible. It compares the resulting state and input trajectories with those of a controller that knows the true input vector.

The notebook is self-contained. Each code section is preceded by a short explanation, and a function table summarizes the consistency-set update, CE selection rule, adaptive gain, simulation routines, and figure-export utilities.

## Installation

The required packages are:

```bash
python -m pip install numpy matplotlib jupyter tikzplotlib
```

- **NumPy** is used for the system simulation, interval updates, and linear-algebra calculations.
- **Matplotlib** displays the numerical results and exports PDF and PNG figures.
- **tikzplotlib** exports the Matplotlib panels as TikZ/PGFPlots `.tex` files.
- **Jupyter** runs and displays the notebook.

## Numerical Experiment

| Panel | Quantity shown |
| --- | --- |
| Figure 1 | First-state trajectory: adaptive CE controller versus known-model benchmark |
| Figure 2 | Second-state trajectory: adaptive CE controller versus known-model benchmark |
| Figure 3 | Control input: adaptive CE controller versus known-model benchmark |
| Figure 4 | Adaptive components of $E(\mathcal C_t)$ and the known-model values $E(\{B_\star\})$ |
| Figure 5 | Consistency interval, CE estimate, and true value for $B_1$ |
| Figure 6 | Consistency interval, CE estimate, and true value for $B_2$ |

The same nonnegative disturbance realization is applied to the adaptive and known-model controllers. By default, `SEED = None`, so rerunning the notebook generates a new realization. Set `SEED` to an integer to reproduce a particular run.

## Figure Export

Running the notebook creates the combined simulation figure in the repository root:

| Output | Format |
| --- | --- |
| `interval_B_vector_ce_simulation.pdf` | Vector PDF |
| `interval_B_vector_ce_simulation.png` | High-resolution PNG |

It also creates the following TikZ/PGFPlots files in `figures/`:

| Generated file | Content |
| --- | --- |
| `figures/state_x1.tex` | First-state trajectory |
| `figures/state_x2.tex` | Second-state trajectory |
| `figures/control_input.tex` | Control input |
| `figures/adaptive_bound.tex` | Adaptive and known-model input bounds |
| `figures/interval_B1.tex` | Consistency interval for $B_1$ |
| `figures/interval_B2.tex` | Consistency interval for $B_2$ |
| `figures/interval_B_vector_ce_all_panels.tex` | Combined six-panel layout |

## Citation

If you use this code, please cite the associated paper:

```bibtex
@misc{bencherki2026minimax,
  title  = {Minimax Adaptive Control of Positive Systems under Nonnegative Disturbances},
  author = {Bencherki, Fethi},
  year   = {2026}
}
```
