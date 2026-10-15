# RAPID: analysis reproduction package

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23354645.svg)](https://doi.org/10.5281/zenodo.23354645)

Code and data to reproduce the numbers, tables and figures of the RAPID manuscript
from stored structure-prediction results. The design pipeline itself is not included.

## Reproduce

    python3 -m venv .venv-repro
    .venv-repro/bin/pip install -r requirements-repro.txt
    PYTHON=.venv-repro/bin/python3 bash scripts/reproduce_paper_tables_figures.sh

The script re-runs eleven analyses and compares every value with the committed
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

## Citation

This release is archived on Zenodo.

- Concept DOI (always resolves to the latest version): 10.5281/zenodo.23354645

Zenodo mints a separate version DOI for each release when it is published, so a
release cannot carry its own version DOI in these files. To cite the exact release
you used, open the concept DOI above, pick the version, and take the version DOI
from its Zenodo record. The manuscript cites the version it reports results from.

See `CITATION.cff` for the full citation metadata.
