# Ajax
Ajax
   
     responseText  最为响应主体被返回的文本
     responseXML  如果响应的内容类型是text/xml或者 application/xml,
                  这个属性中将保存包含响应数据的XML DOM文档                      
     status 响应HTTP状态
     statusText  http状态说明
    
     readyState	
		   存有 XMLHttpRequest 的状态。从 0 到 4 发生变化。
		
      0: 请求未初始化
      1: 服务器连接已建立
      2: 请求已接收
      3: 请求处理中
      4: 请求已完成，且响应已就绪

      status	
       200: "OK"
       404: 未找到页面
     
    首先检查readyState   再看status 响应HTTP状态,如果是200就成功,
    此时responseText属性内容已经就绪,而且在内容类型正确的情况下,responseXML也能够访问了,
     
    







