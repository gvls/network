## 2 `session` 
It be save in `server` and it use resource of `server` 
when `server` record information of `client` , `server` will generate `session` 
generate in `server` and be save in `server` 
it use low time and high space

### 3  `session id` 
random string to identification `client` 
It generate in `server` and be send between `server` and `client` 

#### 4   way which `client` send to `server` 
* `cookie` 
* `url重写` 

### 3  weakness
easy appear `CSRF跨站请求伪造` 
easy appear `CORS跨域资源共享` 
`server` have high pressure
extension is weakness
