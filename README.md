# RAPID: analysis reproduction package

Code and data to reproduce the numbers, tables and figures of the RAPID manuscript
from stored structure-prediction results. The design pipeline itself is not included.

## Reproduce

    python3 -m venv .venv-repro
    .venv-repro/bin/pip install -r requirements-repro.txt
    PYTHON=.venv-repro/bin/python3 bash scripts/reproduce_paper_tables_figures.sh

The script re-runs eight analyses and compares every value with the committed
results in `public_data/benchmark/gate0/` (relative tolerance 1e-9). Figures go to
`figures/submission/`. No GPU or network access is needed.

Structure prediction is not re-run. Details, data sizes and checksums are in
`docs/reproducibility.md` and `public_data/benchmark/gate0/repro_manifest.json`.

## Solubility scores

Scores come from SoluProt 1.0.1.0 (TMHMM-independent model). SoluProt is free for
academic use and is not redistributed here; `scripts/score_soluprot.py` documents how
to install it and re-score the grids.

## License

MIT (see `LICENSE`).
