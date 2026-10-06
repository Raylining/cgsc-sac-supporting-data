
# Data dictionary

| Field or suffix | Definition | Unit/type |
|---|---|---|
| `method`, `algorithm` | Evaluated learning method | category |
| `seed`, `test_seed` | Training or held-out test-day random seed | integer |
| `episode` | Training episode index | integer |
| `mean_20_episode_moving_average_reward` | Across-seed mean of the trailing 20-episode reward average | scaled reward |
| `sd_across_training_seeds` | Sample SD across three independently trained seeds | scaled reward |
| `reward` | Daily cumulative evaluation reward | scaled reward |
| `operating_cost` | Grid purchase minus export revenue plus throughput and load-shedding costs | monetary objective unit |
| `raw_action_violation_rate` | Fraction of 24 raw actions outside the feasible interval | fraction |
| `safety_layer_trigger_rate` | Fraction of 24 actions changed by safety clipping | fraction |
| `final_action_violation_rate` | Fraction of executed actions violating final bounds | fraction |
| `correction_energy_kwh` | Sum of hourly absolute raw-to-executed power corrections multiplied by 1 h | kWh |
| `load_shedding_kwh` | Daily unserved demand | kWh |
| `unabsorbed_surplus_kwh` | Daily surplus remaining after charging and export limits | kWh |
| `case` | Nominal, supply-stress, or surplus-power case | category |
| `severity` | Perturbation level S0 to S3 | category |
| `hour` | Hourly interval start, 0 to 23 | hour index |
| `load_kw`, `pv_kw`, `net_load_kw` | Demand, PV generation, and demand minus PV | kW |
| `grid_power_kw` | Grid exchange, positive for import | kW |
| `battery_power_kw` | Executed battery power, positive for discharge | kW |
| `raw_action_kw`, `executed_action_kw` | Policy output before and after safety clipping | kW |
| `safe_low_kw`, `safe_high_kw` | Feasible battery-power interval | kW |
| `soc_percent`, `soc_percent_start`, `soc_percent_end` | Battery state of charge | percent |
| `buy_price_per_kwh` | Hourly electricity purchase price | currency/kWh |
| `mean`, `ci95`, `n` | Plot mean, 95% CI half-width, and sample count | metric-specific |

Rates must be multiplied by 100 when displayed as percentages. CSV files contain no encoded missing-value marker.
