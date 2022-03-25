## 2 connect of `TCP` 
connect from `套接字socket` | `插口` to `套接字socket` | `插口`
`套接字socket` | `插口` : `<IP>:<port>` 

* connection of `TCP` use `client` and `server` type
assumption host A run `client` and host B run `server` 
host B run `server` , `不断监听` if have request of connection from `client` 
host A run `client` and send request of connection(`报文段`) to `server` of host B


### 3  `build connection` | `三报文握手` 
* `sever` have `保活计时器` 
if after `保活计时器` `server` not receive request from `client`,`server` will send `探测报文段` unceasing
if all `探测报文段` not have response, close connection
after build connection, when `server` receive once request from `client` , this `保活计时器` reset

`TCP规定，SYN报文段（SYN=1的报文段）不能携带数据，但需要消耗掉一个序号。` 
`TCP规定，ACK报文段可以携带数据，但是如果不携带数据则不消耗序号。` 

Tips:
`客户端向服务端发送链接请求，服务端发送确认链接的响应，为了避免因为网络拥塞导致客户端的链接请求在一段时间后（这个时候客户端和服务端并没有链接）服务端受到链接请求并且发送确认链接的响应，但客户端没想链接就没理睬，而服务端以为链接建立了，就一直在等。所以要三报文握手，客户段在受到服务段的确认链接响应后要对链接进行确认（给服务段发送确认链接响应）` 

1. host A run `client` and send request of connection(`报文段`) to `server` of host B
`报文段` : `SYN` == 1 , `seq` == `x` 

2. Host B receive request from host A and if confirm, send confirm of `报文段` to host A
`报文段` : `SYN` == 1 , `seq` == `y`     , `ACK` == 1 , `ack` == `x` + 1

3. Host A receive confirm from host B, send confirm of `报文段` to host B
`报文段` : 		`seq` == `x` + 1 , `ACK` == 1 , `ack` == `y` + 1

* why use `三报文握手` 
prevent `已经失效的连接请求报文段突然发送到` host B
host A send request of connection to `server` of host B
but this `报文段` is `在网络传输过程中停留没有发送到` host B
host A resend request of connection
...
Host A communicate with host B
`disconnect connection` 
the first request of connection of host A is send to host B
Host B receive request from host A and if confirm, send confirm of `报文段` to host A
but host A not response
if not is `三报文握手` , host B `以为建立了链接，就一直在等待` 
`第一次握手：Client 什么都不能确认；Server 确认了对方发送正常; 第二次握手：Client 确认了：自己发送、接收正常，对方发送、接收正常；Server 确认了：自己接收正常，对方发送正常; 第三次握手：Client 确认了：自己发送、接收正常，对方发送、接收正常；Server 确认了：自己发送、接收正常，对方发送接收正常` 

* why `传了 SYN,为啥还要传 ACK`
`双方通信无误必须是两者互相发送信息都无误。传了 SYN，证明发送方到接收方的通道没有问题，但是接收方到发送方的通道还需要 ACK 信号来进行验证。`



### 3  `transport data` 
`seq` of host A is begin from `x` + 1
`seq` of host B is begin from `y` + 1



### 3  `disconnect connection` | `四报文握手` 
` TCP规定，FIN报文段即使不携带数据，也要消耗一个序号。` 

Tips:
`谁没有数据传输想断开链接就发出请求，受到确认后自己不能再发数据，但是能接受对方的数据(对方还没想断开链接，还有数据传输)` 

1. Host A send request of disconnect connection(`报文段` ) to host B
`报文段` : `FIN` == 1 , `seq` == `u`

2. Host B receive request from host A and send confirm of `报文段` to host A
`报文段` : 		`seq` == `v`     , `ACK` == 1 , `ack` == `u` + 1(`u` is used in success)
in this time, connection between host A and host B is `半关闭状态` 
connection from host A to host B is close   but connection from host B to host A still open 
host A can't send data to host B   and host B can't receive data from host A
host B still can send data to host A   and host A also can receive data from host B


3. Host B send request of disconnect connection(`报文段` ) to host A
`报文段` : `FIN` == 1 , `seq` == `v`     , `ACK` == 1 , `ack` == `u` + 1

4. Host A receive request from host B and send confirm of `报文段` to host B
`报文段` : 		`seq` == `u` + 1 , `ACK` == 1 , `ack` == `v` + 1(`v` is used in success)

* After `4.` host A will go to `TIME_WAIT` status and wait `最大报文段生存的时间` 
may `报文段` of `4.` or `报文段` of `3.`   will lose and host B will do `3.` again unceasing
if host A receive `4.` again, host A do `4.` again and go to `TIME_WAIT` again

Close connection

* why use `四报文握手` 
`在释放链接之前双发有数据传输，一方断开链接，另外一方可能还有数据传输过来，这样会造成数据丢失` 

`任何一方都可以在数据传送结束后发出连接释放的通知，待对方确认后进入半关闭状态。当另一方也没有数据再发送的时候，则发出连接释放通知，对方确认后就完全关闭了TCP连接。; 举个例子：A 和 B 打电话，通话即将结束后，A 说“我没啥要说的了”，B回答“我知道了”，但是 B 可能还会有要说的话，A 不能要求 B 跟着自己的节奏结束通话，于是 B 可能又巴拉巴拉说了一通，最后 B 说“我说完了”，A 回答“知道了”，这样通话才算结束。` 
