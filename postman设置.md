设置：扳手图标，

常规设置（general settings)

1 Trim keys and values in request body: 如果使用表单数据（form-data）或网址编码（url-encoded）模式将数据发送到服务器，将其切换为ON，将导致任何参数被装饰。
2 SSL certificate verification（仅限本机应用程序），防止应用程序在发出请求时检查ssl证书的有效性。 设置为OFF (https请求，一定要做这个设置）

3 Request timeout in ms(0 for infinity)  请求超时时间， 0表示无穷大。

4 send no-cache header: 发送无缓存头，确保从服务器获取最新的响应

5 send postman token header: 用于绕过chrome中的错误。

https://www.jianshu.com/u/e890cbaec057
