# Data sources and acquisition

Data files are not committed to this repository. To reproduce the analysis, download the datasets using the sources and settings documented below and place them in `data/raw/`.

## American Soccer Analysis (ASA)

Nine CSV files were downloaded manually from the [ASA application](https://app.americansocceranalysis.com/). The download date was removed from each filename; the file contents remain unchanged.

### MLS

Acquisition date: November 5, 2026.

| Source                                                                                             | Filename                                                   |
| -------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| [Salaries](https://app.americansocceranalysis.com/#!/mls/salaries/players)                         | `american_soccer_analysis_mls_salaries_players.csv`        |
| [Goals Added — Players](https://app.americansocceranalysis.com/#!/mls/goals-added/players)         | `american_soccer_analysis_mls_goals-added_players.csv`     |
| [Goals Added — Goalkeepers](https://app.americansocceranalysis.com/#!/mls/goals-added/goalkeepers) | `american_soccer_analysis_mls_goals-added_goalkeepers.csv` |
| [Expected Passes](https://app.americansocceranalysis.com/#!/mls/xpass/players)                     | `american_soccer_analysis_mls_xpass_players.csv`           |
| [Expected Goals](https://app.americansocceranalysis.com/#!/mls/xgoals/players)                     | `american_soccer_analysis_mls_xgoals_players.csv`          |

### USLC

Acquisition date: November 25, 2026.

| Source                                                                                              | Filename                                                    |
| --------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| [Goals Added — Players](https://app.americansocceranalysis.com/#!/uslc/goals-added/players)         | `american_soccer_analysis_uslc_goals-added_players.csv`     |
| [Goals Added — Goalkeepers](https://app.americansocceranalysis.com/#!/uslc/goals-added/goalkeepers) | `american_soccer_analysis_uslc_goals-added_goalkeepers.csv` |
| [Expected Passes](https://app.americansocceranalysis.com/#!/uslc/xpass/players)                     | `american_soccer_analysis_uslc_xpass_players.csv`           |
| [Expected Goals](https://app.americansocceranalysis.com/#!/uslc/xgoals/players)                     | `american_soccer_analysis_uslc_xgoals_players.csv`          |

### Download filters

| Parameter             | Setting                                     |
| --------------------- | ------------------------------------------- |
| MLS salaries          | 2016–2026                                   |
| MLS performance       | 2016–2025                                   |
| USLC performance      | 2017–2025                                   |
| Teams                 | All                                         |
| Positions             | All                                         |
| Passing third         | All                                         |
| Action types          | All                                         |
| Patterns of play      | All                                         |
| Competition stages    | All, including playoffs and knockout rounds |
| Group results         | Split by season                             |
| Goals Added variation | Above Average                               |
| Normalization         | Per 96 minutes                              |
| Minimum minutes       | 0                                           |
| Minimum shots         | 0                                           |
| Minimum key passes    | 0                                           |
| Minimum passes        | 0                                           |

Performance filters apply to both competitions wherever the corresponding settings are available.

The performance datasets were downloaded without minimum participation thresholds or restrictions on teams, positions, action types, or competition stages. Any subsequent population restrictions are applied during analysis rather than acquisition.

Although salary data extends to 2026, the current analysis covers 2016–2025. USLC performance data is unavailable for 2016 in the downloaded tables.

## Transfermarkt — Archived exploration

Source: [Football Data from Transfermarkt — Kaggle](https://www.kaggle.com/datasets/davidcariboo/player-scores).

The following files were downloaded for the `attribute_coverage_exploration` notebook:

- `clubs.csv`
- `competitions.csv`
- `players.csv`

The notebook has since been archived. These datasets are retained for historical reproducibility but are not required for the current analysis.

## Directory structure

- `data/raw/` — Original source datasets.
- `data/interim/` — Intermediate datasets generated during analysis.
- `data/interim/transfermarkt_coverage/` — Outputs from the archived Transfermarkt exploration.

## Reproducibility

The documented sources, filters, and filenames allow users to repeat the acquisition process. However, providers may revise historical data, meaning subsequent downloads may not exactly reproduce the original datasets.
