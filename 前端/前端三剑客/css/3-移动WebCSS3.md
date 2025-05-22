# 移动WebCSS3

## 平面转换 transform

* 作用：为元素添加动态效果，一般与过渡配合使用
* 概念：改变盒子在平面内的形态（位移、旋转、缩放、倾斜）

### 平面转换 - 平移

* transform：translate（x轴移动距离，y轴移动距离）

  * 取值是百分比，参照的是盒子自身的尺寸

* 平移实现屏幕居中效果

  ``` css
  position:avsolute;
  left:50%;
   top:50%;
  transform：translate（-50%，-50%）
  ```

### 平面转换 -  旋转

* transform：rotate（旋转角度）（单位是deg）

#### 改变旋转点

* 默认情况下，转换原点是元素中心点
* transform-origin：水平原点位置 垂直原点位置
  * 取值：
    * 方位名词
    * 像素单位数值
    * 百分比

### 平面转换 - 多重转换

* 多重转换技巧：要先平移再旋转
* transform：translate（） rotate（）

### 平面转换 - 缩放

* 用宽度和高度加上过渡效果实现缩放效果（效果不是很好）

* transform：scale（缩放倍数）
* transform：scale（x轴缩放倍数，y轴的缩放倍数）
* 取值范围
  * 0-1缩小
  * 1 不变
  * 1-无穷 放大
* 通常只用一个值，表示等比例缩放

### 平面转换 - 倾斜

* transform：skew（角度度数deg）

## 渐变

* 渐变是多个颜色逐渐变化的效果，一般用于设置盒子背景

### 线性渐变

```css
background-image:linear-gradient{
  渐变方向，
  颜色1 终点位置，
  颜色2 终点位置，
  ……
}
```

* 取值
  * 渐变方向：可选
    * to 方位名词
    * 角度度数
  * 终点位置：可选
    * 百分比

### 径向渐变

* 作用：给按钮添加高光效果

  ```css
  background-image:radial-gradient{
     半径 at 圆心位置，
      颜色1 终点位置，
      颜色2 终点位置，
      ……
  }
  ```

* 取值	

  * 半径可以是2条，则为椭圆
  * 圆心位置取值：像素单位数值/百分比/方位名词

## 空间转换

### 空间平移

* transform：translate3d（x，y，z）
  * transform：tranlateX（）
  * transform：tranlateY（）
  * transform：tranlateZ（）
* 取值
  * 像素单位数值
  * 百分比（参照盒子自身尺寸计算结果）
* 视距 perspective
  * 作用：指定了观察者与Z=0平面的距离，为元素添加透视效果
  * 透视效果：近大远小，近实远虚
  * 属性：添加给父级，建议取值范围800-1200
  * 视距属性必须添加给直接父级属性，否则不生效

### 空间旋转

* transform：rotateX（值）需要添加一个视距
* transform：rotateY（值）需要添加一个视距
* transform：rotateZ（值）平面旋转
* transform3d（x，y，z，角度度数） 用来设置自定义旋转轴的位置以及旋转角度
  * x，y，z取值为0-1之间的数字

### 立体呈现

* 作用：设置元素的子元素是位于3D空间中还是平面中
* transform-style
  * 属性值：
    * flat：子级处于平面中
    * preserve-3d：子级处于3D空间

### 缩放

* transform：scale3d（x，y，z）
* transform：scaleX（）
* transform：scaleY（）
* transform：scaleZ（）

## 动画 - animation

* 过渡和动画的区别

  * 过渡：实现两个状态之间的变化过程
  * 动画：实现多个状态间的变化过程，动画过程可控（重复播放，最终画面、是否暂停）

* 动画的实现步骤

  * 定义动画

    ```CSS
    @keyframes 动画名称 {
      from{开始状态}
      to{结束状态}
    }
    
    @keyframes 动画名称 {
      0%{初始状态}
      10%{改变后状态}
     	 ……
      100%{结束状态} // 100% 表示动画时长的百分比
    }
    ```

  * 使用动画

    * animation：动画名称 动画花费的时长 速度曲线 延迟时间 重复次数 动画方向 执行完毕时状态；
      * 速度曲线
        * linear 匀速
        * steps（整数）分步 常用于精灵动画
      * 重复次数
        * 整数
        * infinite 无穷
      * 动画方向
        * alternate 反向
      * 执行完毕时状态
        * forwards 停在动画结束状态
    * 动画名称和动画时长必须赋值
    * 取值不分先后顺序
    * 如果有两个时间值，第一个时间表示动画时长，第二个时间表示延迟时间
    * animation-name 动画名称
    * animation-duration 动画时长
    * animation-delay 延迟时间
    * animation-fill-mode 动画执行完毕时的状态
      * forwards 最后一帧状态
      * backwards 第一帧状态
    * animation-timing-function 速度曲线
      * steps（数字） 逐帧动画
    * animation-iteration-count 重复次数
      * infinite 为无限循环
    * animation-direction 动画执行方向
      * alternate 为反向
    * animation-play-state 暂停动画
      * paused 为暂停，通常配合：hover使用

### 多组动画

* animation：动画1，动画2，动画n；
