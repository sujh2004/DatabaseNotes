# Chapter8 Entity-Relationship Modeling

ER:
- 实体(E)：实例 强/弱(是否依赖)
- 联系(R)：实例 (二、三、多)元 约束(联系方式)
- 属性&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;：单值/多值 简单/复合 导出

|
|
|
↓
relation：
1. 实体->表
2. 1-1，1-n联系不单独建表，放在子实体的表中
3. n-m联系单独建表，放两个实体的主键  

chen氏 UML
Concepts of the ER Model
- Entity types
- Relationship types
- Attributes

矩形就是实体
线就是联系
菱形就是联系 不是两个实体之间的联系，是三个
虚线是联系的属性
s &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;c
&nbsp;-------------
  （score）

实体类型：从一个实例里面抽象出来的类型
实体实例：一个单独的实体就是实体实例

物理存在
概念存在

联系类型：实体之间有意义的关联
联系实例：唯一的可标识的一次关联就是联系

## 8.2 Relationships Types
Degree of a Relationship Type
Supervisor ---> Supervisee  参照到自身

实体和实体有联系，不一定每个实例和每个实例都有联系

## 8.3 Attributes
Attribute:A property of an entitiy or a relationship type
Attribute Domain:The Set of allowable values for one or more attribues

Simple Attribute:
Composite Attribute

Single-valued Attribute
Multi-valued Attribute

Derived attribute 导出属性

主键外键复合键

强实体:不依赖
弱实体
例如：爱好是依附于学生的，若学生实体不存在，则爱好实体不存在

## 8.6 结构约束
one to one
one to many
many to many

Cardinality：基数 （一对一 一对多）
Participation：参与性 看最小的数字， 0 or 1 如果是0：可选参与 指的是对方 如果是1：强制参与

## 8.7 Transform ER into relationship
参考最上面
强实体 弱实体
一对一 一对多 多对多联系
一对一 两边都强制 可以放在一张表 也可以两张表 一般采用主外键
一对一 一边强制 则建议放在两张表，否则会有很多null 
一对一 两边都可选 少部分员工开车 大部分车都被开 选车做子 车那个表会有staffNo为空
  
复杂联系 单独成表 
多值属性

![Transform ER into relationhsip]()













