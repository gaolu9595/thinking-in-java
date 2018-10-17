
## SSM框架及Redis入门🎶🎶🎶

### Spring

 

 - IoC：控制反转（Inversion of Control）
 【IoC是一个容器，根据配置文件来管理JavaBean及其依赖关系】
 【如果想要一个对象(资源)，不再需要先new它，而只需要描述它，IoC将根据描述提供所需资源】
 - AOP： 面向切面编程（Aspect Oriented Programming）
 【常用于数据库事务。默认情况下，只要让Spring接受到异常消息，就能让数据库事务回滚，保持数据的一致性】


### MyBatis：是一个持久层框架
**Hibernate**：通过映射关系来将数据库表和POJO对应起来，完全消除了SQL语句，而只需要操作POJO来操作对应的数据库表（但是存在性能瓶颈）
**MyBatis**：与Hibernate业务逻辑基本一致，也是将数据库表映射为POJO，但是它需要**接口和SQL**（没有屏蔽SQL，可以自己制定SQL规则，更能满足高并发高响应的性能需求）
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTE0OTg4NTAxLDE1NzYwNzg0NDUsMzAyOT
QwNjYzXX0=
-->