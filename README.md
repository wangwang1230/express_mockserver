# 介绍

通过express框架用node.js搭建本地服务器，模拟请求接口，获取json数据。

# 1. 准备工作

需要安装node.js（此处省略）  
全局安装express,express-generator  
npm install express --save -g  
npm install express-generator --save -g  

# 2.安装依赖

cd 项目根目录  
npm install  

# 3.启动服务

npm start  

此时访问http://localhost:3000/  

即可看到Welcome to Express的欢迎界面。  

可能会遇到以下问题：（如果没有请忽略以下步骤）  
Port 3000 is already in use  
Port requires elevated privileges  
如果遇到此类问题，可以查看是否是本机默认3000端口已经使用，或者开启了IIS服务。  

关闭IIS服务的步骤如下：  
cmd –> services.msc –>找到World Wide Web Publishing Service 右键 关闭 可禁止启动。ok了！  

# 4.编写并测试接口

   - 在public文件夹下的json文件夹，新建接口json数据，放入测试json代码。  
   - 在本地项目或者其他vue项目中通过fecth进行接口数据调用即可。  
    
    示例：  
    ```html
    fetch("http://localhost:3000/json/data.json").then(function (res) {
        console.log(res);
        if (res.ok) {
            res.json().then(function (data) {
                console.log(data);
            });
        } else {
            console.log("Looks like the response wasn't perfect, got status", res.status);
        }
      }, function (e) {
        console.log("Fetch failed!", e);
      });
      ```
