# 仓库指南

## 项目结构与模块组织

本仓库是 SimpleDB 的 Java 8 Maven 实现。主代码位于 `src/main/java/simpledb`，按数据库子系统划分为 `common`、`storage`、`execution`、`optimizer`、`transaction`、`index`、`algorithm` 和 `util` 等包。CLI 入口在 `src/main/java/simpledb/SimpleDb.java`，解析器相关类也位于同一包下。测试位于 `src/test/simpledb`，更完整的集成场景位于 `src/test/simpledb/systemtest`。各实验文档在 `document/`；依赖 jar 保存在 `lib/`；格式化配置在 `tools/codestyle/`。

## 构建、测试与开发命令

- `mvn compile`：按 `pom.xml` 中的 Java 8 配置编译主代码。
- `mvn test`：运行 JUnit 4 测试套件。完整测试包含事务、B+ 树和系统测试，可能耗时较长。
- `mvn package`：编译并打包项目产物。
- `mvn formatter:format`：使用 `tools/codestyle/formatter.xml` 执行 Java 代码格式化。
- `java -cp target/classes simpledb.SimpleDb print data.dat 2`：编译后的本地 CLI 调用示例。

## 编码风格与命名约定

使用 Java 8 和 UTF-8。遵循现有包结构，将改动限制在相关子系统内。类名使用 `PascalCase`，方法和字段使用 `camelCase`，常量使用 `UPPER_SNAKE_CASE`，测试类以 `Test` 结尾。设计新代码时，优先使用小接口和高内聚类，并遵守 SRP、OCP、LSP、DIP、ISP、LoD 以及优先组合而非继承的原则。提交前运行格式化工具。

## 测试指南

测试使用 JUnit 4（`org.junit`）。针对局部行为，在 `src/test/simpledb` 中添加聚焦的单元测试；当改动影响端到端数据库流程时，在 `src/test/simpledb/systemtest` 中添加系统测试。测试类应按被测组件命名，例如 `HeapPageWriteTest` 或 `BTreeFileInsertTest`。条件允许时，至少运行相关测试类以及 `mvn test`。

## 提交与 Pull Request 指南

近期提交使用简短、祈使式摘要，例如 `add document for lab6` 和 `pass lab5-indexDB`。提交标题应保持简洁且具体。Pull Request 应说明变更涉及的子系统、列出已运行的测试、标注耗时较长或跳过的测试，并链接相关实验说明或 issue。仅在文档或可视化产物变更时附加截图。

## Agent 专用说明

本仓库包含 `.codegraph/`。定位代码或分析调用路径时，应先查询 CodeGraph，再回退到文本搜索，例如：`codegraph explore "BufferPool getPage locking"`。

## 注意事项

- 一定不要执行任何删除文件的操作
