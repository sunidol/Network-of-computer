**HTTP(HyperText Transfer Protocol，超文本传输协议)最早是计算机与计算机之间沟通的一种标准协议，这种协议限制了通讯内容的格式以及各项内容的含义**


随着时代的发展，技术的变迁，这种协议现在广泛应用在各种领域，故一般现在称HTTP为**端与端之间的通讯协议**

Web属于B/S架构的应用软件，在B/S架构中，浏览器与服务器沟通的协议就是HTTP协议。

*PS:应用软件架构一般分为两种*

    B/S架构---->Browser(浏览器)<---->Server(服务器)，这种软件都是通过浏览器访问一个网站使用，服务器提供数据存储等服务
    
    C/S架构---->Client(客户端)<---->Server(服务器)，这种软件通过安装一个软件到电脑，然后使用，服务器提供数据存储等服务
    
 ### 1.1 协议约定的内容
 
 请求/响应报文格式
 
 请求方法--->GET/POST/etc.
 
 响应状态--->200/ 404 / 302 / 304 / etc.
 
 预设的请求/响应头
 
 ### 1.2 协议约定的形式
 
 1、客户端通过随机端口与服务端某个固定端口（一般为80）*建立连接* 三次握手
 
 2、客户端通过这个连接发送请求到服务端
 
 3、服务端监听端口得到客户端发送过来的请求
 
 4、服务端通过连接响应给客户端状态和内容
 
 **PS：HTTPS不是一个新的协议，而是更安全的HTTP协议，它使得请求报文和响应报文加密后再传到服务端或客户端**
 
 ### 2.1 报文
     
 #### 2.1.1 请求报文
 
 ![image](https://github.com/sunidol/Network-of-computer/blob/master/image/pic1.jpg)
 
 ![image](https://github.com/sunidol/Network-of-computer/blob/master/image/pic2.jpg)
 
 请求行：请求方式 + 空格 + 请求路径 + 空格 + HTTP 协议版本
 
 请求头：客户端想要告诉服务端的一些额外信息，以下为常见的请求头
 
 ![image](https://github.com/sunidol/Network-of-computer/blob/master/image/pic3.jpg)
 
 请求体：这次请求客户端想要发送给服务端的数据正文，一般在 GET 请求时很少用到，因为 GET 请求主观上都是去“拿东西”。
 
 #### 2.1.2 响应报文
 
 ![image](https://github.com/sunidol/Network-of-computer/blob/master/image/pic4.jpg)
 
 状态行:HTTP 协议版本 + 空格 + 状态码 + 空格 + 状态描述
 
 响应头:服务端想要告诉客户端的一些额外信息，常见的有以下
 
 ![image](https://github.com/sunidol/Network-of-computer/blob/master/image/pic5.jpg)
 
 如果需要在程序中设置自定义的响应头（不是预设的），建议使用 X-Property-Name
 
 响应体:这次请求服务端想要返回给客户端的数据正文，一般返回的都是 HTML，也可以返回 JavaScript 或者 CSS（需要修改响应头中的响应类型）。
 
 ### 2.2 请求方式
 
 + GET - 从指定的资源请求数据
 + POST - 向指定的资源提交要被处理的数据
 
 #### GET 方法
 
 请注意，查询字符串（名称/值对）是在 GET 请求的 URL 中发送的：

    /test/demo_form.asp?name1=value1&name2=value2
    
 #### POST 方法
 
 请注意，查询字符串（名称/值对）是在 POST 请求的 HTTP 消息主体中发送的：
 
    POST /test/demo_form.asp HTTP/1.1
    Host: w3schools.com
    name1=value1&name2=value2
 
 #### 比较GET与POST
 
  ![image](https://github.com/sunidol/Network-of-computer/blob/master/image/pic6.jpg)
  
 
 ### 2.3 状态码
 
 状态代码由三位数字组成，第一个数字定义了响应的类别，且有五种可能取值。
 
  + 1xx：指示信息 —— 表示请求已接收，继续处理。
  + 2xx：成功 —— 表示请求已被成功接收、理解、接受。
  + 3xx：重定向 —— 要完成请求必须进行更进一步的操作。
  + 4xx：客户端错误 —— 请求有语法错误或请求无法实现。
  + 5xx：服务器端错误 —— 服务器未能实现合法的请求。
 
 常见状态代码、状态描述的说明如下：
  + 200 OK：客户端请求成功。
  + 301 Moved Permanently: 所请求的页面已经转移至新的url。
  + 302 Found: 所请求的页面已经临时转移至新的url。
  + 303 See Other: 所请求的页面可在别的url下被找到。
  + 400 Bad Request：客户端请求有语法错误，不能被服务器所理解。
  + 401 Unauthorized：请求未经授权，这个状态代码必须和  WWW-Authenticate 报头域一起使用。
  + 403 Forbidden：服务器收到请求，但是拒绝提供服务。
  + 404 Not Found：请求资源不存在，举个例子：输入了错误的URL。
  + 500 Internal Server Error：服务器发生不可预期的错误。
  + 503 Server Unavailable：服务器当前不能处理客户端的请求，一段时间后可能恢复正常。
