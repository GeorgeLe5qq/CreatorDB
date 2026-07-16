# 04. 第四阶段：学事务与锁

## 优先阅读的类

```text
src/main/java/simpledb/transaction/TransactionId.java
src/main/java/simpledb/transaction/Permissions.java
src/main/java/simpledb/storage/BufferPool.java
```

## 核心问题

多个事务同时读写数据库，怎么避免数据错乱？

需要理解：

- 读锁 / 写锁
- 两阶段锁协议 2PL
- 死锁
- 提交与回滚
- `BufferPool.getPage()` 为什么适合做加锁入口

这部分难度会明显上升，建议等你把存储和执行器看懂后再学。

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
