
# Minimal supporting data

This repository contains the minimum processed simulation data needed to inspect the numerical results reported in **Constraint-Guided Reinforcement Learning for Microgrid Energy Storage Scheduling Toward Virtual Power Plant Applications**.

## Included files

| File | Manuscript result supported |
|---|---|
| `data/training_curves_summary.csv` | Figures 3 and 5; mean 20-episode moving-average reward and sample SD across seeds 42, 142, and 242 |
| `data/table3_ablation_daily.csv` | Table 3; 50 held-out test days for each ablation configuration |
| `data/table3_ablation_summary.csv` | Table 3 reported means |
| `data/robustness_daily.csv` | Robustness evaluation; 50 held-out days for each method, case, and severity level |
| `data/robustness_summary.csv` | Robustness summary statistics |
| `data/robustness_plot_summary.csv` | Values plotted in the robustness figure |
| `data/representative_day_dispatch.csv` | Figure 4; selected 24-hour dispatch trajectory |
| `data/representative_day_metadata.json` | Representative-day selection rule and selected-day totals |
| `data/action_correction_traces.csv` | Hourly raw actions, executed actions, feasible bounds, and SOC |
| `data/action_correction_summary.csv` | Daily correction-energy totals for those traces |
| `data/unabsorbed_surplus_daily.csv` | Daily unabsorbed surplus energy under surplus-power scenarios |
| `data/unabsorbed_surplus_summary.csv` | Reported mean and SD of unabsorbed surplus energy |
| `metadata/*.json` | Base parameters, training seeds, and robustness scenario definitions |

## Scope

The deposited files are processed source data supporting the manuscript figures, tables, and numerical statements. They exclude model checkpoints, complete training code, generated figures, the full representative-day candidate pool, and unrelated intermediate outputs. All evaluations use 24 one-hour intervals. Daily cumulative correction energy is `sum(abs(raw_action_kw - executed_action_kw) * 1 h)` and is reported in kWh.

## Recalculation notes

- Table 3 values are arithmetic means over the 50 rows belonging to each algorithm.
- Robustness values are arithmetic means over the 50 rows belonging to each case, severity level, and algorithm.
- Training curves first apply a trailing 20-episode moving average within each seed, then report the mean and sample SD across three independently trained seeds.
- Robustness confidence intervals use `1.96 * sample SD / sqrt(50)`.

## File format and licence

All tables are UTF-8 CSV files with a header row. JSON files contain configuration metadata. See `DATA_DICTIONARY.md` for variable definitions. Before public release, the authors should add a data licence approved by their institution and target journal, such as CC BY 4.0 or CC0. No licence is assigned by this preparation package.
