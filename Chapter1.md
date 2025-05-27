2025年4月28日 8:00
### 1.2.3 Limitations of File-Based Approach
- Separation and isolation data
- Duplication of data
- Data dependence
- Incompatibility of files
- Fixed queries/proliferation of application program

### 1.3.1 The Database
Database: A shared collection of logically related data, and a description of this data, designed to meet the information needs of an organization. 
数据库：逻辑相关数据的共享集合，以及这些数据的描述，旨在满足组织的信息需求

DBMS: A software system that enables users to define, create, maintain, and control access to the database.
DBMS：一种软件系统，使用户能够定义、创建、维护和控制对数据库的访问

DDL:定义数据类型和结构以及约束
DML:插入更新删除和检索从数据库中

Controlled access to database: Security, integrity, concurrency control, recovery control, user-accessible catalog. 
对数据库的受控访问：安全性、完整性、并发控制、恢复控制、用户可访问目录

### 1.3.3 Componens of the DBMS Environment
Five major components in the DBMS environment: hardware, software, data, procedures, and people.
硬件，软件，数据，规程，人

## 1.4 Roles in the Database Environment
DA, DBA, detabase designers, application developers, and the end-users.

### 1.4.1 Data and Database Administrators
The Data Administrator (DA) is responsible for the management of the data resource including database planning, development and maintenance of standards, policies and procedures, and conceptual/logical database design
数据管理员(DA)负责数据资源的管理，包括数据库规划、标准、政策和程序的开发和维护，以及概念性逻辑数据库设计

The Database Administrator (DBA) is responsible for the physical realization of the database, including physical database design and implementation, security and integrity control, maintenance of the operational system, and ensuring satisfactory performance of application for users
数据库管理员（DBA）负责数据库的物理实现，包括物理数据库设计和实现，安全性和完整性控制，对操作系统的维护以及确保用户应用程序的满意性能

## 1.6 Advantages and Disadvantages of DBMSs
- Advantages:
    - control of data redundancy 可控的数据冗余
    - data consistency 数据一致性
    - Sharing of data 数据共享
    - Improved data integrity 提升数据完整性
    - Improved security 提升了安全性

- Disadvantages:
    - Complexity 复杂
    - Cost of DBMSs 花费更多
    - Reduced performance 减少了性能
    - Higher impact of a failure 如果出错，损失更大
    