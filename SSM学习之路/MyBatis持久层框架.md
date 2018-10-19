## MyBatis持久层框架

<font color=#0099ff face="楷体">**Java应用可以通过MyBatis框架访问数据库**</font>
<font color=#0099ff face="楷体">POJO：Plain Ordinary Java Object </font>


**MyBatis核心组件**

SqlSessionFactoryBuilder：按照Builder模式来生成SQLSessionFactory

SqlSessionFactory：生成MyBatis的核心接口对象SqlSession【通常是单例模式】

SqlSession：有DefaultSqlSession（单线程）和SqlSessionManager（多线程）两个实现类

SQLMapper：

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjM2MTkwNjU1LC0xMDM2ODQ1NTI5LDE1Mz
cxMjE3NjUsMTM5MTI3NDI4MV19
-->