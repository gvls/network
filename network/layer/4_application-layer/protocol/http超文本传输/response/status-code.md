## 2 status code
### 3  `1xx` 
`request` still in handle


### 3  `2xx` 
`request` is success
* 200
request is success


### 3  `3xx` 
`server` need more option of `client` 
* 301
current resource is be allocation new `url` 
* 302
current resource is be allocation new `url` in temporary


### 3  `4xx` 
`client` error : `request` is error
* 400
`request` have some error and `server` can't understand
* 401
`request` not be `授权` and `request` need add `Authenticate` 
* 403
`server` receive the `request` but it refuse offer service to `client` 
* 404
resource which `client` request is not exist or `client` not have permission


### 3  `5xx` 
`server` error : `server` can't handle
* 500
`server` have some not expect error
* 503
`server` can't handle `request` in now (after some time **may** recover)
