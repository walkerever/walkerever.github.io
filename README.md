a few command line tools to share. 

I'm more used to work with CLI than UI. that's why for any product/platform introduced I always research the CLI and API availability which is the most automation friendly.

The idea behind these tools is, I used to work with multiple DBMS systems such as db2, sybase and recently more of mysql, postgresql  -- for CLI part, I want better display of table data.  and since for automation I'm dealing with more and more REST APIs and many of them are naturely "table" data like JSON list of list or list of dicts.   So I started to make some console libraries. firstly in bash, then another version in perl, until recently moved to python and opensourced as xtable.   Then I added the support to JSON/YAML/CSV and even XML and Markdown. 

The tools like py-xdb is convinient for me.  technically it's more of a integration project with SQLAlchemy database interface, xtable as console interface, etc. 

next plan is to integrate some nosql such as mongodb. 

btw, py-xdb allow users to define their own plugins  --- I used to keep all kind of queries then when something happens I can simple copy/paste  --- now, just add them into the default .dbx.dbs.json config file and just use the alias.   I put a simple example as "\d" as example.  Bad part of this, be careful, after some months, or longer, you may get lost and cannot remind which system tables to query(they are there, there, but what's the names???) when asked by somebody who's not using the same environment -- hmm, your interviewer? he may think you don't really know them!   I found this is not rare:)  and, after a few years not working as a DBA, I even found myself hard to concisely describe some concepts and from time to time may mix isolation levels of multiple DBMS's --- OK, I just want to shout, even DBA sense, and many skills are really portable, but definitely not for interviews:)  

Another idea behind py-xdb is that I do love the db2 command line interface.  DB2 does have interactive mode within DB2 promot, but DB2 guys are more used to run each query as a separeate *nix command and always feel free to use all *nix utilities.  This is partly why I like the CSV output -- easy to feed into awk.  I implemented a server process which keep the shared connection to avoid wasting from too many short connections in py-dbx which is python+jdbc version py-xdb.  I may migrate this to py-xdb in future, only for now it has rather lower priority. 

When situation become complicated for awk or sed, JSON output is useful.  Like the idea behind powershell that treat input as a object.  QIC is created for this purpose. For many functions it can be treated as "yet another jq" but the basic idea is not the same at all.  QIC allows user to use python code to do more -- you can import modules, defining functions, processing the data in a way you like, say, you have all the ability Python gives you and the input is available to you as a single internal variable "_". 


----

## py-xdb
generic database client in python.  Borrow the ability to talk to databases with SQLAlchemy.  
in the past I wrote py-dbx which is a JDBC client -- it's intially built with perl and embeded Java from DBMS installations -- for rather long time in my working environment as DBA in big financial firms, it's extremely hard to introduce new software packages into the database servers, so was forced to use very basic perl/python to deal with everything -- trust me, it's very hard.  Even an robust CSV parser is not easy, actually rather hard to allow all kinds of special cases.

note, 
1. you need to install DBMS python server separately. eg. for postgres, it could be psycopg2, for mysql, it could be pymysql, etc.  SQLAlchemy handles this part.
2. it integrates the funcitons of csv-join.  To use default in memory sqlite3 database or any others specified by -d (sqlalchemy connection string, or if single word, treated as sqlite3 database file to be created/used.)
3. I did have a lite version without panda, but since panda is so popular so I still make it the public version.  it's only used for the querying from CSV files.  in some environment where there's no good panda distro, such as cygwin, I chose to install py-xdb with --no-deps. 
4. py-xdb has dependency on xtable. xtable has a command line interface as well and it's very useful. you can find a simple demo on this page as well.

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
the function has been integrated into py-xdb.

join CSV files in SQL. by default use sqlite3 in memory. can be configured to use any RDBMS such as postgresql, mysql, db2, etc.

![csv-join show](/assets/images/csvjoin.gif)

----

## py-DBX 
mostly replaced by py-xdb. only this is JDBC based than python native driver. 

this is the python version of poor DBA's database box when I was living with a environment I cannot install perl DBI or python drivers. the only thing can be used at that time is JAVA/JDBC or command line interfaces.

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
