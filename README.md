###### This repository will contain the code that benchmarks all the Julia Database Drivers / Wrappers , End-Users can utilize this code to compare the performance between various Database drivers available in Julia.

# USAGE

End-Users can provide input through command-line mode or they can directly invoke function ```DBPerf()``` and provide input as arguments.


#### Command-Line mode

```
$ julia DBPerf.jl <Database_Driver_1.jl> <Database_Driver_2.jl> ....... <Database_Driver_N.jl> <DBMS>
```
Wherein
* Database_Driver.jl can be one of the following: ODBC.jl, JDBC.jl, PostgreSQL.jl, MySQL.jl
* DBMS field is applicable only if you're using JDBC.jl, DBMS can be either one of the following: Oracle, MySQL

###### Example
```
DBPerf.jl ODBC.jl JDBC.jl Oracle
```
Above example will conduct a performance test on Database driver ODBC.jl and JDBC.jl, DBMS will be automatically selected for ODBC.jl based on the credentials provided in config.jl, whereas JDBC.jl will be tested against Oracle


#### Executing from Julia prompt 

```
julia> include("DBPerf.jl")
julia> DBPerf(<Database_Driver_1.jl>, <Database_Driver_2.jl>, ....... <Database_Driver_N.jl>, <DBMS>)
```
###### Example
```
DBPerf("ODBC.jl","JDBC.jl","Oracle")
```
Above example will conduct a performance test on Database driver ODBC.jl and JDBC.jl, DBMS will be automatically selected for ODBC.jl based on the credentials provided in config.jl, whereas JDBC.jl will be tested against Oracle

#### config.jl should contain all the credentials required for a DBMS connection

# TODO
1. Include MongoDB, HBase, SQLite and Spark SQL in the performance test.
2. Create a performance table that lists the performance results for all the Database drivers. 
3. Creating an automated script that pulls the latest code from all the database drivers to conduct a performance test and automatically update the performance table every week.
