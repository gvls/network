## 2 `域名系统DNS` 
mapper `域名domain name` to `IP` in order to make people easy to `记住` `"IP"` 
it can analysis `domain name` to `IP` 
because `network` is very big, so `DNS` use `层次式和分布式DNS` 
most `domain name` be analysis in local and less be analysis in `Internet` 
people often name machine which run `域名服务器程序` to `域名服务器` 

### 3  analysis
When user use one `domain name` 
make `domain name` in `报文` 
make this `报文` in `UDP用户数据报` 
make this `用户数据报` in `IP data` 
make this `IP data` in `MAC帧` 
Host send `MAC帧` 
`server` receive and response with `IP` 
if this `server` can't response, this `server` as `client` to request this `domain namr` from other `server` 


### 3  compose
like a tree, root is `根` , next layer is `顶级域名` , next + 1 layer is ...
`叶子` of tree is name of one specific computer
`[....<四级域名>.]<三级域名>.<二级域名>.<顶级域名>` 
`各级域名` under the control of `上一级域名` and `顶级域名` under the control of `ICANN` 
MAX of `<>` is 63 character
`<>` is consist of `number` , `-` and `letter`(not case sensitive)
MAX of total length is 255 character
When people get one `domain name` , people can divide next `domain name` by it self without apply to `上级机构` 

#### 4   `国家顶级域名` 
`cn` : `中国` 
`us` : `美国` 
`uk` : `英国` 
`国家顶级域名下的域名` be define by country
`我国把二级域名` divide to `类别域名` and `行政区域名` 

#### 4   `通用顶级域名` 
`com` : `公司` 
`net` : `网络服务机构` 
`org` : `非盈利组织` 
`int` : `国际组织` 
`edu` : `美国专用教育机构` 
`gov` : `美国的政府部门` 
`mil` : `美国军事部门` 

#### 4   `基础结构顶级域名` 
`arpa` : `反向域名` 

#### 4   `叶子` 
`mail` : `邮件服务器` 
`www` : `网站服务器` 



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

