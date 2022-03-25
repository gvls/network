## 2 `网际协议IP` 
### 3  `IP data` (`IPv4`)
include `head`(include fixation length 20 byte and variable length) , `data` 

* `version` 
4 bit
such as : `IPv4` , `IPv6` 

* `head length` 
4 bit
4 byte / number , so max = 15 * 4 = 60 byte
if `head` % 4byte != 0, use `填充字段` to fill

* `区分服务` 
8 bit

* `total length` 
`head`  +  `data` | `data of 分片` 
unit is byte
16 bit
if total length bigger than `MTU` of `data link layer` , `IP data` must `分片` 
`data` of `分片` % 8 byte == 0

* `标识identification` 
16 bit
When generate a `IP data` , it ++
it can identify `分片` of one `IP data` 

* `标志flag` 
3 bit
`最后一位MF` : if `MF` == 1, have `分片` behind it . If `MF` == 0, it is final `分片` 
`中间一位DF` : if `DF` == 1, can't `分片` . If `DF` == 0, can `分片` 

* `片偏移` 
13 bit
unit is 8 byte
position relative to begin of `IP data` 
`片偏移` = position of `current 分片` / 8

* `生存时间TTL` 
8 bit
MAX is 255 and we can set smaller
When `路由器` `转发` `IP data` , it --
if it == 0, `路由器` will `丢弃` it 
it == number of be `转发` by `路由器` 

* `协议` 
8 bit
what type of `data` of `IP data` 
it can help what give `data` to `protocol` of `pre layer` 
`1` : `ICMP` 
`2` : `IGMP` 
`6` : `TCP` 
`17` : `UDP` 
`41` : `IPv6` 
`89` : `OSPE` 

* `首部检验和` 
16 bit
check `head` of `IP data` 

* `源地址` 
32 bit

* `目的地址` 
32 bit



* `可变部分` 
MAX is 32 bit
be used for function
if add function by use it, we must add `0 填充字段` to make total of it % 4 byte == 0
