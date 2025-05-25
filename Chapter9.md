# Chapter9 Normalization
自底向上

## 9.1 Purpose
1NF 2NF 3NF Boyce-Codd NF(BCNF)
更高的要求会带来损失
不规范也就是说会存在冗余，不保证完整性，增删改可能会有故障

## 9.2 Data Redundancy and Update Anomalies
合成一张大表：
- 插入异常 例：插入一条分公司但没有员工
- 删除异常 例：删除SA9，就不存在B007了
- 修改异常 例：修改B003的地址，则对不上了

造成的原因：
数据的冗余

无损连接：join
依赖保存属性


|sname| cname| tname |cname
|-----|------|----|---
张三|DB|孙|4
李四|DB|时|4
    |OS

sname cname  join cname  tname
有损

有效：张三只有一种性别，2*2=4

Functional Dependency:
在R中取出来A，就能找到B的值，可能是属性组也可能是属性
example: staffNo-->position
         position !--> position

- 有一对一关系
- 一直持有
- 非平凡的

阿姆斯特朗公理：
- 自反
- 传递
- 增广

如果找到最小依赖集，那么通过阿姆斯特朗公理，就可以找到全部依赖集

先找到主键，再找到最小函数依赖集(但是不是唯一的) 再找到完备依赖集

## 9.5 1NF
UNF：有一个或多个重复元组
1NF: Indicates that if A and B are attributes of a relation, B is fully dependent on A if B is functionally dependent on A, but not on any proper subset of A

2NF：
谁不让我成为二范式，就把谁删掉，非主键对逐渐的部分依赖
找到之后，把右边的属性删掉

## 9.7 3NF
在二范式之后，删除传递

## 9.8 BCNF
每一个决定因素都是候选键

## 9.9 summary
如果进行设计数据库设计时，要规范化。有哪些数据项，先放在一个大表里面，要进行不断的分解，存在很多数据冗余，会带来广义的更新异常。。所以做分解，首先找到函数依赖(最小)可能不是唯一的，找到主键，看是不是满足二范式，非主键对主键满足完全函数依赖。
