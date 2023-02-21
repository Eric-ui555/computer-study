# javaweb

## 1、数据库

### 1.1 SQL

通用语法

+ SQL预警可以单行或多行书写，以分号结尾
+ SQL预警不区分大小写，关键字建议使用大写；
+ 注释
  + 单行注释:--注释内容或#注释内容
  + 多行注释：/* 注释 */

SQL分类

+ DDL：操作数据库，表等
+ DML：对表中的数据进行增删改
+ DQL：对表中的数据进行查询
+ DCL：对数据库进行权限控制

### 1.2 DDL

DDL 操作数据库

1、查询

```sql
-- 展示当前数据库
SHOW DATABASES;
```

2、创建

```sql
-- 创建数据库
CREATE DATABASE 数据库名称;
CREATE DATABASE IF NOT EXISTS 数据库名称;
```

3、删除

```sql
-- 删除数据库
DROP DATABASE 数据库名称;
DROP DATABASE IF EXISTS 数据库名称;
```

4、使用数据库

```sql
-- 查看当前使用的数据库
SELECT DATABASE();
-- 使用数据库
USE 数据库名称;
```

DDL-操作表

1、查询表

```sql
-- 查询当前数据库下所有表名称
SHOW TABLES;
-- 查询表结构
DESC 表名称;
```

2、创建表

```sql
CREATE TABLE 表名(
	字段名1 数据类型，
	字段名2 数据类型，
	...
	字段名n 数据类型
);
-- 最后一行不能加对号
```

数据类型

<img src="E:\savefile\typora\image\image-20220801200315153.png" alt="image-20220801200315153" style="zoom:80%;" />

3、删除表

```sql
-- 删除表
DROP TABLE 表名;
DROP TABLE IF EXISTE 表名;
```

4、修改表

```sql
-- 修改表名
ALTER TABLE 表名 RENAME TO 新的表名;
-- 添加一列
ALTER TABLE 表名 ADD COLUMN 列名 数据类型;
-- 修改数据类型
ALTER TABLE 表名 MODIFY 列名 新数据类型;
-- 修改列名和数据类型
ALTER TABLE 表名 CHANGE 列明 新列名 新数据类型;
-- 删除列
ALTER TABLE 表名 DROP 列名;
```

### 1.3 DML

1、添加数据

```sql
-- 给指定列添加数据
INSERT INTO 表名(列名1，列名2，...)VALUES(值1，值2);
-- 给全部列添加数据
INSERT INTO 表名 VALUES(值1,值2,...);
-- 批量添加数据
INSERT INTO 表名(列名1，列名2，...) VALUES(值1，值2)...,(值1，值2...)...;
INSERT INTO 表名 VALUES(值1，值2)...,(值1，值2...)...;
```

2、修改数据

```sql
UPDATE 表名 SET 列名1=值1，列名2-值2,...[WHERE 条件];
```

注意：修改语句中如果不加条件，则将所有数据都修改

3、删除数据

```sql
DELETE FROM 表名 [WHERE 条件]；
```

注意：删除语句中如果不加条件，则将所有数据都删除

### 1.4 DQL

1、基础查询

```sql
-- 查询多个字段
SELECT 字段列表 FROM 表名;
SELECT * FROM 表名;
-- 去除重复记录
SELECT DISTINCT 字段列表 FROM 表名;
-- 起别名
AS: AS也可以省略
```

2、条件查询

```sql
SELECT 字段列表 FROM 表名 WHERE 条件列表;
```

| 符号                 | 功能                                 |
| :------------------- | ------------------------------------ |
| >、<、>=、<=、=      |                                      |
| <>或!=               | 不等于                               |
| BETWEEN...AND...     | 在某个范围之间                       |
| IN(...)              | 多选一                               |
| LIKE 占位符          | 模糊查询 _单个任意字符 %多个任意字符 |
| IS NULL、IS NOT NULL | 是NULL  不是NULL                     |
| AND 或 &&            | 并且                                 |
| OR 或 \|\|           | 或者                                 |
| NOT 或 ！            | 非、不是                             |

3、排序查询

```sql
SELECT 字段列表 FROM 表名 ORDER BY 排序字段名1[排序方式1],排序字段名2[排序方式2]...;
-- 排序方式
-- ASC：升序排列（默认值）
-- DESC： 降序排列
```

注意：如果有多个排序条件，当前面的条件一致时，才会根据第二条件进行排序

4、分组查询

聚合函数：将一**列**数据作为一个整体，进行纵向计算

| 函数名      | 功能                           |
| ----------- | ------------------------------ |
| count(列名) | 统计数量(一般选用不为null的列) |
| max(列名))  | 最大值                         |
| min(列名))  | 最小值                         |
| sum(列名))  | 求和                           |
| avg(列名))  | 平均值                         |

```sql
-- 聚合函数语法
SELECT 聚合函数名(列名) FROM 表;
```

注意：null值不参与聚合函数运算

分组查询语法

```sql
SELECT 字段列表 FROM 表名[WHERE 分组前条件限定] GROUP BY 分组字段名 [HAVING 分组后条件过滤];
```

注意：分组之后，查询的字段为聚合函数和分组字段，查询其他字段无任何意义

where和having区别：

+ 执行时机不一样：where是分组之前进行限定，不满足where条件，则不参与分组，二having是分组之后对结果进行过滤；
+ 可判断的条件不一样：where不能对聚合函数进行判断，having可以。

执行顺序：**where>聚合函数>having**

5、分页查询

```sql
SELECT 字段列表 FROM 表名 LIMIT 其实索引,查询条目数;
```

+ 起始索引：（当前页码-1）* 每页显示的条目数，从0开始

### 1.5 约束

概念：约束是作用域表中列上的规则，用于限制加入表的数据 

分类

| 约束名称 |                             描述                             | 关键字      |
| -------- | :----------------------------------------------------------: | ----------- |
| 非空约束 |                 保证列中虽有数据不能有null值                 | NOT NULL    |
| 唯一约束 |                   保证列中所有数据各不相同                   | UNIQUE      |
| 主键约束 |           主键是一行数据的唯一标识，要求非空且唯一           | PRIMARY KEY |
| 检查约束 |                   保证列中的值满足某一条件                   | CHECK       |
| 默认约束 |               保存数据时，未指定值则采用默认值               | DEFAULT     |
| 外键约束 | 外键用来让两个表的数据之间建立链接，保证数据的一致性和完整性 | FOREIGN KEY |

TIPS：MYSQL不支持检查约束

+ 自动增长auto_increment：当列是数字类型并且唯一约束

```sql
-- 约束：NOT NULL/UNIQUE

-- 添加约束
CREATE TABLE 表名(
	列名 数据类型 约束,
	...
);
-- 建完表后添加非空约束
ALTER TABLE　表名　MODIFY　字段名　数据类型　NOT NULL;
-- 建完表后添加唯一约束
ALTER TABLE　表名　MODIFY　字段名　数据类型　UNIQUE;
-- 建完表后添加主键约束
ALTER TABLE　表名　ADD PRIMARY KEY(字段名);
-- 建完表后添加非空约束
ALTER TABLE　表名　MODIFY　字段名　数据类型　NOT NULL/UNIQUE;
-- 建完表后添加默认约束
ALTER TABLE　表名　ALTER 列名 SET DEFAULT 默认值;

-- 删除非空约束
ALTER TABLE　表名　MODIFY　字段名　数据类型;
-- 删除唯一约束
ALTER TABLE 表名 DROP INDEX 字段名;
-- 删除主键约束
ALTER TABLE 表名 DROP PRIMARY KEY;
-- 删除默认约束
ALTER TABLE 表名 ALTER 列名 DROP DEFAULT;
```

外键约束

```sql
-- 添加约束
CREATE TABLE 表名(
	列名 数据类型 约束,
	...
    [CONSTRAINT] [外键名称] FOREIGN KEY(外键列名) REFERENCES 主表(主表列名)
);

-- 建完表后添加外键约束
ALTER TABLE 表名 ADD CONSTRAINT 外键名称 FOREING KEY (外键字段名称) REFERENCES 主表(主表列名称);

-- 删除外键约束
ALTER　TABLE 表名 DROP FOREIGN KEY 外键名称;
```

### 1.6 数据库设计

+ 建立数据库中的表结构以及标语表之间的关联关系的过程
+ 数据库设计的步骤
  + 需求分析（数据是什么？数据具有哪些属性？数据与属性的特点是森么？）
  + 逻辑分析（ER图进行逻辑建模）
  + 物理设计（根据数据库自身的特点吧逻辑设计转换为物理设计）
  + 维护设计（对新的需求进行建表，表优化）

+ 表关系

  + 一对一

  + 实现方式：在任意一方加入外键，关联另一方逐渐，并且设置外键为唯一UNIQUE
    + 一对多
      + 实现方式：在多的一方建立外键，指向一的一方的主键

  + 多对多
    + 实现方式：建立第三张中间表，中间表至少包含两个外键，分别关联两方主键

+ 笛卡尔积：取A，B集合所有组合情况

### 1.7 多表查询

+ 多表查询：从多张表查询数据

  + 连接查询

    + 内连接：相当于查询A B交集数据

    + ```sql
      -- 隐式内连接
      SELECT 字段列表 FROM 表1, 表2...WHERE 条件;
      
      -- 显式内连接
      SELECT 字段列表 FROM 表1 [INNER] JOIN 表2 ON 条件;
      ```

    + 外连接

      + 左外连接：相当于查询A表所有数据和交集部分数据
      + 右外连接：相当于查询B表所有数据和交集部分数据

    + ```sql
      -- 左外连接
      SELECT 字段列表 FROM 表1 LEFT[OUTER] JOIN 表2 ON 条件;
      
      -- 右外连接
      SELECT 字段列表 FROM 表1 RIGHT[OUTER] JOIN 表2 ON 条件;
      ```

  + 子查询：查询中嵌套查询

    + 子查询根据查询结果的不同，租用不同

      + 单行单列：作为条件值，使用= != > <等进行条件判断 

      + ```sql
        SELECT 字段列表 FROM 表 WHERE 字段名=(子查询);
        ```

      + 多行单列：作为条件值，使用in等关键字进行条件判断

        ```sql
        SELECT 字段列表 FROM 表 WHERE 字段名 in(子查询);
        ```

      + 多行多列：作为虚拟表

        ```sql
        SELECT 字段列表 FROM (子查询) WHERE 条件;
        ```

### 1.8 事务

简介：

+ 一组数据库操作命令

```sql
-- 开启事务
START TRANSACTION;
BEGIN;
-- 提交事务
COMMIT;
-- 回滚事务
ROLLBACK;
```

 事务四大特征

+ 原子性：事务是不可分割的最小操作单位，要么同时成功，要么同时失败；
+ 一致性：事务完成时，必须是所有的数据都保持一致状态；
+ 隔离性：多个事物之间，操作的可见性；
+ 持久性：事务一旦提交或回滚，它对数据库中的数据的改变就是永久的。 

MySQL事务默认自动提交

```sql
-- 查看事务的默认提交方式
SELECT @@autocommit;
-- 1 自动提交  0 手动提交
-- 修改事务提交方式
SELECT @@autocommit = 0;
```

## 2、JDBC

+ JDBC就是使用java语言操作关系型数据库的一套API
+ 全称：java DataBase Connectivity java数据库连接
+ 本质
  + 官方定义的一套操作所有关系型数据库的规则，即接口
  + 各个数据库厂商去实现这套接口，提供数据库驱动jar包
  + 真正执行的代码是驱动jar包中的实现类
+ JDBC好处
  + 各数据库厂商使用相同的接口，java代码不需要针对不同数据库分别开发
  + 可随时替换底层数据库，访问数据库的java代码基本不变  

+ 步骤

```java
// 1、注册启动
Class.forName("com.mysql.cj.jdbc.Driver");
// 2、获取数据库连接对象
String url = "jdbc:mysql://localhost:3306/sch_db";
String user = "root";
String password = "c0625fl.";
Connection conn = DriverManager.getConnection(url,user,password);
// 3、定义sql
String sql = "update stu set math = 100 where id = 1;";
// 4、获取执行sql的对象
Statement stmt = conn.createStatement();
// 5、执行sql
int count = stmt.executeUpdate(sql);
// 6、处理结果
System.out.println(count);
// 7、释放资源
stmt.close();
conn.close();
```

### 2.1 JDBC API 详解

1、DriverManager：驱动管理对象

+ 注册驱动：告诉程序该使用哪一个数据库驱动jar

```java
static void registerDriver(Driver driver) :注册与给定的驱动程序 DriverManager 。
Class.forName("com.mysql.jdbc.Driver"):写代码使用：  
```

+ 获取数据库连接：

```java
方法：static Connection getConnection(String url, String user, String password) 
* 参数：
    * url：指定连接的路径
    * 语法：jdbc:mysql://ip地址(域名):端口号/数据库名称
    * 例子：jdbc:mysql://localhost:3306/db3
    * 细节：如果连接的是本机mysql服务器，并且mysql服务默认端口是3306，则url可以简写为：jdbc:mysql:///数据库名称
    * user：用户名
    * password：密码 
```

2、Connection：数据库连接对象

+ 获取执行sql 的对象

```java
Statement createStatement()  普通执行SQL对象
PreparedStatement prepareStatement(String sql)  预编译SQL的执行SQL对象：放置SQL注入
```

+ 管理事务

```java
开启事务：setAutoCommit(boolean autoCommit)：调用该方法设置参数为false，即开启事务
提交事务：commit() 
回滚事务：rollback() 
```

3、Statement：执行sql的对象

+ 执行sql语句
+ 执行DML、DDL语句

```java
boolean execute(String sql) ：可以执行任意的sql 了解 
int executeUpdate(String sql) ：执行DML（insert、update、delete）语句、DDL(create，alter、drop)语句
* 返回值：影响的行数；
```

+ 执行DQL语句

```java
ResultSet executeQuery(String sql)  ：执行DQL（select)语句
```

4、ResultSet

+ 结果集对象，封装查询结果

```java
ResultSet stmt.excuteQuery(sql):执行DQL语句,返回ResultSet对象
```

+ 获取查询结果

```java
boolean next():将光标从当前位置先前移动一行；判断当前行是否为有效行；
返回值：
    true:有效行，当前行有数据、
    false:无效行，当前行没有数据
        
xxx getXxx(参数):获取数据
Xxx：代表数据类型: 如:int getInt(),	String getString()
参数：
    1. int：代表列的编号,从1开始, 如：getString(1)
    2. String：代表列名称。 如：getDouble("balance")
```

5、PreparedStatement

+ **预编译SQL**语句并执行；预防**SQL注入**问题(将敏感字符进行转义)

+ SQL注入：通过操作输入来修改实现定义好的SQL语句，用以达到执行代码对服务器进行攻击的方法

```java
SQL注入问题：在拼接sql时，有一些sql的特殊关键字参与字符串的拼接。会造成安全性问题
输入用户随便，输入密码：a' or 'a' = 'a
sql：select * from user where username = 'fhdsjkf' and password = 'a' or 'a' = 'a' 
```

+ 获取PreparedStatement对象

```java
// SQL语句中的参数值，使用？占位符替代
String sql = ”select * from user where username =? and password = ?;
// 通过Connection对象，并传入对应的sql语句
PreparedStatement pstmt = conn.prepareStatement(sql);
```

+ 设置参数值

```
PrepareStatement对象：setXxx(参数1，参数2)：给？赋值
Xxx:数据类型；如setInt(参数1,参数2);
参数1：？的位置编号，从1开始
参数2：？的值
```

+ 执行SQL

```
executeUpdate(); / executeQuery(); 不需要在传递sql
```

### 2.2 数据库连接池

+ 数据库连接池是个容器，负责分配、管理数据库连接

+ 它允许应用和程序重复使用一个现有的数据库连接，而不是重新建立一个；

+ 释放空闲时间超过最带空闲时间的数据库连接来避免因为没有释放数据库连接而引起的数据库连接遗漏；

+ 好处

  + 资源重用
  + 提升系统响应速度
  + 避免数据库连接遗漏

+ 标准接口：DataSource 

  ```java
  Connection getConnection();
  ```

+ 常见的数据库连接池：DBCP、C3P0、Druid

+ Druid
  + Druid连接池是阿里巴巴开源的数据库连接池项目
  + 功能强大，性能优秀，是Java语言最好的数据库连接池之一

+ Druid使用步骤
  + 导入jar包
  + 定义配置文件
  + 加载配置文件
  + 获取数据库连接池对象
  + 获取连接

## 3、Maven

Maven是专门用于管理和构建java项目的工具

+ 提供了一套标准化的项目结构
+ 提供了一套标准化的构架流程（编译、测试、打包、发布）
+ 提供了一套方便的**依赖管理机制**

依赖管理：就是管理项目所依赖的第三方资源（jar包、插件...）

Maven常用命令

```java
mvn compile: 编译
mvn clean: 清理
mvn test: 测试
mvn package: 打包
mvn install: 安装
```

Maven生命周期

+ Maven构建项目生命周期描述的是以后构建过程经历了多少个事件
+ Maven对项目构建的生命周期划分为3套
  + clean：清理工作
  + default：核心工作，例如编译，测试，打包，安装等
  + site：产生报告，发布站点等

Maven坐标

+ Maven中的坐标是资源的唯一标识
+ 使用坐标来定义项目或引入项目中需要的依赖

Maven坐标主要组成

+ groupId：定义当前Maven项目隶属组织名称（通常是域名反写）
+ artifactId：定义当前Maven项目名称（通常是模块名称）
+ version：定义当前项目版本号

Maven项目依赖管理

+ 导入依赖：https://mvnrepository.com/
