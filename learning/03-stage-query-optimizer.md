# 03. 第三阶段：学查询优化

## 优先阅读的类

```text
src/main/java/simpledb/optimizer/TableStats.java
src/main/java/simpledb/optimizer/IntHistogram.java
src/main/java/simpledb/optimizer/JoinOptimizer.java
src/main/java/simpledb/optimizer/LogicalPlan.java
```

## 核心问题

同一个 SQL 有很多种执行方式，数据库怎么选比较快的那个？

比如三表 join：

```text
A JOIN B JOIN C
```

可以先 `A join B`，也可以先 `B join C`。优化器会用统计信息估算代价，然后选择较优顺序。

初学时只需要先理解：

- 直方图用于估算选择率。
- `TableStats` 用于估算扫描成本和结果行数。
- `JoinOptimizer` 用动态规划找 join 顺序。

## 学习进度

- 开始日期：
- 完成日期：
- 当前状态：未开始
- 本阶段目标：
- 已阅读类：
- 已运行测试：
- 理解笔记：
- 遇到的问题：
- 下一步：
