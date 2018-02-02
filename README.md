# Ajax
  Ajax
   
		      一个完整的HTTP响应由状态码，响应头集合和响应主体组成，

		      使用这两个方法可以查询到响应头信息	 
		      getResponseHeader()
		      getAllResponseHeaders()
	
	
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


		    响应主体可以从responseText属性中得到文本形式，
		    从responseXML属性中得到的是Document形式的




