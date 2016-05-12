#Database Index Search Accelerator

`ingredients.sql` contains a list of 100,000 recipe ingredients. My task was to query the database, and return statistics on it. I did this exercise to practice using the `psql` console, and to utilize a DB index to speed up my SQL queries.

###Database Setup Instructions

**Run the Following Commands:**
```no-highlight
$ createdb ingredients
$ psql ingredients < ingredients.sql
```

###Queries
`queries.sql` contains queries that do the following:
* Find all rows that have an ingredient `name` of `Brussels sprouts`.
* Calculate the total count of rows of ingredients with a `name` of `Brussels sprouts`.
* Find all `Brussels sprouts` ingredients having a unit type of `gallon(s)`.
* Find all rows that have a unit type of `gallon(s)`, a name of `Brussels sprouts` or has the letter `j` in it.

###Explain Analyze Results
Without DB indices it took about **81.307ms**.
![DB_Accelerator_No_Index](http://gdurl.com/3yq6)

After indexing `ingredients(name)` and `ingredients(unit)`, it took about **2.623ms**.
![DB_Accelerator_With_Index](http://gdurl.com/f-ZD)

###Conclusion
Indexing this SQL database made my query run about **31 times** faster!
