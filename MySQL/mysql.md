# 1. Introduction
## What is mySQL
###### my sql is **relational database management system** (RDBMS) developed by ORACLE that is baseed on structured query language (SQL).

## What is Database
###### A database is organized collection of structured data.

## what is DBMS 
###### Database Management System (DBMS) are software system which are used to store, retrive and manage data by runing queries on data.

### Types of DBMS ?
![Types of DBMS](https://github.com/user-attachments/assets/81db2917-b6c3-429c-b842-4907290e5ca0)
#### Relational And Non-Relational Databases

### List of SQL Databases 
- MySQL
- MariaDB
- Oraccle
- PostgreSQL
- MS_SQL

###### Databases are made of tables

# 2. How to Install MySQL
###### installation process i wouldn't write here!!!

### how to check database on your pc
```
show databases;
- output

```
### Database making command 
```
create database DBname;
```
###### ex
```
create database learnings;
```
###### will create a database named learnings
### how to use database 
```
use dBname;
```
# 3. Tables in MySQL
###### Database table is a collection of rows and columns that contains relational data. 
ex :- 
| Id | Name  | Email            | DOB        |
|----|-------|------------------|------------|
| 1  | Ramesh | ramesh@gmail.com | 10-01-1999 |
| 2  | John   | john@gmail.com   | 05-02-1997 |
| 3  | Reena  | reena@gmail.com  | 15-05-1997 |

### Categories of Datatypes
1. String
2. numerical
3. Date & Time

#### Create table syntext
```
Create Table table_name
(
    Column1 datatype,
    column2 datatype,
    column3 datatype,
    .....
),
```
#### <div align="center"> String Data Types </div>

1. CHAR(size) 0 to 255
2. VARCHAR(size) 0 to 65535
3. BINARY(size) 1
4. VARBINARY(size)

###### In SQL, BINARY and VARBINARY are data types used to store binary data (like images, files, or raw bytes). difference between them, including their size specifications:

1. BINARY(size)
###### Fixed-length binary string.

###### Always occupies the specified size in bytes, padding with zeros if the stored data is shorter.

###### Example:

###### sql
###### BINARY(10)  -- Always stores exactly 10 bytes.
###### If you store 0xABCD (2 bytes) in a BINARY(10), it will be padded to 0xABCD00000000000000.

2. VARBINARY(size)
###### Variable-length binary string.

###### Only uses as much space as needed (up to the specified size).

###### More space-efficient for shorter values.

###### Example:

###### sql
###### VARBINARY(255)  -- Can store up to 255 bytes, but only uses what's needed.
###### If you store 0xABCD (2 bytes) in a VARBINARY(10), it will occupy only 2 bytes.

###### Key Differences
| Feature               | `BINARY(size)`                          | `VARBINARY(size)`                      |
|-----------------------|----------------------------------------|----------------------------------------|
| **Storage Type**      | Fixed-length                           | Variable-length                       |
| **Padding**           | Pads with zeros to fill `size`         | No padding (uses only needed space)   |
| **Storage Efficiency**| Less efficient (always uses `size`)    | More efficient (adapts to data size)  |
| **Example Declaration**| `BINARY(10)`                          | `VARBINARY(255)`                      |
| **Stores `0xABCD` as** | `0xABCD00000000000000` (10 bytes)      | `0xABCD` (2 bytes)                    |
| **Use Case**          | Hashes, fixed-length IDs               | Files, blobs, variable-length data    |
| **Max Size**          | Depends on DB (e.g., MySQL: 65,535)    | Depends on DB (e.g., SQL Server: 8KB) |

### Size Limits
###### The size parameter defines the maximum number of bytes the column can hold.
###### Common max sizes:

###### MySQL: Up to 65,535 bytes (for VARBINARY).

###### SQL Server: Up to 8,000 bytes (or MAX for very large data).

###### PostgreSQL: Uses BYTEA (similar to VARBINARY) with no explicit size limit.
