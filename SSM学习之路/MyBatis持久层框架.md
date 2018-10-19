## MyBatis持久层框架

<font color=#0099ff face="楷体">**Java应用可以通过MyBatis框架访问数据库**</font>
<font color=#0099ff face="楷体">**POJO**：Plain Ordinary Java Object（简单Java对象），特指与数据库打交道的Java对象</font>


**MyBatis核心组件**

SqlSessionFactoryBuilder：按照Builder模式来生成SQLSessionFactory。创建完

SqlSessionFactory：生成MyBatis的核心接口对象SqlSession【通常是单例模式】

SqlSession：有DefaultSqlSession（单线程）和SqlSessionManager（多线程）两个实现类

SQLMapper：两种实现映射器的方式（XML与注解）

【SQLSession和SqlMapper都可以发送SQL语句，推荐后者】
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY3MjQwNzE3LC0xNDkyMzUwMTY2LDE0OT
MzMDE5MzAsLTEwMzY4NDU1MjksMTUzNzEyMTc2NSwxMzkxMjc0
MjgxXX0=
-->