# Drat

* 定义变量
  * var 变量名 = 值 或 类型 变量名 = 值
* 常量
  * const
  * final
  * final和const的区别
    * final是运行时常量const是编译时常量
* 字符串
  * 创建
    * String 变量名 = '值'
    * String 变量名 = "值"
    * String 变量名 = "''值"''       可以换行输出
  * 拼接
    * print('$变量名 $变量名')
    * print(字符串变量名+字符串变量名)
* 整型和浮点型
  * int 变量名 = '值'
  * double 变量名 = '值'
* 布尔类型
  * bool 变量名  = '值'   值只能是true或flase
* 数组 list
  * var 数组名 = [值1，值2]     可以存储任意类型
  * var 数组名 = <类型>[值1，值2]     // 指定存储类型
  * var 数组名 = []; 通过数组名.add('值') 进行添加
  * var 数组名 = List.filled(数组长度，值)   // 创建固定长度的集合
* maps 类似与json对象 key必须是字符串 
  * var 变量名 = {'key1'：值}
  * 变量名['key1']    // 这样调用
  * var p = new Map()
* is 关键词可以判断类型

## 运算符

* \+  加
* \-减
* \* 乘
* / 除
* % 取余
* \~/ 取整
* \! 取反（非）
* && 与
* || 或
* =  ??=  赋值运算 
* 自增自减运算符
  * 前++、-- 先++、--后运算
  * 后++、-- 先运算后++、--

* 复合运算符
  * \+=  加等于
  * \-=减等于
  * \*= 乘等于
  * /= 除等于
  * %= 取余等于
  * \~/= 取整等于

## 条件表达式

* if（）elseif（）else{}
* switch（value）{case value：值 break;case value2：值 break;}
* 表达式？值1：值2
* var a;
  var b;
  b = a ？？ 10    // a有值那就用a，没有用10

* 强制转换
  * 字符串和整型浮点型相互转换
    * 整型浮点型.parse(要转换的变量名(字符串))
    * 整型浮点型.tostring()
  * 布尔型和其他类型相互转换
    * isEmpty：判断字符串是否为空

## 循环

* for（）
* while（）
* do……while（）
* brack和continue的区别
  * brack跳出一层循环continue跳过本次循环

## 列表常用属性和方法

* 常用属性
  * length 长度
  * reversed 反转
  * isEnpty 是否为空
  * isNotEmpty 是否不为空
* 常用方法
  * add 添加一个
  * addAll 添加多个（传递数组）
  * indexOf  查找 传入具体值
  * remove 删除 传入具体值
  * removeAt 删除 传入索引值
  * fillRange 修改
  * insert（index，value）  指定位置插入
  * insertAll（index，list） 指定位置插入多个
  * toList（） 其他类型转为list
  * join（） list 转为字符串
  * split （）字符串转为List
  * foreach （）数组循环
* **Set**是没有顺序且不能重复的集合，所以不能用索引去获取值
* Map

## 定义自定义方法

* 返回类型 方法名称 （形参1，形参2）{return 返回值}
* 方法传参
  * 可选参数
    * 返回类型 方法名称 （形参1，【形参1，形参2】）{return 返回值}
    * 方法名（实参1，实参2） -- 位置要对应
  * 命名参数
    * 返回类型 方法名称 （形参1，{形参1，形参2}）{return 返回值}
    * 方法名（实参1，形参名称：实参）
