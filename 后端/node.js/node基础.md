# node.js 基础

node.js 顶级对象是 global，globalThis（es2020）

## Buffer

Buffer 中文译为缓冲区，是一个类似于Array的对象，用于表示固定长度的字节序列

* 特点
  * Buffer 大小固定且无法调账
  * Buffer 性能较好，可以直接对计算机内存进行操作
  * 每个元素的大小为一字节
* 创建
  
  * let buf = Buffer.alloc（）
  * let buf = Buffer.allocUnsafe（）
  * let buf = Buffer.from（）

## fs文件读取写入模块

* 导入fs模块

  * const fs = require（‘fs’）
* 读取文件内容

  * fs.readFiles(path，【options】，callback)
  * path：文件路径
  * options：以什么编码格式读取文件，默认utf8
  * callback：通过回调函数拿到读取结果
* 文件流式读取

  * const rs = fs.createReadStream（file）
  * 绑定data事件
    * fs.on（‘data’，chunk=>{}）
    * fs.on（‘end’，）


* 文件写入内容

  

  fs.witeFile(file，data，【options】，callback)

  file：文件路径

  data：文件内容

  options：以什么编码格式读取文件，默认utf8

  callback：通过回调函数拿到读取结果

  文件追加写入

  fs.appendFile（file，data，【options】，callback）

  file：文件路径

  data：文件内容

  options：以什么编码格式读取文件，默认utf8

  callback：通过回调函数拿到读取结果

  文件流式写入

  const ws = fs.createWriteStream（）

  文件重命名

  fs.rename（‘文件路径’，‘文件新路径’，回调函数）

  文件删除

  fs.unlink（‘文件路径’，回调函数）

  fs.rm（‘文件路径’，回调函数）

  创建文件夹

  fs.mkdir（）

  读取文件夹

  fs.readdir（）

  删除文件夹

  fs.rmdir（）

  fs.rm（）

  查看资源信息

  fs.stat（）


## path

拼接归规范绝对路径

path.resolve（） 获取操作系统的路径分隔符

path.sep（）

解析路径并返回对象

path.parse（）

获取路径的基础名称

path.basename（）

获取路径的目录名

path.dirname（）

获取路径的扩展名

path.extname（）

## http

创建服务对象

const server = http.createServer((req(请求报文数据)，res（响应报文数据)⇒{

res.end() 设置响应体

})

监听端口，启动服务

server.listen(3000(端口号),()⇒{

console,log(’服务成功启动’)

})

响应内容中文乱码的解决办法 设置响应头

res.setHeader(’content-type’,’text/html;charset=utf-8’)

提取请求方法

req.method()

提取请求版本

req.httpVersion()

提取请求路径

req.url()

提取URL路径

req(’url’).parse(req.url),pathname()

提取URL查询字符串

req(’url’).parse(req.url,true),query()

提取请求头

req.headers()

提取请求体

req.on(’data’,function(chunk){})

req.on(’end’,function(){})

提取URL新

let url = new URL（）

## 模块化

暴露数据

module.exports = 要暴露的数据（可以暴露任何数据）

module.对外暴露数据的名称 = 要暴露的数据

module.exports = {

要暴露的多个数据

}

使用数据

先导入，在使用





