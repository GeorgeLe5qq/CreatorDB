# 00. 整体地图

CreatorDB / SimpleDB 本质上是一个“从零实现小型关系型数据库内核”的教学项目。作为初学者，不建议一上来就啃所有代码，而是按数据库系统的执行链路来学。

## 学习顺序

先知道数据库做什么。SQL 查询大致会经过：

```text
SQL
 -> Parser 解析
 -> LogicalPlan 逻辑计划
 -> Optimizer 优化
 -> Operator 执行
 -> BufferPool 读写页
 -> HeapFile / B+TreeFile 访问磁盘文件
 -> Transaction / Lock / Log 保证并发与恢复
```

对应项目目录大概是：

```text
src/main/java/simpledb/common       全局对象、配置、类型
src/main/java/simpledb/storage      Tuple、Page、HeapFile、BufferPool
src/main/java/simpledb/execution    SeqScan、Filter、Join、Aggregate 等算子
src/main/java/simpledb/optimizer    查询优化、统计信息、Join 顺序
src/main/java/simpledb/transaction  事务、锁、并发控制
src/main/java/simpledb/index        B+ 树索引
```

先不要急着看 `optimizer`、`transaction`、`index`，它们是后面的内容。

## 学习进度

- 开始日期：
- 完成日期：
- 当前状态：未开始
- 本阶段目标：
- 已完成内容：
- 遇到的问题：
- 下一步：
