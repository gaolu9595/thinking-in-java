### <font face="Cabrili">Spring IoC</font>

 1. Inversion of Control：**控制反转**（将创建对象的主动权，从程序员自己手中交给容器，让容器按需求和依赖规则来创建和管理对象）是一种通过描述（Java中可以是XML或者注解）并通过第三方产生或者获取特定对象的方式
 2. IoC容器：容纳和管理所有Bean（资源）
 3. IoC容器的设计：BeanFactory是SpringIoC容器定义的最底层的接口， ApplicationContext是其高级实现的扩展接口（最为常用）
 4. **Bean的初始化与依赖注入**是IoC容器的两大步骤
	- 首先通过XML配置文件，将对象和依赖对象都配置到某个XML文件中；
	- 然后通过BeanFactory等类来自动实现注入过程
	- 举例
<pre><code>
<bean id="car" class="car的全限定名"> </bean>
<bean id="person" class="person的全限定名"> 
	<property name="car" ref="car"> 
</bean>
</code></pre>
	
	
5. Spring **Bean的生命周期** 的管理

### <font face="Cabrili">Spring Bean的装载</font>

1. 实现IoC容器的方式，主要分为依赖查找和依赖注入（Spring中采用后者）
2. **依赖注入**：举例来说，若Person类需要引用Car类的对象，那么Person类就依赖于Car类，这就导致了Person类的对象需要负责创建Car类的对象并管理他的生命周期，这样会导致耦合度高、难以维护。而依赖注入的核心就是要将Person类对象A依赖的Car类对象B注入到A中去，而无需A自己去引用B，这个注入的过程，通常是由一个控制程序来完成的，无需对象去关心。
3. **依赖注入的三种方式**：构造器注入，setter注入，接口注入
5. setter注入是最常用的方式，它借助于**Java反射**来创建对象，并且调用setter方法来注入配置的值：<font color=#ff0000>【插入图片】</font>









<font color=#0099ff face="楷体">**关于Spring的一些理解:**</font>
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUzNzQ0MTYxLC0yMDU5NjEwMjcwLC0xNj
g2NDA5NTkyLC0yOTIxODg5MTcsMTAzMzIyMjU5LDE0ODcyNzQ4
MjAsLTE0MTM0MTI2MjJdfQ==
-->