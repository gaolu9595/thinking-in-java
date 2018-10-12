## Java程序设计基础😁

### 相关概念
JDK: Java Development Kit (包含JRE，同时包括client和server端的)
JRE: Java Runtime Enviorment (只包含client运行环境下的JVM：jre/bin/client/jvm.dll)
IDE: Integrated Development Enviorment (e.g. Eclipse)
问题空间（一项业务）<=============>   解空间（计算机）

### （Object-oriented Programming）OOP基本思想
1. 👌**万物皆为对象**👌
2. 程序是对象的集合
3. 每个对象都有自己的由其他对象所构成的存储
4. 每个对象都有其类型（class），某一特定类型的所有对象都可以接收相同的消息
5. ***示例***：创建了一个Student类型的对象，定义了该对象的引用s，同时对s发送getAge消息请求。 
    Student s = new Student();
    s.getAge()   
6. 每个对象都提供服务，程序应该被理解：通过调用其他对象提供的服务，来为用户提供服务
7. 良好的OOP中，每个对象都可以很好的完成一项任务，但是它并不试图做更多的事
8. 类创建者对类消费者（客户端程序员）隐藏具体实现，只暴露必需的部分【访问控制能便于维护+减轻开发任务，Java用关键字public、private、protected来设定*****类的边界*****，Java还设置了*****包访问权限*****】
9. 🔥**继承**🔥（is-a和is-like-a关系）与**组合**
10. ❓❓❓***多态** [在OOP中编译器无法产生传统意义上的函数调用，即“前期绑定”，Java缺省使用动态的“后期绑定”]--------向上转型upcasting*❓❓❓
11. 所有的类最终都继承于Object类（单根继承结构）
12. 🔥**容器**🔥（e.g. C++的STL等；Java提供的诸多类似List/Map/Set等的容器，以及队列/树/堆栈等多种构件）【只需要创建一个容器对象，让它处理所有细节，而不需要管将来会将多少个对象置于容器中】
13. 




> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM3OTU2NDczMSwtMTMyMjMwMTQwNyw1Mz
MyNDY1NzMsLTg3NzcwNTEyOSw1MDAyNzI4NjcsLTk3NDM5ODI0
OCwtNDQ0MDMwNzg4LDgyNTgxMjM0MywxMDE2OTAzMzM1LC04Mz
A1NDEzNTUsNDE4ODQ2ODM1LDE3MTU4MjQ0OTEsLTE2MTI0ODUx
OTAsMTU3NzA3ODU0MSwtMTc5ODI1OTg3NCw3MzMxOTczOTUsLT
gyMTE5Nzk4MCwtMTIyNjUyOTk4M119
-->