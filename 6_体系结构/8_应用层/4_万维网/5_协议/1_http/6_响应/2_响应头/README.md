##  响应头
`Content-Base` :

`Content-Encoding` : 
标识返回的数据的压缩格式

`Content-Language` :
use which language to understand `response` 

`Content-Type` :  表明数据的类型
* pre define
`text/plain` 
`text/html` (default)
`text/css` 
`image/jpeg` 
`image/png` 
`image/svg+xml` 
`audio/mp4` 
`video/mp4` 
`application/javascript` 
`application/pdf` 
`application/zip` 
`application/atom+xml` 

* custom (`MIME type`)


`Content-length` :
响应数据的长度

`Etag` :
mark of `url` to `标志` resource of require if change

`Age` :
time which `实体` save in `response` 

`server` :
information of software which `server` use

`Allow` :
`server` support which `request method` 

`Cache-Control` :
相对时间
实现强制缓存
优先级高于`Expires` 
选项更多、设置更加精细、建议采用其做强缓存


`Expires` :
绝对时间
实现强制缓存
