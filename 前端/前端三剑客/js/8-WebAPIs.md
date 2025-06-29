# WebAPIs

## DOM操作

### MDN

* [MDN Web Docs](https://developer.mozilla.org/zh-CN/)

### 什么是DOM

* DOM-文档对象模型
* 操作网页文档，开发网页特效和实现用户交互
* DOM的核心思想就是把网页内容当做对象来处理，通过对象的属性和方法对网页内容操作
* document对象
  * 是DOM里提供的一个对象，是DOM顶级对象
  * 作为网页内容的入口
  * 所以它提供的属性和方法都是用来访问和操作网页内容结构的

### 获取元素

* 通过css选择器获取DOM元素
  * document.querySelector('css选择器')
  * document.querySelectorAll('css选择器')
* 其他获取DOM元素方法
  * document.getElementByld() 根据id获取元素，单个元素
  * document.getElementsByTagName() 根据标签名获取元素，伪数组
  * document.getElementsByClassName() 根据类名获取元素，伪数组
  * document.getElementsByName() 根据name属性值获取元素，伪数组

### 操作元素

* 操作元素内容
  * document.innerText 不会解析标签
  * document.innerHTML 会解析标签
*  操作元素常见属性
  * document.属性 = 值
* 操作元素样式属性
  * 通过style属性操作css
    * document.style.样式属性 = 值
  * 通过类名操作元素样式
    * 声明一个css类，然后替换类
  * 通过className操作元素样式
    * 也得先声明一个要添加的css类
    * 新增
      * document.classList.add('类名')
    * 删除
      * document.classList.remove('类名')
    * 切换
      * document.classList.toggle('类名')

### 自定义属性

* data-自定义属性
*  获取自定义属性
  * document.querySelector('css选择器').dataset.自定义属性

### 定时器

* 开启定时器
  * 间隔函数
    * setInterval（函数,间隔时间）
* 关闭定时器
  * clearInterval（定时器）

## 事件

* 事件是程序在运行的时候，发生的特定动作或着特定的事情

### 事件监听

* 元素对象.addEventListener('事件类型',事件处理函数) 不会覆盖
* 元素对象.on事件类型 = 事件处理函数     会覆盖同名事件

### 事件类型

#### 鼠标事件

* click 鼠标点击
* mouseenter 鼠标经过
* moseover 鼠标经过 有冒泡
* mouseleave 鼠标离开
* mouseout 鼠标离开 有冒泡

#### 焦点事件

* focus 获取焦点
* blur 失去焦点

#### 键盘事件

* keydown 键盘按下
* keyup 键盘抬起

#### 文本事件

* input 表单value 被修改时触发

#### 事件对象

* 这个对象里有事件触发时的相关信息，包含属性和方法

* 在注册时间中，回调函数的第一个参数就是事件对象 一般命名为event 、ev、e

  ##### 事件对象的常用属性

  * altkey 事件发生时，是否按下alt按键
  * ctrlkey 事件发生时，是否按下ctrl按键
  * shiftkey 事件发生时，是否按下shift按键
  * offsetX 事件发生时，鼠标相对于事件源的x坐标
  * offsetY 事件发生时，鼠标相对于事件源的y坐标
  * target 事件源对象
  * pageX 事件发生时，鼠标相对于网页的x坐标
  * pageY 事件发生时，鼠标相对于网页的y坐标
  * clientX 事件发生时，鼠标相对于视口的x坐标
  * clientY 事件发生时，鼠标相对于视口的y坐标
  * key 如果是键盘事件，则事件对象中包含该属性，表示事件发生时，按下的是什么键

## 事件流

* 事件流是事件完整执行过程中的流动路径
* 当触发事件时，会经历两个阶段，分别是捕获阶段、冒泡阶段
* 事件捕获感念
  * 当一个元素的事件被触发时，会从DOM的根元素开始依次调用同名事件（从外到里）
  * 写法
    * 元素对象.addEventListener('触发事件',处理函数，true（在捕获阶段）不写或写false（冒泡阶段）)
* 阻止冒泡/捕获
  * 事件对象.sotpPrioagation()

## 事件委托

* 事件委托：原本需要注册在子元素的事件委托给父元素，让父元素担当事件监听的职务
* 优点：减少注册次数，可以提高程序性能
* 原理：事件委托其实是利用事件冒泡的特点
  * 给父元素注册事件，当我们触发子元素的时候，会冒泡到父元素身上，从而触发父元素的事件
* 事件委托如何获取点击元素
  * 事件对象.targent

## 阻止默认行为

* 阻止元素发生的默认行为
* 写法
  * 事件对象.oreventDefault()

## 移除事件监听

* 移除事件处理函数，也称为解绑事件
* on事件方式
  * 直接使用元素对象.on事件类型 = null
  * 只有冒泡阶段
* addEventListener
  * removeEventListener(事件类型，事件处理函数，[捕获或冒泡阶段])   匿名函数无法解绑

## 页面加载事件

* 加载外部资源，加载完毕时触发的事件
* 写法
  * window.addEventListener('load',处理函数) 解析全部资源（css、图片等）
  * document.addEventListener('DOMContentLoaded',处理函数) 解析完HTML就触发

## 页面滚动事件

* 滚动条在滚动的时候持续触发的事件
* 写法
  * window.addEventListener('scroll',处理函数)
  * 监听某个元素的内部滚动直接加元素身上
* 获取html标签
  * docment.docmentElement()
* 获取滚动距离
  * scrollLeft 获取往左滚动了多少
  * scrollTop 获取往上滚动了多少

## 页面尺寸事件

* 写法
  * window.addEventListener('resize',处理函数)
* 获取视口宽度addEventListener('load',处理函数)
  * docment.docmentElement.clientWidth 宽度
  * docment.docmentElement.clientHegth 高度

##元素尺寸与位置

* 获取元素宽高
  * 元素对象.clientWidth  宽 包含width和podding
  * 元素对象.clientHegth 高 包含width和podding
  * 元素对象.offsetWidth 包含padding和border
  * 元素对象.offsetHegth 包含padding和border
* 获取位置
  * offsetLeft和offsetTop
  * 获取元素距离自己定位父级元素的左、上距离，跟绝对定位类似
  * 如果父级都没有定位则以浏览器文档为准
  * scrollLeftLift和scrollLeftTop 页面/元素被卷去的头部和左侧，可读写

## 日期对象

* 日期对象：用来表示日期和时间对象
* 作用：可以得到当前系统的日期和时间
* 用法：
  * const date = new Date（'指定日期和时间'）
* 格式化日期对象
  * getFullYear() 获得年份
  * getMonth() 获得月份 取值为 0~11
  * getDate() 获得当前是几号
  * getDay() 获得星期 取值为 0~6
  * getHours() 获得小时
  * getMinutes() 获得分钟
  * getSeconds() 获得秒
  * toLocaleString 返回该日期对象的字符串（包含日期和时间）
  * toLocaleDateString 返回日期对象日期部分字符串
  * toLocaleTimeString 返回日期对象时间部分字符串
* 时间戳
  * 从1979年1月1日00时00分00秒到现在的总毫秒数
  * 获取时间戳
    * 日期对象.getTime()
    * +new Date（）
    * Date.now() 只能得到当前时间的时间戳
  * 时间转换公式
    * 毫秒转秒
      * 毫秒/1000
    * h = parseInt（总秒数/60/60%24）
    * m = parseInt（总秒数/60%60）
    * s = parseInt（总秒数%60）

## DOM 节点

* DOM 树：DOM将HTML文档以树状结构直观的表现出来

* 节点：是DOM树中的单个点

* 节点类型：元素、属性、文本

* 查找节点

  * 利用节点关系查找节点，返回的都是对象
  * 父节点查找
    * 子元素.parentNode 返回最近一级父节点对象，找不到返回null
  * 子节点查找
    * 节点对象.children 返回的是一个伪数组
    * 节点对象.previousEiementSibling 上一个兄弟
    * 节点对象.nextEiementSibling 上一个兄弟
  * 增加节点
    * 创建节点
      * document.createElement("标签名")
    * 追加节点
      * 元素.append() 添加到后面
      * 元素.prepend() 添加到前面
    * 删除节点
      * 元素.remove()
  * M端（移动端）事件
    * 触屏事件
      * touchstart 手指触摸到一个DOM元素时触发
      * touchmove 手指在一个DOM元素上滑动时触发
      * touchend 手指从一个DOM元素上移开时触发

  ## 插件-swiper

  ## 插件-AlloyFinger

  

## BOM

* BOM：浏览器对象模型，定义了一套操作浏览器窗口的API
* window对象是一个全局对象，也可以说是JavaScript中的顶级对象
* 所有通过var定义在全局作用域中的变量、函数都会变成window对象的属性和方法

### 定时器-延迟函数

* 语法：setTimeout（回调函数，等待毫秒数）
* 只执行一次
* 清楚延时函数
  * clearsetTimeout（定时器）

## location 对象

* location（地址）它拆分并保存了URL地址的各个组成部分，它是一个对象
* 常用属性和方法
  * href 获取完整的URL地址，赋值时用于地址的跳转
  * search 获取地址中携带的参数，符号？后面的部分
  * hash 获取地址中的哈希值，符号#后面的部分
  * reload（）用来刷新当前页面，传入参数true是表示强制刷新

## navigator对象

* 该对象下记录了浏览器自身的相关信息
* 常用属性和方法
  * 通过userAgent检测浏览器的版本即平台

## histroy对象

* 主要管理历史记录，该对象与浏览器地址栏的操作相对应
* 常见方法
  * back（）后退
  * forward（）前进
  * go（值）值是整数为前进，负数为后退

## 本地存储

* 将数据存储在本地浏览器中
* 好处
  * 页面刷新或者关闭不丢失数据，实现数据持久化
  * 容量较大，sessionStorage和localStorage约5M左右
* 特性：以键值对的形式存储，并且存储的是字符串
* 语法
  * 存储
    * localStorage.setitem(key,value)
  * 读取
    * localStorage.getitem(key,vaslue)
  * 删除
    * localStorage.removeitem(key)
* 复杂数据本地存储
  * 先转换为JSON字符串
  * 语法
    * JSON.strlngify（复杂数据）
    * 把JSON字符串转换为对象
      * JSON.parse（JSON字符串）

## 正则表达式

* 是一种字符串匹配的模式（规则）
* 定义正则表达式
  * / 匹配规则/
* 使用正则
  * test方法 包含内容 为true
  * 普通字符
    * 大多数字符仅能够描述它们本身
    * 普通字符只能够匹配字符串中与他们相同的字符
  * 元字符
    * 是一些具有特殊含义的字符，可以极大提高了灵活性和强大的匹配功能
    * 边界符
      * ^表示匹配行首的文本（以谁开始）
      * $表示匹配行尾的文本（以谁结束）
      * 他俩一起，表示精准匹配
    * 量词
      * \*  重复零次或更多次
      * \+ 重复一次或更多次
      * ? 重复零次或一次
      * {n} 重复n次
      * {n,} 重复n次或更多次
      * {n,m} 重复n次到m次
    * 范围
      * []表示范围
      * [abc] 匹配包含的单个字符
      * [a-z] 连字符 来制定字符的范围
      * [^abc] 去反符 匹配除了里面以外的字符
    * 字符类
      * \d 匹配0-9之间的任一数字
      * \D 匹配0-9以外的字符
      * \w 匹配任意字符、数字和下划线
      * \W 除所有字母、数字和下划线以外的字符
      * \s 匹配空格（包含换行、制表、空格）
      * \S 匹配除空格的字符
    * 替换和修饰符
      * 替换语法
        * 字符串.replace(正则表达式，替换文本)
      * 修饰符语法
        * /表达式/修饰符
        * i ignore的缩写 ，正则匹配时字母不区分大小写
        * g global的缩写，匹配所有满足正则表达式的结果
