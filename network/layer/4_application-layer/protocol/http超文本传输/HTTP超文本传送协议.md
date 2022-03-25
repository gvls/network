## 2 `超文本传送协议HTTP` 
basic on `C/S` 
basic on `TCP` 
implement `链接` in `万维网` 
define `client用户代理程序`(such as : `broser`) how send request to `server` of `万维网`  and `server` how send response to `client` 
transport : `文本` , `超文本`(browser analysis it) , `声音` , `图像` ...
Face to `事务` 

* Face not connection 
`server` only handle one `request` in one connection

* It is `stateless` 
haven't `持久化` on `requset` and `response` 
we can use `session` or `cookie` to save some status of connection

* we have `tcp` , why we need `http` 
`tcp/ip` : only make one procedure can **reliably connect** with other procedure (they can `识别` transmissive data)
`http` : define **rule of transmission** between two procedure

### 3  `request` 

### 3  `response` 


### 3  process
1. `client` request `DNS` server to get `ip` 
2. `client` get connection of `tcp` to `server` 
3. `client` send `request` to 80 `port` of `server` 
4. `server` send `response` to `client` 
5. If mode of connection is `close`, `server` **release** connection of `tcp` 
> If mode of connection is `keepalive`(`http1.1`), connection **keep sometimes**
6. `client` analysis content of `response` 
7. ...


`HTTP是一种不保存状态,即无状态(stateless)协议。HTTP协议 自身不对请求和响应之间的通信状态进行保存` 
`虽然是无状态协议,但为了实现期望的保持状态功能, 于是引入了Cookie技术。有了Cookie再用HTTP协议通信,就可以管 理状态了。有关Cookie的详细内容稍后讲解。` 
`无连接

　　　　无连接的含义是限制每次连接只处理一个请求。服务器处理完客户的请求，并收到客户的应答后，即断开连接。采用这种方式可以节省传输时间，并且可以提高并发性能，不能和每个用户建立长久的连接，请求一次相应一次，服务端和客户端就中断了。但是无连接有两种方式，早期的http协议是一个请求一个响应之后，直接就断开了，但是现在的http协议1.1版本不是直接就断开了，而是等几秒钟，这几秒钟是等什么呢，等着用户有后续的操作，如果用户在这几秒钟之内有新的请求，那么还是通过之前的连接通道来收发消息，如果过了这几秒钟用户没有发送新的请求，那么就会断开连接，这样可以提高效率，减少短时间内建立连接的次数，因为建立连接也是耗时的，默认的好像是3秒中现在，但是这个时间是可以通过咱们后端的代码来调整的，自己网站根据自己网站用户的行为来分析统计出一个最优的等待时间。` 
`GET

向指定的资源发出“显示”请求。使用GET方法应该只用在读取数据，而不应当被用于产生“副作用”的操作中，` 
`HEAD

与GET方法一样，都是向服务器发出指定资源的请求。只不过服务器将不传回资源的本文部分。它的好处在于，使用这个方法可以在不必传输全部内容的情况下，就可以获取其中“关于该资源的信息”` 
`POST

向指定资源提交数据，请求服务器进行处理（例如提交表单或者上传文件）。数据被包含在请求本文中。这个请求可能会创建新的资源或修改现有资源，或二者皆有。` 
`PUT

向指定资源位置上传其最新内容。
DELETE

请求服务器删除Request-URI所标识的资源。
TRACE

回显服务器收到的请求，主要用于测试或诊断。
OPTIONS

这个方法可使服务器传回该资源所支持的所有HTTP请求方法。用'*'来代替资源名称，向Web服务器发送OPTIONS请求，可以测试服务器功能是否正常运作。
CONNECT

HTTP/1.1协议中预留给能够将连接改为管道方式的代理服务器。通常用于SSL加密服务器的链接（经由非加密的HTTP代理服务器）。` 


`GET提交的数据会放在URL之后，也就是请求行里面，以?分割URL和传输数据，参数之间以&相连，如EditBook?name=test1&id=123456.（请求头里面那个content-type做的这种参数形式，后面讲） POST方法是把提交的数据放在HTTP包的请求体中.` 
`

GET提交的数据大小有限制（因为浏览器对URL的长度有限制），而POST方法提交的数据没有限制.

GET与POST请求在服务端获取请求数据方式不同，就是我们自己在服务端取请求数据的时候的方式不同了，这句废话昂。
` 
`
    传送协议。
        层级URL标记符号(为[//],固定不变)
	    访问资源需要的凭证信息（可省略）
	        服务器。（通常为域名，有时为IP地址）
		    端口号。（以数字方式表示，若为HTTP的默认值“:80”可省略）
		        路径。（以“/”字符区别路径中的每一个目录名称）
			    查询。（GET模式的窗体参数，以“?”字符为起点，每个参数以“&”隔开，再以“=”分开参数名称与数据，通常以UTF8的URL编码，避开字符冲突的问题）
			        片段。以“#”字符为起点
				` 


### 3  process
1. build `TCP` connection
2. `client` send request of `HTTP` 
3. `server` send response of `HTTP` 
...
4. disconnect connection of `TCP` 
```
浏览器向 DNS 服务器请求解析该 URL 中的域名所对应的 IP 地址;
\1. 客户端连接到Web服务器
一个HTTP客户端，通常是浏览器，与Web服务器的HTTP端口（默认为80）建立一个TCP套接字连接。例如，http://www.baidu.com。

\2. 发送HTTP请求
通过TCP套接字，客户端向Web服务器发送一个文本的请求报文，一个请求报文由 请求行、请求头部、空行 和请求数据4部分组成。

\3. 服务器接受请求并返回HTTP响应
Web服务器解析请求，定位请求资源。服务器将资源复本写到TCP套接字，由客户端读取。一个响应由 状态行、响应头部、空行 和响应数据 4部分组成。

\4. 释放连接TCP连接
若connection 模式为close，则服务器主动关闭TCP连接(defualt: 短连接)，客户端被动关闭连接，释放TCP连接;若connection 模式为keepalive，则该连接会保持一段时间，在该时间内可以继续接收请求;

\5. 客户端浏览器解析HTML内容
客户端浏览器首先解析状态行，查看表明请求是否成功的状态代码。然后解析每一个响应头，响应头告知以下为若干字节的HTML文档和文档的字符集。客户端浏览器读取响应数据HTML，根据HTML的语法对其进行格式化，并在浏览器窗口中显示。
```

### 3  work type
* `非流水线方式` 
`client` send request after receive response of pre request

* `流水线方式` 
`client` send request needn't after receive response of pre request

