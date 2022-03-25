## 2 `用户数据报` 
### 3  `head` 
8 byte

* `resource port` 
2 byte
When needn't response of `"goal host"` , write `0` 

* `goal port` 
2 byte
if `goal host` can't find `process` use `goal port` or `goal port` error, will `丢弃` this `用户数据报`  and let `ICMP` send `差错报文` of `终点不可达` to `resource host` 

* `length` 
2 byte
length of `用户数据报` 
mini is 8 byte(only have `head` )

* `检验和` 
2 byte
check `用户数据报` 
When have error, current `用户数据报` will be `丢弃` 

### 3  `报文` 
