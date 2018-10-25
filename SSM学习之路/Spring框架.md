### <font face="Cabrili">Spring IoC</font>

 1. Inversion of Control：**控制反转**（将创建对象的主动权，从程序员自己手中交给容器，让容器按需求和依赖规则来创建和管理对象）是一种通过描述（Java中可以是XML或者注解）并通过第三方产生或者获取特定对象的方式
 2. IoC容器：容纳和管理所有Bean（资源），默认情况下Bean是作为单例存在的
 3. IoC容器的设计：BeanFactory是SpringIoC容器定义的最底层的接口， ApplicationContext是其高级实现的扩展接口（最为常用）
 4. BeanFactory与ApplicationContext的区别：BeanFactory在getBean的时候才会生成Bean，属于延迟加载；而ApplicationContext则是在容器启动后，扫描完容器中的Bean和依赖之后就会生成Bean。
 5. **Bean的初始化与依赖注入**是IoC容器的两大步骤：
	- **Bean 的初始化**分 为 3 步 【扫描-生成-注册】：  
	- 1)  Resource 定位，这步是 Spring IoC 容器根据开发者的配置，进行资源定位，在 Spring  的开发中，通过 XML 或者注解都是十分常见的方式，定位的内容是由开发者所提供的 。  
	- 2) BeanDefinition 的载入，这个过程就是 Spring 根据开发者的配置获取对应的 POJO,  用以生成对应实例的过程 。  
	- 3) BeanDefinition 的注册, 这个步骤就相当于把之前通过BeanDefinition载入的 POJO  往 Spring IoC 容器中注册，这样就可以使得开发和测试人员都可以通过描述从中得到 Spring  IoC 容器的 Bean 了 。
	- **依赖注入**
6. Spring **Bean的生命周期** 的管理
	

### <font face="Cabrili">Spring Bean的装载</font>

1. 实现IoC容器的方式，主要分为依赖查找和依赖注入（Spring中采用后者）
2. **依赖注入**：举例来说，若Person类需要引用Car类的对象，那么Person类就依赖于Car类，这就导致了Person类的对象需要负责创建Car类的对象并管理他的生命周期，这样会导致耦合度高、难以维护。而依赖注入的核心就是要将Person类对象A依赖的Car类对象B注入到A中去，而无需A自己去引用B，这个注入的过程，通常是由一个控制程序来完成的，无需对象去关心。
3. **依赖注入的三种方式**：构造器注入，setter注入，接口注入
4. setter注入是最常用的方式，它借助于**Java反射**来创建对象，并且调用setter方法来注入配置的值
5. 将Bean装配到Spring IoC容器中的三种方式：
	· 在 XML 中显示配置(在需要用到第三方类库的时候)；
	· 在 Java 的接口和类中实现配置（次优先）；  
	· 隐式 Bean 的发现机制和自动装配原则（优先）。
6. **利用注解来装配Bean**是最重要最常用的方式
7. **Bean的作用域**[Spring提供四种]：
	- 单例（Singleton）：默认选项，在整个应用中，Spring只为其生成一个Bean的实例；
	- 原型（Prototype）：每次注入或者通过Spring IoC容器获取Bean时，Spring都会为它创建一个新的实例
	- 会话（Session）：在Web应用中使用，在整个会话过程中Spring只创建一个Bean的实例
	- 请求（Request）：在Web应用中使用，在一次请求中Spring会创建一个实例，而不同的请求会创建不同的实例  

### <font face="Cabrili">Spring AOP<font size="4">  [AOP是对OOP的延伸与扩展]</font></font>

1. Spring AOP可以使得程序员把重点和精力放在业务逻辑上，而不是数据库事务管理和资源管控上。当方法标注为@Transactional时，该方法将启用数据库事务功能
2. AOP的底层依赖是**动态代理**。AOP将事务处理流程做一定的封装 ，然后通过动态代理技术，将代码植入到对应的流程环节中，用代理对象来执行实际业务逻辑和数据库事务管理的代理逻辑【参考Ch11_lulu_AOP_chapter11.game】
3. AOP是通过动态代理模式，来管控各个对象操作的切面环境，管理包括日志、数据库事务等操作，让我们拥有可以在反射原有对象方法之前正常返回、异常返回事后插入自己逻辑代码的能力，有时候甚至取代原始方法。




<font color=#0099ff face="楷体">**关于Spring的一些理解:**</font>
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2Njg0OTA3MTMsLTExMDA4NTI0NTQsMT
g3MjE2MzkzMiw4NjI1OTg5MTIsLTE5NjM0NDk2MTgsNTY3NjQ5
OTA1LC0xNTI3NjAxMTcyLDE1NDIyMDg1ODEsLTUxODg1MzYxMy
wxMjcyNzM3OTA5LDE1Mzc0NDE2MSwtMjA1OTYxMDI3MCwtMTY4
NjQwOTU5MiwtMjkyMTg4OTE3LDEwMzMyMjI1OSwxNDg3Mjc0OD
IwLC0xNDEzNDEyNjIyXX0=
-->