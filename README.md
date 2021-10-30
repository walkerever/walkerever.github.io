some open source Python projects I owned.  all available through pip.

## csv-join
join CSV files in SQL. by default use sqlite3 in memory. can be configured to use any RDBMS such as postgresql, mysql, db2, etc.

[document coming...]


## QIC
[qic](https://walkerever.github.io/qic)

JSON/YAML/XML comand line query tool with interactive mode.

![qic show](/assets/images/qic.show.gif)

By design, it tries to keep simple but powerful.  You can chain multiple QIC call together which is much easier than composing very complicated queries in a single expression.  

----

## XTABLE
[xtable](https://walkerever.github.io/xtable)
print console tables. xtable serves as both a class and a command line tool.


----

## py-DBX
[py-dbx](https://walkerever.github.io/py-dbx)
make JDBC calls from command line. It maintains server connection across calls and user doesn't need to connect each time.  One purpose of this tool is to make JDBC result directly open to unix utitlies.  

it also supports plugin. A plugin is a set of queries, you can name them then DBX will run it when you name the alias.

----

## novels
a crawler which downloads Chinese online novels:)  

[document coming...]


----
## json-to-html
[json2html](https://walkerever.github.io/json2html)
convert JSON to HTML.

support collapse/expand, rows sampling.
