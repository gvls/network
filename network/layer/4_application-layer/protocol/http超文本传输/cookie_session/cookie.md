## 2 `cookie` 
it be write in `request` or `response` to control status of `client` 
if `client` forbidden `cookie` and want to use `session` , it will add `sid=<id>` to end of `url` 
It be save in `client` and it may not safe
max of `cookie` is 3k
`coookie` generate by `server` , include `session id` and be save in `client` 

Such as :
`cookie` can save username and password to make user automatic login `server` 

### 3  process
1. `response` of `server` have field `set-cookie` 
2. `server` is inform `client` to save `cookie` 
3. `client` will generate and add `cookie` in next `request`  
4. `server` check `cookie` to `识别` specific `client` and `对比` record on `server` to get status
