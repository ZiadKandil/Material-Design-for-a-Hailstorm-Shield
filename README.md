# Material Design for a Hailstorm Shield

The notebook develops a reduced-order model for the material-design of a hailstorm shield and uses it to study displacement, approximation error, computational cost, and the optimal stiffness parameter.

## Notebook

- `Material_design_for_a_hailstorm_shield.ipynb`

## Workflow

1. Builds a unit-square finite-element mesh representing the rescaled shield.
2. Defines and solves the full-order linear elasticity problem for a given material ratio, impact magnitude, and impact angle.
3. Samples 100 parameter values using Latin-hypercube and uniform sampling.
4. Computes a singular value decomposition of the training snapshots and selects a five-dimensional reduced basis.
5. Assembles and solves the reduced-basis model.
6. Reports relative errors on the training and test samples.
7. Compares full-order and reduced-order computation times.
8. Computes the minimum material ratio that satisfies a displacement constraint as a function of impact angle.

## Repository Contents

- `Material_design_for_a_hailstorm_shield.ipynb`: main solution notebook.
- `problem_statement.md`: standalone text summary of the first problem.
- `requirements.txt`: Python dependencies used by the notebook.

## Requirements

The notebook uses Python packages and utilities including:

- `numpy`
- `scipy`
- `matplotlib`
- `fenics`
- `ufl-legacy`
- `dlroms`

The notebook also contains a fallback cell that installs `dlroms` directly from its GitHub repository when it is unavailable.

FEniCS is platform-dependent. On Windows, use a compatible Linux environment such as WSL or Docker if a native installation is not available.

## How to run

1. Create or activate a Python environment with the dependencies in `requirements.txt` and a working FEniCS installation.
2. Open `Material_design_for_a_hailstorm_shield.ipynb` in Jupyter or VS Code.
3. Run the notebook from top to bottom.

The notebook generates the mesh and plots, evaluates the full-order and reduced-order solutions, reports approximation errors and speed-up, and plots the admissible stiffness curve.
