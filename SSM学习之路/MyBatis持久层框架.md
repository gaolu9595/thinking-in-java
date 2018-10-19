## MyBatis持久层框架

<font color=#0099ff face="楷体">**Java应用可以通过MyBatis框架访问数据库**</font>
<font color=#0099ff face="楷体">**POJO**：Plain Ordinary Java Object（简单Java对象），特指与数据库打交道的Java对象</font>
<font color=#0099ff face="楷体">**对MyBatis的理解**：MyBatis是一个持久层框架，用于Java应用访问数据库。先将对数据库表（POJO类）的操作与SQL语言映射起来（XML或注解实现），然后用面向对象的编程方式（操作Mapper接口）来操作数据库完成事务。使用制造者模式创建（通过mybati-config.xml）一个单例的session工厂，再运用工厂模式来创建一个个session完成事务请求。MyBatis相比较Hibernate而言更加灵活高效，因为它不屏蔽SQL语句，并且支持动态SQL。
</font>

### <font color=#0000ff >**MyBatis核心组件（必须厘清思路）**</font>

**SqlSessionFactoryBuilder**：按照Builder模式来生成SqlSessionFactory。创建完SqlSessionFactory就应该关闭。

**SqlSessionFactory**：相当于对数据库的Connection池，用于生成MyBatis的核心接口对象SqlSession【*通常是单例模式*】。SqlSessionFactory 的生命周期就**等同于 MyBatis 的应用周期**。

**SqlSession**：相当于一个Connection对象，有DefaultSqlSession（单线程）和SqlSessionManager（多线程）两个实现类。它应该**存活在一个业务请求中**，处理完整个请求后，应该关闭这条连接，让它归还给 SqlSessionFactory。

**SQLMapper**：两种实现映射器的方式（XML与注解）。它的生命周期应该小于等于 SqlSession 的生命周期，代表一个业务请求中的业务处理

【SQLSession和SqlMapper都可以发送SQL语句，后者更符合面向对象编程的语法规则】

### <font color=#0000ff >**MyBatis配置config**</font>

**MyBatis的配置项顺序不能颠倒**


### <font color=#0000ff >**MyBatis映射器mapper（Mybatis最复杂的部分）**</font>

映射器由一个**接口**和**XML文件**组成（或注解），通过操作接口对象来完成数据库事务

映射器的配置元素：
| 配置元素|  |
|--|--|
| select |  |
| insert |  |
| delete |  |
| update |  |
| sql | 定义Sql语句的一部分，以供重复使用 |
| cache | 开启SqlSessionFactory层面的二级缓存，搭配实现了java.io.Serializable接口的POJO对象 |
| cache-ref | 引用其他映射器的缓存设置 |
| resultMap | 复杂[用于级联] |

MyBatis级联：鉴别器、一对多、一对一
（看得很晕。。。标记一下）

MyBatis缓存（支持一级缓存和二级缓存）


### <font color=#0000ff >**动态SQL**</font>


| 元素 | 作用 | 备注 |
|--|--|--|
| if | 判断语句 | 单条件分支判断   |
| choose (when, otherwise)  | 相当于 Java 中的 switch 和 case 语句 | 多条件分支判断【if-elif-else】   |
| trim {where, set)  | 辅助元素，用于处理特定的SQL拼装问题，比如去掉多余的and/or等 | 用于处理SQL拼装的问题   |
| foreach | 循环语句  | 在in语句等列举条件常用 |
| test | 判断真假| 可以做字符串或数值判断，和if通常连用 |
| bind | 循环语句  | 在 i n 语句等列举条件常用 |


<!--stackedit_data:
eyJoaXN0b3J5IjpbODczMTc1NzE4LDExNDg3MzYxMjQsMjQ1Nz
Y3MDAxLDE3MzMyMTI1NTUsMTkwNzIyNzUzMiwyMTU3NzA2MTIs
NDk0NzkxMTg1LC0xMTI2MDg1MTAyLC0xMDY4MTgxNTQ1LDEyMz
E0MTE3MjQsNDgwOTY2MDUwLDE0MTQ5MTM5NzcsLTEzODI3MTM3
NjcsLTE0Mzg0Mjg5NywtNDA4NzIwMjc1LC04NzkyODU4MzgsMT
MxMDc4NzgzNSwtMTQ5MjM1MDE2NiwxNDkzMzAxOTMwLC0xMDM2
ODQ1NTI5XX0=
-->