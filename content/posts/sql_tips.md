---
title: "Sql tips for your everyday world"
date: 2021-05-31T15:02:07-04:00
draft: false
---
### Ecto → Raw SQL
Have you ever wanted to chuck an ecto query into your sql tool of choice? Here's a handy snippet that will output your ecto query into a state that you can directly copy/paste to sql.

```elixir
:all
|> Ecto.Adapters.SQL.to_sql(Repo, <insert ecto query here>)
|> Tuple.to_list()
|> Enum.at(0)
|> String.replace("\"", "")
|> Kernel.<>(";")
|> IO.inspect(label: "QUERY HERE")
```

Example output:
```
QUERY HERE: "SELECT l2.id, d4.geo_point, d4.zip_code FROM ….. WHERE (d4.zip_code != l2.zip_code);"
```

### EXPLAIN my SQL

Have you ever wondered how efficient your query is? Wonder no more! [Postgres provides a tool to see the execution plan of your query](https://www.postgresql.org/docs/9.1/sql-explain.html). By prefacing your query with EXPLAIN ANALYZE you will be provided a LOT of information, but one of the most important data points is the execution cost, which the docs describe as “a guess at how long it will take to run the statement (measured in units of disk page fetches)”.  However, the `ANALYZE` option allows for the query to actually be executed, and the time of execution returned. Additionally the number of “loops” that Postgres makes over the data is given. For more information about EXPLAIN, here’s a great blog post from [ThoughtBot](https://thoughtbot.com/blog/reading-an-explain-analyze-query-plan).
