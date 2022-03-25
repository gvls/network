## 2 `protocol` / `规程procedure` 



### 3  `点对点的PPP协议` 
be used in what user connect `ISP`  and get `IP` from `ISP` 

#### 4   `protocol` 
* `链路控制协议LCP` 

* `网络控制协议NCP` 

#### 4   format of `frame` 
1 byte == 8 bit

##### 5    `frame head` 
* `F` | `PPP帧的定界符` 
`0111 1110` 
flag begin of `frame` 

* `A` 
`1111 1111` 
haven't information

* `C` 
`0000 0011` 
haven't information

* `协议` 
`____ ____ ____ ____` 

##### 5    `IP data` 
max is 1500 byte

##### 5    `frame tail` 
* `FCS` 
`____ ____ ____ ____` 

* `F` | `PPP帧的定界符` 
`0111 1110` 
flag end of `frame` 

#### 4   `字节填充` 
implement `透明传输` in `异步传输` 
`转义符` : `0111 1101` 

* add `转义符` to front of `0111 1110(F)` 
* add `0101 1101` to end of `0111 1101(转义符)` 
* add `转义符` to front of `ASCII字符 of value < 0010 0000` 

#### 4   `零比特填充` 
implement `透明传输` in `同步传输` 

* add `0` to end of `111 11` (may same with `0111 1110(F)`)



### 3  `PPPoE` (`PPP over Ethernet`) 
`PPP` packaging `data` 
`PPPoE` packaging `PPP` 
`以太网帧` packaging `PPPoE` 
packaging `frame` of `ppp` to `frame` of `PPPoE` 
often be used in `宽带上网` 



