# 网络请求http基础知识

* HTTP响应
  * 响应码；
    * 1xx：信息
    * 2xx；成功
    * 3xx；重定向
    * 4xx；客户端错误
    * 5xx；服务的错误
* URL（统一资源定位符）
  * 标准格式：协议；//服务器ip(域名)：端口/路径？携带参数
  * 

# java 网络请求核心类URL和URLConnection

* ```
  System.out.println(url.getHost()); // 主机地址
  System.out.println(url.getProtocol());// 协议
  System.out.println(url.getFile());// 路径+查询字符串
  System.out.println(url.getPath());//路径
  System.out.println(url.getPort());//端口
  System.out.println(url.getQuery());// 查询字符串
  ```

* HttpURLConnection
  * java.net包中提供了访问http协议的类，继承于URLConnection
  * 常见API
    * 设置请求方式
      * setRequestMethod（）
    * 获取服务器响应码
      * int getResponseCode（）
    * 返回URL的输入流，用于读取资源
      * public InputSteam getInputStream（）

# JSON

* 格式key value 键值对
  * 花括号保存对象
  * 方括号保存数组

##  Java操作JSON

* 常见的json'库
  * gson
  * fastjson