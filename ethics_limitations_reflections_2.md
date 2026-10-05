**Ethics, Limitations, and Reflection**

This dataset has several limitations. It does not capture factors such as player injuries, lineup changes, rest between games, or puck-possession time. These factors could influence shot totals. Games that include overtime also provide more time to generate shots, which the model does not explicitly account for.

The analysis uses three regular seasons and excludes games without sufficient prior history. This limits how well the findings apply to season-opening games or playoffs. Historical averages summarize previous performance but do not fully explain what happened during a particular game. Additionally, the evaluation season had already been explored earlier in the project, so it was not a completely untouched test.

The data consists of publicly available team statistics. If I had more time, I would include additional seasons and investigate predictors such as rest days, injuries, and expected goals. This project taught me that a more complex model does not automatically perform better: Poisson regression performed similarly to XGBoost while being easier to interpret.
