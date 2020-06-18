# Job-Summary系列
 Job-Summary系列主要总结我在工作中一些场景实现的策略，以及我所用到的所用到的技术。

##### 第一部分  request_process

```java

本部分主要功能是：实现访问拦截，以及前后端分离下使用token登录的解决方案。
   （1）访问拦截的实现策略：
       主要使用@interface（自定义的注解）与拦截器配合使用实现URL的访问拦截。
   （2）前后端分离下使用token登录的解决策略：
      1.前端登录，将用户的密码经过base64加密同账号一起提交到后端服务器.
      2.后台服务器将对应的账号信息经过系列处理（数据库中并不是单纯的保存密码经过加密后的信息）同前台
    提交的信息进行对比。
      3.对比无误后，利用提交的账号+事先定义好的秘钥+token失效时间返回后台。
      4.前台将后台传递获取的token存储在localstorage，以及vuex中。
      5.前台请求后台地址，在axios请求头中携带token，后台拦截器根据是否有自定义的注解展开拦截，拦截
    器并根据请求头中是否有token，以及token的正确性
    
    
    
    
```








