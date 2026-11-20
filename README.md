# ANN dataset for thermoelastic damping peaks

Data for *Size-dependent thermoelastic damping peaks in porous FG-GPLRC microplates: Semi-analytical modeling and ANN surrogates*.

- `development.csv`: 3,204 samples from 89 base designs, with semi-analytical labels and development splits.
- `holdout.csv`: 432 independent test samples from 12 base designs, with semi-analytical labels and final ANN predictions side by side.

## Columns

- `gpl_mass_fraction` is a decimal (0.035 = 3.5%). `porosity_coefficient` is dimensionless. `mcst_length_um` is in µm.
- `gpl_distribution`: UD, FG-X or FG-O. `porosity_distribution`: P1 (uniform), P2 (mid-plane enriched) or P3 (surface enriched). `mode_m` and `mode_n` are the vibration mode indices.
- `peak_inverse_quality_factor` (dimensionless) and `critical_thickness_um` (µm) are semi-analytical values. The adjacent `predicted_` columns are ANN predictions in the same units.
- `base_design_id` groups the 36 configurations at each continuous design. `cv_fold` gives the five grouped folds. For architecture selection, `architecture_split` uses fold 1 for validation and folds 2–5 for training. Final training uses the full development set.

Labels use through-thickness Fourier conduction with Maxwell–Eucken conductivity, 10 material layers and 20 thermal sublayers.
