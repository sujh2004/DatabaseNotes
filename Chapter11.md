# Chapter11 Query Processing
## 11.1 Overview of Query Processing
![alt text](./src/11.1%20four%20main%20phases.png)
优化分为逻辑优化和物理优化

------------考试不会考---------------

分析
规范化
semantic analysis
simplification
query restructuring

-------------------

查询优化
12条规则
把选择往下拽
![alt text](./src/11.4%20.png)
把笛卡尔积变成选择加连接
![alt text](./src/11.4.2.png)

## 11.5 五条指导
五条指导

---------这章会考，但不会考大题----------------


## 11.6 
nTuples(R)
bFactor(R)
nBlocks(R)

第二类：针对于属性
![](./src/11.6.2.png)
