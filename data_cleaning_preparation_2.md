**Data Cleaning and Preparation**

The first step was to check for missing values in essential columns, duplicate team-game records, and whether each game contained exactly two team observations. I also verified that each team’s shots allowed matched its opponent’s shots on goal.

Next, I renamed the relevant columns, converted game dates to a datetime format, and sorted the data chronologically within each team and season. I converted `homeRoad` into `is_home`, coded as 1 for home and 0 for away.

I then calculated each team’s prior average shots and prior average shots allowed using only earlier games in the same season. I matched each team with its opponent using the game ID to attach the opponent’s prior average shots allowed. I also excluded the current game from these averages to try and prevent information leakage.

Lastly, I removed observations without the prior history needed for the predictors. I used 2021–22 for fitting and 2022–23 for validation. After fixing the model settings, I combined those two seasons for final training and evaluated the models on the 2023–24 regular season.
