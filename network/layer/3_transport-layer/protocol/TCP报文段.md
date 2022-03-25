## 2 `TCP报文段` 

### 3  `head` 
20 byte + 4n byte

* `resource port` 
2 byte

* `goal port` 
2 byte

* `序号seq` | `报文段序号` 
4 byte
When `序号` add to 2^32-1, next is return to 0 (old `序号` already arrive goal host)
all byte of `报文` which `报文段` transport must be `编号` by order
first `序号` of total `字节流` must be set in build `TCP` connection
`序号` is `编号` of first byte of `报文` 
such as:
`序号` of one `报文段` is 301 and `报文段` have 100 byte `报文` 
`编号` of `报文` is 301 ~ 400
`序号` of next `报文段` is 401

* `确认号ack` 
4 byte
expert what receive `序号` of `对方下一个报文段的第一个数据字节` 
such as:
host B receive `报文段` whose `序号` is 501 byte and length of `报文` is 200 byte from host A
host B send `报文段` whose `确认号` is 701 to host A
Tips:
When `确认号` of `报文段` which be send is N, `确认号` of N-1 and before N-1 is receive already

* `数据偏移` 
4 bit
length of `head` of `报文段` 
unit is 4 byte
MAX length of `head` is 60 byte

* `保留` 
6 bit
`保留为今后使用，目前为0` 

* `紧急URG` 
1 bit
When `URG` == 1, `紧急指针有效` 
express this `报文段` is urgency
this `报文段` is high priority
system will first send this `报文段` 
`紧急数据` will be insert into first of `报文` (use `紧急指针` to get position of `紧急数据` )
such as: `Control + C` 

* `确认ACK` 
1 bit
After build `TCP` connection is success, `ACK` of all `报文段` == 1
only `ACK` == 1, `确认号才有效果` 

* `推送PSH` 
1 bit
in sometime, `process` want receive response quickly
~~When `PSH` == 1, `发送缓存` needn't wait cache is full and quickly send~~
When `PSH` == 1, `接收缓存` needn't wait cache is full and quickly receive

* `复位RST` 
1 bit
When `RST` == 1, may have some error and must disconnect `TCP` 

* `同步SYN` 
1 bit
`同步` in build `TCP` connection
in request of connection, `SYN` == 1 and `ACK` == 0
in response of connection, `SYN` ==1 and `ACK` == 1

* `终止FIN` 
1 bit
disconnect `TCP` connection
When `FIN` of `报文段` of `sender` == 1, all data is send and want to disconnect `TCP` connection

* `窗口` 
2 byte
own `接受窗口` 
`从本报文段中的确认号算起，自己可以允许对方发送的数据量` (receive cache)
unit is byte
it is dynamic

* `检验和` 
2 byte
check `head` and `报文` 

* `紧急指针` 
2 byte
When `URG` == 1, it can be used
position of end of `紧急数据` in `报文段` 
When `窗口` == 0 , also can send data

* `选项` 
0 ~ 40 byte
`最大报文段长度MSS` :
> MAX length of `报文` 
> When it is short, `网络利用率底(head of IP and head of TCP)` 
> When is is long , `在IP层需要分片，开销增大` 
> default is 536 byte
`窗口扩大` 
`时间c` 
`选择确认` 

* `填充` 



### 3  `报文` 
