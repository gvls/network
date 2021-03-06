##  TCP报文段 

###   头部
20 byte + 4n byte

* 源端口
2 byte



* 目的端口
2 byte



* 序号seq / 报文段序号 
4 byte
当序号添加到 2^32-1，下一个序号回到0，旧的序号一定是已经到目的主机了 
传输报文段前，报文的所有 比特 必须按序编号
序号： 报文的 第一个字节 的编号
在建立链接时，所有字节流的第一个序号 必须被确定
例子:
当前报文段 有100个数据(301 ~ 400)，序号是 301
下一个报文段的 序号是 401



* 确认号ack 
4 byte
期望对方的下一个报文段的序号
当确认号是 n ，表示 n-1及之前的数据已经被受到了
例子:
收到了 501 ~ 700 的数据
响应 确认号 701



* 数据偏移/首部长度
4 bit
报文段的 头部的长度
单位是 4 byte
最大长度是 60 byte

* 保留 
6 bit
保留为今后使用，目前为0 

* 紧急URG 
1 bit
当 URG == 1, 紧急指针才有效 
表示该报文段 很紧急，有很高的优先权，系统会第一时间发送该报文段
紧急数据会被插入报文的第一个位置，可以使用紧急指针得到紧急数据的位置
比如: `Control + C` 

* 确认ACK/标识为回复
1 bit
在建立链接成功之后，所有报文段的 ACK == 1
只有 ACK == 1，确认号才有用

* 推送PSH 
1 bit
进程想尽快受到响应
~~ 当 PSH == 1，发送缓存 不再等待 TCP缓存满，立即发送 ~~
当 PSH == 1，接收缓存 不再等待 TCP缓存满，立即接受

* 复位RST 
1 bit
当 PST == 1，出现了一些错误，必须断开链接

* 同步SYN/发起链接
1 bit
在建立链接时 使用
在请求连接时，SYN == 1、ACK == 0
在响应连接时，SYN == 1、ACK == 1

* 终止FIN/断开链接
1 bit
在断开链接时 使用
当发送者的报文段的 FIN == 1，所有数据以及被发送，并想断开链接



* 窗口 
2 byte
自己的 接收窗口
从本报文段的确认号算起，自己可以允许对方发送的数据量
单位是 byte
动态变化的



* 检验和 
2 byte
检验 头部和报文



* 紧急指针 
2 byte
当 URG == 1，它才可以被使用 
紧急数据在报文段的最后位置
当窗口 == 0，当前报文也会被发送



* 选项 
0 ~ 40 byte
窗口扩大 
时间戳  
选择确认 
最大报文段长度MSS :
报文的最大长度
若它太短，网络利用率底(IP的头部和TCP的头部占用比例大) 
若它太常，IP层需要分片，开销大
默认是 536 byte

* 填充 




###   报文 

