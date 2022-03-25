## 2 `network layer` 
Packaging `segment` or `用户数据报` from `transport layer` to `分组` , `数据报` , `IP数据报` or `包` 
provide service of `无连接, 不可靠，尽最大努力交付` to `transport layer` 
`transport layer` provide logical communication to `host` 

### 3  `protocol` 
#### 4   `网际协议IP` 

##### 5    `地址解析协议ARP` 

##### 5    `网际控制报文协议ICMP` 

##### 5    `网际组管理协议IGMP` 

### 3  Why use `IP` and not use `MAC` 
have different `network` in the world
different `network` have different `硬件地址` 
transform `硬件地址` to connect different `network` is very complex
`MAC` like `身份证确定人` and `IP` like `确定具体位置国家省份门牌号` 
`MAC` is create by many `商家` and not suit `物理位置定位` 
`IP` have function of `路由` 
`IP` can unify standard
`IP` can resolve problem of connection automatic
`IP` `屏蔽` detail of `底层` 
`IP` can make all `host` like in same `nextwork` 
