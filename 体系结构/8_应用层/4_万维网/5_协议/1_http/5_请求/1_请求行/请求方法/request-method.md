## 2 request method
### 3  `GET` 
data be write in `url` as `parameter` 
length of `url` can't bigger than 256 character
`<url>` : `<protocol>://<socket套接字></path/>[fileName]<parameter>`
> `parameter` : `?<nameOfFirstParameter>=<dataOfFirstParameter>&<nameOfParameter>=<dataOfParameter>[...]`
`url`(`统一资源标识符`) : is a specific `uri`(`统一资源定位器`)
`parameter` be write in end of `url` 
* `parameter` 
if data is letter or number, send directly
if data is ` ` , transform it to `+` 
if data is other character, use `BASE64` to encrypt (`%<16进制>%<16进制>[...]`)
because `url` have length limit, count of `parameter` have limit
basic on `tcp` and send one data which include `http head` and `data` 


* why use
needn't safe for `parameter` 
`侧重` get resource
result of `request` haven't `持续 effect` 
length of all data not longer than 1024 character
main goal is get data from `server` 

* use way
address of browser
`link` in webpage



### 3  `POST` 
`parameter` be packaging in `request body` 
`parameter` : `<nameOfParameter>=<dataOfParameter>[...]` 
`parameter` haven't limit in **theory** but browser have limit in general
basic on `tcp` and send data of `http head` and data of `data`(after `client` receive `response`(100) of `http head` , `client` send it)

* why use
`侧重` : commit data
result of `request` is change resource
result of `request` have `持续 effect` (like add data in database)
If use `get` , `url` will more long
data not use 7 bit `ASCII` 
need more safety on data
main goal is transform data to `server` 
basic on `tcp` and send data of `http head` and data of `data`(after `client` receive `response`(100) of `http head` , `client` send it)

### 3  `HEAD` 
like `get` but `server` only response the `http head` 

Follow `reqeust method` is define in `http 1.1` 

### 3  `PUT` 
upload content

### 3  `DELETE` 
request delete resource

### 3  `TRACE` 
it use in test

### 3  `OPTIONS` 
get all support `request method` of resource of `server` 

### 3  `CONNECT` 
