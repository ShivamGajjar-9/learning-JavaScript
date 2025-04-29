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

1. CHAR(size) 0 to 255   -characters
2. VARCHAR(size) 0 to 65535   -characters
3. BINARY(size)      -Bytes
4. VARBINARY(size)      -Bytes
5. TINYTEXT 255    -characters
6. TEXT(size) 65535      -bytes
7. MEDIUMTEXT 16,777,215 characters
8. LONGTEXT 4,294,967,295 characters
9. TINYBLOB 255 bytes
10. BLOB(size) 65,535 bytes
11. MEDIUMBLOB 16,777,215 bytes
12. LONGBLOB 4,294,967,295 bytees
13. ENUM(val1, val2, val3, ...) list up to 65535 values
14. SET(val1, val2, val3, ...) list up to 64 values

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


### <div align = "center"> Number Data Types </div>

1. **BIT(size)**   - Stores 1 to 64 bits (binary values).

2. **TINYINT(size)**    - Range: `-128` to `127` (signed) or `0` to `255` (unsigned).

3. **INT(size)**     - Range: `-2,147,483,648` to `2,147,483,647` (signed).

4. **INTEGER(size)**     - Alias for `INT(size)`.

5. **SMALLINT(size)**     - Range: `-32,768` to `32,767` (signed).

6. **MEDIUMINT(size)**    - Range: `-8,388,608` to `8,388,607` (signed).

7. **BIGINT(size)**    - Range: `-9,223,372,036,854,775,808` to `9,223,372,036,854,775,807` (signed).

8. **BOOL**     - Synonym for `TINYINT(1)` (stores `0` or `1`).

9. **BOOLEAN**     - Same as `BOOL` (`0` = false, `1` = true).

10. **FLOAT(p)**     - Floating-point number with precision `p`.

11. **DOUBLE(size, d)**     - Double-precision float (e.g., `255.568`).    - `size`: Total digits, `d`: Decimal places.

12. **DECIMAL(size, d)**      - Fixed-point number (e.g., `size=60`, `d=30`).

13. **DEC(size, d)**     - Alias for `DECIMAL(size, d)`.
