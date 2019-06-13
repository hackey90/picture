# **Redis 5.0.5 Install manual**

>**单实例安装**

>**1.Download, extract and compile Redis with**
```shell
$ wget http://download.redis.io/releases/redis-5.0.5.tar.gz
$ tar xzf redis-5.0.5.tar.gz
$ cd redis-5.0.5
$ make MALLOC=libc
```
>**2.test redis**
```shell
$ yum install tcl
$ make test
```
![](https://github.com/hackey90/picture/blob/master/redis%20install%20picture/Image4.png?raw=true)
> **3.run redis**

The binaries that are now compiled are available in the src directory. Run Redis with:
```shell
$ src/redis-server
```
![](https://github.com/hackey90/picture/blob/master/redis%20install%20picture/Image5.png?raw=true)
You can interact with Redis using the built-in client:
```shell
$ src/redis-cli
redis> set foo bar
OK
redis> get foo
"bar"
```
>**4.performance test**

use redis-benchmark tools test redis performance .

```shell
#实例同时执行 1000 个请求来检测性能
./redis-benchmark -n 1000 -q
```
![](https://github.com/hackey90/picture/blob/master/redis%20install%20picture/2019-06-13_162713.png?raw=true)
```shell
#测试存取大小为100字节的数据包的性能
redis-benchmark -h 127.0.0.1 -p 6379 -q -d 100
```
![](https://github.com/hackey90/picture/blob/master/redis%20install%20picture/2019-06-13_163023.png?raw=true)
```shell
#100个并发连接，100000个请求，检测host为localhost 端口为6379的redis服务器性能 
redis-benchmark -h 127.0.0.1 -p 6379 -c 100 -n 100000 
```
![](https://github.com/hackey90/picture/blob/master/redis%20install%20picture/2019-06-13_163135.png?raw=true)
