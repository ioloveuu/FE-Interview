# 前端面试总结：

## 1. https状态码:

### 1XX：信息状态码
- 100 Continue：客户端应当继续发送请求。这个临时相应是用来通知客户端它的部分请求已经被服务器接收，且仍未被拒绝。客户端应当继续发送请求的剩余部分，或者如果请求已经完成，忽略这个响应。服务器必须在请求万仇向客户端发送一个最终响应

- 101 Switching Protocols：服务器已经理解力客户端的请求，并将通过Upgrade消息头通知客户端采用不同的协议来完成这个请求。在发送完这个响应最后的空行后，服务器将会切换到Upgrade消息头中定义的那些协议。
### 2XX：成功状态码
- 200 OK：请求成功，请求所希望的响应头或数据体将随此响应返回
- 201 Created：
- 202 Accepted：
- 203 Non-Authoritative Information：
- 204 No Content：
- 205 Reset Content：
- 206 Partial Content：
### 3XX：重定向
- 300 Multiple Choices：
- 301 Moved Permanently：
- 302 Found：
- 303 See Other：
- 304 Not Modified：
- 305 Use Proxy：
- 306 （unused）：
- 307 Temporary Redirect：
### 4XX：客户端错误
- 400 Bad Request:
- 401 Unauthorized:
- 402 Payment Required:
- 403 Forbidden:
- 404 Not Found:
- 405 Method Not Allowed:
- 406 Not Acceptable:
- 407 Proxy Authentication Required:
- 408 Request Timeout:
- 409 Conflict:
- 410 Gone:
- 411 Length Required:
- 412 Precondition Failed:
- 413 Request Entity Too Large:
- 414 Request-URI Too Long:
- 415 Unsupported Media Type:
- 416 Requested Range Not Satisfiable:
- 417 Expectation Failed:
### 5XX: 服务器错误
- 500 Internal Server Error:
- 501 Not Implemented:
- 502 Bad Gateway:
- 503 Service Unavailable:
- 504 Gateway Timeout:
- 505 HTTP Version Not Supported:

<font color=#0099ff size=7 face="黑体">color=#0099ff size=72 face="黑体"</font>

## 2.理解闭包的面试题目

###什么是closure?
js里构建很多高级应用都要依靠闭包实现，那么闭包是什么？又在什么场景下使用适用？
闭包在书面上是由函数引用其周边状态，即词法环境绑在一起形成的封装组合结构。在js里面 ,每个函数被创建的时候就形成了闭包。

## 3.HTTP request报文结构是怎样的

 rfc2616中进行了定义：

首行是Request-Line包括：请求方法，请求URI，协议版本，CRLF
首行之后是若干行请求头，包括general-header，request-header或者entity-header，每个一行以CRLF结束
请求头和消息实体之间有一个CRLF分隔
根据实际请求需要可能包含一个消息实体 一个请求报文例子如下：


```

GET /Protocols/rfc2616/rfc2616-sec5.html HTTP/1.1
Host: www.w3.org
Connection: keep-alive
Cache-Control: max-age=0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,*/*;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.1916.153 Safari/537.36
Referer: https://www.google.com.hk/
Accept-Encoding: gzip,deflate,sdch
Accept-Language: zh-CN,zh;q=0.8,en;q=0.6
Cookie: authorstyle=yes
If-None-Match: "2cc8-3e3073913b100"
If-Modified-Since: Wed, 01 Sep 2004 13:24:52 GMT
name=ioloveuu&age=25

```

## 4.HTTP response报文结构是怎样的

rfc2616中进行了定义：

首行是状态行包括：HTTP版本，状态码，状态描述，后面跟一个CRLF
首行之后是若干行响应头，包括：通用头部，响应头部，实体头部
响应头部和响应实体之间用一个CRLF空行分隔
最后是一个可能的消息实体 响应报文例子如下：

```

HTTP/1.1 200 OK
Date: Tue, 08 Jul 2014 05:28:43 GMT
Server: Apache/2
Last-Modified: Wed, 01 Sep 2004 13:24:52 GMT
ETag: "40d7-3e3073913b100"
Accept-Ranges: bytes
Content-Length: 16599
Cache-Control: max-age=21600
Expires: Tue, 08 Jul 2014 11:28:43 GMT
P3P: policyref="http://www.w3.org/2001/05/P3P/p3p.xml"
Content-Type: text/html; charset=iso-8859-1
{"name": "ioloveuu", "age": 25}

```
## 5.理解原型和原型链
