## 2 `文件传输协议FTP` 
use `TCP` 
use `client` and `server` 
function of `FTP` is used to reduce `不兼容性` of handle file in different operation system


### 3  `server` of `FTP`
include one `主进程` and many `从属进程` 

#### 4   `主进程` 
receive request 
`port` 21 

#### 4   `从属进程` 
handle single request
Include `控制进程` and `数据传送进程` 
`port` of `控制进程` is 21
`port` of `数据传输进程` is 20
`client` must build `TCP` of `控制连接` and `TCP` of `数据连接` with `server` 
