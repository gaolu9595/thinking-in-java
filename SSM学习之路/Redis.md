### <font face="Cabrili" color="123456">Redis</font>👌

1. **性能优越性的原因**：
 - 基于ANSI C语言编写，接近汇编语言，运行很快速
 - 基于内存的读/写
 - 只有6种数据结构，规则也较关系数据库少
2. **RedisTemplat**e是Spring操作Redis用的最多的类，StringRedisTemplate是操作字符串的类。注意他们的序列化器
3. Redis默认使用的客户端驱动是lettuce，而**jedis**是最常用的客户端驱动。因此在pom.xml中要注意按需消除对lettuce的依赖，而增加对jedis的依赖
4. 可以将对同一个数据类型的操作使用BoundXXXOperations绑定到一起，方便操作
5. JdkSerializationRedisSerializer是默认的序列化器，可以将Java对象序列化并存储到Redis服务器中。而StringSerializer是**只针对字符串**的序列化器，可以将字符串自动赋值为 StringRedisSerializer对象，可读性很好。
6. Redis对不同数据类型的操作：
	- String：字符串是最常用的数据类型之一，可以直接用StringRedisTemplate操作，较为方便
	- Hash：散列结构是最常用的数据类型之一【field-value对】
	- List：Redis中的List采用的是**链表结构**，因此其查询性能低，增删性能高
	- Set：集合是不允许有重复元素存在的，在数据结构上来说它是散列表，因此无序
	- Zset：有序集合 ，也是散列表结构，依靠增加属性score来实现有序
	- Geo地理位置
	- 基数
7. Redis支持一定的事务能力:【watch...multi...exec】




<font color="654321" size="4"> **Redis（NoSQL）与数据库的异同**

NoSQL的数据主要存储在**内存**中，部分可以持久化到磁盘；而数据库主要用磁盘来存储数据

NoSQL的数据结构比较简单，**功能有限**，不能支持复杂的计算，不如数据库的SQL语句强大

NoSQL并**不完全安全稳定**，因为它基于内存，一旦停电或者机器故障容易丢失数据，持久化能力不强

NoSQL的数据完整性、事务能力、


</font>
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTQ1OTMyNDc3OSwxMzMyNTk1OTI1LC0xMT
g0Mzg3ODExLDEzMzI5MTc4Nyw3MDczMzU2ODEsMTgwNTU4Nzkz
MiwtMzY5OTczNDMwXX0=
-->