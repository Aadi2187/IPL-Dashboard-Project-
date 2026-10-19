# IPL 2025 Dashboard Project: Insights and Solution

Analysis of `IPL_Dashboard_Project.xlsx` (60 matches, 22 Mar to 19 May 2025).

## Files
| File | Purpose |
|---|---|
| `IPL_Solution_Report.pdf` | Full solution report (insights, answers, data issues, recommendations) |
| `IPL_Insights_Presentation.pptx` | Presentation deck |
| `analysis.py` | Python script that rebuilds the tables and charts |
| `team_table.csv`, `top_bat.csv`, `top_bowl.csv`, `venue.csv` | Output tables |
| `charts/` | Chart images used in the report |

## Data
Sheets used: `fact_match` (60 rows), `fact_player` (201 rows), `dim_team` (8), `dim_player` (33), `dim_venue` (10). The pivot/dashboard sheets were not used as a data source.

## Key insights
1. **SRH (69.2%) and CSK (66.7%)** have the best win rates; PBKS (33.3%), DC (35.7%), MI (38.5%) the worst.
2. **RCB** scores the most per match (182.6) at the highest-scoring ground (Bengaluru, 185.7) but wins only 54.5% and concedes the most (180.6).
3. **Home side won 60%** of decided matches (30/50). The home side also bats first in this data, so the effects overlap.
4. **Toss winners won only 30%** (15/50): the toss was not an advantage.
5. **Virat Kohli**: 982 runs, avg 65.5, SR 162.6, most Man of the Match awards (4).
6. **Finishers**: Russell (SR 189.7) and Klaasen (SR 188.3); 71 to 75% of their runs come in boundaries.
7. **Bowling**: Bumrah 25 wickets (economy 6.95); Kuldeep best economy (4.60).
8. **Scoring**: average innings 174.5; only 3 scores of 200+ (max 208); sixes are 25.7% of player runs.

## Method
- Win % = wins / decided matches, where the winner is one of the two teams playing.
- Avg scored/conceded = runs per team innings.
- Strike rate = runs / balls x 100 (rows with balls faced > 0). Economy = runs conceded / overs (rows with overs > 0).
- Venue average = mean of first- and second-innings averages.

## Data quality notes (please verify at source)
- 10 of 60 matches list a `Match_Winner` who did not play; excluded from win, toss and home analysis. Run totals in 7 matches also conflict with the recorded winner.
- The workbook's average strike rate (106.7) includes bowling-only rows with 0. Correct weighted value: **166.0**.
- The workbook's Economy KPI sums the column (613.4). Correct weighted value: **7.08**.
- Team-level wickets (799) count wickets lost by batting sides in each innings; player-level wickets total 178 because player rows cover only about 3 players per match. Player leaderboards are therefore a sample.
- Small samples (13 to 16 matches per team, 5 to 8 per venue): treat results as indicative.

