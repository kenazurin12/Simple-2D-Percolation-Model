# Simple-2D-Percolation-Model
Python-based computational simulation of a 2D lattice percolation model. Main goal is to replicate and analyze the critical phenomena associated with phase transitions in random systems, as described in percolation theory. Code is implemented in a Jupyter Notebook (`MP3.ipynb`)

---

## Theoretical Background

Percolation theory models connectivity in random systems. This simulation uses a **2D site percolation model**, where each site on a square lattice is "occupied" with a given probability `p`.

- **Clusters:** Groups of adjacent (touching) occupied sites form "clusters" or "components."
- **Phase Transition:** As `p` increases, the system undergoes a phase transition from a fragmented state (many small, isolated clusters) to a connected state.
- **Critical Probability ($p_c$):** This transition occurs abruptly around a specific critical probability, $p_c$. At this point, a "giant component"—a single cluster that spans the entire lattice—emerges for the first time.
- **Power Law:** At the critical point, the distribution of cluster sizes is scale-invariant, meaning it follows a power-law distribution. This is a hallmark of systems at a critical threshold.

## Features

- **2D Site Percolation Simulation:** Simulates the percolation process on an L x L lattice for a range of occupation probabilities.
- **Critical Probability Estimation:** Automatically calculates the critical probability ($p_c$) by finding the point of maximum growth of the largest cluster.
- **Statistical Analysis:** Generates plots for the mean size of the largest and non-largest clusters as a function of `p`, clearly illustrating the phase transition.
- **Spatial Visualization:** Creates high-contrast intensity maps of the lattice at sub-critical, critical, and super-critical phases, with distinct coloring for each cluster and a special highlight for the largest one.
- **Power-Law Verification:** Confirms the power-law distribution of cluster sizes at criticality through a log-log plot, a linear fit, and an R² goodness-of-fit calculation.

## Dependencies

Written in Python 3 and requires the ff. libraries:

- `numpy`
- `matplotlib`
- `scipy`
- `tqdm`
- `scikit-learn`

## Code Notes

- **`percolate(L, p)` function:** Generates single `L x L` lattice for a given `p` -> identifies all clusters using `scipy.ndimage.label` -> and returns cluster sizes.
- **Main Simulation Loop:**
    - Sets simulation parameters (`L`, `num_runs`, `p_values`).
    - Iterates through each probability `p`, running `num_run` trials to get mean size of the largest and non-largest clusters.
- After running the notebook, the following PDF files will be generated in the same directory:
    - ### `means.pdf`
    - ### `[phase].pdf`
      - Four separate PDF files: `Sub-subcritical.pdf`, `Subcritical.pdf`, `Critical.pdf`, `Supercritical.pdf`
    - ### `loglogPower.pdf`
