##  README
### 3  `domain server` 
`一个服务器负责管理的范围叫 区zone` 
`zone` <= `域` 

#### 4   `根域名服务器` 
most important
When `local DNS server` can't handle analysis, `local DNS server` can request to `根域名服务器` (`迭代查询` )
it know `domain name` and `ip` of all `顶级域名服务器` 
if all of it isn't work, `DNS` isn't work
number of `domain name` of `根域名服务器` is 13 but machine of `根域名服务器` is more than 13
when send request to this `server` , `server` will tell you find resource from one `顶级域名` 

#### 4   `顶级域名服务器` 
when send request to this `server` , `server` will tell you find resource from one `domain name server` or get you result of `IP` 

#### 4   `权限域名服务器` 
when send request to this `server` , `server` will tell you find resource from one `权限域名服务器` or get you result of `IP` 

#### 4   `本地域名服务器local DNS server` | `默认域名服务器` 
When host send request of `DNS` , first send to `local DNS server` (`递归查询`)
have `高速缓存`(host also have) which save mapper which be search recently

* `主域名服务器` 
update data only in `主域名服务器` 
at regular intervals, copy data to `辅助域名服务器` 

* `辅助域名服务器` 
When `主域名服务器` isn't work, user can use this `server` 

