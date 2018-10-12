## Java编程基础😁

### 😉相关概念
JDK: Java Development Kit (包含JRE，同时包括client和server端的)
JRE: Java Runtime Enviorment (只包含client运行环境下的JVM：jre/bin/client/jvm.dll)
IDE: Integrated Development Enviorment (e.g. Eclipse)
问题空间（一项业务）<=============>   解空间（计算机）

### 😍Object-oriented Programming）OOP基本思想
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
9. 🔥 **继承** 🔥（is-a和is-like-a关系）与**组合**
10. ❓❓❓ ***多态** [在OOP中编译器无法产生传统意义上的函数调用，即“前期绑定”，Java缺省使用动态的“后期绑定”]--------向上转型upcasting* ❓❓❓
11. 所有的类最终都继承于Object类（单根继承结构）
12. 🔥 **容器** 🔥（e.g. C++的STL等；Java提供的诸多类似List/Map/Set等的容器，以及队列/树/堆栈等多种构件）【只需要创建一个容器对象，让它处理所有细节，而不需要管将来会将多少个对象置于容器中】
13. 范型：创建一个容器并让它知道自己保存的对象的具体类型（非Object类型），避免向下转型的不安全性
14. 🔥 **对象的创建与生命周期** 🔥：Java采用完全动态内存分配的方式，只能在堆上new一个对象，并且采用垃圾回收器机制（注：内存池---->堆）
15. **异常处理**与**并发编程**
16. C/S模式

| 客户端 | 服务器端 | 前端开发(界面) |
|--|--|--|
| 安卓/IOS/PC开发/浏览器(JS,Applet) | Web服务器，Servlet及JSP | HTML/CSS |


###  📝Java程序设计
1. 数据**存储**到什么地方：寄存器(处理器内部)、堆栈、堆(memory pool，所有Java对象)、常量存储(程序内部)、非RAM存储(e.g.持久化对象和流对象)
2. Java**基本数据类型**[强类型语言]：
| boolean | char | byte | short | int | long | float | double | void |
3. **类(class)**：程序员定义的新数据类型【字段+方法】
4. **static**修饰的方法和字段是不依赖于类的对象而存在的，可以直接通过类名来访问
5. **类变量能被Java自动初始化**，而方法中的局部变量则不能，需要程序员手动初始化
6. 🔥 **“==”和“equals()”的区别** 🔥：前者比较的是基本数据类型的数值和引用类型的“对象地址”；后者不能用来比较基本数据类型，而在一些引用类型（未重写equals时）中比较“对象地址”，在另一些（重写了equals时，如String，Date，包装器类型）中比较对象的值。
7. 基本类型存储的是实际的数值，而并非指向一个对象的引用；而引用类型则不是这样（易出现“  *别名现象*  ”）
8. a++和a--：先赋值再计算； ++a和--a：先计算再赋值
9. 使用逻辑



> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbNjYwMzM3Mjc1LC00MzU0ODM4MTQsMjAyOT
czODU4MiwtMjAxNDYyMzc2OCw1NzA0OTI0NjIsLTEzMTc3NzA2
OTUsMTM2MDUyNTcsLTc2Mzg3MDA4NSwtMzczNjU3MjEzLDQ1Nj
kxMzkxOCwtNjMxMjY2NTA4LC0xMzgxMTc1MjMxLDEzODQ3OTE3
MTEsLTE3MzkxODg4NDMsLTEyNjA4MjQ0NDcsLTc3Nzc3Mzg1NS
w3NTc2MTc5NDEsLTE3MDQ2NzE1MTYsMTM3OTU2NDczMSwtMTMy
MjMwMTQwN119
-->