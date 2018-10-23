### <font face="Cabrili">Spring IoC</font>

 1. Inversion of Control：**控制反转**（将创建对象的主动权，从程序员自己手中交给容器，让容器按需求和依赖规则来创建和管理对象）是一种通过描述（Java中可以是XML或者注解）并通过第三方产生或者获取特定对象的方式
 2. IoC容器：容纳和管理所有Bean（资源）
 3. IoC容器的设计：BeanFactory是SpringIoC容器定义的最底层的接口， ApplicationContext是其高级实现的扩展接口（最为常用）
 4. **Bean的初始化与依赖注入**是IoC容器的两大步骤
	- 首先通过XML配置文件，将对象和依赖对象都配置到某个XML文件中；
	- 然后通过BeanFactory类来自动实现注入过程
	- 举例
<pre><code>
<bean id="car" class="car的全限定名"> </bean>
<bean id="person" class="person的全限定名"> 
	<property name="car" ref="car"> 
</bean>
<code><pre>
	
	
5. Spring **Bean的生命周期** 的管理

### <font face="Cabrili">Spring Bean的装载</font>

1. 实现IoC容器的方式，主要分为依赖查找和依赖注入（Spring中采用后者）
2. **依赖注入的三种方式**：构造器注入，setter注入，接口注入
3. 构造器注入：










<font color=#0099ff face="楷体">**关于Spring的一些理解:**</font>
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MTc2NTUyMDQsLTIwNTk2MTAyNzAsLT
E2ODY0MDk1OTIsLTI5MjE4ODkxNywxMDMzMjIyNTksMTQ4NzI3
NDgyMCwtMTQxMzQxMjYyMl19
-->