# Pop Goes the Nation

**What Billboard, GDP, and Spotify audio features say about America's mood.**

A data analysis project exploring whether the mood of popular music shifts when the country experiences economic stress, and which factors actually predict a song's chart longevity.

---

## Overview

This project merges three independent datasets — the Billboard Hot 100, US GDP, and Spotify audio features — to investigate a central question: **does popular music sound different when the economy struggles or the country is in crisis?**

Along the way it examines how chart volume, song longevity, collaborations, and superstar dominance have evolved, and whether early chart performance can predict long-running hits.

## Data

| Dataset | Coverage | Description |
|---------|----------|-------------|
| Billboard Hot 100 | 1958–2021 | 64 years of weekly chart data |
| US GDP | 1997–2020 | Annual economic growth |
| Spotify Audio Features | — | Valence, acousticness, and other mood signals |

## Approach

1. **Load** Billboard, GDP, and Spotify CSVs into pandas DataFrames.
2. **Clean & transform** — standardize columns, convert dates, derive `year`, `month`, and `decade`.
3. **Engineer features** — binary flags for collaborative tracks and "crisis" years (recessions, wars, pandemics).
4. **Merge** all three sources into a single analysis-ready DataFrame.
5. **Explore** trends in chart volume, longevity, mood, and collaborations.
6. **Model** song longevity with supervised learning (Random Forest, Decision Tree).

## Key Findings

- **Charts have grown and sped up.** Annual Hot 100 entries rose from ~2,226 to ~6,434; average weeks on chart ranged from ~5.2 to over 13.1 across decades — more churn, but enduring hits persist.
- **Collaboration culture took over.** Collaborative tracks grew from 6.5% (early years) to 15.7% (recent years).
- **The economy barely moves song longevity.** Average weeks on chart were nearly identical in strong vs. weak GDP years (11.69 vs. 11.74), with only a weak negative correlation (−0.21).
- **Crisis years sound *slightly* brighter, not sadder.** Average valence rose from 0.57 (normal) to 0.62 (crisis), and acousticness from 0.22 to 0.33 — though individual #1 hits varied widely.
- **Early chart momentum is the strongest predictor.** A Decision Tree classifier predicted long-running-hit status with **93% accuracy**, with strong early rank and high peak rank driving longevity.

## Models

- **Random Forest Regressor** — predicts total `weeks_on_board` from chart performance and time-based features; evaluated with MSE and R².
- **Decision Tree Classifier** — predicts whether a song lasts 20+ weeks (93% test accuracy), producing interpretable if-then rules.

## Tech Stack

- Python
- pandas, NumPy
- scikit-learn
- Matplotlib / Seaborn


