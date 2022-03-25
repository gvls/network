## 2 `广播信道的局域网CSMA/CD协议(载波监听多点接入/碰撞检测)` 
work in `适配器` 

### 3  `多点接入` 
It's meaning is this is `总线型网络` 

### 3  `载波监听` 
without stop check `channel` before send information, sending information to know other host if is sending information

* in before send information
in order to get power of send
if other host is sending , you should wait for `channel` is free 

* in sending information
check other host may send information lead to `碰撞` (`半双工通信` )
why will `碰撞` appear and we check before send ? : speed `延迟` of `电磁波` 

### 3  `碰撞检测` | `边发送边监听` | `冲突检测` 
When appear `碰撞` , host must stop send information and delay a short random time
