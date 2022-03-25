## 2 version
### 3  `http 1.0` 
performance is low than `http 1.1` 
`client` only can send one `request` on one connection (after `server` receive `request` , `server` will close the connection)



### 3  `http 1.1` 
#### 4   long connection
have `keep-alive` (default)
`keep-alive` can keep sometime, after `server` response first `request` 

#### 4   `pipelining管道` 
`client` can send more than one `request` on one connection
`client` can needn't receive `response` for pre `request` to send next `request` 



### 3  `http 2.0` 
it use binary format rather than text
it use `多路复用` : `实现` response more `request` 
it use `包头压缩` 
it can make `response` `主动地` push to cache of `client` 
