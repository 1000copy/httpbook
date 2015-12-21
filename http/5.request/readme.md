#HTTP 请求

HTTP协议只允许客户端发起请求，也只允许服务器针对请求返回响应。我们已经看到了请求的样例，现在我们具体了解HTTP请求消息的构成。请求消息包括一个首行，首部，请求主体。


        Request       = Request-Line              CRLF
                        *Header					  CRLF
                        CRLF
                        [ message-body ]          
#首行

请求行由请求方法，请求URL，一个HTTP版本构成。

        Request-Line   = Method SPACE Request-URI SPACE HTTP-Version CRLF

#请求方法

HTTP/1.1支持方法包括：

               Method         =          "OPTIONS"         
                      | "GET"               
                      | "POST"               
                      | "PUT"                 
                      | "DELETE"          
                      | "TRACE"                
                      | "CONNECT"              
                      | extension-method
       extension-method = token

GET方法是HTTP 0.9协议支持的唯一HTTP请求方法，用来指示传递一个指定URL关联的资源。随后，为了优化的目的，HEAD方法被加入进来；为了支持像服务器提交数据，引入了POST，PUT,DELETE方法。分别在语义上表达更新，创建和删除指定的资源。对于任何一个通用目的的HTTP服务器，GET,HEAD方法是必须实现的，其他的方法都是可选实现的。可以采用OPTIONS方法去查询一个服务器资源所支持的请求方法清单。

采用文本的首部，让HTTP变得容易扩展。只要客户端和服务器做好约定，就可添加自己需要的新的请求方法。不过，这个部分的内容，不是本书需要讨论的。

# 消息主体 message-body
会单独分章说明

#稍作总结：


- GET 表示我要请求一个由URI指定的在服务器上的资源。
- POST表示我要更新一个由URI指定的资源
- PUT表示我要创建一个由URI指定的资源
- DELETE表示我要删除一个由URI指定的资源。
- HEAD 和GET一样，但是仅仅返回指定资源响应的头部分，而不必返回响应主体
- OPTIONS 查询目标资源支持method的清单。
- TRACE 查询到目标资源经过的中间节点。用于测试。
- CONNECT 建立一个到URI指定的服务器的隧道。 

#如下为本章节目录。

- [GET请求和HEAD请求](get+head.md)
- [POST请求](post.md)
- [OPTIONS请求](options.md)
- [PUT请求和DELETE请求](put+delete.md)
- [CONNECT请求](connect.md)



