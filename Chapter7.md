# Chapter 7.Database Planning,Design and Administration
2025年5月7日 8:00
可能考生命周期包括哪些阶段(简答题)
可能考粉色区域:概念设计
              逻辑设计
              物理设计
第七章 数据库规划，设计和管理

软件危机    

结构化的软件开发方法--软件开发生命周期

## 7.1 The Information system
信息系统：在组织结构内用于收集、管理、控制和分发信息的一种资源

IS 包括 DA

## 7.2 The Database Application Lifecycle
数据库应用生命周期
![数据库应用生命周期](https://github.com/sujh2004/DatabaseNotes/blob/main/src/7.2.1.png?raw=true)

 数据库规划：需求(大体)
 
 系统定义：边界 VIEW(视角)
 
 需求收集与分析：进一步需求(CREATE AND MAINTAIN、number of records)从功能 非功能需求(性能，安全)角度出发


|概念| 卡  &nbsp;终端(多对多)
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;↓
|逻辑| 卡  &nbsp;终端 明细(联系的属性而非两个主体的属性) 出表
|物理| 具体的语句 CREATE TABLE

多对多必须单独弄一个表
一对多可以通过主外键

逻辑的时候知道要用关系型DBMS，但不知道用哪个

## 7.6.3
Conceptual database design: The process of constructing a model of the information used in an enterprise,independent of all physical considerations
独立于

若找不到 没有需求则罢，有需求则调整ER(概念)


## 7.9 Prototyping(原型)
通常为实现最终系统所需要具备的所有特性和功能
快，不断迭代

## 7.10 Implementation
## 7.12 测试
## 7.13 运维
DBA

## 7.14 CASE Tools
ER符 UML
不用手搓

## 7.15 DA和DBA 

数据库设计：是一种管理活动，为了更高效的完成数据库生命周期中的操作
系统定义：确定范围边界和用户的主要视图
需求收集与分析：收集分析企业需要数据库系统支持的信息，并由此定义系统需求的过程。
数据库设计：为企业设计的数据库而生成的设计方案                                                                                                      
- 概念数据库设计：建立概念数据模型，与所有的物理实现无关
- 逻辑数据库设计：将概念模型的基础上建立逻辑数据模型。与其他的物理因素和具体的DBMS无关
- 物理数据库设计: 描述在辅存上实现数据库的过程。

DBMS选型：为数据库选择合适的的DBMS
应用程序设计：设计出用户页面和事务设计，描述了应用程序对数据库的使用和访问
建立原型系统：建立数据库系统的工作模型
实现：对数据库和应用设计的物理实现
数据转换和加载：将原有的数据一直到新的数据库中，同时移植原有的应用程序并使其能在新的数据库上运行
测试：对数据库软件进行测试，找出潜在bug
运维：运行和维护
CASE：工具是指任何支持软件开发并能够使得数据库系统的开发活动尽可能高效且有效的工具。