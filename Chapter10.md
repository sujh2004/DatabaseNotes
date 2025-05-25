# Chapter10 Transaction Management

卡        明细
"Update    insert"
卡1         卡2
+100        -100

可靠性 +100 -100 断电
一致性 -1 -1 = -1

完整性 安全性


Transaction:An action, or series of actions,reads or updates

read(staffNo=x,salary)
salary=salary*1.1
write(staffNo=x,new_salary)

commits
aborts
rolled back

committed transaction cannot be aborted.

Begin Transaction
    SQL1
    /0
    SQL2
Commit

diagram

![alt text](./src/image.png)

四大特性acid
a -> atomocity    原子性
c -> consistency  一致性
i -> isolation    隔离性
d -> durability   持久性

![alt text](./src/image-1.png)

## 10.2 Concurrency Control
交叉导致三种问题：
– Lost update problem.：丢失更新
– Uncommitted dependency problem. (脏读)未提交依赖
– Inconsistent analysis problem：不可重复读/不一致分析


Two basic concurrency control techniques:
- Locking
- Timestamping

读锁叫共享锁 写锁叫独占(排他)锁
可读  不可写 可读 可写

Two-phase locking:Transaction follows 2PL protocol if all locking operations precede first unlock operation in the ransaction

Two phases for transaction:
– Growing phase: acquires all locks but cannot release any locks.
– Shrinking phase: releases locks but cannot acquire any new locks.
![alt text](./src/10.2.3Locking.png)

![alt text](./src/10.2.3Two-Lock.png)