## 2 `TCP拥塞控制` 
`拥塞` : `对网络中某一资源的需求超过该资源能提供的可用部分` 
`资源` : `链路容量、交换结点中的缓存和处理机...` 
Only balance in each part, this `拥塞` can be handle
`sender` set `拥塞窗口` which `发送窗口取拥塞窗口和接收方的接收窗口中最小的一个` 

* only add one resource can handle this problem
add one `结点的缓存`
`该节点的排队时间` increase
`超时重传` 

* `拥塞控制` 
global control
prevent too many data go in `network` 

### 3  `开环控制` 
control before run `network` 

### 3  `闭环控制` 
basic on `反馈环路` 
control after run `network` 
