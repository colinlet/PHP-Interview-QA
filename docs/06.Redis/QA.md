# 问题与简答

## Redis 篇

### Redis 介绍

Redis 是一个高性能的 key-value 数据库。每秒可执行操作高达 10万+ QPS

### Redis 特点

- 支持数据持久化，可将内存中的数据保存在磁盘，重启时再次加载
- 支持 KV 类型数据，也支持其他丰富的数据结构存储
- 支持数据备份，即 master-slave 模式的数据备份

### Redis 支持哪些数据结构

- STRING：字符串、整数或浮点数

- LIST：列表，可存储多个相同的字符串

- SET：集合，存储不同元素，无序排列

- HASH：散列表，存储键值对之间的映射，无序排列

- ZSET：有序集合，存储键值对，有序排列

### Redis 与 Memcache 区别

|对比项|Redis|Memcache|
|-|-|-|
|数据结构|丰富数据类型|只支持简单 KV 数据类型|
|数据一致性|事务|cas|
|持久性|快照/AOF|不支持|
|网络IO|单线程 IO 复用|多线程、非阻塞 IO 复用|
|内存管理机制|现场申请内存|预分配内存|

### 发布订阅

发布订阅(pub/sub)是一种消息通信模式：发送者(pub)发送消息，订阅者(sub)接收消息

### 持久化策略

#### 快照持久化 RDB

将某一时刻的所有数据写入硬盘。使用`BGSAVE`命令，随着内存使用量的增加，执行 BGSAVE 可能会导致系统长时间地停顿

#### AOF 持久化

只追加文件，在执行写命令时，将被执行的写命令复制到硬盘里面。使用 AOF 策略需要对硬盘进行大量写入，Redis 处理速度会受到硬盘性能的限制

### Redis 事务

```shell
redis> MULTI  #标记事务开始
OK
redis> INCR user_id  #多条命令按顺序入队
QUEUED
redis> INCR user_id
QUEUED
redis> INCR user_id
QUEUED
redis> PING
QUEUED
redis> EXEC  #执行
1) (integer) 1
2) (integer) 2
3) (integer) 3
4) PONG
```

> 在 Redis 事务中如果有某一条命令执行失败，其后的命令仍然会被继续执行

> 使用 DISCARD 可以取消事务，放弃执行事务块内的所有命令

### 如何实现分布式锁

#### 方式一

```text
tryLock() {
    SETNX Key 1 Seconds
}
release() {
    DELETE Key
}
```

缺陷：C<sub>1</sub> 执行时间过长未主动释放锁，C<sub>2</sub> 在 C<sub>1</sub> 的锁超时后获取到锁，C<sub>1</sub> 和 C<sub>2</sub> 都同时在执行，可能造成数据不一致等未知情况。如果 C<sub>1</sub> 先执行完毕，则会释放 C<sub>2</sub> 的锁，此时可能导致另外一个 C<sub>3</sub> 获取到锁

#### 方式二

```text
tryLock() {
    SETNX Key UnixTimestamp Seconds
}
release() {
    EVAL (
        //LuaScript
        if redis.call("get", KEYS[1] == ARGV[1]) then
            return redis.call("del", KEYS[1])
        else
            return 0
        end
    )
}
```

缺陷：极高并发场景下(如抢红包场景)，可能存在 UnixTimestamp 重复问题。分布式环境下物理时钟一致性，也无法保证，也可能存在 UnixTimestamp 重复问题

#### 方式三

```text
tryLock() {
    SET Key UniqId Seconds
}
release() {
    EVAL (
        //LuaScript
        if redis.call("get", KEYS[1]) == ARGV[1] then
            return redis.call("del", KEYS[1])
        else
            return 0
        end
    )
}
```

> 执行 `SET key value NX` 的效果等同于执行 `SETNX key value`

目前最优的分布式锁方案，但是如果在集群下依然存在问题。由于 Redis 集群数据同步为异步，假设在 Master 节点获取到锁后未完成数据同步情况下 Master 节点 crash，在新的 Master 节点依然可以获取锁，所以多个 Client 同时获取到了锁

### Redis 过期策略及内存淘汰机制

#### 过期策略

Redis 的过期策略就是指当 Redis 中缓存的 Key 过期了，Redis 如何处理

- 定时过期：每个设置过期时间的 Key 创建定时器，到过期时间立即清除。内存友好，CPU 不友好

- 惰性过期：访问 Key 时判断是否过期，过期则清除。CPU 友好，内存不友好

- 定期过期：隔一定时间，expires 字典中扫描一定数量的 Key，清除其中已过期的 Key。内存和 CPU 资源达到最优的平衡效果

#### 内存淘汰机制

```shell
[root]# redis-cli config get maxmemory-policy
1) "maxmemory-policy"
2) "noeviction"
```

- noeviction：新写入操作会报错
- allkeys-lru：移除最近最少使用的 key
- allkeys-random：随机移除某些 key
- volatile-lru：在设置了过期时间的键中，移除最近最少使用的 key
- volatile-random：在设置了过期时间的键中，随机移除某些 key
- volatile-ttl：在设置了过期时间的键中，有更早过期时间的 key 优先移除

### 为什么 Redis 是单线程的

Redis 是基于内存的操作，CPU 不是 Redis 的瓶颈，Redis 瓶颈最有可能是内存或网络。而且单线程容易实现，避免了不必要的上下文切换和竞争条件，不存在多线程切换消耗 CPU

### 如何利用 CPU 多核心

在单机单实例下，如果操作都是 O(N)、O(log(N)) 复杂度，对 CPU 消耗不会太高。为了最大利用 CPU，单机可以部署多个实例

### 集合命令的实现方法

|命令|intset 编码的实现方法|hashtable 编码的实现方法|
|-|-|-|
|SADD|调用 intsetAdd 函数，将所有新元素添加到整数集合里面|调用 dictAdd，以新元素为键，NULL 为值，将键值对添加到字典里面|
|SCARD|调用 intsetLen 函数，返回整数集合所包含的元素数量，这个数量就是集合对象所包含的元素数量|调用 dictSize 函数，返回字典所包含的键值对数量，这个数量就是集合对象所包含的元素数量|
|SISMEMBER|调用 intsetFind 函数，在整数集合中查找给定的元素，如果找到了元素存在于集合，没找到则说明元素不存在集合|调用 dictFind 函数，在字典的键中查找给定的元素，如果找到了说明元素存在于集合，没找到则说明元素不存在于集合|
|SMEMBERS|遍历整个整数集合，调用 inisetGet 函数返回集合元素|遍历整个字典，使用 dictGetKey 函数返回字典的键作为集合元素|
|SRANDMEMBER|调用 intsetRandom 函数，从整数集合中随机返回一个元素|调用 dictGetRandomKey 函数，从字典中随机返回一个字典键|
|SPOP|调用 intsetRandom 函数，从整数集合中随机取出一个元素，再将这个随机元素返回给客户端之后，调用 intsetRemove 函数，将随机元素从整数集合中删除掉|调用 dictGetRandomKey 函数，从字典中随机取出一个字典键，在将这个随机字典键的值返回给客户端之后，调用 dictDelete 函数，从字典中删除随机字典键所对应的键值对|
|SREM|调用 intsetRemove 函数，从整数集合中删除所有给定的元素|调用 dictDelete 函数，从字典中删除所有键为给定元素的键值对|

### 有序集合命令的实现方法

|命令|ziplist 编码的实现方法|zset 编码的实现方法|
|-|-|-|
|ZADD|调用 ziplistInsert 函数，将成员和分值作为两个节点分别插入到压缩列表|先调用 zslInsert 函数，将新元素添加到跳跃表，然后调用 dictAdd 函数，将新元素关联到字典|
|ZCARD|调用 ziplistLen 函数，获得压缩列表包含节点的数量，将这个数量除以2得出集合元素的数量|访问跳跃表数据结构的 length 属性，直接访问集合元素的数量|
|ZCOUND|遍历压缩列表，统计分值在给定范围内的节点的数量|遍历跳跃表，统计分值在给定范围内的节点的数量|
|ZRANGE|从表头向表尾遍历压缩列表，返回给定索引范围内的所有元素|从表头向表尾遍历跳跃表，返回给定索引范围内的所有元素|
|ZREVRANGE|表尾向表头遍历压缩列表，返回给定索引范围内的所有元素|从表尾向表头遍历跳跃表，返回给定索引范围的所有元素|
|ZRANK|从表头向表尾遍历压缩列表，查找给定的成员，沿途记录经过节点的数量，当找到给定成员之后，沿途节点的数量就是该成员所对应元素的排名|从表头向表尾遍历跳跃表，查找给定的成员，沿途记录经过节点的数量，当找到给定成员之后，沿途节点的数量就是该成员所对应元素的排名|
|ZREVRANK|从表尾向表头遍历压缩列表，查找给定的成员，沿途记录经过节点的数量，当找到给定成员之后，沿途节点的数量就是该成员所对应元素的排名|从表尾向表头遍历跳跃表，查找给定的成员，沿途纪录经过节点的数量，当找到给定成员之后，沿途节点的数量就是该成员所对应元素的排名|
|ZREM|遍历压缩列表，删除所有包含给定成员的节点，以及被删除成员节点旁边的分值节点|遍历跳跃表，删除所有包含了给定成员的跳跃表节点。并在字典中解除被删除元素的成员和分值关联|
|ZSCORE|遍历压缩列表，查找包含了给定成员的节点，然后取出成员节点旁边的分值节点保存的元素分值|直接从字典中取出给定成员的分值|


### redis 跳跃表

跳跃表(skiplist)是一种有序数据结构，它通过在每个节点中维持多个指向其他节点的指针，从而达到快速访问节点的目的。

跳跃表支持平均O(logN)、最坏O(N)复杂度的节点查找，还可以通过顺序性操作来批量处理节点。

在大部分情况下，跳跃表的效率可以和平衡树相媲美，并且因为跳跃表的实现比平衡树要来得更为简单，所以有不少程序都使用跳跃表来代替平衡树。

### redis.conf 配置

### 慢查询