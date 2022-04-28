# How to Use SQL in Pandas
When you compare the structure of a Pandas DataFrame to the structure of a table in a SQL Database, you'll notice that they're pretty similar. They're both made up of data points, or values, with a unique index for each row and a unique name for each column. As a result, SQL enables you to quickly access the specific data you require for whichever project you're working on. However, Pandas may be used to create very similar queries! In this project article, I'll show you how to accomplish precisely that, as well as the libraries you'll need to get started.

## Built With
The following are details of the programming language and libraries used in building this project:<br>
- [**pandas**](https://pandas.pydata.org/)<br>
- [**NumPy**](https://numpy.org/)<br>
- [**seaborn**](https://seaborn.pydata.org/)<br>
- [**matplotlib**](https://matplotlib.org/)<br>
- [**pandasql**](https://www.analyticsvidhya.com/blog/2021/07/pandasql-best-way-to-run-sql-queries-and-codes-in-jupyter-notebook-using-python/)<br>

## About `pandasql` Library
The ability to use SQL and/or all of its variants is well known, and it is one of the most in-demand employment skills for data scientists, even during a pandemic. Fortunately, there is now a Python package called pandasql that allows you to retrieve data from Pandas DataFrames using SQL-style syntax! This is useful for both aspiring data scientists who wish to improve their SQL skills and seasoned data scientists who are familiar with SQL-style syntax. Simply type!pip install: to install it on your PC.
```
!pip install pandasql
```
<br>

Then, to import it into your notebook, you want to import a sqldf object from pandasql:
```
from pandasql import sqldf
```
```
import pandasql
```
<br>

For df1 and df2 datasets, we'll utilize the Join function in conjunction with pd.merge.
```
query = """
        SELECT
            a.userId,
            a.rating,
            b.movieId,
            b.title
        FROM
            df_ratings AS a
        LEFT JOIN
            df_movies AS b ON a.movieId = b.movieId
        """

result = pandasql.sqldf(query)
result
```
![image](https://user-images.githubusercontent.com/73176284/165699060-922238df-5fb1-48c3-863e-e8e996310278.png) <br>

## Additional Note
There are various supporting files and articles in this project that you can use as reference material. Below is a list of resources that you can use.
- [**SQL Cheat Sheet Documentation**](https://github.com/yandaaw/sql-to-pandas/blob/main/SQL_Cheat_Sheet.ipynb)
- [**Exploratory Data Analysis using SQL-Pandas part 1**](https://github.com/yandaaw/sql-to-pandas/blob/main/SQL_EDA_CASE01.ipynb)
- [**Exploratory Data Analysis using SQL-Pandas part 2**](https://github.com/yandaaw/sql-to-pandas/blob/main/SQL_EDA_CASE02.ipynb)
- [**SQL ROW_NUMBER**](https://www.sqltutorial.org/sql-window-functions/sql-row_number/)
