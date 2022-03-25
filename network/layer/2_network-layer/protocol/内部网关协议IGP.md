## 2 `内部网关协议IGP` 
`域内路由选择` 
use inside of `自治系统网络AS` 

### 3  `内部网关协议RIP` 
`路由选择协议` of `基于距离向量` of `分布式` 
it is simple and cost small
each `路由器` need record `距离` from itself to other `network` 
`RIP` choose shortest `距离` (`经过最少路由器`) rather than one road which have long `距离` but may have high`speed` and low `延迟` 

* `距离` 
direct connect is `1` 
When pass one `路由器`, `距离` ++
MAX `距离` is 15 (suit small `network` )

* characteristic
exchange `路由表` from neighbor `路由器` in fixed time
`路由表` : shortest `距离` and `下一跳路由器的IP地址` from own to all other `network` 
tips:
When `router A` and `router B` tell `router C` can connect one `network` , `router C` calculate and choose shortest one to save

#### 4   process
1. get `距离 1` of direct connect `network` 
2. exchange `路由表` from neighbor `路由器` in fixed time
3. get shortest `距离` and `下一跳路由器的IP地址` from own to all other `network` 




### 3  `内部网关协议OSPF` 
`路由选择协议` of `基于链路状态` of `分布式` 

* characteristic
`洪泛法` : exchange `路由表` from all other `路由器` when `链路状态` is change(send information to neighbor `router` and neighbor `router` send information to neighbor `router`)
`路由表` : `链路状态` | `度量` | `代价` from own to all neighbor `network` 
`代价` : `费用 | 距离 | 时延 | 宽带 ...` 
use `IP data` to connect
in order to adapt big `network` , `OSPF` divide `network` to many `区域` and use `层次结构的区域划分` to connect add `区域` 
can set `代价` on specific `链路` 
can have more path to `goal nextwork` and use `负载平衡` 
when `router` exchange information, `router` can authenticate identity of `MAC帧` 
support `无分类编址CIDR` and `可变长度的子网划分` 

#### 4   process
1. `洪泛法` 
2. when `链路状态` is change , use `洪泛法` 
3. get `链路状态数据库` which is `全网的拓扑结构图` 
