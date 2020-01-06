基于登陆请求之外的任何操作，进行想往后台发送请求，都需要进行身份验证。 因为有些页面，是给特定的人看的。
postman的authorization，验证请求的用户，是否有权限从服务器访问所需的数据，发送请求时，通常必须包含参数以确保
请求有权访问并返回所需的数据。

鉴权，通常需要核对的信息，主要包括一些：
1 密码，只有本人才会知道的字符串信息
2 动态令牌，仅限本人吃用的设备内显示的一次性密码
3 数字证书，仅限本人（终端）持有的信息

HTTP使用的认证方式：

2.1 BASIC认证
step1: 当请求的资源需要basic认证时，服务器返回状态码401 Authorization Required， 并返回WWW-Authenticate字段， 该字段包含BASIC认证方式，以及Request-URI安全
域字符串(realm)
step2: 接收到状态码401的客户端，将用户ID和密码发送给服务器。 发送的字符串内容是由用户ID和密码构成，两者中间以冒号：连接，再经过base64编码处理
比如：用户id为guest, 密码是guest， 连接起来是guest:guest，然后经过base64编码，最后的结果是ZCVLc3Q6Z3VLc3Q=， 
然后把这串字符写入Header字段Authorization后，发送请求
step3: 接收到包含authorization请求的服务器，会对认证信息的正确性进行验证，如果验证通过，则返回一条包含Request-uri资源的响应。

2.2 DIGEST认证（摘要认证）


2.3 Cookie Auth
    Cookie 认证机制： 一次请求认证在服务端创建session对象（绑定用户的id和session值），同时在客户端的浏览器创建一个cookie对象，通过客户端带上来的cookie对象与服务端的session对象进行匹配。
    默认情况，当关闭浏览器的时候，cookie会被删除的。但可以通过修改cookie的expire time使cookie在一定时间内容有效。
    
    step1: 客户端第一次登陆，把用户id和密码登陆信息，post到后台。 
    
    step2: 服务器会发放一个识别用户的Session ID，通过验证从客户端发送过来的登陆信息进行验证， 

2.4 Token Auth


    
