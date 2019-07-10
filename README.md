# nginx

//起本地服务，反向代理改动

server {
        listen       8088;  //反代理  端口号
        server_name  localhost;    //本地

        location / {  
            proxy_pass   http://192.168.12.203:8089/;    //代理接口（后端传入）
            index  index.html index.htm;     //  默认跳转页面（可写可不写）
        }  
    }
