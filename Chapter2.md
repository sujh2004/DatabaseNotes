# Chapter2 Database Environment
## 2.1 The Three-level ANSI-SPARC Architecture(三级结构)

目的(objective):将每个用户的数据库视图与数据库的物理呈现方式分开
如此分离的原因：
- 所有用户都应该能访问相同的数据
- 用户的视图不受其他视图更改的影响
- 用户不需要了解数据库的物理存储细节
- DBA应该能够更改数据库的存储结构，而不会影响用户的视图
- 数据库的内部结构应该不受存储物理方面更改的影响
- DBA应该能够更改数据库的概念结构，而不会影响所有用户

**外部层**
External level:The user's view of database.This level describes that part of the database that is relevant to each user.
- The external level consists of a number of different views of the database
- Describes that part of database that is relevant to a particular user.

外部层：数据库的用户视图。这一层描述与每一个用户相关的数据库部分。
- 外部层包括由一些不同的数据库视图组成
- 描述了与特定用户相关的数据库部分

**概念层**
Conceptual level:The community view of the database/this level describes what data is stored in the database and relationships among the data
概念层：数据库的整体视图。这一层描述了哪些数据被存储在数据库中，以及这些数据之间的关系。

This level contains the logical structure of the entire database as seen by the DBA.The conceptual level represents:
- All entities,their attributes,and their relationships;
- The constraints on the data;
- Semantic information about the data;
- Security and integrity information;

此级别包含DBA所看到的整个数据库的逻辑结构，概念层描述:
- 所有的实体、实体的属性和实体间的联系。
- 数据的约束
- 数据的语义信息
- 安全性和完整性信息

**内部层**
Internal level: The physical representation of the database on computer.This level describes how the data is store in the database.
内部层：数据库在计算机上的物理表示。这一层描述了数据是如何存储在数据库中的。

The internal level covers the data structures and file
organizations used to storage devices. It concerned
with such things as:
- Storage space allocation for data and indexes;
- Record descriptions for storage;
- Record placement;
- Data compression and data encryption techniques;

内部层涵盖存储设备使用的数据结构和文件组织。它涉及以下内容：
- 数据和索引的存储空间分配
- 用于存储的记录描述
- 记录防置
- 数据压缩和数据加密技术

The overall description of the database is called the database schema.There are three different types of schema in the database:external schema,conceptual schema,internal schema.
数据库的整体描述叫做数据库模式。在数据库中有三种不同的模式：外层模式，概念模式，内部模式

DBMS负责这三类模式之间的映射。每一个外部模式通过外部层到概念层的映射与概念模式相联系。概念模式通过概念层到内部层的映射与内部模式相联系。