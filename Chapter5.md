# Chapter 5 Data Manipulation
2025年4月24日 9:00
## 5.1 Introduction to SQL
### 5.1.1 Objectives of SQL
- database language should allow user to:
    1. create the database and relation structures
    2. perform insertion,modification,deletion of data reom relations.
    3. perform simple and complex queries

<br>

- must perform these tasks with minimal user effort and command structure/syntax must be easy to learn


<br>

- It must be portable

<br>

- SQL is a transform-oriented language with 2 major components:
    1. A DDL for defining database structure.
2   . A DML for retrieving and updating data.

<br>

- SQL是易学的：
    1. 它是非过程的
    2. 本质是自由格式的
    3. 命令结构由英文组成
    4. 可以由一系列用户使用

### 5.1.2 History of SQL

### 5.1.3 Importance of SQL
SQL has become part of application
architectures such as IBM’s Systems Application Architecture.

## 5.2 Writing SQL Commands
- SQL statement consists of reserved words and user-difined words. 
    1. Reserved words are a fixed part of SQL and must be spelt exactly as required and cannot be split across lines.
    2. User-defined words are made up by user and represent names of various database objects such as relations,columns,views.

<br>

- Most componets of an SQL statement are case insensitive.Letters can be typed in either upper or lower case

<br>

- More readable with indentation and lineation:
    1. Each clause should begin on a new line.
    2. Start of a clause should line up with start of
other clauses.
    3. If clause has several parts, should each
appear on a separate line and be indented
under start of clause.

## 5.3 Data Manipulation
### 5.3.1 Simple Queries

**SELECT**

- SELECT [DISTINCT|ALL]
    {*|[columnExpression[AS newName]][,...]}
    FROM TableName [alias][,...]
    [WHERE condition]
    [GROUP BY columnList] [HAVING condition]
    [ORDER BY columnList]

<br>

- The sequence of processing in a SELECT statement is：
    -FROM
    -WHERE
    -GROUP BY
    -HAVING
    -SELECT
    -ORDER BY

<br>

- Calculated fields
    SELECT staffNo，fName,lName,**salary/12 AS monthlySalary**
    FROM Staff;

<br>

- Use of :
    1. distinct
    2. Calculated fields as clause
    3. Where
    4. Compound comparison search condition
    5. Range search(BETWEEN / NOT BETWEEN)
    6. Set membership search (IN / NOT IN)
    7. Pattern match search (LIKE / NOT LIKE):% and _
    8. Null search(IS NULL / IS NOT NULL)

### 5.3.2 Sorting Results (ORDER BY)
- Single-column ordering:
    SELECT staffNo, fName, lName, salary
    FROM Staff
     ORDER BY salary DESC;

<br>

- Multiple column ordering
    SELECT propertyNo, type, rooms, rent
    FROM PropertyForRent
    ORDER BY type, rent DESC;

### 5.3.3 Using the SQL Aggregate Function
- COUNT
- SUM
- AVG
- MIN
- MAX


COUNT, MIN, and MAX apply to numeric and
non-numeric fields, but SUM and AVG may be
used on numeric fields only. 

Apart from COUNT(*), each function eliminates
nulls first and operates only on remaining nonnull values.

Aggregate functions can be used only in
SELECT list and in HAVING clause.

### 5.3.4 Grouping Results (GROUP BY)

Restricted Groupings(HAVING clause)

Column names in HAVING clause must also appear in the GROUP BY list or be contained
within an aggregate function

### 5.3.5 Subqueries
A subselect can be used in WHERE and
HAVING clauses of an outer SELECT,
where it is called a subquery or nested
query. 

Subselects may also appear in INSERT,
UPDATE, and DELETE statements.

By default, column names refer to table name in FROM clause of subquery. Can refer to a table in FROM using an alias. 

### 5.3.6 ANY and ALL
If subquery is empty, ALL returns true, ANY
returns false.

Example 5.22:

    SELECT staffNo, fName, lName, position, salary
    FROM Staff
     WHERE salary > SOME (SELECT salary
    FROM Staff
    WHERE branchNo = ‘B003’);

### 5.3.7 Multi-table Queries

If result columns come from more than one table must use a join.
如果查询结果中的列来自多余一个表，则必须使用连接

**简单连接**

    SELECT c.clientNo, fName, lName,propertyNo,comment
    FROM Client c, Viewing v
    WHERE c.clientNo = v.clientNo;
    

SQL provides alternative ways to specify joins:

    FROM Client c JOIN Viewing v ON c.clientNo = v.clientNo
    FROM Client JOIN Viewing USING clientNo
    FROM Client NATURAL JOIN Viewing 

**Left Outer Join** 
左边全要，右边没有就是NULL，右边多的就舍弃，只要与左边相对应的

    SELECT b.*, p.*
    FROM Branch1 b LEFT JOIN
    PropertyForRent1 p ON b.bCity = p.pCity;


**Right Outer Join**
**Full Outer Join**

### 5.3.8 exists and not exists
EXISTS and NOT EXISTS are for use only with
subqueries. Produce a simple true/false result. 

True if and only if there exists at least one row in result table returned by subquery

### 5.3.9 Combining Result Tables(union intersect except)

    (SELECT city FROM Branch WHERE city IS NOT NULL)
    UNION
    (SELECT cityFROM PropertyForRent
    WHERE city IS NOT NULL); 

    OR

    (SELECT * FROM Branch WHERE city IS NOT NULL)
    UNION CORRESPONDING BY city
        (SELECT * FROM PropertyForRent
        WHERE city IS NOT NULL);


### 5.3.10 Database Updates

**Insert**

    INSERT INTO TableName [ (columnList) ]
    VALUES (dataValueList)

**Update**

    UPDATE TableName
    SET columnName1 = dataValue1
    [, columnName2 = dataValue2...]
    [WHERE searchCondition] 


**Delete**
    
    DELETE FROM Viewing
    WHERE propertyNo = ‘PG4’;