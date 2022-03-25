## 2 `网络地址转换NAT` 
use in what `host` of `专用网` which use `私网IP` connect `host` of `Internet` 
`NAT router` : should install `NAT` in `router` which belong `私网` and connect `Internet`(have `公网IP`)
host of `专用网` can't use as `service host` : when `IP data` arrive `NAT router` , `NAT router` can't handle `goal IP` 


### 3  process 
When host A in `私网` send information to host B in `公网`
host A : 192.168.0.3
host B : 213.18.2.4
`NAT router` in `私网` : 192.168.0.4
`NAT router` in `公网` : 172.38.1.5

1. host A send `IP data` to `私网 IP` of `NAT router` 
2. change `resource IP` of `IP data` of host A to `公网 IP` of `NAT router` and send
3. host B receive and response to `NAT router` 
4. `NAT router` receive `IP data` from host B
5. change `goal IP` of `IP data` of host B to host A
6. send `IP data` to host A

### 3  `网络地址与端口号转换NAPT` 
basic on `NAT` and add `port` to end of `IP` 
use `port` can implement more than one host of `私网` communicate host in `Internet` in the same time
`公网 IP` of `NAT router` + custom port(`:xxxxx`) to mark one host of `私网` 

#### 4   process
like `NAT`, but in change : need change `port` 
