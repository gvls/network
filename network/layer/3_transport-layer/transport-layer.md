## 2 `transport layer
Provide **general data transmission service** for all `process` of `application layer` 
When host A communicate with host B, actual is `process` of host A communicate with `process` of host B
`protocol` of `IP` only complete send data to host, still stay `nextwork layer` and not give data to `process` 
`transport layer` provide logical communication to `process` (from `port` to `port`)
`屏蔽` detail for `网络拓扑、路由选择协议...` to make user see like one logical channel from `port` to `port` 

### 3  `复用` 
Many `process` of `application layer` use service which `transport layer` provide at the same time

### 3  `分用` 
After `transport layer` receive data from `network layer` , It send data to corresponding `process` of `application layer` 

### 3  `protocol` 
#### 4   `用户数据报协议 UDP` 

#### 4   `传输控制协议 TCP` 

### 3  `差错检测` for `报文` 
because in `network layer` , only check `head` and not check `data` 
