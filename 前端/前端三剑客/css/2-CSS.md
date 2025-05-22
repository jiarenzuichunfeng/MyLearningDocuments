# CSS

* CSS定义
  * 层叠样式表，用来美化HTML

## 基础选择器

### 标签选择器

* 使用标签名作为选择器-》选中同名标签设置相同的样式

### 类选择器

* 定义类选择器
  * .类名
* 使用类选择器
  * 要用到的标签属性，添加一个class=“要引用的类选择器名称”

### id选择器

* 定义id选择器
  * #id名
* 使用id选择器
  * 要用到的标签属性，添加一个id=“要引用的id选择器名称”

### id选择器与类选择器的区别

* id只能用一次，类可以复用

### 通配符选择器

* *

## 文字控制属性

* 字体大小 font-size
* 字体粗细 font-weight
* 字体倾斜 font-style
* 行高 line-height
* 字体 font-family
* 字体复合属性 font
  * 是否倾斜 是否加粗 字号/行高 字体
* 文本缩进 text-indent
  * 1em = 当前标签的字号大小
* 文本对齐 text-align
  * left 左对齐（默认）
  * center 居中对齐
  * right 右对齐
* 修饰线 text-decoration
  * none 无
  * underline 下划线
  * line-through 删除线
  * overline 上划线
* 颜色 color
  * 颜色关键字
  * rgb表示法
  * tgba表示法
    * a表示透明度

  * 十六进制表示法


## 复合选择器

* 定义： 有两个或多个基础选择器，通过不同的方式组合而成

### 后代选择器

* 父选择器 子选择器，父子选择器之间用空格隔开

### 子代选择器

* 父类选择器 > 子类选择器，父子选择器之间用大于号隔开

### 并集选择器

* 选择器1,选择器2,...,选择器N,选择器之间用,隔开

### 交集选择器

* 选择器1选择器2，选择器之间连写，没有任何符号
* 标签选择器必须书写在前面

### 伪类选择器

* 伪类-超链接
  * ：link 访问前
  * ：visited 访问后
  * ：hover 鼠标悬停时
  * ：active 点击时

### 结构伪类选择器

* E：first-child 查找第一个E元素
* E：last-child 查找最后一个E元素
* E：nth-child（N）查找第N个E元素
  * N可以是公式
    * 偶数标签 2n
    * 奇数标签 2n+1；2n-1
    * 找到5的倍数的标签 5n
    * 找到第5个以后得标签 n+5
    * 找到第5个以前的标签 -n+5
* E：not（） 否定伪类 除了第n项
* E是标签名

### 伪元素选择器

* 作用：创建虚拟元素，用来摆放装饰性内容
* E：：before 在E元素里边最前面添加一个伪元素
* E：：after 在E元素里面最后面添加一个伪元素
* E：：first-letter 第一个元素
* E：：first-letter 第一个行 只能用于块级元素
* E：：selection 选中
* 注意点
  * 必须设置content：“”属性，用来设置伪元素的内容，如果没有内容，则引号为空
  * 伪元素默认是行内显示模式
  * 权重和标签选择器相同

## CSS特性

* 继承
  * 子级默认继承父级的文字控制属性
* 层叠
  * 相同的属性会覆盖
    * 后面的CSS属性会覆盖前边的CSS属性
  * 不同的属性会叠加
    * 不同的CSS属性都生效
* 优先
  * 通配符<标签<类<id<行内<！important
  * 选择标签的范围越大，优先级越低
  * 权重叠加计算规则
    * 行内，id，类，标签
    * 从左向右依次比较个数，同一级个数多的优先级高，个数相同则向后比较
    * ！important权重最高
    * 继承权重最低

## Emmet写法

* 类选择器
  * 标签名.类名
* id选择器
  * 标签名#id名
* 同级标签
  * 标签名+标签名
* 父子级标签
  * 标签名>标签名
* 多个相同的标签
  * 标签名*个数
* 有内容的标签
  * 标签名{内容}

## 背景属性

* background-color 背景色
* background-image 背景图片 bgi
* background-repeat 背景平铺方式 bgr
  * no-repeat 不平铺
  * repeat 平铺（默认）
  * repeat-x 水平方向平铺
  * repeat-y 垂直方向平铺

* background-posistion 背景图位置 bgp
  * 属性值：水平方向 垂直方向
  * 关键字
  * 坐标
    * 水平：正数向右；负数向左
    * 垂直：正数向下；负数向上

  * 提示
    * 关键字取值方式写法，可以颠倒取值顺序
    * 可以只写一个关键字，另一个方向默认居中；数字只写一个值表示水平方向，垂直方向默认居中

* background-size 缩放 bgz
  * 属性值：
    * 关键字
      * cover：等比例缩放背景图以完全覆盖背景区，可能背景图片部分看不见
      * contain：等比例缩放背景图片以完全装入背景区，可能背景区部分空白

    * 百分比：根据盒子尺寸计算图片大小
    * 数字+单位

* background-attachment 背景图固定 bga
  * 属性值：fixed

* background 背景复合属性 bg
  * 背景色、背景图、背景图平铺方式、背景图位置/背景图缩放、背景图固定；空格隔开各属性值


## 显示模式

* 块级元素
  * 独占一行
  * 宽度默认是父级的100%
  * 添加宽高属性生效
* 行内元素
  * 一行共存多个
  * 尺寸由内容撑开
  * 添加宽高属性不生效
* 行内块元素
  * 一行共存多个
  * 默认尺寸由内容撑开
  * 添加宽高属性生效
* 转换显示模式
  * display
    * block 块级
    * inline-block 行内块
    * inline 行内

## 盒子模型

* w3c标准模型
  * boxWidth=contentWidth
* IE标准模型
  * box-sizing：border-box
  * boxWidth=contentWidth+border+padding

* 组成
  * 内容区域 width & height
  * 内边距 padding/padding-方位名词 pd
  * 边框线 border bd
    * 边框线的粗细 线条样式 颜色
    * 常用的线条样式
      * solid 实线
      * dashed 虚线
      * dotted 点线
    * 单方向边框线
      * border-方位名词
  * 外边距 margin/margin-方位名词 mg
* 尺寸计算
  * 默认情况
    * 盒子尺寸=内容情况+border尺寸+内边距尺寸
    * 内减模式：box-sizeing；border-box
* 元素溢出
  * 属性名：overflow
  * 属性值
    * hldden 溢出隐藏
    * scroll 溢出滚动（显示滚动条）
    * auto 溢出滚动（溢出才显示滚动条）
* 外边距问题
  * 合并问题
    * 上盒子设置下边距，下盒子设置上边距，结果会造成外边距合并，外边距的值是俩盒子最大的值
  * 塌陷问题
    * 父盒子，里边的子盒子设置了上外边距，会造成父盒子向下移动
    * 解决问题
      * 取消子盒子的margin，父级设置padding
      * 父级设置 overflow：hidden
      * 父级设置 border-top
* 行内元素-内外边距问题
  * 场景：内外元素添加margin和padding，无法改变元素的垂直位置
  * 解决方法：给行内元素添加line-height 可以改变垂直位置
* 圆角
  * 属性名：border-radius
  * 属性值：数字+px或百分比
* 阴影
  * 属性名：box-shadow
  * 属性值：x轴偏移量 y轴偏移量 模糊半径 扩散半径 颜色 内外阴影（默认是外阴影，内阴影inset）

## 浮动

* 标准流

  * 标准流也叫文档流，指的是标签在页面中默认的排布规则

* 属性名：float

* 属性值：

  * left：左对齐
  * right：右对齐

* 特点

  * 浮动后的盒子顶对齐
  * 浮动后的盒子具备行内块特点
  * 父级宽度不够，浮动的子级会换行
  * 浮动后的盒子脱标

* 清除浮动

  * 浮动元素会脱标，如果父级没有高度，子级无法撑开父级高度（可能导致页面布局错乱）

  * 额外标签法

    * 在父元素内容的最后添加一个块元素，设置css属性clear：both

  * 单伪元素法

    * 在父元素的最后加伪元素标签

      ```CSS
      .类名::after{
        content:"";
        display:block;
        clear:both;
      }
      ```

  * 双伪元素法

    * 在父元素开头和结尾都加伪元素标签

      ```CSS
      .类名::before,
      .类名::after{
        content:"";
        display:table;
      }
      .类名::after{
          clear:both;
      }
      ```

  * 父元素添加CSS属性oberflow：hidden

## Flex布局

* Flex布局也叫弹性布局，是浏览器提倡的布局模型，非常适合结构化布局，提供了强大的空间分布和对齐能力
* Flex模型不会产生浮动布局中脱标现象，布局网页更简单、更灵活。
* Flex组成
  * 设置方式：给父元素设置display：flex，子元素可以自动挤压或拉伸
  * 主轴：默认在水平方向
  * 侧轴：默认在垂直方向
  * 水平对齐方式：justify-content
    * flex-start 默认值，弹性盒从起点开始依次排列
    * flex-end 弹性盒从终点开始依次排列
    * center 弹性盒沿主轴居中排列
    * space-between 弹性盒沿主轴均匀排列，空白间距均分在弹性盒之间
    * space-around 弹性盒沿主轴均匀排列，空白间距均分在弹性盒两侧
    * space-evenly 弹性盒沿主轴均匀排列 弹性盒与容器之间间距相等
  * 垂直对齐方式：align-items / 某个弹性盒子侧轴对齐方式:align-self
    * stretch 弹性盒沿着侧轴被拉伸至铺满容器（弹性盒没有设置侧轴方向尺寸则默认拉伸）
    * center 弹性盒侧轴居中
    * flex-start 弹性盒从起点依次排序
    * flex-end 弹性盒从终点依次排序
    * baseline 以文本的基准线进行排版
  * 定义多个轴线（多行/多列）对齐方式
    * align-content
      * flex-start 
      * flex-end
      * center
      * space-between
      * space-around
      * stretch
  * 修改主轴方向:flex-direction
    * row 水平方向，从左向右（默认）
    * column 垂直方向，从上向下
    * row-reverse 水平方向，从右向左
    * column-reverse 垂直方向，从下向上
  * 弹性伸缩比：flex
    * 属性值：整数数字，表示占用父级剩余尺寸的份数
  * 弹性盒子换行：flex-wrap
    * wrap 换行
    * nowrap 不换行（默认）
    * wrap-reverse 颠倒换行
  * 行对齐方式：align-content
    * flex-start 默认值，弹性盒从起点开始依次排列
    * flex-end 弹性盒从终点开始依次排列
    * center 弹性盒沿主轴居中排列
    * space-between 弹性盒沿主轴均匀排列，空白间距均分在弹性盒之间
    * space-around 弹性盒沿主轴均匀排列，空白间距均分在弹性盒两侧
    * space-evenly 弹性盒沿主轴均匀排列 弹性盒与容器之间间距相等
  * 子元素容器的属性
    * 定义子元素的排列顺序，默认为0
      * order -10~0~10
    * 定义子元素的放大比例，默认为0
      * flex-grow 0~3
    * 定义子元素的缩小比例，默认为1
      * flex-shrink 0~1
    * 定义 了在分配多余空间之前，项目占据的主轴空间
      * flex-basis：<length> | auto
    * 符合属性
      * flex：flex-grow flex-shrink flex-basis

## 定位

### 相对定位

* position：relative  
  * 属性
    * left
    * right
    * top
    * bottom
  * 特点
    * 改变位置的参照物是该物体原来的位置
    * 不脱标，占位
    * 标签显示模式不变

### 绝对定位

* 使用场景：子级绝对定位，父级相对定位

* position：absolute
  * 属性
    * left
    * right
    * top
    * bottom
  * 特点
    * 脱标，不占位
    * 先找距离自己最近已定位的祖先元素，没有则参照浏览器（父级添加相对定位，如果不添加相对定位则会参照浏览器）
    * 显示模式改变，宽高生效

### 定位居中

* 实线步骤
  * 绝对定位
  * 水平、垂直边偏移50%
  * 子级向左、上移动自身尺寸的一半
    * 左、上的外边距为-尺寸的一半
    * margin-left:盒子宽的一半，margin-top:盒子高的一半
    * transform:translate(-50%,-50%)

### 固定定位

* 元素的位置在网页滚动是不会改变
* position：fixed
  * 属性
    * left
    * right
    * top
    * bottom
  * 特点
    * 脱标，不占位
    * 参照物是浏览器
    * 显示模式是行内块

### 粘性定位

* 元素到了顶部就不会再滚动了
* position：sticky

### 层叠属性

* z-index：取值是整数，取值越大越在上边
  * 默认效果：按照标签的书写顺序，后来者居上
  * 作用：设置定位元素的层级顺序

## CSS 精灵

* CSS精灵，是一种网页图片应用处理方式，把网页中一些背景图片整合到一张图片文件中，再background-position精确的定位出背景图片的位置
* 优点：减少服务器被请求的次数，减轻服务器压力，提高页面加载速度

## 字体图标

* 字体图标：展示的是图标，本质是字体
* 作用：在网页中添加简单的、颜色单一的小图标
* 优点：
  * 灵活性：灵活的修改样式
  * 轻量级：体积小、渲染快、降低服务器压力
  * 兼容性：几乎兼容所有主流浏览器
  * 使用方便:先下载再使用

* 垂直对齐方式
  * vertical-align
    * 属性值
      * baseline 基线对齐
      * top 顶部对齐
      * middle 居中对齐
      * bottom 底部对齐

* 过渡 transition
  * 作用：可以为一个元素在不同状态之间切换的时候添加过度效果
  * 属性名：transition（复合属性）
  * 属性值：过渡的属性 花费的时间（s）
    * 过渡的属性可以是具体的css属性
    * 也可以为all（两个状态属性值不同的所有属性，都产生过渡效果）
    * transition 设置给元素本身

* 透明度 opacity
  * 作用：设置整个元素的透明度（包含背景和内容）
  * 属性值
    * 0 完全透明
    * 1 不透明
    * 0~1之间的小数 半透明

* 光标类型 cursor
  * 属性值
    * defauit 默认值，箭头
    * pointer 小手，可以点击
    * text 工字型，可以选中问下
    * move 十字光标，可以移动

## CSS水平垂直居中

### 行内块元素

* line-height = 高度
* text-align：center
* display：flex
  justify-content：center
  align-items：center

### 块元素

* position+mrging 清楚子元素高度
* position + transform 不清楚子元素高度
* flex
