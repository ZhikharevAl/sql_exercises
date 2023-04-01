# This project uses the [SQLite3](https://docs.python.org/3/library/sqlite3.html) database and demonstrates the use of SELECT, GROUP BY, subqueries, and JOIN commands to work with data in the database.
## Adding data to SQLite database:
1. Create a SQLite connection object using the sqlite3.connect() function. For example:
```sh
import sqlite3
con = sqlite3.connect('db')
```
2. Import the pandas library and load data from a CSV file into a DataFrame object. For example:
```sh
import pandas as pd
df = pd.read_csv('database/german_credit_augmented.csv')
```
3. Use the to_sql() function to add data to a table in the SQLite database. For example:
```sh
df.to_sql('german_credit', con, index=False, if_exists='replace')
```
#### The to_sql() function takes the following arguments:

 - name: the name of the table in the SQLite database.
 - con: the SQLite connection object created using sqlite3.connect().
 - index: a boolean value indicating whether to include the DataFrame index in the database (default is True).
 - if_exists: a string indicating what to do if the table already exists in the database. If if_exists='replace', the old table will be deleted and replaced with the new one. If if_exists='append', the data will be added to the existing table. By default, if_exists='fail', which means an error will be raised if the table already exists in the database.

#### After executing this command, the data from the DataFrame df will be inserted into the german_credit table in the SQLite database, and you can use SQL queries to extract them from the database. For example, to select the first 10 rows from the german_credit table, use the following code:
```sh
import pandas as pd
import sqlite3
con = sqlite3.connect('db')
df = pd.read_sql_query('SELECT * FROM german_credit LIMIT 10;', con)
```
This will extract the first 10 rows from the german_credit table into the DataFrame object df.

You can add any additional notes or instructions that you think are necessary. It is also important to ensure that your instructions are clear and easy to understand for the user.