# Thommen_Chaos_2026_SBML_gating
SBML models for external and state-referenced gating in biological oscillators — Chaos (2026), doi:10.1063/5.0357018

Four SBML Level 3 Version 2 models associated with:

**Q. Thommen**, *State-referenced gating reshapes entrainment and perturbation recovery in periodically forced biological oscillators*, **Chaos** **36** (2026). DOI: [10.1063/5.0357018](https://doi.org/10.1063/5.0357018).

## Models

| SBML file | Oscillator | Gate reference |
| --- | --- | --- |
| `Repressilator_externe.xml` | Three-variable repressilator | External Zeitgeber time; periodic Gaussian gate |
| `Repressilator_interne.xml` | Three-variable repressilator | State-referenced gate in `(x1, x2)` |
| `KimForger_externe.xml` | Kim–Forger sequestration oscillator | External Zeitgeber time; periodic Gaussian gate |
| `KimForger_interne.xml` | Kim–Forger sequestration oscillator | State-referenced gate in `(M, P)` |

The two oscillators receive a smooth 24-hour light/dark input, added to `x3` in the repressilator and `P` in the Kim–Forger system. The initial parameters are `T_free_h = 24.07`, `forcing_fraction = 0.6`, and `gate_position_h = 14`. External gates additionally expose `gate_sigma_h = 1.5`.

## Scope and reproducibility

The four files provide the forced ODE systems with **geometric gates** as described in Appendix A of the article. They support numerical trajectory simulation and selected external-versus-state-reference comparisons. They are **not** standalone reproductions of every published figure: interaction-function analysis with exact on-cycle waveform matching, Arnold-tongue continuation, constrained optimization, and local perturbation/return-map metrics require separate numerical workflows.

The internal state-space gates have pre-calibrated centers and widths for `gate_position_h` equal to **3, 14, or 20** hours (nominal width 1.5 h). For all other values, their assignment rules use the **14 h default calibration**, rather than a continuous gate-position scan. The external gate permits continuous gate-center and width changes.

## Basic usage

Load any `.xml` file into an SBML Level 3 Version 2-compatible simulator. Set the simulation horizon in hours; for example, simulate from 0 to 1200 h to inspect transients and entrainment behavior. The forcing gain is specified by `forcing_fraction` and the gate center by `gate_position_h` (hours).

For analysis of stable 1:1 entrainment domains, use periodic-orbit continuation and stability calculations rather than assuming that a 24-hour-looking trajectory proves stable locking.

## Citation

Please cite the associated *Chaos* article above when using these models. The repository includes a `CITATION.cff` file for GitHub's citation interface.

## License

No reuse license has yet been selected for this repository. Add an explicit `LICENSE` file before inviting downstream reuse.
