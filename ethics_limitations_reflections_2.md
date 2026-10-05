**Ethics, Limitations, and Reflection**

This dataset has several limitations. It does not capture factors that could impact shots, such as player injuries removing key players thus creating lineup changes, the amount of rest between games(back-to-back vs multiple days), or puck-possession time, in the offensive and defensive zones. Lastly, games that include overtime also provide more time to generate shots, which the model does not explicitly account for.

The analysis uses three regular seasons and excludes games without sufficient prior history. This limits how well the findings apply to season-opening games or playoffs. Also, historical averages summarize previous performance but do not fully explain what happened during a particular game to create the average. 

The data consists of publicly available team statistics. If I had more time, I would include additional seasons and investigate predictors such as rest days, injuries, and expected goals. This project taught me that a more complex model does not automatically perform better; Poisson regression performed similarly to XGBoost while being easier to interpret.
