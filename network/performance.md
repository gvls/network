## 2 `速率` / `数据率` / `比特率` 
Point `额定速率` or `标称速率` 
`bit` : 0 or 1
k = 10^3 bit/s
M = 10^6 bit/s
G = 10^9 bit/s
T = 10^12 bit/s
P = 10^15 bit/s
E = 10^18 bit/s
Z = 10^21 bit/s
Y = 10^24 bit/s

## 2 `带宽` 
Point width of `频带` 
such as : 300Hz ~ 3.4kHz
If `带宽` more width , `最高数据率` is more high

## 2 `吞吐量` 
in unit time , actual number of data which access one network

## 2 `时延` / `延迟` / `迟延` 
time of data(`message` or `packet` or `bit` ) from port to port
`时延` = `发送时延` + `传播时延` + `处理时延` + `排队时延` 

### 3  `排队时延` 
* wait in input queue of `router` 
* wait in output queue of `router` 

### 3  `处理时延` 
after `router` or `host` accept a `packet` , it need some time to handle : analyse `header` , extract `datd` , `差错检测` , find next `router` ...

### 3  `发送时延` / `传输时延` 
happen in `网络适配器` ...
`发送时延` = `数据帧长度bit` / `发送速率bit/s` 
In high speed network link, we only increase `发送时延` rather than `传播时延` 

### 3  `传播时延` 
happen out of machine
`传播时延` = `信道长度m` / `电磁波在信道上的传播速率m/s` 
`传播速率` of `光纤` is lower than `传播速率` of `铜线` 

## 2 `利用率` 
### 3  `信道利用率` 
How many percent time in `信道` be used
It isn't high is better , because of `时延` . Like expressway
Not exceed 50% is better

### 3  `网络利用率` 
`加权平均值` of `信道利用率` 
`网络当前的时延` = `网络空闲时的时延` / ( 1 - `网络的利用率(0~1)` )
It isn't high is better , because of `时延` . Like expressway
Not exceed 50% is better
