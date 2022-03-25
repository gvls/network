## 2 `协议端口port` 
16 bit
unification standard in any operation system
address of communication of `process` 
`process` occupy `port` 
`transport layer` according `goal port` of data from `network layer` to give data to `process` 

### 3  classification
#### 4   be used by `service` 
* `熟知端口号` | `系统端口号` 
0 ~ 1023
be used by some `process` 
can find in [website](www.iana.org) 
such as:
`FTP` : `21` 
`SMTP` : `25` 
`DNS` : `53` 
`HTTP` : `80` 
`HTTPS` : `443` 

* `登记端口号` 
1024 ~ 49151
must `等级` before use it


#### 4   be used by `client` 
* `短暂端口号` 
49152 ~ 65535
When run `process` , it be dynamic allocation to `process` 
