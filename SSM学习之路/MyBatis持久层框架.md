## MyBatis持久层框架

<font color=#0099ff face="楷体">**Java应用可以通过MyBatis框架访问数据库**</font>
<font color=#0099ff face="楷体">**POJO**：Plain Ordinary Java Object（简单Java对象），特指与数据库打交道的Java对象</font>
<font color=#0099ff face="楷体">**对MyBatis的理解**：MyBatis是一个持久层框架，用于Java应用访问数据库。先将对数据库表的操作与SQL语言映射起来，然后用面向对象的编程方式来操作数据库完成事务。使用制造者模式创建一个单例的session工厂，再运用工厂模式来创建一个个session完成事务请求。MyBatis相比较Hibernate而言更加灵活高效，因为它不屏蔽SQL语句。
</font>

### <font color=#0000ff >**MyBatis核心组件**</font>

**SqlSessionFactoryBuilder**：按照Builder模式来生成SqlSessionFactory。创建完SqlSessionFactory就应该关闭。

**SqlSessionFactory**：相当于对数据库的Connection池，用于生成MyBatis的核心接口对象SqlSession【*通常是单例模式*】。SqlSessionFactory 的生命周期就**等同于 MyBatis 的应用周期**。

**SqlSession**：相当于一个Connection对象，有DefaultSqlSession（单线程）和SqlSessionManager（多线程）两个实现类。它应该**存活在一个业务请求中**，处理完整个请求后，应该关闭这条连接，让它归还给 SqlSessionFactory。

**SQLMapper**：两种实现映射器的方式（XML与注解）。它的生命周期应该小于等于 SqlSession 的生命周期，代表一个业务请求中的业务处理

【SQLSession和SqlMapper都可以发送SQL语句，后者更符合面向对象编程的语法规则】

### <font color=#0000ff >**MyBatis配置**</font>

**MyBatis的配置项顺序不能颠倒**


### <font color=#0000ff >**MyBatis映射器**</font>

映射器由一个**接口**和**XML文件**组成（或注解）

映射器的配置元素：
| 配置元素|  |
|--|--|
| select |  |
| insert |  |
| delete |  |
| update |  |
| sql |  |
| cache |  |
| cache-ref |  |
| resultMap | 复杂 |

MyBatis级联：鉴别器、一对多、一对一
（）
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU5Njc0ODc2NywtMTEyNjA4NTEwMiwtMT
A2ODE4MTU0NSwxMjMxNDExNzI0LDQ4MDk2NjA1MCwxNDE0OTEz
OTc3LC0xMzgyNzEzNzY3LC0xNDM4NDI4OTcsLTQwODcyMDI3NS
wtODc5Mjg1ODM4LDEzMTA3ODc4MzUsLTE0OTIzNTAxNjYsMTQ5
MzMwMTkzMCwtMTAzNjg0NTUyOSwxNTM3MTIxNzY1LDEzOTEyNz
QyODFdfQ==
-->