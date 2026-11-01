# Relative temporal-difference octree refinement for tabular Q-learning in 3D UAV path planning

Simulation code and result files for the paper submitted to the Journal of Science and
Technique (manuscript 1279).

Author: Nguyen Van Bang, Faculty of Missiles, Air Defence-Air Force Academy, Ha Noi, Viet Nam
(banghvpkkq@gmail.com, ORCID 0000-0002-9354-9283).

## Contents

- `code/paper2_sim.py`: Complete simulation in one file (Python 3, NumPy, Matplotlib):
  three-dimensional kinematics, backup-maneuver safety filter, uniform grids, octree with the
  relative temporal-difference split rule, alternative scores, visit-count and
  absolute-threshold refinement, double DQN with action masking, A* search, the frozen-table
  check of Proposition 1, and all figures.
- `figs/p2r/*.json`: Result files of the revision experiments (one file per run: three seeds,
  three maps, visit-count and absolute-threshold refinement, reward scaling, A* search,
  frozen-table check). The tables and Figs. 8 to 10 of the paper are generated from them.
- `figures/`: Figs. 8 to 10 as produced by the code.

The script writes and reads its results relative to its own location (`../figs/...`), so
keep the folder layout above.

## Usage

```
cd code
python3 paper2_sim.py --all          # original 17 configurations (Tables 2 to 4), 6000 episodes each
python3 paper2_sim.py --revall       # revision experiments (seeds, maps, baselines, A*, DQN)
python3 paper2_sim.py --rev M_td_s2027 S_td_s2026 astar   # selected runs
python3 paper2_sim.py --figs --revfigs                    # redraw all figures
```

Run names: `<map>_<config>_s<seed>[_x<reward scale>]`, with map S, M or D, config `td`
(proposed), `u12`, `u24` (uniform grids), `count` (visit counting), `abs8` (absolute
threshold 8). All runs are deterministic for a given seed.

## License

MIT License, see `LICENSE`.
