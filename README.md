一、	小程序端代码框架
 
其中utils目录下的api.js和util.js为封装的公共函数，api用于各个页面调用，util为更底层的微信接口的封装。

在api中通过函数的url与java服务器端交互，如：
 

二、	服务器端代码框架
 
服务器端采用springBoot+Spring+Mybatis,没有web.xml。所有配置通过注解形式，采用maven形式进行依赖包的管理，编译依赖包找到maven地址添加到pom.xml文件中即可。
代码下载到本地后PortraitApplication类
 
启动后即可启动服务。
注意mysql配置与application.properties文件中相关一致，建表语句见back.sql

三、	小程序与服务器的交互
小程序接口在util.js的fetch函数中对微信接口做了一次封装，所有java服务器端返回的数据要按照这个形式进行：
小程序端处理
 

 
服务器端按照Map<String, Object>形式返回，小程序可以直接处理返回的data
 
