# Testen einer JDBC connection
```
select * from
(
import from jdbc at JDBC_ORACLE
statement 'select ''Connection works'' from dual'
); 
```
# Testen einer Oracle Connection
```
select * from
(
import from ora at ORA_CONNECT
statement 'select ''Connection works'' from dual'
); 
```
Referenzen:
https://docs.exasol.com/db/latest/sql/create_connection.htm?Highlight=connection

https://docs.exasol.com/db/latest/sql/alter_connection.htm

https://docs.exasol.com/db/6.2/loading_data/connect_sources/oracle.htm