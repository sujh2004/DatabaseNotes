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
|逻辑| 卡  &nbsp;终端 明细(联系的属性而非两个主体的属性)
|物理| 具体的语句

多对多必须单独弄一个表
一对多可以通过主外键

逻辑的时候知道要用关系型DBMS，但不知道用哪个

## 7.6.3
Conceptual database design: The process of constructing a model of the information used in an enterprise,independent of all physical considerations
独立于

若找不到 没有需求则罢，有需求则调整ER(概念)