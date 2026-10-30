# nba-rookie-longevity
In this project we build a dataset with information about nba rookies to build classifiers that will predict if the player will still be in the league after 5 years. Using different sets of features we will try to find which features are more determinant than others, as well as relations between features.

---

## STEP 1: Setting up the environment
First, we import the libraries:
* `Pandas`: Data manipulation and analysis of data.
* `ipthon-sql`: It will allow us to run SQL queries directly in jupyter notebook.
* `sqlite3`: Imports Python's built-in driver for interacting with SQLite databases.
* `prettytable`: Makes the SQL query results more structured so that they are easier to read.

Next, we set up the connection to the database.
* `%load_ext sql`: This will activate the SQL magic extension.
* `con = sqlite3.connect("player_statistics.db")` & `cur = con.cursor()`: Establishes a connection and creates a cursor object to execute SQL queries on the `player_statistics.db` database.
* `%sql sqlite:///player_statistics.db`: Connects the ipython-sql extension to the database.

---

## STEP 2: Building the dataset

We will build our dataset from three different datasets:
* `rookies_by_year`: This will be the main dataset. The final dataset will be constructed by adding new columns to this dataset. Includes statistics from 1538 NBA rookies from 1980 to 2016. More details about the statistics will be given later.
* `all_seasons`: It has stats about player per season. It will be used mainly to construct the column that will tell us if the player was successful or not.
* `team_stats`: It has information about the team, such as win percentage and other features.

We read the **csv** file using pandas, and then we transform the pandas dataframe into a SQL table. Then, we build our final dataset ``
`DATASET_ROOKIE_PREDICTION`.

---

## STEP 3: Training and testing classifiers

We will import some necessary libraries which will be given in more detail later. Then, we work with different subsets of features and try to come up with ideas to learn which statistics are more important. This comparative approach will help us uncover underlying relationships, among the different basketball statistics.

## STEP 4: Final conclusions
To wrap up, we will give a table comparing the accuracy of each classifier and present final conclusions.
