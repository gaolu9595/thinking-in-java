
## Java反射与动态代理

### 反射

在程序运行时动态创建对象和调用方法，而不需要在提前在程序中写死

Java反射相比较直接new对象而言，更加灵活，很适合框架开发，但是会有一些性能损耗

反射技术是IoC实现的基础，IoC通过读取配置文件来利用Java反射动态地创建对象和调用方法

    Book book = null;
    // **包起来的是灵活可变的参数
    try{
    book = (Book)Class.forName("*package path*").getConstructor("*parameter list*").newInstance("*parameters*");
    Method method = book.getClass().getMethod("*method name*","*parameter list*");
    method.invoke(book, "*paremeters*")
    }
    catch(.....){
    }





### 动态代理	👩‍💻👩‍💻👩‍💻 Hard

生成一个代理对象，来控制对真实对象的访问


1.用getProxy生成代理对象；
2.制定代理的逻辑类【代理逻辑类要实现一个接口的一个方法，该方法就是代理对象的逻辑方法，可以控制真实对象的方法】

**JDK动态代理**： 需要接口  【绕得不行啊啊啊，慢慢来慢慢理解】

    // 定义一个接口if,作为代理类
    // 用ifImpl类实现if，作为真实对象类
    // 定义一个JdkProxy类实现InvocationHandler接口：用bind()方法得到一个代理对象proxy；用invoke()方法来描述代理逻辑[在proxy调用方法时，就会进入invoke]
    // 拦截器模式时：程序员只需要关注拦截器提供的接口需要实现哪些方法，而不需要管具体的代理逻辑了。在有拦截器时拦截；无拦截器时就直接反射真实对象的方法了。
    // 测试时，先用真实对象[ifImpl类]调用bind得到一个代理对象[if类]，用代理对象去调用具体方法

**CGLIB动态代理**：不需要接口


## 设计模式

**责任链模式**：对应于一个对象在多个角色中处理的场景
**观察者模式**：一（被观察者，继承Observable类）对多（观察者，实现Observer接口）的依赖关系
**工厂模式**：只需要告知工厂需要什么对象，而不需要关注工厂如何创建对象
**建造者模式**：可以将一个产品的内部表象（属性〉与产品的生成过程分割开来，从而使一个建造过程生成具有不同的内部表象的产品对象。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUxMTgyMTg3Myw0MDcwNzI5MjIsLTc2OT
E5NzQ0MCwxODAzNjI0Mjg0LDExNjgwNjMyODUsMTY2OTI0MzAz
LC0yMjIyMDg5MzcsODAwOTE4MzcxLDcyODMwNTA3MSwxNjkwOT
A1MTI5XX0=
-->