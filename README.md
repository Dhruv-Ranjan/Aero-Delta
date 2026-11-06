# AeroDelta-4 — Cropped-Delta UAV Performance Project

Independent Project 4 implementation by **Dhruv Ranjan**. The project evaluates trim, speed, thrust required, and power required for a 3.5 kg cropped-delta UAV in steady level flight.

## Project description

Aero-Delta is a computational aerodynamic analysis of a cropped-delta unmanned aerial vehicle (UAV). The project evaluates the aircraft's lift, drag, trim, thrust, and power requirements across a range of angles of attack and flight speeds. It also examines how uncertainty in the aircraft and operating conditions affects performance at a representative angle of attack.

The analysis combines a nominal flight-condition sweep with a Monte Carlo uncertainty study. The results are presented as tabulated data, summary metrics, and figures that support early-stage aerodynamic sizing, propulsion selection, and flight-envelope assessment.

## Key results

- Wing area: **0.7875 m²**
- Aspect ratio: **2.857**
- Taper ratio: **0.167**
- Weight: **34.32 N**
- Nominal minimum power required: **42.52 W**
- Nominal minimum thrust required: **3.84 N**
- Monte Carlo samples accepted: **10,000**
- Monte Carlo acceptance rate: **100%**

## What is included

- `build_project.py` — single source of truth for the model, plots, CSV exports, and Word report.
- `deliverables/AeroDelta-4_Cropped_Delta_UAV_Report.docx` — completed technical report with native Word math paragraphs and editable linear-LaTeX source beneath each equation.
- `deliverables/nominal_sweep.csv` — angle-of-attack performance sweep.
- `deliverables/uncertainty_samples_alpha6deg.csv` — seeded 10,000-trial coefficient-uncertainty study.
- `deliverables/figures/` — labelled report figures.
- `deliverables/results_summary.txt` — headline numerical results.

## Run it

```powershell
python -m pip install -r requirements.txt
python build_project.py
```

The script recreates `deliverables/` so that every output is generated from the current source. The aerodynamic coefficient table in the supplied assignment was blank, so the report explicitly labels the coefficient values as illustrative placeholders. Replace them in the `Inputs` dataclass before making validated performance claims.

## Model scope

The model uses a trapezoidal planform, linear lift and pitching-moment models, a parabolic drag polar, steady-level lift equilibrium, and a transparent screening limit. The uncertainty extension perturbs aerodynamic coefficients with a fixed seed and reports percentile envelopes; it is a sensitivity study, not a flight-test confidence interval.

## Suggested repository setup

```powershell
git init
git add README.md requirements.txt build_project.py
git add deliverables
git commit -m "Build AeroDelta-4 cropped-delta UAV project"
```

The original supplied files are retained in the folder for traceability. They are not used as hidden inputs by the generator.
