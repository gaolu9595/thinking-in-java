
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

**JDK动态代理**： 需要接口

    // 定义一个接口if,作为代理类
    // 用ifImpl类实现if，作为真实对象类
    // 定义一个JdkProxy类实现InvocationHandler接口：用bind()方法得到一个代理对象proxy；用invoke()方法来描述代理逻辑[在proxy调用方法时，就会进入invoke]。
    interfa

**CGLIB动态代理**：不需要接口

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk0ODM5MTc3MSw4MDA5MTgzNzEsNzI4Mz
A1MDcxLDE2OTA5MDUxMjldfQ==
-->