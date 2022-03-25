## 2 `token` | `JWT` | `JSON Web TOken` 
identification `client` 
It generate in `server` and be send between `server` and `client` 
it include `data` and `sign` 
It use high time and low space

### 3  `data`
have id of `client` 
#### 4   `UID` 

#### 4   `time` 
current `时间cuo` 


### 3  `sign`
`client` use `密钥` and `HMAC-SHA256算法` to encrypt `data` as `sign` 


### 3  process
1. `client` visit `server` by identification
2. `server` send `ID` to `client` 
3. `client` coding `data`(include `ID`) and `sign` by `BASE64` as data
3. `client` send data to `server` 
4. `server` calculate `data` to `sign` and compare it to `sign` which `client` send


### 3  feature
* not status
* can extend
* support mobile devices
* safe
