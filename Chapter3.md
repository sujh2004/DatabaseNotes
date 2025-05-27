### 4.2.3 Database Relation
Relation schema: A named relation defined by a set of attribute and domain anme pairs
关系模式：用一组属性和域名对定义的具名的关系

Relational database schema:A set of relation schemas, each with a distinct name
关系数据库模式：关系模式的集合，集合中的每个关系都应有不同的名字

### 4.2.4 Properties of Relations
**关系的性质：**
- 每个关系都有一个名字，同一个关系模式中关系的名字不能相同
- 关系中的单元格内的值应为原子值
- 每一个属性都有不同的名字
- 每一个属性下的值都应该属于同一个域
- 各元组不能相同
- 属性的顺序并不重要
- 理论上来说，元组的顺序也并不重要

### 4.2.5 Relational keys
Superkey
Candidate Key
Primary Key
Alternate Keys
Foreign Key

## 4.3 Relational Integrity
2025年4月28日 13:00
### 4.3.2 Entity Integrity
**Entity Integrity:** In a base relation, no attribute of a primary key can be null
实体完整性：在基本关系中，主关键字的属性不能为空。

**Referential Integrity:** If foreign key exists in a relation. either foreign key value must match a candidate key value of some tuple in its home relation or foreign key value must be wholly null.
引用完整性：如果在关系中存在某个外部关键字，则它的值或与主关系中某个元组的候选关键字取值相同，或者全为空

**Enterprise Constraints:** Additional rules specified by the users or database administrators of a database
一般性约束：由数据库用户或数据库管理员所指定的附加规则，他约束企业的某些方面

## 4.4 Views

### 4.4.1 Terminology
**Base Relation:** A named relation corresponding to an entity in conceptual schema,whose tuples are physically stored in database.
基本关系：与概念模式中一个实体相对应的具名关系，他的元组都存储在数据库的物理结构中

**View:** The dynamic result of one or more relational operations operating on base relations to produce another relation. A view is a virtual relation that does not necessarily exist in the database but can be produced upon request by a particular user, at the time of request.
视图：对一个或多个基本关系进行关系操作得到的动态结果。视图是一个无需存在于数据库当中,但却可以根据某个特定用戶需要在必要时再生成的虚关系。