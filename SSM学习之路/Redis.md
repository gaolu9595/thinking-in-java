### <font face="Cabrili" color="123456">Redis</font>👌

1. 性能优越性的原因：
 - 基于ANSI C语言编写，接近汇编语言，运行很快速
 - 基于内存的读/写
 - 只有6种数据结构，规则也较关系数据库少
2. RedisTemplate是Spring操作Redis用的最多的类，注意其序列化器
3. JdkSerializationRedisSerializer是默认的序列化器，可以将Java对象序列化并存储到Redis服务器中。而StringSerializer是*只针对字符串*的序列化器，可以将字符串自动赋值为 StringRedisSerializer对象，可读性很好。
4. 
> Written with [StackEdit](https://stackedit.io/).
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM2OTk3MzQzMF19
-->