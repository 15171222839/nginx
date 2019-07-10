# nginx

//起本地服务，反向代理

//改动页面nginx.conf
//路径     nginx\nginx\conf

    server {
        listen       8088;  //反代理  端口号
        server_name  localhost;    //本地

        location / {  
            proxy_pass   http://192.168.12.203:8089/;    //代理接口（后端传入）
            index  index.html index.htm;     //  默认跳转页面（可写可不写）
        }  
    }
    
    
// 其他地方无需改动



//页面接口调用

   var api = 'http://localhost:8088'
   
  //地区
  
  function loc(){
  
    $.ajax({
    
      type:"get",
      
      url: api+"/capita/largeScreenData/getRegionInfo",
      
      success:function(res){
      
        console.log(res)
        
      }
      
    })
    
  }
  
  loc()
