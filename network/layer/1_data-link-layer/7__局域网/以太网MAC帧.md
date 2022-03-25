## 2 format of `以太网MAC帧` 
format of `MAC` of `以太网` : `DIX Ethernet V2` , `IEEE 802.3` 

### 3  `DIX Ethernet V2` 
* goal `MAC` 
`__:__:__:__` (`16进制`)

* source `MAC` 
`__:__:__:__` (`16进制`)

* type of `protocol` of `pre layer`
have 2 byte
it can help : give `data` to corresponding `protocol` of `pre layer` 

* `data` 
length : 46 ~ 1500 byte
if `IP data` longer, improve efficiency of transmission
if `IP data` shorter, improve efficiency of `分组转发` 
why mini length is 46: When appear `碰撞` , data of already send is a short `帧` 
`适配器` `丢弃` short `帧` 
When `data` small than 46, add `整数字节的填充字段` to end of `data` (`total data length` of `data` can know the length of `data` )

* `FCS` 
have 4 byte
