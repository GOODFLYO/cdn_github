---
title: mysql教程
date: 2022-05-10 21:00:55
tags:
- 语言
categories:
- 计算机
---
**零、零散知识点**

**层次数据库**是按记录来存取数据的；

**网状数据库**是采用网状原理和方法来存储数据；

**关系型数据库**是以行和列的形式存储数据。

1. 规范化是为了解决数据库中数据的插入、删除、修改异常等问题的一组规则
2. 关系数据库管理系统应能实现的专门关系运算包括 **选择、投影、连接**
3. 属于数据完整性约束的是：实体完整性、参照完整性、用户定义的完整性
4. DML是数据操纵语言，包括select、insert、delete、update，后三个动作会改变数据，可以创建触发器来捕获动作。 DDL是数据定义语言，创建库、表、触发器、存储过程、视图等命令，均属于此范畴。 综上，创建触发器是DDL，触发器工作依靠DML。

**一、**SQL简介

**SQL****介绍**

1. SQL全称是 Structured Query Language（结构化查询语言）是用于访问和操作数据库中的数据的标准数据库编程语言
2. SQL 是一种 ANSI（American National Standards Institute 美国国家标准化组织）标准的计算机语言

**1.SQL** **能做什么？**

1. SQL可以创建新的数据库及其对象（表，索引，视图，存储过程，函数和触发器）
2. SQL可以TRUNCATE（删除）表中的所有记录
3. SQL可以在数据库中设置用户的GRANT和REVOKE权限
4. 注意：
5. 虽然 SQL 是一门 ANSI（American National Standards Institute 美国国家标准化组织）标准的计算机语言，但是仍然存在着多种不同版本的 SQL 语言。

然而，为了与 ANSI 标准相兼容，它们必须以相似的方式共同地来支持一些主要的命令（比如 SELECT、UPDATE、DELETE、INSERT、WHERE 等等）。

**注释：** 除SQL标准之外，大多数SQL数据库程序还具有自己的专有扩展名！

**2.****在您的网站中使用** **SQL**

要创建一个显示数据库中数据的网站，您需要：

- 一个RDBMS数据库程序（即MS Access，SQL Server，MySQL）。
- 使用服务器端脚本语言，如PHP或ASP。
- 使用SQL来获取所需的数据。
- 使用HTML / CSS来设置页面的样式

**3.RDBMS**

RDBMS 指关系型数据库管理系统，全称 Relational Database Management System。

RDBMS 是 SQL 的基础，同样也是所有现代数据库系统的基础，比如 MS SQL Server、IBM DB2、Oracle、MySQL 以及 Microsoft Access。

RDBMS 中的数据存储在被称为表的数据库对象中。

表是相关的数据项的集合，它由列和行组成。

**代码示例：**

SELECT * FROM Customers;

**2****、****SQL** **语法**

**1.SQL****语法规则**

- SQL语句总是以关键字开始。
- SQL语句以分号结尾。
- SQL不区分大小写，意味着更新与UPDATE相同

**2.****一些最重要的** **SQL** **命令**

- **CREATE DATABASE** - 创建新数据库
- **ALTER DATABASE** - 修改数据库
- **CREATE TABLE** - 创建新表
- **ALTER TABLE** - 变更（改变）数据库表
- **DROP TABLE** - 删除表//删除一列
-  
- **SELECT** -     从数据库中提取数据
- **UPDATE** -     更新数据库中的数据
- **DELETE** -     从数据库中删除数据//删除一行
- **INSERT INTO** - 向数据库中插入新数据
- **CREATE INDEX** - 创建索引（搜索键）
- **DROP INDEX** - 删除索引

**3.SQL Select****（选择）** **语法**

SELECT 语法用于从数据库中选择数据。

返回的数据存储在结果表中，称为结果集。

**4.SQL WHERE Clause****（查询子句）**

WHERE 子句用于过滤记录。

**注意：** WHERE子句不仅用于SELECT语法，还用于UPDATE，DELETE语法等！

**5.WHERE** **子句中的运算符**

WHERE子句中可以使用以下运算符：

| **运算符** | **描述**                                                     |
| ---------- | ------------------------------------------------------------ |
| =          | 等于                                                         |
| <>         | 不等于。 **注意** ：在某些版本的SQL中，这个操作符可能写成！= |
| >          | 大于                                                         |
| <          | 小于                                                         |
| >=         | 大于等于                                                     |
| <=         | 小于等于                                                     |
| BETWEEN    | 在某个范围内                                                 |
| LIKE       | 搜索某种模式                                                 |
| IN         | 为列指定多个可能的值                                         |

**6.SQL AND, OR and NOT****（与，或不是运算符）**

AND&OR运算符用于根据一个以上的条件过滤记录。

**NOT****语法**

SELECT column1, column2, ...
 FROM table_name
 WHERE NOT condition;

以下SQL语句选择来自"Customers" 的国家不是 "Germany" 且不是 "USA"的所有字段：

**代码示例：**

SELECT * FROM Customers
 WHERE NOT Country='Germany' AND NOT Country='USA';

**7.SQL ORDER BY Keyword****（按关键字排序）**

ORDER BY 关键字用于对结果集进行排序。关键字默认情况下按升序排序记录。

SQL **ORDER** BY 语法

SELECT column1, column2, ...
 FROM table_name
 ORDER BY column1, column2, ... ASC|DESC;

**8.SQL INSERT INTO** **语句（在表中插入）**

INSERT INTO 语句用于向表中插入新记录。

**9.****什么是****SQL NULL****值？**

SQL 中， **NULL** 用于表示缺失的值。数据表中的 NULL 值表示该值所处的字段为空。

具有NULL值的字段是没有值的字段。

如果表中的字段是可选的，则可以插入新记录或更新记录而不向该字段添加值。然后，该字段将被保存为NULL值。

值为 NULL 的字段没有值。尤其要明白的是，NULL 值与 0 或者包含空白（spaces）的字段是不同的。

**10.****如何测试****NULL****值？**

使用比较运算符（例如=，<或<>）来测试NULL值是不可行的。

我们将不得不使用IS NULL和IS NOT NULL运算符。

**IS NULL****语法**

SELECT column_names
 FROM table_name
 WHERE column_name IS NULL;

**IS NOT NULL****语法**

SELECT column_names
 FROM table_name
 WHERE column_name IS NOT NULL;

创建表的时候，NULL 的基本语法如下：

SQL> CREATE TABLE CUSTOMERS(
  ID  INT        NOT NULL,
  NAME VARCHAR (20)   NOT NULL,
  AGE  INT        NOT NULL,
  ADDRESS  CHAR (25) ,
  SALARY  DECIMAL (18, 2),    
  PRIMARY KEY (ID)
 );

**11.SQL UPDATE** **语句（更新表中的记录）**



UPDATE 语句用于更新表中的现有记录。

**12.SQL UPDATE** **语句**

UPDATE 语句用于更新表中已存在的记录。

**SQL UPDATE** **语法**

UPDATE table_name
 SET column1 = value1, column2 = value2, ...
 WHERE condition;

**请注意**

**更新表中的记录时要小心！** 要注意SQL UPDATE 语句中的 WHERE 子句！ WHERE子句指定哪些记录需要更新。如果省略WHERE子句，所有记录都将更新！

**13.SQL Delete** **语句（删除表中的记录）**



DELETE语句用于删除表中现有记录。

**14.SQL DELETE** **语句**

DELETE 语句用于删除表中的行。

**SQL DELETE** **语法**

DELETE FROM table_name
 WHERE condition;

**请注意** **删除表格中的记录时要小心！** 注意SQL DELETE 语句中的 WHERE 子句！ WHERE子句指定需要删除哪些记录。如果省略了WHERE子句，表中所有记录都将被删除！

**删除所有数据**

您可以删除表中的所有行，而不需要删除该表。这意味着表的结构、属性和索引将保持不变：

DELETE FROM table_name;

**或者**

DELETE * FROM table_name;

**注意：** 在没有备份的情况下，删除记录要格外小心！因为你删除了不能重复！

**15.SQL SELECT TOP, LIMIT, ROWNUM(****一样的效果****)**

- SELECT TOP 子句用于指定要返回的记录数量。
- SELECT TOP子句在包含数千条记录的大型表上很有用。返回大量记录会影响性能。

**注：** 并不是所有的数据库系统都支持SELECT TOP子句。MySQL支持LIMIT子句来选择有限数量的记录，而Oracle使用ROWNUM。

**SQL SELECT TOP PERCENT** **实例**

以下SQL语句从 "Customers" 表中选择前50%的记录：

**实例**

SELECT TOP 50 PERCENT * FROM Customers;

**SQL TOP****，****LIMIT****和****ROWNUM****示例**

以下SQL语句从"Customers"表中选择前三个记录：

SELECT TOP 3 * FROM Customers;

以下SQL语句显示了使用LIMIT子句的等效示例：

SELECT * FROM Customers
 LIMIT 3;

以下SQL语句显示了使用ROWNUM的等效示例：

SELECT * FROM Customer
 WHERE ROWNUM <= 3;

**16.SQL LIKE** **运算符**

在WHERE子句中使用LIKE运算符来**搜索列中**的指定模式。

**SQL LIKE** **操作符**

LIKE 操作符用于在 WHERE 子句中搜索列中的指定模式。

有两个通配符与LIKE运算符一起使用：

- ％ - 百分号表示零个，一个或多个字符
- _ - 下划线表示单个字符

**注意：** MS Access使用问号（?）而不是下划线（_）。

百分号和下划线也可以组合使用！

**17.SQL LIKE** **语法**

SELECT column1, column2, ...
 FROM table_name
 WHERE columnN LIKE pattern;

**提示** ：您还可以使用AND或OR运算符组合任意数量的条件。

下面是一些使用'％'和'_'通配符显示不同LIKE运算符的例子：

| **LIKE** **运算符**             | **描述**                             |
| ------------------------------- | ------------------------------------ |
| WHERE CustomerName LIKE 'a%'    | 查找以“a”开头的任何值                |
| WHERE CustomerName  LIKE '%a'   | 查找以“a”结尾的任何值                |
| WHERE CustomerName LIKE '%or%'  | 在任何位置查找任何具有“or”的值       |
| WHERE CustomerName  LIKE '_r%'  | 在第二个位置查找任何具有“r”的值      |
| WHERE CustomerName LIKE 'a*%*%' | 查找以“a”开头且长度至少为3个字符的值 |
| WHERE ContactName  LIKE 'a%o'   | 找到以"a"开头，以"o"结尾的值         |

**18.****使用** **SQL [charlist]** **通配符**

以下SQL语句选择所有客户City以"b"、"s"或"p"开头：

**实例**

SELECT * FROM Customers 
 WHERE City LIKE '[bsp]%';

以下SQL语句选择“City”以“a”、“b”或“c”开头的所有客户：

**实例**

SELECT * FROM Customers 
 WHERE City LIKE '[a-c]%';

以下SQL语句选择所有客户City不以"b"、"s"或"p"开头：

**实例**

SELECT * FROM Customers 
 WHERE City LIKE '[!bsp]%';

**19.SQL IN** **运算符**



IN运算符允许您在WHERE子句中指定多个值。

IN运算符是多个OR条件的简写。

**SQL IN** **语法**

SELECT column_name(s)
 FROM table_name
 WHERE column_name IN (value1, value2, ...);

**或者**

SELECT column_name(s)
 FROM table_name
 WHERE column_name IN (SELECT STATEMENT);

**20.IN** **操作符实例**

以下SQL语句选择位于“Germany”，“France”和“UK”的所有客户：

**代码示例：**

SELECT * FROM Customers
 WHERE Country IN ('Germany', 'France', 'UK');

以下SQL语句选择不在“Germany”，“France”或“UK”中的所有客户：

**代码示例：**

SELECT * FROM Customers
 WHERE Country NOT IN ('Germany', 'France', 'UK');

以下SQL语句选择来自同一国家的所有客户作为供应商：

**代码示例：**

SELECT * FROM Customers
 WHERE Country IN (SELECT Country FROM Suppliers);

**21.SQL BETWEEN****运算符**

BETWEEN 操作符用于选取介于两个值之间的数据范围内的值。

BETWEEN运算符选择给定范围内的值。值可以是数字，文本或日期。

BETWEEN运算符是包含性的：包括开始和结束值。

SELECT column_name(s)
 FROM table_name
 WHERE column_name BETWEEN value1 AND value2;

**22.NOT BETWEEN** **操作符实例**

要显示前面示例范围之外的产品，请使用NOT BETWEEN：

**实例**

SELECT * FROM Products 
 WHERE Price NOT BETWEEN 10 AND 20;

以下SQL语句选择所有带有ProductName BETWEEN'Carnarvon Tigers'和'Mozzarella di Giovanni'的产品：

**实例**

SELECT * FROM Products 
 WHERE ProductName BETWEEN 'Carnarvon Tigers' AND 'Mozzarella di Giovanni' 
 ORDER BY ProductName;

以下 SQL 语句选取 OrderDate 介于 '04-July-1996' 和 '09-July-1996' 之间的所有订单：

**实例**

SELECT * FROM Orders 
 WHERE OrderDate BETWEEN #07/04/1996# AND #07/09/1996#;

**请注意，在不同的数据库中，BETWEEN 操作符会产生不同的结果！

在一些数据库中，BETWEEN 选取介于两个值之间但不包括两个测试值的字段。 在一些数据库中，BETWEEN 选取介于两个值之间且包括两个测试值的字段。 在一些数据库中，BETWEEN 选取介于两个值之间且包括第一个测试值但不包括最后一个测试值的字段

**23.SQL** **通用数据类型**

数据库表中的每一列都需要有一个名称和数据类型。

SQL 开发人员必须在创建 SQL 表时决定表中的每个列将要存储的数据的类型。数据类型是一个标签，是便于 SQL 了解每个列期望存储什么类型的数据的指南，它也标识了 SQL 如何与存储的数据进行交互。

下面的表格列出了 SQL 中通用的数据类型：

| **数据类型**                        | **描述**                                                     |
| ----------------------------------- | ------------------------------------------------------------ |
| CHARACTER(n)                        | 字符/字符串。固定长度 n。                                    |
| VARCHAR(n) 或 CHARACTER  VARYING(n) | 字符/字符串。可变长度。最大长度 n。                          |
| BINARY(n)                           | 二进制串。固定长度 n。                                       |
| BOOLEAN                             | 存储 TRUE 或  FALSE 值                                       |
| VARBINARY(n) 或 BINARY VARYING(n)   | 二进制串。可变长度。最大长度 n。                             |
| INTEGER(p)                          | 整数值（没有小数点）。精度  p。                              |
| SMALLINT                            | 整数值（没有小数点）。精度 5。                               |
| INTEGER                             | 整数值（没有小数点）。精度  10。                             |
| BIGINT                              | 整数值（没有小数点）。精度 19。                              |
| DECIMAL(p,s)                        | 精确数值，精度 p，小数点后位数 s。例如：decimal(5,2) 是一个小数点前有 3 位数小数点后有 2 位数的数字。 |
| NUMERIC(p,s)                        | 精确数值，精度 p，小数点后位数 s。（与 DECIMAL 相同）        |
| FLOAT(p)                            | 近似数值，尾数精度 p。一个采用以 10 为基数的指数计数法的浮点数。该类型的 size 参数由一个指定最小精度的单一数字组成。 |
| REAL                                | 近似数值，尾数精度 7。                                       |
| FLOAT                               | 近似数值，尾数精度 16。                                      |
| DOUBLE PRECISION                    | 近似数值，尾数精度 16。                                      |
| DATE                                | 存储年、月、日的值。                                         |
| TIME                                | 存储小时、分、秒的值。                                       |
| TIMESTAMP                           | 存储年、月、日、小时、分、秒的值。                           |
| INTERVAL                            | 由一些整数字段组成，代表一段时间，取决于区间的类型。         |
| ARRAY                               | 元素的固定长度的有序集合                                     |
| MULTISET                            | 元素的可变长度的无序集合                                     |
| XML                                 | 存储 XML 数据                                                |

 

| **CREATE INDEX** | ***\*CREATE INDEX index_name ON table_name (column_name)   or CREATE UNIQUE INDEX index_name ON table_name (column_name)\**** |
| ---------------- | ------------------------------------------------------------ |
|                  |                                                              |

 

| **CREATE VIEW** | ***\*CREATE VIEW view_name AS SELECT column_name(s) FROM   table_name WHERE condition\**** |
| --------------- | ------------------------------------------------------------ |
|                 |                                                              |

 

| **DROP INDEX** | **ALTER TABLE table_name DROP INDEX index_name (MySQL)`** |
| -------------- | --------------------------------------------------------- |
|                |                                                           |

 

| **INNER JOIN** | ***\*SELECT column_name(s) FROM table_name1 INNER JOIN   table_name2 ON table_name1.column_name=table_name2.column_name\**** |
| -------------- | ------------------------------------------------------------ |
| LEFT JOIN      | **SELECT column_name(s) FROM table_name1 LEFT JOIN table_name2 ON  table_name1.column_name=table_name2.column_name** |
| RIGHT JOIN     | **SELECT column_name(s) FROM table_name1 RIGHT JOIN table_name2 ON  table_name1.column_name=table_name2.column_name** |
| FULL JOIN      | **SELECT column_name(s) FROM table_name1 FULL JOIN table_name2 ON  table_name1.column_name=table_name2.column_name** |
| LIKE           | **SELECT column_name(s) FROM table_name WHERE column_nameLIKE pattern** |

 

| **TRUNCATE TABLE** | ***\*TRUNCATE TABLE table_name\****                          |
| ------------------ | ------------------------------------------------------------ |
| UNION              | **SELECT column_name(s) FROM table_name1 UNION SELECT column_name(s)  FROM table_name2** |
| UNION ALL          | **SELECT column_name(s) FROM table_name1 UNION ALL SELECT column_name(s)  FROM table_name2** |

**三、****SQL** **连接（****Joins****）**



SQL join 用于把来自两个或多个表的行结合起来。

**1.SQL JOIN**

SQL JOIN 子句用于把来自两个或多个表的行结合起来，**基于这些表之间的共同字段。**

最常见的 JOIN 类型： **SQL INNER JOIN****（简单的** **JOIN****）** 。 SQL INNER JOIN 从多个表中返回满足 JOIN 条件的所有行。

**2.****不同的** **SQL JOIN**

在我们继续讲解实例之前，我们先列出您可以使用的不同的 SQL JOIN 类型：

- **INNER JOIN** ：如果表中有至少一个匹配，则返回行
- **LEFT JOIN** ：即使右表中没有匹配，也从左表返回所有的行
- **RIGHT JOIN** ：即使左表中没有匹配，也从右表返回所有的行
- **FULL JOIN** ：只要其中一个表中存在匹配，则返回行
- **注释：** INNER JOIN 与 JOIN 是相同的。

以下是 "Customers" 表中的数据：

| **CustomerID** | **CustomerName**                    | **ContactName** | **Address**                    | **City**    | **PostalCode** | **Country** |
| -------------- | ----------------------------------- | --------------- | ------------------------------ | ----------- | -------------- | ----------- |
| 1              | Alfreds Futterkiste                 | Maria Anders    | Obere Str. 57                  | Berlin      | 12209          | Germany     |
| 2              | Ana Trujillo  Emparedados y helados | Ana Trujillo    | Avda. de la  Constitución 2222 | México D.F. | 05021          | Mexico      |
| 3              | Antonio Moreno Taquería             | Antonio Moreno  | Mataderos 2312                 | México D.F. | 05023          | Mexico      |

选自 "Orders" 表的数据：

| **OrderID** | **CustomerID** | **EmployeeID** | **OrderDate** | **ShipperID** |
| ----------- | -------------- | -------------- | ------------- | ------------- |
| 10308       | 2              | 7              | 1996-09-18    | 3             |
| 10309       | 37             | 3              | 1996-09-19    | 1             |
| 10310       | 77             | 8              | 1996-09-20    | 2             |



**SQL INNER JOIN** **实例**

以下SQL语句将返回所有下订单的客户：

**示例**

SELECT Customers.CustomerName, Orders.OrderID 
 FROM Customers 
 INNER JOIN Orders 
 ON Customers.CustomerID=Orders.CustomerID 
 ORDER BY Customers.CustomerName;

**注释：** 如果表中至少有一个匹配项，INNER JOIN 关键字将返回一行。如果 "Customers" 表中的行与"Orders" 不匹配，则不会列出行。

以下SQL语句选择包含客户和货运单信息的所有订单：

**示例：**

SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
 FROM ((Orders
 INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID)
 INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID);

让我们看看选自 "Orders" 表的数据：

| **OrderID** | **CustomerID** | **OrderDate** |
| ----------- | -------------- | ------------- |
| 10308       | 2              | 1996-09-18    |
| 10309       | 37             | 1996-09-19    |
| 10310       | 77             | 1996-09-20    |

然后，看看选自 "Customers" 表的数据：

| **CustomerID** | **CustomerName**                    | **ContactName** | **Country** |
| -------------- | ----------------------------------- | --------------- | ----------- |
| 1              | Alfreds Futterkiste                 | Maria Anders    | Germany     |
| 2              | Ana Trujillo  Emparedados y helados | Ana Trujillo    | Mexico      |
| 3              | Antonio Moreno Taquería             | Antonio Moreno  | Mexico      |

请注意，"Orders" 表中的 "CustomerID" 列指向 "Customers" 表中的客户。上面这两个表是通过 "CustomerID" 列联系起来的。

然后，如果我们运行下面的 SQL 语句（包含 INNER JOIN）：

**实例**

SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate 
 FROM Orders 
 INNER JOIN Customers 
 ON Orders.CustomerID=Customers.CustomerID;

运行结果如下所示：

| **OrderID** | **CustomerName**                   | **OrderDate** |
| ----------- | ---------------------------------- | ------------- |
| 10308       | Ana Trujillo Emparedados y helados | 1996-09-18    |

**SQL LEFT JOIN** **实例**

以下SQL语句将选择所有客户以及他们可能拥有的任何订单：

**实例**

SELECT Customers.CustomerName, Orders.OrderID 
 FROM Customers 
 LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID 
 ORDER BY Customers.CustomerName;

**注释：** LEFT JOIN 关键字返回左表（Customers）中的所有行，即使在右边表（Orders）中没有匹配。

***结果只会显示符合\******where\******子句的数据，只要没有符合的都不会显示，因为它是筛选连接后的临时表中的数据，而\******on\*** ***只是连接，如果右边没有符合的数据，就显示\******null\******，而左边的数据都会显示，不会被过滤，这就是\******where\******和\******on\******最大的区别\***

**SQL RIGHT JOIN** **实例**

以下SQL语句将返回所有雇员以及他们可能已经放置的任何订单：

**实例**

SELECT Orders.OrderID, Employees.LastName, Employees.FirstName  
 FROM Orders 
 RIGHT JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID 
 ORDER BY Orders.OrderID;

**注释：** RIGHT JOIN 关键字返回右表（Employees）的所有行，即使在左表（Orders）中没有匹配。

以下是"Customers" 表中的数据：

| **CustomerID** | **CustomerName**                    | **ContactName** | **Address**                    | **City**    | **PostalCode** | **Country** |
| -------------- | ----------------------------------- | --------------- | ------------------------------ | ----------- | -------------- | ----------- |
| 1              | Alfreds Futterkiste                 | Maria Anders    | Obere Str. 57                  | Berlin      | 12209          | Germany     |
| 2              | Ana Trujillo  Emparedados y helados | Ana Trujillo    | Avda. de la  Constitución 2222 | México D.F. | 05021          | Mexico      |
| 3              | Antonio Moreno Taquería             | Antonio Moreno  | Mataderos 2312                 | México D.F. | 05023          | Mexico      |

选自 "Orders" 表的数据：

| **OrderID** | **CustomerID** | **EmployeeID** | **OrderDate** | **ShipperID** |
| ----------- | -------------- | -------------- | ------------- | ------------- |
| 10308       | 2              | 7              | 1996-09-18    | 3             |
| 10309       | 3              | 3              | 1996-09-19    | 1             |
| 10310       | 77             | 8              | 1996-09-20    | 2             |



**SQL FULL OUTER JOIN** **实例**

当左（表1）或右（表2）表记录匹配时，FULL OUTER JOIN关键字将返回所有记录。

**注意：** FULL OUTER JOIN可能会返回非常大的结果集！

以下SQL语句选择所有客户和所有订单：

SELECT Customers.CustomerName, Orders.OrderID
 FROM Customers
 FULL OUTER JOIN Orders ON Customers.CustomerID=Orders.CustomerID
 ORDER BY Customers.CustomerName;

从这套结果中选择的数据如下：

| **CustomerName**                    | **OrderID** |
| ----------------------------------- | ----------- |
| Alfreds Futterkiste                 |             |
| Ana Trujillo  Emparedados y helados | 10308       |
| Antonio Moreno Taquería             | 10365       |
|                                     | 10382       |
|                                     | 10351       |

**注意** ： FULL OUTER JOIN关键字返回左表（Customers）中的所有行，以及右表（Orders）中的所有行。如果 "Customers"中的行中没有"Orders"中的匹配项，或者"Orders"中的行中没有 "Customers"中的匹配项，那么这些行也会列出。

**3.SQL****自联接**

自联接是一种常规联接，但表本身是连接的。

**就是可以把一张表看成两张表** **取不同的名字暂时使用**

**Self JOIN****语法**

SELECT column_name(s)
 FROM table1 T1, table1 T2
 WHERE condition;

**4.SQL UNION** **运算符**

UNION运算符用于组合两个或更多SELECT语句的结果集。

- UNION中的每个SELECT语句必须具有相同的列数
- 这些列也必须具有相似的数据类型
- 每个SELECT语句中的列也必须以相同的顺序排列

**SQL UNION** **语法**

SELECT column_name(s) FROM table1
 UNION
 SELECT column_name(s) FROM table2;

**注释：** 默认情况下，UNION 运算符选择一个不同的值。如果允许重复值，请使用 UNION ALL。

**SQL UNION ALL** **语法**

SELECT column_name(s) FROM table1
 UNION ALL
 SELECT column_name(s) FROM table2;

**注释：** UNION结果集中的列名总是等于UNION中第一个SELECT语句中的列名。

**5.SQL SELECT INTO** **语句（这是列的插入复制）**

SELECT INTO 语句从一个表复制数据，然后把数据插入到另一个新表中。***

我们可以把所有的列都复制到新表中：

SELECT * 
 INTO _newtable_ [IN _externaldb_ ] 
 FROM _table1;_

或者只复制希望的列插入到新表中：

SELECT _column_name(s)_ 
 INTO _newtable_ [IN _externaldb_ ] 
 FROM _table1;_

提示： 将使用SELECT语句中定义的列名和类型创建新表。您可以使用AS子句来应用一个新名称。

创建 Customers 的备份复件：

SELECT * 
 INTO CustomersBackup2013 
 FROM Customers;

请使用 IN 子句来复制表到另一个数据库中：

SELECT * 
 INTO CustomersBackup2013 IN 'Backup.mdb' 
 FROM Customers;

只复制一些列插入到新表中：

SELECT CustomerName, ContactName 
 INTO CustomersBackup2013 
 FROM Customers;

**6.SQL INSERT INTO SELECT** **语句（这是列的插入复制）**

INSERT INTO SELECT 语句从表中复制数据，并将数据插入现有的表中。目标表中的任何现有行都不会受到影响

我们可以将所有列从一个表中复制到另一个已经存在的表中：

INSERT INTO _table2_ 
 SELECT * FROM _table1;_

或者我们可以把想要的列复制到另一个现有的表中：

INSERT INTO _table2_ 
 _(column_name(s))_ 
 SELECT _column_name(s)_ 
 FROM _table1;_

把 "Suppliers" 一栏复制到 "Customers" 一栏：

**实例**

INSERT INTO Customers (CustomerName, Country) 
 SELECT SupplierName, Country FROM Suppliers;

\# 

**四、****SQL** **子查询**

子查询（Sub Query）或者说内查询（Inner Query），也可以称作嵌套查询（Nested Query），是一种嵌套在其他 SQL 查询的 WHERE 子句中的查询。

子查询用于为主查询返回其所需数据，或者对检索数据进行进一步的限制。

子查询可以在 SELECT、INSERT、UPDATE 和 DELETE 语句中，同 =、<、>、>=、<=、IN、BETWEEN 等运算符一起使用。

使用子查询必须遵循以下几个规则：

- 子查询必须括在圆括号中。
- 子查询的 SELECT 子句中只能有一个列，除非主查询中有多个列，用于与子查询选中的列相比较。
- 子查询不能使用 ORDER BY，不过主查询可以。在子查询中，GROUP BY 可以起到同 ORDER BY 相同的作用。
- 返回多行数据的子查询只能同多值操作符一起使用，比如 IN 操作符。
- SELECT 列表中不能包含任何对 BLOB、ARRAY、CLOB 或者 NCLOB 类型值的引用。
- 子查询不能直接用在集合函数中。
- BETWEEN 操作符不能同子查询一起使用，但是 BETWEEN 操作符可以用在子查询中。

**五、****SQL****函数**

**一、创建函数** **语法：** 

*create function* *函数名**(**参数列表**)* 

*retrurns* *返回类型* 

*begin* *函数体* *end* 

注意： 参数列表包含两部分： 参数名 参数类型函数体：肯定会有return语句，如果没有会报错 如果return语句没有放在函数体的最后也不会报错，但不建议 return值；（建议放最后）函数体中仅有一句话，则可以省略begin end使用delimiter语句设置结束标记 学过的函数：LENGTH、SUBSTR、CONCAT等 **二、调用语法** **语法：** 

*SELECT* *函数名（参数列表）* *即执行函数中的所有语句，并显示返回值* #函数的使用（案例演示） 无参有返回 #返回公司的员工个数 

注：mysql的设置默认是不允许创建函数 这是我们开启了bin-log, 我们就必须指定我们的函数是否是

1 .DETERMINISTIC 不确定的 

2 .NO SQL 没有SQl语句，当然也不会修改数据

3 .READS SQL DATA 只是读取数据，当然也不会修改数据

1. MODIFIES SQL DATA 要修改数据 
2. CONTAINS SQL 包含了SQL语句 其中在function里面，只有 DETERMINISTIC, NO SQL 和 READS SQL DATA 被支持。

如果我们开启了 bin-log, 我们就必须为我们的function指定一个参数。 

在MySQL中创建函数时出现这种错误的解决方法：

set global log_bin_trust_function_creators=TRUE;

或执行： set global log_bin_trust_function_creators=1;

***举个例子\***

-- (3)     创建一个函数，输入出生日期，返回年龄。
 drop function if EXISTS func_年龄;
 delimiter $$
 CREATE FUNCTION `func_年龄`(
 inyear date
 )
          RETURNS integer
 NO SQL -- 表示方法体里里面没有关于sql的语句了
 BEGIN
          DECLARE a INT DEFAULT 0;
          SET a = YEAR(now())-YEAR(inyear);
          RETURN a;
 END$$
 delimiter;
 
 SELECT func_年龄('2001-08-11') 年龄;

**顺序结构**

先来一个简单的，创建一个函数将'2009-06-23 00:00:00'这样格式的datetime时间转化为‘2009年6月23日0时0分0秒’这样的格式：

\## 创建一个叫getdate的自定义函数 ##

DELIMITER $$ DROP FUNCTION IF EXISTS testdb.fn_getdate$$ CREATE FUNCTION testdb.fn_getdate(gdate datetime) 

RETURNS varchar(255) BEGIN DECLARE dt VARCHAR(255) DEFAULT ''; SET dt = date_format(gdate, '%Y年%m月%d日%h时%i分%s秒'); RETURN dt; END $$ DELIMITER ;

**解析：**

第一句DELIMITER 是定义一个结束标识符$$，因为MySQL默认是以分号作为SQL语句的结束符的，而函数体内部要用到分号，所以会跟默认的SQL结束符发生冲突，所以需要先定义一个其他的符号作为SQL的结束符；

第二句是如果这个函数已经存在了，就删除掉，testdb是数据库的名字，函数是跟数据库相关联的，getdate是函数的名字；

第三句是创建一个函数，（）里是参数的名字和类型，RETURNS 定义这个函数返回值的类型；

函数体必须放在BEGIN END之间；

DECLARE 是定义函数体的变量，这里定义一个变量x,默认是空，然后SET给x变量赋值；

RETURN 是返回值，这里把变量x返回，x的类型必须与第三句中定义的返回类型一致。

**调用：********SELECT** fn_getdate('2009-06-23 00:00:00'）; //返回 '2009年06月23日00时00分00秒'

**自定义函数分为二种，一种是标量值函数，另一种是表格值函数**

**一****.** **标量值函数** **：返回一个标量值**

**语法：**

Create function 函数名（参数）
 Returns 返回值数据类型
 as
 begin
 SQL语句(必须有return 变量或值)
 End

例子：

1.创建函数：

CREATE FUNCTION MySTR(@strs VARCHAR(50))
 RETURNS VARCHAR(50) 
 AS
 BEGIN
 DECLARE @str2 VARCHAR(30)
 SET @str2=@strs
 RETURN @str2
 END

2.执行函数：

SELECT dbo.MySTR('aa') AS result

在sql语句中执行：

DECLARE @str3 VARCHAR(30)
 SET @str3=(select name from userinfo where huji=dbo.MySTR('邯郸') and id=23 )
 select @str3

**函数的调用：**

- 直接使用函数名()就可以调用【**虽然这么说，但返回的是一个结果，****sql****中不使用****select****的话任何结果都无法显示出来（所以单纯调用会报错），】**
- 如果想要传入参数可以使用函数名(参数)
- 调用方式【下面调用的函数都是上面中创建的。】：

-- 无参调用
 select myselect3();
 -- 传参调用
 select myselect5("python");
 select * from class where id=myselect5("python");

经典例子：

-- 最简单的仅有一条sql的函数
 create function myselect2() returns int return 666;
 select myselect2(); -- 调用函数
 \--
 create function myselect3() returns int
 begin 
   declare c int;
   select id from class where cname="python" into c;
   return c;
 end;
 select myselect3();
 -- 带传参的函数
 create function myselect5(name varchar(15)) returns int
 begin 
   declare c int;
   select id from class where cname=name into c;
   return c;
 end;
 select myselect5("python");

**二、** **表格值函数** **，表格值函数有二种（内联表格值函数，多句表格值函数）**

- **A****、**内联表格值函数：返回一个表格

语法：

create function 函数名（参数）
 returns table
 as
 return(一条SQL语句)

例子：

1.创建函数：

CREATE FUNCTION  tabcmess(@title VARCHAR(10))
 RETURNS TABLE 
 AS 
 return(select title,des from product where title like '%'+@title+'%')

2.执行：

SELECT * FROM tabcmess('aaa')

- **B.****多句表格值函数**

语法：

 create function 函数名（参数）
  returns 表格变量名table (表格变量定义)
 as
  begin
   SQL语句
  end

例子：

CREATE  function tabcmessalot (@title varchar(10))
 Returns @ctable table(title varchar(10) null,des varchar(100) null)
 As
 Begin
 Insert @ctable Select title,des from product WHERE title LIKE '%'+@title+'%'
 return
 End
 --执行
 SELECT * FROM tabcmessalot('aaa')

**六、****SQL****存储过程**

**七、****SQL****触发器**

**一、基本知识**

**0****、什么是触发器**

触发器是与表有关的数据库对象，在对表进行insert/update/delete之前或之后，会触发并执行触发器中定义的SQL语句。触发器的这种特性可以协助应用在数据库端确保数据的完整性,记录日志,校验数据等。

简单的说，就是一张表发生了某件事(插入、删除、更新操作)，然后自动触发了预先编写好的若干条SQL语句的执行;

**１、****MySQL****触发器的创建语法：** 

CREATE[DEFINER = {'user'| CURRENT_USER}]　
 TRIGGER trigger_name
 trigger_time trigger_event
 ON table_name
 FOR EACH ROW
 [trigger_order]
 trigger_body

**2****、****MySQL****创建语法中的关键词解释：**

| **字段**      | **含义**                                                     | **可能的值**                          |
| ------------- | ------------------------------------------------------------ | ------------------------------------- |
| DEFINER=      | 可选参数，指定创建者，默认为当前登录用户（CURRENT_USER）； 该触发器将以此参数指定的用户执行，所以需要考虑权限问题； | DEFINER='root@%' DEFINER=CURRENT_USER |
| trigger_name  | 触发器名称，最好由表名+触发事件关键词+触发时间关键词组成；   |                                       |
| trigger_time  | 触发时间，在某个事件之前还是之后；                           | BEFORE、AFTER                         |
| trigger_event | 触发事件，如插入时触发、删除时触发； 　　*INSERT*：插入操作触发器，INSERT、LOAD DATA、REPLACE时触发； 　　*UPDATE*：更新操作触发器，UPDATE操作时触发； 　　*DELETE*：删除操作触发器，DELETE、REPLACE操作时触发； | INSERT、UPDATE、DELETE                |
| table_name    | 触发操作时间的表名；                                         |                                       |
| trigger_order | 可选参数，如果定义了多个具有相同触发事件和触法时间的触发器时（  如：BEFORE UPDATE），默认触发顺序与触发器的创建顺序一致，可以 使用此参数来改变它们触发顺序。mysql 5.7.2起开始支持此参数。 　　*FOLLOWS*：当前创建触发器在现有触发器之后激活；  　　*PRECEDES*：当前创建触发器在现有触发器之前激活； | FOLLOWS、PRECEDES                     |
| trigger_body  | 触发执行的SQL语句内容，一般以begin开头，end结尾              | begin .. end                          |

**３、触发执行语句内容（****trigger_body****）中的****OLD****，****NEW****：** 

　　在trigger_body中，我们可以使用NEW表示将要插入的新行（相当于MS SQL的INSERTED），OLD表示将要删除的旧行（相当于MS SQL的DELETED）。通过OLD，NEW中获取它们的字段内容，方便在触发操作中使用，下面是对应事件是否支持OLD、NEW的对应关系：

| **事件** | **OLD** | **NEW** |
| -------- | ------- | ------- |
| INSERT   | ×       | √       |
| DELETE   | √       | ×       |
| UPDATE   | √       | √       |

　　由于UPDATE相当于删除旧行（OLD），然后插入新行（NEW），所以UPDATE同时支持OLD、NEW；

**４、****MySQL****分隔符（****DELIMITER****）：** 

　　MySQL默认使用“;”作为分隔符，SQL语句遇到“;”就会提交。而我们的触发器中可能会有多个“;”符，为了防止触发器创建语句过早的提交，我们需要临时修改MySQL分隔符，创建完后，再将分隔符改回来。使用DELIMITER可以修改分隔符，如下：

DELIMITER $``... ``--触发器创建语句；``$ ``--提交创建语句；``DELIMITER ;

**二、****MySQL****触发器创建进阶：** 

**1****、****MySQL****触发器中使用变量：** 

　　MySQL触发器中变量变量前面加'@'，无需定义，可以直接使用：

-- 变量直接赋值``set` `@num=999;`` ` `-- 使用select语句查询出来的数据方式赋值，需要加括号：``set` `@``name` `=(``select` `name` `from` `table``);

**2****、****MySQL****触发器中使用****if****语做条件判断：** 

-- 简单的if语句：``set` `sex = if (new.sex=1, ``'男'``, ``'女'``);`` ` `-- 多条件if语句：``if old.type=1 ``then`` ``update` `table` `...;``elseif old.type=2 ``then`` ``update` `table` `...;``end` `if;

**三、Ｍｙ****SQL****查看触发器：** 

　　可以使用“show triggers;”查看触发器。由于MySQL创建的触发器保存在“information_schema库中的triggers表中，所以还可以通过查询此表查看触发器：

-- 通过information_schema.triggers表查看触发器：``select` `* ``from` `information_schema.triggers;``
 ` `-- mysql 查看当前数据库的触发器``show triggers;`` ` `-- mysql 查看指定数据库"aiezu"的触发器``show triggers ``from` `aiezu;

**四、****MySQL****删除触发器：** 

**1****、可以使用****drop trigger****删除触发器：** 

drop` `trigger` `trigger_name;

**2****、删除前先判断触发器是否存在：** 

drop` `trigger` `if exists trigger_name

**五、****Msql****触发器用法举例：** 

**1****、****MySQL****触发器****Insert****触发更新同一张表：** 

　　下面我们有一个表“tmp1”，tmp1表有两个整型字段：n1、n2。我们要通过触发器实现，在tmp插入记录时，自动将n2字段的值设置为n1字段的5倍。

　创建测试表和触发器：

-- 创建测试表``drop` `table` `if exists tmp1;``create` `table` `tmp1 (n1 ``int``, n2 ``int``);`` ` `-- 创建触发器``DELIMITER $``drop` `trigger` `if exists tmp1_insert$``create` `trigger` `tmp1_insert``before ``insert` `on` `tmp1``for` `each row``begin`` ``set` `new.n2 = new.n1*5;``end``$``DELIMITER ;

测试触发更新效果：

mysql> ``insert` `tmp1(n1) ``values``(18);``Query OK, 1 row affected (0.01 sec)``
 ` `mysql> ``insert` `tmp1(n1) ``values``(99);``Query OK, 1 row affected (0.00 sec)``
 ` `mysql> ``select` `* ``from` `tmp1;``+``------+------+``| n1 | n2 |``+``------+------+``| 18 | 90 |``| 99 | 495 |``+``------+------+``2 ``rows` `in` `set` `(0.00 sec)

**多个执行语句的触发器语法结构：**

CREATE TRIGGER 触发器名称,触发时机(before,after),触发事件(INSERT,UPDATE和DELETE)

ON 建立触发器的表名 FOR EACH ROW

BEGIN

触发器执行语句;

END;

使用触发器

**八、复制表**

**1.****复制表结构及其数据**

下面这个语句会拷贝数据到新表中。

**注意**：这个语句其实只是把select语句的结果建一个表，所以新表不会有主键，索引。

create table table_name_new as (select * from table_name_old);

**2.****只复制表结构**

create table table_name_new as select * from table_name_old where 1=2;

或者

create table table_name_new like table_name_old;

**注意**：前一种方式是不会复制主键类型，索引的，而后一种方式是把旧表的所有字段类型都复制到新表。

**3.****只复制表数据**

如果两个表结构一样

insert into table_name_new select * from table_name_old;

如果两个表结构不一样

insert into table_name_new(column1,column2...) select column1,column2... from table_name_old;

**注意**：很多文章说可以通过如下语句进行数据复制，table_name_new表可以不存在，会在执行的过程中自动创建。其实该[SELECT ... INTO](https://dev.mysql.com/doc/refman/8.0/en/select-into.html)形式是使查询结果存储在变量或将其写入文件，即table_name_new是一个变量或者文件。

select column1,column2,.... into table_name_new from table_name_old;

需求：我有个表 table1，当我向 table1 insert 数据 xx,xx,5555,xx 的时候，触发建立一个新表 t5555

不能做到在TRIGGER中建立表，会提示

Explicit or implicit commit is not allowed in stored function or trigger.

存储函数中不允许有DDL语句，这样会导致隐式的 commit;

由于上面的原因，因此也不能在事务中使用DLL语言，因为他会隐式的commit;

------解决方案--------------------

1、建议重新考虑你的数据库设计，一般很少会出现这种需求，在数据库设计完成后，不应该出现表结构上的变动。 

2、这个在程序逻辑里判断比较好 

**九、****SQL****事务**

**SQL** **事务**

事务是在数据库上按照一定的逻辑顺序执行的任务序列，既可以由用户手动执行，也可以由某种数据库程序自动执行。

事务实际上就是对数据库的一个或者多个更改。当你在某张表上创建更新或者删除记录的时，你就已经在使用事务了。控制事务以保证数据完整性，并对数据库错误做出处理，对数据库来说非常重要。

实践中，通常会将很多 SQL 查询组合在一起，并将其作为某个事务一部分来执行。

**事务的属性：**

事务具有以下四个标准属性，通常用缩略词 ACID 来表示：

- **原子性：** 保证任务中的所有操作都执行完毕；否则，事务会在出现错误时终止，并回滚之前所有操作到原始状态。
- **一致性：** 如果事务成功执行，则数据库的状态得到了进行了正确的转变。
- **隔离性：** 保证不同的事务相互独立、透明地执行。
- **持久性：** 即使出现系统故障，之前成功执行的事务的结果也会持久存在。

**事务控制：**

有四个命令用于控制事务：

- **COMMIT****：** 提交更改；
- **ROLLBACK****：** 回滚更改；
- **SAVEPOINT****：** 在事务内部创建一系列可以 ROLLBACK 的还原点；
- **SET TRANSACTION****：** 命名事务；

**COMMIT** **命令：**

COMMIT 命令用于保存事务对数据库所做的更改。

COMMIT 命令会将自上次 COMMIT 命令或者 ROLLBACK 命令执行以来所有的事务都保存到数据库中。

COMMIT 命令的语法如下所示：

COMMIT;

示例：

考虑 CUSTOMERS 表，表中的记录如下所示：

+----+----------+-----+-----------+----------+
 | ID | NAME   | AGE | ADDRESS  | SALARY  |
 +----+----------+-----+-----------+----------+
 | 1 | Ramesh  | 32 | Ahmedabad | 2000.00 |
 | 2 | Khilan  | 25 | Delhi   | 1500.00 |
 | 3 | kaushik | 23 | Kota   | 2000.00 |
 | 4 | Chaitali | 25 | Mumbai  | 6500.00 |
 | 5 | Hardik  | 27 | Bhopal  | 8500.00 |
 | 6 | Komal  | 22 | MP    | 4500.00 |
 | 7 | Muffy  | 24 | Indore  | 10000.00 |
 +----+----------+-----+-----------+----------+

下面的示例将会删除表中 age=25 的记录，然后将更改提交（COMMIT）到数据库中。

SQL> DELETE FROM CUSTOMERS
   WHERE AGE = 25;
 SQL> COMMIT;

上述语句将会从表中删除两行记录，再执行 SELECT 语句将会得到如下结果：

+----+----------+-----+-----------+----------+
 | ID | NAME   | AGE | ADDRESS  | SALARY  |
 +----+----------+-----+-----------+----------+
 | 1 | Ramesh  | 32 | Ahmedabad | 2000.00 |
 | 3 | kaushik | 23 | Kota   | 2000.00 |
 | 5 | Hardik  | 27 | Bhopal  | 8500.00 |
 | 6 | Komal  | 22 | MP    | 4500.00 |
 | 7 | Muffy  | 24 | Indore  | 10000.00 |
 +----+----------+-----+-----------+----------+

**ROLLBACK** **命令：**

ROLLBACK 命令用于撤销尚未保存到数据库中的事务。

ROLLBACK 命令只能撤销自上次 COMMIT 命令或者 ROLLBACK 命令执行以来的事务。

ROLLBACK 命令的语法如下所示：

ROLLBACK;

示例：

考虑 CUSTOMERS 表，表中的记录如下所示：

+----+----------+-----+-----------+----------+
 | ID | NAME   | AGE | ADDRESS  | SALARY  |
 +----+----------+-----+-----------+----------+
 | 1 | Ramesh  | 32 | Ahmedabad | 2000.00 |
 | 2 | Khilan  | 25 | Delhi   | 1500.00 |
 | 3 | kaushik | 23 | Kota   | 2000.00 |
 | 4 | Chaitali | 25 | Mumbai  | 6500.00 |
 | 5 | Hardik  | 27 | Bhopal  | 8500.00 |
 | 6 | Komal  | 22 | MP    | 4500.00 |
 | 7 | Muffy  | 24 | Indore  | 10000.00 |
 +----+----------+-----+-----------+----------+

下面的示例将会从表中删除所有 age=25 的记录，然后回滚（ROLLBACK）对数据库所做的更改。

SQL> DELETE FROM CUSTOMERS
   WHERE AGE = 25;
 SQL> ROLLBACK;

结果是删除操作并不会对数据库产生影响。现在，执行 SELECT 语句将会得到如下结果：

+----+----------+-----+-----------+----------+
 | ID | NAME   | AGE | ADDRESS  | SALARY  |
 +----+----------+-----+-----------+----------+
 | 1 | Ramesh  | 32 | Ahmedabad | 2000.00 |
 | 2 | Khilan  | 25 | Delhi   | 1500.00 |
 | 3 | kaushik | 23 | Kota   | 2000.00 |
 | 4 | Chaitali | 25 | Mumbai  | 6500.00 |
 | 5 | Hardik  | 27 | Bhopal  | 8500.00 |
 | 6 | Komal  | 22 | MP    | 4500.00 |
 | 7 | Muffy  | 24 | Indore  | 10000.00 |
 +----+----------+-----+-----------+----------+

**SAVEPOINT** **命令：**

SAVEPOINT 是事务中的一个状态点，使得我们可以将事务回滚至特定的点，而不是将整个事务都撤销。

SAVEPOINT 命令的记录如下所示：

SAVEPOINT SAVEPOINT_NAME;

该命令只能在事务语句之间创建保存点（SAVEPOINT）。ROLLBACK 命令可以用于撤销一系列的事务。

回滚至某一保存点的语法如下所示：

ROLLBACK TO SAVEPOINT_NAME;

下面的示例中，你计划从 CUSTOMERS 表中删除三条不同的记录，并在每次删除之前创建一个保存点（SAVEPOINT），从而使得你可以在任何任何时候回滚到任意的保存点，以恢复数据至其原始状态。

示例：

考虑 CUSTOMERS 表，表中的记录如下所示：

+----+----------+-----+-----------+----------+
 | ID | NAME   | AGE | ADDRESS  | SALARY  |
 +----+----------+-----+-----------+----------+
 | 1 | Ramesh  | 32 | Ahmedabad | 2000.00 |
 | 2 | Khilan  | 25 | Delhi   | 1500.00 |
 | 3 | kaushik | 23 | Kota   | 2000.00 |
 | 4 | Chaitali | 25 | Mumbai  | 6500.00 |
 | 5 | Hardik  | 27 | Bhopal  | 8500.00 |
 | 6 | Komal  | 22 | MP    | 4500.00 |
 | 7 | Muffy  | 24 | Indore  | 10000.00 |
 +----+----------+-----+-----------+----------+

操作序列如下所示：

SQL> SAVEPOINT SP1;
 Savepoint created.
 SQL> DELETE FROM CUSTOMERS WHERE ID=1;
 1 row deleted.
 SQL> SAVEPOINT SP2;
 Savepoint created.
 SQL> DELETE FROM CUSTOMERS WHERE ID=2;
 1 row deleted.
 SQL> SAVEPOINT SP3;
 Savepoint created.
 SQL> DELETE FROM CUSTOMERS WHERE ID=3;
 1 row deleted.

现在，三次删除操作已经生效了，如果此时你改变主意决定回滚至名字为 SP2 的保存点，由于 SP2 于第一次删除操作之后创建，所以后两次删除操作将会被撤销。

SQL> ROLLBACK TO SP2;
 Rollback complete.

注意，由于你将数据库回滚至 SP2，所以只有第一次删除真正起效了：

SQL> SELECT * FROM CUSTOMERS;
 +----+----------+-----+-----------+----------+
 | ID | NAME   | AGE | ADDRESS  | SALARY  |
 +----+----------+-----+-----------+----------+
 | 2 | Khilan  | 25 | Delhi   | 1500.00 |
 | 3 | kaushik | 23 | Kota   | 2000.00 |
 | 4 | Chaitali | 25 | Mumbai  | 6500.00 |
 | 5 | Hardik  | 27 | Bhopal  | 8500.00 |
 | 6 | Komal  | 22 | MP    | 4500.00 |
 | 7 | Muffy  | 24 | Indore  | 10000.00 |
 +----+----------+-----+-----------+----------+
   6 rows selected.

**RELEASE SAVEPOINT** **命令：**

RELEASE SAVEPOINT 命令用于删除先前创建的保存点。

RELEASE SAVEPOINT 的语法如下所示：

RELEASE SAVEPOINT SAVEPOINT_NAME;

保存点一旦被释放，你就不能够再用 ROLLBACK 命令来撤销该保存点之后的事务了。

**SET TRANSACTION** **命令：**

SET TRANSACTION 命令可以用来初始化数据库事务，指定随后的事务的各种特征。

例如，你可以将某个事务指定为只读或者读写。

SET TRANSACTION 命令的语法如下所示：

SET TRANSACTION [ READ WRITE | READ ONLY ];

**游标**

1、游标简介

SQL是一种集合操作语言，但有时候需要对单行操作怎么办呢？
 也就是有时候会过滤出不止一行的数据，但是想一行行的处理；
 
 ---游标
 
 
 游标：
   从集合中依次提取单条记录，直接提取完最后一条；
   类似于指针的作用；
   尽管游标能遍历结果中的所有行，但一次只指向一行；
 游标的适用场景：
   存储过程
   函数
   触发器
 游标的使用步骤：
  定义游标
   DECLARE 游标名称 CURSOR FOR SELECT子句;
  打开游标
   OPEN 游标名称
  使用游标
   FETCH 游标名称 INTO 变量名1,变量名2,变量名3[,…]
  关闭游标
   CLOSE 游标名称

2、游标使用的示例

\##配合存储过程使用
 
 CREATE PROCEDURE cursor_student()
 BEGIN
  DECLARE v_student_id varchar(50); 
  DECLARE v_student_name varchar(100); 
  DECLARE done INT DEFAULT false; 
 
  DECLARE mycursor CURSOR FOR SELECT student_id,student_name FROM student WHERE score >= 90;
  DECLARE CONTINUE HANDLER FOR NOT FOUND SET done = true;
 
  OPEN mycursor;
 
  FETCH mycursor INTO v_student_id,v_student_name; 
 
  WHILE(NOT done) 
  DO 
   SELECT v_student_id,v_student_name;
   FETCH mycursor INTO v_student_id,v_student_name; 
  END WHILE; 
 
  CLOSE mycursor;
 END;

3、游标的优缺点

优点：
   提供了一种除集合操作外的行操作方式；
 
 缺点：
   性能一般，数据量比较大的时候，还可能会造成内存不足；

**十、****SQL****的****having****语句**

HAVING 子句使你能够指定过滤条件，从而控制查询结果中哪些组可以出现在最终结果里面。

WHERE 子句对被选择的列施加条件，而 HAVING 子句则对 GROUP BY 子句所产生的组施加条件。

**语法：**

下面可以看到 HAVING 子句在 SELECT 查询中的位置：

SELECT
 FROM
 WHERE
 GROUP BY
 HAVING
 ORDER BY

在 SELECT 查询中，HAVING 子句必须紧随 GROUP BY 子句，并出现在 ORDER BY 子句（如果有的话）之前。带有 HAVING 子句的 SELECT 语句的语法如下所示：

SELECT column1, column2
 FROM table1, table2
 WHERE [ conditions ]
 GROUP BY column1, column2
 HAVING [ conditions ]
 ORDER BY column1, column2

**示例**：

考虑 CUSTOMERS 表，表中的记录如下所示：

+----+----------+-----+-----------+----------+
 | ID | NAME   | AGE | ADDRESS  | SALARY  |
 +----+----------+-----+-----------+----------+
 | 1 | Ramesh  | 32 | Ahmedabad | 2000.00 |
 | 2 | Khilan  | 25 | Delhi   | 1500.00 |
 | 3 | kaushik | 23 | Kota   | 2000.00 |
 | 4 | Chaitali | 25 | Mumbai  | 6500.00 |
 | 5 | Hardik  | 27 | Bhopal  | 8500.00 |
 | 6 | Komal  | 22 | MP    | 4500.00 |
 | 7 | Muffy  | 24 | Indore  | 10000.00 |
 +----+----------+-----+-----------+----------+

下面是一个有关 HAVING 子句使用的实例，该实例将会筛选出出现次数大于或等于 2 的所有记录。

SQL > SELECT ID, NAME, AGE, ADDRESS, SALARY
 FROM CUSTOMERS
 GROUP BY age
 HAVING COUNT(age) >= 2;

其执行结果如下所示：

+----+--------+-----+---------+---------+
 | ID | NAME  | AGE | ADDRESS | SALARY |
 +----+--------+-----+---------+---------+
 | 2 | Khilan | 25 | Delhi  | 1500.00 |
 +----+--------+-----+---------+---------+

**十一、****MYSQL****用户管理**

MySQL 是一个多用户数据库，具有功能强大的访问控制系统，可以为不同用户指定不同权限。在前面的章节中我们使用的是 root 用户，该用户是超级管理员，拥有所有权限，包括创建用户、删除用户和修改用户密码等管理权限。

**为了实际项目的需要，可以创建拥有不同权限的普通用户。**

通过本章的学习，读者可以了解到 MySQL 中的各种权限表、登录数据库的详细内容、用户管理和密码管理等。本章内容涉及到了数据库的安全，是数据库管理中非常重要的内容。

**1.MySQL user****权限表详解**

MySQL 在安装时会自动创建一个名为 mysql 的数据库，mysql 数据库中存储的都是用户权限表。用户登录以后，MySQL 会根据这些权限表的内容为每个用户赋予相应的权限。

user 表是 MySQL 中最重要的一个权限表，用来记录允许连接到服务器的账号信息。需要注意的是，在 user 表里启用的所有权限都是全局级的，适用于所有数据库。

user 表中的字段大致可以分为 4 类，分别是用户列、权限列、安全列和资源控制列，下面主要介绍这些字段的含义。

**用户列**

用户列存储了用户连接 MySQL 数据库时需要输入的信息。需要注意的是 MySQL 5.7 版本不再使用 Password 来作为密码的字段，而改成了 authentication_string。

MySQL 5.7 版本的用户列如表 1 所示。

| **字段名**            | **字段类型** | **是否为空** | **默认值** | **说明** |
| --------------------- | ------------ | ------------ | ---------- | -------- |
| Host                  | char(60)     | NO           | 无         | 主机名   |
| User                  | char(32)     | NO           | 无         | 用户名   |
| authentication_string | text         | YES          | 无         | 密码     |

用户登录时，如果这 3 个字段同时匹配，MySQL 数据库系统才会允许其登录。创建新用户时，也是设置这 3 个字段的值。修改用户密码时，实际就是修改 user 表的 authentication_string 字段的值。因此，这 3 个字段决定了用户能否登录。

**权限列**

权限列的字段决定了用户的权限，用来描述在全局范围内允许对数据和数据库进行的操作。

权限大致分为两大类，分别是高级管理权限和普通权限：

- 高级管理权限主要对数据库进行管理，例如关闭服务的权限、超级权限和加载用户等；
- 普通权限主要操作数据库，例如查询权限、修改权限等。

user 表的权限列包括 Select_priv、Insert_ priv 等以 priv 结尾的字段，这些字段值的数据类型为 ENUM，可取的值只有 Y 和 N：Y 表示该用户有对应的权限，N 表示该用户没有对应的权限。从安全角度考虑，这些字段的默认值都为 N。

| **字段名**             | **字段类型**  | **是否为空** | **默认值** | **说明**                                                     |
| ---------------------- | ------------- | ------------ | ---------- | ------------------------------------------------------------ |
| Select_priv            | enum('N','Y') | NO           | N          | 是否可以通过SELECT 命令查询数据                              |
| Insert_priv            | enum('N','Y') | NO           | N          | 是否可以通过 INSERT  命令插入数据                            |
| Update_priv            | enum('N','Y') | NO           | N          | 是否可以通过UPDATE 命令修改现有数据                          |
| Delete_priv            | enum('N','Y') | NO           | N          | 是否可以通过DELETE 命令删除现有数据                          |
| Create_priv            | enum('N','Y') | NO           | N          | 是否可以创建新的数据库和表                                   |
| Drop_priv              | enum('N','Y') | NO           | N          | 是否可以删除现有数据库和表                                   |
| Reload_priv            | enum('N','Y') | NO           | N          | 是否可以执行刷新和重新加载MySQL所用的各种内部缓存的特定命令，包括日志、权限、主机、查询和表 |
| Shutdown_priv          | enum('N','Y') | NO           | N          | 是否可以关闭MySQL服务器。将此权限提供给root账户之外的任何用户时，都应当非常谨慎 |
| Process_priv           | enum('N','Y') | NO           | N          | 是否可以通过SHOW PROCESSLIST命令查看其他用户的进程           |
| File_priv              | enum('N','Y') | NO           | N          | 是否可以执行SELECT  INTO OUTFILE和LOAD DATA INFILE命令       |
| Grant_priv             | enum('N','Y') | NO           | N          | 是否可以将自己的权限再授予其他用户                           |
| References_priv        | enum('N','Y') | NO           | N          | 是否可以创建外键约束                                         |
| Index_priv             | enum('N','Y') | NO           | N          | 是否可以对索引进行增删查                                     |
| Alter_priv             | enum('N','Y') | NO           | N          | 是否可以重命名和修改表结构                                   |
| Show_db_priv           | enum('N','Y') | NO           | N          | 是否可以查看服务器上所有数据库的名字，包括用户拥有足够访问权限的数据库 |
| Super_priv             | enum('N','Y') | NO           | N          | 是否可以执行某些强大的管理功能，例如通过KILL命令删除用户进程；使用SET GLOBAL命令修改全局MySQL变量，执行关于复制和日志的各种命令。（超级权限） |
| Create_tmp_table_priv  | enum('N','Y') | NO           | N          | 是否可以创建临时表                                           |
| Lock_tables_priv       | enum('N','Y') | NO           | N          | 是否可以使用LOCK  TABLES命令阻止对表的访问/修改              |
| Execute_priv           | enum('N','Y') | NO           | N          | 是否可以执行存储过程                                         |
| Repl_slave_priv        | enum('N','Y') | NO           | N          | 是否可以读取用于维护复制数据库环境的二进制日志文件           |
| Repl_client_priv       | enum('N','Y') | NO           | N          | 是否可以确定复制从服务器和主服务器的位置                     |
| Create_view_priv       | enum('N','Y') | NO           | N          | 是否可以创建视图                                             |
| Show_view_priv         | enum('N','Y') | NO           | N          | 是否可以查看视图                                             |
| Create_routine_priv    | enum('N','Y') | NO           | N          | 是否可以更改或放弃存储过程和函数                             |
| Alter_routine_priv     | enum('N','Y') | NO           | N          | 是否可以修改或删除存储函数及函数                             |
| Create_user_priv       | enum('N','Y') | NO           | N          | 是否可以执行CREATE  USER命令，这个命令用于创建新的MySQL账户  |
| Event_priv             | enum('N','Y') | NO           | N          | 是否可以创建、修改和删除事件                                 |
| Trigger_priv           | enum('N','Y') | NO           | N          | 是否可以创建和删除触发器                                     |
| Create_tablespace_priv | enum('N','Y') | NO           | N          | 是否可以创建表空间                                           |

如果要修改权限，可以使用 GRANT 语句为用户赋予一些权限，也可以通过 UPDATE 语句更新 user 表的方式来设置权限。

**安全列**

安全列主要用来判断用户是否能够登录成功，user 表中的安全列如表 3 所示：

| **字段名**            | **字段类型**                      | **是否为空** | **默认值**            | **说明**                                                     |
| --------------------- | --------------------------------- | ------------ | --------------------- | ------------------------------------------------------------ |
| ssl_type              | enum('','ANY','X509','SPECIFIED') | NO           |                       | 支持ssl标准加密安全字段                                      |
| ssl_cipher            | blob                              | NO           |                       | 支持ssl标准加密安全字段                                      |
| x509_issuer           | blob                              | NO           |                       | 支持x509标准字段                                             |
| x509_subject          | blob                              | NO           |                       | 支持x509标准字段                                             |
| plugin                | char(64)                          | NO           | mysql_native_password | 引入plugins以进行用户连接时的密码验证，plugin创建外部/代理用户 |
| password_expired      | enum('N','Y')                     | NO           | N                     | 密码是否过期 (N 未过期，y 已过期)                            |
| password_last_changed | timestamp                         | YES          |                       | 记录密码最近修改的时间                                       |
| password_lifetime     | smallint(5)  unsigned             | YES          |                       | 设置密码的有效时间，单位为天数                               |
| account_locked        | enum('N','Y')                     | NO           | N                     | 用户是否被锁定（Y 锁定，N 未锁定）                           |

注意：即使 password_expired 为“Y”，用户也可以使用密码登录 MySQL，但是不允许做任何操作。

通常标准的发行版不支持 ssl，读者可以使用 SHOW VARIABLES LIKE "have_openssl" 语句来查看是否具有 ssl 功能。如果 have_openssl 的值为 DISABLED，那么则不支持 ssl 加密功能。

**资源控制列**

资源控制列的字段用来限制用户使用的资源，user 表中的资源控制列如表 4 所示。

| **字段名**           | **字段类型**     | **是否为空** | **默认值** | **说明**                         |
| -------------------- | ---------------- | ------------ | ---------- | -------------------------------- |
| max_questions        | int(11) unsigned | NO           | 0          | 规定每小时允许执行查询的操作次数 |
| max_updates          | int(11) unsigned | NO           | 0          | 规定每小时允许执行更新的操作次数 |
| max_connections      | int(11) unsigned | NO           | 0          | 规定每小时允许执行的连接操作次数 |
| max_user_connections | int(11) unsigned | NO           | 0          | 规定允许同时建立的连接次数       |

以上字段的默认值为 0，表示没有限制。一个小时内用户查询或者连接数量超过资源控制限制，用户将被锁定，直到下一个小时才可以在此执行对应的操作。可以使用 GRANT 语句更新这些字段的值。

**2.MYSQL****其他权限表**

**db****表**

db 表比较常用，是 MySQL 数据库中非常重要的权限表，表中存储了用户对某个数据库的操作权限。表中的字段大致可以分为两类，分别是用户列和权限列。

**用户列**

db 表用户列有 3 个字段，分别是 Host、User、Db，标识从某个主机连接某个用户对某个数据库的操作权限，这 3 个字段的组合构成了 db 表的主键。

db 表的用户列如下表所示：

| **字段名** | **字段类型** | **是否为空** | **默认值** | **说明** |
| ---------- | ------------ | ------------ | ---------- | -------- |
| Host       | char(60)     | NO           | 无         | 主机名   |
| Db         | char(64)     | NO           | 无         | 数据库名 |
| User       | char(32)     | NO           | 无         | 用户名   |

权限列

db 表中的权限列和 user 表中的权限列大致相同，只是user 表中的权限是针对所有数据库的，而 db 表中的权限只针对指定的数据库。如果希望用户只对某个数据库有操作权限，可以先将 user 表中对应的权限设置为 N，然后在 db 表中设置对应数据库的操作权限。

**tables_priv****表和****columns_priv****表**

tables_priv 表用来对单个表进行权限设置，columns_priv 表用来对单个数据列进行权限设置。tables_priv 表结构如下表所示：

| **字段名**  | **字段类型**                                                 | **是否为空** | **默认值**        | **说明**                                                     |
| ----------- | ------------------------------------------------------------ | ------------ | ----------------- | ------------------------------------------------------------ |
| Host        | char(60)                                                     | NO           | 无                | 主机                                                         |
| Db          | char(64)                                                     | NO           | 无                | 数据库名                                                     |
| User        | char(32)                                                     | NO           | 无                | 用户名                                                       |
| Table_name  | char(64)                                                     | NO           | 无                | 表名                                                         |
| Grantor     | char(93)                                                     | NO           | 无                | 修改该记录的用户                                             |
| Timestamp   | timestamp                                                    | NO           | CURRENT_TIMESTAMP | 修改该记录的时间                                             |
| Table_priv  | set('Select','Insert','Update','Delete',' Create','Drop','Grant','References',  'Index','Alter','Create View','Show view','Trigger') | NO           | 无                | 表示对表的操作权限，包括 Select、Insert、Update、Delete、Create、Drop、Grant、References、Index 和 Alter 等 |
| Column_priv | set('Select','Insert','Update','References')                 | NO           | 无                | 表示对表中的列的操作权限，包括 Select、Insert、Update  和 References |

columns_priv 表结构如下表所示：

| **字段名**  | **字段类型**                                 | **是否为空** | **默认值**        | **说明**                                                     |
| ----------- | -------------------------------------------- | ------------ | ----------------- | ------------------------------------------------------------ |
| Host        | char(60)                                     | NO           | 无                | 主机                                                         |
| Db          | char(64)                                     | NO           | 无                | 数据库名                                                     |
| User        | char(32)                                     | NO           | 无                | 用户名                                                       |
| Table_name  | char(64)                                     | NO           | 无                | 表名                                                         |
| Column_name | char(64)                                     | NO           | 无                | 数据列名称，用来指定对哪些数据列具有操作权限                 |
| Timestamp   | timestamp                                    | NO           | CURRENT_TIMESTAMP | 修改该记录的时间                                             |
| Column_priv | set('Select','Insert','Update','References') | NO           | 无                | 表示对表中的列的操作权限，包括 Select、Insert、Update 和 References |

**procs_priv****表**

procs_priv 表可以对存储过程和存储函数进行权限设置，procs_priv 的表结构如表所示：

| **字段名**   | **字段类型**                           | **是否为空** | **默认值**        | **说明**                                                     |
| ------------ | -------------------------------------- | ------------ | ----------------- | ------------------------------------------------------------ |
| Host         | char(60)                               | NO           | 无                | 主机名                                                       |
| Db           | char(64)                               | NO           | 无                | 数据库名                                                     |
| User         | char(32)                               | NO           | 无                | 用户名                                                       |
| Routine_name | char(64)                               | NO           | 无                | 表示存储过程或函数的名称                                     |
| Routine_type | enum('FUNCTION','PROCEDURE')           | NO           | 无                | 表示存储过程或函数的类型，Routine_type 字段有两个值，分别是 FUNCTION 和 PROCEDURE。FUNCTION 表示这是一个函数；PROCEDURE 表示这是一个 存储过程。 |
| Grantor      | char(93)                               | NO           | 无                | 插入或修改该记录的用户                                       |
| Proc_priv    | set('Execute','Alter Routine','Grant') | NO           | 无                | 表示拥有的权限，包括 Execute、Alter  Routine、Grant 3种      |
| Timestamp    | timestamp                              | NO           | CURRENT_TIMESTAMP | 表示记录更新时间                                             |

**3.MySQL****创建用户（****3****种方式）**

MySQL 在安装时，会默认创建一个名为 root 的用户，该用户拥有超级权限，可以控制整个 MySQL 服务器。

在对 MySQL 的日常管理和操作中，为了避免有人恶意使用 root 用户控制数据库，我们通常创建一些具有适当权限的用户，尽可能地不用或少用 root 用户登录系统，以此来确保数据的安全访问。

MySQL 提供了以下 3 种方法创建用户。

1. 使用 CREATE USER 语句创建用户
2. 在 mysql.user 表中添加用户
3. 使用 GRANT 语句创建用户

下面根据实例详细讲解这 3 种方法。

**1.** **使用****CREATE USER****语句创建用户**

可以使用 **CREATE USER** 语句来创建 MySQL 用户，并设置相应的密码。其基本语法格式如下：

CREATE USER <用户> [ IDENTIFIED BY [ PASSWORD ] 'password' ] [ ,用户 [ IDENTIFIED BY [ PASSWORD ] 'password' ]]

参数说明如下：

**1)** **用户**

指定创建用户账号，格式为 user_name'@'host_name。这里的user_name是用户名，host_name为主机名，即用户连接 MySQL 时所用主机的名字。如果在创建的过程中，只给出了用户名，而没指定主机名，那么主机名默认为“%”，表示一组主机，即对所有主机开放权限。

**2) IDENTIFIED BY****子句**

用于指定用户密码。新用户可以没有初始密码，若该用户不设密码，可省略此子句。

**3) PASSWORD 'password'**

PASSWORD 表示使用哈希值设置密码，该参数可选。如果密码是一个普通的字符串，则不需要使用 PASSWORD 关键字。'password' 表示用户登录时使用的密码，需要用单引号括起来。

使用 CREATE USER 语句时应注意以下几点：

- CREATE USER 语句可以不指定初始密码。但是从安全的角度来说，不推荐这种做法。
- 使用 CREATE USER 语句必须拥有 mysql 数据库的 INSERT 权限或全局 CREATE USER 权限。
- 使用 CREATE USER 语句创建一个用户后，MySQL 会在 mysql 数据库的 user 表中添加一条新记录。
- CREATE USER 语句可以同时创建多个用户，多个用户用逗号隔开。

新创建的用户拥有的权限很少，它们只能执行不需要权限的操作。如登录 MySQL、使用 SHOW 语句查询所有存储引擎和字符集的列表等。如果两个用户的用户名相同，但主机名不同，MySQL 会将它们视为两个用户，并允许为这两个用户分配不同的权限集合。

**例** **1**

使用 CREATE USER 创建一个用户，用户名是 test1，密码是 test1，主机名是 localhost。SQL 语句和执行过程如下。

mysql> CREATE USER 'test1'@'localhost' IDENTIFIED BY 'test1';
 Query OK, 1 rows affected (0.06 sec)

结果显示，创建 test1 用户成功。

在实际应用中，我们应避免明文指定密码，可以通过 PASSWORD 关键字使用密码的哈希值设置密码。

**例** **2**

在 MySQL 中，可以使用 password() 函数获取密码的哈希值，查看 test1 哈希值的 SQL 语句和执行过程如下：

mysql> SELECT password('test1');
 +-------------------------------------------+
 | password('test1')             |
 +-------------------------------------------+
 | *06C0BF5B64ECE2F648B5F048A71903906BA08E5C |
 +-------------------------------------------+
 1 row in set, 1 warning (0.00 sec)

“*06C0BF5B64ECE2F648B5F048A71903906BA08E5C”就是 test1 的哈希值。下面创建用户 test1，SQL 语句和执行过程如下：

mysql> CREATE USER 'test1'@'localhost'IDENTIFIED BY PASSWORD '*06C0BF5B64ECE2F648B5F048A71903906BA08E5C';
 Query OK, 0 rows affected, 1 warning (0.00 sec)

执行成功后就可以使用密码“test1”登录了。

**2.** **使用** **INSERT** **语句新建用户**

可以使用 INSERT 语句将用户的信息添加到 mysql.user 表中，但必须拥有对 mysql.user 表的 INSERT 权限。通常 INSERT 语句只添加 Host、User 和 authentication_string 这 3 个字段的值。

MySQL 5.7 的 user 表中的密码字段从 Password 变成了 authentication_string，如果你使用的是 MySQL 5.7 之前的版本，将 authentication_string 字段替换成 Password 即可。

使用 **INSERT** 语句创建用户的代码如下：

INSERT INTO mysql.user(Host, User, authentication_string, ssl_cipher, x509_issuer, x509_subject) VALUES ('hostname', 'username', PASSWORD('password'), '', '', '');

由于 mysql 数据库的 user 表中，ssl_cipher、x509_issuer 和 x509_subject 这 3 个字段没有默认值，所以向 user 表插入新记录时，一定要设置这 3 个字段的值，否则 INSERT 语句将不能执行。

**例** **3**

下面使用 INSERT 语句创建名为 test2 的用户，主机名是 localhost，密码也是 test2。SQL 语句和执行过程如下：

mysql> INSERT INTO mysql.user(Host, User, authentication_string, ssl_cipher, x509_issuer, x509_subject) VALUES ('localhost', 'test2', PASSWORD('test2'), '', '', '');
 Query OK, 1 row affected, 1 warning (0.02 sec)

结果显示，新建用户成功。但是这时如果通过该账户登录 MySQL 服务器，不会登录成功，因为 test2 用户还没有生效。

可以使用 FLUSH 命令让用户生效，命令如下：

FLUSH PRIVILEGES;

使用以上命令可以让 MySQL 刷新系统权限相关表。执行 FLUSH 命令需要 RELOAD 权限。

注意：user 表中的 User 和 Host 字段区分大小写，创建用户时要指定正确的用户名称或主机名。

**3.** **使用****GRANT****语句新建用户**

虽然 CREATE USER 和 INSERT INTO 语句都可以创建普通用户，但是这两种方式不便授予用户权限。于是 MySQL 提供了 GRANT 语句。

使用 **GRANT** 语句创建用户的基本语法形式如下:

GRANT priv_type ON database.table TO user [IDENTIFIED BY [PASSWORD] 'password']

其中：

- priv_type 参数表示新用户的权限；
- database.table 参数表示新用户的权限范围，即只能在指定的数据库和表上使用自己的权限；
- user 参数指定新用户的账号，由用户名和主机名构成；
- IDENTIFIED BY 关键字用来设置密码；
- password 参数表示新用户的密码。

**例** **4**

下面使用 GRANT 语句创建名为 test3 的用户，主机名为 localhost，密码为 test3。该用户对所有数据库的所有表都有 SELECT 权限。SQL 语句和执行过程如下：

mysql> GRANT SELECT ON*.* TO 'test3'@localhost IDENTIFIED BY 'test3';
 Query OK, 0 rows affected, 1 warning (0.01 sec)

其中，“*.*” 表示所有数据库下的所有表。结果显示创建用户成功，且 test3 用户对所有表都有查询（SELECT）权限。

技巧：GRANT 语句是 MySQL 中一个非常重要的语句，它可以用来创建用户、修改用户密码和设置用户权限。教程后面会详细介绍如何使用 GRANT 语句修改密码、更改权限。

**4.MySQL****修改用户（****RENAME USER****）**

在 [MySQL](http://c.biancheng.net/mysql/) 中，我们可以使用 **RENAME USER** 语句修改一个或多个已经存在的用户账号。

语法格式如下：

RENAME USER <旧用户> TO <新用户>

其中：

- <旧用户>：系统中已经存在的 MySQL 用户账号。
- <新用户>：新的 MySQL 用户账号。

使用 RENAME USER 语句时应注意以下几点：

- RENAME USER 语句用于对原有的 MySQL 用户进行重命名。
- 若系统中旧账户不存在或者新账户已存在，该语句执行时会出现错误。
- 使用 RENAME USER 语句，必须拥有 mysql 数据库的 UPDATE 权限或全局 CREATE USER 权限。

**例** **1**

使用 RENAME USER 语句将用户名 test1 修改为 testUser1，主机是 localhost。SQL 语句和执行过程如下。

mysql> RENAME USER 'test1'@'localhost'
   -> TO 'testUser1'@'localhost';
 Query OK, 0 rows affected (0.03 sec)

在 cmd 命令行工具中，使用 testUser1 用户登录数据库服务器，如下所示。

C:\Users\USER>mysql -h localhost -u testUser1 -p
 Enter password: *****
 Welcome to the MySQL monitor. Commands end with ; or \g.
 Your MySQL connection id is 7
 Server version: 5.7.20-log MySQL Community Server (GPL)
 Copyright (c) 2000, 2017, Oracle and/or its affiliates. All rights reserved.
 Oracle is a registered trademark of Oracle Corporation and/or its
 affiliates. Other names may be trademarks of their respective
 owners.
 Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

**十二、数据库三大模式**

![img](https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fp.ananas.chaoxing.com%2Fstar3%2Forigin%2F5503039f53706e35b9f30b9e.jpg&refer=http%3A%2F%2Fp.ananas.chaoxing.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=auto?sec=1654779905&t=844b4b74126f1031db989c2e205379d3)

人们为数据库设计了一个严谨的体系结构，数据库领域公认的标准结构是三级模式结构，它包括外模式、概念模式、内模式，有效地组织、管理数据，提高了数据库的逻辑独立性和物理独立性。用户级对应外模式，概念级对应概念模式，物理级对应内模式，使不同级别的用户对数据库形成不同的视图。所谓视图，就是指观察、认识和理解数据的范围、角度和方法，是数据库在用户“眼中"的反映，很显然，不同层次（级别）用户所“看到”的数据库是不相同的。

**外模式** 外模式又称子模式或**用户模式**，对应于**用户级**。它是某个或某几个用户所看到的数据库的数据视图，是与某一应用有关的数据的逻辑表示。外模式是从模式导出的一个子集，包含模式中允许特定用户使用的那部分数据。用户可以通过外模式描述语言来描述、定义对应于用户的数据记录(外模式)，也可以利用数据操纵语言(Data Manipulation Language，DML)对这些数据记录进行操作。外模式反映了数据库系统的用户观。

**概念模式** 概念模式又称模式或**逻辑模式**，对应于**概念级**。它是由数据库设计者综合所有用户的数据，按照统一的观点构造的全局逻辑结构，是对数据库中全部数据的逻辑结构和特征的总体描述，是所有用户的公共数据视图(全局视图)。它是由数据库管理系统提供的数据模式描述语言(Data Description Language，DDL)来描述、定义的。概念模式反映了数据库系统的整体观。

**内模式** 内模式又称**存储模式**，对应于**物理级**。它是数据库中全体数据的内部表示或底层描述，是数据库最低一级的逻辑描述，它描述了数据在存储介质上的存储方式和物理结构，对应着实际存储在外存储介质上的数据库。内模式由内模式描述语言来描述、定义的。内模式反映了数据库系统的存储观。 在一个数据库系统中，只有唯一的数据库， 因而作为定义 、描述数据库存储结构的内模式和定义、描述数据库逻辑结构的模式，也是唯一的，但建立在数据库系统之上的应用则是非常广泛、多样的，所以对应的外模式不是唯一的，也不可能是唯一的。

 