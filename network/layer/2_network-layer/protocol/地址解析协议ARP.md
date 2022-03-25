## 2 `地址解析协议ARP` 
handle `IP` to `MAC` in `局域网` automatic
mapper from `IP` to `MAC` in `ARP高速缓存` of every host
`ARP请求分组` : `我的IP是xxx 硬件地址是xxx，我想知道IP是yyy 的硬件地址` 
`ARP响应分组` : `我的IP是yyy，硬件地址是yyy` 
mapper from `IP` to `MAC` have life time

### 3  process
1. host A send information to host B
2. if can find `IP` from `ARP高速缓存` , write `MAC` in `MAC帧` 
3. if can't find, `ARP` **broadcast** `ARP请求分组` to all other host in `局域网` 
4. host B find `请求的IP` same as own and receive this `ARP请求组` 
5. host B write mapper of `IP` and `MAC` of host A to `ARP高速缓存` 
5. host B send `ARP响应分组` **to host A**
6. host A receive `ARP相应分组` from host B and writ mapper of `IP` and `MAC` of host B to `ARP高速缓存` 

### 3  in different `局域网` 
if host C in `局域网` C and host D in `局域网` D
host C send information to `路由器` which belong `局域网` C and can connect to `局域网` D
