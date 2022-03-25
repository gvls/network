## 2 `IP` 
unique identifier of `network interface` in all the world
have 32 bit
according to `IP` , we can find the actual address of host
`IP` is logical address of host
function: `屏蔽了下层复杂的细节` 

* method of expression
`点分十进制记法`  : `<8 bit>.<8 bit>.<8 bit>.<8 bit>` 
`binary` : `________ ________ ________ ________` 



### 3  `分类的IP` | `二级IP地址` 
include fixation length :  `网络号` , `主机号` 
`网络号` : unique identifier in all the world. Include `类别位` 
`主机号` : unique identifier in own `网络号` 
`IP 地址管理结构` only need allocation `网络号` 
one `网络` is all host which have same `网络号` 
`主机号` is allocation by ourself

#### 4   `A类` 
first number is 0 ~ 127
`类别位` : `0` 
`网络号` : `8-1 bit` 
`主机号` : `24 bit` 

* some `网络号` can't point to other
`网络号 all is 0` : `本网络` 
`网络号 is 127` : `本地软件环回测试本主机的进程之间的通信` 
`主机号 all is 0` : `网络号 of current connect` 
`主机号 all is 1` : `all host in this network`

#### 4   `B类` 
first number is 128 ~ 191
`类别位` : `10` 
`网络号` : `16-2 bit` 
`主机号` : `16 bit` 

* some `网络号` can't point to other
`网络号 is 128` : can't be used
`主机号 all is 0` : `网络号 of current connect` 
`主机号 all is 1` : `all host in this network`

#### 4   `C类` 
first number is 192 ~ 223
`类别位` : `110` 
`网络号` : `24-3 bit` 
`主机号` : `8 bit` 

* some `网络号` can't point to other
`网络号 is 192` : can't be used
`主机号 all is 0` : `网络号 of current connect` 
`主机号 all is 1` : `all host in this network`

#### 4   `D类` 
`多播地址` 
first number is 224 ~ 239
`类别位` : `1110` 
`网络号` : 
`主机号` : 

#### 4   `E类` 
`保留使用` 
first number is 240 ~ 255
`类别位` : `1111` 
`网络号` : 
`主机号` : 



### 3  `无分类编址` (`主用` ) | `三级IP地址` 
basic on `分类IP地址` 

#### 4   why need `无分类IP` 
people apply `分类IP` , may many `IP` will be waste
When have many `network` , write mapper of `网络号` in `路由表` will make `路由表` very big
`二级IP地址` isn't flexible: if people apply extra `IP` , people should wait some time

#### 4   compose
Include :  `网络号` , `子网号字段` , `主机号`



### 3  `无分类域间路由选择CIDR` 
basic on `分类IP地址` 
We also can use this knowledge in `分类IP地址` 
address of allocation is 2^X

* method of expression
`点分十进制记法`  : `<8 bit>.<8 bit>.<8 bit>.<8 bit>/<number of 前缀>` 
`binary` : `________ ________ ________ ________` 

#### 4   compose
include variable length : `前缀` , `后缀` , `斜线记法` | `CIDR记法` 
`前缀` | `网络前缀` : point to `network` 
`后缀` | `host` : point to `host` 
`斜线记法` : write `/<bit number of 前缀>` to end of `IP` 
if point one `network` , we need `网络地址` and    `地址掩码` or `bit number of 前缀` 

* `网络地址` : `前缀` + `后缀`(all is `0` )

#### 4   `CIDR 地址块` 
all `IP` which `前缀` is same and succession
When we know one of `CIDR 地址块` , we can know begin , end and total address

* method of expression of `地址块` 
`<begin address>/<number of 前缀>` 
`/<number of 前缀>` 

* some address not use
`all host is 0` 
`all host is 1` 

#### 4   `地址掩码` | `子网掩码` 
32 bit
relative to `IP` 
in `前缀` : current bit is `1` 
in `host` : current bit is `0` 

* method of expression
`点分十进制记法`  : `<8 bit>.<8 bit>.<8 bit>.<8 bit>` 
`binary` : `________ ________ ________ ________` 

#### 4   get `网络地址` form `IP` 
`IP` `逻辑与AND` `子网掩码` 

* tips
A : 128.14.41.7/21   255.255.248.0
B : 128.14.41.7/22   255.255.252.0
`网络地址` of A and B is same

#### 4   `地址聚合` 
simplify `路由表` 
because one `CIDR地址块` have many address, `路由表` use `CIDR地址块` to find `goal nextwork` (`路由聚合`)
one item of `路由表` can express many item of `old 路由表` 
many `网络地址`(`学校学院` | `广东省广州市，广东省深圳市` ...) `聚合` to one address(`学校` | `广东省`) by same `"前缀"` 

##### 5    example
* `ISP路由器` 
206.0.64.0/18	(`ISP` )	`11001110.00000000.01*` 
206.0.68.0/22 	(`大学`)	`11001110.00000000.010001*`

* `大学路由器` 
206.0.68.0/22   (`大学`)	`11001110.00000000.010001*`	(4 `C类`)
206.0.68.0/23   (`一系`)	`11001110.00000000.0100010*`
206.0.70.0/24   (`二系`)	`11001110.00000000.01000110*` 
206.0.71.0/25   (`三系`)	`11001110.00000000.01000111.0*` 
206.0.71.128/25 (`四系`)	`11001110.00000000.01000111.1*` 




### 3  `私网IP` | `本地IP` | `专用IP` 
`IPv4地址协议中预留了3个IP地址段，专门用作私有地址，仅供内网使用。这三个私网网段，恰好分布在A、B、C三类IP地址中`

```
A类地址：10.0.0.0--10.255.255.255 | 10.0.0.0/8
B类地址：172.16.0.0--172.31.255.255 | 172.16.0.0/12
C类地址：192.168.0.0--192.168.255.255 | 192.168.0.0/16
```
