# 请求消息 

HTTP协议只允许客户端发起请求，也只允许服务器针对请求返回响应。我们已经看到了请求的样例，现在我们具体了解HTTP请求消息的构成。请求消息包括一个首行、首部、请求主体。


        Request       = Request-Line              CRLF
                        *Header           CRLF
                        CRLF
                        [ message-body ]          
##首行

请求行由请求方法、请求URL、一个HTTP版本构成。

        Request-Line   = Method SPACE Request-URI SPACE HTTP-Version CRLF

##请求方法

HTTP/1.1支持方法包括：

               Method         =          "OPTIONS"         
                      | "GET"               
                      | "HEAD"               
                      | "POST"               
                      | "PUT"                 
                      | "DELETE"          
                      | "TRACE"                
                      | "CONNECT"              
                      | extension-method
       extension-method = token

HTTP 0.9协议版本中，GET方法是唯一被支持的HTTP请求方法，用来向服务器请求一个指定URL关联的资源。随后，为了优化的目的，HEAD方法被加入进来；为了支持向服务器提交数据，引入了POST、PUT、DELETE方法。分别在语义上表达更新、创建和删除指定的资源。对于任何一个通用目的的HTTP服务器，GET、HEAD方法是必须实现的，其他的方法都是可选实现的。可以采用OPTIONS方法去查询一个服务器资源所支持的请求方法清单。

## 首部

首部包括零到多个首部行，每个首部行由“：”分隔，左边的文本被称为首部字段，右边的文本被称为首部值。采用文本的首部让HTTP变得容易扩展。只要客户端和服务器做好约定，就可添加自己需要的新的请求方法。不过，对于如何扩展的内容，不在本书需要讨论的范围。

## 消息主体 message-body
消息主体就是消息的承载内容。单独分章节随同请求方法来做说明

##稍作总结：


- GET 表示我要请求一个由URI指定的在服务器上的资源。
- PUT方法 表示如果指定URI资源不存在就创建它，否则就修改它。 
- POST方法 表示要创建一个新的子资源，或者更新一个存在的资源。
- DELETE表示我要删除一个由URI指定的资源。
- HEAD 和GET一样，但是仅仅返回指定资源响应的头部分，而不必返回响应主体
- OPTIONS 查询目标资源支持method的清单。
- TRACE 查询到目标资源经过的中间节点。用于测试。
- CONNECT 建立一个到URI指定的服务器的隧道。   
