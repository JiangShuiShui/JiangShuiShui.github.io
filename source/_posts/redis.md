String

~~~bash
set name jiangshui
get name
APPEND name shui  #追加拼接字符
EXISTS name	#判断name是否存在
keys *  #查看所有的key
EXPIRE name 10 #设置key的过期时间，单位为秒
ttl name  #查看当前key的剩余时间
type name #查看当前key的一个类型
incr key  #将value加1
decr key  #将value减1
INCRBY key 10  #将value设置自增的步长，每次加10
~~~

List

所有的list命令都是以L开头

~~~
LPUSH list one #将一个值或多个值，插入到列表的头部

~~~

