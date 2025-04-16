# Data Definition
## 6.1 The ISO SQL Data Types
2025年4月16日

|datatype|Declarations||||
|---|---|---|---|---|
|boolean|BOOLEAN|
|character|CHAR|VARCHAR|
|bit|BIT|BIT VARYING|
exact numeric|NUMERIC|DECIMAL|INTEGER|SAMLLINT|
approximate numeric|FLOAT|REAL|DOUBLE PRECISION
datatime|DATA|TIME|TIMESTAMP
interval|INTERVAL|
large objects|CHARATER LARGE OBJECT|BINARY LARGE OBJECT

## 6.2 Integrity Enhancement Feature

### 6.2.1 Required Data
```
position VARCHAR(10) NOT NULL
```

### 6.2.2 Domain Constraints
```
sex CHAR NOT NULL CHECK(sex IN ('M','F'))
```

```
CREATE DOMAIN DomainName [AS] datatype
[DEFAULT defaultOption]
[CHECK(searchCondition)]
then
Sex SexType NOT NULL
```

能创建就能删除
```
CREATE DOMAIN BranchNo AS CHAR(4)
CHECK(VALUE IN (SELECT branchNo FROM Branch));

DROP DOMAIN DomainName
```

级联删除后就变成基本数据类型（AS后面的）

### 6.2.3 ENtity Intergrity
```
PRIMARY KEY(staffNo)
```
一个表只能定义一次主键
如果你不定义，他会隐式创建一列行id
候选键
```
UNIQUE(telNo)
```

### 6.2.4 Referential Integrity
```
FOREIGNKEY (branchNo) REFERENCES BRANCH.xxx
FOREIGNKEY (branchNO) REFERENCES Branch 则同名
```
一般参照主键，也可以参照候选键

referential action 参照动作
ON UPDATE and ON DELETE:
-CASCADE 级联 你删我也删
-SET NULL 设空 你删了我为空 外键可以为空
-SET DEFAULT 默认 你删了我变成我的默认值 
-NO ACTION 驳回 不让你删

如果毕业了就要删卡号，但是食堂不允许
卡  ： 卡号
明细：卡号 ID 金额
    |
    |
    ↓
    导出来，放到另一个库，OLAP

那就取消参照，不过后面的人可能会发现卡号对不上
OLTP:联机事务处理 Online 增删改 
OLAP:分析 查
```
FOREIGN KEY(staffNo) REFERENCES Staff ON DELETE SET NULL
```

### 6.2.5 Enterprise Constraints
CHECK/UNIQUE
example:
```
CREATE ASSERTION
    StaffNotHandlingTooMuch
        CHECK(NOT EXISTS(SELECT staffNo
                         FROM PropertyForRent
                         GROUP BY staffNo
                         HAVING COUNT(*)>100))
```
如果违反就驳回

创建断言就会对N个表进行检查
能创建断言就能DROP

## 6.3 Data Definition
```
CREATE SCHEMA          DROP SCHEMA
CREATE/ALTER DOMAIN    DROP DOMAIN
CREATE/ALTER TABLE     DROP TABLE
CREATE VIEW            DROP VIEW
```
为何VIEW没有ALTER，因为你改变的话就是删掉原来的创建新的，没有意义

Many DBMSs also provide:
```
CREATE INDEX            DROP INDEX
```

### 6.3.1 Creating a Database
```
CREATE SCHEMA [NAME|
        AUTHORIZATION Creatorld]
```

### 6.3.2 Creating a Table
![Creating a Table](https://github.com/sujh2004/Notes/blob/main/src/6.3.2Creating%20a%20Table.png)



### 6.3.3 Changing a Table Definition
Add a new column to a table
Drop a colmn from a table
Add a new table constraint
Drop a table constraint
Set a default for a column
Drop a default for a column