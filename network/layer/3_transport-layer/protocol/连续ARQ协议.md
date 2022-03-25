## 2 `连续ARQ协议` | `自动重传请求ARQ` 
update for `停止等待协议` : improve `利用率` of `channel` (`流水线传输`)
`sender` send next data needn't after receive `confirm` of data

`sender` send data from 1 to XXX
* `发送窗口` 
`发送窗口` have more than one data
data in `发送窗口` can be order and continuous send needn't after receive `confirm` of itself
When `sender` receive one `confirm` of data in `发送窗口` , `发送窗口` move next(include data of `窗口外` and exclude data of `窗口内最前面`)

* `累积确认` 
`receiver` needn't send `confirm` for all data
`receiver` send `confirm` of final data(the last data which `按序到达` and `receiver` receive in `一段时间` )
it is easy to implement
When `confirm` is lose, `sender` needn't resend (`更后面的数据的确认到达了` )
`receiver` can't give information which `receiver` receive to `sender` 

