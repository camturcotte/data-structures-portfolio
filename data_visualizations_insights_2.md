# Data Visualizations and Insights

## Predicted Versus Actual Shots on Goal

I created a scatterplot comparing the Poisson model's predicted shots with actual shots in the 2023–24 regular season. Each point represents one team in one game. The horizontal axis shows predicted shots, and the vertical axis shows actual shots. The dashed diagonal line represents perfect predictions.

Most predictions cluster around typical shot totals, while actual results vary more widely. Points above the line represent underpredictions, and points below it represent overpredictions. The model does not anticipate many unusually high- or low-shot games. Because it predicts expected shot totals, its predictions do not need to span the full range of observed outcomes.

## Distribution of Prediction Errors

I created a histogram of errors, calculated as actual shots minus predicted shots. Negative values indicate overprediction, while positive values indicate underprediction.

The errors are roughly centered around zero. The mean error is approximately **+0.06 shots**, indicating little overall bias. However, the mean absolute error (MAE) is **5.057 shots**, meaning predictions differ from actual totals by about five shots on average. These measures describe different things: positive and negative errors can cancel in the mean error, but not in MAE.

## Model Performance Comparison

I compared a baseline that predicts each team's prior average shots with Poisson regression and XGBoost. All three methods were evaluated on the same eligible games. Lower MAE indicates better prediction accuracy.

| Model | 2022–23 validation MAE | 2023–24 evaluation MAE |
| --- | ---: | ---: |
| Prior-average baseline | 5.583 | 5.274 |
| Poisson regression | 5.303 | 5.057 |
| XGBoost | 5.364 | 5.091 |

For validation, models were fitted on 2021–22. For final evaluation, they were refitted on 2021–22 and 2022–23 combined, with settings held fixed.

Poisson regression reduced evaluation MAE by approximately **4.1%** relative to the baseline. Its advantage over XGBoost was only **0.034 shots per game**, so their predictive performance was very similar. I preferred Poisson regression because it was easier to interpret and had slightly lower validation error. These small differences do not establish statistical significance.

## Team-Level Insights

I also compared errors by team to determine whether the low overall bias concealed differences between teams. The final notebook includes a table of team-level mean error, MAE, and improvement over the baseline.

- **Washington had the lowest Poisson MAE**, at approximately 4.016 shots, even though the model overpredicted its shots by about 1.538 on average.
- **The Kings and Blues had nearly zero mean error**, but their MAEs were 5.461 and 5.138, respectively. Their errors balanced out without being especially small.
- **Poisson improved on the baseline for 26 of 32 teams.** Buffalo had the largest improvement, approximately 0.529 shots per game.
- **Carolina's MAE decreased from 5.427 to 5.058**, an improvement of approximately 6.8%.
- **Nashville had the largest decline**, with Poisson MAE approximately 0.323 shots higher than the baseline.

These results suggest that the model's modest benefit was spread across most teams, but it did not improve predictions for every team. Team rankings describe this evaluation season and may change in other seasons.

## Main Takeaway and Limitations

Prior shooting averages, the opponent's prior shots-allowed average, and home/away status provided a modest improvement over using the team's prior average alone. The model showed little overall bias but substantial uncertainty for individual games.

The evaluation covers one regular season that had already been explored during the project, so it is not a completely untouched test. Games without the required prior history were excluded. Shot totals include overtime when played, and the predictors do not capture every factor affecting shots, such as lineup changes or game-specific circumstances. Another untouched season would provide a stronger check of whether these findings generalize.
