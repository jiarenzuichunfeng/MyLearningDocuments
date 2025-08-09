# express 框架

* 使用express框架
  * 先导入express
    * const express = require（‘express’）
  * 创建应用对象
    * const app = express（）
  * 创建路由
    * app.get（‘路径’，（req，res）=》{res.end()设置响应体}）
    * app.listen(端口号，（）=》{console.log（服务已启动）})
  * 路由
    * app.<方法>(路径，回调函数)
  * 获取请求参数
  * 获取请求方法
    * req.methods
  * 获取url
    * req.url
  * 获取http版本号
    * req.httpVersion
  * 获取请求头
    * req.headers
  * 获取路径
    * req.path
  * 获取查询字符串
    * req.query
  * 获取ip
    * req.ip
  * 获取路由参数
    * req,[oarams.id](http://oarams.id)
  * 原生响应
  * 设置响应码
    * res.statusCode
  * 设置响应信息
    * res.statusMessage
  * 设置响应头
    * res.setHader
  * 设置响应体
    * res.write
    * res.end
  * express 响应  可以链式调用
  * 设置响应码
    * res.status()
  * 设置响应头
    * res.set()
  * 设置响应体
    * res.send()
  * 重定向响应
    * res.redirect()
  * 下载响应
    * res.download()
  * 响应json
    * res.json()
  * 响应文件内容
    * res.sendFile()

## 中间件

* 全局中间件
* 声明全局中间件函数
* function 中间件函数名称（req，res，next）{
* 结构体
* next（） // 放行
* }
* 使用全局中间件函数
* app.use（中间件函数名称）
* 路由中间件
* 声明路由中间件函数
* function 中间件函数名称（req，res，next）{
* 结构体
* next（） // 放行
* }
* 使用路由中间件
* 在需要用路由中间件的路由路径后面加上路由中间件函数
* 静态资源中间件
* app,use(express.static(__dirname+’/public’))
* 注意点
* index.html 文件为默认打开资源
* 如果静态资源与路由规则同时匹配，谁先匹配谁就响应
* 路由响应动态资源，静态资源中间件响应静态资源
* **处理请求体数据**
* express可以使用body-parser 包处理请求体
* 模板引擎  ejs
* express-generator 快速搭建nodeweb服务项目
* 处理文件内容
* express 可以使用formidable 包来处理文件数据

## 浏览器同源策略

* 同源策略：是一个重要的安全策略，它用于限制一个源的文档或它加载的脚本名如同能与另一个源的资源进行交互
* 源：web内容的源由于访问它的URL的方案（协议）、主机名（域名）和端口定义，只有当协议，主机和端口都匹配时，两个对象才具有相同的源

**跨域问题**

* 跨域：从一个源的文档/脚本，加载另一个源的资源就产生了跨域
* 解决方案1（服务端）
  * cors（跨域资源共享），一种基于HTTP头的机制，该机制通过允许服务器标示除了它自己以外的其他源，使得浏览器允许这些源访问加载自己的资源
  * 目标：前后端分离项目，前端和后端不在一个源，还要保证数据通信
  * 服务器端：设置Access-Control-Allow-Origin 响应头字段，允许除了它自己以外的源来访问自己的资源
  * 步骤
    1. 下载 cors
    2. 导入 cors函数
    3. 使用express 的 use 方法 给web服务添加插件功能
    4. 把cors函数调用传入给web服务
* 解决方案2（前段文件提供给浏览器访问）
  * 步骤
    * 前端项目打包给后端
    * 后端把前端包，放入后端服务文件夹下的public文件夹中
