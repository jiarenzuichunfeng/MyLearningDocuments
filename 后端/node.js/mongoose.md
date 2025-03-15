# mongoose

mongoose 使用

先安装mongoose

导入mongoose

const mongoose  = require（‘mongoose ’）

连接mongoose 服务

mongoose.connect（‘mongodb://127.0.0.1：27017’/数据库名）

设置回调

on和once的区别

on重启服务多次调用，once只调用一次

设置连接成功回调

mongoose.connection.once(’open’,()⇒{})

设置连接错误回调

mongoose.connection.on(’error’,()⇒{})

设置连接关闭回调

mongoose.connection.on(’close’,()⇒{})

下面所有操作都是在连接成功回调函数中进行

创建文档的结构对象

let 文档名 = new mongoose.Schema（{

属性值：属性类型

}）

创建模型对象

let 模型对象名 = mongoose..model(’要操作的集合名称（如果集合不存在则会使用集合名称的复数，创建集合）‘，文档对象)

新增数据

模型对象名.create（{

要插入的数据，要跟声明跟文档对象结构一样的数据

}，（err，data）=》{}）

关闭数据库连接

mongoose.disconnect（）

mongoose提供的数据类型

String 字符串

Number 数字

Boolean 布尔值

Array 数组 也可以用【】来标识

Date 日期

Buffer Buffer对象

Mixed 任意类型，需要使用mongoose.Schema.Tyoes.Mixed指定

Objectld 对象id  需要使用mongoose.Schema.Tyoes.Mixed指定

Decimal128 高精度数字 需要使用mongoose.Schema.Tyoes.Mixed指定

mongoose.字段验证

使用字段验证

let 文档名 = new mongoose.Schema（{

属性值：{

type：类型，

required：设置是否为必填项 Boolan，

default：默认值，

enum：【’男‘，’女‘】设置的值必须是数组中的，

unique：是否为唯一值 Boolan，   需要重建集合

}

}）

mongoose 删除文档

删除一条数据

模型对象名.deleteOne({要删除的字段名：字段值},{err,data}⇒{})

批量删除

模型对象名.deleteMany({要删除的字段名：字段值},{err,data}⇒{})

mongoose更新文档

更新一条数据

模型对象名.updateOne({更新条件}，{要更新的字段名：字段值},{err,data}⇒{})

批量更新

模型对象名.updateMany({跟新条件},{要更新的字段名：字段值}，{err,data}⇒{})

mongoose读取文档

读取一条数据

模型对象名.findOne({读取条件}，{err,data}⇒{})

根据id获取文档

模型对象名.findById({更新条件}，{要更新的字段名：字段值},{err,data}⇒{})

批量获取

模型对象名.find({读取条件}，{err,data}⇒{})

读取所有

模型对象名.find({err,data}⇒{})

mongoose条件控制

运算符

在mongodb不能 > < ≥ ≤ ≠ 等运算符，需要使用替代符号

'>'使用$gt

<使用$lt

≥ 使用$gte

≤ 使用$lte

≠ 使用$ne

逻辑运算

逻辑与

$and

逻辑或

$or

正则匹配

条件中可以直接使用js的正则语法

个性化读取

字段筛选    select（属性名：属性值只能为1（选中）0（不选中））

模型对象名.find().select({属性名：属性值,属性名：属性值}).exec(function(err,data){

操作

})

数据排序    sort（{属性名：属性值只能为1（升序）-1（倒叙）}）

模型对象名.find().sort({属性名：属性值}).exec(function(err,data){

操作

})

数据截断         skip(数字)数字多少就是跳过多少条  limit（数字）数字多少就是需要多少条

模型对象名.find().skip(10).limit(10).exec(function(err,data){

操作

})

## 代码模块化

封装mongose公共方法

导入mongoose

const mongoose  = require（‘mongoose ’）

连接mongoose 服务

mongoose.connect（‘mongodb://127.0.0.1：27017’/数据库名）

设置回调

on和once的区别

on重启服务多次调用，once只调用一次

设置连接成功回调

mongoose.connection.once(’open’,()⇒{})

设置连接错误回调

mongoose.connection.on(’error’,()⇒{})

封装暴露一个函数

module.exports = (success,error) ⇒ {

导入mongoose

const mongoose  = require（‘mongoose ’）

连接mongoose 服务

mongoose.connect（‘mongodb://127.0.0.1：27017’/数据库名）

设置回调

on和once的区别

on重启服务多次调用，once只调用一次

设置连接成功回调

mongoose.connection.once(’open’,()⇒{

sucess()

})

设置连接错误回调

mongoose.connection.on(’error’,()⇒{

error()

})

}

使用这个函数

const db = require（封装方法的文件路径）

db.(()⇒{

创建文档的结构对象

let 文档名 = new mongoose.Schema（{

属性值：属性类型

}）

创建模型对象

let 模型对象名 = mongoose..model(’要操作的集合名称（如果集合不存在则会使用集合名称的复数，创建集合）‘，文档对象)

新增数据

模型对象名.create（{

要插入的数据，要跟声明跟文档对象结构一样的数据

}，（err，data）=》{}）

},()⇒{

})

代码模块化实现方法

1.把mongoose公共方法抽离为一个文件，在向外共享一个函数，

2.把mongoose的文档模型和模型对象抽离，向外共享模型对象