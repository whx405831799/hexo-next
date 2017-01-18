title: Redis-2.数据类型
date: 2017/01/13 19:06:06
categories:
- JAVA服务端-redis
tags:
- redis
---

# Redis命令第一部分-键(key)

## 1.连接redis

```
$ redis-cli -h host -p port -a password
eg：redis-cli -h 127.0.0.1 -p 6379 -a redis 
如果没密码 直接redis-cli
```

## 2.Redis的键命令

命令 | 作用 | 例子 | 结果
---|---|---|---
SET key | 插入键 | SET mykey whx| ok
GET key | 插入键 | GET mykey whx| whx
DEL key | 删除键 | DEL mykey| (integer) 1
DUMP key  | 返回存储在指定键的值的序列化版本 | DUMP mykey| \x00\x03whx\a\x00N\xa8h\x85\xcb\xa1t4
EXISTS key | 查询键是否存在 | EXISTS mykey| (integer) 1
EXPIRE key seconds | 指定键的过期时间，秒 | EXPIRE mykey 10| (integer) 1
EXPIREAT key timestamp  | 指定的键过期时间，时间为Unix时间戳格式 | EXPIREAT mykey 1484539499| (integer) 1
PEXPIRE key milliseconds | 指定键的过期时间，毫秒 | PEXPIRE mykey  10000| (integer) 1
PEXPIREAT key milliseconds-timestamp  | 设置键在Unix时间戳指定为毫秒到期 | PEXPIREAT key 1484556630000| (integer) 1
KEYS pattern  | 查找与指定模式匹配的所有键 | KEYS my*| mykey
MOVE key db   | 移动键到另一个数据库(select 0 就是选择0库) | MOVE mykey 1| (integer) 1
PERSIST key   |命令用于移除给定 key 的过期时间，使得 key 永不过期 | PERSIST mykey| 当过期时间移除成功时，返回 1 。 如果 key 不存在或 key 没有设置过期时间，返回 0 。
TTL keys  | TTL 命令以秒为单位返回 key 的剩余过期时间| TTL mykey| 当 key 不存在时，返回 -2 。 当 key 存在但没有设置剩余生存时间时，返回 -1 。 否则，以毫秒为单位，返回 key 的剩余生存时间。
PTTL key | 以毫秒为单位返回 key 的剩余过期时间 | PTTL mykey| 当 key 不存在时，返回 -2 。 当 key 存在但没有设置剩余生存时间时，返回 -1 。 否则，以毫秒为单位，返回 key 的剩余生存时间。
RANDOMKEY  | 从当前数据库中随机返回一个 key | RANDOMKEY| mykey
RENAME key newkey  | 修改键的名字 | RENAME mykey newmykey| ok
RENAMENX key newkey   | 用于在新的 key 不存在时修改 key 的名称 | RENAMEX mykey newmykey| ok
TYPE key   | 用于返回 key 所储存的值的类型 | TYPE mykey| String
 



 


