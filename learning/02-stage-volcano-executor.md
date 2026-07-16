# 02. 第二阶段：学执行器 Volcano 模型

## 优先阅读的类

```text
src/main/java/simpledb/execution/OpIterator.java
src/main/java/simpledb/execution/Operator.java
src/main/java/simpledb/execution/SeqScan.java
src/main/java/simpledb/execution/Filter.java
src/main/java/simpledb/execution/Join.java
src/main/java/simpledb/execution/Aggregate.java
src/main/java/simpledb/execution/Insert.java
src/main/java/simpledb/execution/Delete.java
```

## 核心模型

SimpleDB 使用的是 Volcano 模型，也就是每个算子都像迭代器：

```java
open();
while (hasNext()) {
    Tuple t = next();
}
close();
```

可以把 SQL 想象成一棵执行树：

```sql
SELECT * FROM users WHERE age > 18;
```

大概对应：

```text
Filter(age > 18)
    |
 SeqScan(users)
```

`SeqScan` 一行一行吐数据，`Filter` 判断条件，符合就继续往上吐。

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
