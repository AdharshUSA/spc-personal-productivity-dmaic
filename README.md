# Statistical Process Control on a Personal Self-Tracking Dataset

Individual project for **IE 530 Quality Control** (Purdue, April 2026). A seven-week study that applies the DMAIC framework and standard SPC tools to a self-collected dataset, treating day-to-day routine as a process whose variation can be measured.

The report covers Define, Measure and Analyze in depth, and lays out Improve and Control as a plan. The recorded data is in [`data/daily_observations.csv`](data/daily_observations.csv).

## Data

- 10 binary daily self-assessments (0 = issue absent, 1 = issue present), recorded each evening
- 49 consecutive days, giving 490 observations in total
- 292 defect events recorded, a mean of 5.96 per day (p-bar = 0.596)
- File layout: one row per item (1 to 10), one column per day (d1 to d49)

| Item | Behavior tracked | Days flagged (of 49) |
|---|---|---|
| 1 | Workload balance | 25 |
| 2 | Tech distraction | 30 |
| 3 | Irregular sleep | 31 |
| 4 | Procrastination | 29 |
| 5 | Skipping exercise | 33 |
| 6 | Social media | 29 |
| 7 | Disorganized space | 22 |
| 8 | Inconsistent routines | 29 |
| 9 | Overthinking | 33 |
| 10 | Exam stress | 31 |

## Methods

| Tool | Purpose | Result |
|---|---|---|
| p-chart | Daily proportion of items flagged | Every day inside the limits, so no special-cause variation. UCL = 1.061, which exceeds 1.0 because p-bar is high and the subgroup size is only 10 |
| c-chart | Daily count of flagged items | UCL = 13.28; daily counts ranged from 3 to 9, all in control |
| Pareto analysis | Which items drive most of the defects | Fairly flat distribution: the top four items together made up 43.8% of occurrences |
| Weekly trend analysis | Temporal patterns | Weekly totals of 51, 43, 33, 50, 43, 39 and 33: peaks in weeks 1 and 4, lowest in weeks 3 and 7 |

## Findings

1. The process is statistically stable, so the variation is common-cause (built into the system), not driven by special events. Improvement needs a change to the system, not a hunt for one-off causes.
2. A flat Pareto means no single dominant cause. Gains come from addressing several of the top contributors together.
3. The weekly pattern lines up with the academic calendar, with higher counts early in term and mid-term.
4. The lowest weeks come at the end of the study, which the report attributes to a likely Hawthorne effect from self-monitoring.

## Limitations

- Self-reported, subjective binary scoring from one person, so it does not generalize
- One 49-day window with no control group
- With only 10 items per day the p-chart limits are wide, and the p-chart upper control limit is above 1.0, so in practice it is capped at 1.0 and cannot signal an upward shift

## Skills demonstrated

DMAIC, control chart construction and interpretation (p and c charts), Pareto analysis, data collection design, and reading statistical results with their limits in mind.
