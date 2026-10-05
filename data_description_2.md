# Data description - Project 2
The key variables are shots_on_goal, prior_avg_shots, opponent_prior_avg_shots_against, shots_against, and homeRoad.
### Conceptualization and Operationalization of variables
The primary dependent variable in this project is shots_on_goal. 
| Variable | Conceptual Definition | Operational Definition |
|---|---|---|
| `shots_on_goal` | A team’s shots that score or would enter the net if not saved | The team’s recorded shots on goal in the game, including overtime when played |
| `prior_avg_shots` | The team’s historical tendency to generate shots on goal | The mean of the team’s shots on goal in all earlier games of the same season, excluding the current game |
| `opponent_prior_avg_shots_against` | The opponent’s historical tendency to allow shots on goal | The mean shots allowed by the opponent in all earlier games of the same season, excluding the current game |
| `shots_against` | The number of shots on goal a team allows | The opposing team’s recorded shots on goal in that game |
| `homeRoad` | Whether the team is playing at home or away | The NHL API’s home/away designation: `"H"` for home and `"R"` for road |

The `shots_against` variable is used to construct the historical defensive averages. It is not meant to be for the same game, because its value is unknown before that game is played.

For modeling, `homeRoad` is converted into `is_home`, coded as **1 for home and 0 for away**. All historical averages are reset at the start of each season and use only information available before the game being predicted.
