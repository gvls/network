## 2 `https` 
make `http` more safe
`https` == `http` + `ssl` 
support one direction authentication(authentication `server`) or two direction authentication(authentication `server` and `client`)

### 3  process
1. browser send `request` to `server` 
2. `server` response `数字证书` to `client` 
3. `client` check `数字证书` 
4. `client` use `通过非对称密钥算法协商好对话密钥`(`对称密钥`) to communication
