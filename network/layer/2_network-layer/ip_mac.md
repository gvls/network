## 2 `ip mac` 
`MAC帧` use in : `data link layer` and `next layer` 
`IP data` use in : `network layer` and `pre layer` 

We can't get `IP` information from `MAC帧` 
after `MAC帧` transform to `IP data`  we can the `IP` information
We can't get `MAC` information from `IP data` 

### 3  process
1. When host | `router` receive a `MAC帧` 
2. according to `MAC` of `head` to decide if save
3. if save, unlock `MAC帧` to `IP data` and get `IP` information
