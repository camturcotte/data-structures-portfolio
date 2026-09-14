## Data Cleaning and Preparation

# The first step I took in the data cleaning process was to check out all the variables and their data types using .info(). There was one column that was empty, S3, so it was dropped as stage 3 is the final stage where the end of the race happens.

# Then, I created a variable to add to the data that says which generation of car was used in each particular race. This was done through if and else statements and the year variable to assign the generations.

# Next, I created a separate dataframe for Logano so that he would be singled out. Then, I created 3 variables: year type to determine if a year was even or odd, dnf to quantify if he didn't finish a race, and position gain to calculate how many positions he gained/lost each race.

# Lastly, I filtered the data based on the variables and drivers that I wanted to examine.
