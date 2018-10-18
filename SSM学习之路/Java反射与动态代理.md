
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





### 动态代理	

生成一个代理对象，来控制对真实对象的访问

**JDK动态代理**： 需要接口


**CGLIB动态代理**：不需要接口

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY5MDkwNTEyOV19
-->