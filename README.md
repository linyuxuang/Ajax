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


overrideMimeType()方法

	  xmlhttp = new XMLHttpRequest();   

	  保证浏览器发送的串行化数据长度正确，针对某些特定版本的mozillar浏览器的BUG进行修正 

	  如果来自服务器的响应没有 XML mime-type 头部，则一些版本的 Mozilla 浏览器不能正常运行。

	  对于这种情况，httpRequest.overrideMimeType('text/xml'); 语句将覆盖发送给服务器的头部，
	  强制text/xml 作为 mime-type

	 if (xmlhttp.overrideMimeType) {   

	  xmlhttp.overrideMimeType("text/xml");   

	}



ajax跨域集中方法



          一，传统的ajax方法

		js代码
		查看复制打印?

		    $("#ajax").click(function(){  
		     $.ajax({  
		     type: "POST",  
		     url: "http://manual.51yip.com/test2.php",  
		     data: 'name=ajax',  
		     dataType:"json",  
		     success: function(data){  
		     $('#Result').text(data.name);  
		     }  
		     });  
		     });  


		test2.php代码
		 
		    <?php  
		       //允许 blog.51yip.com提交访问 
		       header("Access-Control-Allow-Origin:http://blog.51yip.com"); 
		         //允许任何访问  
		      //header("Access-Control-Allow-Origin:*");    
		    echo json_encode($_POST);  



          
          二，ajax jsonp

		js代码

		    $("#jsonp").click(function(){  
		     $.ajax({  
		     url: 'http://manual.51yip.com/test1.php',  
		     data: {name: 'jsonp'},  
		     dataType: 'jsonp',  
		     jsonp: 'callback',      //为服务端准备的参数  
		     jsonpCallback: 'getdata',   //回调函数  
		     success: function(){  
		     alert("success");  
		     }  
		     });  
		     });  

		    function getdata(data){  
		     $('#Result').text(data.name);  
		    }  

		  test1.php

		    <?php  
		       //callback根js端要对应，不然会报错的  
		     if(isset($_GET['name']) && isset($_GET['callback']))
		     {  
		      //格式固定的，为什么这样，不清楚 
		     echo $_GET['callback']. '(' . json_encode($_GET) . ');';   
		     }  
		    ?> 



























