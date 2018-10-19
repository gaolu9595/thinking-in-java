## MyBatis持久层框架

<font color=#0099ff face="楷体">**Java应用可以通过MyBatis框架访问数据库**</font>
<font color=#0099ff face="楷体">**POJO**：Plain Ordinary Java Object（简单Java对象），特指与数据库打交道的Java对象</font>
<font color=#0099ff face="楷体">**对MyBatis的理解**：
</font>

**MyBatis核心组件**

**SqlSessionFactoryBuilder**：按照Builder模式来生成SqlSessionFactory。创建完SqlSessionFactory就应该关闭。

**SqlSessionFactory**：相当于对数据库的Connection池，用于生成MyBatis的核心接口对象SqlSession【*通常是单例模式*】。SqlSessionFactory 的生命周期就**等同于 MyBatis 的应用周期**。

**SqlSession**：相当于一个Connection对象，有DefaultSqlSession（单线程）和SqlSessionManager（多线程）两个实现类。它应该**存活在一个业务请求中**，处理完整个请求后，应该关闭这条连接，让它归还给 SqlSessionFactory。

**SQLMapper**：两种实现映射器的方式（XML与注解）。它的生命周期应该小于等于 SqlSession 的生命周期，代表一个业务请求中的业务处理

【SQLSession和SqlMapper都可以发送SQL语句，后者更符合面向对象编程的语法规则】
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQwODcyMDI3NSwtODc5Mjg1ODM4LDEzMT
A3ODc4MzUsLTE0OTIzNTAxNjYsMTQ5MzMwMTkzMCwtMTAzNjg0
NTUyOSwxNTM3MTIxNzY1LDEzOTEyNzQyODFdfQ==
-->