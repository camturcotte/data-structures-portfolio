# Data Description
## The key variables are finish, rating, position gain, win rate, DNF rate, and year type.
### Conceptualization and Operationalization of Variables

The primary independent variable in this project is season type. Season type for this context represents whether a NASCAR season is even-numbered or odd-numbered. It is used by labeling seasons divisible by two as “Even” and all other seasons as “Odd.”

The dependent variables represent different aspects of driver performance:

| Variable | Conceptual Definition | Operational Definition |

| Finishing position | How well a driver finished in an individual race | The `Finish` column, where a lower number represents a better result |

| Driver rating | A driver’s overall performance during a race | The `Rating` variable, where higher values represent stronger performance |

| Position gain | How a driver’s position changed from the start to the end of a race | Calculated as `Start - Finish`; positive values indicate positions gained |

| Win rate | The proportion of races won by a driver | Calculated as total wins divided by total races entered |

| DNF rate | The proportion of races a driver did not finish | Calculated as total DNFs divided by total races entered |

The `Win` variable was used to identify whether a driver won each individual race. The `DNF` variable was created from the `Status` column and was coded as 1 when the status was not “running” and 0 when the status was “running.”

The  `Driver` variable is used to identify each driver. `Season` identifies the year of each race, while `Length` records the track length in miles per lap and is used here to examine whether performance differs across tracks of different lengths.
