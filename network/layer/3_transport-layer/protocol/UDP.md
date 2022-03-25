## 2 `用户数据报协议 UDP` 
unit of data transmission is `用户数据报` 
packaging `报文` from `application layer` to `用户数据报` (not `拆分` and not `合并`)
`process` should choose suitable length of `报文` to avoid `分片` in `network layer` 
make logical channel from `port` to `port` as `全双工不可靠信道` 
data transmission of `best efforts`
`not reliable`
is efficient
support communication of `一对一` , `一对多` , `多对多` 
efficiency of transport is quick

* haven't `拥塞控制` 
when appear `拥塞` in `network` , speed of send of `resource host` isn't change
allow lose some data in `网络拥塞` 
not allow many `时延` in data
often be use in `IP 电话` , `实时视频` ...

* `not connect`
host needn't build connection before send data
after host receive data, needn't response


### 3  which `protocol` of `application layer` use `UDP` 
* `DNS` 

* `TFTP` 

* `RIP` 

* `DHCP` 

* `专用协议` 

* `IGMP` 

### 3  function
#### 4   `分用` 

#### 4   `复用` 

#### 4   `差错检测` 


### 3  compose of `用户数据报` 
