# Problem Statement

## Material design for a hailstorm shield

A square shield is modeled in two dimensions as a linearly elastic body. The lower edge is clamped, the body force acts vertically downward, and a hailstone applies a localized traction on the upper edge. The shield is made of two materials: the lower half has reference Lamé parameters, while the upper half has both parameters multiplied by a material ratio `r`.

The impact is described by a magnitude `m` and an angle `theta`. The parameter vector is

```text
mu = [r, m, theta]
```

with

```text
0.5 <= r <= 1.0
0.5 <= m <= 2.0
-0.4 <= theta <= 0.4.
```

The geometry is rescaled to the unit square. A hailstone of diameter 1.2 cm is represented by a localized load with radius 0.1 around the center of the top boundary.

The displacement field `u` is computed from the linear elasticity variational problem with zero displacement on the lower boundary. The notebook solves the full-order model, constructs a reduced basis from sampled solutions, and evaluates the reduced-basis approximation.

## Tasks addressed by the notebook

1. Generate 100 full-order solutions from parameter samples and compute a singular value decomposition of the training snapshots.
2. Select a five-mode reduced basis and build a reduced-order solver.
3. Compute average, minimum, and maximum relative errors on training and test samples.
4. Compare the online reduced-order computation time with the full-order solve.
5. For a fixed impact magnitude, determine the minimum material ratio `r` that keeps the maximum vertical displacement below the prescribed critical value, and plot this value as a function of the impact angle `theta`.

The notebook uses the `dlroms` finite-element utilities together with FEniCS, NumPy, SciPy, and Matplotlib.
