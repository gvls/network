## 2 `传输控制协议 TCP` 
reliable service(`无差错、不丢失、不重复、按序到达)`  of data transmission
unit of data transmission is `报文段segment` 
make logical channel from `port` to `port` as `全双工可靠信道`
only support `一对一` and not support `广播` and `多播` 
efficiency of transport is slow

* length of `报文段` be decide by `current network 拥塞` and `对方给出的窗口值` 
`TCP` not concern how long data `application layer` give to `TCP缓存` 
if data of `TCP缓存` is too long, `TCP` can divide it
if data of `TCP缓存` is too short, `TCP` can wait what it long before send

* `全双工通信` of `TCP` 
host is `sender` and `receiver` 
host have `发送缓存` and `接收缓存`
When send data, `process` give data to `TCP缓存` and can do something else
in a suitable time , `TCP` send data
`TCP缓存` receive data
in a suitable time for `process` , `process` read data from `TCP缓存` 


* `face to connect`
like take phone
host must build connection before send data
after host receive data, must response
after send is end, must release connection

* `face to 字节流` 
stream is point `字节序列` which go to `process` and go out `process` 
`TCP` don't known meaning of data and see it as `无结构的字节流` 
such as:
`TCP` of host A send 10 data to `TCP` of host B
`TCP` of host B may give 5 data to `application layer` 
`字节流`  which `application layer` of host B receive is same as `字节流`  of host A send

### 3  `可靠传输` 
When appear `差错` in data, let sender resend
When receiver is too late to receive, tell reduce speed of send to sender

#### 4   `停止等待协议` 

#### 4   `连续ARQ协议` and `滑动窗口协议`

### 3  which `protocol` of `application layer` use `TCP` 
* `SMTP` 

* `HTTP` 

* `FTP` 
