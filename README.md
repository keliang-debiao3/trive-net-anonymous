TRiVE-Net
This repository contains the TRiVE-Net code package for cross-corpus music emotion prediction. It includes model components, data preparation tools, evaluation scripts, configuration files, repository checks, and documentation.
Repository contents
Path	Contents
src/trive_net/	TRiVE-Net model definition, audio feature handling, target construction, loss functions, calibration, metrics, statistical utilities, and reference-artifact support.
configs/trive_deam.yaml	Model, feature, training, label-mapping, and evaluation settings for the DEAM and SunoCaps workflow.
configs/baselines.yaml	Baseline configuration definitions.
scripts/	Command-line programs for manifest auditing, feature caching, grouped fold creation, cache-list preparation, layer selection, cross-validation training, prediction, ensembling, out-of-fold merging, external validation, ablation runs, statistical analysis, reference-artifact generation, and repository checks.
data/README.md	The required DEAM and SunoCaps manifest fields and the feature-cache layout.
results/reference/	Reference CSV and JSON files constructed from manuscript-specified numerical matrices for checking aggregation and output formats.
logs/reference/	Deterministic reference traces for the package's data-audit, training, evaluation, and reporting workflows. These files are not raw training logs or hardware telemetry.
tests/	Tests for core package components and statistical utilities.
run_study.sh	Shell entry point connecting manifest checks, fold preparation, training, prediction, ensembling, and external evaluation.
run_all.sh, Makefile	Entry points for reference-artifact generation, repository checks, and tests.
REPRODUCIBILITY.md	Execution order, artifact categories, random-seed settings, and data-partition boundaries.
ANONYMITY.md	Notes on the package's anonymous-review metadata.
requirements.txt, pyproject.toml	Python dependencies and package configuration.
LICENSE, CITATION.cff, .gitignore	License, citation metadata, and version-control exclusions.


Code modules
The src/trive_net/ package separates the network architecture (model.py), feature processing (features.py), target handling (targets.py), training objectives (losses.py), temperature calibration (calibration.py), evaluation measures (metrics.py), and statistical procedures (statistics.py). reference.py supports the packaged reference artifacts.

The scripts cover the DEAM grouped development workflow and the SunoCaps external-evaluation workflow. They include components for foundation-model layer selection, tonal and rhythmic feature preparation, model training, prediction combination, component ablations, calibration, and statistical comparisons. The source code and configuration files specify the detailed implementation.
Data and artifacts
Audio files are not included. data/README.md describes the manifest schemas used to point the scripts to locally obtained DEAM and SunoCaps audio. Newly executed workflows create their own files in user-selected run directories; the bundled results/reference/ and logs/reference/ directories contain reference materials supplied with the package.
