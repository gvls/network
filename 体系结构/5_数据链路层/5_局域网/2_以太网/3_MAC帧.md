##  以太网MAC帧
###   DIX Ethernet V2 
* 目的 `MAC` 
`__:__:__:__:__:__` (`16进制`)

* 源 `MAC` 
`__:__:__:__:__:__` (`16进制`)

* 上一层协议的类型
2 byte

* 数据
长度 : 46 ~ 1500 byte
if `IP data` longer, improve efficiency of transmission
if `IP data` shorter, improve efficiency of `分组转发` 
为什么长度最小46：当发生碰撞，已经发送的数据 是一个短帧，适配器会丢弃收到的 短帧
当发送的数据短于46：添加整数字节的填充字段 到数据的末尾(数据长度字段可以得到真正的数据)

* FCS 
4 byte



###   IEEE 802.3
