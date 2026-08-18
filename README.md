DOI: [![DOI](https://zenodo.org/badge/1338409061.svg)](https://doi.org/10.5281/zenodo.21995874)
# Gaia–APOGEE–GALAH RGB chemical-label transportability

## Reproducibility release 2.1.0

Authors: **Hilola Arslonova, Salakhutdin Nuritdinov, and Sobir Turaev**.

This archive accompanies the study **“Testing cross-survey chemical-label transportability in a Gaia–APOGEE–GALAH red-giant atlas.”** It contains the analysis-code snapshot, frozen configurations and protocols, publication figures, machine-readable result tables, numerical validation records, and executable checks. The manuscript source and compiled manuscript are intentionally excluded.

The release separates four questions: overlap-sample calibration, robustness of Galactic gradients on comparable survey support, detectability of radial transitions, and stability of alpha-sequence morphology. Decisions are reported as stable, sensitive, or indeterminate according to predefined numerical rules. An indeterminate outcome is not interpreted as evidence of physical equality or absence.

### Principal results

- The merged parent catalogue contains 1,591,571 unique sources; authoritative global-gradient fits use 315,818–323,324 stars per label.
- The common-footprint analysis contains 34,177 stars in 208 HEALPix NSIDE=16 cells.
- `[Ni/Fe]` is stable in radial and vertical gradients. `[Si/Fe]` and `[Ca/Fe]` are stable vertically and indeterminate radially. `[Fe/H]` and `[Mg/Fe]` are indeterminate in both coordinates.
- The alpha-sequence morphology analysis contains 26,180 eligible stars. Its three cross-survey morphology estimands remain indeterminate.
- The smaller fitted GALAH sequence separation at low metallicity is associated with larger abundance-error proxies and lower native signal-to-noise, but the contrast persists in the high-signal-to-noise subset. The audit does not identify which survey is closer to the underlying distribution.
- In 36 prospective survey designs, the maximum null false-positive rate is 3.91%. No tested design reaches 80% or 90% power across both signal signs and both transition locations. The best worst-case power is 10.94%.

### Contents

- `tables/`: machine-readable numerical results and sensitivity summaries.
- `figures/`: five vector publication figures.
- `validation/`: integrity and simulation-validation records.
- `scripts/`: release validation and forecast-summary reconstruction.
- `code/pipeline/`: complete collected analysis-code snapshot, launchers, configurations, protocols, self-tests, and dependency specifications.
- `documentation/`: methods, provenance, data access, column definitions, and limitations.
- `CITATION.cff`, `.zenodo.json`: citation and deposit metadata.
- `MANIFEST.sha256`: file-level integrity manifest.

### Validation

From the archive root, run:

```bash
python scripts/validate_release.py
python scripts/recompute_forecast_summary.py
```

The first command checks file integrity, row counts, key numerical results, and metadata. The second reconstructs the principal power statistics directly from the included simulation replicates.

The full pipeline uses public upstream survey catalogues that are not redistributed. Its preserved stage identifiers are functional path and configuration keys rather than scientific terminology; renaming them would break exact launcher/configuration correspondence. See `documentation/CODE_INVENTORY.md` and `documentation/EXECUTION_GUIDE.md`.

### Data scope

Gaia DR3, APOGEE DR17, and GALAH DR4 source catalogues are not redistributed. The included tables are derived numerical products. See `documentation/DATA_ACCESS.md` for source identifiers and reconstruction requirements.

### Licence

Tables, figures, and documentation are licensed under CC BY 4.0. Code in `scripts/` is licensed under MIT.
