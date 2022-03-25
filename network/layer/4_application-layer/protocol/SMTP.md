## 2 `简单邮件传输协议SMTP` 
work in : user send e-mail to `server` of user   and `server` of user send e-mail to `server` of other user
use `TCP` 
use `client` and `server` 

### 3  process
When user A send e-mail to user B

1. user A write e-mail and click button which named send
2. `用户代理` will use `SMTP protocol` to send this e-mail to `server` of user A
3. `server` of user A receive the e-mail and save it to cache
4. `server` of user A request `TCP` connection with `server` of user B
5. if `server` of user B isn't response, after wait some time, `server` of user A request again  otherwise use `SMTP protocol` to send e-mail
6. `server` of user B receive the e-mail and put it to `邮箱` of user B
7. in free time of user B, user B can open `用户代理` use `POP3 protocol` to request e-mail from `server` of user B
