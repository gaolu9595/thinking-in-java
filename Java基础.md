## Java编程基础😁

### 😉相关概念
JDK: Java Development Kit (包含JRE，同时包括client和server端的)
JRE: Java Runtime Enviorment (只包含client运行环境下的JVM：jre/bin/client/jvm.dll)
IDE: Integrated Development Enviorment (e.g. Eclipse)
问题空间（一项业务）<=============>   解空间（计算机）

### 😍(Object-oriented Programming）OOP基本思想
1. 👌**万物皆为对象**👌
2. 程序是对象的集合
3. 每个对象都有自己的由其他对象所构成的存储
4. 每个对象都有其类型（class），某一特定类型的所有对象都可以接收相同的消息
5. ***示例***：创建了一个Student类型的对象，定义了该对象的引用s，同时对s发送getAge消息请求。 
    Student s = new Student();
    s.getAge()   
6. 每个对象都提供服务，程序应该被理解为：通过调用其他对象提供的服务，来为用户提供服务
7. 良好的OOP中，每个对象都可以很好的完成一项任务，但是它并不试图做更多的事
8. 类创建者对类消费者（客户端程序员）隐藏具体实现，只暴露必需的部分【访问控制能便于维护+减轻开发任务，Java用关键字public、private、protected来设定*****类的边界*****，Java还设置了*****包访问权限*****】
9. 🔥 **继承** 🔥（is-a和is-like-a关系）与**组合**
10. ❓❓❓ **多态** [在OOP中编译器无法产生传统意义上的函数调用，即“前期绑定”，Java缺省使用动态的“后期绑定”]--------向上转型upcasting*❓❓❓
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
2. Java**基本数据类型**[强类型语言]：（每个基本数据类型都有自己的包装类）
| boolean | char | byte | short | int | long | float | double | void |
3. **类(class)**：程序员定义的新数据类型【字段+方法】
4. **static**修饰的方法和字段是不依赖于类的对象而存在的，可以直接通过类名来访问，是没有this的方法。不论创建多少个对象，静态数据都只占用一份存储区域
5. **类的数据成员能被Java自动初始化**，而方法中的局部变量则不能，需要程序员手动初始化
6. 🔥 **“==”和“equals()”的区别** 🔥：前者比较的是基本数据类型的数值和引用类型的“对象地址”；后者不能用来比较基本数据类型，而在一些引用类型（未重写equals时）中比较“对象地址”，在另一些（重写了equals时，如String，Date，包装器类型）中比较对象的值。
7. 基本类型存储的是实际的数值，而并非指向一个对象的引用；而引用类型则不是这样（易出现“  *别名现象*  ”）
8. a++和a--：先赋值再计算； ++a和--a：先计算再赋值
9. 使用逻辑操作符时，“短路”的发生可以获得潜在的性能提升
10. BigInteger和BigDecimal是用于int和float高精度计算的两个类，支持任意精度的整数和浮点数，计算值不丢失任何信息；但是需要用方法调用来取代运算符实现运算，所以会慢一些
11. 单精度浮点数的表示范围（4bytes）：-3.40E+38~3.40E+38
12. 双精度浮点数的表示范围（8bytes）：-1.79E+308~-1.79E+308
13. Java中的小数默认是double类型，若需得到float类型要进行类型转换
14. **二进制编码**（原码---反码---补码）
15. 通常，表达式中出现的最大的数据类型决定了表达式最终的数据类型（e.g. 将一个float值和一个double值相乘，结果是double）；只要比int小的类型（char，byte和short），在运算之前，值都会自动转换成int
16. Java中包含的控制执行语句主要有“if-else, while, do-while, for, foreach, return, break, continue, switch-case”，不支持goto语句
17. **构造方法**：每个类都有至少一个构造方法，若没有显示定义一个构造方法，编译器会自动创建一个默认构造器（无参）；而若显示定义了构造方法，默认构造器就不会被创建。*除构造方法外，Java编译器中禁止在其他任何方法中调用构造方法*。      **方法重载**。
18. this关键字，用于在方法的内部获得对当前对象的引用；可以解决参数名和数据成员名相同时出现的歧义问题
19. finalize方法（终结处理）是危险的，多余的【垃圾回收】
20. 在类的内部，变量定义的先后顺序决定了初始化的顺序(**先静态对象，再非静态对象**)，即使变量定义散布于方法定义间，它们依旧会*在任何方法（包括构造方法）被调用之前*就得到初始化 
21. 对象的创建过程 [e.g. HelloLulu/src/constructor/StaticInitialization.java]
22. package和import关键字允许程序员做的，是将单一的全局名字空间分割开，使得不论多少人使用Internet（因为在发布Java程序时，package的名称一般使用反顺序的域名）和Java编写类都不会出现名称冲突的问题
23. 访问权限控制可以确保不会有任何客户端程序员依赖于某个类的底层实现的任何部分，也能简化他们对类的理解
24. **Java访问权限修饰词**：包访问权限（无任何访问权限修饰时）；public（该成员声明自己对每个人都是可用的）；private（除了包含该成员的类外，其他任何类都无法访问这个成员）；protected（继承访问权限，使得该成员对继承自该成员所在类的其他类是可用的，而对于其所在包以外的其他非子类不可用）
25. Java中的类仅有public和包访问权限两个选择。如果不希望任何其他人访问该类，可以将类中所有的构造方法设置为private，阻止任何人创建类的对象。
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MzEwNTYzMTUsMTM0MDk3MzI4MiwtND
U5NjE5ODQsLTIyMDAyNTEwMSwtNjAwMzE4NTI3LDE0ODc1NDc3
MjAsMzU0NjY2ODgwLC0xMjQ2NzkwNjMwLC0xNDI1MzcyMDAyLC
0xODMzNDY2MTQ1LDU1MDYzMDM5NiwtNzYyNzc5MzM3LDI2ODc5
NzM1NywtMTc2ODI4NjgzLC0xNzcyNDkwMjMwLDE5MzQxOTk4Nj
IsLTEzNTg3NjcyMDUsLTQ4OTA0MTQ5MCwxMjA4NDM3MDU2LC0z
MzEzNjk2NDJdfQ==
-->