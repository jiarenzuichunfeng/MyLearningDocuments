# Node.js

* 定义
  * Node.js是一个跨平台的js环境

## fs 文件模块

* 语法

  * 引入fs模块

    * const fs = require（'fs'）

  * 写入文件内容

    * fs.writeFile('文件路径','写入内容',err=>{

         回调函数
      })

  * 读取文件内容

    * fs.readFile('文件路径',（err,data）=>{

         回调函数
      })


