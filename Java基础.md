## Java程序设计基础

### 相关概念
JDK: Java Development Kit (包含JRE，同时包括client和server端的)
JRE: Java Runtime Enviorment (只包含client运行环境下的JVM：jre/bin/client/jvm.dll)
IDE: Integrated Development Enviorment (e.g. Eclipse)
问题空间（一项业务）<=============>解空间（计算机）

### OOP基本思想
1. 万物皆为对象
2. 程序是对象的集合
3. 每个对象都有自己的由其他对象所构成的存储
4. 每个对象都有其类型（class），某一特定类型的所有对象都可以接收相同的消息
5. 示例：创建了一个Student类型的对象，定义了该对象的引用s，同时对s发送getAge消息请求。 
    Student s = new Student();
    s.getAge()   
 6. 每个对象都提供服务，程序应该被理解：通过调用其他对象提供的服务，来为用户提供服务
 7. 良好的OOP中，每个对象都可以很好的完成一项任务，但是它并不试图做更多的事
 8. 类创建者对类消费者（客户端程序员）隐藏具体实现，只暴露必需的部分【访问控制能便于维护+减轻开发任务，Java用关键字public、private、protected来设定类的边界，Java还设置了*****包访问权限*****】





> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTQ1NTA3MDA3NiwtODMwNTQxMzU1LDQxOD
g0NjgzNSwxNzE1ODI0NDkxLC0xNjEyNDg1MTkwLDE1NzcwNzg1
NDEsLTE3OTgyNTk4NzQsNzMzMTk3Mzk1LC04MjExOTc5ODAsLT
EyMjY1Mjk5ODNdfQ==
-->