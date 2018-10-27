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
2. AOP的底层依赖是**动态代理**。**AOP将事务处理流程做一定的封装 ，然后通过动态代理技术，将业务代码织入到对应的流程环节中**，用代理对象来执行实际业务逻辑和处理流程的代理逻辑【参考Ch11_lulu_AOP_chapter11.game】
3. **AOP**通过动态代理模式，带来管控各个对象操作的切面环境，管理包括日志、数据库事务等操作，让我们拥有可以在反射原有对象方法之前正常返回、异常返回事后插入自己逻辑代码的能力，有时候甚至取代原始方法。在一些常用流程中，如数据库事务，AOP会提供默认的实现逻辑。
4. **AOP的专用术语**：
	- **切面**（Aspect）：即业务在怎样的一个**环境**中进行。如数据库事务流程类就是一个切面类
	- **通知**：切面开启后，切面的方法。如前置通知(before)等
	- 引入：允许我们在现有类中添加自定义的类和方法
	- **切点**：被切面拦截的就是一个切点。切面将切点按照一定的逻辑织入到约定流程中
	- **连接点**：判断条件，由它来指定哪些是切点
	- 织入：生成代理对象的过程
5. Spring是方法级别的AOP框架，只能基于方法进行拦截
6. AOP的开发方式，主要是**注解**（AspectJ）和XML【Ch11_lulu_AOP_chapter11.aspectJ】
7. Spring底层是**通过责任链模式来实现多个切面**的【Ch11_lulu_AOP_chapter11.multiAspect】

### <font face="Cabrili">Spring数据库事务管理</font>
Spring的数据库事务是通过PlatformTransactionTemplate管理的

1. @Transactional注解
2. 事务的传播方法与隔离级别

### <font face="Cabrili">Spring MVC</font>
1. Spring MVC的**组件与流程**
2. XML配置Spring MVC  【Web.xml】
3. Java注解配置Spring MVC 【只要继承 AbstractAnnotationConfigDispatcherServletlnitializer 类就完成了DispatcherServlet映射关系和 Spring IoC 容器的初始化工作】
4. Spring MVC的**初始化**  【通过实现ServletContextListener接口，可以使得在DispatcherServlet初始化前就完成Spring IoC容器的初始化，也可以在结束前完成对IoC容器的销毁】【大部分场景下，应该让DispatcherServlet在服务器启动期间就完成Spring IoC的初始化，所以建议使用ContextLoaderListener进行初始化】【DispatcherServlet映射关系初始化可以设定在DispatcherServlet启动时或者是第一次接受到用户请求时】
5. Spring MVC 需要初始化 IoC 容器和DispatcherServlet 请求两个上下文，其中 DispatcherServlet 请求上下文是 Spring IoC 上下文的扩展，这样就能使得 Spring 各个 Bean 能够形成依赖注入。
6. Spring MVC的开发流程



<font color=#0099ff face="楷体">**关于Spring的一些理解:**</font>
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEyNTk2NTMwNTcsMTE5OTI3NjQ5NywtMT
c2MzcyODI0NSwtMTk5NDEzNDk2OSwyNTk0MDQ1MDgsMTM3OTQ1
MDE4MiwtMjA2ODExMzcyMiwyMDg4NjMwMTA1LDUxMTk4OTcyMS
wxOTIzNjkyMDMwLC0xMTAwODUyNDU0LDE4NzIxNjM5MzIsODYy
NTk4OTEyLC0xOTYzNDQ5NjE4LDU2NzY0OTkwNSwtMTUyNzYwMT
E3MiwxNTQyMjA4NTgxLC01MTg4NTM2MTMsMTI3MjczNzkwOSwx
NTM3NDQxNjFdfQ==
-->