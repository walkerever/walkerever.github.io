a few command line tools to share. 

----

## py-xdb
generic database client in python.  Borrow the ability to talk to databases with SQLAlchemy.  
in the past I wrote py-dbx which is a JDBC client -- in rather long time in my working environment as DBA in big firms, it's extremely hard to introduced new software packages into the database servers, so was forced to use very basic perl/python to deal with everything -- trust me, it's very hard.  Even an robust CSV parser is not easy, actually rather hard to allow all kinds of special cases.

![xdb show](/assets/images/xdb.gif)
![xdb show](/assets/images/xdb2.gif)

----

## QIC
[qic](https://walkerever.github.io/qic)

JSON/YAML/XML comand line query tool with interactive mode.

![qic show](/assets/images/qic.show.gif)

By design, it tries to keep simple but powerful.  You can chain multiple QIC call together which is much easier than composing very complicated queries in a single expression.  

----

## mysql-xml-formatter
applying a formatter to the "mysql --xml" output, make it eaiser to read and operate in command line. 

a.  wrap and cutwrap options. \
b.  column filter with -I/-E.   -E to exlude columns and -I to include columns.  

![mysql-xml-formatter show](/assets/images/mysql-xml-formatter.gif)


-----


## mysql-replication-display
like pt-slave-find but do more.  allow detection of stopped replicas.
![mysql-replication-display](/assets/images/mysql_repl_display.gif)
-----


## XTABLE
[xtable](https://walkerever.github.io/xtable)
print console tables. xtable serves as both a class and a command line tool.
![xtable show](/assets/images/xtable.gif)

----
## csv-join
join CSV files in SQL. by default use sqlite3 in memory. can be configured to use any RDBMS such as postgresql, mysql, db2, etc.

![csv-join show](/assets/images/csvjoin.gif)

----

## py-DBX
[py-dbx](https://walkerever.github.io/py-dbx)
make JDBC calls from command line. It maintains server connection across calls and user doesn't need to connect each time.  One purpose of this tool is to make JDBC result directly open to unix utitlies.  

it also supports plugin. A plugin is a set of queries, you can name them then DBX will run it when you name the alias.
![dbx show](/assets/images/dbx.gif)
----

----

## ltexpect
make expect easily available to comman line
![ltexpect show](/assets/images/ltexpect.gif)


## novels
a crawler which downloads Chinese online novels:)  

[document coming...]


----
## json-to-html
[json2html](https://walkerever.github.io/json2html)
convert JSON to HTML.

support collapse/expand, rows sampling.
